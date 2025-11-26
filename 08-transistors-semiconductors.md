# Chapter 8: Transistors and Semiconductor Electronics

## The Transistor Revolution

The transistor, invented in 1947, transformed electronics:
- **Size**: 1/1000th volume of vacuum tube
- **Power**: 1/100th consumption
- **Life**: Years instead of months
- **Speed**: No warm-up, faster switching
- **Reliability**: Solid state, no moving parts or filaments to burn out

But transistors are **much harder to manufacture** than tubes. You need:
- Ultra-pure semiconductor materials (silicon or germanium)
- Precise doping control (parts per million)
- Clean environment
- Advanced equipment

**Timeline**: Expect 20-40 years post-collapse before transistor manufacturing is practical.

## Semiconductor Fundamentals

### Crystal Structure and Doping

**Pure Silicon**:
- 4 valence electrons
- Forms diamond crystal structure
- Covalent bonds with 4 neighbors
- At absolute zero: Perfect insulator
- At room temp: Small conductivity (thermally generated electron-hole pairs)

**N-Type Doping** (Negative Charge Carriers):
- Add phosphorus or arsenic (5 valence electrons)
- Extra electron becomes mobile charge carrier
- Concentration: 10¹⁴ to 10¹⁸ atoms/cm³ (parts per million to parts per thousand)

**P-Type Doping** (Positive Charge Carriers):
- Add boron or gallium (3 valence electrons)
- Missing electron creates "hole" (behaves like positive charge)
- Holes are mobile charge carriers

**PN Junction**:
- Boundary between P and N regions
- Depletion region forms (no mobile carriers)
- Voltage barrier prevents current flow
- **Forward bias** (P positive, N negative): Current flows
- **Reverse bias** (P negative, N positive): Current blocked
- This is a **diode**

### Transistor Operation

**Bipolar Junction Transistor (BJT)**:

**NPN Structure**:
- Emitter: Heavily doped N
- Base: Thin, lightly doped P
- Collector: Lightly doped N

**Operation**:
- Base-emitter junction forward biased: Electrons flow from emitter to base
- Most electrons cross thin base to collector (attracted by positive voltage)
- Small base current controls large collector current
- Current gain (β): 50-500 typical
- Collector current = β × Base current

**PNP Structure**:
- Opposite polarity (P-N-P)
- Holes are majority carriers
- Operates similarly but voltages reversed

**Field Effect Transistor (FET)**:

**JFET (Junction FET)**:
- Channel of N or P material
- Gate: Opposite type material forms junction
- Voltage on gate controls channel conductivity
- Voltage-controlled device (vs. current-controlled BJT)

**MOSFET (Metal-Oxide-Semiconductor FET)**:
- Gate insulated from channel by oxide layer
- No gate current (very high impedance)
- Enhancement mode: Channel forms when gate voltage applied
- Depletion mode: Channel exists, gate voltage reduces it

**Advantage of MOSFETs**: Lower power, high input impedance, scalable to tiny sizes (billions on one chip)

## Silicon Purification and Processing

### Starting Material

**Metallurgical Grade Silicon** (98% pure):
1. Mine quartz (SiO₂) - sand
2. Reduce in electric arc furnace with carbon
   - SiO₂ + 2C → Si + 2CO
   - Temperature: 1,900°C
   - Power: Enormous (arc furnace needs hundreds of kW)

**Electronic Grade Silicon** (99.9999999% pure - "nine nines"):

**Siemens Process**:
1. React metallurgical silicon with HCl:
   - Si + 3HCl → SiHCl₃ (trichlorosilane) + H₂
2. Purify trichlorosilane by fractional distillation
   - Impurities have different boiling points
   - Repeat distillation many times
3. Reduce back to silicon:
   - SiHCl₃ + H₂ → Si + 3HCl (at 1,100°C)
   - Deposit on pure silicon rod
4. Result: Polycrystalline silicon (polysilicon)

**Difficulty**: Extreme. Each step requires precise control.

### Single Crystal Growth

**Czochralski Process** (CZ):
1. Melt polysilicon in quartz crucible (1,414°C)
2. Dip seed crystal into melt
3. Slowly pull up while rotating (1-100 mm/hour)
4. Silicon crystallizes onto seed in single crystal structure
5. Result: Cylindrical ingot (boule), 10-30 cm diameter, up to 2 meters long

**Float Zone Process** (FZ):
- Alternative method
- Higher purity possible
- More difficult

**Requirements**:
- Furnace with precise temperature control
- Inert atmosphere (argon) or vacuum
- Rotation mechanism
- Pulling mechanism
- Days of operation per boule

**Difficulty**: Very high, but achievable with precision equipment

### Wafer Preparation

1. **Slice boule** into wafers (0.5-1 mm thick)
   - Diamond saw
   - Loses ~50% to cutting (saw kerf)
2. **Lap wafers** (flatten and thin)
3. **Polish** to mirror finish
   - Chemical-mechanical polishing
   - Surface roughness <1 nanometer
4. **Clean** thoroughly
   - No particles, no contamination

## Transistor Manufacturing

### Planar Process (Standard Method)

**Steps** (Simplified):

1. **Oxidation**:
   - Heat wafer in oxygen (1,000°C)
   - SiO₂ layer grows on surface (0.1-1 µm thick)
   - Protects surface, acts as mask

