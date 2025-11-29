# Chapter 5: Basic Electronic Components

## From Electricity to Electronics

In Chapter 3, you learned to generate and distribute electricity. Now you'll learn to control it with precision. Electronics is about manipulating electrical signals to:
- Switch circuits on and off
- Amplify weak signals
- Filter and shape waveforms
- Store and process information
- Convert between different forms of energy

Every computer, radio, and modern device depends on electronic components. This chapter covers the fundamental building blocks.

**Chapter Dependencies and Cross-References:**

This chapter builds foundational electronics knowledge required for all advanced technology. For complete implementation, reference:

**Prerequisites (Read First):**
- **Chapter 3: Electricity** — Power generation, voltage, current, AC/DC concepts
- **Chapter 2: Metalworking** — Wire making, metal forming, precision tools
- **Chapter 4: Essential Chemistry** — Etching chemicals (ferric chloride), semiconductor materials

**Advanced Applications (Read After):**
- **Chapter 6: Radio** — RF circuits, amplifiers, oscillators, filters
- **Chapter 7: Vacuum Tubes** — Building active components from scratch
- **Chapter 8: Semiconductors** — Transistor and diode fabrication
- **Chapter 9+: Computers** — Logic gates, memory, processing circuits

**Related Techniques:**
- **Chapter 2.7: Standardization** — Measurement precision for component values
- **Chapter 1: Salvaging** — Harvesting components from old electronics (highest priority!)

**Strategic Approach:**
1. **Salvage first**: Exhaust salvaged components before attempting manufacture
2. **Build simple passives second**: Resistors, capacitors, inductors from basic materials
3. **Attempt active components third**: Vacuum tubes before transistors (much easier)

Whenever this chapter references "see Chapter X," treat it as essential for that technique.

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

**Dielectric Properties and Performance:**

The dielectric material between capacitor plates determines performance characteristics.

**Paper/Oil Capacitors:**
- **Dielectric**: Oil-impregnated paper
- **Voltage rating**: Very high (kV range possible)
- **Frequency**: Low frequency (DC to audio)
- **Temperature stability**: Fair
- **ESR**: Low to moderate
- **Applications**: Power factor correction, high-voltage coupling, tube amplifiers
- **Construction**: Paper between foil, rolled, immersed in oil, sealed
- **Advantages**: High voltage capability, self-healing (small faults burn clear)
- **Disadvantages**: Large, can leak oil

**Ceramic Capacitors:**
- **Dielectric**: Ceramic (various formulations)
- **Types by temperature coefficient**:
  - **NPO (COG)**: Near-zero temp coefficient, very stable, low capacitance
  - **X7R**: ±15% over -55°C to +125°C, moderate capacitance
  - **Y5V**: ±22% to -82% over temperature, high capacitance but unstable
  - **Z5U**: Similar to Y5V, older designation
- **Voltage**: Low to moderate (10V-1kV)
- **Frequency**: DC to RF (GHz capable)
- **Applications**:
  - NPO: Precision timing, filters, oscillators (where stability critical)
  - X7R: General-purpose bypass, coupling
  - Y5V/Z5U: Bulk bypass (where exact value not critical)
- **Advantages**: Small, cheap, reliable, wide frequency range
- **Disadvantages**: Value varies with voltage (especially Y5V), temperature

**Polyester (Mylar) / Polypropylene Film:**
- **Dielectric**: Plastic film
- **Voltage**: Moderate (50V-600V typical)
- **Frequency**: DC to several MHz
- **Temperature stability**: Good (polyester), Excellent (polypropylene)
- **ESR**: Low
- **Applications**: General-purpose audio, timing, signal coupling
- **Advantages**: Stable, reliable, good all-around characteristics
- **Disadvantages**: Larger than ceramic for same value
- **Post-collapse**: Can be made from salvaged plastic film

**Mica Capacitors:**
- **Dielectric**: Thin mica sheets
- **Voltage**: Moderate to high
- **Frequency**: DC to VHF/UHF (very low loss)
- **Temperature stability**: Excellent (±0.5%)
- **ESR**: Very low
- **Applications**: RF circuits, precision oscillators, high-frequency filters
- **Advantages**: Very stable, low loss, reliable
- **Disadvantages**: Expensive, limited values, bulky
- **Salvage**: From old radios, transmitters

**Electrolytic Capacitors:**
- **Dielectric**: Thin oxide layer on aluminum or tantalum
- **Capacitance**: Very high (1µF to 100,000µF+)
- **Voltage**: Low to moderate (6V-450V typical)
- **ESR**: High (compared to other types)
- **Frequency**: DC to low frequency only (not for RF)
- **Polarity**: MUST observe polarity (explosion risk if reversed)
- **Lifetime**: Limited (electrolyte dries out over years)
- **Applications**: Power supply filtering, bulk energy storage
- **Advantages**: High capacitance in small space, cheap
- **Disadvantages**: Polarized, high ESR, limited life, can fail catastrophically

