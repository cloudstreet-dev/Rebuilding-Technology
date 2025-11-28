# Chapter 3: Generating and Storing Electricity

## Why Electricity Is Critical

Electricity transforms what's possible:
- **Light**: Extends productive hours beyond daylight
- **Communication**: Telegraph, radio, telephone
- **Motors**: Precision tools, automation
- **Electronics**: Computing, control systems
- **Heating**: Controlled, clean heat for manufacturing

Without electricity, you're limited to mechanical and chemical processes. With it, you can build modern technology.

## First Week Electrical: Immediate Post-Collapse Power

Before diving into building generators or understanding complex theory, you need basic electrical capability NOW. Here's a 24-48 hour path from nothing to working lights:

**Day 1: Salvage and Basic Power (4-8 hours)**

1. **Find a car battery**
   - Check voltage with multimeter (should read 12-14V if charged)
   - If dead, set aside for charging later
   - **Safety:** Batteries contain sulfuric acid - don't tip, don't short terminals

2. **Find any solar panel**
   - Roof installations, garden lights, calculators (small but functional)
   - Test in sunlight: Should produce 15-20V (12V panel) or 30-40V (24V panel)
   - **Don't connect directly to battery yet** (need charge controller - see solar section)

3. **Connect for immediate use:**
   - **With charge controller (ideal):** Panel → Controller → Battery
   - **Without controller (temporary):** Monitor voltage manually
     - Connect panel to battery
     - Check battery voltage every 30 minutes
     - Disconnect when battery reaches 14.4V
     - **This is emergency-only** - destroys batteries long-term

4. **Power LED lights:**
   - Salvage 12V LED lights (RV, automotive, marine)
   - Connect directly to battery (LEDs have low current draw)
   - Polarity matters: Red (+) to positive, Black (-) to negative
   - Result: Working lights powered by solar-charged battery

**Day 2: Improve and Expand (4-8 hours)**

5. **Add more panels (if available):**
   - Panels connect in parallel for more current (same voltage)
   - Match voltages (all 12V or all 24V)
   - Use salvaged wire (10-14 gauge for short runs)

6. **Build simple charge controller:**
   - See Practical Projects section
   - Or continue manual monitoring (tedious but works)

7. **Add USB charging:**
   - Salvage 12V USB adapters (car chargers)
   - Powers phones, tablets, small devices
   - Prioritize devices that store knowledge (e-readers, phones with offline docs)

**Success criteria:**
- Working lights (extends productive hours)
- Device charging (preserves access to stored information)
- Battery charging from sun (renewable, no fuel needed)

**Next steps:** With basic power working, study the rest of this chapter to understand principles, build better systems, and expand capacity.

## Understanding Electricity Basics

### Essential Concepts

**Voltage (V)**: Electrical "pressure" that pushes electrons
- Measured in volts (V)
- Like water pressure in a pipe
- Higher voltage can be dangerous

**Current (I)**: Flow rate of electrons
- Measured in amperes or amps (A)
- Like water flow rate
- Amount of current determines power capacity

**Resistance (R)**: Opposition to current flow
- Measured in ohms (Ω)
- Like friction in a pipe
- Conductors have low resistance, insulators have high resistance

**Power (P)**: Rate of energy transfer
- Measured in watts (W)
- Formula: P = V × I (power = voltage × current)
- Example: 120V × 10A = 1,200W (1.2 kilowatts)

**Ohm's Law** (most important equation):
```
V = I × R
(Voltage = Current × Resistance)
```
If you know any two values, you can calculate the third.

**AC vs. DC**:
- **DC (Direct Current)**: Flows one direction, constant voltage (batteries, solar panels)
- **AC (Alternating Current)**: Reverses direction 50-60 times per second (generators, grid power)
- AC is easier to generate and transform to different voltages
- DC is easier to store and use in electronics

### Energy and Power

**Energy**: Total work done, measured in watt-hours (Wh) or kilowatt-hours (kWh)
- Formula: Energy = Power × Time
- Example: 100W light bulb for 10 hours = 1,000 Wh = 1 kWh

**Efficiency**: No conversion is 100% efficient
- Generator: 60-90% efficient (rest becomes heat)
- Battery: 70-90% round-trip efficiency
- Power transmission: Loses energy to resistance in wires

## Generating Electricity

### Electromagnetic Induction (The Principle)

**Faraday's Law**: Moving a conductor through a magnetic field generates voltage

**Basic Generator**:
```
Rotating coil of wire (conductor)
    + Magnetic field (from permanent magnets or electromagnets)
    = Electricity generated in coil
```

**Key factors**:
- Stronger magnetic field = more voltage
- Faster rotation = more voltage
- More turns of wire = more voltage
- Larger coil = more power capacity

### Hand-Crank Generator (Simplest)

**Construction**:
1. **Rotor**: Coil of copper wire wound on iron core
   - 200-500 turns of magnet wire (thin insulated copper wire)
   - Iron core (salvaged from motor or transformer)
2. **Stator**: Permanent magnets (salvage from hard drives, speakers)
   - Arrange magnets so opposite poles face each other across rotor
