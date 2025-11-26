# Chapter 14: Displays and Human-Computer Interfaces

## Why Interfaces Matter

A computer without a way to input data and view results is useless. Human-computer interaction requires:
- **Input Devices**: Keyboard, mouse, touchscreen, sensors
- **Output Devices**: Displays, printers, speakers
- **Interface Software**: Programs that connect users to computers

This chapter covers the hardware and software for effective human-computer interaction.

## Visual Displays

### The Need for Visual Output

**Early Computers**: Switches and lights (binary), paper tape, teletype printers
**Modern Expectation**: Visual display showing text, graphics, video

**Display Evolution**:
1. Lights (binary indicators)
2. Seven-segment displays (digits)
3. Character displays (text)
4. Graphics displays (pixels)
5. High-resolution color (modern)

### Simple LED/Light Indicators

**Simplest Output**: Light on/off indicates bit value

**Single LED**:
- Current-limiting resistor
- Connect to output pin
- On = 1, Off = 0

**LED Array** (8 bits):
- 8 LEDs show byte value in binary
- Good for debugging, simple status display

**Seven-Segment Display**:
```
  ___a___
 |       |
f|       |b
 |___g___|
 |       |
e|       |c
 |___d___|  (+ decimal point)
```
- 7 segments + decimal point = 8 LEDs
- Display digits 0-9, some letters
- Common cathode or common anode
- Driver IC (or discrete transistors) for each digit

**Multiple Digits**:
- **Multiplexing**: Illuminate one digit at a time, cycle rapidly
  - Reduces pins (8 for segments + N for digit select)
  - Appears solid to human eye (>30 Hz refresh)
- Example: 4-digit display = 8 segment pins + 4 digit pins = 12 pins total

**Uses**:
- Calculators
- Clocks
- Meters
- Status displays

**Building**:
- Salvage seven-segment displays (common)
- Or make with individual LEDs
- Driver: Decoder IC (BCD to seven-segment) or microcontroller

### Nixie Tubes

**Historical Display** (1950s-1970s):
- Gas-filled tube with shaped cathodes (digits 0-9)
- High voltage (170V) makes selected cathode glow
- Beautiful orange glow
- Used in calculators, instruments, clocks

**Construction**:
- 10 cathodes (digit shapes) stacked
- Anode wire grid
- Neon or argon gas
- Glass envelope

**Driving**:
- High voltage (170-180V)
- Decade counter or BCD decoder
- Driver transistors (high voltage)

**Salvage**: Nixie tubes rare but collectible (pre-collapse). May find in old equipment.

**Making New Nixies**: Possible but difficult (glassworking, vacuum, precise cathodes)

**Use**: If available, good for retro-style displays. Otherwise, seven-segment more practical.

### Cathode Ray Tube (CRT)

**Principle**: Electron beam scans phosphor screen
- Deflect beam with magnetic or electrostatic fields
- Phosphor glows where beam hits
- Scan entire screen repeatedly (refresh)

**Components**:
1. **Electron Gun**: Heated cathode emits electrons
2. **Deflection**: Horizontal and vertical (magnetic coils or electrostatic plates)
3. **Phosphor Screen**: Glows when struck by electrons
4. **Glass Envelope**: Vacuum tube
5. **Shadow Mask** (Color CRTs): Separates red, green, blue phosphors

**Monochrome CRT**:
- Single electron gun
- One phosphor color (green, amber, or white typical)
- Simpler than color

**Color CRT**:
- Three guns (red, green, blue) or one gun with three beams
- Three phosphor types
- Shadow mask aligns beams to correct phosphors

**Deflection Systems**:

**Electrostatic** (Oscilloscopes):
- Deflection plates (X and Y)
- Voltage on plates deflects beam
- Fast, simple
- Requires high voltage (1,000s of volts)

**Magnetic** (TVs, Monitors):
- Deflection yoke (coils around neck)
- Current through coils creates magnetic field
- Deflects beam
- More complex drive circuitry but allows larger screens

**Scanning**:
- **Raster Scan**: Left to right, top to bottom, like reading
  - Horizontal: 15-100 kHz (line rate)
  - Vertical: 50-120 Hz (frame rate)
- **Vector Scan** (Oscilloscope, some games): Draw lines point-to-point