2. **Photolithography**:
   - Coat with photoresist (light-sensitive polymer)
   - Expose through mask (pattern of opaque and transparent areas)
   - Develop: Removes exposed (or unexposed) resist
   - Result: Pattern defined on wafer

3. **Etching**:
   - Etch oxide where resist removed
   - Hydrofluoric acid (HF) etches SiO₂
   - Resist protects other areas
   - Strip resist after etching

4. **Doping** (Create P and N regions):

   **Diffusion Method**:
   - Heat wafer in atmosphere of dopant (900-1,200°C)
   - Dopant diffuses into silicon where oxide removed
   - Depth: 0.1-10 µm (controlled by time and temperature)
   - Oxide blocks diffusion in protected areas

   **Ion Implantation** (Better Control):
   - Accelerate dopant ions to high energy
   - Implant into silicon
   - Precise depth and concentration
   - Requires particle accelerator (expensive)

5. **Metallization**:
   - Deposit metal (aluminum or copper) on surface
   - Pattern with photolithography
   - Creates connections between transistors

6. **Repeat**: Multiple cycles of oxidation, patterning, doping, metallization
   - Build up layers
   - Create complex structures

**For One NPN Transistor**:
1. Start with P-type wafer (or N-type with P well diffused)
2. Diffuse N regions for collector and emitter
3. Diffuse P region for base (between collector and emitter)
4. Add contacts (metal to each region)
5. Isolate from other transistors

**Yield**: Even with good process, many transistors fail. Expect 50-90% yield after learning.

### Discrete Transistor Packaging

1. **Dice wafer**: Cut into individual chips
2. **Mount die**: Attach chip to header or lead frame
3. **Wire bond**: Connect chip to pins with tiny gold or aluminum wires
4. **Encapsulate**: Seal in plastic or metal can
5. **Test**: Verify operation and parameters

### Early Transistor Manufacturing (Easier)

**Germanium Transistors**:
- Ge easier to purify than Si (lower melting point)
- Used in first transistors (1940s-1960s)
- Lower performance than Si (lower bandgap, works poorly at high temp)
- Consider for first manufacturing attempts

**Grown Junction**:
- Pull crystal from melt
- Change dopant during growth (P, then N, then P)
- Creates PNP junctions in crystal
- Slice and package
- Crude but works

**Alloy Junction**:
- Start with N or P crystal
- Place dots of opposite-type material on surface
- Heat: Alloy dots diffuse into crystal, create junctions
- Simpler than planar process
- Lower performance

**Point Contact** (Simplest):
- Like cat's whisker diode but with two contacts
- Very unreliable, low performance
- Historical only

**Recommendation**: Start with germanium alloy junction transistors if attempting early manufacturing.

## Building Transistor Circuits

### Common Transistor Circuits

**Amplifier** (Common Emitter):
```
Vcc (+12V)
 |
Load Resistor (1k)
 |
Collector—NPN—Emitter
           |      |
Input—Base Resistor (10k)
           |      |
          GND   Resistor (100Ω)
                 |
                GND
```
- Voltage gain: 10-100
- Current gain: 20-200
- Use for audio, RF, sensors

**Switch**:
- Transistor fully on or fully off
- On: Base current applied, collector-emitter conducts
- Off: No base current, collector-emitter blocked
- Use for digital logic

**Oscillator**:
- LC tank or RC timing
- Positive feedback sustains oscillation
- Use for signal generation, clocks

**Voltage Regulator**:
- Sense output voltage
- Adjust transistor conduction to maintain constant voltage
- Or use dedicated IC (salvage 7805, LM317, etc.)

### Digital Logic with Transistors

**RTL (Resistor-Transistor Logic)**:
- Simplest digital logic family
- Resistors and transistors only
- Slow, power-hungry
- Good for learning

**DTL (Diode-Transistor Logic)**:
- Diodes for AND/OR, transistor for inversion
- Faster than RTL
- Still simple

**TTL (Transistor-Transistor Logic)**:
- Multiple transistors per gate
- Fast, robust
- Dominant logic family 1960s-1980s
- 7400 series ICs (salvage these!)

**CMOS (Complementary MOS)**:
- Uses both NMOS and PMOS transistors
- Extremely low power (only draws current when switching)
- Modern logic family
- Harder to manufacture (requires P and N channel MOSFETs)

**Building Gates**:

**NOT Gate** (Inverter):
- One transistor with load resistor
- Input high → Transistor on → Output low
- Input low → Transistor off → Output high

**NAND Gate**:
- Two transistors in series with load resistor
- Both inputs high → Both on → Output low
- Any input low → Output high
- Universal gate (can build all logic from NAND)

**NOR Gate**:
- Two transistors in parallel
- Any input high → Output low
- Both inputs low → Output high
- Also universal

## Integrated Circuits (ICs)

### From Discrete to Integrated

**Problem with Discrete Transistors**:
- Many parts to assemble
- Large size
- Reliability decreases with part count
- Expensive

**Solution**: Build multiple transistors on single chip

**Integrated Circuit**:
- Many transistors, resistors, capacitors on one die
- Manufactured simultaneously with planar process
- Interconnections built into chip
- Package as single component

