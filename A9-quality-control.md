# Appendix A9: Quality Control and Testing

*Verification procedures for each technology area to ensure safety, reliability, and reproducibility.*

---

## Why Quality Control Matters

In a rebuilding scenario, you cannot afford:
- **Failures that injure people** (structural collapse, electrical shock, chemical burns)
- **Wasted materials** (limited resources mean every failure costs dearly)
- **Unreliable equipment** (a generator that works sometimes is worse than none)
- **Knowledge loss** (if you can't verify quality, you can't teach it)

Quality control provides:
- Confidence that something works before depending on it
- Standards that allow trade and interchangeability
- Documentation that preserves knowledge
- Safety assurance for dangerous processes

This appendix provides testing procedures organized by technology area, matching the book's chapter structure.

---

## General Principles

### The Testing Hierarchy

1. **Visual inspection**: Look before you measure
2. **Dimensional check**: Does it meet specifications?
3. **Functional test**: Does it work as intended?
4. **Load test**: Does it work under full stress?
5. **Endurance test**: Does it keep working over time?

### Documentation Requirements

Every test should record:
- Date and tester name
- Item being tested
- Test procedure used
- Pass/fail criteria
- Actual results
- Disposition (pass, fail, rework)

### Accept/Reject Decisions

**Accept**: Meets all specifications, safe to use
**Conditional accept**: Minor deviation, acceptable for limited use
**Rework**: Can be fixed, send back for correction
**Reject**: Cannot be fixed safely, scrap or recycle

---

## Part 1: Metallurgy and Metalworking (Chapter 2)

### Raw Material Testing

#### Iron Ore Quality

**Visual inspection**:
- Color: Red-brown (hematite), black (magnetite), yellow-brown (limonite)
- Consistency: Should be uniform, not mixed with excess rock
- Contamination: Remove visible foreign material

**Magnet test** (for magnetite):
- Strong attraction indicates good ore
- Weak attraction suggests low iron content or wrong ore type

**Density test**:
- Good iron ore is noticeably heavy
- Compare to known good sample

**Smelting trial**:
- Small batch test before committing large resources
- Record: ore weight in, iron weight out
- Calculate yield percentage

#### Charcoal Quality

**Visual inspection**:
- Color: Deep black (not brown or gray)
- Sound: Rings like metal when struck (not dull thud)
- Fracture: Conchoidal (shell-like), not crumbly

**Float test**:
- Good charcoal floats high in water
- Waterlogged or poor quality sinks lower

**Burn test**:
- Burns hot with minimal smoke
- Leaves white ash (not black residue)

### Metal Quality Testing

#### Wrought Iron

**Spark test**:
- Dull red sparks with minimal branching
- Short spark stream (6-12 inches)
- Few "bursts" at end

**Bend test**:
- Should bend without cracking
- Heat and bend 90°, cool, bend back
- No cracks = good quality

**Forge weld test**:
- Heat two pieces to welding heat
- Hammer together
- Should bond without crumbling

#### Steel Carbon Content (Approximate)

**Spark test comparison**:

| Carbon % | Spark Color | Stream Length | Branching |
|----------|-------------|---------------|-----------|
| 0.1% (mild) | Dull red | Long | Few |
| 0.4% (medium) | Light orange | Medium | Moderate |
| 0.8% (high) | White | Short | Heavy, explosive |
| 1.0%+ (tool) | White | Very short | Very heavy |

**Hardness test after quench**:
- File should skate on properly hardened high-carbon steel
- File should cut easily on mild steel

**Fracture test** (destructive):
- Break a test piece
- Fine grain = good steel
- Coarse grain = needs normalizing
- Bright crystalline = may be cast iron

### Heat Treatment Verification

#### Hardening

**File test**:
- Hardened steel: file skates, won't cut
- Unhardened: file bites and cuts
- Partially hardened: some resistance

**Hammer test** (careful):
- Properly hardened steel rings clearly
- Soft steel gives dull thud
- Over-hardened may chip

#### Tempering Colors

| Color | Temperature | Use |
|-------|-------------|-----|
| Pale straw | 220°C/430°F | Scrapers, gravers |
| Straw | 230°C/450°F | Drills, taps |
| Dark straw | 240°C/465°F | Punches, dies |
| Bronze | 255°C/490°F | Cold chisels |
| Purple | 270°C/520°F | Axes, knives |
| Blue | 290°C/555°F | Springs, saws |
| Light blue | 310°C/590°F | Screwdrivers |

