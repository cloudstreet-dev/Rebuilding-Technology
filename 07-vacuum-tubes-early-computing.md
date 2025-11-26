# Chapter 7: Vacuum Tubes and Early Computing

## Why Vacuum Tubes Matter

Before transistors (1947) and integrated circuits (1960s), vacuum tubes were the only electronic amplifying and switching devices. They enabled:
- Radio and television
- Electronic computers
- Radar and communications systems
- Industrial control

Post-collapse, vacuum tubes are **much easier to manufacture than transistors**. You can build them with:
- Glassworking skills
- Basic metalworking
- Vacuum pump (can be improvised)
- No ultra-pure materials required
- No clean room needed

A tube-based computer is achievable within 10-20 years post-collapse. A transistor-based computer requires decades more infrastructure.

## Vacuum Tube Fundamentals

### Thermionic Emission

**Principle**: Hot metal emits electrons into surrounding space

**Process**:
1. Heat cathode to 800-1,200°C (dull red to orange)
2. Electrons gain enough energy to escape metal surface
3. If positive voltage nearby (anode), electrons flow to it
4. Current flows through vacuum

**Key Insight**: Vacuum prevents electrons from colliding with air molecules. Current flows freely.

### Basic Tube Types

**Diode** (Two Elements):
- **Cathode**: Heated, emits electrons
- **Anode (Plate)**: Collects electrons when positive
- **Function**: Rectifies AC to DC (current flows one direction only)

**Triode** (Three Elements):
- **Cathode**: Emits electrons
- **Grid**: Wire mesh between cathode and plate
- **Plate**: Collects electrons
- **Function**: Grid voltage controls plate current (amplification and switching)
- **Gain**: 10-100 typical

**Tetrode** (Four Elements):
- Adds screen grid between control grid and plate
- Reduces inter-electrode capacitance
- Higher gain, better at high frequencies

**Pentode** (Five Elements):
- Adds suppressor grid
- Prevents secondary emission problems
- Most versatile tube type

## Building Vacuum Tubes

### Materials Needed

**Envelope (Glass Bulb)**:
- Borosilicate glass (Pyrex) preferred
- Or soda-lime glass (more common, harder to work)
- Salvage: Light bulbs, bottles, lab glassware
- Or blow your own from glass tubing

**Cathode**:
- **Filament type**: Tungsten wire (pure tungsten or thoriated tungsten)
  - Heat by passing current through wire
  - Directly emits electrons
- **Oxide-coated type**: Nickel tube coated with barium/strontium oxide
  - Separate heater wire inside tube
  - Lower temperature, longer life, more efficient

**Grid**:
- Fine wire wound in helix or mesh
- Tungsten, molybdenum, or nickel
- Must withstand heat
- Spacing critical (0.1-0.5 mm typical)

**Plate (Anode)**:
- Nickel, molybdenum, or iron sheet
- Cylindrical, surrounds cathode and grid
- Or flat plate in planar designs

**Base**:
- Ceramic or Bakelite (see Chapter 4)
- Pins for connections (brass or copper)
- Glass-to-metal seal where envelope connects to base

**Getter**:
- Material that absorbs residual gas after sealing
- Typically barium or magnesium
- Flashed (evaporated) onto inside of envelope during processing

### Construction Process

**1. Fabricate Elements**:

**Cathode** (Oxide-Coated Type):
- Nickel tube, 1-3 mm diameter
- Coat with carbonates of barium and strontium
- Heat in vacuum or hydrogen to convert to oxides
- Insert tungsten heater wire inside

**Grid**:
- Wind fine wire (0.05-0.1 mm) on mandrel
- 10-50 turns, evenly spaced
- Support with molybdenum rods
- Or make mesh from fine screen

**Plate**:
- Roll nickel sheet into cylinder, 5-15 mm diameter
- Or form from sheet metal
- Support tabs for mounting

**2. Assemble Elements**:
- Mount on mica or ceramic spacers
- Maintain alignment: cathode in center, grid around cathode, plate around grid
- Spacing crucial: Too close = shorts, too far = low gain
- Connect to pins in base

**3. Seal in Envelope**:

**Method 1: Bottom Seal** (Traditional):
- Elements attached to base with pins
- Glass envelope (tube shape, closed at top)
- Heat glass base with torch
- Press onto base
- Glass melts and seals around pins
- Requires glass-to-metal seals (tricky)

**Method 2: Top Seal** (Easier):
- Build elements inside glass tube
- Seal one end
- Evacuate from other end
- Tip off (melt and seal) while under vacuum

**4. Evacuation**:

**Vacuum Pump** (Critical Step):
- Need pressure <0.001 torr (0.001 mm Hg)
- Lower is better (<0.0001 torr ideal)

**Building a Vacuum Pump**:

**Rotary Vane Pump** (Mechanical):
- Rotating vane in cylindrical chamber
- Oil-sealed (to prevent leakage)
- Can achieve 0.001 torr
- Salvage from refrigeration, automotive AC, or scientific equipment
- Or build: Machine cylinder, rotor, and vanes from metal

**Diffusion Pump** (For Higher Vacuum):
- Boils oil, vapor jets trap gas molecules
- Backs onto rotary pump
- Achieves 0.00001 torr
- Build: Glass or metal chamber with oil and heater

**Evacuation Process**:
1. Connect tube to pump via glass tubing
2. Heat tube while pumping (drives out absorbed gases)
3. Pump for 30-60 minutes
4. Flash getter (heat magnesium or barium to evaporate)
5. Getter deposits on envelope, absorbs remaining gas
6. Tip off connection tube while still pumping
7. Result: Sealed tube under high vacuum

**5. Testing**:
- Apply filament/heater voltage (typically 6.3V or 12.6V)
- Wait for warm-up (10-60 seconds)
- Apply plate voltage (50-300V)
- Measure plate current
- Test grid control (vary grid voltage, observe plate current change)

**Common Problems**:
- **No current**: Vacuum lost, cathode damaged, heater not working
- **Low gain**: Grid-cathode spacing too large, weak emission
- **Gassy tube**: Vacuum insufficient (blue glow visible)
- **Shorts**: Elements touching due to misalignment or warping

### Specific Tube Designs

**Simple Diode** (Good First Project):
- Just filament and plate
- No grid = simpler construction
- Use for rectification
- Typical: 1-5A at 50-500V

**Triode Amplifier Tube**:
- Add single grid
- Spacing: ~0.3 mm cathode to grid, ~1 mm grid to plate
- Typical gain: 20-50
- Use for audio amplification, oscillators

**Pentode** (Advanced):
- Three grids (control, screen, suppressor)
- More complex but better performance
- Attempt after mastering triode

## Tube Circuits

### Rectifier (AC to DC)

**Half-Wave Rectifier**:
```
AC in → Diode tube → Load → Ground
```
- Conducts on positive half-cycle only
- Output: Pulsing DC

**Full-Wave Rectifier**:
- Two diodes with center-tapped transformer
- Or four diodes in bridge
- Output: Smoother pulsing DC
- Add capacitor for filtering

**Typical Circuit** (For Tube Power Supply):
```
AC → Transformer (step up to 300V) → Diode rectifier → Filter cap → DC output (250V)
```

### Amplifier

**Common Cathode Amplifier** (Most Common):

**Components**:
- Triode tube
- Plate load resistor (10-100 kΩ)
- Cathode resistor (1-5 kΩ)
- Bypass capacitor (10-100 µF)
- Coupling capacitors (0.1-1 µF)
- Power supply (200-300V)

**Circuit**:
```
B+ (250V) → Load resistor → Plate
                                |
Input → Coupling cap → Grid     Tube
                                |
                            Cathode → Resistor → Ground
                                |
                           Bypass cap
```

**Operation**:
- Input signal on grid varies plate current
- Varying current through load resistor produces voltage changes
- Voltage gain: 20-50 typical
- Phase inverted (input positive → output negative)

**Cathode Follower** (Low Output Impedance):
- Load in cathode instead of plate
- No voltage gain (unity gain)
- High current gain
- Use for impedance matching

### Oscillator

**Armstrong Oscillator**:
- Triode with LC tank circuit in plate
- Feedback from plate to grid via transformer
- Positive feedback sustains oscillation
- Frequency set by LC values

**Colpitts, Hartley Oscillators**:
- Similar principle, different feedback configurations
- Use with crystals for stable frequency

**Multivibrator** (Square Wave):
- Two triodes cross-coupled
- Alternately conduct
- Frequency set by RC time constants
- Use for timing, pulse generation

### Logic Gates (Digital Circuits)

**NOT Gate (Inverter)**:
- Common cathode amplifier
- Input high → Output low
- Input low → Output high

**OR Gate**:
- Two triodes with plates connected
- Either input high → Output high

**AND Gate**:
- Series triodes
- Both inputs must be high for output high
- Or use diodes with tube amplifier

**NAND, NOR**: Combine gates

**Flip-Flop** (Memory Element):
- Two cross-coupled triodes
- Stable in two states (0 or 1)
- Stores one bit of information
- Foundation of computer memory

## Early Computers

### Relay-Based Computers (Even Simpler Than Tubes)

**Before Tubes**: Electromechanical relays used for logic

**Relay**:
- Electromagnetic switch
- Coil energizes → contacts close or open
- Can implement logic gates
- Slow (milliseconds), but reliable and easy to build

**Example: Harvard Mark I** (1944):
- 3,304 relays, 72 words of memory
- Addition in 0.3 seconds
- Multiplication in 6 seconds
- Very loud (clicking relays)

