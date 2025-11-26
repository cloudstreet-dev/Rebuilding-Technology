# Chapter 9: Building Your First Computer

## Computer Fundamentals

A computer is a machine that:
1. **Stores** instructions and data
2. **Executes** instructions automatically
3. **Performs** arithmetic and logical operations
4. **Controls** its own operation based on results

**Key Insight**: A computer is built from simple components (gates, flip-flops) arranged in complex patterns.

## Digital Logic Review

### Binary Number System

**Why Binary**: Electronics naturally represent two states (on/off, high/low voltage)

**Binary Counting**:
```
Decimal  Binary
0        0000
1        0001
2        0010
3        0011
4        0100
...
15       1111
```

**Hexadecimal** (Base-16, shorthand for binary):
```
Dec  Hex  Binary
0    0    0000
10   A    1010
15   F    1111
255  FF   11111111
```

### Boolean Algebra

**Basic Operations**:
- AND: Output 1 only if all inputs 1
- OR: Output 1 if any input 1
- NOT: Inverts input
- XOR: Output 1 if inputs different
- NAND: NOT-AND (universal gate)
- NOR: NOT-OR (universal gate)

**De Morgan's Laws**:
- NOT(A AND B) = (NOT A) OR (NOT B)
- NOT(A OR B) = (NOT A) AND (NOT B)

Use these to simplify logic circuits.

### Combinational Logic

**Half Adder** (Adds 2 bits):
- Inputs: A, B
- Outputs: Sum = A XOR B, Carry = A AND B

**Full Adder** (Adds 3 bits including carry):
- Inputs: A, B, Cin
- Outputs: Sum = A XOR B XOR Cin, Cout = (A AND B) OR (Cin AND (A XOR B))

**4-Bit Adder**: Chain 4 full adders (carry propagates)

**Subtraction**: Use 2's complement
- Negate B (invert all bits, add 1)
- Add A + (-B)

**Multiplexer** (Data Selector):
- Multiple inputs, one output
- Select lines choose which input passes through

**Decoder**: Convert binary to one-of-many outputs

**Encoder**: Opposite of decoder

### Sequential Logic

**SR Latch** (Set-Reset):
- 2 NOR gates cross-coupled
- Set input: Output goes to 1
- Reset input: Output goes to 0
- Memory element (stays in last state)

**D Flip-Flop**:
- Data input, Clock input
- Output captures Data when Clock pulses
- Foundation of registers and memory

**Register**: Multiple flip-flops
- 8 flip-flops = 8-bit register
- Stores one byte

**Counter**: Register that increments
- Use for program counter, timing

**Shift Register**: Data shifts left or right each clock
- Serial to parallel conversion
- Parallel to serial conversion

## Computer Architecture

### Von Neumann vs. Harvard

**Von Neumann** (Most Common):
- Single memory for both program and data
- Simpler
- Program can modify itself

**Harvard**:
- Separate program and data memory
- Can fetch instruction and data simultaneously (faster)
- More complex

We'll use Von Neumann for simplicity.

### Basic Components

**1. Central Processing Unit (CPU)**:
- **ALU (Arithmetic Logic Unit)**: Performs operations
- **Control Unit**: Decodes instructions, generates control signals
- **Registers**: Small, fast memory inside CPU
  - Accumulator: Holds calculation results
  - Program Counter (PC): Address of next instruction
  - Instruction Register (IR): Holds current instruction
  - General purpose registers: Temporary storage

**2. Memory**:
- **RAM (Random Access Memory)**: Read and write
- **ROM (Read Only Memory)**: Permanent storage (bootstrap program)
- Organized as bytes (8 bits) with addresses
- Typical size for early computer: 256 bytes to 64 KB

**3. Input/Output (I/O)**:
- Input: Switches, keyboard, paper tape, storage
- Output: Lights, display, paper tape, printer, storage

**4. Bus**:
- **Address Bus**: CPU specifies memory location
- **Data Bus**: Transfers data
- **Control Bus**: Read/write, clock, etc.

### Instruction Set Architecture (ISA)

**Defines**: What instructions the computer can execute

**Example Simple ISA** (8-bit):

**Data Movement**:
- LDA addr: Load Accumulator from memory
- STA addr: Store Accumulator to memory
- LDI imm: Load Immediate value to Accumulator
- MOV reg1, reg2: Move between registers