**Video Signal** (Monochrome, Simplified):
- Horizontal sync pulse: Start new line
- Vertical sync pulse: Start new frame
- Video level: Brightness of each point

**Composite Video** (Analog):
- One signal contains sync and video
- Example: NTSC (US), PAL (Europe), SECAM (France/Russia)
- 525 or 625 lines (including blanking)
- 30 or 25 frames/second (interlaced)

**RGB** (Separate Color Signals):
- Three signals: Red, Green, Blue
- Separate or combined sync
- Higher quality than composite

**Making CRT Display**:

**Salvage First**: CRTs from old TVs, monitors, oscilloscopes
- Still functional if glass intact and vacuum maintained
- Driving circuitry may need replacement

**Character Display** (Text Mode):
1. **Character ROM**: 7×9 or 8×8 pixel patterns for each ASCII character
2. **Text Buffer**: RAM holding screen contents (80×25 characters typical = 2,000 bytes)
3. **Video Generator**:
   - Read character from buffer
   - Look up pixel pattern in ROM
   - Shift out pixels (video signal)
   - Advance to next character
4. **Sync Generator**: Horizontal and vertical sync pulses
5. **Output**: Composite video or separate signals

**Effort**: Moderate. Can build discrete logic character generator with ~20-50 ICs. Or use microcontroller.

**Graphics Display** (Pixel Addressable):
1. **Frame Buffer**: RAM holding pixel values
   - Example: 320×240 monochrome = 76,800 bits ≈ 9,600 bytes
   - Color: Multiply by bits per pixel (3 for RGB, or palette index)
2. **Video DAC**: Convert pixel value to analog voltage (brightness/color)
3. **Timing Generator**: Pixel clock, sync pulses
4. **Output**: Video signal

**Effort**: Requires more memory and faster logic. Achievable with early computer capability.

**Resolution and Memory**:
```
Resolution  Monochrome  16-color    256-color   24-bit color
320×240     9 KB        38 KB       75 KB       225 KB
640×480     38 KB       150 KB      300 KB      900 KB
800×600     59 KB       234 KB      469 KB      1.4 MB
1024×768    96 KB       384 KB      768 KB      2.3 MB
1920×1080   253 KB      1 MB        2 MB        6.2 MB
```

**Trade-off**: Higher resolution and color depth require more memory and faster access.

**CRT Lifespan**: Phosphor degrades over thousands of hours. Cathode weakens. Expect 10,000-30,000 hours (years of use).

**Safety**: CRTs contain high voltage (10-30 kV). Can hold charge after power off. Implosion risk if broken. Handle with care.

### Liquid Crystal Display (LCD)

**Principle**: Liquid crystals rotate polarized light
- Polarizers on front and back
- Apply voltage: Crystals rotate, block or pass light
- Backlight (or reflective) provides illumination

**Types**:

**TN** (Twisted Nematic, Early):
- Simple, fast
- Poor viewing angle
- Used in calculators, watches

**STN** (Super Twisted Nematic):
- Better contrast
- Still limited viewing angle

**IPS** (In-Plane Switching):
- Wide viewing angle
- Better color
- More complex (and expensive)

**TFT** (Thin-Film Transistor):
- Active matrix: Transistor for each pixel
- High quality, fast
- Complex manufacturing (requires IC fabrication on glass)

**Monochrome LCD** (Simplest):
- 7-segment (calculator, watch)
- Character matrix (16×2, 20×4 common)
- Graphics (128×64, 240×320, etc.)

**Driving**:
- Multiplexing (for >few segments)
- AC drive (prevents degradation)
- Controller IC (e.g., HD44780 for character LCDs)

**Advantages of LCD vs. CRT**:
- Low power
- Flat, lightweight
- No high voltage
- Long life (no phosphor burn-in)

**Disadvantages**:
- Manufacturing complex (precision glass, liquid crystals, polarizers)
- Viewing angle (early types)
- Response time (early types)

**Salvage Priority**: Very high. LCDs abundant in 2025 (phones, tablets, laptops, monitors).

**Indigenous Manufacturing**: Difficult. Requires:
- Precision glass substrates
- Transparent electrodes (ITO - indium tin oxide)
- Liquid crystal synthesis
- Polarizer films
- Backlight (LEDs or CFLs)
- For TFT: Thin-film transistor fab on glass