**Building Relay Logic**:
- Easier than tubes (no vacuum required)
- Use salvaged relays
- But much slower and larger

**Recommendation**: Build small relay computer to understand principles, then move to tubes for speed.

### Tube-Based Digital Computer Architecture

**Von Neumann Architecture** (Standard Design):

**Components**:
1. **Memory**: Stores program and data
2. **Control Unit**: Decodes instructions, coordinates operations
3. **Arithmetic Logic Unit (ALU)**: Performs calculations
4. **Input/Output**: Communicates with user and storage
5. **Clock**: Synchronizes operations

**Building Blocks**:

**1. Flip-Flops** (Memory):
- Each flip-flop stores 1 bit
- Chain together for registers
- 8 flip-flops = 1 byte
- Typical word size: 8-40 bits for early computers

**2. Gates** (Logic):
- AND, OR, NOT, NAND, NOR, XOR
- Built from tubes (2-4 tubes per gate)

**3. Adder** (Arithmetic):
- Half adder: Adds 2 bits
  - Inputs: A, B
  - Outputs: Sum, Carry
  - Logic: Sum = A XOR B, Carry = A AND B
- Full adder: Adds 3 bits (A, B, Carry-in)
- Chain full adders for multi-bit addition

**4. Registers** (Storage):
- Collection of flip-flops
- Stores numbers temporarily
- Typical: 8-40 bits
- Needs: Accumulator, program counter, instruction register

**5. Clock** (Timing):
- Oscillator (crystal-controlled for stability)
- Dividers to get desired speed
- Typical early computers: 100 kHz to 1 MHz

**6. Control Logic** (Sequencing):
- Decodes instruction
- Generates control signals
- Steps through instruction cycle:
  - Fetch instruction from memory
  - Decode instruction
  - Execute instruction
  - Store result

### Example: Minimal Tube Computer

**Design Goals**:
- Understand principles
- Minimal complexity
- Achievable with modest resources

**Specification**:
- **Word size**: 8 bits
- **Memory**: 256 bytes (very small, but usable)
- **Speed**: 10-100 kHz
- **Instruction set**: 16 instructions
- **I/O**: Switches for input, lights for output

**Tube Count Estimate**:
- Each flip-flop: 2 triodes
- Each gate: 1-2 triodes
- 8-bit register: 8 flip-flops = 16 triodes
- Memory (256 bytes, static): 256 × 8 × 2 = 4,096 triodes
- ALU (8-bit): ~200 triodes
- Control logic: ~100 triodes
- Total: **~4,500 triodes**

**Reality Check**: This is a large project! First tube computers (ENIAC, 1945) used ~18,000 tubes and filled a room.

**Practical Approach**:
1. Build small calculator first (4-bit, 4 functions)
2. Expand to 8-bit
3. Add memory gradually
4. Build full computer only when capability proven

**Power Consumption**: Each tube ~3W → 13,500W (~14 kW) for full computer!
- Need substantial electrical generation
- Cooling essential

**Reliability**: Tubes fail
- Mean time between failures (MTBF): 1,000-10,000 hours per tube
- 4,500 tubes = failure every 0.2-2 hours on average
- Need extensive troubleshooting and spare tubes

### Memory Technologies

**Flip-Flop (Static) Memory**:
- Fast, simple, but requires 2 tubes per bit
- Expensive in tubes
- Use for registers only

**Williams Tube** (CRT Storage):
- Cathode ray tube stores bits as charged spots on phosphor
- 512-4,096 bits per tube
- Fast read/write
- Requires complex drive circuitry
- Fragile, charge leaks (refresh needed)

**Mercury Delay Line**:
- Sound waves in mercury tube store bits
- Cheap (bits per tube)
- Slow (serial access)
- Temperature-sensitive
- Used in early computers (EDSAC, UNIVAC)

**Magnetic Core Memory** (Best Early Solution):
- Tiny ferrite rings threaded with wires
- Magnetic polarity stores bit (clockwise or counterclockwise)
- Non-volatile (retains data when power off)
- Requires no tubes (just cores and wire)
- Dominant memory technology 1955-1975

**Building Core Memory**:
1. **Cores**: Ferrite rings, 0.5-2 mm diameter
   - Make from ferrite (magnetic ceramic, see Chapter 4)
   - Or salvage from old core memory modules
2. **Threading**: Each core threaded with 4 wires
   - X wire, Y wire (select core)
   - Sense wire (read data)
   - Inhibit wire (write data)
3. **Assembly**: Weave wires through cores in grid
   - Very tedious (originally done by hand, later by machine)
4. **Drive circuits**: Current pulses magnetize cores
5. **Sense amplifiers**: Detect magnetic state

**Capacity**: 4,096-65,536 bits typical for early computers

### Programming