**ESR (Equivalent Series Resistance):**

All real capacitors have internal resistance (ESR) in series with ideal capacitance.

**Effects of ESR:**
- **Power loss**: I²R heating in capacitor
- **Voltage drop**: Reduces filtering effectiveness
- **Frequency response**: Limits high-frequency performance

**Typical ESR values:**
- Ceramic (small): 0.01-0.1Ω
- Film: 0.01-1Ω
- Electrolytic (small): 0.1-5Ω
- Electrolytic (large): 0.01-0.5Ω

**Low ESR matters for:**
- High-frequency bypass (digital circuits)
- Switching power supplies
- Pulse applications

**Capacitor Selection Guide:**

| Application | Best Type | Reason |
|-------------|-----------|--------|
| Power supply filter | Electrolytic | High capacitance |
| Bypass (digital) | Ceramic (X7R) + electrolytic | Low ESR + bulk capacity |
| RF coupling | Ceramic (NPO) or mica | Stable, low loss |
| Precision timing | Ceramic (NPO), polyester, mica | Temperature stable |
| Audio coupling | Film (polyester/polypropylene) | Low distortion |
| High voltage DC | Paper/oil or film | Voltage capability |

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

**Inductor Core Materials (Detailed):**

The core material dramatically affects inductor performance. Choose based on frequency, current, and available materials.

**Air Core:**
- **Material**: Nothing (just wire coil)
- **Advantages**: No saturation, no losses, stable
- **Disadvantages**: Low inductance for size
- **Applications**: RF circuits (MHz), high-frequency oscillators
- **When to use**: Above 10 MHz, or when very stable inductance needed

**Solid Iron Core:**
- **Material**: Iron rod or wire bundle
- **Advantages**: Very simple, high permeability (µ ≈ 100-1000)
- **Disadvantages**: Eddy current losses heat core at AC frequencies
- **Applications**: DC chokes, low-frequency (<100 Hz)
- **Construction**: Insert iron rod into coil center, or wind around iron rod

**Laminated Iron Core:**
- **Material**: Thin iron sheets (0.014"-0.025" thick), insulated between layers
- **Advantages**: Reduced eddy currents, works to ~10 kHz
- **Disadvantages**: Requires thin sheet fabrication
- **Applications**: Power transformers (50/60 Hz), audio transformers
- **Construction**: Stack iron sheets, clamp together, wind coil around stack
- **Insulation**: Varnish, paper, or oxide layer between sheets

**Powdered Iron Cores:**
- **Material**: Iron powder mixed with insulating binder
- **Construction**:
  1. Grind iron to fine powder (file iron, collect filings)
  2. Mix with binder (epoxy, varnish, or sodium silicate)
  3. Ratio: ~80% iron, 20% binder by volume
  4. Press into mold under pressure
  5. Cure binder (heat if epoxy, air-dry if varnish)
- **Result**: Each iron particle insulated, minimal eddy currents
- **Permeability**: Lower than solid iron (µ ≈ 10-100) but stable
- **Applications**: 100 kHz - 10 MHz, switching power supplies
- **Advantages**: Can be formed into shapes (toroids, rods, slugs)

**Ferrite Cores:**
- **Material**: Iron oxide (Fe₂O₃) + manganese/zinc/nickel oxides, sintered
- **Composition examples**:
  - **Manganese-zinc ferrite**: Good for <1 MHz, higher permeability
  - **Nickel-zinc ferrite**: Good for 1-100 MHz, lower losses
- **Manufacturing** (advanced, requires kiln):
  1. Mix powdered iron oxide + other metal oxides
  2. Add binder, press into shape
  3. Sinter at 1200-1400°C in controlled atmosphere
  4. Cool slowly
- **Permeability**: µ = 100-10,000 depending on composition
- **Applications**: RF transformers, high-frequency chokes, EMI suppression
- **Salvage**: Ferrite beads and cores from old electronics (best source post-collapse)

**Toroidal Cores (Ring Shape):**
- **Geometry**: Donut/ring shape
- **Advantages**:
  - Magnetic field completely contained (minimal radiation)
  - No air gap (unless intentional)
  - Higher inductance per turn
  - Less interference with nearby components
- **Disadvantages**: Harder to wind (thread wire through center repeatedly)
- **Materials**: Can be powdered iron, ferrite, or laminated steel
- **Applications**: Power supply chokes, balanced transformers, precision inductors
- **Winding**: Use shuttle or needle to pass wire through center hole

**Air Gaps in Cores:**

Sometimes you intentionally add a gap in the magnetic circuit:

**Purpose:**
- **Prevents saturation** in high-current inductors
- **Stores energy** in the gap (magnetic field energy)
- **Reduces permeability** in controlled way
- **Linearizes** inductance vs. current