### Dimensional Inspection

#### Required Measuring Tools

- Steel rule (graduated to 1/64" or 0.5mm)
- Calipers (inside and outside)
- Micrometer (if available)
- Thread pitch gauge
- Feeler gauges
- Surface plate or known flat surface

#### Tolerance Guidelines

| Application | Tolerance |
|-------------|-----------|
| Rough work | ±1/16" (1.5mm) |
| General fit | ±1/32" (0.8mm) |
| Sliding fit | ±0.005" (0.1mm) |
| Press fit | ±0.001" (0.025mm) |
| Precision | ±0.0005" (0.01mm) |

### Weld Quality Testing

**Visual inspection**:
- Uniform bead width
- No visible cracks or porosity
- Proper penetration (examine back side if accessible)
- No undercut at edges

**Bend test**:
- Bend welded sample 90°
- No cracks in weld or heat-affected zone
- Weld should not separate

**Break test** (destructive):
- Break through weld
- Examine fracture surface
- Should show complete fusion, no slag inclusion

---

## Part 2: Textiles (Chapter 2.5)

### Fiber Quality

**Visual inspection**:
- Uniform color
- No mold, mildew, or pest damage
- Appropriate staple length

**Feel test**:
- Cotton: soft, slightly rough
- Wool: springy, may feel slightly oily
- Linen: smooth, cool to touch

**Strength test**:
- Break individual fibers by hand
- Good fiber should resist, then break cleanly
- Weak fiber crumbles or breaks too easily

**Burn test** (fiber identification):

| Fiber | Behavior | Smell | Ash |
|-------|----------|-------|-----|
| Cotton | Burns quickly, afterglow | Paper | Gray, light |
| Wool | Smolders, self-extinguishes | Burning hair | Crushable black bead |
| Linen | Burns quickly | Paper | Gray |
| Silk | Burns slowly, self-extinguishes | Burning hair | Crushable black bead |

### Thread and Yarn Quality

**Twist test**:
- Untwist 1 inch section
- Count turns
- Compare to specification or known good sample

**Tensile test**:
- Suspend known weight
- Note breaking point
- Compare batches for consistency

**Evenness**:
- Run through fingers
- Should be consistent thickness
- No thick/thin spots or lumps

### Fabric Quality

**Thread count**:
- Count threads per inch in both directions
- Compare to specification
- Higher count = finer, denser fabric

**Weight test**:
- Weigh measured sample (e.g., 1 square foot)
- Compare to specification

**Strength test**:
- Cut standard strip (1" × 6")
- Suspend weight, note failure point
- Test both warp and weft directions

**Shrinkage test**:
- Mark measured square on sample
- Wash and dry as intended
- Measure again, calculate shrinkage %

---

## Part 3: Mechanical Systems (Chapter 2.6)

### Gear Inspection

**Visual inspection**:
- Tooth surfaces smooth, no pitting
- Uniform tooth spacing
- No cracks at tooth roots
- Proper finish

**Dimensional checks**:
- Overall diameter (use calipers)
- Bore diameter (for mounting)
- Face width
- Tooth thickness at pitch circle

**Mesh test**:
- Mount gears on shafts
- Roll together by hand
- Should turn smoothly without binding
- Check for consistent backlash

**Paint transfer test**:
- Apply marking compound to one gear
- Roll against mating gear
- Examine contact pattern
- Should show contact across full face width

### Bearing Inspection

**Plain bearings**:
- Inside diameter matches shaft + clearance
- No scoring or gouges on surface
- Oil grooves clear and properly cut

**Ball bearings**:
- Rotate by hand - should be smooth
- No rough spots or clicking
- Minimal radial play (check specification)
- Balls should not fall out when inverted

**Installation check**:
- Shaft should turn freely
- No binding under load
- Proper lubrication applied

### Shaft Inspection

**Straightness**:
- Roll on surface plate
- Check with dial indicator in V-blocks
- Runout should be within tolerance

**Diameter check**:
- Measure at multiple points
- Check for taper (unwanted)
- Compare to bearing/coupling specs

**Surface finish**:
- Visual and feel inspection
- Journal areas should be smooth
- No tool marks or scoring

### Assembled Mechanism Testing

**Free motion test**:
- Move mechanism by hand through full range
- Should move smoothly
- Note any binding or rough spots

**Alignment check**:
- Shafts should be parallel or coaxial as required
- Couplings properly aligned
- Belts/chains track properly

**Load test**:
- Apply working load gradually
- Monitor for unusual noise or vibration
- Check temperature rise in bearings

---

## Part 4: Lubricants and Seals (Chapter 2.8)

### Lubricant Quality

**Visual inspection**:
- Color: appropriate for type
- Clarity: no excessive contamination
- Consistency: proper viscosity

**Water contamination test**:
- Heat small sample
- Listen for crackling (water boiling)
- Observe for spattering

**Viscosity comparison**:
- Compare flow rate to known good sample
- Heat both to same temperature
- Observe flow through identical orifice

**Acid test** (for degraded oil):
- Filter paper spot test
- Dark ring indicates acid contamination
- Oil should be changed

### Seal Inspection

**Visual inspection**:
- No cracks, cuts, or damage
- Correct size for application
- Material appropriate for fluid

**Dimension check**:
- Measure ID, OD, cross-section
- Compare to housing/shaft dimensions
- Calculate compression ratio

**Hardness check** (rubber):
- Press with fingernail
- Compare to known good sample
- Too hard = aged, replace
- Too soft = wrong material

**Installation verification**:
- Seat properly in groove
- Not twisted or pinched
- Correct orientation (lip direction for lip seals)

---

## Part 5: Electricity (Chapter 3)

### Wire Testing

**Continuity test**:
- Use battery and bulb/buzzer
- Touch leads to each end
- Should complete circuit

**Resistance measurement** (if meter available):
- Measure resistance per unit length
- Compare to AWG tables
- High resistance indicates damage or wrong gauge

**Insulation test**:
- Visual inspection for cracks/damage
- Flex test: bend sharply, check for cracking
- Immersion test: submerge in water, check for leaks to conductor

### Generator/Motor Testing

**Open circuit voltage**:
- Run generator at rated speed
- Measure output voltage
- Should match design specification

**Short circuit test** (brief):
- Very brief short to check current capability
- Ammeter in series
- Compare to rated output

**Load test**:
- Connect known load
- Measure voltage and current
- Voltage drop should be within spec

**Insulation resistance**:
- Megohmmeter if available
- Or high-voltage battery test
- Should show no continuity to frame

**Motor no-load test**:
- Run motor with no load
- Current should be 25-50% of rated
- Higher indicates problems

**Motor locked rotor test**:
- Briefly apply voltage to locked motor
- Measure current
- Should be within starting current spec

### Battery Testing

**Open circuit voltage**:
- Measure without load
- Should match rated voltage ±10%
- Low voltage = discharged or damaged

**Load test**:
- Apply known load
- Measure voltage under load
- Significant drop indicates weak battery

**Specific gravity** (lead-acid):
- Use hydrometer
- Fully charged: 1.265-1.285
- Discharged: below 1.200
- Variation between cells indicates problem

**Capacity test**:
- Fully charge
- Discharge at rated rate
- Time until voltage cutoff
- Compare to rated amp-hours

### Circuit Testing

**Continuity verification**:
- Test each connection point to point
- Compare to circuit diagram
- No unintended connections

**Polarity check**:
- Verify + and - correctly connected
- Critical for batteries, diodes, electrolytic capacitors

**Function test**:
- Apply power with protection (fuse)
- Verify intended operation
- Test all modes/functions

**Safety test**:
- No exposed live conductors
- Enclosures properly grounded
- Fuses/breakers correctly sized

---

## Part 6: Basic Electronics (Chapter 5)

### Component Testing

#### Resistors

**Visual inspection**:
- Check color bands
- No burning or discoloration
- Leads intact

**Ohmmeter test**:
- Measure actual resistance
- Compare to marked value
- Tolerance: typically ±5% or ±10%

#### Capacitors

**Visual inspection**:
- No bulging or leaking (electrolytic)
- Leads intact
- No burn marks

**Charging test**:
- Briefly touch to DC source
- Disconnect
- Touch leads together
- Should spark (larger caps)

**Meter test** (if available):
- Capacitance within tolerance
- No short circuit (low resistance)
- No open circuit (infinite resistance)

#### Inductors

**Continuity test**:
- Should show low resistance
- Open = broken winding

**Inductance measurement**:
- Requires LCR meter or calculated test
- Compare to specification

#### Diodes

**Forward/reverse test**:
- Multimeter diode setting
- Forward: low voltage drop (0.3-0.7V silicon)
- Reverse: no conduction (high/infinite)
- Same both directions = shorted
- High both directions = open

#### Transistors

**Junction test**:
- Test each junction like a diode
- B-E: should conduct one way
- B-C: should conduct one way
- C-E: should not conduct

**Gain test** (if equipment available):
- Apply known base current
- Measure collector current
- Calculate beta (hFE)
- Compare to datasheet

### Circuit Board Testing

**Visual inspection**:
- No solder bridges
- All joints shiny and wet-looking
- No cold solder joints (dull, grainy)
- No cracked or lifted traces

**Continuity verification**:
- Check each trace for continuity
- Verify no shorts between adjacent traces
- Check power and ground distribution

**Power supply test**:
- Apply power through current-limited source
- Check for excessive current draw
- Verify voltage at test points

**Signal tracing**:
- Inject known signal at input
- Trace through circuit
- Verify expected signal at each stage

---

## Part 7: Communications (Chapter 6)

### Telegraph Testing

**Key test**:
- Continuity when pressed
- No continuity when released
- Clean, positive action

**Sounder test**:
- Apply voltage
- Should click distinctly
- Armature gap correct

**Line test**:
- Continuity end to end
- Insulation resistance to ground
- Measure line resistance

**Complete system test**:
- Send test pattern (SOS, test message)
- Verify clear reception
- Adjust as needed

### Radio Testing

**Transmitter output power**:
- RF power meter or dummy load with lamp
- Measure at antenna output
- Compare to design specification

**Frequency check**:
- Frequency counter or receiver comparison
- Should be on intended frequency
- Check for stability (drift)

**Modulation quality**:
- Listen on receiver
- Voice should be clear, not distorted
- Check modulation percentage if possible

**Antenna testing**:
- SWR measurement (standing wave ratio)
- Below 2:1 is acceptable
- Below 1.5:1 is good
- High SWR indicates antenna/feedline problem

**Receiver sensitivity**:
- Tune to weak station
- Note signal strength
- Compare to reference receiver

---

## Part 8: Chemistry (Chapter 4)

### Acid Testing

**Concentration verification** (comparative):
- Reaction rate with known metal
- Compare to standard sample
- Faster reaction = higher concentration

**Purity check**:
- Color should be appropriate (clear for HCl, clear to pale for H2SO4)
- No suspended solids
- No unusual smell (beyond expected)

**Neutralization test**:
- React measured amount with known base
- Compare to expected ratio

### Base Testing

**Strength verification**:
- pH indicator or measurement
- Reaction rate with acid
- Compare to standard

**Purity**:
- Visual inspection
- No unusual colors or odors
- Dissolves clearly in water

### General Chemical Safety Checks

**Container integrity**:
- No leaks or cracks
- Proper seal
- Correct labeling

**Storage verification**:
- Incompatible chemicals separated
- Proper ventilation
- Emergency equipment accessible

**Handling readiness**:
- PPE available and functional
- Neutralization materials ready
- First aid accessible

---

## Part 9: Medicine (Chapter 3.5)

### Surgical Instrument Testing

**Visual inspection**:
- No rust or corrosion
- No chips or nicks on cutting edges
- Joints move freely
- Locks engage properly

**Sharpness test** (cutting instruments):
- Should cut clean, not tear
- Test on appropriate material
- Compare to known good instrument

**Sterilization verification**:
- Heat indicator shows proper exposure
- Time and temperature logged
- Instruments stored properly after

### Medicinal Preparations

**Visual inspection**:
- Correct color and consistency
- No contamination or foreign material
- Proper container and labeling

**Potency verification** (when possible):
- Compare to known standard
- Test on model system if available
- Note preparation date and storage

**Dosage accuracy**:
- Weigh or measure prepared dose
- Compare to intended dose
- Verify measuring equipment

### Water Quality

**Visual inspection**:
- Clear, no cloudiness
- No floating particles
- No unusual color

**Smell test**:
- No unusual odors
- Chlorine smell (if treated)
- No sulfur or decay smell

**Simple tests**:
- Boiling point (indicates dissolved solids)
- Residue after evaporation
- pH if indicator available

---

## Part 10: Computing (Chapters 7-13)

### Vacuum Tube Testing

**Filament test**:
- Apply filament voltage
- Should glow appropriately
- No filament = tube is dead

**Emission test**:
- Proper cathode temperature
- Measure plate current
- Compare to tube specifications

**Gas test**:
- Blue glow indicates gas contamination
- Soft tubes may be acceptable
- Hard tubes with gas should be replaced

### Semiconductor Testing

**Diode test**: (See Part 6)

**Transistor test**: (See Part 6)

**IC functional test**:
- Apply power at correct voltage
- Test each pin function
- Compare to datasheet specifications

### Computer System Testing

**Power-on self-test**:
- Observe boot sequence
- Note any error codes
- All indicators respond correctly

**Memory test**:
- Write pattern to all locations
- Read back and verify
- Test with different patterns

**Peripheral test**:
- Each device responds
- Data transfer correct
- No errors in operation

**Software verification**:
- Known test programs
- Compare output to expected
- Test boundary conditions

---

## Part 11: Quality Control Records

### Inspection Log Template

```
INSPECTION LOG

Date: _____________
Inspector: _____________
Item/Batch: _____________
Specification reference: _____________

INSPECTION CHECKLIST:
Item                    | Spec      | Actual    | Pass/Fail
------------------------|-----------|-----------|----------
                        |           |           |
                        |           |           |
                        |           |           |

NOTES:


DISPOSITION:
[ ] Accept
[ ] Conditional accept - conditions: _______________
[ ] Rework - instructions: _______________
[ ] Reject - reason: _______________

Inspector signature: _____________
```

### Calibration Record Template

```
CALIBRATION RECORD

Instrument: _____________
Serial/ID: _____________
Location: _____________

CALIBRATION HISTORY:
Date       | Standard Used | Reading | Adjustment | Technician
-----------|---------------|---------|------------|----------
           |               |         |            |
           |               |         |            |

NEXT CALIBRATION DUE: _____________

NOTES:

```

### Batch Record Template

```
BATCH PRODUCTION RECORD

Product: _____________
Batch number: _____________
Date started: _____________ Date completed: _____________
Quantity: _____________

RAW MATERIALS:
Material        | Spec       | Lot/Source | Qty Used  | Verified
----------------|------------|------------|-----------|----------
                |            |            |           |
                |            |            |           |

PROCESS PARAMETERS:
Parameter       | Spec       | Actual     | In Spec?
----------------|------------|------------|----------
                |            |            |
                |            |            |

TESTING RESULTS:
Test            | Spec       | Result     | Pass/Fail
----------------|------------|------------|----------
                |            |            |
                |            |            |

DISPOSITION:
[ ] Released for use
[ ] Held pending: _______________
[ ] Rejected: _______________

Signatures:
Production: _____________ Date: _____
Quality: _____________ Date: _____
```

---

## Part 12: Establishing a Quality System

### Minimum Requirements

**Documentation**:
- Written specifications for products
- Written procedures for processes
- Inspection records maintained

**Measurement**:
- Calibrated measuring instruments
- Reference standards
- Regular calibration schedule

**Training**:
- Inspectors trained on procedures
- Production workers understand quality requirements
- Documentation of training

**Authority**:
- Clear responsibility for quality decisions
- Authority to stop production if needed
- Path for resolving disputes

### Quality Roles

**Production worker**:
- Follow written procedures
- Self-inspect work
- Report problems

**Inspector**:
- Independent verification
- Record results
- Make accept/reject decisions

**Quality coordinator**:
- Maintain quality system
- Train others
- Trend analysis and improvement

### Continuous Improvement

**Track metrics**:
- First-pass yield (% accepted first try)
- Defect rates by type
- Rework rates

**Analyze failures**:
- Root cause analysis
- Corrective action
- Prevent recurrence

**Review and update**:
- Regular procedure reviews
- Incorporate lessons learned
- Update specifications as capability improves

---

## Cross-References

- **Chapter 2.7: Standardization** - Measurement systems and standards
- **A5: Standard Specifications** - Specifications to test against
- **A6: Glossary** - Terminology definitions
- **Chapter 17: Governance** - Organizational quality structures

---

*"The bitterness of poor quality remains long after the sweetness of low price is forgotten." — Benjamin Franklin (attributed)*