### IC Manufacturing

**Same Process as Transistor**, but:
- Multiple transistors on one chip
- Resistors: Created from doped regions
- Capacitors: Metal plates with oxide dielectric
- Interconnections: Multiple metal layers

**Levels of Integration**:
- **SSI (Small Scale)**: 10-100 transistors (simple gates, flip-flops)
- **MSI (Medium Scale)**: 100-1,000 transistors (adders, counters, multiplexers)
- **LSI (Large Scale)**: 1,000-10,000 transistors (calculators, simple microprocessors)
- **VLSI (Very Large)**: 10,000-1,000,000 transistors (microprocessors, memory)
- **ULSI (Ultra Large)**: 1,000,000+ transistors (modern CPUs, GPUs)

**Difficulty Scaling**:
- SSI: Achievable with early semiconductor capability
- MSI: Requires process refinement
- LSI: Requires clean room, precise lithography
- VLSI/ULSI: Requires advanced lithography (photolithography, then electron beam, then EUV), extreme clean rooms

### Photolithography Challenges

**Resolution** (Smallest Feature Size):
- Limited by wavelength of light
- Visible light: ~400-700 nm → features ~1,000 nm (1 µm)
- UV light: ~200-400 nm → features ~500 nm
- Deep UV: ~190 nm → features ~200-300 nm
- Extreme UV (EUV): 13.5 nm → features ~7-50 nm (modern chips)

**Early ICs**: 10 µm features (visible light lithography)
**1990s**: 1 µm features (UV)
**2000s**: 100-500 nm (deep UV)
**2010s**: 10-30 nm (EUV, multi-patterning)
**2020s**: 3-7 nm (advanced EUV)

**Post-Collapse Path**:
- Start with 10-50 µm features (simple UV or visible light)
- Progress to 1-5 µm (refined UV)
- Many years before sub-micron

**Implication**: Early ICs will be large, simple, low transistor count.

### Designing ICs

**Layout**:
- Draw each layer (diffusion, oxide, metal)
- Specify dimensions and alignment
- Computer-aided design (CAD) helps but not essential

**Mask Making**:
- Photo mask: Glass with opaque pattern
- Early: Hand-drawn and photographically reduced
- Later: Computer-controlled (E-beam or laser writes pattern)

**Testing**:
- Probe wafer before dicing (weed out bad chips)
- Test packaged ICs
- Bin by performance (speed, power)

## Clean Room Design and Construction

### Why Clean Rooms Matter

**Particle Contamination**: The enemy of semiconductor manufacturing
- A single dust particle (>0.5 µm) can short a circuit or prevent proper etching
- Modern ICs have features <100 nm; even tiny particles are catastrophic
- Early transistors: More tolerant (10 µm features) but still need cleanliness

**Clean Room Classification**:
- **ISO Class**: Particles per cubic meter
- **Class 10,000** (ISO 7): 10,000 particles ≥0.5 µm per cubic foot
  - Adequate for early transistor work (10 µm features)
  - Achievable post-collapse
- **Class 1,000** (ISO 6): 1,000 particles per cubic foot
  - Better for refined processes
  - More difficult but achievable
- **Class 100** (ISO 5): Required for sub-micron work
  - Very difficult without modern HVAC
- **Class 10, Class 1** (ISO 4-3): Modern IC fabrication
  - Extremely difficult, likely not achievable for decades

### Building a Clean Room

**Location**:
- Inside existing building (easier to control environment)
- Away from dusty operations (grinding, sawing, etc.)
- Low external contamination area

**Construction**:

**1. Walls and Ceiling**:
- Smooth, non-shedding materials
- Sealed joints (no gaps for particles to enter)
- Materials:
  - Vinyl or epoxy-coated panels
  - Stainless steel (expensive but ideal)
  - Painted drywall (cheap but must be very smooth)