**Expectation**: Salvage LCDs for decades. Indigenous manufacturing 50-100 years out.

### E-Ink (Electronic Paper)

**Principle**: Microcapsules with white and black particles
- Apply voltage: Particles migrate to top or bottom
- Bistable (retains image without power)
- Reflective (uses ambient light)

**Advantages**:
- Very low power (only uses power when changing)
- Readable in sunlight
- Paper-like appearance

**Disadvantages**:
- Slow refresh (unsuitable for video)
- Usually monochrome (color e-ink exists but limited)

**Uses**: E-readers, signage

**Salvage**: E-readers (Kindle, etc.) have e-ink displays

**Manufacturing**: Very difficult (specialized materials and processes)

### OLED (Organic LED)

**Principle**: Organic compounds emit light when current applied

**Advantages**:
- Emissive (no backlight needed)
- High contrast (true black)
- Fast response
- Flexible (can bend)

**Disadvantages**:
- Organic materials degrade (limited life)
- Expensive (by 2025, becoming more common)

**Salvage**: Phones, some TVs and monitors (by 2025)

**Manufacturing**: Very difficult (vacuum deposition of organic layers)

### LED Matrix Displays

**Principle**: Array of LEDs, individually controlled

**Types**:
- Monochrome (red, green, etc.)
- RGB (full color)

**Resolution**:
- Low: 8×8, 16×16 (simple displays)
- High: 64×64, 128×128+ (video walls, large displays)

**Multiplexing**: Scan rows, drive columns (or vice versa)

**Driving**:
- Shift registers to feed data
- Current drivers for LEDs
- Refresh >100 Hz

**Advantages**:
- Bright (outdoor visible)
- Rugged
- Scalable (tile multiple panels)

**Disadvantages**:
- Lower resolution (per size) than LCD
- Power-hungry

**Uses**: Outdoor signs, scoreboards, large displays

**Building**: Easier than LCD or CRT (discrete LEDs)
- Salvage LED modules
- Or build from individual LEDs

### Vector Displays and Oscilloscopes

**Oscilloscope**: X-Y display for waveforms
- CRT with electrostatic deflection
- Can display arbitrary waveforms
- Used in test equipment, some games (Asteroids, Tempest)

**Advantages**: Fast, infinite resolution (vector-drawn)
**Disadvantages**: Can't fill areas, limited brightness

### Comparison of Display Technologies

```
Technology   Cost  Power  Resolution  Color  Lifespan  Availability
LEDs         Low   High   Low         Yes    Long      Easy to make
7-Segment    Low   Med    N/A         No     Long      Easy
CRT          Med   High   High        Yes    Medium    Salvage
LCD          Med   Low    High        Yes    Long      Salvage
OLED         High  Low    High        Yes    Medium    Salvage
E-Ink        Med   V.Low  Medium      Limited Long     Salvage
```

**Post-Collapse Recommendation**:
- **Immediate**: LEDs, seven-segment (easy to build/salvage)
- **Short-term**: Salvaged CRTs (abundant, drive circuits buildable)
- **Medium-term**: Salvaged LCDs (more efficient, longer-lasting)
- **Long-term**: Build LED matrices, eventually attempt LCD manufacture

## Input Devices

### Switches and Buttons

**Simplest Input**: Binary on/off
- Toggle switches
- Push buttons
- DIP switches (settings)

**Debouncing**: Mechanical contacts bounce (multiple pulses for one press)
- Hardware: RC filter, Schmitt trigger
- Software: Wait a few milliseconds, sample again

**Uses**: Early computers (toggle in programs), reset/control, keyboards

### Keyboard

**Purpose**: Type text and commands

**Types**:

**Matrix Keyboard**:
- Switches arranged in grid (rows and columns)
- Scan rows, read columns (or vice versa)
- N×M switches with N+M wires (e.g., 8×8 = 64 keys with 16 wires)

**Scanning Process**:
1. Drive row 0 low
2. Read all columns (pressed key connects row to column)
3. Drive row 1 low
4. Read columns
5. Repeat for all rows
6. Decode: Row + column → key code (ASCII or scan code)