**Construction:**
- Cut core, insert non-magnetic spacer (paper, plastic)
- Gap size: 0.001" to 0.1" depending on application
- Larger gap = lower inductance but higher saturation current

**When to use:**
- Power inductors (DC bias current)
- Switching power supply inductors
- When core saturation is a problem

**Gap sizing**: Smaller gap = more inductance but saturates easier

**Core Selection Guide:**

| Frequency | Core Type | Permeability | Application |
|-----------|-----------|--------------|-------------|
| DC-100Hz | Laminated iron | 1000-5000 | Power transformers, chokes |
| 100Hz-100kHz | Powdered iron | 10-100 | Audio, switching supplies |
| 100kHz-10MHz | Powdered iron | 10-100 | RF chokes, resonant circuits |
| 10MHz+ | Air or ferrite | 1 (air), 10-100 (ferrite) | RF coils, antennas |

**Salvage Priority:**
- Ferrite beads/cores from cables, power supplies
- Iron transformer cores from old equipment
- Toroidal cores from computer power supplies

**Transformer** (Two Coupled Inductors):
1. **Primary coil**: Input
2. **Secondary coil**: Output
3. **Shared core**: Magnetic coupling
4. **Turns ratio**: Determines voltage transformation
   - Voltage ratio = Turns ratio
   - Example: 1000 turns primary, 100 turns secondary = 10:1 step down
5. **Construction**: See below for detailed winding guidance

**Transformer Winding Details:**

**Turns Per Volt Calculation:**

The number of turns needed depends on core size, material, and frequency.

**Formula** (approximate for iron core, 50/60 Hz):
```
Turns per volt = 1 / (4.44 × f × Ac × Bmax × 10⁻⁴)

Where:
f = frequency (Hz)
Ac = core cross-sectional area (cm²)
Bmax = maximum flux density (gauss, typically 10,000-14,000 for iron)
```

**Simplified rule of thumb** (50/60 Hz power transformer):
- **Small core** (1 cm² area): ~10-15 turns/volt
- **Medium core** (4 cm² area): ~3-5 turns/volt
- **Large core** (16 cm² area): ~1-2 turns/volt

**Example**: 120V primary on medium core (4 cm² area):
- Turns/volt ≈ 4
- Primary turns = 120V × 4 = 480 turns
- For 12V secondary: 12V × 4 = 48 turns

**Measuring unknown core:**
1. Wind test coil (e.g., 100 turns)
2. Apply known voltage, measure current
3. If current excessive, need more turns/volt
4. If no heating and low current, can use fewer turns/volt

**Wire Gauge Selection:**

Wire must handle current without overheating.

**Current density**: 2-4 A/mm² safe for continuous operation

**AWG gauge selection**:
| Current | AWG | Wire diameter |
|---------|-----|---------------|
| 0.1 A | 30 | 0.25 mm |
| 0.5 A | 24 | 0.51 mm |
| 1 A | 20 | 0.81 mm |
| 2 A | 18 | 1.02 mm |
| 5 A | 14 | 1.63 mm |
| 10 A | 10 | 2.59 mm |

**Winding Technique:**

**Layer-by-layer winding** (most reliable):

1. **First layer** (primary or innermost):
   - Wind turns tightly and evenly
   - Each turn touching previous turn
   - Keep tension consistent
   - Count carefully

2. **Insulation between layers**:
   - **Paper**: Thin paper (onion-skin, wax paper) works
   - **Varnish**: Coat layer with varnish, let dry
   - **Tape**: Electrical tape, fabric tape
   - **Thickness**: 2-3 layers paper minimum between windings
   - **Purpose**: Prevent turn-to-turn shorts between layers

3. **Next layer**:
   - Wind in reverse direction (back toward start)
   - OR wind same direction and bring wire back via lead
   - Continue until correct turns reached

4. **Multiple windings**:
   - Primary closest to core (usually)
   - Secondary outside primary
   - OR interleaved (primary layer, secondary layer, repeat)

**Insulation for Safety (Mains Transformers):**

**Primary/secondary isolation** critical for safety when primary connects to mains voltage:

1. **Physical separation**:
   - Heavy insulation layer between primary and secondary
   - Multiple layers of insulating tape or thick paper
   - Minimum 0.1mm thick insulation
   - OR wind primary and secondary on separate bobbins

2. **End insulation**:
   - Insulate wire ends
   - Prevent flash-over at connections
   - Heat-shrink tubing or tape

3. **Testing isolation**:
   - Measure resistance between primary and secondary with megohmmeter
   - Should be >1 MΩ (preferably >10 MΩ)
   - If <100kΩ, insulation inadequate

**Center-Tapped Secondary:**

For full-wave rectification without bridge rectifier:

**Construction**:
1. Wind half of secondary turns
2. Bring out tap wire (solder to connection point)
3. Continue winding remaining turns
4. Result: Three connections (two ends + center)