**Arithmetic**:
- ADD addr: Add memory to Accumulator
- SUB addr: Subtract memory from Accumulator
- INC: Increment Accumulator
- DEC: Decrement Accumulator

**Logical**:
- AND addr: Logical AND
- OR addr: Logical OR
- XOR addr: Logical XOR
- NOT: Invert Accumulator

**Jumps and Branches**:
- JMP addr: Jump to address
- JZ addr: Jump if Zero flag set
- JNZ addr: Jump if Not Zero
- CALL addr: Call subroutine
- RET: Return from subroutine

**I/O**:
- IN port: Read from input port
- OUT port: Write to output port

**Control**:
- NOP: No operation
- HLT: Halt

**Instruction Format** (8-bit):
- 4 bits opcode (16 possible instructions)
- 4 bits operand or register
- Or 8 bits opcode (256 instructions, operand in next byte)

### Fetch-Decode-Execute Cycle

**Every instruction follows**:

1. **Fetch**:
   - Read instruction from memory at address in PC
   - Store in IR
   - Increment PC

2. **Decode**:
   - Control unit interprets opcode
   - Determines which operation to perform

3. **Execute**:
   - Perform the operation
   - Update registers, memory, flags

4. **Repeat**

**Clock**: Synchronizes each step
- Typical early computers: 1-10 MHz
- Each instruction: 1-10 clock cycles

## Building a Minimal Computer

### Design Goals

**Keep It Simple**:
- 4-bit or 8-bit data path
- 16 instructions (4-bit opcode)
- 256 bytes memory (8-bit address)
- Toggle switches for input
- LEDs for output

### Component Count Estimates

**4-Bit Computer** (Easier First Project):
- ALU: 40-80 gates (160-320 transistors or 20-40 ICs)
- Registers (4 registers × 4 bits): 16 flip-flops = 32 transistors
- Control logic: 50-100 gates (200-400 transistors)
- Memory (256 × 4 bits): Core memory or SRAM
- Clock: 1 oscillator + dividers
- **Total**: ~500-1,000 transistors or ~50-100 ICs

**8-Bit Computer** (More Capable):
- ALU: 80-160 gates
- Registers (4 registers × 8 bits): 32 flip-flops
- Control: 100-200 gates
- Memory: 256-4,096 bytes
- **Total**: ~1,000-2,000 transistors or ~100-200 ICs

### ALU Design

**Functions**: ADD, SUB, AND, OR, XOR, NOT, shift

**4-Bit ALU**:
```
Components:
- 4-bit adder (4 full adders)
- 4× 2-input multiplexers (select operation)
- Logic gates for AND, OR, XOR, NOT
- Barrel shifter (for shifts/rotates)

Operation select: 3 bits (8 operations)
Inputs: A (4 bits), B (4 bits)
Output: Result (4 bits), Carry, Zero flag
```

**74-series ICs available** (if salvaged):
- 7483: 4-bit full adder
- 7408: Quad AND gate
- 7432: Quad OR gate
- 7486: Quad XOR gate
- 74157: Quad 2-to-1 multiplexer

### Control Unit Design

**Hardwired** (Simpler):
- Decode instruction with logic gates
- Generate control signals directly
- Fast but inflexible

**Microcoded** (Flexible):
- ROM stores microinstructions
- Each instruction is series of microinstructions
- Easier to modify and debug
- Slightly slower

**Example Control Signals**:
- Register load enables
- ALU operation select
- Memory read/write
- Bus multiplexer select
- PC increment/load

**State Machine**: Steps through fetch-decode-execute

### Memory Implementation

**Static RAM (SRAM)**:
- Each bit: 6 transistors (in CMOS) or 2 tubes/transistors + resistors
- Fast, simple
- Expensive (many components per bit)
- Use for registers and small memory

**Dynamic RAM (DRAM)**:
- Each bit: 1 transistor + 1 capacitor
- Requires refresh (capacitor leaks)
- Higher density
- More complex to drive

**Core Memory** (Best for Large Memory):
- Magnetic cores (see Chapter 7)
- Non-volatile
- Moderate speed
- Reliable
- Standard for computers 1955-1975

**ROM (For Bootstrap)**:
- Diode matrix: Diodes connect row/column where bit is 1
- Or salvage EPROM/EEPROM
- Stores program to start computer

