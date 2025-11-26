# Chapter 15: Cellular and Wireless Communication Networks

## Why Cellular Networks Matter

Wired networks (Ethernet, telephone) require physical infrastructure—cables connecting every location. Wireless networks free users to move while staying connected:
- **Mobility**: Communicate while moving
- **Flexibility**: No need to run wires
- **Rapid deployment**: Set up network quickly
- **Coverage**: Reach remote areas

By 2025, cellular networks connected billions of devices worldwide. Post-collapse, rebuilding wireless networks can reconnect dispersed communities faster than laying cable.

## Cellular Network Fundamentals

### The Cellular Concept

**Problem**: Radio spectrum is limited. Using one frequency for entire region limits capacity.

**Solution**: Divide region into cells
- Each cell has base station (tower)
- Use same frequencies in non-adjacent cells (frequency reuse)
- Handoff: Transfer call as user moves between cells

**Cell Pattern** (Hexagonal ideal):
```
   ___     ___     ___
  / A \___/ B \___/ C \___
  \___/ A \___/ B \___/ A
  / B \___/ C \___/ A \___
  \___/ A \___/ B \___/
```
- Frequency set A, B, C
- Cluster size: 3 (or 4, 7, 12 depending on interference tolerance)
- Smaller cells = more capacity (more reuse) but more infrastructure

**Frequency Reuse Distance**: D = R × √(3N)
- R = cell radius
- N = cluster size
- Example: N=7, R=5 km → D=13 km minimum distance for same frequency

### Cellular Network Components

**Mobile Station (MS)**: User device (cell phone)
- Transmitter and receiver (transceiver)
- Antenna
- Battery
- Controller (microprocessor)
- User interface (display, keypad, speaker, microphone)

**Base Transceiver Station (BTS)**: Cell tower
- Transmitter and receiver (higher power than MS)
- Antenna (often directional for sector coverage)
- Connects to BSC

**Base Station Controller (BSC)**: Manages multiple BTSs
- Handoff decisions
- Power control
- Frequency assignment

**Mobile Switching Center (MSC)**: Core network switch
- Routes calls between BSCs
- Connects to PSTN (public switched telephone network)
- Manages mobility (location tracking, authentication)

**Home Location Register (HLR)**: Database
- Subscriber information
- Current location
- Services allowed

**Visitor Location Register (VLR)**: Temporary database
- Tracks users currently in this MSC's area
- Copy of HLR data for active users

**Authentication Center (AuC)**: Security
- Authenticates users
- Encryption keys

**Equipment Identity Register (EIR)**: Device database
- Valid device IDs
- Stolen phone blacklist

### Cellular Generations

**1G** (First Generation, 1980s):
- Analog voice (FM modulation)
- AMPS (US), NMT (Europe), TACS (UK)
- 800-900 MHz
- No encryption (easy to eavesdrop)
- Example: Motorola DynaTAC

**2G** (Second Generation, 1990s):
- Digital voice and SMS
- GSM (Global System for Mobile), CDMA (Code Division Multiple Access)
- 900/1800 MHz (GSM), 800/1900 MHz (CDMA)
- Encryption
- Data: GPRS (General Packet Radio Service), EDGE (Enhanced Data rates for GSM Evolution)
  - Up to 40-120 kbps

**2.5G / 3G** (2000s):
- Higher-speed data
- UMTS/HSPA (GSM evolution), CDMA2000 (CDMA evolution)
- 384 kbps to 42 Mbps
- Video calls, mobile internet

**4G / LTE** (Long-Term Evolution, 2010s):
- All-IP network (voice and data as IP packets)
- 100 Mbps to 1 Gbps
- OFDMA (Orthogonal Frequency Division Multiple Access)
- MIMO (Multiple Input Multiple Output)

**5G** (2020s):
- Even higher speed (multi-Gbps)
- Lower latency (<1 ms)
- Massive device density (IoT)
- mmWave frequencies (24-100 GHz) plus sub-6 GHz

**Post-Collapse Path**: Start with simple analog (1G-like), progress to digital (2G), eventually reach modern standards (decades out).

## Building a Cellular Network

### Stage 1: Simple Mobile Radio (Pre-Cellular)

**Simplest Mobile Communication**: Like Chapter 6 radio, but mobile