**Example**: 24V center-tapped:
- Primary: 480 turns (for 120V input)
- Secondary: 48 turns each side of center tap (96 total)
- Center tap at turn 48
- Output: 12V-0V-12V (24V total, 12V each half)

**Special Winding Configurations:**

**Bifilar winding** (two wires wound together):
- Wind two wires side-by-side simultaneously
- Very tight magnetic coupling
- Used for current transformers, isolated supplies
- Ensures identical turns count

**Pi-wound sections**:
- Split winding into sections
- Interleave primary and secondary sections
- Reduces leakage inductance
- Better high-frequency response

**Winding Direction:**

**Phasing matters** when connecting multiple secondaries:

- Mark start of each winding (dot convention)
- Windings wound in same direction = in-phase
- Test: Connect secondaries in series, measure voltage
  - If in-phase: Voltages add
  - If out-of-phase: Voltages subtract

**Common Winding Problems:**

| Problem | Cause | Fix |
|---------|-------|-----|
| Overheating | Too few turns (saturation) | Add turns |
| No output | Broken winding | Check continuity, rewind |
| Low output | Shorted turns | Check for insulation damage, rewind |
| Hum/vibration | Loose laminations | Tighten core, varnish impregnate |
| Arcing | Insufficient insulation | Add more insulation layers |

**Impregnation** (improves reliability):
- After winding, dip transformer in varnish
- Let varnish soak into windings
- Dry/cure
- Result: Moisture protection, mechanical strength, better cooling

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
- Forward: Low resistance (voltage drop varies by type)
- Reverse: High resistance (infinite)

**Forward Voltage Drop (Vf) by Diode Type:**

**Silicon Diodes** (~0.6-0.7V typical):
- **Signal diodes** (1N4148, 1N914): 0.7V at 10mA
- **Rectifier diodes** (1N4001-1N4007): 0.7V at 1A
- **Power rectifiers**: 0.7-1.0V at higher currents
- Most common type, robust, temperature stable

**Germanium Diodes** (~0.3V typical):
- Lower voltage drop than silicon
- **Advantages**:
  - Low-voltage rectification (useful when every 0.1V matters)
  - Detector circuits (crystal radio) - minimal signal loss
  - Precision applications where 0.7V is too much
- **Disadvantages**:
  - Higher leakage current (worse reverse blocking)
  - Temperature sensitive (leakage increases with heat)
  - Harder to manufacture post-collapse
- **Salvage**: Old radios, vintage test equipment

**Schottky Diodes** (~0.2-0.4V typical):
- **1N5817**: 0.45V at 1A
- **1N5819**: 0.4V at 1A
- **Advantages**:
  - Very low forward drop = less power loss
  - Fast recovery time (good for high-frequency switching)
  - Lower junction capacitance
- **Applications**:
  - High-efficiency rectifiers (switching power supplies)
  - Reverse polarity protection (lower voltage drop)
  - High-frequency circuits (>100 kHz)
- **Salvage**: Modern power supplies, laptop chargers

**Light Emitting Diodes (LED)** (1.8-3.3V):
- **Red**: ~1.8-2.2V
- **Yellow/Green**: ~2.0-2.4V
- **Blue/White**: ~3.0-3.3V
- Higher forward voltage than rectifier diodes
- Require current limiting resistor

**Zener Diodes** (Breakdown Voltage):
- Forward: Same as silicon (~0.7V)
- Reverse: Controlled breakdown at specified voltage
- Common values: 3.3V, 5.1V, 6.8V, 9.1V, 12V, 15V

**Impact on Circuit Design:**
- **Power efficiency**: Schottky 0.3V vs Silicon 0.7V = 40% less power loss in low-voltage supplies
- **Precision rectifiers**: Lower Vf = better accuracy at low signal levels
- **Detector circuits**: Germanium preferred (0.3V drop preserves weak RF signals)
- **Temperature**: Silicon most stable, germanium worst (leakage doubles every 10°C)
- **High current**: Voltage drop increases (1N4001 at 1A: 0.7V, at 0.1A: 0.6V)

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

**Transistor Biasing (Setting Operating Point):**

For amplifiers, transistor must be biased to operate in linear region. Different biasing methods offer tradeoffs between simplicity and stability.

**1. Fixed Bias** (Simplest, least stable):
```
Vcc → [Rb] → Base
              |
         Transistor
              |
            Emitter → GND
```
- **Pro**: Only two resistors needed
- **Con**: Very temperature-sensitive, gain-dependent
- **Q-point**: Set by Rb value
- **Use**: Only when temperature/gain variation acceptable

