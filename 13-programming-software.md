# Chapter 13: Programming Languages and Software Development

## Why Software Matters

Hardware is potential. Software is realization. The most powerful computer is useless without software to direct it. Software is:
- **Instructions**: Telling hardware what to do
- **Algorithms**: Efficient methods for solving problems
- **Abstraction**: Managing complexity
- **Automation**: Making computers useful

Post-collapse, you'll need to write enormous amounts of software:
- Operating systems
- Compilers and interpreters
- Applications (editors, spreadsheets, databases)
- Scientific computation
- Control systems
- Communication software

This chapter teaches you how to build the software tools and applications needed to rebuild civilization.

## Machine Code: The Foundation

### Binary Instructions

**Every program** ultimately becomes machine code—binary instructions the CPU executes directly.

**Example** (Hypothetical 8-bit CPU):
```
Address  Machine Code  Assembly       Meaning
0000     00110001      LDA $50        Load accumulator from address $50
0001     01010000                     (address operand)
0002     00110010      ADD $51        Add value at address $51
0003     01010001                     (address operand)
0004     00110011      STA $52        Store accumulator at address $52
0005     01010010                     (address operand)
0006     11110000      HLT            Halt
...
0050     00000101      (data: 5)
0051     00000011      (data: 3)
0052     00000000      (result location)
```

**When Executed**: Loads 5, adds 3, stores 8 at location $52, then halts.

**Programming in Machine Code**:
- Tedious and error-prone
- Hard to modify
- Difficult to debug
- But: Necessary for the very first program on a new computer

**Historical Example**: ENIAC (1945) was programmed by physically setting switches and cables. First stored-program computers (late 1940s) were programmed in raw binary, toggled in via switches.

## Assembly Language: Human-Readable Machine Code

### What Assembly Is

**Assembly Language**: Symbolic representation of machine code
- Mnemonics instead of binary: `LDA` instead of `00110001`
- Labels instead of addresses: `loop:` instead of $0020
- Comments: Explain what code does
- Symbolic constants: `COUNT EQU 10` instead of magic numbers

**Same Program in Assembly**:
```assembly
        LDA num1     ; Load first number
        ADD num2     ; Add second number
        STA result   ; Store result
        HLT          ; Halt

num1:   DB 5         ; Data Byte: 5
num2:   DB 3         ; Data Byte: 3
result: DB 0         ; Result location
```

**Much More Readable**: Purpose is clear from mnemonics and labels.

### Assembler

**Assembler**: Program that converts assembly language to machine code

**Two-Pass Assembler** (Standard Approach):

**Pass 1**: Build symbol table
1. Read source file line by line
2. Track current address (location counter)
3. For each label: Record label name and address
4. For each instruction/data: Increment location counter by instruction size
5. Result: Symbol table mapping labels to addresses

**Pass 2**: Generate machine code
1. Read source file again
2. For each instruction:
   - Look up opcode (mnemonic → binary)
   - Look up operand address in symbol table (if label)
   - Emit machine code
3. Write output file (binary or hex format)

**Example Symbol Table**:
```
Label    Address
num1     $0007
num2     $0008
result   $0009
```

**Example Pass 2 Output**:
```
Address  Machine Code
0000     00110001     (LDA)
0001     00000111     (address $07 = num1)
0002     00110010     (ADD)
0003     00001000     (address $08 = num2)
0004     00110011     (STA)
0005     00001001     (address $09 = result)
0006     11110000     (HLT)
0007     00000101     (5)
0008     00000011     (3)
0009     00000000     (0)
```

**Writing Your First Assembler**:
1. Choose target CPU (or your custom design)
2. Define opcode table: Mnemonic → binary value
3. Write parser: Read assembly source, tokenize
4. Implement Pass 1: Build symbol table
5. Implement Pass 2: Generate code
6. Test with simple programs

**Language**: Can write assembler in any language
- Initially: Hand-written in machine code (painful but necessary for first assembler)
- Later: Written in assembly (self-hosting)
- Eventually: Written in higher-level language (once available)

**Effort**: 1,000-5,000 lines of code for basic assembler

### Assembly Language Programming

**Advantages**:
- Full control over hardware
- Maximum efficiency
- Small code size
- Direct access to all CPU features

**Disadvantages**:
- Tedious for large programs
- Not portable (CPU-specific)
- Hard to maintain
- Easy to make mistakes