**Components**:
- **Mobile Unit**: VHF/UHF FM transceiver (walkie-talkie type)
  - 2-5W power
  - Battery-powered
- **Base Station**: Higher-power transceiver on hilltop or tower
  - 25-50W power
  - Good antenna (gain, height)
  - Power supply (AC or solar)
- **Repeater** (Optional): Receives on one frequency, retransmits on another
  - Extends range

**Operation**:
- Push-to-talk (PTT): Press button to transmit
- Simplex (one talks at a time) or duplex (simultaneous)
- Manual: User calls base station, operator connects call

**Coverage**: 10-50 km depending on terrain, power, antenna height

**Capacity**: Limited (one conversation per channel)

**Uses**: Taxi dispatch, police/fire, business communications

**Building**:
- Transceivers: Salvage walkie-talkies or build (see Chapter 6)
- Repeater: Two transceivers, back-to-back, with controller
- Effort: Moderate

### Stage 2: Trunked Radio (More Capacity)

**Problem**: Simple radio wastes spectrum (channels idle much of time)

**Solution**: Trunked system
- Pool of channels
- Controller assigns channel dynamically when user presses PTT
- Channels released after use
- More users than channels (statistical multiplexing)

**Components**:
- Multiple channel repeaters
- Controller (logic to assign channels)
- Mobile units with trunking capability

**Capacity**: 2-5× more users than channels (depending on usage)

**Example**: 10 channels, 30 users (not all talk simultaneously)

**Building**: Requires controller (microprocessor-based)

### Stage 3: Analog Cellular (1G)

**AMPS** (Advanced Mobile Phone System):
- Developed by Bell Labs (1970s), deployed 1980s
- Well-documented
- Good first cellular system to build

**Frequency**:
- 824-849 MHz: Mobile transmit, base receive
- 869-894 MHz: Base transmit, mobile receive
- 832 channels (30 kHz each)
- Paired channels (frequency division duplex)

**Modulation**: FM (frequency modulation)

**Control Channels**: Setup calls, paging
- Out-of-band signaling (separate channels)

**Voice Channels**: Carry calls
- FM voice

**Call Setup**:
1. Mobile scans control channels, selects strongest
2. Mobile registers with base (sends ID)
3. Network acknowledges
4. To make call: Mobile sends digits on control channel
5. Network assigns voice channel
6. Mobile and base switch to voice channel
7. Call proceeds

**Handoff**:
1. Network monitors signal strength
2. When weak, network commands mobile to switch to new cell's frequency
3. Mobile retunes, call continues

**Building AMPS System**:

**Mobile Unit**:
- RF transceiver (800-900 MHz)
  - Synthesizer (tune to any channel)
  - FM modulator/demodulator
  - Power amplifier (0.6-3W)
- Controller (microprocessor)
  - Protocol stack
  - UI (keypad, display)
- Audio (microphone, speaker, codec)

**Base Station**:
- RF transceiver (higher power, 10-100W)
- Duplexer (transmit and receive simultaneously)
- Controller
- Connection to MSC (telephone line or microwave link)

**MSC** (Mobile Switching Center):
- Call routing
- Database (HLR/VLR)
- Connection to PSTN

**Effort**: Large. Each component is complex.
- Mobile unit: 10,000-50,000 lines of code
- Base station: Similar
- MSC: 100,000+ lines

**Recommendation**:
- Salvage 1G phones and base stations if available (may still find in developing world or old equipment)
- Study AMPS specs (public domain)
- Build gradually: Start with single cell, expand

**Challenges**:
- RF design (800-900 MHz not trivial)
- Protocol complexity
- Need spectrum coordination (avoid interference)

### Stage 4: Digital Cellular (2G)

**GSM** (Global System for Mobile Communications):
- European standard, became worldwide
- Most deployed cellular system (by 2010s)
- Well-documented, open standard

**Frequency Bands**: 900 MHz, 1800 MHz, 1900 MHz (varies by region)

**Multiple Access**: TDMA (Time Division Multiple Access)
- 8 time slots per channel (200 kHz wide)
- Each user gets one slot
- Frame: 8 slots, 4.615 ms
- 13 kbps per slot (voice codec compresses to this rate)