### Clock and Timing

**Crystal Oscillator**:
- 1-10 MHz crystal (salvaged)
- Oscillator circuit (single transistor or IC)
- Dividers to get slower clock if needed

**Single-Step Mode**:
- Switch to manually pulse clock
- For debugging
- Step through program one instruction at a time

### I/O

**Input**:
- Toggle switches for data
- Push buttons for control
- Later: Keyboard, paper tape reader

**Output**:
- LEDs (binary display)
- 7-segment displays (decimal)
- Later: Terminal, printer, storage

**Ports**:
- Memory-mapped: I/O appears as memory addresses
- Port-mapped: Separate IN/OUT instructions

### Power Supply

**Voltage Requirements**:
- Logic: +5V (TTL), +12V/-12V (some logic)
- Tubes: Hundreds of volts
- Total power:
  - 4-bit with 100 ICs: ~50W
  - 8-bit with 200 ICs: ~100W
  - Tube computer: 1-10 kW

**Build**: Transformer, rectifier, regulator (see Chapter 3)

## Assembly and Testing

### Build in Stages

**Stage 1: ALU**:
- Build 4-bit adder
- Test: Verify all additions
- Add other functions
- Test each function

**Stage 2: Registers**:
- Build accumulator, 1-2 general registers
- Test: Load, store, transfer

**Stage 3: Memory Interface**:
- Small memory (16-256 bytes)
- Address decoder
- Test: Read/write

**Stage 4: Control Unit**:
- Start with 2-3 instructions (NOP, LDA, STA)
- Manual single-step mode
- Verify fetch-decode-execute

**Stage 5: Expand Instructions**:
- Add instructions one at a time
- Test each thoroughly

**Stage 6: Expand Memory**:
- Add more memory as needed

**Stage 7: I/O**:
- Add input and output ports

### Debugging Techniques

**LEDs Everywhere**:
- Bus values
- Register values
- Control signals
- Helps visualize what's happening

**Single-Step**:
- Execute one clock cycle at a time
- Watch state changes

**Test Programs**:
- Simple sequences to verify instructions
- Counting loops
- Memory fill patterns

**Logic Analyzer** (If Available):
- Capture and display many signals simultaneously
- Invaluable for debugging

## Programming Your Computer

### Machine Code

**Direct Binary**:
```
Address  Instruction  Meaning
0000     0001 0100    LDA 0100  ; Load from address 4
0001     0010 0101    ADD 0101  ; Add address 5
0010     0011 0110    STA 0110  ; Store to address 6
0011     1111 0000    HLT       ; Halt
0100     0000 0011    03        ; Data: 3
0101     0000 0101    05        ; Data: 5
0110     0000 0000    00        ; Result location
```

**Hand Assembly**: Translate assembly mnemonics to binary by hand

### Assembly Language

**Assembler** (Program that translates):
- Write in mnemonics (LDA, ADD, etc.)
- Assembler converts to machine code
- Much easier than hand-coding binary

**Initial Problem**: You need a working computer to run assembler
**Solution**: Hand-assemble your first assembler, then use it for future programs

**Example Program** (Add two numbers):
```assembly
      LDI  3      ; Load immediate 3 into accumulator
      STA  temp   ; Store in temp
      LDI  5      ; Load immediate 5
      ADD  temp   ; Add temp to accumulator
      STA  result ; Store result
      HLT         ; Halt
temp: 0
result: 0
```

### Higher-Level Languages

**After You Have Working Computer**:

**Interpreted Languages** (Easier to implement):
- **BASIC**: Beginner's language, interactive
  - Simple to write interpreter
  - Slow execution
  - Good for learning
- **Forth**: Stack-based, minimal interpreter
  - Fast for interpreted language
  - Extensible
  - Good for embedded systems

**Compiled Languages** (Faster execution):
- **C**: System programming, efficient
  - Need to write compiler (complex)
  - Or cross-compile on salvaged modern computer
- **Pascal**: Structured, educational
- **FORTRAN**: Scientific computing

**Writing an Interpreter**:
1. Tokenizer: Convert text to tokens
2. Parser: Analyze grammar
3. Executor: Run commands
4. Works directly with source code (no separate compilation)

**Writing a Compiler**:
1. Lexer: Tokenize
2. Parser: Build syntax tree
3. Code generator: Output machine code
4. Much more complex than interpreter

