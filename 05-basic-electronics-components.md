# Chapter 5: Basic Electronic Components

## From Electricity to Electronics

In Chapter 3, you learned to generate and distribute electricity. Now you'll learn to control it with precision. Electronics is about manipulating electrical signals to:
- Switch circuits on and off
- Amplify weak signals
- Filter and shape waveforms
- Store and process information
- Convert between different forms of energy

Every computer, radio, and modern device depends on electronic components. This chapter covers the fundamental building blocks.

## Passive Components (No Power Source Needed)

### Resistors

**Purpose**: Limit current flow, divide voltage, dissipate power

**Ohm's Law Application**:
```
V = I × R

Example: 12V battery, want 10 mA current
R = V / I = 12V / 0.01A = 1,200Ω (1.2kΩ)
```

**Construction**:

**Carbon Composition** (Easiest to Make):
1. **Materials**: Carbon (charcoal powder), clay or ceramic binder, wire leads
2. **Process**:
   - Mix carbon and binder in ratios:
     - More carbon = lower resistance
     - More binder = higher resistance
   - Form into cylinder
   - Embed wire leads at ends
   - Bake to harden
3. **Test**: Measure resistance with multimeter
4. **Iterate**: Adjust carbon/binder ratio to get desired values

**Wire-Wound**:
1. **Materials**: Nichrome wire (nickel-chromium alloy) or other high-resistance wire
2. **Process**:
   - Wind wire around ceramic or fiberglass core
   - More turns or thinner wire = higher resistance
   - Coat with enamel or ceramic
3. **Advantages**: Precise, high power rating
4. **Uses**: Power resistors, precision resistors

**Carbon Film**:
- Deposit carbon film on ceramic rod
- Cut spiral groove to adjust resistance
- More difficult to manufacture

**Values and Color Codes**:
- Standard resistors use color bands to indicate value
- Salvage resistors from old electronics and sort by value
- Make custom values as needed

**Power Rating**:
- Power dissipated = I² × R = V² / R
- Resistor must handle power without overheating
- Larger physical size = higher power rating
- Example: 12V across 120Ω resistor = 1.2W, need 2W+ resistor

### Capacitors

**Purpose**: Store electrical charge, filter signals, block DC while passing AC

**How It Works**:
- Two conductive plates separated by insulator (dielectric)
- Charge accumulates on plates
- Capacity (farads) = permittivity × area / distance

**Construction**:

**Parallel Plate Capacitor** (Simplest):
1. **Materials**:
   - Two sheets of aluminum foil (plates)
   - Dielectric: plastic sheet, wax paper, mica, or glass
2. **Assembly**:
   - Layer: foil, dielectric, foil
   - Add wire leads to each foil
   - Roll up or stack flat
   - Seal to prevent moisture

**Capacitance**: Very low (picofarads to nanofarads) unless large area

**Improved Designs**:

**Rolled Film Capacitor**:
- Long strips of foil and plastic film
- Roll tightly
- More capacitance in smaller space
- Typical: 0.001 to 10 µF

**Leyden Jar** (Historical Capacitor):
- Glass jar coated inside and out with foil
- Simple but low capacity
- Used in early electrical experiments

**Electrolytic Capacitor** (High Capacity):
1. **Materials**:
   - Aluminum foil (anode)
   - Electrolyte: Boric acid, glycol, or other ionic solution
   - Another foil (cathode, or electrolyte contacts cathode)
2. **Process**:
   - Apply voltage to aluminum in electrolyte
   - Oxide layer forms on aluminum (dielectric)
   - Very thin oxide = high capacitance
3. **Result**: 1 to 10,000 µF possible
4. **Polarity**: Must connect correctly (positive to anode) or it explodes
5. **Salvage**: Old electrolytics may work or can be rebuilt

**Capacitor Values**:
- Measured in farads (F)
  - 1 µF (microfarad) = 10⁻⁶ F (common)
  - 1 nF (nanofarad) = 10⁻⁹ F
  - 1 pF (picofarad) = 10⁻¹² F
- Voltage rating: Must exceed maximum voltage

**Applications**:
- **Filtering**: Smooth DC power supplies (remove ripple)
- **Coupling**: Pass AC signal, block DC
- **Timing**: With resistor, creates time delay (τ = R × C)
- **Energy storage**: Camera flash, defibrillator

