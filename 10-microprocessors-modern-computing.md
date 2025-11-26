# Chapter 10: Integrated Circuits and Microprocessors

## The Microprocessor Revolution

The microprocessor—an entire CPU on a single chip—transformed computing from room-filling machines to devices that fit in your pocket. The first microprocessor, Intel's 4004 (1971), contained 2,300 transistors. By 2025, chips contained tens of billions of transistors.

Post-collapse, you'll walk this same path: from discrete logic → simple ICs → microprocessors. But you'll do it faster because you know where you're going.

## From Discrete Components to Integration

### Why Integrate?

**Problems with Discrete Components**:
- **Size**: 1,000-transistor computer fills multiple racks
- **Power**: Each transistor consumes power, generates heat
- **Reliability**: More connections = more failure points
- **Speed**: Signal delays between components limit clock speed
- **Cost**: Assembly labor expensive

**Solution**: Build multiple components on single silicon die
- **Smaller**: Thousands of transistors in space of one discrete transistor
- **Lower power**: Smaller transistors, shorter wires
- **More reliable**: Fewer connections to fail
- **Faster**: Shorter signal paths
- **Cheaper**: Manufacturing cost per transistor drops dramatically at scale

### Levels of Integration (Historical)

**Small-Scale Integration (SSI)**: 10-100 transistors
- Examples: Logic gates, flip-flops
- 7400 series TTL (1960s-1970s)
- Your first ICs will be SSI

**Medium-Scale Integration (MSI)**: 100-1,000 transistors
- Examples: Adders, counters, multiplexers, shift registers
- 74-series MSI chips
- Achievable within a few years of first SSI

**Large-Scale Integration (LSI)**: 1,000-10,000 transistors
- Examples: Simple calculators, small microprocessors
- Intel 4004 (2,300 transistors), 8008 (3,500)
- Requires refined process, better lithography

**Very Large-Scale Integration (VLSI)**: 10,000-1,000,000 transistors
- Examples: 16-bit microprocessors, memory chips (64K, 256K)
- Intel 8086 (29,000 transistors), Motorola 68000 (68,000)
- Requires advanced lithography, clean room

**Ultra-Large-Scale Integration (ULSI)**: 1,000,000+ transistors
- Examples: Modern CPUs, GPUs, SoCs
- Pentium (1993): 3.1 million transistors
- Apple M1 (2020): 16 billion transistors
- Requires extreme UV lithography, 5-7 nm process

## IC Design Fundamentals

### Circuit Design

**Schematic Entry**:
1. Draw circuit with logic gates, transistors, resistors, capacitors
2. Specify connections
3. Simulate to verify function

**Standard Cell Library**:
- Pre-designed and characterized cells (NAND, NOR, flip-flop, etc.)
- Place and route software arranges cells
- Faster than custom design for most logic

**Custom Layout**:
- Hand-design transistor placement
- For critical paths, analog circuits, memory
- More work but optimal performance

### Layout Design

**Layers** (Typical CMOS Process):
- **N-well**: P-type substrate with N-type regions
- **Active**: Where transistors are formed
- **Polysilicon**: Gates of transistors
- **Metal 1, 2, 3, ...**: Interconnect layers
- **Vias**: Connections between metal layers
- **Passivation**: Protective layer

**Design Rules**:
- Minimum width: Can't make features smaller than process limit
- Minimum spacing: Can't place features too close
- Via size and placement rules
- Antenna rules: Prevent charge buildup during processing

**Example**: 10 µm process
- Minimum feature: 10 µm
- Metal width: 10 µm minimum
- Metal spacing: 10 µm minimum
- Gate length: 10 µm

**Modern processes**: 7 nm features, dozens of metal layers, extremely complex rules

### Design Verification

**Simulation**:
- Functional: Does the logic work correctly?
- Timing: Are all signals fast enough?
- Power: How much current drawn?

**Design Rule Check (DRC)**:
- Automated software checks layout against process rules
- Finds spacing violations, width errors, etc.

**Layout vs. Schematic (LVS)**:
- Verifies layout matches schematic
- Extracts netlist from layout, compares to design netlist

**Test Structures**:
- Include test patterns on chip
- Verify process parameters (threshold voltage, resistivity, etc.)

## Microprocessor Architecture

### 4-Bit Microprocessors (Simplest)