**2. Voltage Divider Bias** (Most common):
```
Vcc → [R1] → Base
        |
       [R2] → GND

Emitter → [Re] → GND
```
- **Pro**: Much more stable than fixed bias
- **Con**: More resistors (R1, R2, Re, Rc)
- **Q-point**: Set by R1/R2 ratio and Re
- **Design**: Make divider stiff (low impedance), Ve ≈ 1-2V typical
- **Use**: General-purpose amplifiers

**3. Emitter Degeneration** (Most stable):
```
Voltage divider bias + bypass capacitor across Re

Emitter → [Re] → GND
          [Ce] (parallel with Re)
```
- **Pro**: Excellent stability, temperature compensation
- **Con**: Reduced gain (Re provides negative feedback)
- **Bypass capacitor**: Shorts Re at AC (restores gain), keeps DC feedback
- **Use**: High-quality amplifiers, wide temperature range

**Operating Point Selection:**

**Quiescent current** (Ic with no signal):
- **Class A**: Ic = 50% of max (linear but inefficient)
- **Class B**: Ic ≈ 0 (efficient but distortion at crossover)
- **Class AB**: Small Ic (compromise)

**Design example** (voltage divider bias):
1. Choose Ic (e.g., 1mA for small-signal)
2. Set Ve = 1V (gives headroom)
3. Re = Ve/Ic = 1V/1mA = 1kΩ
4. Vb = Ve + 0.7V = 1.7V (silicon Vbe)
5. R1/R2 divider for Vb (make stiff: R1||R2 < 0.1×β×Re)
6. Rc sets voltage gain

**Temperature Compensation:**
- BJTs: Vbe drops ~2mV/°C
- Without compensation: Ic drifts, distortion increases
- Emitter resistor Re provides automatic compensation
- More Re = more stable but less gain

**Common Salvage Transistors**:
- 2N2222, 2N3904 (NPN, general purpose, small signal)
- 2N3906, 2N2907 (PNP, general purpose, small signal)
- 2N3055, TIP31/32 (NPN/PNP, power)
- BS170, 2N7000 (N-channel MOSFET, small signal)
- IRF540, IRFZ44 (N-channel MOSFET, power)

**Heat Sinking for Power Transistors:**

Power transistors dissipate heat (P = Vce × Ic). Without heatsinking, they overheat and fail.

**Thermal Resistance Concept:**
- Measured in °C/W (degrees Celsius per watt)
- Analogous to electrical resistance
- **Junction to case** (Rθjc): Inside transistor (~1-5°C/W)
- **Case to heatsink** (Rθcs): Thermal interface (~0.5-2°C/W)
- **Heatsink to ambient** (Rθsa): Heatsink itself (~1-50°C/W)

**Total**: Rθja = Rθjc + Rθcs + Rθsa

**Temperature rise**: ΔT = P × Rθja

**Example**: 2N3055 dissipating 10W
- Rθjc = 1.5°C/W
- Rθcs = 1°C/W (with thermal paste)
- Rθsa = 5°C/W (small heatsink)
- Rθja = 7.5°C/W
- ΔT = 10W × 7.5°C/W = 75°C rise
- If ambient = 25°C, junction = 100°C (safe, max usually 150°C)

**Heatsink Sizing:**
1. **Calculate power**: P = Vce × Ic
2. **Determine max Tj**: From datasheet (typically 150°C)
3. **Calculate required Rθsa**:
   - Rθsa = (Tj_max - T_ambient)/P - Rθjc - Rθcs
4. **Select heatsink** with Rθsa lower than calculated

**Heatsink Types:**
- **Finned aluminum**: Most common, various sizes
- **Black anodized**: Better radiation (lower Rθsa)
- **Fan-cooled**: Much better (forced convection)
- **Natural convection**: Passive, quiet, larger

**Mounting Techniques:**
1. **Thermal paste**: Fill microscopic air gaps
   - Thin layer only (too much reduces effectiveness)
   - Types: Silicone-based, zinc oxide, Arctic Silver
2. **Thermal pads**: Pre-formed, easier but slightly worse
3. **Insulators**: If transistor case must be isolated
   - Mica washer + thermal paste
   - Silicone pad
   - Reduces thermal performance but necessary for safety

**Thermal Management Tips:**
- Mount heatsink vertically (natural convection works better)
- Don't paint heatsink (reduces radiation)
- Ensure good airflow
- Multiple transistors: Separate heatsinks or very large shared one
- Test: Touch heatsink - should be warm but not painful to touch

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

**Voltage Regulator Alternatives (When ICs Unavailable):**

If you lack integrated regulator ICs (7805, etc.), these discrete alternatives work:

**1. Zener Diode + Series Resistor** (Simplest, low current):
```
Unregulated DC → [Resistor] → Output
                      |
                   [Zener] → GND
```
- **How**: Zener maintains constant voltage
- **Current**: <100mA (resistor wastes power)
- **Regulation**: Poor (±10%), load-sensitive
- **Use**: Low-power circuits, reference voltages
- **Example**: 12V Zener + 100Ω resistor for 12V at 50mA

