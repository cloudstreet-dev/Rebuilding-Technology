# Chapter 6: Telegraph and Radio Communication

## Why Communication Matters

A scattered, isolated post-collapse civilization will rebuild slowly. Communication enables:
- **Coordination**: Organize trade, resources, knowledge
- **Safety**: Warn of dangers, coordinate rescue
- **Knowledge sharing**: Prevent duplication of effort, share discoveries
- **Social cohesion**: Maintain connection between communities

Communication technology progresses in stages:
1. **Physical**: Messengers, letters (slow but requires no technology)
2. **Visual**: Flags, smoke signals, heliograph (line-of-sight only)
3. **Telegraph**: Wired electrical signals (requires wire infrastructure)
4. **Radio**: Wireless electromagnetic waves (freedom from wires!)
5. **Digital**: Computer networks, internet (covered in later chapters)

This chapter focuses on telegraph (simplest electrical communication) and radio (most useful early wireless technology).

**Chapter Dependencies and Cross-References:**

This chapter enables critical communication capabilities. For complete implementation, reference:

**Prerequisites (Read First):**
- **Chapter 3: Electricity** — Power generation, batteries, DC/AC principles, power supplies
- **Chapter 5: Basic Electronics Components** — Resistors, capacitors, inductors, transformers, diodes
- **Chapter 2: Metalworking** — Wire production (copper drawing), antenna construction, chassis fabrication
- **Chapter 7: Vacuum Tubes** — Tube-based amplifier and oscillator designs (historical approach)
- **Chapter 8: Semiconductors** — Transistor-based designs (modern approach if achievable)

**Applications Enabled (Read After):**
- **Chapter 9+: Computers** — Digital communication, networks, internet protocols
- **Chapter 3.3: Timekeeping** — Broadcast time signals for synchronization
- **Chapter 3.4: Navigation** — Radio direction finding, beacon navigation
- **Trade coordination** — Market information, pricing, supply/demand
- **Emergency response** — Warnings, rescue coordination, disaster management
- **Weather reporting** — Agricultural planning, storm warnings

**Related Techniques:**
- **Chapter 5.5: Optics** — Heliograph (visual line-of-sight communication alternative)
- **Chapter 4: Chemistry** — Battery construction for power supplies

**Why This Chapter is Critical:**

**Wire requirements constrain expansion**. Telegraph systems consumed enormous quantities of copper wire historically. Post-collapse wire salvage and later copper production directly limit communication network growth. A single long-distance telegraph line may require tons of copper—this is not a trivial material requirement.

Communication enables coordination. Isolated communities rebuild slowly. Connected communities share knowledge, warn of dangers, coordinate trade, and maintain social cohesion. The difference between isolated subsistence and coordinated rebuilding is communication technology.

## Telegraph Systems

### Simple Telegraph (On/Off Signaling)

**Principle**: Complete or break electrical circuit to send pulses

**Basic Components**:
1. **Power source**: Battery (12V adequate)
2. **Key**: Switch to make and break circuit
3. **Wire**: Connects stations (can be very long)
4. **Sounder**: Electromagnetic device that clicks when current flows
5. **Ground return**: Earth can be one conductor (saves wire)

**Construction**:

**Telegraph Key** (Transmitter):
1. **Lever**: Metal arm, pivots in middle
2. **Contacts**: Metal pieces that touch when lever pressed
3. **Spring**: Returns lever to open position
4. **Base**: Insulated mounting

**Telegraph Sounder** (Receiver):
1. **Electromagnet**: Coil around iron core
2. **Armature**: Iron piece attracted when electromagnet energized
3. **Clapper**: Attached to armature, strikes sounding plate
4. **Spring**: Returns armature when current stops
5. **Result**: Click when circuit closed, clack when opened

**Circuit**:
```
Battery(+) → Key → Wire (miles) → Sounder → Wire/Ground → Battery(-)
```

**Operation**:
1. Press key: Current flows, sounder clicks
2. Release key: Current stops, sounder clacks
3. Pattern of clicks: Encoded message (Morse code)

**Morse Code**:
- Letters, numbers, and punctuation encoded as dots and dashes
- Dot: Short press
- Dash: Long press (3× dot length)
- Space between symbols: 1 dot length
- Space between letters: 3 dot lengths
- Space between words: 7 dot lengths

**Common Letters**:
- A: ·−
- B: −···
- C: −·−·
- D: −··
- E: ·
- S: ···
- O: −−−
- T: −

**SOS Distress Signal**: ··· −−− ··· (easy to recognize)

**Range**: Depends heavily on wire gauge, sounder sensitivity, and voltage

**Practical ranges:**
- **12V battery, heavy wire (AWG 10-12)**: 20-50 km
- **12V battery, thin wire (AWG 18-20)**: 5-15 km (resistance limits current)
- **Higher voltage (50-100V)**: 100-200 km possible
- **Historical systems**: Used 100V+ for long distances

**Wire gauge matters**:
- Thicker wire = lower resistance = longer range
- AWG 10 (2.6mm): ~3.3 Ω/km
- AWG 18 (1.0mm): ~21 Ω/km (6× more resistance!)
- For 50km line: AWG 10 = 165Ω total, AWG 18 = 1050Ω total

**Repeater Stations Enable Unlimited Range**:

This is the KEY concept: Each relay regenerates the signal.

**How repeaters work**:
1. **Incoming weak signal** activates sensitive relay
2. **Relay closes** local circuit with fresh battery
3. **Strong signal sent** to next station
4. **Repeat** at each station

**Result**: Signal never degrades beyond one hop. With repeaters every 50-100km, you can span continents.

**Historical example**: 1861 transcontinental telegraph (USA) used dozens of repeater stations across 3,000+ km. Each station had operator who manually re-keyed messages, or automatic relays that electronically repeated signals.

**Post-collapse strategy**:
- Start with local links (20-50km, no repeaters)
- Add repeater stations as network grows
- Solar-powered repeaters on hilltops (unattended operation)
- Eventually: Hundreds of stations = continent-wide network

### Printing Telegraph

**Improvement**: Automatically prints message instead of audio clicks

**Type 1: Morse Register**:
- Pen attached to sounder armature
- Paper tape pulled under pen
- Marks on paper show dots and dashes
- Operator reads tape

**Type 2: Multiplex Telegraph**:
- Multiple messages on same wire (time-division or frequency-division)
- More complex

**Type 3: Teletype**:
- Keyboard input
- Encoded as pulses (Baudot code, later ASCII)
- Prints letters directly
- Covered in Chapter 11 (requires more electronics)

### Telephone (Voice Telegraph)

**Principle**: Varying electrical signal represents sound waves

**Basic Components**:

**Carbon Microphone** (Transmitter, Simple to Build):
1. **Diaphragm**: Thin metal or mica disc
2. **Carbon granules**: Loosely packed between contacts
3. **Sound waves hit diaphragm**: Compresses carbon
4. **Compression changes resistance**: Current varies with sound
5. **Result**: Electrical signal mimics sound

**Construction**:
- Container with carbon granules
- Metal diaphragm on one side
- Electrodes in contact with carbon
- Sound waves vibrate diaphragm, modulating carbon resistance

**Electromagnetic Speaker** (Receiver):
1. **Permanent magnet** with coil
2. **Varying current in coil**: Creates varying magnetic field
3. **Field attracts/repels diaphragm**: Creates sound waves
4. **Result**: Sound reproduces electrical signal

**Simple Telephone Circuit**:
```
Battery → Microphone → Line → Speaker → Ground return
```

**Improvements**:
- **Amplification**: Needed for long distances (vacuum tube or transistor amplifiers)
- **Switchboard**: Operators manually connect calls
- **Automated switching**: Relays or electronic switches route calls (complex)

**Range**: 10-20 km without amplification, unlimited with repeater amplifiers

## Radio Fundamentals

### Electromagnetic Waves

**Discovery**: Moving electric current creates electromagnetic waves that propagate through space at speed of light

**Frequency and Wavelength**:
```
Speed of light = Frequency × Wavelength
c = f × λ

c = 300,000,000 meters/second
f in Hertz (Hz, cycles per second)
λ in meters

Example: 1 MHz (1,000,000 Hz) frequency
λ = 300,000,000 / 1,000,000 = 300 meters
```

**Radio Spectrum**:
- **VLF (Very Low Frequency)**: 3-30 kHz, wavelength 100-10 km
  - Long range, penetrates water, large antennas
- **LF (Low Frequency)**: 30-300 kHz, 10-1 km
  - Long range, AM broadcasting (Europe)
- **MF (Medium Frequency)**: 300-3,000 kHz, 1 km-100 m
  - AM broadcasting (Americas), good day and night range
- **HF (High Frequency)**: 3-30 MHz, 100-10 m
  - Shortwave, reflects off ionosphere, worldwide range
- **VHF (Very High Frequency)**: 30-300 MHz, 10-1 m
  - FM broadcasting, TV, line-of-sight communication
- **UHF (Ultra High Frequency)**: 300-3,000 MHz, 1 m-10 cm
  - TV, cell phones, satellite, line-of-sight

**Antenna Basics**:
- Efficient antenna length ≈ λ/4 or λ/2
- Example: 1 MHz → 300m wavelength → 75m antenna (λ/4)
- Example: 100 MHz → 3m wavelength → 0.75m antenna

**Implication**: Lower frequencies need huge antennas but travel farther. Higher frequencies need small antennas but limited to line-of-sight.

### Spark Gap Transmitter (Simplest Radio)

**Warning**: Illegal in most pre-collapse jurisdictions due to interference. Post-collapse, regulatory concerns are moot, but be aware this creates broad, noisy signals.

**Principle**: Electric spark creates burst of electromagnetic waves across wide frequency range

**Construction**:
1. **Power source**: High voltage (1,000-10,000V)
   - Car ignition coil with 12V battery
   - Or transformer stepping up AC mains
2. **Capacitor**: Stores charge
3. **Spark gap**: Two electrodes with small air gap
4. **Inductor**: Coil of wire
5. **Antenna**: Wire, length ≈ λ/4 of desired frequency

**Circuit**:
```
HV source → Capacitor → Spark gap → Inductor → Antenna
                                        |
                                      Ground
```

**Operation**:
1. Capacitor charges from HV source
2. Voltage reaches breakdown point of air gap
3. Spark jumps gap, capacitor discharges through inductor
4. Inductor and antenna radiate electromagnetic pulse
5. Repeat at ~50-500 times per second

**Modulation**: Key the HV source on and off (Morse code)

**Reception**: Any radio receiver nearby will hear loud clicks

**Disadvantages**:
- Inefficient
- Broad, noisy signal (interferes with everything)
- Short range (few km without huge power)

**Historical Significance**: First wireless telegraphy (Marconi, 1890s)

**Recommendation**: Only use if nothing better available. Good for emergency signaling.

### Crystal Radio Receiver (No Power Required!)

**Principle**: Radio waves induce current in antenna, detector extracts audio

**Components**:
1. **Antenna**: Long wire, 10-30 meters
2. **Ground**: Earth connection (metal rod driven into soil, or water pipe)
3. **Tuning coil**: Inductor, 100-300 turns of wire
4. **Variable capacitor**: For tuning frequency
5. **Detector**: Crystal diode (galena crystal or salvaged diode)
6. **Headphones**: High-impedance (2,000+ ohms)

**Circuit**:
```
Antenna → Tuning coil ← Variable capacitor → Diode → Headphones → Ground
```

**Operation**:
1. **Antenna captures radio waves**: Induces tiny AC voltage
2. **LC tuned circuit**: Resonates at specific frequency (station you want to hear)
   - Resonant frequency: f = 1 / (2π√(L×C))
   - Adjust capacitor to change frequency
3. **Diode rectifies**: Removes one half of AC wave (demodulation)
4. **Headphones respond**: To audio component of signal

**No battery needed!** Energy comes from radio waves themselves (very weak).

**Building**:

**1. RF Coil Construction (Detailed)**:

**Coil winding for radio frequency** requires attention to Q factor (quality factor) and parasitic capacitance.

**Q Factor** (Quality Factor):
- Measures coil efficiency: Q = X_L / R (reactance / resistance)
- **High Q** (>100): Sharp tuning, good selectivity, less loss
- **Low Q** (<50): Broad tuning, poor selectivity, lossy
- **Goal**: Maximize Q for best receiver performance

**Winding methods**:

**Close-Wound Coils**:
- **Method**: Turns touching, side-by-side
- **Advantages**: Maximum inductance for size, simple to wind
- **Disadvantages**: Higher inter-turn capacitance (lowers resonant frequency, reduces Q at high frequencies)
- **Best for**: Low frequencies (<1 MHz), physical small size needed

**Spaced-Wound Coils** (Better for RF):
- **Method**: Small gap between turns (wire diameter spacing)
- **Advantages**: Reduced inter-turn capacitance, higher Q, more stable
- **Disadvantages**: Longer coil, more difficult to wind
- **Best for**: High frequencies (>1 MHz), highest performance
- **Spacing**: 1× wire diameter typical (e.g., 1mm wire = 1mm spacing)

**Coil Forms**:
- **Air core**: Best for RF (no losses), coil self-supporting or on non-metallic form
  - Cardboard tube, PVC pipe, ceramic, wood (treated)
  - **Avoid**: Metal (eddy current losses)
- **Ferrite core**: Increases inductance (10-100×), allows smaller coils
  - **Powdered iron** or **ferrite rod** (salvage from AM radio antenna)
  - **Advantage**: Much smaller coil for same inductance
  - **Disadvantage**: Core losses at high frequencies, saturation at high power

**Practical Crystal Radio Coil**:
- **Wire**: 26-30 AWG enameled copper (magnet wire)
- **Form**: 5-10 cm diameter tube (cardboard, PVC)
- **Turns**: 100-200 for AM broadcast band (500-1600 kHz)
  - More turns = lower frequency
  - Fewer turns = higher frequency
- **Winding**: Close-wound acceptable for simplicity
- **Taps**: Add taps every 20-50 turns for coarse tuning
  - Strip insulation, solder wire lead, continue winding
  - Allows switching coil sections in/out

**Tap Positions for Impedance Matching**:

**Why taps matter**: Different tap points provide different impedances for antenna coupling

**Example coil** (200 turns total):
- **Tap at turn 50**: Low impedance, tight coupling (strong signal, less selective)
- **Tap at turn 100**: Medium impedance
- **Tap at turn 150**: High impedance, loose coupling (weaker signal, more selective)
- **All turns (200)**: Maximum inductance, highest impedance