**Rollover**: Multiple keys pressed simultaneously
- 2-key rollover (detects two keys)
- N-key rollover (detects all keys)
- Ghost keys (false positives with >2 keys)

**Diodes**: Add diode to each switch to prevent ghosting

**Key Switches**:
- Membrane (cheap, quiet)
- Mechanical (tactile, durable, loud)
- Capacitive (expensive, no contact wear)

**Building Keyboard**:
- Salvage keys and switches (abundant)
- Wire matrix
- Microcontroller to scan and encode
- Or use salvaged keyboard (PS/2, USB)

**Interface**:
- **PS/2**: Serial protocol, simple to implement
- **USB**: Complex protocol, requires USB controller
- **Serial**: Simple UART connection (custom)

**Layouts**:
- QWERTY (standard)
- DVORAK (more efficient, less common)
- Others (language-specific)

### Mouse

**Principle**: Pointing device
- X and Y position (or relative motion)
- Buttons (1-3+ typical)

**Types**:

**Mechanical** (Ball Mouse, Historical):
- Rolling ball
- Encoders detect motion (X and Y)
- Simple, but requires cleaning

**Optical** (LED + Sensor):
- LED illuminates surface
- Camera sensor detects motion
- More reliable than mechanical

**Laser** (High-Precision Optical):
- Laser instead of LED
- Higher precision
- Works on more surfaces

**Driving**:
- Serial protocol (PS/2, USB)
- Quadrature encoding (for mechanical)

**Salvage**: Abundant. USB mice require USB controller to read.

**Building Mouse**:
- Mechanical: Encoders on ball axes, buttons
- Optical: Requires image sensor and processing (difficult)
- Recommendation: Salvage

**Alternative Pointing Devices**:
- Trackball: Inverted mouse (ball on top)
- Touchpad: Capacitive surface
- Joystick: Analog or digital directional control
- Light pen: CRT-specific (detects beam timing)

### Touchscreen

**Principle**: Detect touch position on screen

**Types**:

**Resistive**:
- Two conductive layers, separated by spacers
- Press: Layers touch, measures position by resistance
- Works with any object (finger, stylus)
- Low cost
- Used in older smartphones, PDAs, industrial terminals

**Capacitive**:
- Glass with conductive coating
- Finger (conductor) changes capacitance
- Measures position by capacitance change
- Multi-touch capable
- Clearer display (no resistive layers)
- Used in modern smartphones, tablets

**Infrared**:
- IR LEDs and sensors around bezel
- Detects finger by broken beam
- Works with any object
- No overlay on screen
- Used in some industrial/commercial displays

**Optical** (Camera-Based):
- Cameras detect finger
- Requires processing power

**Making Touchscreen**:
- Resistive: Easier (conductive layers, pressure)
- Capacitive: Requires precise coating, controller IC

**Salvage**: Touchscreens common in salvaged devices

**Post-Collapse**: Salvage initially. Building touchscreens difficult until advanced manufacturing capability.

### Voice Input

**Speech Recognition**:
- Microphone captures audio
- Processing: Convert sound to text (or commands)
- Complex: Requires significant compute power and algorithms

**Early Systems** (1980s-1990s):
- Limited vocabulary (100-1,000 words)
- Speaker-dependent (train for each user)
- Low accuracy

**Modern Systems** (2010s-2020s):
- Large vocabulary
- Speaker-independent
- High accuracy
- Uses machine learning (neural networks)

**Post-Collapse Timeline**:
- Early (10-20 years): Simple voice commands (limited vocabulary)
- Later (30-50 years): General speech recognition (requires advanced AI, see Chapter 16)

### Sensors (Non-Human Input)

**Temperature**: Thermistor, thermocouple, RTD, IC sensor
**Light**: Photoresistor, photodiode, phototransistor
**Pressure**: Piezoelectric, capacitive, strain gauge
**Acceleration**: Accelerometer (MEMS)
**Rotation**: Gyroscope (MEMS), encoder
**Position**: GPS, encoders, potentiometers
**Proximity**: Ultrasonic, IR, capacitive, hall effect
**Humidity**: Capacitive, resistive

**Uses**: Environmental monitoring, robotics, industrial control

**Salvage**: Sensors abundant in modern devices (phones have 10+ sensors)

