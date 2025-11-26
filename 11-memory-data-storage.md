# Chapter 11: Memory and Data Storage

## The Memory Hierarchy

Every computer needs memory—both temporary (volatile) and permanent (non-volatile) storage. Without memory:
- No place to store programs
- No place to store data being processed
- No way to save work
- Computer must be reprogrammed after every power cycle

The memory hierarchy trades off **speed vs. capacity vs. cost**:
- **Registers**: Fastest, smallest, most expensive (inside CPU)
- **Cache**: Very fast, small, expensive (on or near CPU)
- **Main Memory (RAM)**: Fast, medium size, moderate cost
- **Secondary Storage**: Slower, large, cheap (hard drives, SSD, tape)
- **Tertiary Storage**: Slowest, massive, cheapest (archived tape, optical)

Post-collapse, you'll rebuild this hierarchy from the bottom up.

## Volatile Memory (RAM)

### Static RAM (SRAM)

**Principle**: Flip-flops store bits
- Each bit: 4-6 transistors (cross-coupled inverters)
- Holds data as long as power applied
- No refresh needed
- Fast access (<10 ns modern, 100-1,000 ns early)

**Construction**:

**Discrete SRAM** (Early Method):
- Build flip-flops from individual transistors or tubes
- Each bit requires 2 tubes or 4-6 transistors
- Practical for small amounts: 8-256 bytes
- Example: 256 bytes = 2,048 bits = 8,192-12,288 transistors
- Plus address decoding and control logic

**Integrated SRAM**:
- Many bits on single chip
- 6-transistor cell (6T SRAM) standard
- Density: ~120-140 F² per bit (F = feature size)
  - 10 µm process: ~140 × 100 µm² = 14,000 µm² per bit
  - Can fit ~7,000 bits per mm²
  - 1 cm² chip: ~700,000 bits (87.5 KB)
  - Practical: 1K-16K bits per chip (early), MB+ per chip (modern)

**SRAM Cell Design** (6T):
```
        VDD
         |
    T1   |   T2
     |---|---|
     |       |
     |       |
 WL→ T5     T6 ←WL
     |       |
     |       |
    BL      /BL
```
- T1-T4: Cross-coupled inverters (storage)
- T5-T6: Access transistors (controlled by word line)
- BL, /BL: Bit lines (differential, for noise immunity)

**Organization**:
- Array of cells in rows and columns
- Row decoder: Selects word line (activates one row)
- Column decoder: Selects bit lines (chooses which bits to read/write)
- Sense amplifiers: Detect small voltage difference on bit lines
- Write drivers: Force bit lines to desired voltage for writing

**Example**: 1K × 8 SRAM (1 kilobyte)
- 1,024 addresses × 8 bits = 8,192 bits
- Organize as 128 rows × 64 columns
- 10 address bits: 7 for row, 3 for column byte
- Transistor count: 8,192 × 6 + decoding + control ≈ 50,000-60,000

**Advantages**:
- Fast
- Simple to interface (no refresh)
- Low power when not switching

**Disadvantages**:
- Low density (many transistors per bit)
- Expensive
- Uses power when holding data (leakage)

**Uses**:
- CPU cache
- Register files
- Small fast buffers
- Embedded memory in ASICs

### Dynamic RAM (DRAM)

**Principle**: Capacitor stores charge (bit)
- Each bit: 1 transistor + 1 capacitor (1T1C)
- Charge leaks over time (milliseconds)
- Must refresh periodically (read and rewrite)
- Slower than SRAM but much denser

**DRAM Cell**:
```
    Word Line (WL)
        |
        T (transistor)
        |
        C (capacitor)
        |
       GND
```
- WL high: Transistor conducts, capacitor connects to bit line
- Read: Bit line precharged to VDD/2, capacitor shares charge, sense amplifier detects difference
- Write: Bit line driven to VDD (1) or GND (0), charge transfers to capacitor

**Capacitor Construction**:
- Early: Planar capacitor (plates in substrate)
- Later: Trench capacitor (vertical hole in silicon)
- Modern: Stacked capacitor (3D structure above transistor)
- Need ~25-50 fF (femtofarads) minimum for reliable sensing

