# Komodo Series - Technical Specifications

Complete technical specifications for all Komodo chassis variants.

## 📊 Model Comparison Chart

| Specification | Komodo-ZERO | Komodo-01 | Komodo-02 |
|---------------|------------|-----------|-----------|
| **Payload Capacity** | 5 kg | 15 kg | 25 kg |
| **Dimensions (L×W×H)** | 250×200×120 mm | 350×280×150 mm | 450×350×180 mm |
| **Weight (Base)** | 2.5 kg | 5.0 kg | 8.5 kg |
| **Max Speed** | 1.5 m/s | 1.2 m/s | 1.0 m/s |
| **Max Torque** | 2.5 N⋅m | 4.0 N⋅m | 6.5 N⋅m |
| **Battery Capacity** | 24V 5Ah | 24V 10Ah | 24V 15Ah |
| **Runtime** | 2-3 hours | 3-4 hours | 3-4 hours |
| **Wheel Diameter** | 120 mm | 150 mm | 180 mm |
| **Track Width** | 180 mm | 250 mm | 320 mm |
| **Ground Clearance** | 40 mm | 50 mm | 60 mm |
| **Motor Type** | 24V DC Brushed | 24V DC Brushed | 24V DC Brushed |
| **Encoder Resolution** | 1024 CPR | 1024 CPR | 1024 CPR |
| **Terrain Type** | Indoor | Indoor/Outdoor | Outdoor/Rugged |
| **Weatherproofing** | IP54 | IP67 | IP67 |
| **Communication** | USB/Serial | USB/Serial/CAN | USB/Serial/CAN/Ethernet |
| **Price Range** | $299-$349 | $499-$599 | $799-$999 |

---

## 🤖 Komodo-ZERO Specifications

### Overview
Compact, lightweight chassis ideal for education, prototyping, and indoor navigation applications.

### Physical Dimensions
- **Length**: 250 mm
- **Width**: 200 mm
- **Height**: 120 mm
- **Weight (chassis only)**: 2.5 kg
- **Max Payload**: 5 kg (Total system weight: 7.5 kg)
- **Wheel Diameter**: 120 mm
- **Track Width**: 180 mm
- **Ground Clearance**: 40 mm
- **Turning Radius**: 150 mm

### Power System
- **Voltage**: 24V DC nominal
- **Battery Capacity**: 5Ah Lithium
- **Runtime**: 2-3 hours (continuous operation)
- **Charging Time**: 2-3 hours (standard charger)
- **Motor Count**: 2 × 24V DC brushed motors
- **Max Current**: 5A per motor

### Performance
- **Max Speed**: 1.5 m/s (5.4 km/h)
- **Acceleration**: 0-1.5 m/s in 2 seconds
- **Max Torque**: 2.5 N⋅m per wheel
- **Wheel Slip**: <5% on level ground
- **Slope Capability**: Up to 15° grade
- **Obstacle Crossing**: Up to 50 mm height

### Control & Communication
- **Motor Controller**: Onboard 24V dual-channel H-bridge
- **Communication Interface**: USB Serial
- **Baud Rate**: 115200 bps
- **Control Protocol**: Serial ASCII commands
- **Feedback**: Encoder feedback via motor controller
- **Response Time**: <50 ms

### Sensors (Base System)
- **Wheel Encoders**: 1024 CPR (Counts Per Revolution)
- **IMU**: Optional (via sensor hub)
- **IR Cliff Sensors**: 4 × optional
- **Bumper Sensors**: Optional 2 × bumpers

### Environmental
- **Operating Temperature**: 0°C to 40°C
- **Storage Temperature**: -10°C to 50°C
- **Humidity**: 10% to 90% non-condensing
- **Weatherproofing**: IP54 (splash-resistant)
- **Terrain**: Smooth indoor surfaces, light carpet

### Electrical Connectors
- **Power Input**: XT60 connector (24V)
- **Motor Output**: XT30 connectors
- **Sensor I/O**: JST-XH 2.54mm pitch
- **Communication**: USB Mini-B

---

## 🤖 Komodo-01 Specifications

### Overview
Mid-range platform for research, industry applications, and field robotics with improved payload and weatherproofing.

### Physical Dimensions
- **Length**: 350 mm
- **Width**: 280 mm
- **Height**: 150 mm
- **Weight (chassis only)**: 5.0 kg
- **Max Payload**: 15 kg (Total system weight: 20 kg)
- **Wheel Diameter**: 150 mm
- **Track Width**: 250 mm
- **Ground Clearance**: 50 mm
- **Turning Radius**: 200 mm