3. **Shaft and bearings**: Allow rotor to spin smoothly
4. **Crank handle**: For manual rotation
5. **Slip rings or brushes**: Transfer electricity from spinning rotor

**Output**: 6-24V DC, 10-50W (depending on size and crank speed)
**Uses**: Charging batteries, emergency lighting, small electronics
**Build time**: 1-2 days with salvaged materials

**Improving Output**:
- More magnets = higher voltage
- Stronger magnets (neodymium) = higher voltage
- Faster cranking = higher voltage
- More wire turns = higher voltage (but more resistance)
- Thicker wire = more current capacity

### Using Salvaged Motors as Generators

Many post-collapse communities will have access to salvaged motors. Motors and generators are the same device running in reverse, but the details matter:

**DC Motors as Generators (Simple - Works Directly):**

- **Permanent magnet DC motors:** Spin the shaft, get voltage at terminals. That's it.
  - Examples: Cordless drill motors, car window motors, small appliance motors
  - Output voltage: Proportional to RPM (typical: 12-24V at 500-1000 RPM)
  - Polarity: Reverse spin direction = reverse polarity
  - **Best for:** Hand-crank generators, bike generators, small wind/hydro
  - **Advantages:** No external excitation needed, very simple

- **DC motors with field coils (not permanent magnets):**
  - Require external power to field coil to create magnetic field
  - Connect 12V battery to field terminals while spinning shaft
  - Once generating, can sometimes self-excite (output powers own field)
  - More complex, but works if permanent magnet motors unavailable

**AC Induction Motors as Generators (Complex - Need Capacitors):**

- **Most common salvaged motors are AC induction motors** (appliances, power tools, HVAC)
- Induction motors have NO permanent magnets and NO brushes
- To use as generator:
  1. **Residual magnetism required:** Small amount of magnetism must remain in rotor
  2. **Capacitor excitation:** Connect capacitors across output terminals
     - Capacitance value critical (typically 10-50 μF per kW rating)
     - Wrong value = no output or motor overheats
  3. **Must spin faster than synchronous speed** (>1800 RPM for 60 Hz motors)
  4. **Output frequency varies with speed** (not fixed like grid power)

- **Reality:** AC induction motors as generators are finicky
  - Capacitor sizing is trial-and-error
  - Load changes affect voltage and frequency
  - Only worth attempting if no DC motors available

**Practical Salvage Strategy:**

1. **First priority:** Permanent magnet DC motors (cordless tools, car accessories)
2. **Second priority:** DC motors with field coils (car starters can work)
3. **Third priority:** Car alternators (need modification - see Wind Generator section)
4. **Last resort:** AC induction motors (complex, unreliable without proper capacitors)

**Testing salvaged motors:**
- Spin shaft by hand, measure voltage at terminals with multimeter
- If you get voltage (even small), it's a permanent magnet motor - usable as generator
- If no voltage, it's either induction or field-coil motor - more complex

### Water Wheel/Hydro Generator

**Principle**: Flowing water turns wheel, wheel turns generator

**Requirements**:
- Flowing water source (stream, river, canal)
- Vertical drop (head) of at least 1-2 meters
- Consistent flow year-round (or seasonal use)

**Types**:

**1. Overshot Wheel** (water falls on top):
- Efficiency: 60-85%
- Best for: High head (>2m), low flow rate
- Construction: Large wheel with buckets, water fills buckets at top, weight turns wheel
- Diameter: 2-6 meters typical

**2. Undershot Wheel** (water pushes at bottom):
- Efficiency: 30-50%
- Best for: Low head (<1m), high flow rate
- Construction: Paddles at bottom, water current pushes them

**3. Modern Turbine** (more efficient):
- Efficiency: 70-90%
- Requires more sophisticated construction
- Types: Pelton (high head), Francis (medium head), Kaplan (low head)

**Power Calculation**:
```
Power (watts) = 9.81 × Flow rate (liters/sec) × Head (meters) × Efficiency

Example:
Stream with 100 liters/sec flow, 5m drop, 70% efficiency:
P = 9.81 × 100 × 5 × 0.70 = 3,434 watts (3.4 kW)
```

**Construction Steps**:
1. **Survey site**: Measure head and flow rate
2. **Build dam/diversion**: Channel water to wheel
3. **Construct wheel**: Wood or metal, 2-4m diameter
4. **Add generator**: Salvaged alternator or build coil generator
5. **Gearing**: Match wheel speed (slow) to generator speed (fast)
   - Typical: Wheel 5-20 RPM, generator needs 100-500 RPM
   - Use belt drive or gear train (10:1 to 50:1 ratio)

**Achieving Speed Increase with Gearing/Belt Drives:**

The water wheel turns slowly (5-20 RPM) but generators need higher speed (100-500 RPM). You need a 10:1 to 50:1 speed increase. Three approaches:

**1. Belt Drive with Pulley Ratios (Simplest):**
   - Small pulley on generator shaft, large pulley on water wheel shaft
   - Ratio = (Wheel pulley diameter) / (Generator pulley diameter)
   - Example: 500mm wheel pulley, 50mm generator pulley = 10:1 ratio
   - For 20:1, use 1000mm wheel pulley, 50mm generator pulley
   - **Advantages:** Simple, quiet, tolerates misalignment
   - **Disadvantages:** Belt slippage under load, belt wear
   - **Belt types:** V-belt (best), flat belt (acceptable), salvaged serpentine belt

**2. Chain and Sprocket System:**
   - Bicycle chains and sprockets work well for small systems
   - Ratio = (Wheel sprocket teeth) / (Generator sprocket teeth)
   - Example: 60-tooth wheel sprocket, 12-tooth generator sprocket = 5:1 ratio
   - **Multiple stages:** For 25:1, use two 5:1 stages (intermediate shaft between wheel and generator)
   - **Advantages:** No slippage, durable, salvageable from bicycles
   - **Disadvantages:** Requires precise alignment, needs lubrication (Chapter 2.8)

**3. Gear Train (Most Durable):**
   - Spur gears meshing directly
   - Ratio = (Wheel gear teeth) / (Generator gear teeth)
   - **Multiple stages needed:** 50:1 requires two or three gear stages
   - Example: Stage 1 = 7:1 (70/10 teeth), Stage 2 = 7:1 (70/10 teeth) = 49:1 total
   - **Advantages:** No slippage, efficient, very durable
   - **Disadvantages:** Expensive, requires precise machining, requires lubrication

**Practical Recommendation:**
- **Small systems (<500W):** Belt drive, possibly multi-stage (belt to intermediate shaft, belt to generator)
- **Medium systems (500-2000W):** Chain and sprocket or combination (chain primary, belt final)
- **Large systems (>2000W):** Gear train or heavy-duty chain

**Design notes:**
- Higher ratios need stronger mounting (torque increases)
- Intermediate shaft (jackshaft) between wheel and generator allows multiple stages
- Tensioning: Springs or adjustable mounts maintain tension as belts/chains stretch

6. **Penstock**: Pipe to deliver water if using turbine instead of wheel

**Advantages**: Continuous power, no fuel needed, reliable
**Challenges**: Needs water source, seasonal variation, freezing in winter

### Wind Generator

**Principle**: Wind turns blades, blades turn generator

**Power in Wind**:
```
Power (watts) = 0.5 × Air density × Area × Wind speed³

Air density ≈ 1.225 kg/m³ at sea level
Area = π × radius² (swept area of blades)
Wind speed in meters/second
```

**Key insight**: Power increases with cube of wind speed
- 5 m/s (11 mph) → baseline
- 10 m/s (22 mph) → 8× more power
- 15 m/s (34 mph) → 27× more power

**Practical Efficiency**: Betz limit says max 59.3% of wind energy can be captured; real turbines get 30-45%

**Design**:

**Blade Number**:
- 1-2 blades: High speed, requires balancing, efficient
- 3 blades: Most common, good balance of efficiency and stability
- 6+ blades: Low speed, high torque (like farm windmills), less efficient

**Blade Construction**:
- Simplest: Wood, carved to airfoil shape
- Better: PVC pipe cut lengthwise, shaped
- Best: Fiberglass or aluminum, precision airfoil
- Length: 1-3 meters for small turbine

**Tower**:
- Height: Higher is better (wind speed increases with height)
- Minimum: 10m above obstacles within 100m
- Construction: Steel pipe, wooden pole, or lattice tower
- Guy wires: Stabilize tower

**Generator**:
- Salvaged car alternator (easiest)
  - Needs modification for low RPM operation
  - Add more powerful magnets or rewind stator
- Custom permanent magnet generator (better efficiency)
- Gear up from blade rotation if needed

**Modifying Alternators for Low-RPM Operation:**

Car alternators are designed for 1,800-6,000 RPM (engine speed). Wind/hydro applications run much slower (50-500 RPM). To make alternators work at low RPM:

1. **Replace voltage regulator:**
   - Remove built-in regulator (limits voltage at high RPM)
   - Install external regulator designed for low-RPM charging
   - Or use fixed resistor to field coil (maintains stronger magnetic field)

2. **Add external field control:**
   - Car alternators use electromagnets (field coils), not permanent magnets
   - At low RPM, weak field = low voltage
   - Increase field current: 12V battery directly to field coil through resistor (2-5 ohms, 25W)
   - This "over-excites" the field, boosting output at low speeds

3. **Rewind with more turns:**
   - Disassemble stator (stationary coil assembly)
   - Replace thick wire (few turns) with thinner wire (many more turns)
   - Target: 2-3× the original turns using half the wire diameter
   - This increases voltage at low RPM but reduces current capacity
   - Labor-intensive but effective for dedicated low-RPM applications

4. **Replace with stronger magnets (advanced):**
   - Some alternators allow rotor replacement
   - Salvage neodymium magnets, mount on rotor in place of field coils
   - Converts alternator to permanent magnet generator
   - Best option but requires machining and careful magnetic polarity alignment