### Inductors (Coils)

**Purpose**: Store energy in magnetic field, filter signals, transform voltage

**How It Works**:
- Coil of wire creates magnetic field when current flows
- Resists changes in current
- Inductance (henries) depends on: turns², core material, geometry

**Construction**:

**Air Core Inductor**:
1. **Materials**: Magnet wire (insulated copper), coil form
2. **Process**:
   - Wind wire around form (tube, rod, or nothing)
   - More turns = more inductance
   - Larger diameter = more inductance
   - Close-wound or spaced turns (spacing reduces capacitance)
3. **Values**: Microhenries (µH) typical for air core

**Iron Core Inductor**:
1. **Add iron core** to center of coil
2. **Inductance increases** 100-1000× with iron
3. **Values**: Millihenries (mH) to henries (H)
4. **Core materials**:
   - Solid iron: Simple but eddy current losses
   - Laminated iron: Thin sheets reduce losses (for AC)
   - Ferrite: Ceramic iron oxide, very high frequency capability

**Transformer** (Two Coupled Inductors):
1. **Primary coil**: Input
2. **Secondary coil**: Output
3. **Shared core**: Magnetic coupling
4. **Turns ratio**: Determines voltage transformation
   - Voltage ratio = Turns ratio
   - Example: 1000 turns primary, 100 turns secondary = 10:1 step down
5. **Construction**: See Chapter 3

**Applications**:
- **Filtering**: Block AC, pass DC (opposite of capacitor)
- **Chokes**: Smooth power supply ripple
- **Transformers**: Change voltage levels
- **Resonance**: Combine with capacitor for tuned circuits (radios)

### Diodes

**Purpose**: Allow current to flow in one direction only

**How It Works**:
- Junction between P-type and N-type semiconductor
- Forward bias: Current flows easily
- Reverse bias: Current blocked (small leakage)

**Types**:

**Point-Contact Diode** (Cat's Whisker):
1. **Materials**: Galena crystal (lead sulfide) or silicon crystal, fine wire (cat's whisker)
2. **Assembly**:
   - Mount crystal
   - Touch wire to crystal surface
   - Move wire to find sensitive spot (trial and error)
   - Fix wire in place
3. **Performance**: Works but unreliable, sensitive spot can move
4. **Historical**: Used in crystal radio receivers

**PN Junction Diode** (Modern Type):
1. **Materials**: Silicon or germanium, doped to create P and N regions
2. **Process**:
   - Diffuse dopants into semiconductor
   - Create junction between P and N regions
   - Attach leads
   - Encapsulate
3. **Performance**: Reliable, consistent
4. **Difficulty**: Requires semiconductor processing (see Chapter 4)

**Schottky Diode**:
- Metal-semiconductor junction
- Faster switching than PN junction
- Lower forward voltage drop

**Zener Diode**:
- Designed to conduct in reverse at specific voltage
- Voltage regulation

**LED (Light Emitting Diode)**:
- PN junction in specific materials (gallium arsenide, gallium phosphide, etc.)
- Electrons recombine with holes, emit light
- Extremely efficient lighting

**Salvage Priority**: Very high. Diodes are difficult to manufacture. Salvage from any electronics.

**Testing Diodes**:
- Multimeter in diode mode
- Forward: Low resistance (~0.5-0.7V drop)
- Reverse: High resistance (infinite)

**Applications**:
- **Rectification**: Convert AC to DC
- **Protection**: Prevent reverse voltage
- **Switching**: Fast electronic switch
- **Voltage reference**: Zener diodes

**Diode Bridge Rectifier**:
- Four diodes arranged in bridge
- Converts AC to pulsing DC
- Full-wave rectification

```
Circuit:
     AC in
       |
   D1  |  D2
    \  |  /
     \ | /
      \|/---- +DC out
      /|\
     / | \
    /  |  \
   D3  |  D4
       |
      GND
```

### Crystals (Quartz, Piezoelectric)

**Purpose**: Precise frequency reference

**How It Works**:
- Quartz crystal vibrates at precise frequency when voltage applied (piezoelectric effect)
- Frequency depends on size and cut of crystal
- Extreme stability and accuracy

**Salvage**: Quartz crystals from watches, radios, computers
- Common frequencies: 32.768 kHz (watches), 1-100 MHz (computers, radios)

**Manufacturing**: Difficult, requires precision cutting and grinding of quartz

**Applications**:
- Timekeeping (watches, clocks)
- Frequency control (radios, computers)
- Filters (precise frequency selection)

## Active Components (Require Power, Provide Gain/Switching)

### Vacuum Tubes

**Purpose**: Amplify signals, switch current, rectify AC

**How It Works**:
- Heated cathode emits electrons (thermionic emission)
- Electrons flow through vacuum to anode (plate)
- Grid electrode controls electron flow
- Small voltage change on grid creates large current change in plate circuit

**Basic Diode Tube** (Rectifier):
1. **Cathode**: Heated filament or oxide-coated metal
2. **Plate**: Metal electrode to collect electrons
3. **Envelope**: Glass bulb, evacuated
4. **Heater**: Wire to heat cathode

**Triode** (Amplifier):
- Add grid between cathode and plate
- Grid voltage controls plate current
- Amplification factor: 10-100 typical

**Tetrode, Pentode**:
- Additional grids for improved performance
- Screen grid, suppressor grid
- Higher gain, better high-frequency performance

**Construction** (See Chapter 7 for detailed instructions):
- Requires glassworking, vacuum pump, precision parts
- Considerable skill needed
- But achievable with practice

**Advantages**:
- Can be manufactured with modest equipment
- Robust (survives overvoltage, EMP)
- High voltage, high power capability

**Disadvantages**:
- Large, heavy
- High power consumption (heater)
- Fragile (glass)
- Short life (1,000-10,000 hours)

### Transistors

**Purpose**: Amplify signals, switch current (similar to vacuum tube but solid-state)

**How It Works**:
- Three layers of semiconductor: NPN or PNP
- Base current controls collector-emitter current
- Current gain: 50-500 typical
- Small base current → large collector current

**Types**:

**Bipolar Junction Transistor (BJT)**:
- NPN or PNP structure
- Current-controlled device
- General purpose amplification and switching

**Field Effect Transistor (FET)**:
- Voltage-controlled device
- Types: JFET, MOSFET
- Lower power, higher impedance
- Used extensively in modern circuits

**Construction**:
- Requires pure semiconductor (silicon or germanium)
- Doping to create P and N regions
- Metal contacts
- Encapsulation
- Process detailed in Chapter 8

**Difficulty**: High. Requires:
- Ultra-pure materials
- Precise doping control
- Clean environment
- Considerable expertise

**Salvage Priority**: Extremely high. Salvage all transistors from electronics. Catalog by type and specifications.

**Testing Transistors**:
- Multimeter can check junctions (acts like two diodes back-to-back)
- Transistor tester for gain (hFE) measurement

**Applications**:
- Amplification: Audio, RF, sensors
- Switching: Digital logic, power control
- Oscillation: Signal generation
- Regulation: Voltage and current control

**Common Salvage Transistors**:
- 2N2222, 2N3904 (NPN, general purpose)
- 2N3906, 2N2907 (PNP, general purpose)
- MOSFETs in power supplies, motor controllers

### Integrated Circuits (ICs)

**Purpose**: Thousands to billions of components in single package

**Types**:
- **Analog**: Amplifiers (op-amps), voltage regulators, timers
- **Digital**: Logic gates, microprocessors, memory
- **Mixed-signal**: Analog-to-digital converters, etc.

**Salvage Priority**: CRITICAL. Impossible to manufacture in early stages.

**Common Useful ICs**:
- **555 Timer**: Oscillator, timer, pulse generator
- **741 Op-Amp**: Amplifier, comparator, signal processing
- **7400 Series Logic**: AND, OR, NOT, flip-flops, counters
- **Voltage Regulators**: 7805 (5V), 7812 (12V), adjustable types
- **Microcontrollers**: Arduino, PIC, AVR (if you can program them)

**Storage**:
- Anti-static bags or conductive foam
- Organized by type and part number
- Document pinouts and specifications

**Manufacturing**: Covered in Chapter 10. Extremely difficult, requires advanced facilities.

## Circuit Construction Techniques

### Breadboarding (Temporary Circuits)

**Solderless Breadboard**:
- Salvage from electronics workshops
- Allows quick circuit prototyping
- Components pushed into holes, internal connections link them
- No soldering needed

**Improvised Breadboard**:
- Wooden board, nails or screws as terminals
- Wrap wires around terminals
- Crude but functional

### Perfboard (Permanent Circuits)

**Materials**:
- Board with grid of holes
- Copper pads around holes (or plain holes)

**Assembly**:
1. Insert components through holes
2. Bend leads to hold components
3. Solder connections on underside
4. Trim excess leads

**Making Perfboard**:
1. Drill holes in grid pattern in copper-clad board
2. Or leave copper and just drill holes

### Printed Circuit Boards (PCB)

**Advantages**: Neat, reliable, reproducible

**Construction**:

**Materials**:
- Copper-clad board (copper foil on fiberglass or phenolic)
- Etchant (ferric chloride, cupric chloride, or ammonium persulfate)
- Resist (to protect copper you want to keep)

**Methods**:

**1. Direct Drawing**:
- Draw circuit pattern on copper with permanent marker or resist pen
- Etch away unmarked copper
- Remove resist
- Drill holes
- Insert and solder components

**2. Transfer Method**:
- Print circuit pattern with laser printer on glossy paper
- Iron onto copper (heat transfers toner)
- Toner acts as resist
- Etch, remove toner, drill, solder

**3. Photoresist Method** (Best Quality):
- Coat copper with photoresist
- Expose through film positive of circuit pattern
- Develop (removes exposed or unexposed areas, depending on resist type)
- Etch
- Remove remaining resist
- Drill and solder

**Making Copper-Clad Board**:
1. **Substrate**: Fiberglass sheet, phenolic board, or even wood
2. **Adhesive**: Epoxy or other strong glue
3. **Copper**: Thin foil (0.035 mm or 1 oz/ft²)
4. **Laminate**: Press copper to substrate with adhesive, apply heat and pressure
5. **Result**: Smooth, flat copper-clad board

**Etching Process**:
1. Apply resist pattern
2. Submerge in etchant (ferric chloride typical)
3. Agitate gently
4. Wait 30-60 minutes (until exposed copper dissolved)
5. Remove, wash thoroughly
6. Remove resist with solvent

**Drilling**:
- Small drill (0.8-1.0 mm for component leads)
- Drill press or rotary tool
- Deburr holes

### Soldering

**Purpose**: Electrically and mechanically connect components

**Materials**:
- **Solder**: Tin-lead alloy (60/40 or 63/37) or lead-free (tin-copper-silver)
  - Melting point: 180-190°C (tin-lead), higher for lead-free
- **Flux**: Rosin or acid flux (cleans oxidation, helps solder flow)
- **Soldering iron**: 15-60W, temperature-controlled best
- **Tip**: Copper, iron-plated, various shapes

**Process**:
1. Clean surfaces (no oxidation, grease, or dirt)
2. Heat both parts with iron (3-5 seconds)
3. Apply solder to joint (not to iron)
4. Solder melts and flows into joint
5. Remove solder, then iron
6. Hold still until solder solidifies (1-2 seconds)

**Good Solder Joint**:
- Shiny, smooth surface
- Concave fillet shape
- Solder wets both surfaces

**Bad Solder Joint**:
- Dull, grainy (cold joint—not enough heat)
- Blobby (too much solder)
- No wetting (dirty surfaces or no flux)

**Desoldering**:
- Solder wick (copper braid): Absorbs molten solder
- Solder sucker (pump): Vacuum removes solder
- Heat joint, apply removal tool

### Wire and Cabling

**Wire Types**:
- **Solid core**: Single strand, easy to insert in breadboard, stiff
- **Stranded**: Multiple strands, flexible, better for movement
- **Magnet wire**: Thin enamel insulation, for coils
- **Hookup wire**: Insulated, 22-26 AWG typical for electronics

**Stripping Wire**:
- Wire strippers (tool)
- Or carefully with knife (don't nick conductor)

**Connectors**:
- Salvage various types (USB, power, data, etc.)
- Screw terminals for easy connect/disconnect
- Solder joints for permanent

## Building Functional Circuits

### Power Supply (AC to DC)

**Components**:
1. **Transformer**: Step down AC voltage (120V → 12V)
2. **Rectifier**: Diode bridge converts AC to pulsing DC
3. **Filter capacitor**: Large electrolytic (1,000+ µF) smooths pulsing
4. **Voltage regulator**: IC (7805, 7812, etc.) provides stable voltage
5. **Output capacitors**: Reduce noise

**Circuit**:
```
AC in → Transformer → Diode bridge → Filter cap → Regulator → Output
                                                        |
                                                       GND
```

**Result**: Clean, regulated DC voltage for electronics

### Amplifier (Audio)

**Simple Transistor Amplifier**:
1. **Input**: Audio signal (microphone, radio, etc.)
2. **Transistor**: NPN type (2N2222 or similar)
3. **Biasing resistors**: Set operating point
4. **Coupling capacitors**: Pass AC, block DC
5. **Load**: Speaker or next stage

**Gain**: 10-100× typical for single stage

**Improvement**: Multiple stages for more gain, or use op-amp IC

### Oscillator (Signal Generator)

**Relaxation Oscillator** (Simple):
- Resistor charges capacitor
- Device (transistor, tube, or IC) discharges capacitor when voltage reaches threshold
- Repeat
- Creates square wave or sawtooth

**LC Oscillator** (Sine Wave):
- Inductor and capacitor resonate at specific frequency
- Amplifier sustains oscillation
- Clean sine wave output

**Crystal Oscillator** (Precise):
- Quartz crystal determines frequency
- Transistor or IC amplifier
- Extremely stable frequency

**555 Timer IC** (Versatile):
- Astable mode: Continuous oscillation
- Monostable mode: Single pulse
- Frequency set by external resistors and capacitors
- Frequency = 1.44 / ((R1 + 2×R2) × C)

### Logic Gates (Digital Basics)

**Basic Gates**:
- **NOT**: Inverts signal (1→0, 0→1)
- **AND**: Output 1 only if all inputs 1
- **OR**: Output 1 if any input 1
- **NAND**: NOT-AND (universal gate—can build any logic)
- **NOR**: NOT-OR (also universal)
- **XOR**: Exclusive OR (output 1 if inputs different)

**Implementation**:

**With Relays** (Mechanical):
- Slow, bulky, but easy to understand and build
- Relay coil energized = switch closes

**With Vacuum Tubes**:
- Moderate speed, large, power-hungry
- But buildable with modest equipment

**With Transistors** (Best):
- Fast, small, efficient
- Discrete transistor logic or salvaged ICs

**With ICs** (Easiest if Available):
- 7400 series TTL logic
- 4000 series CMOS logic
- Salvage from old computers and electronics

**Building Combinational Logic**:
- Combine gates to create: Adders, multiplexers, decoders, encoders
- Foundation of computer arithmetic and control

**Building Sequential Logic**:
- Flip-flops (memory elements)
- Counters, shift registers, state machines
- Foundation of computer memory and control

## Test Equipment

You can't build electronics without measuring and testing:

### Multimeter

**Essential Tool**: Measures voltage, current, resistance, continuity

**Salvage Priority**: High. Digital multimeters are common in 2025.

**Building a Simple Meter**:
- **Galvanometer**: Coil in magnetic field, current causes deflection
  - Build: Wind coil, suspend in magnetic field from permanent magnets
  - Attach needle to show deflection
- **Shunt resistors**: Measure different current ranges
- **Multiplier resistors**: Measure different voltage ranges

**Digital Multimeter**:
- Requires IC (salvage only in early stages)
- Much more precise and easier to read

### Oscilloscope

**Purpose**: Visualize voltage over time (waveforms)

**Salvage Priority**: High, but less common than multimeters

**Components**:
- **CRT (Cathode Ray Tube)**: Electron beam draws waveform on phosphor screen
- **Vertical amplifier**: Scales input signal
- **Horizontal timebase**: Sweeps beam across screen
- **Trigger circuit**: Stabilizes display

**Building**: Very difficult, requires CRT and complex circuits

**Alternative**: Use computer with ADC (analog-to-digital converter) as digital oscilloscope

### Signal Generator

**Purpose**: Create test signals (sine, square, triangle waves at various frequencies)

**Simple Version**:
- 555 timer IC for square waves
- LC oscillator for sine waves
- Variable resistors and capacitors to change frequency

**Advanced**:
- Microcontroller-based (if you have programmable ICs)
- Direct Digital Synthesis (complex)

### Component Tester

**Purpose**: Test resistors, capacitors, transistors, diodes

**LCR Meter**: Measures inductance (L), capacitance (C), resistance (R)

**Transistor Tester**: Identifies type (NPN/PNP), measures gain (hFE)

**Build or Salvage**: Simple testers can be built with 555 timers or op-amps

## Component Values and Selection

### Reading Component Values

**Resistor Color Codes**:
- Band 1: First digit
- Band 2: Second digit
- Band 3: Multiplier (number of zeros)
- Band 4: Tolerance (gold=5%, silver=10%)
- Colors: Black=0, Brown=1, Red=2, Orange=3, Yellow=4, Green=5, Blue=6, Violet=7, Gray=8, White=9

**Capacitor Markings**:
- Often numeric code: 104 = 10 × 10⁴ pF = 100,000 pF = 0.1 µF
- Or direct value printed
- Polarity marked on electrolytic capacitors

### Standard Values

**E12 Series** (10% tolerance):
- 10, 12, 15, 18, 22, 27, 33, 39, 47, 56, 68, 82, then ×10

**E24 Series** (5% tolerance):
- More values in between

**Why Standard Values**: Manufacturing ease, sufficient for most designs

**Creating Non-Standard Values**:
- Series resistors: R_total = R1 + R2
- Parallel resistors: 1/R_total = 1/R1 + 1/R2
- Series capacitors: 1/C_total = 1/C1 + 1/C2
- Parallel capacitors: C_total = C1 + C2

## Troubleshooting

**Common Problems**:
- **No power**: Check supply voltage, fuses, connections
- **Intermittent**: Cold solder joints, loose wires
- **Wrong output**: Component values wrong, circuit error, damaged components
- **Overheating**: Excessive current, insufficient heat sinking, shorted component

**Debugging Process**:
1. Visual inspection: Burnt components, poor solder joints, wrong components
2. Power check: Verify all voltages correct
3. Signal tracing: Follow signal path with oscilloscope or meter
4. Component testing: Test individual components out of circuit
5. Comparison: Compare to known-good circuit or schematic

## Summary: Electronics Capability Stages

**Stage 1 (Year 0-5): Salvage and Simple Circuits**
- Use salvaged components
- Build simple circuits (power supplies, amplifiers, oscillators)
- Construct basic test equipment
- PCB etching

**Stage 2 (Year 5-15): Vacuum Tubes and Discrete Transistors**
- Manufacture vacuum tubes
- Build tube amplifiers, radios, simple computers
- Attempt germanium transistor production
- Advanced circuit design

**Stage 3 (Year 15-30): Silicon Transistors and Simple ICs**
- Silicon transistor production
- Basic IC fabrication (small-scale integration)
- Digital logic systems
- Advanced test equipment

**Stage 4 (Year 30+): Modern Electronics**
- Large-scale IC production
- Microprocessors
- High-speed digital systems
- Advanced analog circuits

## Safety Reminders

**Electrical Shock**:
- Even low-voltage circuits can have high-voltage sections (power supplies, CRTs)
- Capacitors store charge after power off
- Always discharge capacitors before handling

**Heat**:
- Soldering irons, components get hot
- Don't touch components immediately after soldering
- Heat sinks for power components

**Fumes**:
- Solder flux produces fumes (use ventilation)
- Burning components release toxic fumes
- Work in ventilated area

**Static Electricity**:
- Can destroy CMOS ICs and MOSFETs
- Use anti-static wrist strap when handling sensitive components
- Store in conductive foam or anti-static bags

## Next Steps

With basic electronic components mastered, you can now:
- Build communication systems (Chapter 6)
- Create vacuum tube circuits (Chapter 7)
- Attempt transistor manufacturing (Chapter 8)
- Design and build computers (Chapter 9)

Electronics is the control layer. Mechanical systems provide power, electronics provide intelligence. Master these components, and you're ready to build complex systems.

**Key Principle**: Salvage first, build simple passives second, attempt active components third. Vacuum tubes are easier to manufacture than transistors. Transistors are easier than ICs. Progress in stages, and use salvaged advanced components as long as possible.
