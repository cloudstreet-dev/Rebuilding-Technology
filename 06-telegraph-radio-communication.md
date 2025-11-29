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
1. **Coil**: Wind 100-200 turns of magnet wire on tube (5-10 cm diameter)
2. **Variable capacitor**: Salvage from old radio, or make from aluminum foil sheets with adjustable spacing
3. **Diode**: Galena crystal with cat's whisker wire, or salvaged silicon diode
4. **Antenna**: As long as possible, up high
5. **Ground**: Good earth connection essential

**Reception**: Weak, requires quiet environment and good station signal. Works best for nearby AM stations.

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
- Audio signal: Varies frequency ±75 kHz
- Frequency deviation proportional to audio amplitude

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

**FM Detection**:
- Discriminator or ratio detector (classic)
- PLL detector (modern, requires IC)

**Building a Superheterodyne Receiver**:
- Can use salvaged ICs (one chip often does mixer, oscillator, IF amp, detector)
- Or build discrete components (more difficult)
- Alignment requires signal generator and oscilloscope or meter

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