**2. Zener + Pass Transistor** (Better, more current):
```
Unregulated → [Resistor] → [Transistor collector]
                   |              |
                [Zener]      (emitter to output)
                   |
                  GND
```
- **How**: Zener sets base voltage, transistor provides current gain
- **Current**: Up to several amps (depends on transistor)
- **Regulation**: Fair (±5%)
- **Heat**: Transistor dissipates (V_dropout × I_load)
- **Use**: General-purpose regulation when ICs unavailable
- **Components**: 12V Zener + 2N3055 power transistor

**3. Series Tube Regulator** (For vacuum tube systems):
```
B+ → [Tube (triode)] → Regulated output
           |
        [Voltage reference]
```
- **How**: Tube acts as variable resistor, controlled by reference
- **Current**: Depends on tube (100mA to 1A+)
- **Regulation**: Good (±2-3% with feedback)
- **Use**: Tube equipment power supplies
- **Tubes**: 6AS7, 6080 (high current), or triode section of multi-section tube

**4. Shunt Regulator** (Constant current load):
```
Unregulated → [Current source] → Output
                                    |
                              [Shunt device]
                                    |
                                   GND
```
- **How**: Excess current shunted to ground
- **Efficiency**: Poor (always wastes power)
- **Regulation**: Excellent
- **Use**: Low-power precision references

**Comparison:**

| Type | Current | Efficiency | Complexity | Use Case |
|------|---------|------------|------------|----------|
| Zener + R | <100mA | Poor | Simplest | References only |
| Zener + Transistor | 1-5A | Fair | Simple | General purpose |
| Series tube | 100mA-1A | Fair | Moderate | Tube equipment |
| IC (7805) | 1.5A | Good | Simplest | Modern (if available) |

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
- Band 3: Multiplier (×10^n where n=band value)
  - Brown (1) = ×10¹ = ×10
  - Red (2) = ×10² = ×100
  - Orange (3) = ×10³ = ×1,000
  - Gold = ×0.1 (for sub-ohm resistors)
  - Silver = ×0.01 (for sub-ohm resistors)
- Band 4: Tolerance (gold=5%, silver=10%, none=20%)
- Colors: Black=0, Brown=1, Red=2, Orange=3, Yellow=4, Green=5, Blue=6, Violet=7, Gray=8, White=9
- Example: Brown-Black-Red-Gold = 10×10² = 1,000Ω = 1kΩ ±5%

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

## Relay Logic (Intermediate Between Manual and Electronic)

Before vacuum tubes or transistors, relays provided automated control. Still valuable for high-power switching and fail-safe systems.

**Relay Types:**

**SPST (Single Pole, Single Throw):**
- One switch, on/off
- Use: Simple on/off control

**SPDT (Single Pole, Double Throw):**
- One input, two outputs (common + NO + NC)
- **NO**: Normally Open (closes when energized)
- **NC**: Normally Closed (opens when energized)
- Use: Selecting between two circuits

**DPDT (Double Pole, Double Throw):**
- Two independent SPDT switches in one relay
- Use: Reversing polarity, switching two signals simultaneously

**Latching Relays:**
- Stay in position after pulse (no continuous power needed)
- Two coils: Set and Reset
- Use: Low-power applications, memory

**Relay Driver Circuits:**

Relays need more current than logic circuits can provide. Use transistor driver:

```
Logic signal → [Rb] → Transistor base
                           |
Vcc → [Relay coil] → Transistor collector
                           |
                      [Flyback diode]
                           |
                        Emitter → GND
```

**Flyback diode critical**: When relay de-energizes, coil generates voltage spike that can destroy transistor. Diode shorts this spike (cathode to Vcc, anode to collector).

**Relay Timing:**
- **Operate time**: 5-50ms typical
- **Release time**: 5-50ms typical
- **Bounce**: Contacts bounce when closing (10-20ms)
  - Problem for digital circuits (looks like multiple pulses)
  - Solution: Debounce circuit (RC + Schmitt trigger, or software delay)

**Relay Logic Examples:**

**AND gate**: Two relays in series
**OR gate**: Two relays in parallel
**NOT gate**: Use NC contact instead of NO
**Latch**: Relay holds itself closed via NO contact

**Advantages:**
- High current/voltage capability
- Complete isolation (input/output electrically separate)
- Visible operation (can see/hear relay state)
- Proven reliability
- EMP resistant

**Disadvantages:**
- Slow (milliseconds vs. nanoseconds for transistors)
- Wear out (mechanical contacts)
- Power hungry (coils draw continuous current)
- Noisy (clicking)

**Post-collapse use:**
- Heavy machinery control
- Power switching
- Safety interlocks
- Simple automation (timers, sequencers)
- Logic before tubes/transistors available

## Grounding and Shielding

Proper grounding prevents noise, hum, oscillation, and safety hazards.