**Cell Size**:
- Theoretical: ~6-8 F² per bit (much smaller than 6T SRAM)
- Practical: 10-20 F² with access circuitry
- 10 µm process: ~1,000-2,000 µm² per bit
  - Can fit ~500-1,000 bits per mm²
  - 10× denser than SRAM

**Refresh**:
- Capacitor leaks, must rewrite within 8-64 ms
- Refresh controller reads each row sequentially
- During refresh, memory unavailable
- Overhead: ~1-5% of time spent refreshing

**Organization**:
- Similar to SRAM: Rows and columns
- Address multiplexed: Row address first (RAS), then column address (CAS)
  - Saves pins (don't need 20+ address pins)
  - Example: 1M × 1 DRAM (1 Megabit)
    - 20-bit address total
    - Multiplex: 10-bit row, 10-bit column
    - Only need 10 address pins plus RAS, CAS control

**Timing**:
- RAS-to-CAS delay (tRCD): 15-20 ns (modern), 100-300 ns (early)
- CAS access time (tCAC): 10-15 ns (modern), 80-200 ns (early)
- Refresh period: 64 ms typical
- Row cycle time: 60-100 ns (modern), 300-600 ns (early)

**Advantages**:
- High density (4-8× more than SRAM)
- Cheaper per bit

**Disadvantages**:
- Slower
- Requires refresh logic
- More complex interface
- Manufacturing more difficult (need good capacitors)

**Uses**:
- Main system RAM (from 1970s onward)
- Dominant memory technology for PCs, servers

**Evolution**:
- **FPM DRAM** (Fast Page Mode, 1980s): Access multiple columns in one row
- **EDO DRAM** (Extended Data Out, 1990s): Overlaps operations
- **SDRAM** (Synchronous, 1990s): Clocked, pipelined
- **DDR SDRAM** (Double Data Rate, 2000s): Transfers on both clock edges
- **DDR2, DDR3, DDR4, DDR5** (2000s-2020s): Faster, lower voltage, higher density

**Post-Collapse Path**:
- Start with SRAM (simpler to build)
- Progress to DRAM as process matures
- Many years before DDR technology

### Magnetic Core Memory

**Historical Importance**: Dominated 1955-1975
- Non-volatile (retains data when power off)
- Reliable
- No refresh
- Moderate speed

**Principle**: Tiny ferrite rings (cores) store magnetic polarity
- Magnetize clockwise = 1
- Magnetize counterclockwise = 0
- Hysteresis keeps magnetization without power

**Core**:
- Ferrite toroid, 0.5-2 mm outer diameter
- Hole for threading wires
- Material: Manganese-zinc ferrite or similar

**Operation**:
- **Write**: Pass current through X and Y wires
  - Half-select current: Not enough to switch core alone
  - Full-select (X + Y): Switches core
  - Inhibit wire: Prevents writing 1 if 0 desired
- **Read**: Destructive (resets core to 0)
  - If core was 1: Large signal on sense wire
  - If core was 0: Small signal
  - Must rewrite after reading

**Array Construction**:
```
      X wires (rows)
         |||
    →→→→→→→→→→ Y wires (columns)
         |||
    Each intersection: One core threaded by X, Y, Sense, Inhibit wires
```

- Example: 64 × 64 array = 4,096 bits (512 bytes)
- Each core has 4 wires through it: X, Y, Sense, Inhibit
- Hand-threading cores was tedious labor (later automated)

**Timing**:
- Cycle time: 0.5-2 µs (early), 200-500 ns (late)
- Slower than SRAM but faster than mechanical storage

**Advantages**:
- Non-volatile
- Radiation-hard (still used in space applications)
- No power needed to retain data
- Reliable (no semiconductor failures)

**Disadvantages**:
- Large, heavy
- Expensive (labor-intensive assembly)
- Destructive read (must rewrite)
- Slower than semiconductor RAM

**Making Cores**:
- Mix ferrite powder with binder
- Form into toroid shape
- Fire in kiln (1,200-1,400°C)
- Precise magnetic properties needed

**Threading**:
- Manual: Use needle or specialized tool
- Each core threaded with 4 wires in specific order
- Very tedious for large arrays
- Automated machines developed (1960s) but still slow

**Post-Collapse Viability**:
- Easier than early semiconductor RAM (no transistors)
- But labor-intensive
- Good intermediate technology while developing ICs
- Non-volatility valuable (survives power outages)

**Recommendation**: Build small core memories (256-4,096 bytes) to learn and for critical applications. Transition to semiconductor RAM as capability develops.

## Non-Volatile Memory (Long-Term Storage)

### Mask ROM (Read-Only Memory)

**Principle**: Permanent pattern hard-wired during manufacturing
- Cannot be changed
- Used for firmware, boot code, character sets

**Construction**:

**Diode Matrix**:
- Grid of wires (rows and columns)
- Diode at intersection = 1
- No diode = 0
- Row selected, columns indicate bits

**Transistor Matrix**:
- Transistor presence/absence or threshold voltage
- During manufacturing, metal layer connects (or doesn't) transistor to bit line

**Programming**:
- Done during IC fabrication (mask layer)
- Requires new mask for each program
- Expensive for one-off, cheap for mass production

**Uses**:
- Bootstrap code (runs on power-up, loads OS)
- Character generators (fonts for displays)
- Lookup tables
- Microcode ROMs (in CPUs)

**Making ROM**:
- Design data pattern
- Convert to mask layout
- Fabricate IC with pattern
- Test

### PROM (Programmable ROM)

**Principle**: Manufactured with all bits set to 1 (or 0)
- User "blows" fuses to change bits
- One-time programmable (OTP)

**Construction**:
- Each bit has fusible link (thin wire or polysilicon)
- High current vaporizes link
- Blown = 0, intact = 1 (or vice versa)

**Programming**:
- PROM programmer device
- Applies high voltage/current to blow fuses
- Irreversible

**Advantages**:
- User-programmable
- No custom manufacturing
- Moderate cost

**Disadvantages**:
- One-time only (cannot erase)
- Programming requires special equipment

**Uses**:
- Small-scale production (10s to 1,000s)
- Prototyping
- Field updates (if socketed, replace chip)

### EPROM (Erasable PROM)

**Principle**: Floating gate MOSFET stores charge
- Charge trapped on gate = programmed state
- UV light provides energy to discharge
- Electrically re-programmable after erasing

**Construction**:
- MOSFET with two gates:
  - Control gate (normal gate)
  - Floating gate (isolated, between control gate and channel)
- Charge on floating gate raises threshold voltage

**Programming**:
- High voltage (12-25V) on drain and gate
- Hot electron injection puts charge on floating gate
- Programmed cell: High threshold, won't conduct (reads as 0 or 1 depending on convention)

**Erasing**:
- Expose to UV light (254 nm typical) for 10-20 minutes
- Photons provide energy for electrons to escape floating gate
- Entire chip erased at once
- Quartz window in package for UV exposure

**Typical Parts**:
- 2716: 2K × 8 (16 Kbit)
- 2732: 4K × 8 (32 Kbit)
- 27C256: 32K × 8 (256 Kbit)
- Up to several Mbit

**Advantages**:
- Re-programmable (100-1,000 erase cycles)
- Non-volatile (retains data 10-40 years)
- Standard part (no custom manufacturing)

**Disadvantages**:
- Requires UV eraser
- Slow erase (minutes)
- Bulk erase only (can't erase individual bytes)
- Programming time: ~100 µs to 1 ms per byte

**Uses**:
- Development and prototyping
- Low-volume production
- Firmware storage

**Making EPROMs**:
- Requires ability to make floating gate transistors
- More complex than standard CMOS
- Additional process steps (double polysilicon)
- Achievable with mature IC process

### EEPROM (Electrically Erasable PROM)

**Principle**: Similar to EPROM but electrically erasable
- Thin tunnel oxide allows electrons to tunnel on/off floating gate
- Can erase individual bytes
- No UV needed

**Construction**:
- Floating gate MOSFET with thin oxide
- Control circuitry for erase/program

**Programming**:
- High voltage (10-20V) applied to control gate
- Electrons tunnel through oxide to floating gate

**Erasing**:
- Reverse voltage
- Electrons tunnel back off floating gate

**Characteristics**:
- Byte-erasable (some types)
- Electrically erasable
- Slower than RAM (ms to write)
- Limited erase cycles (10,000-100,000 typical, 1,000,000+ for modern)
- Non-volatile

**Uses**:
- Configuration data
- Calibration values
- Small data storage
- Firmware in embedded systems

### Flash Memory

**Principle**: EEPROM variant optimized for density and speed
- Erases in blocks, not bytes
- NAND flash: High density (for storage)
- NOR flash: Faster read (for code execution)

**NAND Flash**:
- Cells in series (like NAND gates)
- Very high density
- Block erase (4-512 KB blocks)
- Sequential read fast, random read slower
- Used in: USB drives, SD cards, SSDs

**NOR Flash**:
- Cells in parallel (like NOR gates)
- Lower density than NAND
- Byte-addressable read
- Slower write than NAND
- Used in: Code storage, BIOS

**Characteristics**:
- High density (multi-level cell: 2+ bits per transistor)
- Fast read, moderate write
- Limited erase cycles (1,000-100,000 depending on type)
- Wear leveling required for long life

**Making Flash**:
- Advanced process needed
- Requires precise oxide thickness control
- Multi-level cell (MLC) needs very tight threshold voltage control
- Likely decades before achievable post-collapse

**Salvage Priority**: High. Flash drives and SD cards from 2025 will last for years. Stockpile diverse capacities.

## Magnetic Storage

### Magnetic Tape

**Principle**: Magnetize particles on tape to store bits
- Moving tape past read/write head
- Sequential access (must wind/rewind)

**Recording Method**:
- Longitudinal: Magnetization along tape direction (traditional)
- Perpendicular: Magnetization perpendicular to tape (higher density)

**Tape Medium**:
- Base: Polyester film (PET) or similar
- Coating: Magnetic particles (iron oxide, chromium dioxide, metal particles)
- Binder: Holds particles to base

**Making Magnetic Tape**:
1. **Base film**: Polyester (see Chapter 4, plastics)
2. **Magnetic coating**:
   - Iron oxide (Fe₂O₃ or Fe₃O₄): Make by precipitating from iron salt solution
   - Mix with binder (polyurethane, vinyl, etc.)
   - Coat onto film (precision coating)
   - Orient particles in magnetic field while wet
   - Dry and cure
3. **Slitting**: Cut to width (1/4", 1/2", 1", etc.)
4. **Wind onto reels**

**Read/Write Head**:
- Electromagnet with gap
- Write: Current through coil magnetizes gap, transfers pattern to tape
- Read: Moving magnetized tape induces voltage in coil
- Material: Permalloy (nickel-iron alloy), ferrite, or metal

**Mechanism**:
- Supply reel and take-up reel
- Motors for winding
- Capstan and pinch roller for constant speed
- Tension control
- Tape guides

**Encoding**:
- Simple: NRZ (Non-Return to Zero): 1 = positive, 0 = negative
- Better: NRZI, PE (Phase Encoding), GCR (Group Code Recording)
- More complex: Run-length limited (RLL) codes

**Capacity**:
- Early (1950s): ~100 bytes per inch
- 1970s: 800-1600 bytes per inch
- 1990s: 10-100 KB per inch
- 2000s: MB per inch
- Reel length: 2,400 feet typical (732 meters)
- Cassette: Varies (C60 = 60 minutes audio = ~280 meters)

**Example**: 1/2" tape, 1600 BPI, 2400 feet
- Capacity: 1600 × 12 × 2400 = 46 million bytes ≈ 46 MB

**Advantages**:
- High capacity
- Low cost per byte
- Long archival life (10-30+ years if stored properly)
- Portable

**Disadvantages**:
- Sequential access (slow to find data)
- Mechanical wear
- Sensitive to temperature, humidity, magnetic fields

**Uses**:
- Backup
- Archival storage
- Data interchange
- Program loading (early computers)

**Salvage**: Tape drives from 2025 (LTO tape, etc.) work for decades. But manufacturing tape is relatively easy, so worth learning.

### Floppy Disk

**Principle**: Rotating magnetic disk
- Random access (can seek to any track)
- Slower than hard disk but removable

**Construction**:
- **Disk**: Mylar (polyester) sheet, circular
- **Coating**: Magnetic particles (iron oxide or similar)
- **Jacket**: Protective envelope (flexible for floppy)
- **Hub**: Center hole for spindle

**Sizes**:
- 8": 80 KB to 1.2 MB (early, 1970s)
- 5.25": 360 KB to 1.2 MB (1980s)
- 3.5": 720 KB to 2.88 MB (1980s-2000s)

**Organization**:
- **Tracks**: Concentric circles
- **Sectors**: Divisions of track (typically 512 bytes each)
- **Formatting**: Creates track and sector structure

**Read/Write Head**:
- Contacts disk surface (or flies very close)
- Magnetic head (similar to tape)

**Mechanism**:
- Motor spins disk (300-360 RPM typical)
- Stepper motor moves head radially (selects track)
- Head load solenoid (presses head to disk when accessing)

**Controller**:
- Interface between computer and drive
- Handles timing, encoding, error checking
- Classic: NEC 765 controller chip (or compatible)

**Making Floppy Disks**:
- Simpler than hard disk (no clean room needed)
- Coat disk with magnetic particles
- Precision: Track spacing ~48 TPI (tracks per inch) for 5.25", ~135 TPI for 3.5"
- Cut to size, insert in jacket
- Add hub, write-protect notch, index hole

**Advantages**:
- Removable (multiple disks, unlimited capacity)
- Random access
- Moderate speed
- Relatively cheap

**Disadvantages**:
- Low capacity (vs. hard disk)
- Slow (vs. hard disk)
- Fragile (disk can be damaged)
- Limited life (wear from head contact)

**Uses**:
- Program distribution
- Data transfer
- Backup (for small amounts)
- Booting operating system

### Hard Disk Drive (HDD)

**Principle**: Rigid rotating platters with magnetic coating
- High speed, high density
- Fixed (not removable, normally)

**Construction**:
- **Platters**: Aluminum or glass substrate, magnetic coating
  - Multiple platters stacked on spindle
- **Heads**: Magnetic read/write heads
  - One head per platter surface
  - Flies on air bearing (not touching) at high speed
  - Flying height: 10-50 nm (modern), 500-1000 nm (early)
- **Actuator**: Voice coil motor positions heads
  - Fast, precise seeking
- **Spindle**: Motor spins platters (3,600-15,000 RPM)
- **Controller**: On-board electronics
- **Enclosure**: Sealed (filtered air, keeps dust out)

**Recording**:
- Longitudinal (early): Bits along track
- Perpendicular (modern): Bits perpendicular to platter
  - Higher density (grains oriented vertically)

**Capacity Evolution**:
- 1956 (IBM 350): 3.75 MB, 50× 24" platters, 1,200 lb
- 1973 (IBM 3340): 70 MB, 8" platters
- 1980: 10 MB common
- 1990: 100 MB to 1 GB
- 2000: 10-100 GB
- 2010: 500 GB to 2 TB
- 2020: 1-20 TB

**Density Factors**:
- Track density: Tracks per inch (TPI)
  - Early: 100-200 TPI
  - Modern: 300,000+ TPI
- Linear density: Bits per inch along track
  - Early: 1,000-5,000 BPI
  - Modern: 1,000,000+ BPI
- Areal density: Product of track and linear density
  - Early: ~1 Mbit per square inch
  - Modern: 1-2 Tbit per square inch

**Manufacturing Challenges**:
- **Clean room**: Dust particles cause head crashes
  - Class 100 or better (100 particles per cubic foot)
- **Precision platters**: Flatness, roundness critical
  - Platter run-out: <25 µm
- **Head technology**:
  - Inductive heads (early)
  - Thin-film heads
  - Magnetoresistive (MR) heads
  - Giant magnetoresistive (GMR) heads
  - Tunnel magnetoresistive (TMR) heads
- **Servo system**: Position heads accurately
  - Embedded servo information on platters
  - Feedback control system
- **Interface**: IDE/ATA, SCSI, SATA, SAS
  - Complex protocols

**Post-Collapse Timeline**:
- Hard disks are among the most difficult devices to manufacture
- Require precision machining, clean room, advanced materials, complex electronics
- Expect 40-60+ years before indigenous manufacturing possible
- Salvage HDDs from 2025 for as long as they last (5-15 years typically, longer if stored unpowered)

**Solid-State Drives (SSDs)**:
- Flash memory instead of magnetic platters
- No moving parts
- Faster, lower power, more reliable
- More expensive per GB (but gap closing by 2025)
- Requires advanced flash manufacturing
- Salvage priority: High

## Optical Storage

### Compact Disc (CD)

**Principle**: Pits and lands on reflective surface
- Laser reads by detecting reflection changes
- Read-only (CD-ROM) or write-once (CD-R) or rewritable (CD-RW)

**CD-ROM** (Read-Only):
- Manufactured with pits
- Aluminum reflective layer
- Protective layers
- 650-700 MB capacity

**CD-R** (Recordable):
- Organic dye layer (changes reflectivity when heated by laser)
- One-time write
- 650-700 MB

**CD-RW** (Rewritable):
- Phase-change material (switches between crystalline and amorphous states)
- Different reflectivity
- 1,000+ rewrite cycles

**Reading**:
- Laser (780 nm infrared)
- Photodetector senses reflection
- Pit-land transitions encode data

**Writing** (CD-R/RW):
- Higher-power laser heats dye or phase-change material
- Changes optical properties

**Manufacturing CD-ROM**:
1. **Master**: Photoresist on glass, laser exposes pattern
2. **Stamper**: Electroform metal stamper from master
3. **Injection molding**: Polycarbonate disc with pits
4. **Metallization**: Aluminum layer
5. **Lacquer coating**: Protection
6. **Label printing**

**Advantages**:
- High capacity (for 1980s-1990s)
- Durable (if handled properly)
- Mass production cheap (stamping)
- Standardized format

**Disadvantages**:
- Read-only (CD-ROM) or write-once (CD-R)
- Slower than HDD
- Fragile (scratches affect reading)

**DVD** (Digital Versatile Disc):
- Smaller pits, closer tracks
- 4.7 GB single-layer, 8.5 GB dual-layer
- 650 nm red laser

**Blu-ray**:
- Even smaller pits
- 25-50 GB per layer
- 405 nm blue-violet laser

**Post-Collapse Viability**:
- CD/DVD drives salvaged from 2025 will work for decades (if lasers last)
- Manufacturing blank media (CD-R) requires chemical synthesis (organic dyes)
- Manufacturing drives requires precision optics, laser diodes, complex electronics
- Expect many decades before indigenous production

## Data Encoding and Error Correction

### Encoding Schemes

**Why Encode**: Raw binary data not optimal for storage
- Clock recovery: Need transitions to synchronize
- DC balance: Avoid long runs of 1s or 0s (affects servo systems)
- Error detection: Add redundancy to detect/correct errors

**NRZ** (Non-Return to Zero):
- 1 = high voltage, 0 = low voltage
- Simple but no clock recovery
- Used in early systems

**NRZI** (NRZ Inverted):
- Transition = 1, no transition = 0
- Slightly better

**FM** (Frequency Modulation):
- Clock transition every bit time
- Data transition for 1, none for 0
- 50% efficiency (need 2 flux changes per bit)

**MFM** (Modified FM):
- Clock transition only if needed
- ~100% efficiency

**RLL** (Run-Length Limited):
- Encodes groups of bits with constrained run lengths
- Higher efficiency
- Examples: RLL 2,7 (used in floppy disks)

### Error Correction

**Why Needed**: Storage media have defects, bits can flip

**Parity** (Simplest):
- Add extra bit so total 1s is even (or odd)
- Detects single-bit error
- Cannot correct

**Hamming Code**:
- Multiple parity bits
- Can detect 2-bit error, correct 1-bit error
- Overhead: log₂(n) bits for n-bit data

**CRC** (Cyclic Redundancy Check):
- Polynomial division
- Detects burst errors
- Doesn't correct
- Common in communications

**Reed-Solomon**:
- Powerful error correction
- Used in CDs, DVDs, QR codes
- Can correct multiple byte errors
- More complex

**LDPC** (Low-Density Parity Check):
- Modern code
- Near-optimal performance
- Complex decoder
- Used in flash memory, hard drives, satellites

## File Systems

### Purpose

**Organization**: How files are stored on disk
- Track allocation
- Directory structure
- Metadata (file names, sizes, dates, permissions)

### Simple File Systems

**FAT** (File Allocation Table):
- Developed for floppy disks (late 1970s)
- Used in DOS, Windows 9x
- Variants: FAT12, FAT16, FAT32

**Structure**:
- Boot sector: Partition info, file system parameters
- FAT: Table linking clusters (allocation units)
- Root directory: Fixed location and size (FAT12/16)
- Data area: File contents

**File Allocation**:
- Each cluster (group of sectors) has entry in FAT
- Entry points to next cluster (linked list) or end-of-file
- Free clusters marked with 0
- Find free cluster: Scan FAT

**Advantages**:
- Simple
- Well-documented
- Universal support

**Disadvantages**:
- No permissions, security
- File size limits (2-4 GB depending on variant)
- Fragmentation
- Slow for large disks

**EXT** (Extended File System, Linux):
- More advanced
- Permissions, ownership
- Symbolic links
- Larger files and volumes

**NTFS** (Windows NT File System):
- Journaling (recovery from crashes)
- Permissions, encryption
- Large file support
- Complex

### Implementing a File System

**On Your Computer**:
1. Define format (cluster size, FAT size, etc.)
2. Write formatter (creates file system on blank disk)
3. Write low-level I/O (read/write sectors)
4. Write FAT management (allocate, free, link clusters)
5. Write directory management (create, delete, list files)
6. Write file operations (open, close, read, write)
7. Integrate with OS or provide API for programs

**Start Simple**: Single-directory, small files, no permissions. Add features gradually.

## Summary: Memory Development Stages

**Stage 1 (Year 5-15): Core Memory and Tape**
- Magnetic core memory (256 bytes to 4 KB)
- Magnetic tape storage (cassette or reel-to-reel)
- Paper tape (for backup)

**Stage 2 (Year 15-30): Early Semiconductor Memory**
- SRAM (discrete or small ICs, 256 bytes to 4 KB)
- PROM/EPROM (1-8 KB)
- Floppy disks (100-500 KB)

**Stage 3 (Year 30-50): Integrated Memory**
- DRAM (64-256 KB)
- Larger EPROM/EEPROM (64-256 KB)
- Hard disk (salvaged, 10-100 MB)
- CD-ROM (salvaged)

**Stage 4 (Year 50-75): Modern Memory**
- DRAM (MB to tens of MB)
- Flash memory (first attempts, low capacity)
- Hard disk (indigenous manufacturing, 10-100 MB)
- CD-R manufacturing

**Stage 5 (Year 75-100+): Advanced Storage**
- GB-range DRAM
- High-capacity flash
- GB+ hard disks
- DVD and beyond

## Practical Advice

### Salvage First
- Hard drives, SSDs from 2025: Last 5-15 years
- USB flash drives: 10-20 years (if not written frequently)
- SD cards: Similar to USB drives
- Optical discs (CD, DVD, Blu-ray): 10-50+ years if stored properly
- Store all in climate-controlled, low-humidity environment

### Build What You Can
- Magnetic tape: Achievable relatively early
- Floppy disks: Moderate difficulty
- Core memory: Labor-intensive but achievable
- SRAM: Once you have ICs
- DRAM: More advanced IC process
- Hard disks: Very difficult, late-stage technology

### Maintain Compatibility
- Use standard formats when possible (FAT file system, standard sector sizes)
- Document any custom formats thoroughly
- Ensure data can be migrated to newer storage as technology improves

### Redundancy
- Critical data: Multiple copies on different media types
- Periodic migration to newer media (before old media fails)
- Test backups regularly

## Next Steps

With storage capability:
- Build complete computer systems (Chapter 9)
- Store and distribute software (Chapter 13)
- Archive knowledge (this guide and other technical documentation)
- Enable databases and complex applications
- Foundation for networks (Chapter 12) and internet services

Memory and storage are the foundation of persistent computing. Temporary memory (RAM) allows complex calculations. Permanent storage (disk, tape) allows computers to remember and accumulate knowledge. Together, they transform computers from calculators into intelligent systems.

**Key Principle**: Storage is as important as processing. A computer that can't save its work is a very expensive calculator. Invest in storage technology early, and preserve data carefully. The knowledge stored now is the foundation for future rebuilding.