**Practical approach:** Start with external field control (easiest). If insufficient, rewind stator. Most wind/hydro systems need gearing anyway (see below).

**Power Output** (estimated for 3-blade turbine):
- 1m diameter blades, 5 m/s wind: ~50W
- 2m diameter blades, 7 m/s wind: ~300W
- 3m diameter blades, 10 m/s wind: ~1,000W

**Critical Components**:
- **Yaw mechanism**: Allows turbine to face into wind
- **Brake**: Stops blades in high winds (or they'll destroy themselves)
- **Charge controller**: Prevents battery overcharge

**Challenges**:
- Wind is intermittent
- Needs battery storage
- Mechanical wear from constant operation
- Storm damage risk

### Steam Power (Thermal to Electricity)

**Principle**: Heat water → steam → turns turbine → generates electricity

**Heat Sources**:
- Wood or coal fire
- Solar concentrator
- Geothermal (if available)
- Waste heat from industrial processes

**Components**:

**1. Boiler**:
- Pressure vessel to contain steam
- Safety valve (critical—boiler explosions are deadly)
- Materials: Steel pipe or sheet metal
- Pressure: 50-150 PSI (3-10 bar) for small systems

⚠️ **CRITICAL SAFETY WARNING - BOILER EXPLOSIONS:**

**More people have been killed by boiler explosions than any other industrial accident in history.** Boiler explosions are catastrophic: superheated water instantly flashes to steam (expands 1,600×), releasing energy equivalent to TNT. Buildings are destroyed, people are killed instantly.

**DO NOT build a steam system without someone experienced in pressure vessel safety.**

**Mandatory safety features:**
- **Pressure relief valve:** MUST open before reaching design pressure (set 10% below max)
- **Pressure gauge:** Visible, accurate, calibrated
- **Water level indicator:** Glass tube or gauge cocks - NEVER run boiler dry
- **Low-water cutoff:** Automatic fuel shutoff if water drops below safe level
- **Multiple redundant safeties:** One failure should not cause explosion

**Design requirements:**
- Use thick-walled pressure-rated pipe or professionally welded pressure vessel
- Never plug a safety valve or pressure relief
- Test pressure relief valves monthly (pull test lever, should release steam)
- Inspect boiler annually for corrosion, cracks, leaks
- Never exceed design pressure - even briefly

**If you don't understand pressure vessel design, do not build a boiler. Use other power generation methods.**

**2. Turbine**:
- Steam nozzle directs high-speed steam at blades
- Blades on wheel spin from steam impact
- Types:
  - Impulse turbine: Steam hits blades, momentum turns wheel
  - Reaction turbine: Steam expands through blades, pressure drop causes rotation
- Speed: 3,000-10,000 RPM typical

**3. Condenser**:
- Cools steam back to water
- Creates vacuum, improves efficiency
- Construction: Pipes with cooling water flowing around them

**4. Generator**:
- High-speed turbine may drive generator directly
- Or use gearing to match speeds

**Efficiency**: 10-30% for small systems (most energy lost as waste heat)

**Practical Reality**: Steam power is complex and dangerous. Only pursue if:
- You have no hydro or wind option
- You have skilled metalworkers (to build safe boiler)
- You have abundant fuel
- You need significant power (>1 kW)

### Solar Power

**Photovoltaic Panels** (Light to Electricity):

**Salvage First**: Solar panels from 2025 may still function decades later
- Check with multimeter in sunlight:
  - **Open-circuit voltage (Voc):** Disconnect panel, measure voltage in full sun
    - Should read near rated voltage (18-22V for nominal "12V" panel, 30-40V for "24V" panel)
    - Significantly lower (< 70% of rated) indicates degraded cells or damaged connections
  - **Short-circuit current (Isc):** Connect multimeter in current mode across panel terminals briefly (< 5 seconds)
    - Should read 70%+ of rated current (check panel label)
    - Low current indicates shading, dirt, or cell damage
  - Test in full midday sun for accurate readings
- Clean surface (dirt/debris reduces output significantly)
- Repair wiring if needed
- Output degrades ~0.5% per year, so 20-year-old panel might produce 90% of original

**CRITICAL: Charge Controllers Are Mandatory**

⚠️ **Never connect solar panels directly to batteries without a charge controller.** This is a common mistake that destroys batteries.

**Why charge controllers matter:**
- Solar panels produce voltage even in partial sunlight
- On sunny days, panel voltage exceeds battery safe charging voltage
- Overcharging causes:
  - Lead-acid batteries: Water loss (boiling electrolyte), plate damage, thermal runaway
  - Battery lifespan reduced from years to months
  - Fire risk (hydrogen gas release + spark = explosion)

**Charge controller functions:**
1. **Voltage regulation:** Stops charging when battery reaches 14.4V (12V system)
2. **Prevents reverse current:** Blocks battery from discharging through panel at night
3. **Load disconnect:** Prevents deep discharge (protects battery from over-discharge)

**Simple improvised controller:**
- Relay-based disconnect when battery voltage exceeds 14.4V
- Diode (10A+ rated) prevents reverse current at night
- Manual monitoring if automatic controller unavailable
- See Practical Projects section for simple controller build

**Controller types:**
- **PWM (Pulse Width Modulation):** Simpler, cheaper, adequate for small systems
- **MPPT (Maximum Power Point Tracking):** More efficient (20-30% gain), complex, worth it for larger systems

**Manufacturing Solar Cells**: Extremely difficult, requires:
- Ultra-pure silicon
- Doping with phosphorus and boron
- Clean room environment
- High-temperature processing
**Recommendation**: Don't attempt to manufacture PV cells until Tier 3+ (years 30+)

**Solar Thermal** (Heat to Electricity):
- Concentrate sunlight with mirrors
- Heat fluid (oil, molten salt)
- Use heat to generate steam → turbine → electricity
- Easier than PV manufacturing but still complex
- Works only in sunny climates

**Practical Solar Use**:
- Salvage panels: High priority
- Solar heating: Easy (black pipes/tanks for water heating)
- Solar cooking: Easy (parabolic reflectors)
- Solar electricity generation: Salvage until you can manufacture

## Storing Electricity

Electricity must be used as it's generated, or stored. Storage is critical for intermittent sources (solar, wind).

### Lead-Acid Batteries (Easiest to Build)

**How It Works**:
- Two lead plates in sulfuric acid
- Chemical reaction stores energy
- Reversible: Discharge (use power), charge (store power)

**Salvage First**:
- Car batteries: 12V, 50-100 amp-hours typical
- Truck/tractor batteries: 12V or 24V, higher capacity
- Deep-cycle batteries: Better for renewable energy use
- Check voltage, attempt to recharge, desulfate if needed

**Testing Old Batteries**:
1. Measure voltage (should be 12.6V+ for 12V battery when full)
2. Load test: Connect to light bulb, voltage shouldn't drop below 10V
3. Specific gravity: Use hydrometer to check acid strength (1.265 for full charge)

**Refurbishing Failed Batteries**:
- **Sulfation** (most common failure):
  - Lead sulfate crystals build up on plates
  - Slowly charge and discharge multiple times
  - Or use desulfation circuit (high frequency pulses)
- **Low electrolyte**:
  - Add distilled water (NOT tap water—minerals damage battery)
  - Never add acid unless acid was spilled
- **Shorted cells**:
  - One cell dead means 10.5V instead of 12.6V
  - Difficult to repair, may need to replace cell

**Building New Lead-Acid Batteries**:

**Materials**:
- Lead sheets (salvage from old batteries, wheel weights, roofing)
- Sulfuric acid (make from sulfur, see Chapter 4, or salvage from old batteries)
- Container (acid-resistant: polypropylene, glass, ceramic)
- Separator (prevents plates from touching): porous material, fiberglass mat, or polyethylene

**Construction**:
1. **Prepare plates**:
   - Positive plate: Lead dioxide (PbO2)—brown/black
   - Negative plate: Pure sponge lead (Pb)—gray
   - Process: Coat lead sheet with lead oxide paste, cure, then "form" electrochemically
2. **Forming process**:
   - Place lead plates in dilute sulfuric acid
   - Pass DC current through (charging)
   - Positive plate converts to PbO2, negative to sponge Pb
   - **Takes days of careful charging/discharging cycles** (not hours)
   - Multiple charge/discharge cycles improve plate formation
   - Process is labor-intensive and requires patience

**Performance Expectations:**
- Homemade batteries will NOT match commercial quality
- **Expect 50-70% of commercial battery performance** from homemade cells
- Lower capacity, shorter lifespan (years instead of decades)
- More maintenance required (check water levels frequently)
- **But they work** - adequate for basic electrical storage needs

3. **Assemble cell**:
   - Alternate positive and negative plates
   - Separators between each plate
   - More plates = more capacity
   - Typical: 3-7 plates per cell
4. **Connect cells**:
   - Each cell = 2V
   - 6 cells in series = 12V battery
5. **Add acid**:
   - Fill with sulfuric acid solution (1.265 specific gravity)
   - Let soak, then do initial charge

**Capacity**:
- Depends on plate size and number
- Rough estimate: 1 amp-hour per 10 cm² of plate area
- Example: 10cm × 10cm plates, 5 pairs → 50 Ah battery

**Safety**:
- Sulfuric acid is extremely corrosive
- Wear protection: goggles, gloves, apron
- Work in ventilated area
- Batteries produce hydrogen when charging (explosive)
- No sparks or flames near batteries

**Maintenance**:
- Keep electrolyte level above plates
- Don't discharge below 50% (damages plates)
- Equalization charge monthly (controlled overcharge to balance cells)
- Keep terminals clean

### Other Battery Types

**Alkaline Batteries** (primary cells, not rechargeable in standard form):
- Zinc and manganese dioxide
- Potassium hydroxide electrolyte
- Difficult to make, moderate energy density
- Better as salvage

**Nickel-Iron (NiFe) Batteries**:
- Extremely long-lasting (50+ years possible)
- More forgiving than lead-acid
- Lower energy density
- Expensive to build (needs nickel)
- Construction similar to lead-acid but different chemistry
- Consider for long-term installations

**Critical Advantage - Abuse Tolerance:**

NiFe batteries tolerate abuse that would destroy lead-acid batteries:
- **Deep discharge:** Can discharge to 0V repeatedly without damage (lead-acid sulfates and dies)
- **Overcharge:** Can overcharge for extended periods without harm (lead-acid loses water, warps plates)
- **Neglect:** Can sit discharged for months and still recover (lead-acid sulfates permanently)
- **Temperature extremes:** Operate -20°C to 60°C (lead-acid narrows range)
- **Mechanical shock:** Robust construction tolerates vibration (lead-acid plates can crack)

**Where NiFe advantages matter:**
- Remote installations with infrequent maintenance access
- Harsh environments (extreme temperatures, vibration)
- Applications where battery lifespan matters more than energy density
- Off-grid systems where battery replacement is difficult

**Trade-offs:**
- Higher initial cost (nickel is expensive)
- Lower voltage per cell (1.2V vs 2V for lead-acid)
- Lower energy density (heavier and larger for same capacity)
- **Worth it for:** Critical long-term systems where 50-year lifespan justifies higher cost

**Lithium Batteries**:
- High energy density
- Salvage from phones, laptops, power tools
- **DANGER**: Can catch fire if damaged or overcharged
- Difficult to manufacture (requires lithium metal, precise chemistry)
- Use salvaged cells with proper charge controllers
- Don't attempt to build until advanced chemistry capability

### Mechanical Energy Storage

**Flywheel**:
- Spinning mass stores kinetic energy
- High speed = more energy (energy = ½ × mass × velocity²)
- Advantages: No chemical degradation, fast response
- Disadvantages: Energy loss to friction, requires strong materials
- Use: Short-term storage, power smoothing

**Pumped Water**:
- Pump water uphill when electricity available
- Release through turbine when needed
- Large scale only (need reservoir and elevation)
- Efficiency: 70-85%
- Use: Long-term storage for hydro systems

**Compressed Air**:
- Compress air into tank when electricity available
- Release through air motor when needed
- Efficiency: 50-70%
- Use: Medium-term storage

**Weights and Springs**:
- Lift weight or wind spring when power available
- Descending weight or unwinding spring drives generator
- Use: Very short-term (clocks, timers)

## Electrical Distribution

### Wiring Basics

**Wire Gauge**: Thickness of wire determines current capacity
- Thicker wire (lower gauge number) = more current
- Example: 12 AWG (American Wire Gauge) = 2.05 mm diameter, 20A capacity
- Example: 18 AWG = 1.02 mm diameter, 7A capacity
- Undersized wire overheats and can cause fires

**Wire Insulation Types and Post-Collapse Substitutes:**

Proper insulated wire may become scarce. Alternatives and substitutes:

**Salvage Priority (best to worst):**
1. **Modern insulated wire** (PVC, rubber, THHN) - salvage from buildings, vehicles, appliances
2. **Magnet wire** (enamel-coated thin copper) - from motors, transformers, speakers
3. **Bare copper wire** - must be insulated manually (see below)

**Improvised Insulation Methods:**

1. **Waxed cloth wrapping:**
   - Soak cotton cloth strips in melted paraffin wax or beeswax
   - Wrap tightly around bare wire in overlapping layers
   - Heat with flame briefly to fuse layers together
   - Good for: Low voltage (<50V), dry locations, temporary installations
   - Limitations: Not waterproof long-term, degrades over years

2. **Rubber tubing:**
   - Salvage latex/rubber tubing (medical, automotive vacuum lines)
   - Slide over wire connections and joints
   - Good for: Strain relief, protecting splices, waterproofing
   - Limitations: Rubber degrades with heat and ozone

3. **Varnish coating:**
   - Multiple coats of shellac, polyurethane varnish, or tree resin
   - Apply thin coats, dry between applications
   - Build up 0.5-1mm thickness
   - Good for: Magnet wire replacement, coil windings
   - Limitations: Brittle, cracks with flexing

4. **Physical separation (no insulation):**
   - Mount bare wires on insulators (ceramic, glass, dry wood)
   - Space wires 25mm+ apart to prevent arcing
   - Secure with non-conductive spacers
   - Good for: High voltage outdoor installations, low current
   - Limitations: Dangerous - exposed conductors, weather affects spacing

**Best practice:**
- Salvage modern wire wherever possible
- Use multiple insulation methods (waxed cloth + rubber tubing)
- Avoid bare wire for anything above 24V or high current
- See **Chapter 2.7: Standardization** for wire color coding standards

**Voltage Drop**: Long wire runs lose voltage to resistance
```
Voltage drop = Current × Resistance of wire
```
- Use thicker wire for long distances
- Or use higher voltage (less current for same power, less loss)

**AC vs. DC for Distribution**:
- **DC**: Simpler, battery-compatible, electronic-device friendly
- **AC**: Easier to transform voltage, less loss over distance
- **Recommendation**: Start with DC for small systems, AC for larger

### Transformers (AC Only)

**Purpose**: Change voltage level
- Step up: Increase voltage, decrease current (for transmission)
- Step down: Decrease voltage, increase current (for use)

**How It Works**:
- Two coils of wire around iron core
- AC in primary coil creates changing magnetic field
- Magnetic field induces voltage in secondary coil
- Voltage ratio = turns ratio
  - Example: 1000 turns primary, 100 turns secondary = 10:1 step down
  - 120V in → 12V out

**Construction**:
- Core: Iron laminations (thin sheets to reduce eddy currents)
- Wire: Magnet wire (insulated copper)
- Primary: Designed for input voltage
- Secondary: Designed for output voltage
- Insulation: Between coils, to prevent shorts

**Salvage**: Transformers are everywhere—power supplies, microwaves, electrical equipment. Salvage and reuse, or disassemble and rebuild for your voltage needs.

### Inverters (DC to AC)

**Purpose**: Convert battery/solar DC power to AC

**Simple Inverter** (Square Wave):
- Switching circuit rapidly connects battery positive, then negative, to output
- Creates square wave AC (not true sine wave)
- Efficiency: 75-85%
- Works for: Lights, resistive heaters, simple motors
- Problems with: Electronics, sensitive equipment

**Modified Sine Wave**:
- Switching in multiple steps to approximate sine wave
- Better for electronics
- Efficiency: 80-90%
- More complex circuitry

**Pure Sine Wave**:
- Smooth AC like grid power
- Works with everything
- Efficiency: 85-95%
- Most complex (requires sophisticated electronics)

**Building an Inverter**:
- Early stage: Build simple square wave
- Components: Transistors or MOSFETs for switching, transformer for voltage change
- Control: Oscillator circuit to switch at 50 or 60 Hz
- Details in Chapter 5 (electronics)

### Rectifiers (AC to DC)

**Purpose**: Convert AC to DC (for charging batteries, electronics)

**Diode Bridge**:
- Four diodes arranged to convert AC to pulsing DC
- Add capacitor to smooth pulsing
- Simple, reliable
- Details in Chapter 5

## Power System Sizing

**Determine Your Needs**:
1. **List loads**:
   - Lights: 5-15W per LED, 60-100W per incandescent
   - Computer: 50-300W
   - Tools: 100-1,000W
   - Refrigerator: 100-200W average, 600W startup
2. **Calculate daily usage**:
   - Example: 5 × 10W lights × 4 hours = 200 Wh/day
   - Computer: 100W × 6 hours = 600 Wh/day
   - Total: 800 Wh/day
3. **Add safety margin**: Multiply by 1.5 (for inverter loss, future expansion)
   - 800 × 1.5 = 1,200 Wh/day

**Battery Bank Sizing**:
- Days of autonomy: 2-3 days typical (for cloudy/windless periods)
- Example: 1,200 Wh × 3 days = 3,600 Wh
- Don't discharge below 50%: 3,600 × 2 = 7,200 Wh needed
- At 12V: 7,200 Wh / 12V = 600 Ah
- Use multiple batteries: 6 × 100Ah batteries in parallel

**Generation Capacity**:
- Must produce daily usage on average day
- Example: 1,200 Wh/day
- Solar (5 sun-hours/day in good location): 1,200 / 5 = 240W of panels
- Wind (50% capacity factor): 1,200 / 12 hours = 100W average, need 200W turbine
- Hydro (continuous): 1,200 / 24 = 50W constant (very achievable)

**Voltage Selection**:
- 12V: Easy (car batteries), high current, losses in wiring
- 24V: Better for medium systems, reduces current by half
- 48V: Best for larger systems, even lower current
- Higher voltage = thinner wire, less loss, more dangerous

## Practical Power Systems

### Minimal System (Emergency)
- 1 × 50W solar panel (salvaged)
- 1 × 12V 50Ah battery
- Hand-crank generator backup
- 12V LED lights, phone charging
- Power: Enough for light and communication

### Small Household System
- 4 × 100W solar panels or 500W wind turbine
- 4 × 12V 100Ah batteries (in 24V configuration)
- Charge controller
- Inverter (500W)
- Power: Lights, laptop, phone, small tools, radio

### Workshop System
- 1 kW solar or 2 kW wind or 500W hydro
- 12 × 12V 100Ah batteries (48V, 600Ah)
- Inverter (2,000W continuous, 4,000W surge)
- Power: Above + power tools, welder (short bursts), small machinery

**Why Both Continuous and Surge Ratings Matter:**

Inverters specify two power ratings:
- **Continuous (2,000W):** Power the inverter can deliver indefinitely
- **Surge (4,000W):** Power the inverter can deliver briefly (typically 5-30 seconds)

**Surge capacity is critical for motor startup.** Electric motors draw 3-6× their running current for the first few seconds as they overcome inertia and start spinning.

**Examples:**
- 500W table saw: 500W running, but 2,000-3,000W for 2-3 seconds at startup
- 1/2 HP drill press: 375W running, 1,500-2,000W startup surge
- Refrigerator compressor: 150W running, 600-900W startup

**Without adequate surge capacity:**
- Inverter trips overcurrent protection immediately
- Motor fails to start
- Inverter may be damaged from repeated overload attempts

**Design practice:**
- Continuous rating = sum of all loads you'll run simultaneously
- Surge rating = 2-4× continuous rating (to handle motor startups)
- If workshop has multiple motors, only one typically starts at a time

### Community System
- 10 kW generation (hydro ideal, mix of solar/wind acceptable)
- Large battery bank or direct use
- AC distribution at 120V or 240V
- Power: Multiple households, workshop, small industrial

## Electrical Safety

**Dangers**:
- **Shock**: Can stop heart (50-100 mA through heart is lethal)
  - 12V rarely dangerous (low voltage)
  - 24V can be dangerous in wet conditions
  - 48V+ is dangerous
  - 120V+ is very dangerous
  - Know that even "low voltage" with high current (welders, battery banks) can kill via burns or indirect electrocution
- **Burns**: Arc flash from short circuits (thousands of degrees)
- **Fire**: Overloaded wires, poor connections
- **Explosion**: Hydrogen from batteries, arc igniting flammables

**Safety Practices**:
- **Fuses and circuit breakers**: Disconnect power if overcurrent
- **Insulation**: All wires fully insulated, no exposed conductors
- **Grounding**: Metal enclosures grounded to earth

**Grounding Systems (Critical Safety Feature):**

Grounding provides a safe path for fault current, preventing electrocution. When a live wire touches a metal enclosure, the ground connection conducts fault current back to the source, tripping breakers/fuses instead of electrocuting anyone who touches the equipment.

**How to Ground Equipment:**

1. **Ground Rod Installation:**
   - Drive 8-foot copper or galvanized steel rod into earth
   - Location: Moist soil preferred (better conductivity)
   - Depth: Minimum 8 feet (2.4m), deeper is better
   - Multiple rods: Space 6+ feet apart if soil resistivity is high

2. **Ground Wire Connection:**
   - Use heavy copper wire (6 AWG or thicker for main ground)
   - Connect from ground rod to main electrical panel
   - Bond all metal enclosures (generator housings, battery boxes, inverters, panels) to ground wire
   - Use secure mechanical connections (bolts, clamps), not just wire wrapping

3. **Verification:**
   - Measure resistance from ground wire to earth: Should be <25 ohms (preferably <10)
   - If too high: Add more ground rods, improve soil moisture, use longer rods

**Why grounding works:**
- Normal operation: Ground wire carries no current (just safety backup)
- Fault condition: Live wire contacts metal case → high current flows through ground → trips breaker/fuse instantly
- Without ground: Metal case becomes energized → person touches it → electrocution

**Critical components to ground:**
- Generator frames and housings
- Battery enclosures (metal)
- Inverter chassis
- Metal conduit and junction boxes
- Any metal equipment connected to electrical system

**Grounding vs Neutral:** Not the same. Neutral carries return current (part of circuit). Ground is safety-only, should never carry current during normal operation.

- **Lockout/tagout**: Disconnect power before working, lock switch, tag to warn others
- **Test before touch**: Use multimeter to verify power is off
- **One hand rule**: Keep one hand behind back when working on live circuits (prevents current across heart)
- **Ventilation**: Battery charging produces hydrogen
- **Fire extinguishers**: Dry chemical or CO2 (not water on electrical fires)

**Battery Safety**:
- Ventilate charging area (hydrogen gas)
- No sparks or flames
- Eye protection when working with batteries (acid splash)
- Disconnect batteries by negative terminal first, reconnect negative last

## Progress Milestones

**Year 1**:
- Salvaged solar panels operational
- Battery bank from refurbished car batteries
- Basic 12V DC lighting and device charging

**Year 2-5**:
- Hand-built generator (hydro, wind, or steam)
- Multiple battery banks
- Inverter for AC power
- Small workshop powered

**Year 5-10**:
- Reliable generation (1-5 kW)
- Built replacement batteries
- AC distribution system
- Multiple buildings powered

**Year 10+**:
- Scaled generation (10+ kW)
- Manufacturing capability for generators, batteries, wiring
- Grid-like distribution for community

## Summary

**Key Principles**:
1. **Salvage first**: Solar panels and batteries may outlast your lifetime
2. **Match generation to resources**: Hydro if you have water, wind if you have wind, etc.
3. **Storage is critical**: Batteries enable use of intermittent power
4. **Start small, scale up**: Begin with lighting, expand as capability grows
5. **Safety first**: Electricity can kill—design for safety

**Next Steps**: With electrical power available, you can now:
- Build electronic components (Chapter 5)
- Power precision tools (Chapter 2)
- Perform electrochemistry (Chapter 4)
- Build communication systems (Chapter 6)

Electricity is the enabler. Everything from here depends on it. Build your electrical infrastructure first, then build everything else.