**Grounding Principles:**

**Single-Point Ground** (Audio, Low Frequency):
- All grounds connect at ONE point only
- Prevents ground loops
- Use: Audio amplifiers, low-frequency analog

**Star Ground** (Power Supplies):
- Power supply ground is center of star
- Each section gets dedicated ground wire to center
- Prevents high currents in one section affecting others
- Use: Power supplies feeding multiple circuits

**Multi-Point Ground** (RF, High Frequency):
- Short, direct grounds everywhere
- Ground plane (solid copper sheet or PCB ground plane)
- At high frequency, inductance of long wire is high impedance
- Use: RF circuits, digital circuits above 1 MHz

**Ground Loops (Problem):**

When current flows through ground path, voltage drop occurs. If two circuits share this ground path:
```
Circuit A → [Ground wire, has resistance] → Circuit B
```
Circuit A's current causes voltage in Circuit B's ground = noise/hum

**Solution**: Single-point ground, or eliminate circulating currents

**Example**: Audio system with amp and preamp
- **Wrong**: Preamp grounded to wall, amp grounded to wall (ground loop via AC wiring)
- **Right**: Both grounded at amp chassis only, signal cable shield grounded at one end only

**Shielding:**

**RF Shielding** (Faraday Cage):
- Enclose circuit in conductive enclosure
- Prevents external RF from entering
- Prevents circuit from radiating RF
- Material: Copper, aluminum, steel
- Must be grounded (otherwise acts as antenna)

**Audio Cable Shielding:**
- Braided or foil shield around signal wire
- Shield carries no signal (ground only)
- **Ground shield at one end only** (prevents ground loop)
- Usually ground at receiving end (preamp input, amp input)

**Power Supply Shielding:**
- Transformer generates strong magnetic field
- Shield transformer (mu-metal can if very sensitive)
- Keep transformers away from audio circuits
- Orient transformer perpendicular to sensitive circuits

**Shielding Effectiveness:**
- Solid sheet better than mesh
- Multiple layers better than single
- Seams must make good electrical contact
- Openings reduce effectiveness (keep small)

**Practical Grounding Tips:**
1. Heavy ground wires (short, thick = low impedance)
2. Power ground separate from signal ground until final connection point
3. Digital ground separate from analog ground until power supply
4. High-current paths (power) away from sensitive circuits (preamp)
5. Test for ground loops: Disconnect grounds one by one, listen for hum changes

## Component Substitution Guide

When exact part unavailable, these substitutions often work:

**Resistors:**
| Need | Substitute | Notes |
|------|------------|-------|
| 10kΩ | 12kΩ | ±20% usually acceptable |
| 10kΩ | Two 5.6kΩ in series (11.2kΩ) | Closer value |
| 10kΩ | Two 20kΩ in parallel (10kΩ exact) | Perfect match |
| Exact value | Series/parallel combination | Use online calculator |

**Capacitors:**
| Need | Substitute | Notes |
|------|------------|-------|
| 0.1µF ceramic | 0.1µF polyester | Different characteristics but often works |
| Electrolytic | Multiple smaller in parallel | Add capacitances |
| High-voltage | Multiple in series | Voltages add, capacitances divide |

**Transistors:**
| Need | Substitute | Notes |
|------|------------|-------|
| 2N2222 (NPN) | 2N3904, BC547, BC337 | Similar specs |
| 2N3904 | 2N2222 (higher power) | Works but overkill |
| 2N3906 (PNP) | 2N2907, BC557 | Similar specs |
| 2N3055 (power NPN) | TIP31, TIP41 (lower power) | Check current rating |

**Diodes:**
| Need | Substitute | Notes |
|------|------------|-------|
| 1N4148 (signal) | 1N914, 1N4001 | 1N4001 slower but works |
| 1N4001 (rectifier) | Any 1N400x series | Higher number = higher voltage |
| Zener voltage | Series/parallel combination | Can create needed voltage |

**ICs:**
| Need | Substitute | Notes |
|------|------------|-------|
| 7805 (5V reg) | LM317 + resistors | Adjustable regulator programmed for 5V |
| 555 timer | Two transistors + RC components | Discrete equivalent exists |
| Op-amp (741) | Any general-purpose op-amp | 358, 324, TL071, etc. |

**General Rules:**
- Higher voltage rating is safe (10V cap in 5V circuit is fine)
- Higher current rating is safe (5A transistor for 1A load is fine)
- Higher power rating is safe (2W resistor where 1W needed is fine)
- **Never** use lower ratings (will fail)

## First Circuits to Build

Start simple, gain experience, build confidence.

**Circuit 1: LED + Resistor (1 hour)**
```
Battery (+) → [Resistor 330Ω] → [LED] → Battery (-)
```
- **Learns**: Current limiting, LED polarity
- **Confirms**: Power supply works, resistor values
- **Success**: LED glows
- **Troubleshoot**: Wrong polarity, resistor too high, battery dead