**Modulation**: GMSK (Gaussian Minimum Shift Keying)
- Spectrum-efficient
- Constant envelope (power-efficient)

**Voice Codec**: GSM-FR (Full Rate)
- 13 kbps
- Reasonable quality (not toll-quality but acceptable)
- Later: EFR (Enhanced), AMR (Adaptive Multi-Rate)

**Encryption**: A5 algorithms
- Protect privacy
- Keys from SIM card

**SIM Card** (Subscriber Identity Module):
- Smart card with:
  - Subscriber ID (IMSI)
  - Authentication key
  - Phone book (optional)
- Removable (change phones easily)

**SMS** (Short Message Service):
- 160 characters
- Uses signaling channels
- Store-and-forward

**Call Setup**:
1. Phone sends access request on RACH (Random Access Channel)
2. Network assigns dedicated channel
3. Authentication (SIM card and network exchange keys)
4. Phone sends call request
5. Network routes call, rings destination
6. Call proceeds

**Handoff**: More complex than AMPS (need to synchronize time slots)

**Building GSM System**:

**Significantly More Complex Than AMPS**:
- TDMA synchronization
- Voice codec (DSP required)
- Encryption
- SIM card reader

**Advantage of GSM**:
- Higher capacity (TDMA)
- Better quality (digital)
- Data services (SMS, GPRS)

**Effort**: Very large
- Requires DSP (Digital Signal Processor)
- Complex protocol stack
- Expect 100,000+ lines of code per component

**Recommendation**:
- Salvage 2G equipment (abundant, many networks still operating in 2025)
- Study GSM specs (public, detailed)
- Build only if no salvage available and you have advanced electronics capability

### Stage 5: 3G and Beyond

**UMTS/HSPA** (3G):
- WCDMA (Wideband CDMA)
- 5 MHz channels
- Higher data rates (384 kbps to 42 Mbps)
- More complex modulation and coding

**LTE** (4G):
- All-IP (VoLTE - Voice over LTE)
- OFDMA (Orthogonal Frequency Division)
- MIMO (Multiple antennas)
- 20 MHz channels (up to 100 MHz aggregated)
- 100 Mbps to 1 Gbps

**5G**:
- Massive MIMO (100+ antennas)
- Beamforming (focus signal at user)
- mmWave (24-100 GHz for ultra-high speed)
- Network slicing (virtual networks on shared infrastructure)

**Post-Collapse Timeline**:
- 3G: 40-60 years (requires advanced DSP, software-defined radio)
- 4G: 60-80 years (requires high-performance DSPs, complex protocols)
- 5G: 80-100+ years (requires cutting-edge semiconductor and software capability)

**Recommendation**: Focus on 1G and 2G for first 30-50 years. Salvage 3G/4G/5G equipment and use as long as it functions.

## Wireless Data Networks (WiFi, etc.)

### WiFi (802.11)

**Purpose**: Wireless LAN (local area network)

**Frequencies**:
- 2.4 GHz: 802.11b/g/n (longer range, more interference)
- 5 GHz: 802.11a/n/ac/ax (shorter range, less interference, more bandwidth)
- 6 GHz: 802.11ax (WiFi 6E)

**Modulation**: OFDM (modern), DSSS/CCK (early)

**Data Rates**:
- 802.11b: 11 Mbps
- 802.11g: 54 Mbps
- 802.11n: 600 Mbps
- 802.11ac: 1-7 Gbps
- 802.11ax (WiFi 6): 10+ Gbps