**Connection**:
- Antenna connects to tap
- Ground connects to bottom of coil
- Variable capacitor connects across entire coil (or portion)
- Diode connects across tuned section

**Tuning Range** (practical):
- **100-200 turns, 5-10 cm diameter, variable capacitor**: Covers ~500 kHz to 1.5 MHz (AM broadcast band)
- **Change taps or switch capacitors** to extend range

**2. Variable Capacitor Construction** (Detailed):

**Simple plate capacitor** mentioned earlier deserves expansion:

**Multi-Plate Air Variable Capacitor** (Best Performance):

**Design**:
- **Interleaved plates**: Alternate stator (fixed) and rotor (moving) plates
- **More plates** = more capacitance
- **Air dielectric**: Stable, low loss, ideal for RF

**Construction**:
1. **Stator plates**:
   - Aluminum or brass sheets (0.5-1mm thick)
   - Semi-circular shape (180°), ~5-10 cm radius
   - Mount on insulated frame (plastic, wood)
   - Electrical connection: All stator plates connected together

2. **Rotor plates**:
   - Same material and size as stator
   - Mount on rotating shaft
   - All rotor plates connected together
   - Shaft rotates to mesh/unmesh plates

3. **Spacing**: 1-3mm air gap between stator and rotor
   - Smaller gap = more capacitance (but risk of shorting)

4. **Plate count**:
   - 5-10 plates each side typical
   - More plates = higher maximum capacitance

**Capacitance range**:
- **Minimum** (plates unmeshed): ~10-50 pF (parasitic capacitance)
- **Maximum** (plates fully meshed): ~200-500 pF
- **Range ratio**: 10:1 to 20:1 typical

**Alternative: Mica Dielectric Variable**:
- **Thin mica sheets** between plates
- **Higher capacitance** per volume than air
- **More compact**, but mica may be scarce post-collapse

**Vernier Drive** (Fine Tuning):
- **Gear reduction**: 5:1 or 10:1 between tuning knob and capacitor shaft
- **Allows precise tuning**: Critical for separating closely-spaced stations
- **Construction**: Two gears (large driving small, or worm gear)

**Salvage Priority**:
- **Highest**: Multi-section variable capacitors from old radios
- **Good**: Trimmer capacitors (adjustable, but limited range)

**Makeshift Single-Plate Variable**:
- Two aluminum sheets (10×10 cm)
- Adjust spacing between them (1-10mm)
- Range: ~5 pF (10mm apart) to ~80 pF (1mm apart)
- **Problem**: Difficult to get fine adjustment, unstable tuning

**3. Diode**: Galena crystal with cat's whisker wire, or salvaged silicon diode
**4. Antenna**: As long as possible, up high
**5. Ground**: Good earth connection essential

**Reception**: Weak, requires quiet environment and good station signal. Works best for nearby AM stations.

**Tuning Range Note**: Crystal radio with 100-200 turns (5-10cm diameter) and variable capacitor (10-500 pF) covers roughly 500 kHz to 1.5 MHz (AM broadcast band). To receive other frequencies, change coil taps or switch capacitors.

**Improvement**: Add amplification (requires battery and transistors or tubes)

### Continuous Wave (CW) Transmitter

**Improvement Over Spark**: Generates single, stable frequency

**Principle**: Oscillator creates continuous sine wave at radio frequency

**Basic Design: LC Oscillator**

**Components**:
1. **Oscillator**: Vacuum tube or transistor circuit
2. **LC tank circuit**: Inductor and capacitor set frequency
3. **Power amplifier**: Boost power
4. **Antenna**: Radiates signal
5. **Telegraph key**: Turn carrier on/off (CW = Morse code)

**Simple Vacuum Tube Oscillator**:
- Tube (triode): Amplifies
- LC circuit: Determines frequency
- Positive feedback: Sustains oscillation
- Key: In power supply or between oscillator and antenna

**Transistor Oscillator** (Smaller, More Efficient):
- Colpitts, Hartley, or crystal-controlled oscillator
- Transistor provides gain
- LC or crystal sets frequency
- Output to antenna

**Frequency Stability**:
- LC oscillator: Drifts with temperature (±1% typical)
- Crystal oscillator: Very stable (±0.001%)
- For reliable communication, crystal control preferred

**Modulation**: Simply turn carrier on and off for Morse code

**Reception**: Use beat frequency oscillator (BFO) in receiver to make CW audible

### Keying Methods for CW Transmitters

Keying is how the telegraph key turns the transmitter on and off to send Morse code. Different keying methods affect signal quality, efficiency, and receiver experience.

**Problems with Poor Keying**:
- **Key clicks**: Abrupt on/off creates broadband noise (interferes with nearby frequencies)
- **Chirp**: Frequency shifts during key-down (poor oscillator regulation)
- **Tail**: Signal continues after key-up (slow decay, letters run together)
- **Backwave**: Weak carrier present during key-up (poor keying isolation)

**Good Keying Characteristics**:
- **Clean on/off**: No clicks, chirps, or tails
- **Proper rise time**: 3-5 milliseconds (too fast = clicks, too slow = muddy)
- **Shaped envelope**: Rounded rise and fall (reduces harmonic content)
- **No backwave**: Complete carrier cutoff during key-up

**Keying Circuit Types**:

**1. Primary Keying** (Simplest, Poorest Quality):

**Method**: Key in main power supply line (breaks B+ or cathode/emitter current)

**Circuit** (Tube transmitter):
```
   Power Supply (+HV) ---[Key]--- Transmitter
```

**Advantages**:
- Extremely simple (one wire, one connection)
- Works with any transmitter
- No modifications needed