## Printing and Physical Output

### Printers

**Purpose**: Create permanent copy on paper

**Impact Printers** (Hit Paper):

**Dot Matrix**:
- Print head with pins (7, 9, 24 typical)
- Pins strike ribbon against paper
- Forms characters from dots
- Noisy, low quality, but cheap and reliable
- Carbon copies possible

**Daisy Wheel**:
- Wheel with molded characters
- Rotates to select character, hammer strikes
- Good quality (typewriter-like)
- Slow, noisy
- Historical (1970s-1980s)

**Line Printer**:
- Entire line at once
- Drum or chain with characters
- Very fast for large amounts
- Poor quality
- Used in data centers (historical)

**Non-Impact Printers**:

**Inkjet**:
- Spray tiny droplets of ink
- Piezoelectric or thermal
- High quality, color
- Requires ink (can dry out)

**Laser** (and LED):
- Laser (or LED array) writes pattern on photosensitive drum
- Toner (powder) adheres to charged areas
- Transfers to paper, fused with heat
- High quality, fast
- Complex, expensive

**Thermal**:
- Heat-sensitive paper
- Thermal head heats paper to darken
- Simple, low cost
- Special paper required
- Used in receipts, faxes, labels

**Salvage**: Printers abundant. Laser and inkjet common.
- Consumables (ink, toner, paper) will eventually run out
- Dot matrix more sustainable (ribbon can be re-inked)

**Building Printer**:
- Dot matrix: Solenoids drive pins, stepper motor for paper feed
  - Achievable with early electronics
- Thermal: Heating elements, special paper
  - Simpler mechanically than dot matrix
- Inkjet/Laser: Very complex, salvage only for foreseeable future

### Plotters

**Purpose**: Draw vector graphics (lines, arcs)

**Pen Plotter**:
- Pen moves in X and Y
- Draws by moving pen while down
- Used for CAD drawings, maps

**Types**:
- Flatbed: Paper stationary, pen moves in X and Y
- Drum: Paper moves in Y, pen moves in X

**Building**:
- Stepper motors for X and Y
- Solenoid or servo for pen up/down
- Software: Convert vector graphics to motion commands

**Uses**: Technical drawings, large-format graphics

### CNC Machines (Physical Output Beyond Paper)

**Principle**: Computer-controlled tools
- Milling, lathing, drilling, cutting

**3D Printers**:
- Additive manufacturing (build up layers)
- Fused deposition (FDM): Melt plastic, extrude
- Stereolithography (SLA): UV light cures resin
- Selective laser sintering (SLS): Laser fuses powder

**Uses**: Prototyping, manufacturing, repair

**Building CNC/3D Printer**:
- Stepper motors (X, Y, Z axes)
- Controller (microcontroller or PC)
- Toolhead (spindle for CNC, extruder for 3D printer)
- Frame (rigid, accurate)

**Software**:
- CAD: Design part
- CAM: Convert design to toolpaths (G-code)
- Controller: Execute G-code

**Post-Collapse**: CNC and 3D printing valuable for making parts without extensive machining skills.

## Audio Output

### Speakers

**Principle**: Convert electrical signal to sound waves
- Permanent magnet, coil on diaphragm
- Varying current moves coil, moves diaphragm, creates pressure waves

**Types**:
- Dynamic (moving coil): Most common
- Piezoelectric: Simple, limited range
- Electrostatic: High quality, expensive, fragile

**Building**:
- Salvage speakers (easy, abundant)
- DIY: Coil, magnet, cone (achievable but lower quality)

**Amplifier**: Needed to drive speaker from weak signal
- Transistor or IC amplifier (LM386, etc.)

### Sound Synthesis

**Tone Generation**:
- Simple: Square wave from oscillator (buzzer)
- Better: Waveform synthesis (sine, triangle, sawtooth)

**Music**:
- Programmable Sound Generator (PSG): Multiple channels, envelopes
- FM Synthesis: Frequency modulation creates complex sounds
- Wavetable: Replay recorded samples

**DAC** (Digital to Analog Converter):
- Convert digital values to voltage
- Sampled audio playback (CD quality: 44.1 kHz, 16-bit)