**Intel 4004** (1971, First Commercial Microprocessor):
- **Transistors**: 2,300
- **Process**: 10 µm
- **Clock**: 740 kHz
- **Data**: 4-bit
- **Address**: 12-bit (4,096 bytes)
- **Registers**: 16× 4-bit
- **Instructions**: 46
- **Purpose**: Calculator controller (Busicom calculator)

**Architecture**:
- 4-bit ALU
- Accumulator and status register
- Stack for subroutine calls (3 levels)
- ROM and RAM separated (Harvard architecture)

**Uses Post-Collapse**:
- Control systems (simpler than general-purpose computer)
- Calculators
- Embedded applications

**Design Complexity**: Achievable with early IC capability

### 8-Bit Microprocessors (General Purpose)

**Intel 8008** (1972):
- 3,500 transistors
- 8-bit data, 14-bit address (16 KB)
- 200 kHz
- 48 instructions

**Intel 8080** (1974, Widely Used):
- 6,000 transistors
- 8-bit data, 16-bit address (64 KB)
- 2 MHz
- 78 instructions
- Used in Altair 8800 (first personal computer kit)

**Zilog Z80** (1976, Enhanced 8080):
- 8,500 transistors
- 8-bit data, 16-bit address
- 2.5-6 MHz
- 158 instructions (superset of 8080)
- Used in TRS-80, Sinclair ZX Spectrum, many embedded systems

**MOS 6502** (1975, Simple and Cheap):
- 3,510 transistors
- 8-bit data, 16-bit address
- 1-3 MHz
- 56 instructions
- Used in Apple I/II, Commodore 64, Atari, NES
- Designed for easy manufacturing and low cost

**Architecture Components**:

**ALU**: 8-bit addition, subtraction, AND, OR, XOR, shifts, rotates

**Registers**:
- Accumulator (A): Primary register for arithmetic
- B, C, D, E, H, L: General purpose (8080/Z80)
- X, Y: Index registers (6502)
- Stack Pointer (SP): Points to stack in RAM
- Program Counter (PC): Address of next instruction
- Flags: Zero, Carry, Sign, Overflow, etc.

**Instruction Set**:
- Data movement: MOV, LD, ST
- Arithmetic: ADD, SUB, INC, DEC
- Logical: AND, OR, XOR, NOT
- Shifts and rotates: SHL, SHR, ROL, ROR
- Jumps: JMP, JZ, JNZ, JC, etc.
- Calls: CALL, RET
- Stack: PUSH, POP
- I/O: IN, OUT

**Memory Interface**:
- Address bus: 16 wires (A0-A15)
- Data bus: 8 wires (D0-D7)
- Control: RD, WR, MREQ, IORQ, etc.

**Clock and Timing**:
- External crystal oscillator (1-8 MHz typical)
- Internal dividers generate phases
- Instruction timing: 1-5 clock cycles per instruction (simple ones), up to 17 cycles (complex)

### 16-Bit Microprocessors (More Powerful)

**Intel 8086** (1978, x86 Architecture Origin):
- 29,000 transistors
- 16-bit data, 20-bit address (1 MB)
- 5-10 MHz
- Segmented memory (CS, DS, SS, ES segments)
- Used in original IBM PC (as 8088, 8-bit data bus version)

**Motorola 68000** (1979, Elegant Architecture):
- 68,000 transistors (hence the name)
- 16-bit data, 24-bit address (16 MB)
- 8-16 MHz
- 8 data registers, 8 address registers
- Used in Apple Macintosh, Amiga, Atari ST, early Sun workstations

**Advantages Over 8-Bit**:
- More memory addressable
- Faster processing (16-bit operations in one instruction)
- More registers
- Better for complex software

### 32-Bit and Beyond

**Intel 80386** (1985):
- 275,000 transistors
- 32-bit data and address (4 GB)
- 16-33 MHz
- Virtual memory support
- Protected mode (multitasking)

**ARM** (1985, RISC Architecture):
- 25,000 transistors (ARM2)
- 32-bit RISC (Reduced Instruction Set Computer)
- Very low power
- Dominates mobile/embedded (by 2025)

**Modern Processors** (2020s):
- Billions of transistors
- Multi-core (4-128+ cores)
- GHz clock speeds
- Advanced features: Out-of-order execution, branch prediction, cache hierarchy

**Post-Collapse Path**: 8-bit → 16-bit → 32-bit over decades

## Manufacturing Your First Microprocessor

### Process Technology Requirements