**Uses**:
- Operating system kernels
- Device drivers
- Performance-critical code
- Embedded systems
- Bootstrapping (first program on new system)

**Example: Multiply by Repeated Addition**:
```assembly
; Multiply A * B, result in accumulator
; Destroys B register
        LDA #0         ; Accumulator = 0
        LDB count      ; Load count
multiply_loop:
        ADD value      ; Add value to accumulator
        DEC B          ; Decrement counter
        JNZ multiply_loop ; Jump if not zero
        STA result
        HLT

value:  DB 7           ; Value to multiply
count:  DB 6           ; Multiplier
result: DB 0           ; Result (will be 42)
```

## High-Level Languages: Abstraction and Productivity

### Why High-Level Languages

**Assembly is Tedious**: Even simple programs are hundreds of lines
**Not Portable**: Rewrite for every CPU
**Hard to Maintain**: Difficult to understand others' assembly code

**High-Level Languages** Provide:
- **Abstraction**: Express ideas naturally, not machine operations
- **Portability**: Write once, compile for multiple architectures
- **Productivity**: 10-100× fewer lines of code
- **Maintainability**: Easier to read and modify

**Trade-off**: Slightly less efficient code (but compiler optimization helps)

### Interpreted vs. Compiled

**Interpreted Language**:
- Source code read and executed directly
- Interpreter translates and executes on-the-fly
- Examples: BASIC, Python, JavaScript, Lisp
- Advantages: Interactive, easy to debug, rapid development
- Disadvantages: Slower execution

**Compiled Language**:
- Source code translated to machine code once
- Compiled program runs directly on CPU
- Examples: C, C++, Fortran, Pascal
- Advantages: Fast execution
- Disadvantages: Compile step, harder to debug

**Hybrid** (JIT - Just-In-Time):
- Compile during execution
- Examples: Java (JVM), C# (.NET), modern JavaScript
- Balance between interpreted and compiled

### BASIC: The Beginner's Language