**Recommendation**: Start with simple BASIC interpreter

## Expanding Capability

### More Memory

**Address Space**:
- 8-bit address: 256 bytes
- 16-bit address: 64 KB
- 32-bit address: 4 GB

**Bank Switching** (Expand beyond address space):
- Divide memory into banks
- Select bank with I/O register
- Access one bank at a time

### Better I/O

**Serial Communication**:
- UART (Universal Asynchronous Receiver/Transmitter)
- Send/receive one bit at a time
- Standard rates: 300, 1200, 9600 baud
- Connect to terminal, other computers

**Parallel I/O**:
- Multiple bits simultaneously
- Faster but needs more wires

**Storage**:
- Paper tape: Punch holes for 1s, no hole for 0s
  - Reader: Light sensor or mechanical
  - Punch: Solenoid-driven punch
- Magnetic tape: See Chapter 11
- Floppy disk: See Chapter 11

### Graphics and Sound

**Text Display**:
- Memory-mapped video RAM
- Character generator ROM
- Scan video RAM, output to display

**Graphics**:
- Bitmap: Each pixel stored in memory
- Resolution vs. memory: 320×240 mono = 76,800 bits ≈ 10 KB

**Sound**:
- Square wave generator (simple)
- DAC (Digital to Analog Converter) for better quality

## Example Computer Designs

### Ben Eater's 8-Bit Breadboard Computer

**Modern Educational Example**:
- Built on breadboards with 74-series ICs
- 8-bit data, 4-bit address (16 bytes RAM)
- Programs loaded with DIP switches
- LEDs for output
- Excellent learning platform

**Transferable to Post-Collapse**:
- Uses salvageable ICs
- Clear documentation
- Proven design

### ENIAC (1945)

**First Electronic Computer**:
- 18,000 vacuum tubes
- 5,000 operations/second
- 30 tons, 1,800 square feet, 150 kW
- Programmed with cables and switches
- Ballistics calculations

**Lessons**: Even crude electronics enable computation

### EDSAC (1949)

**First Stored-Program Computer**:
- Von Neumann architecture
- Mercury delay line memory
- 3,000 vacuum tubes
- Assembly language programming

**Lessons**: Stored program much more practical than hardwired

### Apple I (1976)

**First Personal Computer**:
- MOS 6502 processor (8-bit)
- 4 KB RAM (expandable to 8/48 KB)
- Keyboard input, TV output
- Cassette tape storage
- $666.66 price (kit)

**Lessons**: Single-chip CPU revolutionized computing

## Summary: Computer Development Stages

**Stage 1 (Year 15-25): Basic Calculator**
- 4-bit arithmetic unit
- No stored program
- Toggle switch input, LED output
- Proves digital logic works

**Stage 2 (Year 25-35): First Stored-Program Computer**
- 4 or 8-bit
- 256 bytes to 4 KB RAM
- Machine code programming
- Core memory or SRAM

**Stage 3 (Year 35-50): Practical Computing**
- 8 or 16-bit
- 4-64 KB RAM
- Assembly language, simple languages
- Serial I/O, storage (paper tape, magnetic)
- Multiple systems built

**Stage 4 (Year 50-75): Modern Architecture**
- Microprocessor-based (when you can make ICs)
- Megabytes of RAM
- High-level languages (C, BASIC, Pascal)
- Operating system
- Display, keyboard, storage
- Networked

## Safety

**Electrical**:
- Logic voltages (5V) relatively safe
- But power supplies have dangerous voltages
- Capacitors store charge

**ESD (Electrostatic Discharge)**:
- CMOS ICs sensitive to static
- Ground yourself before handling
- Anti-static bags for storage

## Next Steps

With working computer:
- Write software (Chapter 13)
- Connect to network (Chapter 12)
- Build peripherals (Chapter 14: displays, keyboards)
- Develop microprocessors (Chapter 10)
- Enable advanced applications (scientific computing, automation, AI)

**Key Principle**: Start simple (4-bit calculator), prove each stage, then expand. Don't attempt to build a modern computer immediately. Walk the same path historical computers took, but faster because you know the destination.

A working computer, even primitive, is a force multiplier. It can calculate, automate, communicate, and store knowledge. It's worth the considerable effort to build one.