**Security**:
- WEP: Broken (don't use)
- WPA2: Strong (AES encryption)
- WPA3: Stronger (modern)

**Components**:
- **Access Point (AP)**: Base station
  - Connect to wired network (Ethernet)
  - Bridge wireless and wired
- **Client**: WiFi adapter in device
  - Laptop, phone, tablet, IoT, etc.

**Building WiFi**:
- Extremely complex (OFDM, fast DSP, complex MAC layer)
- Recommendation: Salvage only
- WiFi chips and modules very common in 2025

### Bluetooth

**Purpose**: Short-range personal area network (PAN)

**Frequency**: 2.4 GHz (ISM band)

**Range**: 1-100 meters (depending on class)

**Data Rate**: 1-3 Mbps (classic), 1-2 Mbps (BLE)

**Uses**:
- Wireless peripherals (keyboard, mouse, headset)
- File transfer
- IoT sensors (BLE - Bluetooth Low Energy)

**Building**: Very complex. Salvage only.

### LoRa and LoRaWAN

**Purpose**: Long-range, low-power IoT

**Frequency**: ISM bands (433, 868, 915 MHz depending on region)

**Range**: 2-15 km (urban to rural)

**Data Rate**: 0.3-50 kbps (slow but long-range)

**Modulation**: LoRa (proprietary chirp spread spectrum)

**Uses**:
- Sensors (agriculture, environment, industrial)
- Smart meters
- Asset tracking

**Advantage**: Very low power (years on battery)

**Building**: LoRa chips salvageable. Protocol moderately complex but achievable.

**Post-Collapse Use**: Good for connecting remote sensors without running power or network cables.

## Satellite Communication

### Types of Satellites

**GEO** (Geostationary Earth Orbit):
- 35,786 km altitude
- Orbits at Earth's rotation rate (appears stationary)
- Covers 1/3 of Earth
- 3 satellites = global coverage (except poles)
- High latency (240-280 ms round-trip)
- Large antennas, high power required

**MEO** (Medium Earth Orbit):
- 2,000-35,786 km
- GPS satellites (~20,000 km)
- Multiple satellites needed for coverage
- Medium latency

**LEO** (Low Earth Orbit):
- 160-2,000 km
- Fast-moving (orbit in 90-120 minutes)
- Large constellations needed (Starlink: thousands)
- Low latency (20-40 ms)
- Smaller antennas, lower power

### Satellite Phone Systems

**Iridium**:
- LEO (780 km)
- 66 satellites
- Global coverage (including poles)
- Voice and low-speed data

**Globalstar**:
- LEO (1,400 km)
- 48 satellites
- Voice and data
- No coverage at poles

**Inmarsat**:
- GEO
- Maritime, aviation, government

**Post-Collapse Considerations**:
- Existing satellites will fail (10-15 years without maintenance/fuel)
- Launching new satellites: Requires rocket capability (50-100 years)
- Ground stations: Buildable with advanced electronics

**Recommendation**: Use salvaged satellite phones while satellites functional. Don't plan on satellite for long-term post-collapse.

## Spectrum Management

### Why Spectrum Management Matters

**Radio Spectrum Is Limited**:
- Usable frequencies: ~3 kHz to 300 GHz
- Different uses require different frequencies
- Interference if multiple users on same frequency

**Pre-Collapse**: Governments managed spectrum (FCC in US, ITU internationally)

**Post-Collapse**: Need coordination to avoid chaos

### Frequency Allocation

**Example Allocations** (Pre-Collapse, for reference):
- 535-1705 kHz: AM radio
- 88-108 MHz: FM radio
- 174-216 MHz: TV (old VHF channels)
- 470-806 MHz: TV (UHF channels, some reallocated to cellular)
- 824-894 MHz: Cellular (1G, 2G)
- 1850-1990 MHz: Cellular (PCS)
- 2.4 GHz: ISM (WiFi, Bluetooth, microwave ovens)
- 5 GHz: WiFi, radar

**ISM Bands** (Industrial, Scientific, Medical):
- Unlicensed
- 2.4 GHz most common
- Also: 433 MHz, 868 MHz, 915 MHz, 5.8 GHz

**Post-Collapse Allocation**:
- No global authority initially
- Coordinate locally/regionally
- Document allocations
- Establish governance as networks grow

**Principles**:
- Avoid interference (separate uses geographically or by frequency)
- Prioritize critical services (emergency, medical, infrastructure)
- Allow experimentation (reserved bands for development)

## Building a Practical Wireless Network

### Small Community (100-1,000 people)

**Technology**: VHF/UHF FM radio with repeaters

**Coverage**: 10-30 km radius

**Components**:
- Handheld transceivers (salvaged or built)
- Repeaters on high points
- Base stations at key locations (hospital, fire, police, public works)

**Services**:
- Voice communication
- Emergency alerts
- Coordination

**Capacity**: 10-50 users per channel (with trunking)

### Regional Network (10,000-100,000 people, 100-1000 km²)

**Technology**: Simple cellular (1G-like)

**Coverage**: Multiple cells

**Components**:
- 5-20 cell towers
- MSC (central switch)
- Connection to PSTN (if exists) or other networks

**Services**:
- Mobile phones
- Voice calls
- Basic data (if 2G capability)

**Capacity**: 1,000-10,000 concurrent calls

### Wide-Area Network (Millions of people, continent-scale)

**Technology**: 2G or 3G cellular

**Coverage**: Thousands of cells

**Components**:
- Extensive tower infrastructure
- Multiple MSCs
- Interconnection (fiber, microwave)
- Roaming agreements between regions

**Services**:
- Mobile phones
- Internet (data)
- SMS
- Eventually multimedia (3G+)

**Capacity**: Millions of users

**Timeline**: 40-60+ years to achieve

## Practical Steps

### Phase 1: Salvage and Deploy (Years 0-10)

1. Salvage mobile phones, base stations, repeaters
2. Restore power to existing towers
3. Reactivate networks where possible
4. Or deploy simple VHF/UHF radio systems

### Phase 2: Build Simple Wireless (Years 10-25)

1. Build FM transceivers and repeaters
2. Establish trunked radio systems
3. Begin 1G-style cellular (if capability allows)
4. Coordinate spectrum use

### Phase 3: Digital Wireless (Years 25-50)

1. Deploy 2G cellular (GSM-like)
2. Expand coverage
3. Introduce data services
4. Interconnect regional networks

### Phase 4: Modern Wireless (Years 50+)

1. 3G and beyond
2. High-speed mobile data
3. Ubiquitous coverage
4. Advanced services

## Safety and Regulation

### RF Safety

**Non-Ionizing Radiation**: Radio waves don't directly damage DNA (unlike X-rays, gamma rays)

**But**: Heating effect at high power
- Absorption creates heat
- Specific Absorption Rate (SAR): Watts per kilogram
- Limits: 1.6 W/kg (US), 2.0 W/kg (Europe) for mobile phones

**Safe Practices**:
- Limit exposure time near high-power transmitters
- Distance: Power decreases with square of distance
- Don't stand in front of high-gain antennas while transmitting

### Interference Prevention

**Harmonics**: Transmitter emits at multiples of fundamental frequency
- Filter transmitter output
- Shielded enclosures

**Intermodulation**: Two strong signals create spurious signals
- Good receiver design (filtering, shielding)

**Adjacent Channel**: Transmit bandwidth bleeds into next channel
- Sharp filters
- Respect channel spacing

**Coordination**:
- Frequency plans
- Power limits
- Geographic separation

## Summary: Wireless Network Development Stages

**Stage 1 (Year 0-10): Basic Radio**
- Walkie-talkies
- Repeaters
- Push-to-talk systems

**Stage 2 (Year 10-25): Trunked Radio and Early Cellular**
- Trunked systems (more capacity)
- Simple analog cellular (1G-like)
- Limited coverage

**Stage 3 (Year 25-40): Digital Cellular**
- 2G (GSM-like)
- SMS, basic data
- Expanding coverage
- Regional networks

**Stage 4 (Year 40-60): 3G and Data Networks**
- 3G cellular
- Mobile internet
- WiFi (salvaged)
- Continent-scale networks

**Stage 5 (Year 60-100+): Modern Wireless**
- 4G/5G
- High-speed data everywhere
- IoT
- Global connectivity

## Conclusion

Wireless communication is freedom. It connects people without the constraint of cables. It enables mobility. It can be deployed faster than wired infrastructure.

**Priorities**:
1. Salvage existing equipment (use while it lasts)
2. Build simple systems (VHF/UHF radio, repeaters)
3. Progress to cellular gradually (1G → 2G → 3G+)
4. Coordinate spectrum (avoid chaos)
5. Document everything (protocols, frequencies, designs)

Wireless networks are complex, but achievable in stages. Start simple, expand capability over decades, and eventually rebuild the interconnected wireless world that existed before the collapse.

**Key Principle**: Wireless technology requires the integration of many disciplines: RF engineering, DSP, protocols, software, infrastructure. Don't rush. Build the foundation (simpler radio systems) before attempting advanced cellular. Each generation teaches lessons needed for the next.

Wireless networks will reconnect your rebuilding civilization. Invest in them, and watch communities that were isolated become part of a larger, coordinated whole.
