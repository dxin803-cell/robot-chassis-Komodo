# Getting Started with Komodo Series Chassis

This guide will help you get started with your JCROBOT Komodo chassis. Follow these steps to prepare, assemble, and configure your robot.

## 📦 Before You Begin

### What You'll Need
- Your Komodo chassis kit
- Power adapter (24V DC, appropriate amperage for your model)
- USB cable for configuration
- Computer with USB port
- Basic tools (screwdriver, hex wrench set)
- About 1-2 hours for initial setup

### Safety Precautions
⚠️ **Important**: 
- Disconnect power before assembling or modifying hardware
- Keep hands and loose items away from rotating wheels
- Work on a flat, stable surface
- Use ESD protection when handling electronics
- Never exceed rated voltage or current

## 🔧 Step 1: Unpack & Inspect

1. **Remove all components** from packaging carefully
2. **Check for damage** - inspect chassis frame, wheels, motors, and electronics
3. **Verify all parts** against the Bill of Materials (BOM)
4. **Document any issues** - contact support if parts are missing or damaged

## 🔨 Step 2: Assembly

### Quick Assembly Overview

1. **Mount Motors** (if not pre-installed)
   - Follow the [Assembly Guide](./assembly-guide.md)
   - Ensure proper alignment and secure fastening

2. **Attach Wheels**
   - Align wheel hubs with motor shafts
   - Secure with appropriate fasteners
   - Check for smooth rotation

3. **Install Control Electronics**
   - Mount motor controller to designated bracket
   - Connect motor power cables
   - Secure all connections

4. **Connect Power**
   - Connect battery or power supply
   - Verify voltage readings (should show 24V DC)
   - Do NOT power on yet

*For detailed step-by-step instructions with diagrams, see the [Assembly Guide](./assembly-guide.md)*

## 🔌 Step 3: Electrical Connections

### Power Connections

```
Power Supply (24V DC)
    ↓
    ├─→ Motor Controller
    ├─→ Sensor Hub
    └─→ Onboard Computer (if applicable)
```

### Motor Connections

Each motor should have:
- **Power cables**: Red (positive), Black (negative)
- **Feedback cables**: For encoder feedback
- **Control signals**: PWM or serial communication

**Color Code Reference**:
- Red = +24V
- Black = Ground (GND)
- Yellow = Signal/Feedback
- Green = Signal/Feedback

### Verification Checklist
- [ ] All connectors seated firmly
- [ ] No exposed wires
- [ ] Cables routed safely away from moving parts
- [ ] Power readings correct
- [ ] No loose fasteners

## ⚙️ Step 4: Firmware Installation

### For Komodo Models with Microcontroller

1. **Connect to Computer**
   - Use USB cable to connect motor controller
   - Computer should recognize the device

2. **Download Firmware**
   - Visit `/software/firmware/` in this repository
   - Download the firmware for your Komodo model
   - Example: `Komodo-01_firmware_v1.2.3.hex`

3. **Flash Firmware**
   - Use appropriate programmer (e.g., Arduino IDE, PlatformIO)
   - Select your board type
   - Select correct COM port
   - Click "Upload"

4. **Verify Installation**
   - LED indicators should flash
   - No error messages in serial monitor
   - See [Troubleshooting](./troubleshooting.md) if issues occur

## 🚀 Step 5: Initial Power-On

1. **Pre-Power Checklist**
   - [ ] Wheels can rotate freely
   - [ ] All cables connected
   - [ ] Power supply switched OFF
   - [ ] Robot on flat surface away from people

2. **Power On**
   - Turn on power supply slowly
   - Watch for LED status indicators
   - First boot takes 10-30 seconds

3. **Initial Calibration** (Automatic)
   - Wheels may move during calibration
   - Motor controller learns speed characteristics
   - This is normal - do not interrupt

4. **Verify Operation**
   - All LEDs should show green/normal status
   - Check serial console for "Initialization Complete"
   - No error messages

## 🎮 Step 6: Test Movement (Optional)

### Basic Motor Test (if using provided test code)

```python
from komodo import Chassis

# Initialize
robot = Chassis(model="Komodo-01")

# Test forward movement
robot.move_forward(speed=0.5)  # 50% speed
time.sleep(2)

# Test rotation
robot.rotate(angle=90)  # 90 degrees clockwise
time.sleep(2)

# Stop
robot.stop()
```

**Manual Test** (without code):
1. Connect to motor controller via serial/USB
2. Send command: `M 100 100` (both motors 100% forward)
3. Watch wheels - they should rotate steadily
4. Send: `M 0 0` (stop)

## 📝 Step 7: Configuration

### Setup Configuration File

1. **Locate config file**: `/software/config/chassis_config.json`
2. **Edit for your model**:

```json
{
  "model": "Komodo-01",
  "wheel_diameter_mm": 150,
  "wheel_base_mm": 300,
  "max_speed_mps": 1.2,
  "encoder_counts_per_rev": 1024,
  "controller_port": "/dev/ttyUSB0"
}
```

3. **Save and restart** controller

## ✅ Post-Setup Checklist

- [ ] All power connections verified
- [ ] Firmware installed and running
- [ ] Initial calibration completed
- [ ] Motors respond to commands
- [ ] Configuration saved
- [ ] Documentation reviewed
- [ ] Safety manual read

## 📚 Next Steps

1. **Read Full Documentation**
   - [Technical Specifications](./specifications.md)
   - [Advanced Configuration Guide](./advanced-config.md)

2. **Explore Software**
   - Review code examples in `/software/examples/`
   - Check driver libraries in `/software/drivers/`

3. **Join Community**
   - Participate in [GitHub Discussions](../../discussions)
   - Share your projects
   - Report issues or improvements

4. **Advanced Topics**
   - ROS integration
   - Custom sensor additions
   - Network configuration

## 🆘 Troubleshooting

### Common Issues

**Motors not turning**
- Check power connections
- Verify firmware is uploaded correctly
- See [Troubleshooting Guide](./troubleshooting.md)

**Wheels moving unevenly**
- Perform wheel calibration
- Check wheel alignment
- Verify motor power distribution

**Communication issues**
- Check USB cable and port
- Verify correct COM port selected
- Review serial communication settings

For more help, see [Troubleshooting](./troubleshooting.md) or open an [Issue](../../issues).

## 📞 Support

- **Documentation**: Browse [docs folder](../)
- **Issues**: Report at [GitHub Issues](../../issues)
- **Discussions**: Join at [GitHub Discussions](../../discussions)
- **Email**: support@jcrobot.com
- **FAQ**: See [Troubleshooting](./troubleshooting.md)

## 🎉 Congratulations!

You've successfully set up your Komodo chassis! You're now ready to:
- Develop custom software
- Add sensors
- Deploy in your application
- Contribute improvements back to the community

Happy coding! 🚀

---

**Next Section**: [Technical Specifications](./specifications.md)