**Minimum Requirements for Simple Processor**:
- **Feature size**: 10 µm (achievable with UV photolithography)
- **Metal layers**: 2 minimum, 3 better
- **Wafer size**: 2-4 inch diameter (50-100 mm)
- **Clean room**: Class 1,000-10,000 (1,000-10,000 particles per cubic foot)
- **Equipment**:
  - Oxidation furnace
  - Diffusion furnace
  - Photolithography (mask aligner, spinner, developer)
  - Etching (wet chemical)
  - Metallization (vacuum evaporation or sputtering)
  - Dicing saw
  - Wire bonder

**Design Constraints at 10 µm**:
- Large die size: Simple processor ~10 mm × 10 mm = 100 mm²
  - Can fit ~100-200 dies on 4-inch wafer
- Modest transistor count: 1,000-10,000 transistors practical
- Slower speeds: 1-4 MHz due to large capacitances

**Target**: 4-bit or simple 8-bit processor

### Design Process

**1. Architecture Definition**:
- Choose: 4-bit or 8-bit
- Instruction set: 16-32 instructions
- Registers: 2-4 general purpose + special
- Address space: 4K-16K
- I/O: Memory-mapped

**2. Logic Design**:
- Design ALU, registers, control unit
- Draw block diagrams
- Create gate-level schematics
- Simulate functionality

**3. Circuit Design**:
- Convert logic gates to transistor circuits
- NMOS or CMOS technology (CMOS better but more complex)
- Design standard cells or full custom

**4. Layout**:
- Floorplanning: Arrange major blocks
- Placement: Position cells
- Routing: Connect cells with metal
- Verify DRC and LVS

**5. Mask Generation**:
- Convert layout to mask patterns
- One mask per layer (6-8 masks typical)
- Create photomasks:
  - Early: Photographic reduction of hand-drawn patterns
  - Better: E-beam or laser pattern generator

**6. Fabrication**:
- Follow process recipe (Chapter 8)
- 4-8 weeks from start to finished wafer

**7. Testing**:
- Probe wafer: Test each die before dicing
- Dice wafer into individual chips
- Package good dies
- Final test: Verify all functions, speed-grade

**8. Debug and Iterate**:
- First version will have bugs
- Identify issues
- Fix design
- Fabricate new version
- Repeat until working

**Expect**: 2-5 iterations before fully functional chip

### Example: Simple 8-Bit Microprocessor

**Specification**:
- 8-bit data bus
- 12-bit address bus (4,096 bytes)
- 20-30 instructions
- 1-2 MHz clock
- ~2,000-5,000 transistors

**Architecture**:

**Registers** (8-bit):
- A: Accumulator
- B, C: General purpose
- SP: Stack Pointer (12-bit)
- PC: Program Counter (12-bit)
- F: Flags (Zero, Carry, Sign, Overflow)

**Instructions**:
- NOP
- LDA addr, LDB addr, LDC addr: Load register
- STA addr, STB addr, STC addr: Store register
- ADD, SUB: Arithmetic
- AND, OR, XOR: Logic
- INC, DEC: Increment/Decrement
- JMP, JZ, JNZ, JC, JNC: Jumps
- CALL, RET: Subroutines
- IN, OUT: I/O
- HLT: Halt

**Instruction Format**:
- 1 byte opcode
- 0-2 bytes operand (address or immediate)

**Pinout** (40-pin DIP):
- 8 pins: Data bus (D0-D7)
- 12 pins: Address bus (A0-A11)
- Control: CLK, RD, WR, RESET, INT (interrupt)
- Power: VCC, GND
- Remaining: No-connect or future expansion

**Block Diagram**:
```
External → Data Bus ← → ALU ← → Accumulator
Address Bus ← → PC, SP
Control → Control Unit → Instruction Decode
CLK → Clock
```

**Critical Paths** (Determine Max Clock Speed):
- ALU computation
- Register access
- Instruction decode

**Design for 1 MHz**:
- 1 µs clock cycle
- Allow 200-300 ns per logic stage
- With 10 µm process, this is achievable

### Fabrication Challenges

**Yield Management**:
- Dust particles cause defects
- Larger die = lower yield
- Formula: Yield ≈ e^(-Defect_Density × Area)
- Example: 1 defect/cm², 1 cm² die → 37% yield
- First runs: Expect 10-30% yield
- Mature process: 70-90% yield

**Process Variations**:
- Threshold voltage varies across wafer
- Some chips faster, some slower
- Speed-binning: Sort by max clock speed

**Contamination**:
- Metal ions, particles, organic residues
- Clean room discipline essential
- Wet benches and equipment must be clean