### Power System
- **Voltage**: 24V DC nominal
- **Battery Capacity**: 10Ah Lithium
- **Runtime**: 3-4 hours (continuous operation)
- **Charging Time**: 3-4 hours (standard charger)
- **Motor Count**: 2 × 24V DC brushed motors
- **Max Current**: 8A per motor

### Performance
- **Max Speed**: 1.2 m/s (4.3 km/h)
- **Acceleration**: 0-1.2 m/s in 1.8 seconds
- **Max Torque**: 4.0 N⋅m per wheel
- **Wheel Slip**: <3% on level ground
- **Slope Capability**: Up to 20° grade
- **Obstacle Crossing**: Up to 80 mm height
- **Water Fording**: Up to 100 mm depth

### Control & Communication
- **Motor Controller**: Onboard 24V dual-channel H-bridge with current sensing
- **Communication Interface**: USB Serial / CAN bus / RS485
- **Baud Rate**: 115200 bps (Serial)
- **CAN Bitrate**: 500 kbps
- **Control Protocol**: Serial ASCII + CAN extended protocol
- **Feedback**: Dual encoder feedback per motor
- **Response Time**: <30 ms

### Sensors (Base System)
- **Wheel Encoders**: 1024 CPR per motor
- **IMU**: 6-axis (3-axis accelerometer + 3-axis gyro)
- **Compass**: Digital compass (heading)
- **Bumper Sensors**: 4 × omnidirectional bumpers
- **IR Cliff Sensors**: 4 × obstacle avoidance

### Sensor Expansion
- **I2C Bus**: Up to 8 additional sensors
- **SPI Bus**: For advanced sensors
- **GPIO**: 8 × digital I/O pins
- **ADC**: 4 × 12-bit analog inputs

### Environmental
- **Operating Temperature**: -10°C to 50°C
- **Storage Temperature**: -20°C to 60°C
- **Humidity**: 5% to 95% non-condensing
- **Weatherproofing**: IP67 (fully waterproof)
- **Terrain**: Grass, gravel, light mud, indoor/outdoor

### Electrical Connectors
- **Power Input**: XT90-S connector (24V, 60A capable)
- **Motor Output**: XT60 connectors
- **Sensor I/O**: Circular M12 connectors (IP67 rated)
- **Communication**: USB Type-A / CAN-bus / RS485 terminal blocks

---

## 🤖 Komodo-02 Specifications

### Overview
Heavy-duty platform for industrial automation, construction, and demanding terrain applications.

### Physical Dimensions
- **Length**: 450 mm
- **Width**: 350 mm
- **Height**: 180 mm
- **Weight (chassis only)**: 8.5 kg
- **Max Payload**: 25 kg (Total system weight: 33.5 kg)
- **Wheel Diameter**: 180 mm
- **Track Width**: 320 mm
- **Ground Clearance**: 60 mm
- **Turning Radius**: 280 mm

### Power System
- **Voltage**: 24V DC nominal
- **Battery Capacity**: 15Ah Lithium (dual battery support)
- **Runtime**: 3-4 hours (continuous operation)
- **Charging Time**: 4-5 hours (standard charger)
- **Motor Count**: 2 × 24V DC brushed motors (high-torque)
- **Max Current**: 12A per motor

### Performance
- **Max Speed**: 1.0 m/s (3.6 km/h)
- **Acceleration**: 0-1.0 m/s in 2 seconds
- **Max Torque**: 6.5 N⋅m per wheel
- **Wheel Slip**: <2% on level ground
- **Slope Capability**: Up to 25° grade
- **Obstacle Crossing**: Up to 150 mm height
- **Water Fording**: Up to 200 mm depth
- **Mud/Soft Terrain**: Capable

### Control & Communication
- **Motor Controller**: Redundant dual-channel controllers with current sensing
- **Communication Interface**: USB / CAN bus / RS485 / Ethernet (optional)
- **Baud Rate**: 115200 bps (Serial) / 1000 Mbps (Ethernet)
- **CAN Bitrate**: 500 kbps (1 Mbps capable)
- **Control Protocol**: Extended CAN protocol with safety features
- **Feedback**: Triple-redundant encoder feedback
- **Response Time**: <20 ms