**Disadvantages**:
- **Severe key clicks** (abrupt on/off of full power)
- Power supply transients (voltage spikes)
- Hard on key contacts (high voltage, high current arcing)
- Dangerous (key has high voltage on it)
- No break-in capability (can't hear between dots/dashes)

**Use only for**: Emergency, temporary, or very low power (<1W)

**2. Cathode/Emitter Keying** (Better, Common):

**Method**: Key breaks cathode (tube) or emitter (transistor) connection to ground

**Tube Circuit**:
```
                +HV
                 |
             [Tube Plate]
                 |
              Output

         Grid ---|▷|--- Cathode
                          |
                        [Key] --- GND
```

**Advantages**:
- Lower voltage at key (safer)
- Less key clicks than primary keying
- Simple to implement
- Can add shaping networks easily

**Disadvantages**:
- Still some clicks if not shaped
- Oscillator may chirp (varies with cathode current)
- Medium key contact stress

**Shaping Network** (Reduces Clicks):
- **Add RC across key**: Resistor + capacitor slows rise/fall time
- **Typical values**: 1-10kΩ resistor, 0.01-0.1µF capacitor
- **Effect**: Rounds edges, reduces harmonics, eliminates clicks
- **Trade-off**: Too much shaping makes code muddy (limit to 3-5ms rise time)

**3. Grid-Block Keying** (Excellent Quality):

**Method**: Key applies large negative voltage to grid, cutting off tube completely

**Circuit**:
```
                +HV
                 |
             [Tube Plate]
                 |
              Output

         Grid ---[Resistor]--- -Bias (e.g., -50V)
                  |
                [Key] --- GND (or less negative voltage)
```

**When key up**: Grid held at large negative voltage (e.g., -50V), tube cut off
**When key down**: Grid connected to small negative voltage (e.g., -5V), tube conducts

**Advantages**:
- **Excellent click suppression** (oscillator runs continuously, only amplifier keyed)
- No chirp (oscillator frequency stable)
- Low key contact stress (low current, low voltage)
- Clean signal

**Disadvantages**:
- Requires bias supply (extra complexity)
- Oscillator runs continuously (wastes power when not keying)
- Not suitable for oscillator stage (only amplifiers)

**Practical Example**:
- Oscillator: Runs continuously (crystal-controlled for stability)
- Buffer/Driver: Keyed with grid-block keying
- Final Amplifier: Also keyed (or runs continuously if oscillator keyed)

**4. Screen-Grid Keying** (Tube Transmitters, Very Good):

**Method**: Key the screen grid (grid #2) of tetrode or pentode tube

**Circuit**:
```
              +HV (plate)
                |
            [Tube Plate]
                |
             Output

    Grid1 ---|▷|--- Grid2 (screen)
                      |
                    [Key] ---[Resistor]--- +Screen Voltage
                      |
                     GND (via capacitor)
```

**Advantages**:
- Excellent keying (clean, shaped)
- Lower voltage than plate (safer for key)
- Less current than cathode (easier on contacts)
- No chirp if oscillator separate

**Disadvantages**:
- Only works with tetrode/pentode tubes (not triodes)
- Requires screen voltage supply

**5. Transistor Base/Gate Keying** (Solid-State):

**Method**: Key the base (BJT) or gate (FET) to turn transistor on/off

**Circuit** (NPN transistor):
```
              +Vcc
                |
            [Collector]
                |
             Output

    Base ---|▷|--- Emitter
             |        |
           [Key]     GND
             |
      [Bias Resistor]
```

**Advantages**:
- Low voltage, low current (easy on key)
- Fast switching (transistors switch quickly)
- Efficient

**Disadvantages**:
- Can create severe clicks if not shaped
- Requires bias network
- Base-emitter junction fragile (protect from overvoltage)

**Shaping**: Add RC time constant (0.01µF + 10kΩ typical) for 3-5ms rise time

**6. Keyed Oscillator + CW Filter** (Modern, Best Quality):

**Method**:
1. Key oscillator on/off (generates CW signal)
2. Pass through **CW filter** (crystal or LC bandpass, ~500 Hz bandwidth)
3. Amplify in linear amplifiers (Class A or AB)

**Why This Works**:
- Abrupt keying creates clicks (wide spectrum)
- CW filter passes only ~500 Hz centered on carrier
- Clicks (which are wideband) get filtered out
- Result: Clean, shaped CW with no clicks

**Practical Implementation**:
- Crystal filter: 2-4 crystals (same frequency), coupled LC networks
- Bandwidth: 300-500 Hz (narrow enough to shape, wide enough for code)
- Salvage: SSB transceiver crystal filters often suitable

**Break-In Keying** (QSK - Full Break-In):

**Problem**: During transmit, you can't hear the other station. Blind sending wastes time if other station needs to interrupt.

**Solution**: Receiver switches on instantly between dots and dashes, allowing you to hear other station.

**Requirements**:
1. **Fast transmit/receive switching**: <5 milliseconds
2. **Receiver protection**: Prevent transmitter from destroying receiver input
3. **Antenna switching**: TR relay or solid-state switch

**Simple QSK Circuit**:
```
Transmitter ---[TR Relay]--- Antenna
                    |
Receiver -----------+
     |
  [Muting relay, opened during transmit]
```

**TR (Transmit-Receive) Relay**:
- **Contacts**: DPDT (double-pole double-throw) or better
- **Coil voltage**: Driven by keying line
- **Speed**: <5ms actuation time (fast relay required)
- **Contacts**: Heavy-duty (handle RF current without arcing)

**Receiver Muting**:
- Open receiver input during transmit (prevent overload)
- Can use PIN diodes (solid-state, very fast) or relay
- Must operate in sync with TR relay

**Practical QSK Setup**:
1. Key closes:
   - TR relay energizes (antenna to transmitter)
   - Receiver muted
   - Transmitter begins keying (shaped rise)
2. Key opens:
   - Transmitter signal decays (shaped fall)
   - TR relay releases (antenna to receiver)
   - Receiver unmuted
   - Can hear incoming signal within ~5-10ms

**Key Click Filter** (External to Transmitter):

If transmitter has bad clicks and can't be modified, add external filter:

**Low-Pass Filter** (After Transmitter, Before Antenna):
- **Cutoff**: Just above operating frequency
- **Type**: 5-pole Chebyshev or Butterworth
- **Attenuation**: >40 dB at 2× operating frequency

**Example** (7 MHz transmitter):
- Cutoff: 7.3 MHz
- Attenuation at 14 MHz: >50 dB (suppresses 2nd harmonic and clicks)

**Key Types**:

**Straight Key** (Traditional):
- Simple: Lever, spring, contacts
- Operator controls dit/dah length manually
- Slow (10-20 WPM typical, 30 WPM for experts)

**Bug/Semi-Automatic Key**:
- Dits automatic (vibrating contact)
- Dahs manual
- Faster (20-30 WPM typical)

**Electronic Keyer** (Modern):
- IC or microcontroller generates perfect dits/dahs
- Paddle input (squeeze for dit, squeeze other way for dah)
- 20-50+ WPM easily
- Requires external circuit (can build from salvaged ICs)

**Keying Summary Table**:

| Method | Click Suppression | Chirp | Safety | Complexity | Quality |
|--------|-------------------|-------|--------|------------|---------|
| **Primary** | Poor | High | Dangerous | Trivial | Poor |
| **Cathode/Emitter** | Fair (with shaping) | Medium | Moderate | Low | Fair |
| **Grid-Block** | Excellent | None | Good | Medium | Excellent |
| **Screen-Grid** | Excellent | Low | Good | Medium | Excellent |
| **Base/Gate** | Good (with shaping) | Low | Excellent | Low | Good |
| **CW Filter** | Excellent | None | Excellent | High | Excellent |

**Recommendation**:
- **Simple transmitter**: Cathode keying + RC shaping
- **Quality transmitter**: Grid-block or screen-grid keying
- **Modern/complex**: Keyed oscillator + CW filter + QSK

### Power Amplifier Design (All Transmitters)

Power amplifiers (PA) boost low-level RF signals to useful transmit power. Different amplifier classes trade efficiency for linearity. Understanding these is critical for building effective transmitters.

**Amplifier Classes**:

**Class A (Linear, Low Efficiency)**:

**Operation**:
- Tube or transistor conducts **continuously** (full 360° of RF cycle)
- Biased to middle of linear range
- Output is faithful reproduction of input (linear)
- Used for: SSB, AM (driver stages), linear amplification where distortion is unacceptable

**Characteristics**:
- **Efficiency**: 25-40% (most power wasted as heat)
- **Linearity**: Excellent (low distortion)
- **Bias**: Centered in linear region (tubes: ~-2 to -5V grid, transistors: active region)
- **Conduction angle**: 360° (always conducting)
- **Power dissipation**: High (heatsink required)

**When to Use**:
- SSB transmitters (must be linear to avoid distortion)
- AM transmitters (driver stages before final modulated stage)
- Low-power applications where efficiency is not critical

**Tube Circuit Example** (Class A):
```
                    +HV (250-1000V)
                       |
                     [RFC] (RF choke, blocks RF, passes DC)
                       |
                   [Tank Circuit] --- Output to antenna
                       |
              Grid ---|▷|--- Plate (Tube)
                   [Bias] (-2 to -5V)
                       |
                      GND
```

- **Bias voltage**: Keeps tube conducting continuously
- **Tank circuit**: LC resonator at operating frequency
- **RFC**: Prevents RF from entering power supply

**Transistor Circuit Example** (Class A):
- Similar, but bias transistor into middle of active region
- Collector current flows continuously
- Requires good heatsinking (50-70% of DC power becomes heat)

**Class B (Push-Pull, Better Efficiency)**:

**Operation**:
- Each tube/transistor conducts for **half** the RF cycle (180°)
- Two devices in push-pull: One handles positive half, other handles negative half
- Combined output reproduces full waveform
- Used for: AM transmitters (linear enough), SSB (with careful design)

**Characteristics**:
- **Efficiency**: 50-65% (much better than Class A)
- **Linearity**: Good (some crossover distortion at zero-crossing)
- **Bias**: At cutoff (tubes: 0V grid, transistors: just below conduction)
- **Conduction angle**: 180° per device (360° combined)
- **Power dissipation**: Moderate (better than Class A)

**When to Use**:
- AM transmitters (acceptable linearity, good efficiency)
- SSB with careful design (Class AB often preferred)
- Medium power (10-100W) where efficiency matters

**Push-Pull Tube Circuit** (Class B):
```
                      +HV (500-2000V)
                         |
                    [Tank Circuit]
                      /     \
         Tube 1 ---|▷|       |▷|--- Tube 2
                  /             \
    RF Input ---[Transformer]--- RF Input (180° out of phase)
                  |             |
                 GND           GND
```

- **Transformer**: Provides 180° phase shift between tubes
- **Each tube**: Conducts only when input is positive
- **Output**: Combined in tank circuit (full waveform reconstructed)

**Class AB (Compromise Between A and B)**:
- Bias slightly above cutoff (conducts slightly more than 180°)
- Better linearity than Class B, better efficiency than Class A
- Efficiency: 45-60%
- Popular for SSB transmitters (good compromise)

**Class C (Highest Efficiency, Nonlinear)**:

**Operation**:
- Tube or transistor conducts for **less than half** the RF cycle (<180°)
- Heavily biased beyond cutoff
- Only conducts on peaks of input signal
- Tank circuit "rings" to fill in missing portions (flywheel effect)
- Used for: CW transmitters, FM transmitters, frequency multipliers

**Characteristics**:
- **Efficiency**: 70-85% (excellent, minimal heat)
- **Linearity**: Poor (severe distortion, produces harmonics)
- **Bias**: Well beyond cutoff (tubes: -10 to -20V grid, transistors: reverse bias)
- **Conduction angle**: 120-150° (or less)
- **Power dissipation**: Low (most DC power becomes RF output)

**When to Use**:
- CW transmitters (on/off keying, no linearity needed)
- FM transmitters (constant amplitude, frequency varies)
- Frequency multipliers (distortion intentionally creates harmonics)
- High power applications where efficiency is critical

**NEVER Use for**:
- SSB (will cause severe distortion and splatter)
- AM (unless only used for unmodulated carrier stage before plate modulation)

**Tube Circuit Example** (Class C):
```
                    +HV (500-3000V)
                       |
                     [RFC]
                       |
                   [Tank Circuit] --- Output (fundamental frequency)
                       |             [Harmonic filter]
              Grid ---|▷|--- Plate           |
                   [Bias] (-10 to -20V)    Antenna
                       |
        RF Drive ---[Cap]
                       |
                      GND
```

- **Heavy bias**: Tube only conducts on strong positive peaks of input
- **Tank circuit Q**: Must be high (Q > 10) to "flywheel" and fill in missing waveform
- **Harmonic filter**: Removes harmonics created by nonlinear operation
- **Efficiency**: 70-85% typical (much less heat than Class A or B)

**Tank Circuit for Class C**:
- **Higher Q needed**: Q = 10-20 (versus Q = 3-5 for Class A)
- **Flywheel effect**: Stored energy in LC circuit sustains oscillation between conduction pulses
- **Bandwidth**: Narrower (only good for single frequency or narrow band)

**Comparison Table**:

| Class | Conduction Angle | Efficiency | Linearity | Use Case | Bias |
|-------|------------------|------------|-----------|----------|------|
| **A** | 360° | 25-40% | Excellent | SSB, AM driver | Center of linear region |
| **AB** | 180-360° | 45-60% | Good | SSB, AM | Slightly above cutoff |
| **B** | 180° | 50-65% | Fair | AM, some SSB | At cutoff |
| **C** | <180° | 70-85% | Poor | CW, FM, multipliers | Beyond cutoff |

**Practical Design Considerations**:

**Heatsinking**:
- **Class A**: Dissipates 60-75% of DC input as heat (large heatsink required)
- **Class B**: Dissipates 35-50% as heat (moderate heatsink)
- **Class C**: Dissipates 15-30% as heat (small heatsink acceptable)
- **Rule of thumb**: Heatsink thermal resistance < (T_max - T_ambient) / P_dissipated
- **Example**: 50W dissipation, 100°C max junction temp, 25°C ambient
  - Thermal resistance needed: (100 - 25) / 50 = 1.5°C/W
  - Use heatsink rated ≤1.5°C/W

**Tank Circuit Design**:
- **L (inductance)**: Determined by frequency and desired Q
- **C (capacitance)**: Resonates with L at operating frequency
- **Q factor**: Q = X_L / R = (2πfL) / R
- **Class A/B**: Q = 3-5 (broader bandwidth, less critical tuning)
- **Class C**: Q = 10-20 (narrow bandwidth, efficient flywheel)

**Example Tank Circuit** (Class C, 7 MHz, 50W output):
- **Frequency**: 7 MHz
- **Target Q**: 12
- **Load resistance**: 50Ω (antenna)
- **Reactance**: X_L = Q × R = 12 × 50 = 600Ω
- **Inductance**: L = X_L / (2πf) = 600 / (2π × 7×10⁶) ≈ 13.6 μH
- **Capacitance**: C = 1 / (4π²f²L) ≈ 38 pF
- **Coil**: ~15-20 turns on 2.5 cm diameter form (air core)
- **Variable capacitor**: 10-100 pF for tuning

**Neutralization** (Preventing Self-Oscillation):

High-gain amplifiers can oscillate due to feedback between output and input. Neutralization cancels this feedback.

**Tube Amplifiers**:
- **Problem**: Plate-to-grid capacitance (C_pg) feeds signal back
- **Solution**: Add neutralizing capacitor with opposite-phase feedback
- **Method**: Tap center of tank coil, connect neutralizing cap from tap to grid
- **Adjustment**: Tune neutralizing cap until oscillation stops (use grid-dip meter or RF probe)

**Transistor Amplifiers**:
- Similar issue with collector-to-base capacitance
- Neutralization or use of common-base configuration (inherently stable)

**Biasing Methods**:

**Fixed Bias** (Separate bias supply):
- Simple, stable
- Requires separate power supply for bias voltage
- Common in tube transmitters

**Cathode/Emitter Bias** (Self-bias):
- Resistor in cathode/emitter, bypassed with capacitor
- Current through resistor creates bias voltage
- Automatic, simple, but less stable with temperature

**Grid-Leak Bias** (Class C only):
- Capacitor and resistor at grid rectify RF drive
- Creates own bias from RF input
- Only works when RF drive is present
- Common in Class C oscillators and multipliers

**Practical Example: 40W Class C CW Transmitter (7 MHz)**

**Tube**: 6146 (common transmitting tube, salvageable)
**Frequency**: 7.1 MHz (40 meter band)
**Power Output**: 40W RF
**Efficiency**: ~75%
**DC Input**: 40 / 0.75 ≈ 53W
**Plate Voltage**: 500V
**Plate Current**: 53 / 500 ≈ 106 mA

**Circuit**:
1. **Oscillator**: Crystal at 7.1 MHz (or VFO)
2. **Driver**: Small Class A or AB amplifier (boost to ~5W)
3. **Final amplifier**: 6146 in Class C (boost to 40W)
4. **Tank circuit**: L = 13.6 μH, C = 38 pF (variable for tuning)
5. **Bias**: -15V grid (fixed bias or grid-leak)
6. **RFC**: 2.5 mH in plate supply (keeps RF out of power supply)
7. **Harmonic filter**: Low-pass filter after tank (removes harmonics)

**Tuning Procedure**:
1. Set bias to cutoff (no plate current with no drive)
2. Apply RF drive (~1W from driver)
3. Adjust tank capacitor for resonance (dip in plate current, peak in output)
4. Increase drive to rated level
5. Re-tune tank for maximum output
6. Check harmonic output (should be >40 dB below fundamental)

**Keying**: Break cathode connection with telegraph key (cathode keying)

### Amplitude Modulation (AM) Voice Transmitter

**Principle**: Vary amplitude of carrier wave with audio signal

**Components**:
1. **Microphone**: Converts sound to electrical signal
2. **Audio amplifier**: Boost microphone signal
3. **RF oscillator**: Generates carrier wave (e.g., 1 MHz)
4. **Modulator**: Varies oscillator amplitude with audio
5. **Power amplifier**: Boost to desired transmit power
6. **Antenna**: Radiates modulated signal

**Modulation Methods**:

**1. Plate Modulation** (High-Level, Vacuum Tubes):
- Audio signal varies DC voltage to tube plate
- Plate voltage controls RF amplitude
- Efficient, clean

**2. Emitter/Cathode Modulation** (Low-Level):
- Audio varies bias of amplifier
- Can use tubes or transistors

**3. Collector Modulation** (Transistors):
- Audio varies collector supply voltage
- Good efficiency

**Simple AM Transmitter**:
1. Crystal oscillator at carrier frequency (e.g., 1 MHz)
2. Buffer amplifier (isolate oscillator)
3. Modulated amplifier (audio varies gain)
4. Power amplifier (boost to 1-100W)
5. Antenna tuner (match impedance)

**Reception**: AM receiver (superheterodyne design, see below)

**Range**: Depends on power and frequency
- 1W at 1 MHz: 5-10 km daytime, 50-100 km nighttime (ionosphere reflection)
- 100W at 1 MHz: 100+ km daytime, 1,000+ km nighttime

### Frequency Modulation (FM) Transmitter

**Principle**: Vary frequency of carrier (instead of amplitude) with audio

**Advantages Over AM**:
- Better sound quality
- Less affected by interference (static, electrical noise)
- More complex to build

**Components**:
1. **VCO (Voltage Controlled Oscillator)**: Frequency varies with input voltage
2. **Audio input**: Microphone and amplifier
3. **Power amplifier**: Must handle varying frequency
4. **Antenna**: Usually VHF (88-108 MHz for FM broadcast)

**Modulation**:
- Center frequency: Carrier (e.g., 100 MHz)
- **Audio signal varies frequency** (deviation)
- Frequency deviation proportional to audio amplitude

**FM Deviation Standards**:
- **FM broadcast** (88-108 MHz): ±75 kHz deviation (wideband)
  - Channel spacing: 200 kHz
  - Bandwidth: ~200 kHz per channel
  - High fidelity audio (15 kHz audio bandwidth)
- **Narrowband FM** (VHF/UHF voice): ±5 kHz deviation
  - Channel spacing: 12.5-25 kHz
  - Bandwidth: ~16 kHz per channel
  - Communications quality (3 kHz audio bandwidth)
  - Used on 2m (144 MHz) and 70cm (440 MHz) bands
- **Amateur FM**: ±5 kHz typical (compatible with narrowband equipment)

**Deviation vs. Bandwidth**:
- Carson's Rule: BW ≈ 2 × (deviation + audio bandwidth)
- **Broadcast FM**: BW ≈ 2 × (75 + 15) = 180 kHz (fits in 200 kHz channel)
- **Narrowband FM**: BW ≈ 2 × (5 + 3) = 16 kHz (fits in 25 kHz channel)

**Simple FM Transmitter**:
- Varactor diode: Capacitance varies with voltage
- Include in LC oscillator circuit
- Audio varies varactor voltage, thus frequency
- Very simple, low power
- Or use PLL (phase-locked loop) IC for better stability

**Reception**: FM receiver (more complex than AM)

### Radio Receiver Design

**Crystal Radio**: Covered above. No power, weak reception.

**TRF (Tuned Radio Frequency) Receiver**:
1. **Antenna**: Picks up signals
2. **RF amplifier**: Boosts signal at radio frequency
3. **Detector**: Extracts audio (diode for AM)
4. **Audio amplifier**: Drives speaker

**Problems**: Must tune multiple stages together, limited selectivity

**Superheterodyne Receiver** (Best Design):

**Principle**: Convert incoming signal to fixed intermediate frequency (IF), easier to filter and amplify

**Stages**:
1. **RF amplifier**: Select and boost desired signal
2. **Mixer**: Combine incoming signal with local oscillator
   - Produces sum and difference frequencies
   - Difference = IF (usually 455 kHz for AM, 10.7 MHz for FM)
3. **Local oscillator**: Frequency = incoming + IF (or incoming - IF)
   - Tune this to change stations
4. **IF amplifier**: Fixed frequency, high gain, sharp filtering
5. **Detector**: Extract audio from IF signal
6. **Audio amplifier**: Drive speaker

**Advantages**:
- Excellent selectivity (separates stations)
- High gain
- Single tuning control

**Example** (AM broadcast receiver):
- Station: 1,000 kHz
- IF: 455 kHz
- Local oscillator: 1,000 + 455 = 1,455 kHz
- Mixer output: 1,455 - 1,000 = 455 kHz (IF)
- IF amplifier processes 455 kHz signal
- Detector extracts audio

**Image Frequency Problem** (Critical Superheterodyne Issue):

**Problem**: Mixer produces IF from TWO input frequencies, not just the desired one.

**Mathematics**:
- **Desired frequency**: f_signal
- **Local oscillator**: f_LO = f_signal + IF (high-side injection)
- **Mixer output**: f_LO - f_signal = IF ✓ (this is what we want)
- **BUT ALSO**: f_LO - f_image = IF (undesired image frequency)
- **Image frequency**: f_image = f_LO + IF = f_signal + 2×IF

**Example** (AM receiver, 1000 kHz desired station):
- **Desired**: 1000 kHz
- **Local oscillator**: 1000 + 455 = 1455 kHz
- **IF**: 455 kHz
- **Image frequency**: 1455 + 455 = 1910 kHz
  - Mixer sees 1910 kHz signal
  - Calculates: 1910 - 1455 = 455 kHz (same as desired!)
  - If station broadcasting on 1910 kHz, you hear BOTH 1000 kHz and 1910 kHz simultaneously (interference)

**Image Rejection Methods**:

**1. RF Amplifier Pre-Selectivity** (Most Important):
- Tuned circuit before mixer
- Rejects image frequency
- Typically LC tank circuit tracking with main tuning
- **Rejection**: 20-40 dB typical (100:1 to 10,000:1)

**2. Higher IF Frequency**:
- Image separation = 2 × IF
- **455 kHz IF**: Image is 910 kHz away (moderate separation)
- **10.7 MHz IF**: Image is 21.4 MHz away (excellent separation, easy to filter)
- **Why FM uses 10.7 MHz**: Easier image rejection at VHF
- Trade-off: Higher IF harder to build (fewer turns, tighter tolerances)

**3. Dual Conversion** (Two IF Stages):
- **First IF**: High frequency (e.g., 10.7 MHz) for good image rejection
- **Second IF**: Low frequency (e.g., 455 kHz) for good selectivity
- **Best of both worlds**: Excellent image rejection AND sharp filtering
- Used in high-performance receivers (SSB, weak signal)

**Image Frequency Table** (AM Broadcast Band):

| Desired (kHz) | IF (kHz) | LO (kHz) | Image (kHz) | Image Band |
|---------------|----------|----------|-------------|------------|
| 550 | 455 | 1005 | 1460 | Within AM band! |
| 800 | 455 | 1255 | 1710 | Within AM band |
| 1000 | 455 | 1455 | 1910 | Above AM band (less problem) |
| 1600 | 455 | 2055 | 2510 | Well above AM band |

**Why Image Is Serious**:
- **Low bands (AM broadcast)**: Image often within same band (interfering station likely)
- **No RF preselection**: You hear two stations at once (confusing, unusable)
- **Strong image station**: Can completely mask desired weak station

**Testing Image Rejection**:
1. Tune receiver to desired frequency (e.g., 1000 kHz)
2. Inject strong signal at image frequency (e.g., 1910 kHz)
3. Measure output (should be greatly reduced compared to desired frequency)
4. **Good rejection**: >30 dB (1000:1 power ratio)
5. **Poor rejection**: <20 dB (image signal audible, interfering)

**Improving Image Rejection** (Practical):
- Add tuned RF amplifier stage before mixer (tracks with main tuning)
- Use double-tuned RF transformers (better selectivity)
- Increase IF frequency if possible (moves image farther away)
- Use dual-gate MOSFET or cascode amplifier (better gain at RF)

**FM Detection**:
- Discriminator or ratio detector (classic)
- PLL detector (modern, requires IC)

**Building a Superheterodyne Receiver**:
- Can use salvaged ICs (one chip often does mixer, oscillator, IF amp, detector)
- Or build discrete components (more difficult)
- Alignment requires signal generator and oscilloscope or meter

**IF Transformer Construction** (Critical Component):

IF transformers (IFTs) provide frequency-selective coupling between stages in the IF amplifier chain. Proper construction determines receiver selectivity and gain.

**Basic Structure**:
1. **Primary coil**: Input from previous stage
2. **Secondary coil**: Output to next stage
3. **Magnetic coupling**: Core links the coils
4. **Shielded can**: Prevents external interference and inter-stage coupling
5. **Tuning mechanism**: Adjustable core or capacitor for alignment

**Construction for 455 kHz IF (Standard AM)**:

**Coil Specifications**:
- **Wire**: 38-42 AWG enameled copper wire (very fine)
- **Form**: Phenolic or plastic bobbin, ~8-12mm diameter, ~20-25mm long
- **Primary winding**: 80-120 turns
- **Secondary winding**: 80-120 turns (same as primary for 1:1 impedance ratio)
- **Winding direction**: Same direction for both coils (in-phase coupling)
- **Layer insulation**: Thin paper or plastic film between primary and secondary

**Core Material**:
- **Ferrite slug**: Adjustable ferrite core (salvage from old radios)
- **Thread**: 6-32 or M3.5 thread on slug (or use threaded brass adjustment screw)
- **Permeability**: μ = 60-125 typical (higher permeability = more inductance range)
- **Adjustment range**: Core fully in to fully out should cover ±10% of center frequency

**Shielding Can**:
- **Material**: Aluminum or tin-plated steel, ~15-20mm diameter, ~30-40mm tall
- **Purpose**: Prevents coupling between IF stages (would cause oscillation)
- **Grounding**: Can must connect to ground/chassis
- **Mounting**: Solder can to PCB ground plane or chassis

**Capacitor (Parallel Tuning)**:
- **Value**: 100-200 pF ceramic or mica capacitor across each winding
- **Purpose**: Resonates coil at IF frequency (455 kHz)
- **Formula**: f = 1 / (2π√LC)
- **Example**: 100 μH coil + 120 pF = 1 / (2π√(100×10⁻⁶ × 120×10⁻¹²)) ≈ 460 kHz

**Q Factor Requirements**:
- **Unloaded Q**: 80-150 typical for good IFT
- **Loaded Q**: 40-80 (after connecting to circuit)
- **Higher Q**: Better selectivity (narrow bandwidth, separates stations)
- **Lower Q**: Wider bandwidth (better audio quality, less selective)
- **Trade-off**: Q = 50-60 is good compromise for AM broadcast reception

**Coupling Coefficient**:
- **k = 0.01 to 0.05** (1% to 5% coupling) typical
- **Loose coupling** (k < 0.02): Good selectivity, lower gain
- **Tight coupling** (k > 0.03): Higher gain, wider bandwidth
- **Controlled by**: Distance between primary and secondary, core material

**Assembly Procedure**:

1. **Wind primary coil**:
   - Start at bottom of bobbin
   - Wind 80-120 turns, close-wound (no spacing)
   - Secure ends (tape or tie-down posts on bobbin)

2. **Insulation layer**:
   - Wrap thin paper or plastic film around primary
   - Prevents shorts between primary and secondary

3. **Wind secondary coil**:
   - Wind in same direction as primary
   - Same number of turns (80-120)
   - Keep windings neat and tight

4. **Install ferrite slug**:
   - Thread slug into bobbin (if bobbin has threads)
   - Or use separate threaded adjustment screw that pushes slug in/out
   - Slug should move smoothly without binding

5. **Solder connections**:
   - Primary: Connect to previous stage (collector or plate) via coupling capacitor
   - Secondary: Connect to next stage (base or grid) via coupling capacitor
   - Taps (if used): For impedance matching

6. **Install tuning capacitors**:
   - Solder 100-200 pF capacitor across primary winding
   - Solder 100-200 pF capacitor across secondary winding
   - Values should match closely (within 5%)

7. **Mount in shield can**:
   - Slide assembled transformer into aluminum can
   - Leave adjustment screw accessible through hole in top of can
   - Seal with wax or potting compound (optional, prevents movement)

8. **Ground can**:
   - Solder can to chassis or ground plane
   - This is critical for preventing oscillation

**Impedance Matching (If Needed)**:

If source and load impedances don't match (e.g., high-impedance tube plate to low-impedance transistor base):

- **Turns ratio matching**: n = √(Z_primary / Z_secondary)
- **Example**: Match 5000Ω plate to 500Ω base
  - n = √(5000 / 500) = √10 ≈ 3.16
  - Primary: 120 turns
  - Secondary: 120 / 3.16 ≈ 38 turns

- **Tapped windings**: Tap primary or secondary at fraction of total turns
  - Example: Tap at 1/3 of winding gives 1/9 impedance ratio (n²)

**Alignment Procedure** (Requires Signal Generator):

1. **Equipment needed**:
   - RF signal generator (455 kHz modulated with 400-1000 Hz audio)
   - Oscilloscope or AC voltmeter
   - Non-metallic alignment tool (plastic or phenolic screwdriver)

2. **Setup**:
   - Inject 455 kHz signal at mixer output or first IF stage input
   - Monitor output at detector stage or speaker
   - Set signal generator to very low level (avoid overload)

3. **Alignment sequence** (Start at detector end, work backward):
   - **Last IFT**: Adjust core for maximum output (peak voltage or loudest tone)
   - **Second-to-last IFT**: Adjust for maximum output
   - **Continue** backward through all IF stages
   - **Re-peak**: Go through all IFTs again (adjustment of one affects others)
   - **Final pass**: Touch up each for absolute maximum

4. **Check bandwidth**:
   - Tune signal generator ±10 kHz from 455 kHz
   - Output should drop significantly (good selectivity)
   - If output stays high across wide range: Q too low or stages overcoupled

**Salvaging IFTs**:

**Best sources**:
- Old AM radios (1940s-1980s): 455 kHz IFTs
- Transistor radios (1960s-1980s): Small, efficient IFTs
- Car radios: Usually 455 kHz, often potted (sealed in wax)
- FM radios: 10.7 MHz IFTs (different construction, smaller)

**Identification**:
- Usually 3-6 IFTs in superheterodyne receiver
- Located between mixer and detector stages
- Distinctive shielded cans (aluminum, 15-20mm diameter)
- Adjustment screw on top (slotted or hex)

**Testing salvaged IFTs**:
- Check continuity: Both primary and secondary should show ~5-20Ω DC resistance
- Check isolation: Primary to secondary should show open circuit (no connection)
- Check capacitance: Measure across winding (should be ~100-200 pF if capacitor intact)
- Check resonance: Use dip meter or LC meter if available

**Common Problems**:
- **Open winding**: Fine wire broken (nearly impossible to repair)
- **Shorted turns**: Winding touches itself (causes low Q, poor performance)
- **Lost capacitor**: Can replace with external capacitor of same value
- **Stuck slug**: Can sometimes free with penetrating oil and gentle persuasion
- **Corroded connections**: Clean with contact cleaner, resolder if needed

**Alternative: Salvage-Free IFT Construction**:

If no salvage available, build from scratch:

1. **Bobbin**: Turn on lathe from plastic or wood (8-10mm diameter, 25mm long)
2. **Thread**: Cut M3 or M4 thread in center hole
3. **Ferrite slug**: Make from powdered iron + epoxy, or use steel bolt (lower Q)
4. **Can**: Form from salvaged aluminum sheet, solder seam
5. **Wind as described above**

**Performance Expectations**:
- **Home-made IFT**: Q = 40-80 (acceptable for basic receiver)
- **Salvaged IFT**: Q = 60-120 (good performance)
- **Professional IFT** (new old stock): Q = 100-150 (excellent performance)

**10.7 MHz IF Transformers (For FM)**:

FM receivers use 10.7 MHz IF instead of 455 kHz. Construction differences:

- **Fewer turns**: 15-30 turns typical (higher frequency = less inductance needed)
- **Smaller diameter**: 6-8mm coil form
- **Air core or low-μ ferrite**: Permeability = 3-10 (versus 60-125 for AM)
- **Tighter tolerances**: FM bandwidth is narrower (±75 kHz deviation)
- **Multiple IFTs**: FM typically uses 3-4 IFTs for limiting and discrimination

### Automatic Gain Control (AGC)

AGC prevents receiver overload from strong signals and maintains consistent audio output despite varying signal strengths. Essential for comfortable listening and preventing damage.

**Problem Without AGC**:
- **Weak station**: Audio barely audible, must turn up volume
- **Strong station**: Blast of loud audio (damages speaker, hurts ears, overloads stages)
- **Fading signal**: Audio volume fluctuates wildly (annoying, hard to copy)
- **Stage overload**: Strong signals drive amplifiers into distortion or cutoff

**AGC Solution**:
- Detects signal strength
- Automatically reduces gain when signal is strong
- Increases gain when signal is weak
- Maintains relatively constant audio output level

**Basic AGC Principle**:

1. **Sample IF or RF signal strength** (before detector)
2. **Rectify and filter** to get DC voltage proportional to signal strength
3. **Apply DC voltage to earlier stages** (RF amp, mixer, IF amps) to control their gain
4. **Negative feedback**: Strong signal → higher AGC voltage → lower gain → prevents overload

**Simple AGC Circuit (AM Receiver)**:

```
IF Amplifier → Detector → Audio Output
     ↑            |
     |         [Rectify]
     |            |
     |         [Filter] (0.1-1 second time constant)
     |            |
     |        AGC DC Voltage
     |            |
     +------------+ (Feed back to reduce gain)
```

**AGC Voltage Source**:

**Method 1: Detector Voltage**:
- Take DC output from AM detector (after diode, before coupling capacitor)
- Already rectified (diode does this during detection)
- Filter with large capacitor and resistor (0.1-1 second time constant)
- Apply to IF amplifier grid (tube) or base (transistor) to reduce gain

**Method 2: Separate AGC Detector**:
- Tap IF signal before main detector
- Feed to separate diode rectifier
- Filter to DC
- Advantage: Can set different time constants for AGC vs. audio

**AGC Application to Amplifier Stages**:

**Tube Receivers** (Bias Grid for AGC):

**Normal operation** (no AGC):
- Grid bias: -1 to -3V (normal operating point)
- High gain

**Strong signal** (AGC active):
- AGC voltage: -5 to -20V applied to grid
- Tube approaches cutoff
- Gain reduced 10-100×

**Circuit**:
```
                +HV
                 |
             [RF Choke]
                 |
               Plate
                 |
         Grid --|▷|-- Cathode
                 |         |
            [AGC Voltage] GND
                 |
            [Filter Cap]
```

**Transistor Receivers** (Vary Base Bias or Emitter Degeneration):

**Method 1: Base Bias Control**:
- AGC voltage reduces forward bias on base
- Transistor operates at lower collector current
- Gain reduced

**Method 2: Emitter Degeneration**:
- AGC voltage increases emitter resistance
- Reduces gain without changing DC operating point
- More linear gain control

**AGC Time Constants**:

**Fast AGC** (50-100 ms):
- Responds quickly to signal changes
- Good for fading signals (Morse code, ionospheric flutter)
- Can "pump" on audio (gain changes with modulation, distortion)

**Slow AGC** (0.5-2 seconds):
- Smooth response
- Doesn't follow rapid fading
- No pumping on audio modulation
- Good for AM broadcast (strong, stable signals)

**Compromise** (0.1-0.5 seconds):
- Works for most signals
- Typical for general-purpose receivers

**Hang AGC** (Advanced):
- Fast attack (respond quickly to strong signal)
- Slow decay (hold gain reduction for 0.5-1 second after signal drops)
- Advantage: No inter-syllable pumping on SSB/AM voice
- Requires more complex circuit (delay line or storage capacitor)

**Practical AGC Design (Tube Receiver, AM)**:

**Stages to AGC**:
1. **IF amplifiers**: Primary AGC target (most gain here)
2. **RF amplifier**: Secondary AGC (only if very strong signals present)
3. **Mixer**: Usually not AGC'd (needs constant gain for good mixer operation)

**Circuit Values** (Tube IF amplifier):
- **AGC line resistor**: 470kΩ to 2.2MΩ (decouples stages)
- **AGC filter capacitor**: 0.1-1 µF (sets time constant with resistor)
- **Time constant**: R × C
  - Example: 1MΩ × 0.5µF = 0.5 second (good for AM)
  - For CW: 1MΩ × 0.05µF = 0.05 second (faster response)

**AGC Detector Diode**:
- Germanium (low forward voltage, more sensitive) or silicon
- Load resistor: 100kΩ to 1MΩ
- Filter cap: 0.01-0.1 µF (remove RF, pass audio modulation envelope)

**Delayed AGC** (Prevents Weak Signal Gain Reduction):

**Problem**: Simple AGC reduces gain even on weak signals
**Solution**: Don't apply AGC until signal exceeds threshold

**Circuit**:
- Add diode and bias voltage in AGC line
- Bias = threshold voltage (e.g., -3V)
- When AGC voltage < -3V (weak signal): Diode blocks, no AGC action
- When AGC voltage > -3V (strong signal): Diode conducts, AGC applied

**Benefit**: Full gain on weak signals, AGC only on strong signals that need it

**AGC in Superheterodyne vs. TRF**:

**Superheterodyne Advantage**:
- IF amplifiers all at same frequency (455 kHz)
- Easy to apply AGC (all stages respond similarly)
- Effective across all received frequencies

**TRF Challenge**:
- RF stages tuned to different frequencies as you tune radio
- AGC effectiveness varies with frequency
- Less effective than superheterodyne AGC

**Testing and Adjustment**:

**AGC Test Procedure**:
1. **Inject test signal**: Use signal generator at IF frequency (455 kHz modulated)
2. **Set to weak level**: Adjust receiver for comfortable audio
3. **Increase signal level 100× (40 dB)**: Audio should increase only 2-3× (not 100×)
4. **Observe**: If audio increases 100×, AGC not working (check circuit)
5. **Adjust AGC time constant**: If audio "pumps" (varies with modulation), increase time constant

**AGC Range**:
- Good AGC: Handles 40-60 dB signal range (10,000:1 power ratio) with <10 dB audio change
- Excellent AGC: Handles 60-80 dB range with <6 dB audio change

**Salvaging AGC Components**:

**From Old Radios**:
- AGC line resistors: Usually 470kΩ-2.2MΩ, wire-wound or carbon
- AGC filter caps: 0.1-1 µF, tubular or ceramic
- AGC diodes: Germanium (1N34A, 1N60) or silicon (1N4148)
- Check schematic or trace from detector to earlier stages

**AGC for SSB/CW Reception**:

**SSB** (Single Sideband):
- Fast AGC attack (50ms)
- Hang AGC (0.5-1 second hang time) prevents inter-syllable pumping
- More complex: Separate slow and fast AGC

**CW** (Morse Code):
- Fast AGC (50-100ms) follows fading
- Or use manual gain control (operator adjusts volume)
- Some prefer no AGC for CW (manual control gives better weak-signal copying)

**Manual vs. Automatic Gain Control**:

**Manual RF Gain Control**:
- Potentiometer adjusts bias on RF/IF stages
- Operator controls gain manually
- Advantages: No pumping, better weak signal reception, simpler
- Disadvantages: Requires constant adjustment if signal fading

**Combination** (Best Approach):
- AGC for general use
- Manual RF gain control to override AGC when needed
- Switch or potentiometer to disable AGC and set manual gain

**AGC Summary Table**:

| AGC Type | Attack Time | Decay Time | Best For | Complexity |
|----------|-------------|------------|----------|------------|
| **Simple** | 0.1-1s | 0.1-1s | AM broadcast | Low |
| **Fast** | 50-100ms | 50-100ms | CW, fading signals | Low |
| **Slow** | 0.5-2s | 0.5-2s | Strong AM signals | Low |
| **Hang** | 50ms | 0.5-1s hang | SSB voice | Medium |
| **Delayed** | Variable | Variable | Weak + strong signals | Medium |

**Recommendation**:
- **Simple AM receiver**: Basic AGC (0.5s time constant, apply to IF stages)
- **General-purpose receiver**: Delayed AGC + manual override
- **SSB/CW receiver**: Fast attack + hang AGC, or manual control option

### Antenna Design

**Dipole Antenna** (Most Common):
- Length: λ/2 total (λ/4 each side of center)
- Fed at center
- Horizontal: Radiates broadside
- Vertical: Radiates omnidirectionally
- Impedance: 72 ohms

**Monopole/Vertical**:
- Length: λ/4
- Ground plane (radials or earth) provides other half
- Impedance: 36 ohms
- Omnidirectional

**Loop Antenna**:
- Circular or rectangular loop
- Circumference ≈ λ
- Directional (null off sides of loop)
- Good for direction finding

**Yagi Antenna** (Directional, High Gain):
- One driven element (dipole)
- One reflector behind (slightly longer)
- Multiple directors in front (slightly shorter)
- Highly directional
- Gain: 6-15 dBi
- Used for TV, point-to-point links

**Matching and Feedline**:
- Antenna impedance must match transmitter (usually 50 or 75 ohms)
- Feedline: Coaxial cable (salvage from TV/cable installations)
- Antenna tuner: Matches impedance if needed

### Antenna Tuner (ATU) Construction

An antenna tuner matches antenna impedance to transmitter impedance, maximizing power transfer and minimizing reflected power. Essential for multi-band operation and non-resonant antennas.

**Why Antenna Matching Matters**:

**Impedance Mismatch Problems**:
- **Reflected power**: Power bounces back to transmitter instead of radiating
- **Transmitter damage**: High SWR can destroy tube plates or transistor finals
- **Reduced range**: Less power radiated = weaker signal
- **Feedline loss**: High SWR increases loss in coax cable

**Goal**: Match antenna impedance (anywhere from 10Ω to 1000Ω) to transmitter output (typically 50Ω)

**SWR (Standing Wave Ratio)**:
- **Definition**: Ratio of maximum voltage to minimum voltage on feedline
- **Formula**: SWR = Z_antenna / Z_transmitter (if Z_antenna > Z_transmitter) or inverse
- **Ideal**: SWR = 1:1 (perfect match)
- **Acceptable**: SWR < 2:1 (most transmitters tolerate this)
- **Marginal**: SWR 2:1 to 3:1 (some power loss, transmitter may reduce output)
- **Bad**: SWR > 3:1 (significant loss, potential transmitter damage)

**Measuring SWR** (Simple Method):

**SWR Bridge** (Build from resistors):
```
Transmitter ---[50Ω]--- Antenna
       |         |
    [Forward] [Reflected]
    Detector  Detector
       |         |
     Meter    Meter
```

**Construction**:
1. **Resistive bridge**: Four 100Ω resistors in bridge configuration
2. **RF detectors**: Germanium or Schottky diodes (salvage from old radios)
3. **Meters**: Microammeters (0-100 µA or 0-1 mA)
4. **Calibration**: Adjust for full scale with matched load (50Ω resistor)

**Procedure**:
1. Connect transmitter, SWR meter, antenna in series
2. Transmit low power
3. Read forward power (should be high)
4. Read reflected power (should be low)
5. Calculate SWR = (Fwd + Refl) / (Fwd - Refl)
6. Adjust antenna tuner until SWR minimized

**ATU Network Types**:

**L-Network** (Simplest, Two Components):

**Low-Z to High-Z** (e.g., 50Ω to 200Ω):
```
Transmitter --- [Series L] --- Antenna
      (50Ω)         |          (200Ω)
                 [Shunt C]
                    |
                   GND
```

**High-Z to Low-Z** (e.g., 200Ω to 50Ω):
```
Transmitter --- [Series C] --- Antenna
      (50Ω)         |          (20Ω)
                 [Shunt L]
                    |
                   GND
```

**Advantages**:
- Simple (only 2 components)
- Compact
- Low loss

**Disadvantages**:
- Fixed Q (can't adjust bandwidth)
- Limited matching range
- Configuration changes depending on whether matching up or down

**Design Example** (50Ω to 200Ω at 7 MHz):
- **Q needed**: Q = √[(Z_high / Z_low) - 1] = √[(200 / 50) - 1] = √3 ≈ 1.73
- **X_L**: X_L = Q × Z_low = 1.73 × 50 = 86.5Ω
  - L = X_L / (2πf) = 86.5 / (2π × 7×10⁶) ≈ 2.0 μH
- **X_C**: X_C = Z_high / Q = 200 / 1.73 = 115.6Ω
  - C = 1 / (2πf × X_C) = 1 / (2π × 7×10⁶ × 115.6) ≈ 197 pF

**T-Network** (Three Components, More Flexible):

```
Transmitter ---[Series C1]---[Series C2]--- Antenna
      (50Ω)                       |          (Variable)
                              [Shunt L]
                                  |
                                 GND
```

**Configuration**:
- **Input capacitor (C1)**: Tunes input to 50Ω
- **Output capacitor (C2)**: Tunes output to antenna impedance
- **Shunt inductor (L)**: Provides reactance cancellation

**Advantages**:
- Wide matching range (10Ω to 1000Ω)
- Adjustable Q (can set bandwidth)
- Single configuration works for most cases

**Disadvantages**:
- More complex (3 adjustments)
- Larger size
- Interaction between controls (tuning affects each other)

**Practical Construction** (HF Bands, 3.5-30 MHz):
- **C1 (input)**: 0-500 pF variable capacitor
- **C2 (output)**: 0-500 pF variable capacitor
- **L (shunt)**: Roller inductor or switched inductors (5-30 μH range)
  - 7 MHz: ~10 μH
  - 14 MHz: ~5 μH
  - 28 MHz: ~2.5 μH

**Pi-Network** (Most Popular for Transmitters):

```
Transmitter ---[Shunt C1]---[Series L]---[Shunt C2]--- Antenna
      (50Ω)        |                         |         (Variable)
                  GND                       GND
```

**Configuration**:
- **Input capacitor (C1)**: Matches transmitter impedance
- **Series inductor (L)**: Provides inductive reactance
- **Output capacitor (C2)**: Matches antenna impedance

**Advantages**:
- Excellent harmonic attenuation (acts as low-pass filter)
- High power handling (components less stressed)
- Wide matching range
- Smooth, predictable tuning

**Disadvantages**:
- Large size (especially inductor for low bands)
- Expensive components (high-voltage capacitors for transmitters)
- 3 adjustments (can be complex for beginners)

**Design Example** (1000W transmitter, 50Ω to 50Ω, 7 MHz, Q=10):
- **X_C1**: X_C1 = Z_in / Q = 50 / 10 = 5Ω
  - C1 = 1 / (2πf × 5) ≈ 4545 pF (use 0-5000 pF variable, high voltage)
- **X_L**: X_L = Q × Z_in = 10 × 50 = 500Ω
  - L = 500 / (2π × 7×10⁶) ≈ 11.4 μH
- **X_C2**: Same as X_C1 if output is also 50Ω
  - C2 ≈ 4545 pF (0-5000 pF variable)

**For Mismatched Load** (e.g., antenna = 200Ω):
- C1 remains same (matches transmitter side)
- C2 adjusted: X_C2 = Z_antenna / Q = 200 / 10 = 20Ω
  - C2 = 1 / (2π × 7×10⁶ × 20) ≈ 1136 pF

**Component Selection for ATU**:

**Capacitors** (High Current, High Voltage):
- **Receive-only ATU**: Standard variable capacitors (0-500 pF, 500V) acceptable
- **QRP transmitter** (<10W): 500-1000V rating
- **Medium power** (10-100W): 1000-2000V rating
- **High power** (100-1500W): 2500-5000V rating, transmitting-type air variables
- **Construction**: Multi-plate air variables (see crystal radio section), widely spaced for voltage
- **Salvage sources**: Old tube-type transmitters, antenna tuners, RF test equipment

**Inductors** (High Current, Low Loss):
- **Wire gauge**: Heavy enough to handle current without excessive heating
  - 10W: 18 AWG acceptable
  - 100W: 12-14 AWG recommended
  - 1000W: 8-10 AWG required
- **Roller inductor** (best, expensive): Sliding contact varies tap position
  - Continuous tuning (no steps)
  - Salvage from military transmitters, old antenna tuners
- **Switched inductor** (good compromise): Rotary switch selects taps
  - ~10-20 switched positions adequate for HF bands
  - Use ceramic switch (high voltage)
- **Plug-in coils** (simple, tedious): Different coils for different bands
  - One coil per band (80m, 40m, 20m, etc.)
  - Cheap to build, slow to change bands

**Coil Forms**:
- **Air core** (best for high power): No core losses, no saturation
  - Wind on plastic or phenolic tube, remove tube (self-supporting coil)
- **Powdered iron toroid** (compact, lower power): T200 or T300 series
  - Good for QRP (<10W), avoid for high power (core saturates)

**Practical ATU Construction** (100W, Multi-Band HF):

**Simple Pi-Network ATU**:

1. **Input capacitor (C1)**:
   - 0-500 pF air variable (salvage from old tube radio)
   - Mount on front panel with shaft/knob

2. **Series inductor (L)**:
   - **Option A (Roller)**: Salvage roller inductor (5-30 μH range)
   - **Option B (Switched)**: Wind coil with taps
     - Form: 5 cm diameter, 15 cm long
     - Wire: 12 AWG enameled
     - Turns: 50-60 total, tap every 5-10 turns
     - Switch: Ceramic rotary, 1 pole 12 position
   - **Option C (Plug-in)**: Separate coils per band
     - 80m: 30 μH (~50 turns on 5 cm form)
     - 40m: 15 μH (~35 turns)
     - 20m: 7 μH (~25 turns)
     - 10m: 3 μH (~15 turns)

3. **Output capacitor (C2)**:
   - Same as C1 (0-500 pF air variable)
   - Mount on front panel with shaft/knob

4. **Enclosure**:
   - Metal box (aluminum or steel) for shielding
   - SO-239 connectors: Input (from transmitter), output (to antenna)
   - Ground all capacitor frames to enclosure

5. **Layout**:
   - Keep input and output separated (prevent coupling)
   - Short, heavy leads between components (minimize loss)
   - Inductor in center, capacitors on sides

**Tuning Procedure** (Pi-Network ATU):

1. **Initial setup**:
   - Set both capacitors to ~50% meshed
   - Set inductor to middle of range

2. **Connect**:
   - Transmitter → ATU input
   - ATU output → SWR meter → Antenna

3. **Transmit low power** (1-5W if possible):

4. **Tune C1 (input)**:
   - Adjust for minimum reflected power on SWR meter
   - Or adjust for maximum forward power

5. **Tune C2 (output)**:
   - Adjust for minimum SWR

6. **Re-tune C1**:
   - Re-adjust (controls interact)

7. **Alternate between C1 and C2**:
   - Repeat until SWR < 1.5:1

8. **Adjust L if needed**:
   - If cannot achieve low SWR, try different tap/roller position
   - General rule: Lower bands need more inductance

9. **Increase power gradually**:
   - Check SWR remains low
   - Check for arcing (crackling sounds, ozone smell)
   - Touch-test components (should be warm, not hot)

**Dummy Load** (For Testing Without Radiating):

A dummy load absorbs RF power as heat instead of radiating. Essential for transmitter testing and tuning.

**Construction** (50Ω, 100W):
- **Resistors**: Non-inductive carbon composition or metal film
  - Use multiple resistors in series/parallel to reach 50Ω
  - Example: Two 100Ω resistors in parallel = 50Ω
  - Power rating: Derate by 50% (200W resistors for 100W transmitter)
- **Mounting**: Immerse in mineral oil (transformer oil) for cooling
  - Use metal can (paint can, coffee can with lid)
  - Fill with mineral oil
  - SO-239 connector on side, resistors suspended in oil
  - Oil absorbs heat, increases power handling 5-10×

**Alternative** (High Power):
- Large oil-cooled resistor (salvage from industrial equipment)
- Commercial dummy load (often available as surplus)
- Water-cooled resistor (DIY: submerge resistor in flowing water)

**Testing Dummy Load**:
- Measure DC resistance: Should be ~50Ω
- Measure SWR with transmitter: Should be <1.2:1 across all frequencies
- Transmit into dummy load at full power for 1 minute
  - Resistors should warm up (but not smoke!)
  - Oil should warm up gradually
  - No arcing or flashover

### Feedline Construction

Feedlines carry RF power between transmitter and antenna (or antenna and receiver). Choice of feedline affects efficiency, loss, and system complexity.

**Feedline Types**:

**Coaxial Cable** (Most Common, Modern):

**Advantages**:
- Shielded (immune to interference, doesn't radiate)
- Flexible, weatherproof
- 50Ω or 75Ω impedance (standard)
- Easy to route (can run near metal objects)
- Low loss at VHF/UHF

**Disadvantages**:
- Higher loss at HF (especially cheap cable)
- Expensive if new (salvage recommended)
- Difficult to build from scratch
- Loss increases with SWR (avoid mismatches)

**Salvage Sources**:
- TV/cable installations (RG-6, 75Ω)
- CB radio/amateur radio (RG-8, RG-58, 50Ω)
- Ethernet (some types, usually poor for RF)
- Military surplus (high-quality, low-loss types)

**Common Types**:
- **RG-58** (50Ω, ~5mm diameter): Small, flexible, high loss
  - Loss at 7 MHz: ~1.5 dB/100m
  - Loss at 144 MHz: ~10 dB/100m
  - Good for: Short runs (<10m), receive-only, QRP transmit
- **RG-8** (50Ω, ~10mm diameter): Larger, stiffer, lower loss
  - Loss at 7 MHz: ~0.8 dB/100m
  - Loss at 144 MHz: ~4 dB/100m
  - Good for: Longer runs, high power, low bands
- **RG-6** (75Ω, ~6mm diameter): TV cable, widely available
  - Impedance mismatch to 50Ω systems (usable but not ideal)
  - Loss similar to RG-58
  - Good for: Salvage situations, receive-only

**Testing Coax**:
- **DC resistance**: Center to shield should be infinite (open circuit)
- **Short test**: Short far end, measure resistance from near end (should be ~0Ω)
- **Capacitance**: ~30 pF/ft for RG-58, ~20 pF/ft for RG-8
- **Water damage**: Cut end, look for corrosion or water inside

**Open-Wire Feedline** (Parallel Conductor, Lowest Loss):

**Advantages**:
- **Very low loss**: 0.1-0.3 dB/100m at HF (10× better than coax!)
- Easy to build from scratch
- Handles high SWR without excessive loss
- Inexpensive
- Works with antenna tuner for multi-band use

**Disadvantages**:
- Not shielded (picks up noise, radiates slightly)
- Must be kept away from metal objects (changes impedance)
- Harder to route (must be spaced from building, guy wires, etc.)
- Picks up static in storms
- Impedance varies with spacing (requires tuner at transmitter)

**Construction** (450Ω Open-Wire Line):

**Materials**:
- **Wire**: 14-18 AWG copper (solid or stranded)
- **Spacers**: Plastic, wood, or ceramic insulators every 15-30 cm
- **Spacing**: Determines impedance

**Impedance Formula**:
- **Z₀ = 276 × log₁₀(2D/d)**
  - D = center-to-center spacing between wires
  - d = wire diameter
- **Example**: 18 AWG wire (1mm diameter), 5cm spacing
  - Z₀ = 276 × log₁₀(2 × 50 / 1) = 276 × log₁₀(100) = 276 × 2 = 552Ω
- **Example**: 14 AWG wire (1.6mm diameter), 2cm spacing
  - Z₀ = 276 × log₁₀(2 × 20 / 1.6) = 276 × log₁₀(25) = 276 × 1.4 ≈ 387Ω

**Typical Impedances**:
- **300Ω**: TV twin-lead spacing (~1 cm for 18 AWG)
- **450Ω**: Common open-wire (2-5 cm spacing)
- **600Ω**: Wide-spaced (5-10 cm spacing)

**Spacer Construction**:

**Option 1: Plastic Spreaders** (Simple):
- Cut strips from HDPE or acrylic sheet (~2mm thick, 5cm long)
- Drill holes at each end for wires
- Thread wires through holes
- Space spreaders every 20-30 cm

**Option 2: Drilled Insulators** (Stronger):
- Use ceramic or phenolic rod (~1cm diameter, 5-10cm long)
- Drill holes at each end
- Thread wires, tie in place with knots
- Space every 30 cm

**Option 3: X-Spreaders** (Traditional):
- Cross two strips in X pattern
- Notch intersections so they lock together
- Drill holes in ends for wires
- Lightweight, keeps wires spaced

**Assembly**:
1. Cut two wires to length (antenna height + horizontal run + extra)
2. Starting at one end, install spacers at regular intervals
3. Keep wires parallel and tension even
4. Seal ends (prevent water entry): Knot wires, dip in wax or liquid tape

**Installation**:
- Run parallel to ground (not perpendicular to metal objects)
- Keep >30 cm from metal, >15 cm from wood/brick
- Support with insulators (don't let wire touch anything conductive)
- Bring into shack through window or wall insulator
- Connect to antenna tuner (not directly to transmitter)

**Twin-Lead** (Balanced, 300Ω):

TV-type flat twin-lead is widely salvageable and usable for radio feedlines.

**Advantages**:
- Widely available (salvage from old TV antennas)
- 300Ω impedance (can be matched with tuner)
- Flexible, easy to install
- Lower loss than coax at HF
- Cheap or free

**Disadvantages**:
- Not as low-loss as open-wire
- Deteriorates in weather (UV damage)
- Impedance changes when wet
- Must be kept away from metal
- Limited power handling (~100-200W)

**Types**:
- **Tubular/air-dielectric** (best): Wires embedded in foam or plastic web
  - Lower loss (air is lossless dielectric)
  - More weatherproof
- **Flat solid** (common): Wires embedded in solid polyethylene
  - Higher loss (dielectric absorbs RF)
  - Deteriorates faster

**Use Cases**:
- Receive-only antennas (excellent for this)
- Low-power transmit (<100W)
- Temporary installations
- When coax and open-wire not available

**Installation Tips**:
- Twist 180° every 2-3 meters (helps cancel interference pickup)
- Keep away from metal gutters, downspouts, wiring
- Use standoffs to space from walls
- Replace every 5-10 years (UV damage)

**Baluns** (Balanced-to-Unbalanced Transformers):

Antennas like dipoles are balanced (symmetric). Coax is unbalanced (shield at ground). Baluns connect them properly.

**Why Baluns Matter**:
- Without balun: Coax shield carries RF current (radiates, causes interference)
- With balun: Forces current to flow only on center conductor and inside shield
- Result: Better pattern, less noise pickup, reduced feedline radiation

**1:1 Current Balun** (Simple, Effective):

**Coil of Coax Method**:
- Coil 8-10 turns of coax (15-20 cm diameter) at antenna feedpoint
- Coil acts as choke (high impedance to common-mode current)
- Prevents shield from radiating
- No impedance transformation (50Ω coax → 50Ω balanced)

**Ferrite Bead Method**:
- Thread coax through ferrite toroid cores (10-20 cores)
- Cores increase impedance of shield current
- Compact, effective
- Salvage toroids from old computer equipment, power supplies

**4:1 Balun** (Impedance Transformation):

Matches 200Ω balanced antenna (like folded dipole) to 50Ω unbalanced coax.

**Transmission Line Transformer**:
- Wind bifilar (two parallel wires) on ferrite core
- 10-15 turns on FT240-43 or FT240-61 core
- Connections arranged for 4:1 ratio
- Effective 1-30 MHz

**Salvage**:
- Baluns from old ham radio equipment
- TV baluns (300Ω to 75Ω = 4:1 ratio, usable for HF)

**Feedline Comparison Table**:

| Type | Impedance | Loss (7 MHz) | Loss (144 MHz) | Cost | Build Difficulty | Weather Resistance |
|------|-----------|--------------|----------------|------|------------------|--------------------|
| **Open-wire** | 450-600Ω | 0.1-0.3 dB/100m | 0.5-1 dB/100m | Low | Easy | Good (if built well) |
| **Twin-lead** | 300Ω | 0.5-1 dB/100m | 3-5 dB/100m | Low (salvage) | Very easy | Fair (degrades in 5-10 yrs) |
| **RG-58** | 50Ω | 1.5 dB/100m | 10 dB/100m | Medium | Hard to build | Excellent |
| **RG-8** | 50Ω | 0.8 dB/100m | 4 dB/100m | Medium-High | Hard to build | Excellent |
| **Hardline** | 50Ω | 0.2 dB/100m | 1 dB/100m | High | Very hard | Excellent |

**Recommendation by Use Case**:

- **HF transmit, multi-band**: Open-wire + antenna tuner (lowest loss, handles SWR)
- **VHF/UHF**: Coax (RG-8 or better) (shielding critical, short runs minimize loss)
- **HF single-band, resonant antenna**: Coax (RG-8) (low SWR, no tuner needed)
- **Receive-only**: Twin-lead or any salvaged coax (loss not critical for RX)
- **Portable/temporary**: Twin-lead (light, flexible, easy to deploy)
- **High power (>500W)**: Open-wire or hardline coax (handles power without overheating)

**Height**: Higher is better
- Above obstacles
- Ground effects reduced
- VHF/UHF: Line-of-sight, so height critical

### Propagation

**Ground Wave**:
- Follows earth's surface
- Absorption depends on frequency and terrain
- MF/LF can travel 100+ km over land, much farther over seawater

**Sky Wave** (Ionospheric Reflection):
- HF (3-30 MHz) reflects off ionosphere
- Daytime: Higher frequencies work best
- Nighttime: Lower frequencies penetrate less, reflect more
- Skip distance: No reception in area between ground wave and sky wave
- Worldwide communication possible with right frequency and time

**Line of Sight**:
- VHF/UHF mostly line-of-sight
- Distance ≈ 4.12 × (√h1 + √h2) km, where h in meters
- Example: 10m antenna to 10m antenna = 4.12 × (√10 + √10) = 26 km

**Diffraction and Reflection**:
- Radio waves bend around obstacles (more at lower frequencies)
- Reflect off buildings, hills, ionosphere

## Practical Communication Systems

### Radio Frequency Allocation for Post-Collapse Use

Without regulatory bodies, communities must self-coordinate. These frequency ranges offer the best practical characteristics for different applications:

| Frequency Range | Primary Use | Propagation | Antenna Size | Notes |
|-----------------|-------------|-------------|--------------|-------|
| **500-1600 kHz** | AM Broadcasting | Wide area, ground wave | Large (100-300m) | Good for news/information distribution, works day and night |
| **1.8-2.0 MHz** | Local/Regional HF | Ground wave + night skip | Medium (40-80m) | Excellent night propagation, "160 meter band" |
| **3.5-4.0 MHz** | Regional HF | Day and night, reliable | Medium (20-40m) | Good all-around, "80 meter band", works in all conditions |
| **7.0-7.3 MHz** | Medium Distance HF | 200-1000 km typical | Medium (10-20m) | "40 meter band", best all-around HF frequency |
| **14.0-14.35 MHz** | Long Distance HF | Worldwide daytime | Small (10m) | "20 meter band", daytime DX, solar cycle dependent |
| **21.0-21.45 MHz** | Long Distance HF | Worldwide, good sun | Small (7m) | "15 meter band", requires solar activity |
| **28-30 MHz** | Long Distance HF | Worldwide, peak sun | Small (5m) | "10 meter band", best during solar maximum, dead at solar minimum |
| **50-54 MHz** | Regional VHF | Line-of-sight + skip | Small (3m) | "6 meter band", occasional long-distance openings |
| **144-148 MHz** | Local VHF | Line-of-sight only | Very small (1m) | "2 meter band", FM voice, repeaters, most popular VHF |
| **420-450 MHz** | Local UHF | Line-of-sight | Tiny (35cm) | "70 cm band", short range, good for portable/mobile |

**Bandwidth Allocations Within Each Band:**
- **CW (Morse code)**: Lower portion of each band (most efficient, narrowest bandwidth)
- **Phone (Voice)**: Upper portion of each band (SSB for HF, FM for VHF/UHF)
- **Digital modes**: Scattered throughout (packet radio, RTTY, etc.)
- **Emergency frequencies**: Designated specific frequencies for distress calls

**SSB Sideband Conventions** (Critical for Compatibility):
- **Below 10 MHz**: Lower Sideband (LSB) is standard
  - 1.8 MHz, 3.5 MHz, 7 MHz: Use LSB
- **Above 10 MHz**: Upper Sideband (USB) is standard
  - 14 MHz, 21 MHz, 28 MHz, 50 MHz: Use USB
- **Why this matters**: If everyone uses the same convention, communication is possible without confusion

**Recommended Emergency Frequencies** (Post-Collapse Coordination):
- **7.200 MHz**: Primary HF emergency frequency (day/night, reliable)
- **14.300 MHz**: Secondary HF emergency (daytime, long distance)
- **146.52 MHz**: VHF simplex calling/emergency (FM, local)
- **3.750 MHz**: Night emergency frequency (80m, good coverage)

**Time-Based Schedules** (If Continuous Monitoring Not Possible):
- **Morning net**: 0800 local time on 7.200 MHz (check-ins, message traffic)
- **Evening net**: 1900 local time on 3.750 MHz (regional coordination)
- **Emergency**: Monitor 7.200 MHz continuously (if possible)

**Frequency Selection Criteria:**

**For 24/7 Reliability**: 7 MHz (40m) and 3.5 MHz (80m)
- Work day and night
- Not too dependent on solar activity
- Medium antenna size (manageable)

**For Maximum Range**: 14 MHz (20m) daytime, 7 MHz (40m) nighttime
- 14 MHz can reach worldwide during day
- 7 MHz provides night coverage

**For Local Coordination**: 144-148 MHz (2m VHF FM)
- Simple equipment
- Line-of-sight propagation (predictable)
- Small antennas
- Good for repeater networks

**Solar Cycle Considerations**:
- **Solar Maximum** (~11 year cycle): Higher frequencies (14-28 MHz) work well
- **Solar Minimum**: Stick to lower frequencies (3.5-7 MHz), high bands may be dead
- **Post-collapse**: May not know where in solar cycle you are—test all bands

### Local Network (Within 50 km)

**Technology**: VHF FM transceivers
- Frequency: 30-50 MHz (propagate well, reasonable antenna size)
- Power: 5-25W
- Antenna: Vertical, mounted high
- Range: 20-50 km depending on terrain

**Base Stations**:
- High location (hilltop, tall building)
- Good antenna
- Power supply (solar, hydro, or grid)
- Can relay messages

**Mobile/Portable Units**:
- Lower power (1-5W)
- Smaller antenna
- Battery powered
- Range to base station: 10-30 km

**Organization**:
- Assigned frequencies (avoid interference)
- Call signs (identify stations)
- Protocols (who speaks when, message format)
- Schedule (listening times if not continuous)

### Regional Network (50-500 km)

**Technology**: HF SSB (Single Sideband) transceivers
- Frequency: 3-10 MHz (good day and night)
- Power: 25-100W
- Antenna: Dipole or vertical, 10-30m high
- Range: 100-500 km ground wave and near skip

**Propagation**: Mostly ground wave during day, some ionospheric skip at night

### Long Distance (500+ km, Worldwide)

**Technology**: HF SSB, higher power
- Frequency: 5-25 MHz (varies by time of day, season, sunspot cycle)
- Power: 100-1,000W
- Antenna: Beam antenna (Yagi) for directionality, or large dipole
- Range: Worldwide with ionospheric propagation

**Frequency Selection**:
- Day: 15-25 MHz
- Night: 3-10 MHz
- Transition: 10-15 MHz

**Solar Activity**: More sunspots = better HF propagation

### Emergency Communication

**Distress Frequencies**:
- 500 kHz (historical maritime)
- 2182 kHz (maritime MF)
- 121.5 MHz (aviation emergency)
- Designate specific frequencies post-collapse

**Signals**:
- SOS in Morse code
- Voice: "Mayday, mayday, mayday" (immediate distress)
- Voice: "Pan-pan, pan-pan, pan-pan" (urgent, not distress)

**Equipment**:
- Portable transceiver (HF or VHF)
- Battery or hand-crank powered
- Simple antenna (wire dipole)

### Broadcasting

**AM Broadcasting**:
- MF band (500-1,600 kHz)
- Large audience (cheap receivers)
- Range: 50-100 km day, 500+ km night

**FM Broadcasting**:
- VHF (88-108 MHz)
- Better sound quality
- Range: 30-100 km (line of sight)

**Content**:
- News, information
- Education
- Entertainment (music, stories)
- Community coordination

**Transmitter Power**:
- Low power (10-100W): Local coverage
- High power (1-10 kW): Regional coverage

### Repeater Station Design

Repeaters extend communication range by receiving weak signals and retransmitting them at higher power. Critical for VHF/UHF networks and linking communities across difficult terrain.

**Basic Repeater Principle**:
1. **Receive** signal on one frequency (input frequency)
2. **Retransmit** simultaneously on another frequency (output frequency)
3. **Users** transmit on input, listen on output
4. **Result**: Extended range (repeater on hilltop reaches what handhelds cannot)

**Frequency Separation** (Prevents Feedback):

**VHF (2 meters, 144-148 MHz)**:
- **Input**: 146.000 MHz (example)
- **Output**: 146.600 MHz (example)
- **Offset**: +600 kHz standard
- **Why**: Receiver and transmitter run simultaneously, must not interfere

**UHF (70 cm, 420-450 MHz)**:
- **Offset**: +5 MHz typical
- **Example**: Input 145.000 MHz, output 440.000 MHz

**HF Repeaters** (Rare, Complex):
- Different band for input/output (e.g., receive 40m, transmit 80m)
- Or time-division (receive, then transmit, not simultaneous)

**Repeater Components**:

**1. Receiver**:
- Sensitive VHF/UHF receiver (FM typically)
- Squelch circuit (mute when no signal present)
- Audio output connects to transmitter audio input

**2. Transmitter**:
- VHF/UHF FM transmitter
- Keyed by receiver squelch (transmit when receiving signal)
- Power: 10-50W typical for local repeater, 100-500W for wide-area

**3. Duplexer or Dual Antennas**:

**Duplexer** (One Antenna, Simultaneous TX/RX):
- Bandpass filters isolate receiver from transmitter
- **Transmit filter**: Passes output frequency, blocks input frequency (protects transmitter from receiver)
- **Receive filter**: Passes input frequency, blocks output frequency (protects receiver from transmitter)
- **Isolation**: >80 dB required (otherwise transmitter desensitizes receiver)
- **Complex**: Cavity filters (resonant metal cavities, high Q)
- **Salvage**: Commercial repeaters, cell tower equipment, military

**Dual Antennas** (Simpler, Cheaper):
- Separate antennas for transmit and receive
- **Spacing**: >20 wavelengths apart (reduces coupling)
  - VHF (2m): 20 × 2m = 40m spacing
  - UHF (70cm): 20 × 0.7m = 14m spacing
- **Isolation**: Physical separation provides 40-60 dB isolation
- **Easier to build**, but requires more space and two feedlines

**4. Controller**:
- Times out transmitter (prevent stuck-key tying up repeater)
- Sends ID (Morse code or voice, identifies repeater)
- Tail beep (short tone after user stops transmitting, confirms repeater listening)
- Optional: Autopatch (connects repeater to telephone system)

**Simple Repeater Controller** (Tube/Transistor):
- **Timer**: RC network or 555 timer (3-minute timeout typical)
- **ID generator**: Audio oscillator + keyed tone or Morse code
- **Tail beep**: 1-second delay circuit, triggers short tone
- **Logic**: Transistor/relay switching for TX enable, ID timing

**Practical VHF Repeater Construction** (2 Meters, 146 MHz):

**Receiver**:
- Superheterodyne FM receiver (10.7 MHz IF)
- Input frequency: 146.000 MHz (example, coordinate with users)
- Squelch: Threshold set to open only on valid signals (blocks noise)
- Audio output: 1-5V peak-to-peak to transmitter

**Transmitter**:
- VHF FM transmitter, narrowband (±5 kHz deviation)
- Output frequency: 146.600 MHz (+600 kHz from input)
- Power: 25-50W (covers 30-80 km from hilltop)
- Modulation: Audio from receiver triggers transmitter

**Duplexer** (If Using One Antenna):
- Two cavity filters (one for TX, one for RX)
- **Cavity**: Metal cylinder or box, resonant at specific frequency
- **Dimensions**: ~1/2 wavelength at operating frequency
  - 146 MHz: λ = 300/146 ≈ 2.05m, cavity ~1m tall
- **Tuning**: Adjustable probe or slug changes resonance
- **Q factor**: >1000 (very high Q for sharp filtering)
- **Salvage**: Commercial repeater duplexers (often marked with frequencies)

**Repeater Antenna Placement**:
- **Height**: As high as possible (hilltop, tall building, tower)
- **Line of sight**: VHF/UHF mostly line-of-sight
- **Coverage**: Approximately 4.12 × √h km radius (h = height in meters)
  - Example: 100m antenna height → 4.12 × √100 = 41 km radius
- **Clearance**: Above tree line, buildings, obstructions

**Repeater Power**:
- **Solar + battery**: Sustainable, remote sites
  - 50W transmitter (10% duty cycle) ≈ 5W average
  - 100W solar panel + 100Ah battery suitable for remote site
- **Grid power** (if available): Simpler, more reliable if grid stable
- **Backup battery**: Essential (repeater often used in emergencies)

**Repeater Operation**:

**User Side** (Accessing Repeater):
1. Set radio to **output frequency** (146.600 MHz) for listening
2. Set transmit offset to **-600 kHz** (transmit on 146.000 MHz)
3. Enable tone squelch (CTCSS) if repeater uses it (prevents interference)
4. Press PTT (push to talk), speak normally
5. Release PTT, hear own transmission retransmitted 1-2 seconds later

**Repeater Side** (Automatic Operation):
1. Receiver monitors input frequency (146.000 MHz)
2. When signal detected: Squelch opens, audio fed to transmitter
3. Transmitter keys on output frequency (146.600 MHz)
4. Retransmits audio with slight delay (few milliseconds)
5. When user releases PTT: Repeater waits 1-2 seconds (hang time), then sends tail beep and drops
6. Every 10 minutes (or as required): Sends ID in Morse or voice

**CTCSS (Continuous Tone-Coded Squelch System)** (Optional but Recommended):
- **Subaudible tone** (67-250 Hz) sent with voice
- **Repeater**: Only responds to signals with correct tone
- **Benefit**: Blocks interference from distant repeaters on same frequency
- **Implementation**: Add tone generator to transmitter, tone decoder to repeater receiver

**Linking Repeaters** (Wide-Area Network):

**Problem**: Single repeater covers ~50 km. How to link distant communities?

**Solution**: Link multiple repeaters via radio or wired connection.

**Method 1: RF Link** (Radio-to-Radio):
- Repeater A transmits on linking frequency
- Repeater B receives linking frequency, retransmits locally
- **Frequencies**: Use separate band for linking (e.g., UHF link between VHF repeaters)
- **Directional antennas**: Point antennas at each other (Yagi or dish)
- **Range**: 100+ km with good line-of-sight and directional antennas

**Method 2: Wired Link** (If Infrastructure Exists):
- Audio connection via phone line, fiber, or dedicated wire
- Simpler, more reliable
- Requires wired infrastructure (may not exist post-collapse)

**Repeater Example Network** (Regional Communication):

**Scenario**: Three communities, 60 km apart

**Community A**:
- Repeater on hilltop (input 146.00, output 146.60)
- Covers Community A and halfway to B

**Community B**:
- Repeater on hilltop (input 146.20, output 146.80)
- Covers Community B and halfway to A and C
- **Linked to A**: UHF link (440 MHz) with directional antennas

**Community C**:
- Repeater on hilltop (input 146.40, output 147.00)
- Covers Community C and halfway to B
- **Linked to B**: UHF link (445 MHz)

**Result**: User in Community A can talk to user in Community C via repeater network (A → B → C)

**Repeater Maintenance**:
- Check transmitter power output (monthly)
- Inspect antennas and feedlines (quarterly)
- Test backup power (monthly)
- Clean filters and cavities (annually)
- Monitor for interference (ongoing)

### Emergency Communication Protocols

Organized protocols ensure emergency traffic gets through quickly and clearly. Essential for post-collapse coordination.

**Priority Levels**:

**1. EMERGENCY (Highest)**:
- **Immediate threat to life**
- Medical emergency, fire, injury, attack
- **All other traffic stops**
- **Example**: "Break break break, emergency traffic, Community A has injured person, need medical advice"

**2. PRIORITY**:
- **Urgent but not life-threatening**
- Resource shortages, equipment failures, security concerns
- **Interrupts routine traffic**
- **Example**: "Priority traffic, Community B reports water pump failure, request assistance"

**3. HEALTH & WELFARE**:
- **Personal well-being messages**
- Checking on family members, confirming safety
- **After emergency and priority cleared**
- **Example**: "Health and welfare traffic, is John Smith from Community C available?"

**4. ROUTINE**:
- **Normal traffic**
- Coordination, logistics, social communication
- **Lowest priority**

**Distress Call Procedure** (Life-Threatening):

**Voice** (FM/SSB):
```
"Mayday, mayday, mayday"
"This is [Your Callsign or Name] at [Location]"
"We have [Nature of Emergency]"
"We need [Assistance Required]"
"We are [Number of People]"
"Over"
```

**Example**:
```
"Mayday, mayday, mayday"
"This is Community A repeater, located at Miller Hill"
"We have severe fire threatening grain storage"
"We need firefighting equipment and personnel"
"We have 50 people evacuating"
"Over"
```

**Morse Code** (CW):
```
SOS SOS SOS DE [Your Callsign]
[Location] [Emergency] K
```

**All Stations Hearing Mayday**:
- **Stop transmitting immediately** (clear frequency for emergency)
- **Listen** for instructions from control station
- **Assist** if able (relay messages, provide resources)
- **Do not interfere** unless you can directly help

**Emergency Net Control**:

**Purpose**: Organize and direct emergency traffic

**Net Control Station** (NCS):
- **Coordinates all traffic** during emergency
- **Assigns frequencies** if needed
- **Prioritizes messages**
- **Logs all traffic**
- **Provides updates** to all stations

**Procedure**:
1. **Mayday heard**: NCS takes control
2. **Acknowledge emergency**: "All stations, this is [NCS], emergency traffic in progress, stand by"
3. **Gather information**: Ask distressed station for details
4. **Assign tasks**: "Station B, relay to Community C"; "Station D, prepare medical team"
5. **Update**: Periodic updates to all stations on situation
6. **Clear**: When emergency resolved: "All stations, emergency traffic concluded, return to normal operations"

**Scheduled Nets** (Regular Check-Ins):

**Morning Net** (Daily, 0800 local):
- **Frequency**: 7.200 MHz LSB (or designated frequency)
- **Purpose**: Daily check-in, message traffic, coordination
- **Procedure**:
  1. NCS calls: "Good morning, this is morning net, all stations check in"
  2. Stations respond in order (alphabetical or geographic)
  3. Each station reports status, any traffic
  4. Net handles message traffic (deliveries, requests)
  5. Net closes: "No further traffic, net closed, return to normal operations"

**Evening Net** (Daily, 1900 local):
- Similar to morning net
- Focuses on next day's plans, resource needs

**Emergency Preparedness Net** (Weekly):
- Test emergency procedures
- Practice distress calls and responses
- Update emergency plans
- Verify equipment functionality

**Standard Prowords** (Voice Procedure):

| Proword | Meaning |
|---------|---------|
| **Over** | Transmission ended, expecting reply |
| **Out** | Transmission ended, no reply expected |
| **Break** | Separating parts of message |
| **Break break break** | Emergency interruption |
| **Roger** | Message received and understood |
| **Wilco** | Will comply (I will do what you requested) |
| **Say again** | Repeat your last transmission |
| **Spell** | I will spell the next word phonetically |
| **Correction** | I made an error, the correct version is... |
| **Wait** | Pause, I will call you back shortly |
| **Stand by** | Longer wait, several minutes |

**Phonetic Alphabet** (Clear Letter Transmission):

| Letter | Phonetic | Letter | Phonetic |
|--------|----------|--------|----------|
| A | Alpha | N | November |
| B | Bravo | O | Oscar |
| C | Charlie | P | Papa |
| D | Delta | Q | Quebec |
| E | Echo | R | Romeo |
| F | Foxtrot | S | Sierra |
| G | Golf | T | Tango |
| H | Hotel | U | Uniform |
| I | India | V | Victor |
| J | Juliett | W | Whiskey |
| K | Kilo | X | X-ray |
| L | Lima | Y | Yankee |
| M | Mike | Z | Zulu |

**Example Usage**:
- Name "Smith" → "Sierra Mike India Tango Hotel"
- Location "Hilltop 5" → "Hotel India Lima Lima Tango Oscar Papa Fiver"

**Emergency Message Format** (Written Log):

```
FROM: [Originating Station]
TO: [Destination Station]
DATE/TIME: [When sent]
PRIORITY: [Emergency/Priority/Routine]
MESSAGE: [Content]
RELAYED BY: [Intermediate stations]
```

**Emergency Frequencies** (Post-Collapse Recommended):

**Primary**:
- **7.200 MHz LSB**: HF emergency (day/night, reliable, regional/worldwide)
- **146.52 MHz FM**: VHF simplex (local, line-of-sight, 50 km typical)

**Secondary**:
- **3.750 MHz LSB**: Night HF (regional coverage, 80m band)
- **14.300 MHz USB**: Daytime HF (long-distance, 20m band, solar-dependent)

**Monitoring Schedule**:
- **24/7 monitoring**: Ideal but resource-intensive (requires staffing/power)
- **Scheduled checks**: 0800, 1200, 1900 local (reasonable compromise)
- **Emergency activation**: All stations monitor when emergency declared

**Practice and Drills**:
- **Monthly drill**: Simulate emergency (fire, injury, attack scenario)
- **Test all equipment**: Verify transmitters, receivers, antennas functional
- **Rotate net control**: Train multiple operators (redundancy critical)
- **Message relay**: Practice passing messages through multiple stations

**Emergency Go-Bag** (Portable Station):

**Contents**:
- HF/VHF portable transceiver (5-100W)
- Battery (12V, 7-20 Ah) or hand-crank power
- Wire antenna (dipole, 10-40m wire)
- Headphones (save battery vs. speaker)
- Paper log book and pen
- Frequency list and protocols
- Spare batteries/power source
- Flashlight

**Deployment**:
- Can set up in 15 minutes
- Operate from any location (hilltop, vehicle, shelter)
- Battery provides 2-8 hours operation (depending on power/usage)

## First Radio to Build: Learning Progression

Don't start with a complex transceiver. Build skills progressively.

**1. Crystal Radio (Receive AM Broadcast)** - **Start here**
- **Time**: 1-2 days
- **Complexity**: Easiest (no power source!)
- **What you learn**: Tuning, resonance, antenna basics
- **Components**: Coil, variable capacitor, diode, headphones
- **Capabilities**: Receive local AM broadcast stations (if any exist)
- **Limitations**: No amplification, weak signal, headphones only
- **Why first**: Proves radio works, builds confidence, requires minimal components

**2. One-Tube Regenerative Receiver (Better Sensitivity)** - **Second project**
- **Time**: 1 week
- **Complexity**: Moderate
- **What you learn**: Vacuum tube operation, feedback, oscillation control
- **Components**: One triode tube, coil, capacitors, resistors, headphones, battery/power supply
- **Capabilities**:
  - Much more sensitive than crystal radio
  - Can receive distant stations
  - Adjustable regeneration (positive feedback) increases sensitivity
- **Limitations**: Tricky to tune (can oscillate), no loudspeaker (unless you add audio amp)
- **Why second**: Introduces active amplification, still relatively simple

**3. Simple CW Transmitter (Communicate Locally)** - **Third project**
- **Time**: 1-2 weeks
- **Complexity**: Moderate
- **What you learn**: Oscillator design, keying, output coupling, antenna tuning
- **Components**: Oscillator tube/transistor, tank circuit, telegraph key, power supply, antenna
- **Capabilities**:
  - Transmit Morse code
  - Range: 5-50 km (depends on power and frequency)
  - Two-way communication with other stations
- **Limitations**: Morse code only (no voice), requires license/coordination
- **Why third**: Enables actual communication, not just listening

**4. Simple AM Transmitter (Voice Communication)** - **Fourth project**
- **Time**: 2-4 weeks
- **Complexity**: Moderate-High
- **What you learn**: Modulation, audio amplification, microphone circuits
- **Components**: Oscillator, modulator, RF amplifier, microphone, audio amp, power supply
- **Capabilities**:
  - Voice communication
  - Range: 5-50 km
  - Much easier to use than CW (no Morse code needed)
- **Limitations**: Lower efficiency than CW, wider bandwidth
- **Why fourth**: Voice is more natural than Morse for most users

**5. Superheterodyne Receiver (Proper Selectivity)** - **Fifth project**
- **Time**: 4-8 weeks
- **Complexity**: High
- **What you learn**: Frequency conversion, IF amplification, multi-stage design
- **Components**: Mixer, local oscillator, IF transformers, detector, audio amp, multiple tubes/transistors
- **Capabilities**:
  - Excellent selectivity (separate closely-spaced stations)
  - Good sensitivity
  - Stable tuning
  - Loudspeaker operation
- **Limitations**: Complex, many components, alignment required
- **Why fifth**: This is the "professional" receiver design, worth the effort

**6. SSB Transceiver (Efficient HF Communication)** - **Long-term goal**
- **Time**: Months
- **Complexity**: Very High
- **What you learn**: Balanced modulators, filtering, product detection, transmit/receive switching
- **Components**: Many tubes/transistors, crystal filter, mixer stages, VFO, linear amplifier
- **Capabilities**:
  - Most efficient voice mode (2-3× range of AM for same power)
  - Industry standard for HF communication
  - Worldwide communication possible (with good propagation)
- **Limitations**: Very complex, difficult alignment, requires good test equipment
- **Why last**: This is advanced, but becomes the workhorse for long-distance communication

**Recommended Timeline** (for community with 5-10 dedicated individuals):
- **Year 1**: Crystal radios, regenerative receivers, simple CW transmitters
- **Year 2-3**: AM transmitters/receivers, superheterodyne receivers
- **Year 3-5**: SSB transceivers, repeater stations
- **Year 5+**: Network of stations, emergency protocols, broadcasting

**Don't skip steps**. Each project teaches essential skills for the next. A failed superheterodyne receiver wastes months. A successful crystal radio builds confidence and knowledge.

## Building a Complete Radio Station

### Components Needed:

1. **Transmitter**:
   - Oscillator (crystal or VFO)
   - Modulator (for voice)
   - Power amplifier
   - Power supply

2. **Receiver**:
   - Superheterodyne design
   - Speaker and audio amp

3. **Antenna**:
   - Matched to frequency
   - As high as practical

4. **Power**:
   - AC mains (if available)
   - Battery bank with solar/wind charging
   - Generator backup

5. **Accessories**:
   - Microphone
   - Headphones
   - Telegraph key (for CW)
   - Dummy load (for testing without radiating)
   - SWR meter (measures antenna match)
   - Frequency counter (verify transmit frequency)

### Assembly and Testing:

1. **Build transmitter**: Test into dummy load first (resistor matching antenna impedance, 50-100W rating)
2. **Build receiver**: Test with signal generator or existing stations
3. **Install antenna**: Measure SWR (standing wave ratio), should be <2:1
4. **Connect and test**: Start with low power, verify communication
5. **Adjust and optimize**: Tune for best performance

### Licensing and Coordination (Pre-Collapse Concept):

In pre-collapse world, radio usage was regulated. Post-collapse:
- No authorities to license
- But coordination still important
- Agree on frequencies to avoid interference
- Establish protocols and procedures
- Document and share

## Advanced Topics

### Single Sideband (SSB)

**Principle**: AM signal has carrier and two sidebands (upper and lower)
- Sidebands contain information (mirror images)
- Carrier contains no information

**SSB Improvement**: Remove carrier and one sideband
- Transmit only one sideband
- Saves power (factor of 4-6× for same effectiveness)
- Saves bandwidth (half as wide)

**Generation**:
- Balanced modulator: Suppresses carrier
- Filter: Removes one sideband

**Reception**: Requires BFO (beat frequency oscillator) to reinsert carrier

**Advantage**: Standard for HF voice communication (more efficient than AM)

### Digital Modes

**PSK31, RTTY, etc.**:
- Encode text as audio tones
- Feed into SSB transmitter
- Very narrow bandwidth
- Computer with sound card can decode

**Advantages**:
- Weak signal communication
- Error correction
- Automated logging

**Requires**: Computer and software (may be salvaged)

### Spread Spectrum

**Frequency Hopping**: Transmitter and receiver change frequency rapidly in synchronized pattern
**Direct Sequence**: Spread signal over wide bandwidth

**Advantages**:
- Resistant to interference
- Multiple users on same band
- Harder to intercept

**Disadvantages**:
- Complex (requires precise timing)
- Inefficient use of spectrum

**Modern Application**: Cell phones, WiFi (salvaged equipment may use this)

## Troubleshooting

**Transmitter Problems**:
- **No output**: Check power, oscillator running, key closed
- **Low output**: Tubes/transistors weak, poor antenna match, low supply voltage
- **Distortion**: Overmodulation, bad components in modulator
- **Interference**: Harmonics, spurious signals (add filtering)

**Receiver Problems**:
- **No reception**: Check antenna, power, blown components
- **Weak reception**: Poor antenna, misalignment, weak stages
- **No selectivity**: IF transformers misaligned
- **Squealing**: Positive feedback, instability (shield stages, reduce gain)

**Antenna Problems**:
- **High SWR**: Wrong length, poor ground, damaged feedline
- **Low signal**: Antenna too low, obstructed, wrong polarization

## Summary: Communication Capability Stages

**Stage 1 (Year 0-2): Telegraph and Simple Radio**
- Telegraph systems using salvaged wire
- Crystal radios (receive only)
- Spark gap transmitters (emergency)
- Morse code communication

**Stage 2 (Year 2-10): Voice Radio**
- AM transmitters and receivers
- VHF FM for local communication
- HF for long distance
- Telephone systems

**Stage 3 (Year 10-30): Advanced Radio**
- SSB for efficiency
- Precision frequency control (crystal oscillators)
- High power transmitters (1-10 kW)
- Broadcasting infrastructure

**Stage 4 (Year 30+): Digital Communication**
- Computer-controlled radios
- Digital modes
- Spread spectrum
- Data networks (see Chapter 12)

## Safety

**RF Exposure**:
- High power RF can cause burns (internal and external)
- Don't touch antenna while transmitting
- Keep people away from high-power antennas

**High Voltage**:
- Vacuum tube transmitters use 100-3,000V
- Can kill instantly
- Capacitors store charge after power off
- Discharge before working on equipment

**Lightning**:
- Antennas attract lightning
- Disconnect or use lightning arrestor
- Ground antenna system properly

**Interference**:
- High power transmitters can interfere with electronics, pacemakers
- Use shielding and filtering
- Locate away from sensitive equipment

## Next Steps

With communication systems operational, you can:
- Coordinate communities across regions
- Share technical knowledge instantly
- Build larger-scale projects through cooperation
- Establish educational broadcasts
- Create early internet-like networks (Chapter 12)

Communication is the multiplier. It allows civilization to rebuild as a coordinated effort rather than isolated struggles. Establish radio networks early, and share knowledge across your rebuilding world.

**Key Principle**: Start simple (telegraph, crystal radio), build capability gradually (powered receivers, then transmitters), expand in stages (local, regional, worldwide). Communication is force multiplication for every other technology.