**Alignment**:
- Each mask layer must align to previous layers
- Misalignment causes shorts or opens
- Mask aligner accuracy: ±1-2 µm (adequate for 10 µm process)

## Peripheral ICs

### Support Chips for Microprocessor System

**Memory**:
- **ROM**: Program storage
  - EPROM: Erasable with UV light
  - EEPROM: Electrically erasable
  - Early: Diode matrix ROM
- **RAM**: Data storage
  - SRAM: Fast, simple, low density
  - DRAM: Higher density, needs refresh

**I/O Controllers**:
- **PIO (Parallel I/O)**: 8-bit ports for switches, LEDs, etc.
- **UART (Serial I/O)**: RS-232 communication
- **Timer/Counter**: Generate interrupts, count events

**Interrupt Controller**:
- Manages multiple interrupt sources
- Priority encoding

**DMA Controller**:
- Direct Memory Access (move data without CPU)
- Speeds up I/O

**Example**: Z80 System
- Z80 CPU
- Z80 PIO (parallel I/O)
- Z80 CTC (counter/timer)
- Z80 SIO (serial I/O)
- ROM and RAM chips
- Glue logic (address decoding)

### Designing Support ICs

**Simpler Than CPU**:
- Repetitive structures (memory arrays)
- Less complex control logic
- Good learning projects before attempting CPU

**Example: 8-Bit PIO**

**Functionality**:
- Two 8-bit ports (Port A, Port B)
- Each bit configurable as input or output
- Control registers set direction

**Registers** (CPU interface):
- Data_A, Data_B: Read/write port data
- Control_A, Control_B: Set direction (0=input, 1=output)

**Implementation**:
- 16 flip-flops (data storage)
- 16 tri-state buffers (output drivers)
- 16 direction bits
- Address decode logic
- Transistor count: ~500-1,000

## Software Development

### Cross-Development

**Problem**: Your first processor is slower and has less memory than salvaged 2025 computers

**Solution**: Develop software on salvaged computer, transfer to target
- Write and debug on modern system
- Assemble or compile for target processor
- Transfer machine code via serial port, ROM programmer, or SD card
- Test on target hardware

**Cross-Assembler**:
- Runs on development machine
- Outputs machine code for target processor
- Much faster than assembling on target

**Cross-Compiler**:
- Compile C or other language on development machine
- Generate code for target processor

**Emulator/Simulator**:
- Software simulation of target processor
- Run and debug target code on development machine
- Much faster than hardware debugging

### Native Development

**As Capability Grows**:
- Target processor powerful enough to run assembler
- Self-hosting: Processor can assemble its own programs
- Compile on target: C compiler running on target

**Operating Systems**:
- **CP/M** (Control Program for Microcomputers, 1974):
  - 8-bit OS for 8080/Z80
  - Simple, well-documented
  - File system, command shell, program loader
  - Source code available
- **MS-DOS** (1981): Similar to CP/M, for x86
- **Unix**: More complex, requires 16/32-bit processor and more memory

## Modern Computing Concepts

### Moore's Law

**Observation** (Gordon Moore, 1965): Transistor count doubles every ~2 years
- Due to shrinking feature size
- Held roughly true from 1970s to 2010s
- Slowing in 2020s (physical limits approaching)

**Implications**:
- Exponential growth in capability
- Cost per transistor drops exponentially
- Enables modern computing

**Post-Collapse**: Same progression, but timeline stretched
- 10 µm → 5 µm → 2 µm → 1 µm → 0.5 µm over many decades
- Each step requires better lithography

### Cache Hierarchy

**Problem**: Memory slower than CPU

**Solution**: Small, fast memory (cache) close to CPU
- L1 cache: Smallest, fastest (on-chip)
- L2 cache: Larger, slightly slower
- L3 cache: Larger still
- Main RAM: Largest, slowest

**Principle**: Locality of reference (programs access nearby memory repeatedly)

**Implementation**: Complex logic to manage cache
- Worth it when you have millions of transistors available

### Pipelining

**Problem**: CPU sits idle during instruction fetch

**Solution**: Overlap instruction execution
- Stage 1: Fetch instruction
- Stage 2: Decode instruction
- Stage 3: Execute instruction
- Stage 4: Write back result

Multiple instructions in pipeline simultaneously
- Increases throughput (not latency)
- Complexity: Dealing with branches, dependencies