**Circuit 2: Voltage Divider (1 hour)**
```
Vcc → [R1] → [Measure here] → [R2] → GND
```
- **Learns**: Ohm's law, voltage division
- **Use**: Create reference voltages, attenuate signals
- **Success**: Vout = Vin × R2/(R1+R2)
- **Experiment**: Change ratios, measure results

**Circuit 3: RC Time Constant (2 hours)**
```
Switch → [R] → [C] → GND
               |
          [Measure voltage]
```
- **Learns**: Capacitor charging, exponential curves
- **Observe**: Voltage rises when switch closes (τ = R×C)
- **Success**: Time to 63% = R×C seconds
- **Use**: Timing, delays, filters

**Circuit 4: Transistor Switch (2-3 hours)**
```
Vcc → [LED + resistor] → Transistor collector
Input → [Rb] → Transistor base
Transistor emitter → GND
```
- **Learns**: Transistor as switch, current gain
- **Success**: Input high = LED on, input low = LED off
- **Calculate**: Rb for sufficient base current

**Circuit 5: Astable Multivibrator (3-4 hours)**

Two transistors, two LEDs blink alternately (no IC needed!)
```
Classic flip-flop circuit using two transistors cross-coupled
```
- **Learns**: Positive feedback, oscillation
- **Success**: LEDs blink back and forth
- **Frequency**: Set by RC values
- **Troubleshoot**: If oscillates too fast, increase C or R

**Circuit 6: Audio Amplifier (4-6 hours)**
```
Microphone → [coupling cap] → Transistor amplifier → Speaker
```
- **Learns**: AC amplification, biasing, coupling
- **Success**: Hear amplified sound
- **Improvement**: Add volume control (potentiometer)
- **Challenge**: Minimize distortion

**Learning Progression:**
1. Passive components first (resistors, caps)
2. Add simple active (transistor switch)
3. Build simple oscillators
4. Try amplifiers
5. Combine into useful circuits (radio, audio, control)

**Documentation:**
- Keep notes on what works
- Schematic of every successful circuit
- Component values used
- Problems encountered and solutions

## Component Storage and Organization

Organized parts save time and prevent mistakes.

**Resistor Storage:**
- **Sort by value**: 1kΩ, 2.2kΩ, 4.7kΩ, 10kΩ, etc.
- **Label clearly**: Use decade/power notation (1k, 10k, 100k)
- **Small compartments**: Tackle box, parts organizer, labeled bags
- **Standard values first**: Stock E12 series (10, 12, 15, 18, 22, 27, 33, 39, 47, 56, 68, 82 for each decade)

**Capacitor Storage:**
- **Sort by type AND value**:
  - Ceramic separate from electrolytic
  - Film separate from both
- **Watch polarity**: Electrolytics marked + clearly
- **Voltage rating**: Note on label (critical info)
- **Anti-static for high-voltage**: Discharge before handling

**Semiconductor Storage:**
- **By type**: NPN, PNP, MOSFET, diodes separate
- **Static protection**: Anti-static foam, bags, tubes
- **Label pinout**: Save datasheet or note pinout on storage
- **Test before storage**: Mark good/tested vs. unknown/salvage

**IC Storage:**
- **Anti-static tubes or foam**
- **Keep documentation**: Tape datasheet to storage container
- **By function**: Logic, analog, power, specialized
- **Note replacements**: If IC rare, note possible substitutes

**Wire Storage:**
- **By gauge**: 22AWG, 20AWG, 18AWG, etc.
- **By type**: Solid/stranded, insulated/bare
- **By color**: Keep colors organized for ease of use
- **On spools or coiled**: Prevents tangles

**Hardware Storage:**
- Screws, nuts, washers in separate compartments
- Heatsinks, sockets, connectors organized by type
- PCBs, perfboard in flat storage (prevent warping)

**Labeling System:**

**Minimum label info:**
- Component value (100Ω, 0.1µF, 2N2222)
- Quantity approximate
- Source/date if tracking

**Advanced label (for critical parts):**
- Specifications (voltage, current, tolerance)
- Cross-references (substitutes that work)
- Supplier/salvage source
- Test status (verified good vs. unknown)

**Inventory:**
- Simple list (paper or digital)
- Note when running low
- Prioritize salvage operations for depleted types
- Track usage patterns (which values used most)

**Workspace Organization:**
- Frequently-used components in easy reach
- Rarely-used in storage
- Test equipment accessible but protected
- Tools organized by function
- Good lighting (critical for small components)
- Magnification (reading component markings)

**Safety in Storage:**
- High-voltage caps: Discharge before storage, store shorted
- Batteries: Remove from old equipment before corrosion
- Chemicals (etchants): Separate, labeled, sealed
- Sharp leads: Trim or protect ends

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