**Machine Code** (Direct Binary Instructions):
- Each instruction: Binary number
- Example (8-bit hypothetical):
  - 00010001: Load accumulator from memory
  - 00100010: Add to accumulator
  - 01000011: Store accumulator to memory
  - 11110000: Halt

**Assembly Language** (Human-Readable Mnemonics):
- LDA addr: Load accumulator
- ADD addr: Add
- STA addr: Store accumulator
- HLT: Halt

**Assembler**: Program that converts assembly to machine code
- Write in assembly
- Assemble by hand initially
- Later, computer can assemble (once you have a working computer)

**High-Level Languages**:
- FORTRAN (1957): Mathematics and science
- COBOL (1959): Business
- BASIC (1964): Beginners
- Require compiler or interpreter
- Much easier to program
- Build after you have working computer

## Practical Projects

### Project 1: Tube Tester

Before building computers, verify your tubes work:

**Circuit**:
- Filament supply (6.3V or 12.6V AC)
- Variable plate supply (0-300V DC)
- Grid bias supply (-50V to +50V)
- Meters to measure plate current, grid current
- Socket to plug in tube

**Test**:
1. Apply filament voltage
2. Vary plate voltage, measure current
3. Vary grid voltage, measure plate current change
4. Calculate gain (transconductance)

### Project 2: Tube Radio

Practical application, teaches tube circuits:

**Superheterodyne Receiver** (See Chapter 6):
- RF amplifier: 1-2 pentodes
- Mixer and oscillator: 1-2 tubes
- IF amplifier: 2-3 pentodes
- Detector: Diode tube
- Audio amplifier: 2 triodes (or power pentode)
- Power supply: Rectifier tube
- Total: 8-12 tubes

**Learning**: Gain experience with tube circuits before attempting computer

### Project 3: Simple Calculator

**4-bit Calculator**:
- Add, subtract, multiply, divide
- Binary inputs (switches)
- Binary outputs (lights)
- No stored program (hardwired logic)
- Tube count: 50-100

**Build This First**: Proves you can build digital logic, much simpler than computer

### Project 4: Minimal Computer

After proving capability with calculator:

**8-bit Computer**:
- 16 instructions
- 256 bytes RAM
- Toggle switches for programming
- Lights for output
- Later: Add paper tape reader, teletype

**Uses**:
- Calculate mathematical tables
- Solve equations
- Scientific computation
- Foundation for more complex systems

## Transition to Transistors

**When to Transition**:
- Tube technology mature (you've built multiple systems)
- Transistor manufacturing capability developed (Chapter 8)
- Worthwhile because:
  - 10-100× lower power
  - Smaller size
  - No warm-up time
  - Longer life (years vs. months)
  - More reliable

**Hybrid Systems**:
- Use tubes where they excel (high voltage, power amplification)
- Use transistors for logic (low power, reliability)

## Summary: Vacuum Tube Development Stages

**Stage 1 (Year 5-10): Basic Tubes**
- Build simple diodes
- Construct triodes
- Tube radio receivers and transmitters
- Learn glassworking and vacuum techniques

**Stage 2 (Year 10-15): Advanced Tubes and Circuits**
- Pentodes for better performance
- Complex amplifiers
- Oscillators and timing circuits
- Test equipment

**Stage 3 (Year 15-25): Digital Electronics**
- Flip-flops and gates
- Simple calculator
- Core memory
- Minimal computer (8-bit)

**Stage 4 (Year 25-35): Computing Systems**
- Larger computers (16-bit, more memory)
- High-level languages
- Operating systems
- Practical applications
- Begin transistor transition

## Safety

**High Voltage**:
- Tube circuits use 200-500V commonly
- CRTs use up to 25,000V
- Can kill instantly
- Discharge capacitors before working
- One hand in pocket when testing (prevents current across heart)

**X-Rays**:
- Tubes operating above ~15 kV can produce X-rays
- Shield or limit exposure time
- Not a problem for typical tubes (<5 kV)

**Implosion**:
- Vacuum envelope can implode if broken
- Glass shards fly
- Wear safety glasses when handling tubes

**Heat**:
- Tubes get very hot (100-200°C exteriors)
- Power dissipation heats room
- Ensure ventilation and cooling

## Next Steps

With vacuum tube technology mastered:
- Build communication and computation systems
- Develop transistor manufacturing (Chapter 8)
- Create more sophisticated computers (Chapter 9)
- Eventually transition to solid-state electronics

Vacuum tubes are the bridge technology. They're achievable with modest infrastructure, yet powerful enough to build computers and complex electronics. Master tubes, and you've mastered the principles of all electronics. The transition to transistors and ICs is then a matter of manufacturing capability, not conceptual understanding.

**Key Principle**: Don't skip tubes in pursuit of transistors. Tubes are achievable sooner, teach fundamental principles, and provide working technology while you develop the complex infrastructure needed for semiconductor manufacturing.