**BASIC** (Beginners' All-purpose Symbolic Instruction Code, 1964):
- Designed for teaching
- Simple syntax
- Interactive (line-by-line execution)
- Interpreted (fast to write interpreter)

**Example Program**:
```basic
10 PRINT "Enter two numbers"
20 INPUT A, B
30 LET C = A + B
40 PRINT "Sum is"; C
50 END
```

**Features**:
- Line numbers (10, 20, 30...) for ordering and jumps
- Simple commands: PRINT, INPUT, LET, IF, GOTO, FOR, GOSUB
- Variables: Single letter (A-Z) or letter + digit (A1, B2)
- Minimal typing required

**Implementing BASIC Interpreter**:

**Components**:
1. **Tokenizer**: Convert text to tokens
   - Keywords: PRINT, INPUT, LET, IF, GOTO, etc.
   - Numbers: 123, 45.67
   - Operators: +, -, *, /, =, <, >
   - Variables: A, B, X1, etc.

2. **Parser**: Analyze syntax
   - Line number first
   - Statement: Command + arguments
   - Expression: Numbers, variables, operators

3. **Executor**: Run statements
   - Store lines in array or linked list (sorted by line number)
   - Symbol table: Variable name → value
   - Execute: Start from lowest line number, run each statement
   - Commands modify symbol table, control flow, or perform I/O

**Example Execution**:
```
Line 10: PRINT "Hello"
  → Output "Hello" to terminal
Line 20: LET A = 5
  → Symbol table: A = 5
Line 30: PRINT A
  → Look up A in symbol table (5), output "5"
```

**Effort**: 2,000-5,000 lines (in C or assembly) for basic interpreter

**Advantages of BASIC for Post-Collapse**:
- Easy to implement
- Familiar to many (or well-documented)
- Interactive (good for learning and quick programs)
- Adequate for many tasks

**Disadvantages**:
- Slow (interpreted)
- Poor structure (GOTO leads to spaghetti code)
- Limited data structures
- Not suitable for large programs

**Recommendation**: Implement BASIC early. Use for education, simple tools, calculators, data processing.

### C: The Systems Language

**C** (Developed 1972, Dennis Ritchie):
- Low-level access (like assembly)
- High-level constructs (like other languages)
- Portable (compiles for many CPUs)
- Efficient (compiled)
- Used for Unix, Linux, most operating systems

**Example Program**:
```c
#include <stdio.h>

int main() {
    int a, b, c;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);
    c = a + b;
    printf("Sum is %d\n", c);
    return 0;
}
```

**Features**:
- **Variables**: Typed (int, float, char, etc.)
- **Pointers**: Direct memory access
- **Functions**: Modular code
- **Structures**: Composite data types
- **Preprocessor**: Macros, file inclusion
- **Standard Library**: I/O, string handling, math, etc.

**Implementing C Compiler**:

**Extremely Complex**: Thousands to tens of thousands of lines

**Stages**:
1. **Preprocessor**: Handle #include, #define, #if, etc.
2. **Lexer**: Tokenize source code
3. **Parser**: Build Abstract Syntax Tree (AST)
4. **Semantic Analysis**: Type checking, symbol resolution
5. **Optimization**: Improve code (optional but important)
6. **Code Generation**: Convert AST to assembly or machine code
7. **Linker**: Combine object files, resolve external symbols

**Challenges**:
- Complex syntax (pointers, declarations, etc.)
- Type system
- Optimization (naive compilation produces slow code)
- Standard library (large)

**Effort**: 50,000-200,000 lines for full-featured compiler

**Alternative: Cross-Compilation**:
- Use salvaged modern computer with existing C compiler (GCC, Clang)
- Compile programs for target architecture
- Transfer binary to target
- Much easier than writing compiler from scratch

**Once You Have C**:
- Write operating systems
- Write other compilers (for C++ Python, etc.)
- Write applications (editors, shells, utilities)
- Write almost anything

**Recommendation**: Cross-compile initially. Write native compiler only when:
- You have stable computer to develop on
- You have team of skilled programmers
- You need to bootstrap from nothing (no modern computers available)

### Forth: The Minimalist Language

**Forth** (1970, Charles Moore):
- Stack-based
- Minimal interpreter (can fit in <1 KB)
- Extensible (define new words)
- Interactive
- Used in embedded systems, bootloaders

**Example**:
```forth
: square  dup * ;         ( Define word "square": duplicate and multiply )
5 square .                ( Push 5, call square, print result: 25 )

: add-three  + + ;        ( Add three numbers )
2 3 4 add-three .         ( Result: 9 )

: countdown               ( Countdown from n to 0 )
  begin dup . 1 - dup 0< until drop ;
10 countdown              ( Prints: 10 9 8 7 6 5 4 3 2 1 0 )
```

**Features**:
- **Reverse Polish Notation**: `2 3 +` instead of `2 + 3`
- **Stack**: Primary data structure
  - Push numbers, operations consume and produce on stack
- **Words**: Functions defined by sequence of operations
- **Dictionary**: Linked list of word definitions
- **Extensible**: Define words in terms of other words

**Implementing Forth**:
1. **Primitives**: Basic operations (+, -, *, /, dup, swap, drop, etc.)
2. **Dictionary**: List of words with addresses of code
3. **Inner Interpreter**: Execute words
4. **Outer Interpreter**: Parse input, compile or execute
5. **Return Stack**: For control flow (loops, conditionals, calls)

**Effort**: 500-2,000 lines of assembly

**Advantages**:
- Tiny (fits in very small memory)
- Fast (compiled, minimal overhead)
- Interactive
- Self-hosting (Forth written in Forth)
- Good for embedded systems

**Disadvantages**:
- Unusual syntax (stack-based)
- Cryptic (hard to read for beginners)
- Easy to make stack errors

**Recommendation**: Consider Forth for:
- Embedded systems (minimal resources)
- Bootstrapping (write tiny Forth kernel in assembly, expand from there)
- Interactive control systems

### Other Important Languages

**Fortran** (1957, First High-Level Language):
- Scientific computing
- Array operations
- Fast floating-point math
- Still used in supercomputing, physics, engineering

**Lisp** (1958, AI and Symbolic Computation):
- Recursive, functional
- Code is data (S-expressions)
- Interpreted (usually)
- Used in AI, theorem proving

**Pascal** (1970, Teaching Language):
- Structured, strongly typed
- Clear syntax
- Used in education, systems programming (Turbo Pascal)

**Python** (1991, Modern Scripting):
- Clear, readable syntax
- Extensive libraries
- Interpreted
- Widely used (by 2025) for scripting, data science, web, automation

**JavaScript** (1995, Web Language):
- Client-side web scripting
- Also server-side (Node.js)
- Event-driven
- Ubiquitous on web

**Recommendation for Post-Collapse**:
- **Immediately**: Assembly (for bootstrapping)
- **Years 1-10**: BASIC and/or Forth (simple interpreters)
- **Years 10-20**: C (via cross-compilation)
- **Years 20+**: C++ (object-oriented), Python (productivity), others as needed

## Operating Systems

### What an Operating System Does

**Operating System (OS)**: Software that manages hardware and provides services to applications

**Functions**:
1. **Process Management**: Run multiple programs
2. **Memory Management**: Allocate and protect memory
3. **File Systems**: Organize data on storage
4. **Device Drivers**: Interface with hardware
5. **User Interface**: Shell (command-line) or GUI
6. **Networking**: TCP/IP stack, network services

### Minimal OS

**Bare-Bones OS** (For Early Computer):
1. **Boot Loader**: Loads OS from storage into memory
2. **Kernel**: Core OS code
   - Initialize hardware
   - Provide API for programs (system calls)
3. **Shell**: Command-line interface
4. **Basic Utilities**: Load, save, list files

**Example**: Monitor Program
- Simple OS for early microcomputers
- Commands: Examine/modify memory, load/save to tape, run program
- <1 KB of code

### Monolithic Kernel

**Examples**: Unix, Linux, early Windows

**Structure**:
- All OS code runs in kernel mode (full hardware access)
- System calls provide interface to applications

**Components** (Typical Unix-like):
- **Scheduler**: Decides which process runs
- **Memory Manager**: Virtual memory, paging
- **File System**: inodes, directories, read/write
- **Device Drivers**: Keyboard, disk, network, etc.
- **System Call Interface**: open, read, write, fork, exec, etc.

**Advantages**:
- Fast (no context switches between components)
- Simple design

**Disadvantages**:
- Bug in driver can crash entire system
- Large, monolithic codebase

### Microkernel

**Examples**: Minix, QNX, seL4

**Structure**:
- Minimal kernel (scheduling, IPC, basic memory management)
- Other services (file system, drivers) run as user processes
- Communication via message passing

**Advantages**:
- Modular
- More robust (driver crash doesn't crash kernel)
- Easier to debug

**Disadvantages**:
- Slower (message passing overhead)
- More complex

### Building a Simple OS

**Start Small**: Don't try to build Linux from scratch

**Minimal OS** (Few Thousand Lines):
1. **Boot**: Load kernel into memory, jump to it
2. **Initialize**: Set up interrupts, memory, devices
3. **Shell**: Read command, execute
4. **System Calls**: open, read, write, exec
5. **File System**: Simple (flat directory, no subdirectories)
6. **Drivers**: Keyboard, display, storage

**Expand Gradually**:
- Add features one at a time
- Test thoroughly
- Multitasking (cooperative then preemptive)
- Virtual memory
- Hierarchical file system
- Networking

**Example Progression**:
- Year 1: Boot loader + monitor
- Year 2-5: Simple kernel + shell + file system
- Year 5-10: Multitasking, virtual memory
- Year 10-20: Full Unix-like OS
- Year 20+: Modern features (multiprocessor, advanced filesystems, etc.)

### Using Existing OS

**If Salvaged Computers Available**:
- Linux: Open source, well-documented, runs on many architectures
- BSD: Similar to Linux, different license
- Windows: Proprietary (no source), but widely used

**Advantages**:
- Immediate functionality
- Mature, tested
- Large application ecosystem

**Disadvantages**:
- Requires hardware it supports
- Complex (millions of lines of code)
- May need modification for custom hardware

**Recommendation**:
- Use Linux on salvaged hardware
- Study and modify as needed
- Port to custom hardware when necessary
- Write custom OS only if:
  - Educational purposes
  - Specialized needs
  - No suitable existing OS

## Software Development Tools

### Text Editor

**Essential**: You need to write code

**Simple Editor** (Line-Based):
- Commands: Insert line, delete line, change line, save, load
- Example: EDLIN (DOS line editor)
- 500-1,000 lines of code

**Screen Editor** (Full-Screen):
- Cursor movement
- Insert/delete characters
- Search/replace
- Examples: vi, Emacs, nano
- 5,000-50,000 lines

**Start With**: Simple line editor, upgrade to screen editor

### Debugger

**Purpose**: Find and fix bugs

**Features**:
- **Breakpoints**: Pause execution at specific line
- **Step**: Execute one line at a time
- **Inspect**: View variables, memory
- **Modify**: Change values while running

**Types**:
- **Source-Level**: Debug high-level language (C, etc.)
- **Assembly-Level**: Debug machine code

**Building Debugger**:
- Requires OS support (or hardware breakpoints)
- Integrate with compiler (symbols, line numbers)
- Complex but invaluable

**Alternative**: Print statements (crude but effective)

### Version Control

**Purpose**: Track changes, collaborate

**Systems**:
- **RCS** (Revision Control System, 1982): Simple, file-based
- **CVS** (Concurrent Versions System, 1990): Multiple files, client-server
- **SVN** (Subversion, 2000): Improved CVS
- **Git** (2005): Distributed, very popular by 2025

**Basic Concepts**:
- **Repository**: Database of versions
- **Commit**: Save changes
- **Checkout**: Get specific version
- **Branch**: Parallel development
- **Merge**: Combine branches

**Implementing Simple Version Control**:
1. Store snapshots of files (with timestamps, messages)
2. Diff: Show changes between versions
3. Revert: Restore old version
4. Effort: 1,000-5,000 lines

**Recommendation**: Use Git (if salvaged systems available). Otherwise, write simple version control early.

### Build Systems

**Purpose**: Compile large projects

**Make** (1976):
- Specify dependencies
- Only rebuild changed files
- Makefile example:
  ```makefile
  program: main.o utils.o
      gcc -o program main.o utils.o

  main.o: main.c utils.h
      gcc -c main.c

  utils.o: utils.c utils.h
      gcc -c utils.c
  ```
- Efficient (only recompile what changed)

**Implementing Make**:
- Parse Makefile
- Check file timestamps
- Determine what to rebuild
- Execute commands
- Effort: 2,000-5,000 lines

## Applications

### Text Processing

**Word Processor**:
- Edit documents
- Formatting (bold, italic, fonts, sizes)
- Print
- Examples: WordStar, WordPerfect, Microsoft Word

**Typesetting**:
- **TeX/LaTeX**: Professional typesetting (especially math)
- Input: Plain text with markup
- Output: High-quality PDF or PostScript

### Spreadsheets

**Purpose**: Tabular data, calculations, graphs

**Features**:
- Grid of cells
- Formulas: =A1+A2
- Functions: SUM, AVERAGE, IF, etc.
- Graphs and charts

**Examples**: VisiCalc (1979, first spreadsheet), Lotus 1-2-3, Excel

**Implementation**:
- 2D array of cells
- Parser for formulas
- Dependency tracking (recalculate when inputs change)
- Rendering
- Effort: 10,000+ lines

### Databases

**Purpose**: Store, query, manage data

**Types**:
- **Flat-file**: Simple, no relationships (CSV, etc.)
- **Relational**: Tables with relationships (SQL)
- **NoSQL**: Document, key-value, graph (modern)

**Relational Database**:
- **Tables**: Rows and columns
- **Keys**: Unique identifiers
- **Relationships**: Foreign keys link tables
- **SQL**: Query language (SELECT, INSERT, UPDATE, DELETE)

**Examples**: dBASE, Oracle, MySQL, PostgreSQL, SQLite

**Implementing Database**:
- Storage engine (B-tree or hash table)
- SQL parser and executor
- Transactions (ACID: Atomicity, Consistency, Isolation, Durability)
- Indexes
- Effort: 50,000+ lines for full-featured RDBMS

**Recommendation**: SQLite is small, open source, well-documented. Use if available. Otherwise, start with flat-file databases.

### Graphics and CAD

**Graphics Libraries**:
- Draw lines, shapes, text
- Examples: X Window System, OpenGL, SDL

**CAD** (Computer-Aided Design):
- Design physical objects (mechanical parts, buildings, circuits)
- 2D or 3D
- Examples: AutoCAD, FreeCAD, KiCAD (electronics)

**Effort**: Very large (100,000+ lines for CAD)

**Priority**: Lower initially. Text-based tools more urgent. Add graphics when capability allows.

### Scientific and Engineering Software

**Numerical Libraries**:
- Linear algebra: Matrix operations
- Differential equations: Solve ODEs, PDEs
- Optimization: Find minimum/maximum
- Statistics: Mean, variance, regression, etc.

**Examples**:
- **BLAS**: Basic Linear Algebra Subprograms
- **LAPACK**: Linear Algebra Package
- **GSL**: GNU Scientific Library

**Simulation**:
- Physics: Model mechanical, electrical, thermal systems
- Chemistry: Molecular dynamics
- Engineering: Finite element analysis (FEA)

**Recommendation**: Build on existing libraries (BLAS, LAPACK) if available. Otherwise, implement basic algorithms (matrix multiply, Gaussian elimination, etc.) and expand.

## Software Engineering Practices

### Documentation

**Types**:
- **Code Comments**: Explain what code does
- **API Documentation**: How to use functions, libraries
- **User Manuals**: How to use applications
- **Design Docs**: Architecture, decisions, rationale

**Importance**: Post-collapse, knowledge transfer is critical. Document everything.

### Testing

**Unit Tests**: Test individual functions
**Integration Tests**: Test components together
**System Tests**: Test entire program
**Regression Tests**: Ensure fixes don't break other things

**Test-Driven Development (TDD)**: Write tests first, then code to pass tests

### Code Reviews

**Peer Review**: Have others read and critique your code
- Find bugs
- Share knowledge
- Improve code quality

### Modularity and Reusability

**DRY** (Don't Repeat Yourself): Write code once, reuse
**Functions and Libraries**: Encapsulate and share

**Example**: Math library used by many programs

### Standards and Style

**Coding Standards**: Consistent naming, formatting
**Language Standards**: Follow established standards (ANSI C, etc.)

**Benefits**: Code easier to read, maintain, share

## Summary: Software Development Stages

**Stage 1 (Year 0-5): Machine Code and Assembly**
- Toggle programs into computer
- Hand-assemble
- Write first assembler (in machine code)
- Basic monitor/shell

**Stage 2 (Year 5-15): Interpreters and Simple OS**
- BASIC or Forth interpreter
- Simple OS (boot, shell, file system)
- Text editor
- Assembler (self-hosting)

**Stage 3 (Year 15-30): Compiled Languages**
- C compiler (cross-compile or native)
- Unix-like OS
- Development tools (make, debugger, version control)
- Applications (editor, shell, utilities)

**Stage 4 (Year 30-50): Modern Development**
- C++, Python, other languages
- Advanced OS features (multiprocessor, virtual memory, networking)
- IDEs (Integrated Development Environments)
- Large applications (office suites, CAD, databases)

**Stage 5 (Year 50+): Contemporary Software**
- Modern languages (Rust, Go, etc.)
- Web development (browsers, servers, frameworks)
- Machine learning libraries
- Distributed systems

## Practical Advice

### Leverage Existing Software

**Salvaged Computers**: Run Linux, use GCC, Python, etc.
- Immediate productivity
- Study source code to learn

**Open Source**:
- Free to use and modify
- Extensively documented
- Learn by reading

### Build From Basics

**Understand Fundamentals**:
- Don't just use tools, understand how they work
- Build simple versions yourself (educational)

**Example Path**:
1. Study existing C compiler (GCC source)
2. Write tiny C compiler for subset of language
3. Expand gradually
4. Eventually have full compiler

### Prioritize

**Critical First**:
- Assembler
- Simple editor
- Basic OS

**Later**:
- Compilers
- Applications
- Graphical interfaces

### Document Everything

**Preserve Knowledge**:
- Comment code
- Write tutorials
- Create reference manuals
- Teach others

**Remember**: You're not just writing software for now. You're building the knowledge base for future generations.

## Conclusion

Software is the enabler. With software:
- Computers become useful
- Knowledge is preserved and shared
- Complex problems are solved
- Civilization rebuilds faster

**Key Principle**: Start simple. Build tools to build better tools. Each generation of software enables the next. Assembly enables interpreters. Interpreters enable compilers. Compilers enable operating systems. Operating systems enable applications. Applications enable users to rebuild civilization.

The software stack is tall, but you don't have to build it all at once. One layer at a time, one tool at a time, one program at a time. Progress is cumulative. Every program you write makes the next one easier.

Software is thought encoded as instructions. Preserve it, build it, share it. It's as important as any physical technology in this guide.