**2. Floor**:
- Epoxy coating (smooth, seamless)
- Or vinyl tile (sealed seams)
- Static-dissipative (prevent ESD damage to devices)
- Regular wet-mopping (don't sweep—raises dust)

**3. Air Filtration**:
- **HEPA Filters** (High-Efficiency Particulate Air):
  - Remove 99.97% of particles ≥0.3 µm
  - Expensive but salvageable
  - Or make from fine fiberglass mat (less efficient but usable)
- **Laminar Flow**: Air flows in one direction (ceiling to floor or wall to wall)
  - Sweeps particles away from work area
  - Requires powerful fans
- **Air Changes**: 10-30 per hour minimum (Class 10,000)
  - More for better class
- **Positive Pressure**: Higher pressure inside than outside
  - Prevents outside air (and particles) from entering

**4. Air Lock / Gowning Room**:
- Entry chamber between outside and clean room
- Change into clean room garments
- Air shower (blow off loose particles)

**5. Temperature and Humidity Control**:
- Temperature: 20-22°C (68-72°F) typical
  - Stability important (±1°C)
  - Affects photoresist, processes
- Humidity: 30-50% RH (Relative Humidity)
  - Too high: Water condensation, resist problems
  - Too low: Static electricity (ESD)

**Building Clean Room HVAC**:

**Components**:
- Blower/fan (salvage or build)
- HEPA filters (salvage from hospitals, labs, HVAC suppliers)
- Ducting
- Temperature control (cooling/heating)
- Humidity control (dehumidifier/humidifier)

**Airflow**:
- Draw outside air → Filter → Temperature/humidity condition → HEPA filter → Clean room
- Return air from clean room → Some recirculated, some exhausted
- Monitor pressure differential (manometer)

**Effort**: Moderate to difficult
- Small clean room (10 m²): Can build with salvaged HVAC and filters
- Large clean room (100 m²): Requires significant infrastructure

### Clean Room Protocols

**Gowning** (What to Wear):
- Full-body coveralls (Tyvek or similar, non-shedding)
- Hood/bouffant cap (cover hair)
- Shoe covers or dedicated clean room shoes
- Gloves (nitrile or vinyl)
- Face mask (prevent breath particles)
- Safety glasses (over regular glasses)

**Behavior**:
- No fast movements (stir up particles)
- No touching face, hair
- No food, drink, gum, tobacco
- No makeup, perfume, cologne (particles, contamination)
- No paper (sheds fibers)—use cleanroom-compatible notebooks
- Controlled movements, minimal talking

**Cleaning**:
- Wet-mop floors daily
- Wipe surfaces with cleanroom wipes and isopropyl alcohol
- Regular HEPA filter replacement
- Sticky mats at entry (capture particles from shoes)

**Monitoring**:
- Particle counter (measures particle concentration)
  - Expensive but critical for validating clean room class
  - Can build simple version with laser and photodetector
- Temperature and humidity sensors
- Pressure differential gauge

## Detailed Fabrication Process

### Oxidation (Thermal Oxide Growth)

**Purpose**: Grow SiO₂ layer on silicon wafer

**Dry Oxidation**:
- React silicon with oxygen gas
- Si + O₂ → SiO₂
- Temperature: 900-1,200°C
- Rate: Slow (good for thin, high-quality oxides)
- Thickness: 10-100 nm typical

**Wet Oxidation**:
- React silicon with water vapor
- Si + 2H₂O → SiO₂ + 2H₂
- Temperature: 900-1,000°C
- Rate: 3-10× faster than dry
- Thickness: 100-1,000 nm typical
- Quality: Slightly lower than dry (but adequate)

**Furnace**:
- Tube furnace (quartz tube in resistive heater)
- Temperature zones: Ramp up, constant temp, ramp down
- Atmosphere: O₂ (dry) or O₂ + H₂O (wet)
- Load wafers in quartz boat (rack)
- Process time: 10 minutes to several hours

**Building Oxidation Furnace**:
1. Quartz tube (salvage from lamps, lab equipment, or make from fused silica)
   - Diameter: 10-20 cm
   - Length: 50-100 cm
2. Heating elements:
   - Wire-wound resistive heaters (nichrome, kanthal)
   - Or silicon carbide elements
   - Wrap around tube
   - Multiple zones for temperature uniformity
3. Insulation: Ceramic fiber blanket
4. Temperature control:
   - Thermocouples measure temperature
   - PID controller adjusts heater power
   - Accuracy: ±5°C adequate for early work, ±1°C better
5. Gas flow control:
   - Flowmeters for O₂, N₂, H₂
   - Bubble water for H₂O vapor
6. Exhaust: Vent gases safely

**Effort**: Moderate. Can build with salvaged components and basic machining.

### Diffusion (Doping)

**Purpose**: Introduce dopant atoms into silicon

**Process**:
1. **Deposition**: Dopant source on wafer surface
   - Solid source: Wafers coated with dopant compound (boron nitride, phosphorus pentoxide)
   - Liquid source: Dopant in solution, spin coat
   - Gas source: Dopant gas flows over wafer (e.g., diborane B₂H₆ for boron, phosphine PH₃ for phosphorus)
     - **WARNING**: These gases are extremely toxic
2. **Drive-in**: Heat to 900-1,200°C
   - Dopant atoms diffuse into silicon
   - Depth and concentration depend on time and temperature
   - Fick's laws of diffusion govern process

**Diffusion Depth**:
- Junction depth: √(D × t)
- D: Diffusion coefficient (depends on dopant and temperature)
  - Phosphorus in Si at 1,000°C: D ≈ 10⁻¹³ cm²/s
  - Boron in Si at 1,000°C: D ≈ 2 × 10⁻¹³ cm²/s
- t: Time
- Example: 1 hour at 1,000°C → depth ≈ 0.6 µm

**Concentration Profile**:
- Gaussian or erfc (error function complement) depending on process
- Surface concentration highest, decreases with depth
- Need ~10¹⁸ atoms/cm³ for good conductivity

**Diffusion Furnace**:
- Similar to oxidation furnace
- Gas handling for dopant sources
- Separate furnace for N-type and P-type (avoid cross-contamination)

**Safety**:
- Dopant gases (diborane, phosphine, arsine) are deadly
- Proper scrubbing of exhaust
- Leak detection
- Training essential

**Alternative: Spin-On Dopants**:
- Liquid dopant solutions
- Spin coat onto wafer
- Bake and drive-in
- Safer than gas sources
- Less precise but adequate for early work

### Ion Implantation (Advanced Doping)

**Principle**: Accelerate dopant ions, shoot into silicon
- Ions penetrate surface, lodge in crystal
- Depth controlled by energy (keV to MeV)
- Concentration controlled by dose (ions/cm²)

**Advantages Over Diffusion**:
- Precise depth and concentration
- Low temperature (no diffusion)
- Any dopant
- Pattern by masking (no oxide needed)

**Disadvantages**:
- Requires particle accelerator (expensive, complex)
- Crystal damage (needs annealing to repair)

**Ion Implanter Components**:
1. **Ion source**: Generate dopant ions (plasma)
2. **Mass separator**: Select specific isotope (magnetic field)
3. **Accelerator**: High voltage accelerates ions
4. **Beam steering**: Direct ions to target
5. **End station**: Wafer holder in vacuum chamber
6. **Vacuum system**: Prevent ion collisions

**Building Ion Implanter**:
- Very difficult
- Requires high vacuum (10⁻⁶ torr)
- High voltage (10-200 kV)
- Precise beam control
- Not recommended for early post-collapse (decades until capability)

**Recommendation**: Use diffusion for early transistor work. Attempt ion implantation only after mature semiconductor capability.

### Metallization

**Purpose**: Create electrical connections

**Materials**:
- **Aluminum**: Traditional (easy to deposit and pattern)
  - Evaporation or sputtering
  - Good conductivity
  - Can form ohmic contacts to silicon
  - Disadvantage: Electromigration at high current
- **Copper**: Modern (lower resistance)
  - Must use barrier layer (TaN, TiN) to prevent diffusion into silicon
  - Harder to pattern (can't dry etch easily)
- **Gold**: High conductivity, doesn't oxidize
  - Expensive
  - Wire bonding

**Deposition Methods**:

**Evaporation**:
1. Heat metal in vacuum until it vaporizes
2. Metal atoms travel in straight lines, coat wafer
3. Methods:
   - Resistive heating: Pass current through wire or boat holding metal
   - E-beam: Electron beam melts metal
4. Vacuum: 10⁻⁶ torr
5. Rate: 0.1-10 nm/s
6. Uniformity: Moderate (center thicker than edges)

**Building Evaporator**:
- Vacuum chamber (stainless steel, salvage from industrial equipment)
- Pump system (roughing pump + diffusion or turbomolecular pump)
- Heating source (resistive or electron gun)
- Substrate holder (holds wafers)
- Thickness monitor (quartz crystal microbalance)

**Effort**: Moderate to difficult. Achieving good vacuum is challenging.

**Sputtering** (Better Uniformity):
1. Plasma knocks atoms off metal target
2. Atoms deposit on wafer
3. Better step coverage and uniformity than evaporation
4. Requires RF or DC power supply

**Patterning Metal** (Lift-off or Etching):

**Lift-off**:
1. Pattern photoresist before metallization
2. Deposit metal over resist and exposed areas
3. Dissolve resist (takes metal on top with it)
4. Result: Metal only where resist was open

**Etching**:
1. Deposit metal over entire wafer
2. Pattern photoresist on metal
3. Etch metal where resist removed
4. Strip resist
5. Result: Metal pattern

**Metal Etchants**:
- Aluminum: Phosphoric acid + nitric acid + acetic acid (wet etch)
  - Or reactive ion etching (dry, requires plasma)
- Copper: Ferric chloride, ammonium persulfate (wet)

### Passivation

**Purpose**: Protect finished device from environment

**Material**: Silicon dioxide or silicon nitride

**Process**:
- Deposit oxide by CVD (Chemical Vapor Deposition)
- Or grow thermal oxide (if compatible with process)
- Pattern to open contact pads

**CVD** (Chemical Vapor Deposition):
- React gases at wafer surface to deposit film
- Example (SiO₂): SiH₄ + O₂ → SiO₂ + 2H₂ (at 400-450°C)
- Lower temperature than thermal oxide
- Can deposit on metal (thermal growth can't)

## Transistor Characterization and Testing

### DC Characteristics

**NPN Transistor Test Circuit**:
```
Vcc (adjustable 0-15V)
  |
Resistor (1k, current limiting)
  |
Collector → NPN
  |
Base ← Variable voltage source (0-2V)
  |
Emitter → Ground

Measure:
- Ib (base current)
- Ic (collector current)
- Vce (collector-emitter voltage)
```

**Tests**:

**1. Current Gain (β or hFE)**:
- β = Ic / Ib
- Typical: 50-500 for small signal transistors
- Measure at several values of Ic (varies with current)

**2. Collector Characteristic Curves**:
- Plot Ic vs. Vce for different Ib values
- Shows saturation region (fully on), active region (amplification), cutoff (off)

**3. Breakdown Voltages**:
- **BVCEO**: Collector-emitter breakdown (base open)
  - Increase Vce until Ic rises sharply
  - Typical: 20-80V for low-power transistors
- **BVCBO**: Collector-base breakdown (emitter open)
  - Higher than BVCEO
- Don't exceed breakdown (destroys transistor)

**4. Leakage Current**:
- **ICBO**: Collector-base leakage (emitter open, junction reverse-biased)
- **ICEO**: Collector-emitter leakage (base open)
- Should be <1 µA for good transistor
- Higher at elevated temperature

### AC Characteristics

**Frequency Response**:
- **fT (Transition Frequency)**: Frequency where current gain drops to 1
  - Typical: 100-500 MHz for general purpose, 1-10 GHz for RF transistors
- Measure: Small signal AC test with network analyzer

**Capacitances**:
- **Cbe**: Base-emitter capacitance
- **Cbc**: Base-collector capacitance (Miller capacitance)
- Limit high-frequency performance

### Thermal Characteristics

**Power Dissipation**:
- Power = Vce × Ic
- Heats transistor
- Max power limited by junction temperature (typically 150-175°C max)

**Thermal Resistance**:
- θJA: Junction to ambient
  - TO-92 package (plastic): ~200°C/W
  - TO-220 (with heat sink): ~5-50°C/W
- Temperature rise: ΔT = Power × θJA

**Heat Sinking**:
- Attach transistor to metal (aluminum, copper)
- Increases surface area for cooling
- Thermal compound improves contact

## Practical Transistor Projects

### Project 1: Simple Radio

**One-Transistor Radio** (Simplest):

**Circuit**:
```
Antenna → Tuning coil/capacitor (LC tank) → Detector diode → Audio transformer
                                                  ↓
                                            Transistor amplifier → Speaker
```

**Transistor Stage**:
- Single NPN (2N2222 or similar)
- Common emitter amplifier
- Biased for Class A (linear amplification)
- Gain: ~50

**Components**:
- 1 NPN transistor
- 4-5 resistors (biasing and stability)
- 2-3 capacitors (coupling and bypass)
- 1 transformer (interstage or output)
- 1 speaker (salvage from any audio device)
- Battery (9V or 6V)

**Learning**:
- Transistor biasing
- AC coupling
- Impedance matching

**Performance**: Can receive local AM stations, modest volume

**Two-Transistor Radio** (Better):
- First stage: RF amplification
- Second stage: Audio amplification
- Louder, more selective

**Superheterodyne Receiver** (Advanced):
- 6-8 transistors
- Better performance (see Chapter 6 for details)

### Project 2: Audio Amplifier

**Single-Transistor Amplifier**:

**Circuit** (Common Emitter):
```
Input (from microphone or audio source)
  ↓
Coupling capacitor (10µF) → Base resistor divider (bias)
                                ↓
                            NPN transistor
                                ↓
                          Emitter resistor (stability)
                                ↓
                              Ground

Collector → Load resistor → Vcc
         ↓
    Coupling capacitor → Output (to speaker or next stage)
```

**Design**:
- Bias point: Vce ≈ Vcc/2, Ic = 1-10 mA
- Voltage gain: ≈ Rc / Re (without bypass capacitor)
  - Add bypass capacitor across Re for higher AC gain
- Power: Milliwatts (not enough for speaker, need amplifier chain)

**Multi-Transistor Amplifier** (Practical):
- Pre-amplifier: 1-2 stages (voltage gain)
- Driver: 1-2 stages (current gain)
- Output stage: Push-pull (Class B or AB)
  - Two transistors (NPN and PNP) conduct alternate half-cycles
  - More efficient than Class A
  - Can drive speaker directly

**Power Output**:
- 1W: 2-4 transistors
- 10W: 4-8 transistors
- 100W: 8-12 transistors (or power transistors)

**Heat Management**:
- Output transistors dissipate significant power
- Heat sinks essential
- Thermal shutdown protection (for high power)

### Project 3: Digital Logic

**RTL NOR Gate** (Simplest Logic):

**Circuit**:
```
Vcc (+5V)
  |
Resistor (470Ω, pull-up)
  |
  +------ Output
  |
  ├── NPN transistor 1 (Input A)
  ├── NPN transistor 2 (Input B)
  |
Ground
```

**Operation**:
- If either input high: Corresponding transistor conducts, output pulled to ground (low)
- If both inputs low: Both transistors off, resistor pulls output high
- Truth table: NOR (output = NOT(A OR B))

**Power Consumption**: High (resistor always conducting when output low)

**Building Logic Family**:
- Design NOR gates (or NAND)
- Standardize: Voltage levels (0V = low, 5V = high), current drive, fanout
- Build gates, flip-flops, counters, registers
- Create discrete logic computer

**TTL NAND Gate** (More Complex, Better Performance):
- Multiple transistors
- Active pull-up (totem pole output)
- Lower power, faster
- More difficult to build

**CMOS Logic** (Lowest Power):
- Complementary NMOS and PMOS transistors
- Virtually zero static power (only dynamic power when switching)
- Requires ability to make both N and P channel MOSFETs

### Project 4: Small Calculator

**Design**: 4-bit binary adder/subtractor

**Components**:
- **Full Adders**: 4× (each: ~8 gates = 16-32 transistors)
- **Input Switches**: 8 (two 4-bit numbers)
- **Mode Switch**: Add/subtract
- **Display**: 5 LEDs or 7-segment display
- **Total Transistors**: 100-200

**Circuit**:
1. Input A (4 bits) and Input B (4 bits) from switches
2. If subtract mode: Invert B (XOR with mode bit) and set carry-in to 1 (two's complement)
3. Feed to 4-bit ripple-carry adder
4. Output to display

**Learning**:
- Binary arithmetic
- Combinational logic
- Building from transistors

**Expansion**:
- Add multiplication (repeated addition with shift)
- Add division (repeated subtraction)
- Add memory (registers to store results)

### Project 5: Transistor Tester

**Purpose**: Characterize transistors (measure β, leakage, breakdown)

**Circuit**:
- Adjustable voltage sources (base, collector)
- Current measurement (ammeters or resistor + voltmeter)
- Switching to test different configurations

**Measurements**:
- β (hFE) at specified Ic
- ICEO, ICBO (leakage)
- BVCEO (breakdown)

**Display**: Analog meters or digital (with ADC)

**Usefulness**: Essential for salvaging unknown transistors or verifying manufactured ones

## Yield Analysis and Process Control

### Defects and Yield

**Yield** (Y): Percentage of functioning devices

**Defect Density** (D): Defects per unit area (defects/cm²)

**Yield Models**:

**Poisson Model** (for random defects):
```
Y = e^(-D × A)

Y: Yield (0-1)
D: Defect density (defects/cm²)
A: Chip area (cm²)
e: 2.718...
```

**Example**:
- Defect density: 1 defect/cm²
- Chip area: 1 cm²
- Yield: e^(-1 × 1) = 0.37 (37%)

**Implication**: Larger chips have lower yield

**Improving Yield**:
1. **Reduce defect density**:
   - Better clean room (fewer particles)
   - Better process control (fewer process-induced defects)
   - Better materials (purer chemicals, cleaner gases)
2. **Redundancy**: Build extra circuits, disable defective ones (for memory)
3. **Design for manufacturability**: Avoid tight tolerances

**Typical Yields**:
- Early learning: 10-30%
- Mature process: 70-95%
- Advanced processes (cutting edge): 50-70% (lower due to complexity)

### Process Monitoring

**Test Structures**:
- Include test patterns on wafer (alongside real circuits)
- Measure electrical properties
- Verify process parameters

**Examples**:
- **Resistor test structures**: Measure sheet resistance (Ω/square)
  - Verify doping concentration
- **Capacitor test structures**: Measure oxide thickness and quality
  - Capacitance ∝ Area / Thickness
- **Transistor test structures**: Measure threshold voltage, current gain, etc.
- **Van der Pauw structures**: Measure resistivity precisely

**Statistical Process Control** (SPC):
- Track measurements over time
- Plot on control charts
- Detect trends or shifts (process going out of spec)
- Take corrective action before yield drops

**Critical Parameters**:
- Oxide thickness
- Sheet resistance (doping)
- Line width (photolithography)
- Particle counts (clean room)
- Etch rates
- Deposition rates

**Feedback Loop**:
- Measure → Compare to target → Adjust process → Measure again

### Failure Analysis

**When Devices Fail**:
1. **Electrical test**: Identify failure mode
   - Short? Open? Wrong gain?
2. **Visual inspection**: Microscope examination
   - Cracks, particles, pattern defects?
3. **Cross-sectioning**: Cut device, examine layers
   - Verify layer thicknesses, doping profiles
   - Destructive but informative
4. **Root cause analysis**: Why did it fail?
   - Process error? Material defect? Design flaw?
5. **Corrective action**: Fix process or design
6. **Verify**: Build new devices, test

**Tools**:
- Optical microscope (100-1000× magnification)
- SEM (Scanning Electron Microscope) if available (salvage from universities)
  - High magnification, better than optical
- Profilometer (measure step heights, surface roughness)

## Transition to ICs

**When to Attempt ICs**:
- Discrete transistor manufacturing reliable (>70% yield)
- Clean room capability (Class 1,000 or better)
- Photolithography equipment (contact printer or projection aligner)
- Testing capability (probers, testers)
- Design tools (even paper and pencil can work for simple ICs)
- Likely 30-50 years post-collapse

**First ICs**:
- Simple gates (NAND, NOR)
- Flip-flops
- Small counters and shift registers
- 10-100 transistors per chip
- Large features (10-20 µm)
- Low yield acceptable (50%) for learning

**Progression**:
- SSI (10-100 transistors) → MSI (100-1,000) → LSI (1,000-10,000) → VLSI (10,000+)
- Each step requires:
  - Better lithography (finer features)
  - Cleaner process (fewer defects)
  - More layers (more interconnect)
  - Better design tools (can't design 10,000 transistors by hand)

**Timeline**:
- SSI: Years 30-40
- MSI: Years 40-50
- LSI: Years 50-70
- VLSI: Years 70-100+

## Summary: Semiconductor Development Stages

**Stage 1 (Year 10-25): Germanium Transistors**
- Purify germanium (easier than silicon)
- Grown or alloy junction (simpler than planar)
- Low performance, unreliable
- Prove manufacturing capability
- Use in radios, simple circuits

**Stage 2 (Year 25-35): Silicon Transistors**
- Silicon purification (Siemens process)
- Planar process development
- Discrete BJTs and JFETs
- Replace tubes in most applications
- Higher performance, more reliable

**Stage 3 (Year 35-50): Simple ICs**
- SSI and MSI integration
- Logic gates, flip-flops, counters
- Simple microprocessors (4-bit, 8-bit)
- 10 µm process
- Clean room Class 1,000

**Stage 4 (Year 50-75): Advanced ICs**
- LSI and early VLSI
- 16-bit and 32-bit processors
- Megabytes of memory
- 1-5 µm process
- Clean room Class 100

**Stage 5 (Year 75-100+): Modern ICs**
- VLSI and ULSI
- Complex processors, GPUs
- Gigabytes of memory
- Sub-micron process (0.1-1 µm)
- Clean room Class 10 or better

## Safety

**Chemical Hazards**:
- **HF (Hydrofluoric Acid)**: Extremely dangerous
  - Penetrates skin, attacks bones and calcium
  - Proper protection essential (HF-specific gloves, not standard nitrile)
  - Calcium gluconate gel antidote (keep on hand)
  - Ventilation and training mandatory
- **Photoresist Solvents**: Flammable, toxic
  - Acetone, xylene, etc.
  - Fire risk, inhalation hazard
  - Proper storage, handling, ventilation
- **Dopant Gases** (Arsine AsH₃, Phosphine PH₃, Diborane B₂H₆): Deadly
  - Parts-per-million concentrations lethal
  - Gas monitors essential
  - Scrubbers on exhaust
  - Extensive training required
  - Consider alternatives (spin-on dopants, solid sources) if possible

**High Temperature**:
- Furnaces at 1,000-1,400°C
  - Severe burn risk
  - Protective equipment (heat-resistant gloves, face shield)
  - Training on loading/unloading
- Molten silicon: 1,414°C
  - Spatters cause severe burns
  - Containment and safety procedures

**Electrical Hazards**:
- High voltage equipment (ion implanter, e-beam evaporator)
  - Lethal voltages (10-200 kV)
  - Interlocks and grounding essential
  - Lockout/tagout procedures

**Particle Hazards**:
- Silicon dust from sawing/grinding
  - Causes silicosis (lung disease)
  - Respirator protection
  - Wet sawing preferred (reduces airborne dust)

**Radiation**:
- X-rays from high-voltage equipment (ion implanter, e-beam)
  - Shielding (lead)
  - Dosimetry (monitor exposure)
  - Distance and time limits

**Emergency Procedures**:
- Eyewash and safety shower (for chemical splashes)
- Fire suppression (appropriate for chemical fires)
- First aid training (HF burns, chemical exposure)
- Emergency contacts and procedures posted

## Next Steps

With transistor and IC capability:
- Build modern computers (Chapter 9)
- Create complex logic systems
- Develop microprocessors (Chapter 10)
- Enable digital communications (Chapter 12)
- Foundation for all advanced technology

**Key Principle**: Semiconductors are the hardest technology in this book. Don't rush. Use tubes and salvaged transistors for decades while developing manufacturing capability. When you can make transistors reliably, modern computing becomes possible.

**Patience**: The path from first transistor to integrated circuits took the original semiconductor industry 15-20 years (1947 to mid-1960s). Post-collapse, expect similar or longer timelines. But the knowledge exists. Follow the path, document failures, train the next generation, and eventually you'll have the capability to manufacture the components that enable modern computing.

## Transition to ICs

**When to Attempt ICs**:
- Discrete transistor manufacturing reliable
- Clean room capability
- Photolithography equipment
- Likely 30-50 years post-collapse

**First ICs**:
- Simple gates (NAND, NOR)
- Flip-flops
- Small counters and shift registers
- 10-100 transistors per chip

**Progression**:
- SSI → MSI → LSI over decades
- Each step requires better resolution, cleaner processes

## Summary: Semiconductor Development Stages

**Stage 1 (Year 10-25): Germanium Transistors**
- Purify germanium
- Grown or alloy junction
- Low performance, unreliable
- Prove manufacturing capability

**Stage 2 (Year 25-35): Silicon Transistors**
- Silicon purification
- Planar process development
- Discrete BJTs and JFETs
- Replace tubes in most applications

**Stage 3 (Year 35-50): Simple ICs**
- SSI and MSI integration
- Logic gates, flip-flops, counters
- Simple microprocessors (4-bit, 8-bit)
- 10 µm process

**Stage 4 (Year 50-75): Advanced ICs**
- LSI and early VLSI
- 16-bit and 32-bit processors
- Megabytes of memory
- 1-5 µm process

**Stage 5 (Year 75-100+): Modern ICs**
- VLSI and ULSI
- Complex processors, GPUs
- Gigabytes of memory
- Sub-micron process

## Safety

**Chemical Hazards**:
- HF (hydrofluoric acid): Extremely dangerous, attacks bones
- Photoresist solvents: Toxic, flammable
- Dopant gases (arsine, phosphine): Deadly
- Use extreme caution, proper ventilation, protection

**High Temperature**:
- Furnaces at 1,000-1,400°C
- Molten silicon burns
- Proper insulation and handling

**Particle Hazards**:
- Silicon dust from sawing
- Wear respirator

## Next Steps

With transistor and IC capability:
- Build modern computers (Chapter 9)
- Create complex logic systems
- Develop microprocessors (Chapter 10)
- Enable digital communications (Chapter 12)
- Foundation for all advanced technology

**Key Principle**: Semiconductors are the hardest technology in this book. Don't rush. Use tubes and salvaged transistors for decades while developing manufacturing capability. When you can make transistors reliably, modern computing becomes possible.