**Example**: 5-stage pipeline, 1 instruction/cycle (vs. 5 cycles for unpipelined)

### Superscalar Execution

**Multiple Execution Units**:
- Two or more instructions execute simultaneously
- Requires duplicate ALUs, load/store units

**Dynamic Scheduling**:
- CPU reorders instructions for efficiency
- Out-of-order execution
- Complex control logic

**Modern CPUs**: 4-8 instructions per cycle common

### Multicore

**Problem**: Single-core clock speeds limited (power, heat)

**Solution**: Multiple CPUs on one chip
- 2, 4, 8, 16+ cores common
- Each core independent
- Shared cache and memory

**Challenges**: Parallel programming, cache coherence

## Summary: Microprocessor Development Stages

**Stage 1 (Year 30-40): SSI/MSI ICs**
- Simple logic gates
- Counters, registers
- 10-100 transistors per chip
- 10-20 µm process

**Stage 2 (Year 40-50): First Microprocessor**
- 4-bit or simple 8-bit
- 1,000-5,000 transistors
- 1-2 MHz
- 10 µm process
- Used for control applications

**Stage 3 (Year 50-65): 8-Bit Era**
- Full-featured 8-bit processors
- 5,000-10,000 transistors
- 2-4 MHz
- 5-10 µm process
- General-purpose computing, operating systems

**Stage 4 (Year 65-80): 16-Bit Era**
- 16-bit processors
- 20,000-100,000 transistors
- 8-16 MHz
- 2-5 µm process
- Advanced software, multitasking

**Stage 5 (Year 80-100): 32-Bit and Modern Architecture**
- 32-bit processors
- 100,000-1,000,000+ transistors
- 25-100 MHz
- 1-2 µm process
- Virtual memory, protection, modern OSes

**Stage 6 (Year 100+): Advanced Processors**
- Multi-core, GHz speeds
- Billions of transistors
- Sub-micron process
- Comparable to 2000s-2010s technology

## Practical Considerations

### When to Make vs. Salvage

**Salvage** (Priority):
- Modern microprocessors from 2025 will function for decades
- Use them while developing manufacturing capability
- Stockpile varied processors (8-bit through modern)

**Manufacture** (When):
- Salvage running low (decades out)
- Custom designs needed (embedded applications)
- Educational purposes (understanding builds capability)

### Choosing Your First Microprocessor Project

**Don't Start with CPU**:
1. Simple ICs first (gates, flip-flops)
2. MSI (counters, registers)
3. Memory (small SRAM)
4. Peripheral ICs (PIO, UART)
5. Then attempt CPU

**First CPU Should Be**:
- Simple (4-bit or minimal 8-bit)
- Conservative design (proven architecture)
- Generous process (10 µm+)
- Modest goals (1 MHz fine)

**Learn from Historical Designs**:
- 4004, 6502, Z80 are well-documented
- Can copy architecture (no patents post-collapse)
- Adapt to your process capabilities

## Safety and Quality Control

**Clean Room Discipline**:
- Gowning (full body coverage)
- Air showers before entry
- No writing implements (shed particles)
- Slow, careful movements

**Chemical Safety**:
- HF (hydrofluoric acid): Deadly, use with extreme care
- Photoresists: Flammable, toxic
- Developers and etchants: Corrosive
- Proper ventilation, PPE, training essential

**ESD Protection**:
- MOSFET gates extremely sensitive
- Grounding, conductive surfaces, humidity control

**Testing and Validation**:
- Functional testing (verify all operations)
- Speed testing (maximum clock frequency)
- Stress testing (temperature, voltage extremes)
- Long-term reliability (burn-in)

## Next Steps

With microprocessor capability:
- Build modern computer systems (Chapter 9 advanced)
- Create sophisticated software (Chapter 13)
- Enable complex networking (Chapter 12)
- Develop advanced interfaces (Chapter 14)
- Foundation for AI (Chapter 16)

The microprocessor is the heart of modern technology. Every computer, phone, car, appliance (in 2025) contained microprocessors. Rebuilding this capability unlocks the full potential of computing.

**Key Principle**: The microprocessor is the hardest single component in this book to manufacture. It requires the culmination of all previous technologies: metallurgy (equipment), chemistry (processes), electricity (lithography tools), electronics (test equipment), and software (design tools). But once achieved, it opens the door to recreating all of modern computing.

Don't rush this. Build the foundation thoroughly. When you're ready to attempt a microprocessor, you'll have the skills and infrastructure to succeed.