### Sensors (Base System)
- **Wheel Encoders**: 1024 CPR per motor
- **IMU**: 9-axis (3-axis accelerometer + 3-axis gyro + 3-axis magnetometer)
- **LIDAR**: Optional 2D LIDAR mounting point
- **Camera Mount**: Standardized payload mounting
- **Bumper Sensors**: 8 × redundant bumpers (full coverage)
- **IR Sensors**: 6 × cliff detection + 4 × proximity

### Sensor Expansion
- **I2C/SPI Buses**: Full expansion capability
- **GPIO**: 16 × digital I/O pins
- **ADC**: 8 × 12-bit analog inputs
- **PWM**: 4 × high-power PWM outputs (servo capable)

### Environmental
- **Operating Temperature**: -20°C to 60°C
- **Storage Temperature**: -30°C to 70°C
- **Humidity**: 1% to 99% non-condensing
- **Weatherproofing**: IP67 (full submersion rated)
- **Terrain**: Rocky, muddy, steep slopes, snow, sand

### Electrical Connectors
- **Power Input**: Anderson SB50 (600A capable, future-proof)
- **Motor Output**: Circular M16 connectors (IP67 rated, weatherproof)
- **Sensor I/O**: Circular M12 connectors with quick-disconnect
- **Communication**: USB Type-C / M12 circular CAN connector / Terminal blocks

---

## 🔄 Komodo-03 through Komodo-15

**Status**: Coming Soon

These variants will offer:
- Specialized terrain variants (snow, desert, aquatic)
- Extended payload options (up to 50 kg)
- Specialized motor configurations (high-speed, low-speed/high-torque)
- Custom sensor packages
- Multi-motor configurations

---

## 📐 Common Specifications All Models

### Motor Specifications
- **Type**: DC Brushed, 24V nominal
- **Efficiency**: 85-90%
- **Insulation Class**: F
- **Thermal Protection**: Optional thermal cutoff
- **Service Life**: 1000+ hours typical operation

### Encoder Specifications
- **Type**: Incremental rotary encoder
- **Resolution**: 1024 CPR
- **Maximum Speed**: 300 RPM (base models)
- **Accuracy**: ±0.5% over temperature range

### Battery (Standard)
- **Chemistry**: LiFePO4 (Lithium Iron Phosphate)
- **Safety**: Built-in BMS (Battery Management System)
- **Cycle Life**: 2000+ cycles
- **Warranty**: 2 years
- **Charging Standard**: CC-CV (Constant Current - Constant Voltage)

### Software Support
- **Firmware Updates**: Via USB/Serial
- **Operating System Compatibility**: Linux, Windows, macOS
- **Programming Languages**: Python, C/C++, ROS
- **Example Code**: Included for all major platforms

### Mechanical
- **Frame Material**: Aluminum alloy 6061 (weight optimization)
- **Fasteners**: Stainless steel (corrosion resistant)
- **Wheel Material**: High-grip rubber compound
- **Bearing Type**: Ball bearings (sealed, low-friction)

### Quality Assurance
- **Pre-delivery Testing**: 100% tested before shipment
- **Warranty Period**: 1 year (2 years for battery)
- **RoHS Compliance**: Yes
- **CE Certified**: Yes (EU markets)

---

## 📏 Dimensional Drawings

See [3D Models](../3d-models/) for detailed CAD drawings in STEP, STL, and OBJ formats.

---

## ⚡ Power Consumption

### Typical Operating Current Draw

| Model | Idle | Cruising | Max Speed | Peak Acceleration |
|-------|------|----------|-----------|------------------|
| Komodo-ZERO | 0.5A | 2-3A | 4-5A | 8-10A |
| Komodo-01 | 1.0A | 4-6A | 8-10A | 14-16A |
| Komodo-02 | 1.5A | 6-8A | 12-14A | 20-24A |

---

## 🌡️ Thermal Management

- **Operating Range**: See environmental specs for each model
- **Thermal Protection**: Auto shutdown if temp exceeds 70°C
- **Cooling**: Passive airflow (no active cooling required)
- **Thermal Sensors**: Integrated in motor controller (Komodo-01, 02)

---

## 📞 Technical Support

For detailed questions about specifications or comparisons:
- Email: technical@jcrobot.com
- Create an [Issue](../../issues)
- Join [Discussions](../../discussions)

---

**Last Updated**: 2026-07-09