**Building**:
- Simple tones: Easy (timer IC, transistor amplifier, speaker)
- Music: Moderate (PSG chip or microcontroller)
- CD-quality audio: Requires fast DAC and processing

## Graphical User Interface (GUI)

### Command-Line Interface (CLI)

**Earliest Interface**: Text commands
- Type command, press enter
- Computer responds with text
- Examples: Unix shell, DOS

**Advantages**:
- Simple to implement
- Low resource usage
- Powerful (compose commands, scripts)
- Remote-friendly (works over serial/network)

**Disadvantages**:
- Steeper learning curve
- Not intuitive for beginners

### GUI Components

**Windows**: Rectangular areas showing programs
**Icons**: Small images representing files, programs
**Menus**: Lists of commands
**Buttons**: Clickable controls
**Scroll bars**: Navigate content
**Dialog boxes**: Prompts and settings

**WIMP**: Windows, Icons, Menus, Pointer (mouse)

### GUI Systems

**X Window System** (Unix/Linux):
- Client-server architecture
- Applications (clients) communicate with display server
- Network-transparent (client and server can be on different machines)
- Open standard

**Microsoft Windows**:
- Integrated GUI and OS
- Proprietary

**macOS** (Apple):
- Unix-based, proprietary GUI

**Building GUI**:
- Requires graphics display
- Window manager: Controls window position, size, focus
- Widget toolkit: Buttons, menus, etc. (Gtk, Qt, etc.)
- Event loop: Process mouse clicks, key presses

**Effort**: Large. Modern GUIs are millions of lines of code.

**Recommendation**:
- Start with CLI (simple, functional)
- Add simple GUI later (basic windows, buttons)
- Use existing GUI (X Window, etc.) if salvaged computers available

## Accessibility

**Importance**: Not all users have full vision, hearing, or mobility

**Visual Impairment**:
- Screen readers: Convert text to speech
- Braille displays: Raise pins to form Braille characters
- High contrast, large fonts

**Hearing Impairment**:
- Visual alerts (instead of beeps)
- Captions for speech

**Mobility Impairment**:
- Keyboard-only navigation (no mouse required)
- Voice control
- Alternative input devices (sip-and-puff, eye tracking, etc.)

**Post-Collapse**: Accessibility may not be initial priority, but don't forget. Ensure interfaces can be adapted.

## Summary: Interface Development Stages

**Stage 1 (Year 0-10): Basic I/O**
- Switches and lights
- Seven-segment displays
- Simple keyboard
- Teletype or terminal

**Stage 2 (Year 10-25): Text Displays**
- CRT character display (or salvaged monitor)
- Full keyboard
- Simple mouse (or salvaged)
- CLI (command-line)

**Stage 3 (Year 25-40): Graphics and GUI**
- CRT or LCD graphics display
- Color
- Mouse, touchpad
- Basic GUI (windows, menus)
- Dot-matrix or thermal printer

**Stage 4 (Year 40-60): Modern Interfaces**
- High-resolution color displays (LCD)
- Advanced GUI
- Touchscreen
- Voice input (limited)
- Laser or inkjet printer

**Stage 5 (Year 60+): Contemporary HCI**
- Multiple displays, high resolution
- Touch, voice, gesture
- VR/AR (virtual/augmented reality)
- Advanced accessibility

## Practical Guidance

**Salvage First**:
- Keyboards, mice, displays abundant in 2025
- Use salvaged until build capability matures

**Build What You Can**:
- LED displays: Early
- CRT driver circuits: Medium-term
- Keyboards: Medium-term (mechanical easier than full custom)
- Touchscreens: Late (difficult manufacturing)

**Prioritize Usability**:
- Good interface = productive users
- Don't neglect software (GUI, CLI)
- Accessibility matters

**Document**:
- Connector pinouts
- Signal protocols
- Driver software

## Conclusion

Interfaces are the bridge between humans and computers. Good interfaces make technology accessible and useful. Poor interfaces create barriers.

**Key Principle**: Start simple, expand gradually. LEDs and switches are enough to toggle in programs and see results. Add keyboards and displays as soon as possible for productivity. Add GUI when capability allows. Always design for users, not just for machines.

The computer without a screen and keyboard is a black box. The computer with a good interface is a tool for thought. Invest in interfaces, and the technology becomes accessible to everyone, not just engineers.
