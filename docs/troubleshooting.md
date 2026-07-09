# Troubleshooting Guide - Komodo Series Chassis

This guide helps you diagnose and resolve common issues with your Komodo chassis.

## 🔍 General Troubleshooting Steps

Before diving into specific issues, try these basic steps:

1. **Power Cycle**
   - Power off completely (wait 30 seconds)
   - Power on and wait for initialization
   - Check LED indicators

2. **Visual Inspection**
   - Check all cable connections
   - Look for loose fasteners
   - Inspect wheels for debris or damage
   - Verify no components are damaged

3. **Review Documentation**
   - Check [Getting Started Guide](./getting-started.md)
   - Review [Assembly Guide](./assembly-guide.md)
   - Consult [Technical Specifications](./specifications.md)

4. **Check Serial Output**
   - Connect to motor controller via USB
   - Open serial monitor (115200 baud)
   - Look for error messages or status codes

---

## ⚡ Power & Battery Issues

### Issue: Robot Won't Power On

**Symptoms**: No LED indicators, no response

**Solutions**:
1. Check battery connection
   - Verify battery is charged (use multimeter)
   - Ensure connector is fully seated
   - Check for corrosion on connector pins

2. Test power supply
   ```
   Multimeter should read 24V across battery terminals
   ```

3. Verify main power switch is ON

4. Check for blown fuse
   - Locate fuse holder on controller
   - Replace fuse if blackened inside

5. Inspect power cables for damage
   - Look for cuts or exposed wire
   - Check solder joints at connectors

**Still not working?**
- Contact support@jcrobot.com with photos of connections

---

### Issue: Battery Dies Quickly

**Symptoms**: Robot stops after 30 minutes (should be 2-4 hours)

**Causes & Solutions**:

1. **Motors running continuously**
   - Check if wheels are stuck or dragging
   - Verify no software bug keeping motors active
   - Test with `M 0 0` command to stop all motors

2. **Battery needs conditioning**
   - New lithium batteries need 3-5 charge/discharge cycles
   - Fully charge and fully discharge each time
   - Runtime will improve

3. **Cold temperature**
   - Lithium batteries perform poorly below 5°C
   - Move to warmer location
   - Warm battery (don't overheat) before use

4. **Battery degradation**
   - Lithium batteries degrade over time
   - After 500+ cycles, capacity reduces
   - Consider battery replacement

5. **Parasitic drain**
   - Ensure main switch powers everything off
   - Check for stuck relays or switches
   - Verify charging circuit is off when not charging

---

### Issue: Voltage Fluctuations

**Symptoms**: Motors inconsistent, commands fail, LEDs flicker

**Diagnosis**:
```
Use multimeter to check voltage under load:
- Idle: Should be 24V stable
- Light load: 23.5-24V
- Full load: Should not drop below 22V
```

**Solutions**:
1. Check battery connections are tight
2. Inspect power cables for resistance/damage
3. Clean connector contacts (mild corrosion?)
4. Test with known-good battery
5. Replace battery if voltage drops excessively under load

---

## 🚗 Motor & Movement Issues

### Issue: One Wheel Won't Move

**Symptoms**: Robot pulls to one side, one motor silent

**Diagnosis Checklist**:
- [ ] Is motor getting power? (test with multimeter)
- [ ] Is wheel physically stuck?
- [ ] Is encoder feedback present?
- [ ] Is motor controller outputting signal?

**Solutions**:

1. **Check Motor Power Connection**
   ```
   1. Power OFF
   2. Disconnect motor cable
   3. Use multimeter on controller output
   4. Power ON
   5. Send command: M 100 0
   6. Should read ~24V on Motor A output
   ```

2. **Free Stuck Wheel**
   - Manually rotate wheel - should spin freely
   - If stuck, remove wheel and inspect bearing
   - Clean any debris from bearing

3. **Swap Motor Connections**
   - Disconnect both motors
   - Swap motor A and B connections
   - Send test command
   - If other motor now fails, motor is bad
   - If same motor fails, controller issue

4. **Check Encoder Cable**
   - Disconnect encoder cable
   - Inspect for cuts or corrosion
   - Reconnect firmly
   - Test again

5. **Update Firmware**
   - Sometimes firmware bug causes single motor failure
   - Flash latest firmware from `/software/firmware/`
   - Test after update

**Motor Still Won't Move?**
- Replace motor (see hardware specs for model)
- Contact support

---

### Issue: Both Motors Spin Backwards

**Symptoms**: Wheels rotate opposite expected direction

**Solution**: Simple fix!

**Option 1**: Reverse motor polarity
```
Power OFF
Disconnect both motor cables
Swap red and black wire on ONE motor
Power ON
Test - should now go forward
```

**Option 2**: Flip motor mounts
- Rotate motor 180° in bracket
- Reconnect power (polarity unchanged)
- Motors now face opposite direction

**Option 3**: Reverse in software
- Modify firmware to invert motor direction
- See `/software/firmware/config.h`
- Rebuild and flash firmware

---

### Issue: Wheels Spin at Different Speeds

**Symptoms**: Robot drifts left or right, can't go straight

**Causes**:
- Wheel misalignment
- Encoder feedback error
- Motor speed mismatch
- Software calibration issue

**Solutions**:

1. **Manual Wheel Test**
   ```
   Power OFF
   Manually spin each wheel
   Both should have same resistance/friction
   ```

2. **Check Wheel Alignment**
   - Measure motor-to-ground height on both sides
   - Should be identical
   - Adjust motor bracket if needed
   - Tighten all fasteners

3. **Verify Encoder Feedback**
   ```
   Connect serial monitor
   Send: E (read encoder values)
   Both motors should report similar counts
   ```

4. **Run Calibration**
   ```
   Send: CAL (start calibration)
   Let robot sit still while calibrating
   Wait for "Calibration Complete" message
   ```

5. **Check for Wheel Slip**
   - Place robot on smooth surface
   - Command forward movement
   - Measure actual distance traveled
   - If less than expected, wheel slipping

**If still uneven after these steps**:
- Run dual-motor calibration procedure
- See [Advanced Configuration](./advanced-config.md)
- Consider motor replacement if one is significantly weaker

---

## 🔌 Connectivity Issues

### Issue: No Serial Communication

**Symptoms**: USB connected but no response, can't upload firmware

**Diagnosis Checklist**:
- [ ] USB cable is powered (check LED on controller)
- [ ] USB cable is data cable (not charge-only)
- [ ] Correct COM port selected
- [ ] Device shows in Device Manager (Windows) or `lsusb` (Linux)
- [ ] Correct baud rate (115200)

**Solutions**:

1. **Verify USB Connection**
   ```
   Windows: Device Manager → Ports (COM & LPT)
   Look for "USB Serial Device (COM X)"
   
   Linux: ls /dev/ttyUSB*
   Should show /dev/ttyUSB0 or similar
   
   macOS: ls /dev/tty.usbserial*
   Should show a ttyusbserial device
   ```

2. **Test with Different Cable**
   - USB cable may be damaged
   - Try a known-good USB cable
   - Verify it's a data cable, not charge-only

3. **Reinstall USB Drivers**
   - Windows: Download CH340 driver (or FT232 depending on board)
   - Linux: Usually works out of box
   - macOS: May need CH340 driver installation

4. **Try Different USB Port**
   - Try different USB port on computer
   - Try different computer if available
   - Helps isolate port vs. device issue

5. **Check Baud Rate**
   - Default is 115200
   - Verify in your terminal settings
   - Try 9600 if 115200 doesn't work

---

### Issue: Frequent Communication Timeouts

**Symptoms**: Commands work sometimes, then time out

**Solutions**:
1. Check USB cable connection (loose connector?)
2. Move away from sources of electrical noise
3. Shorten USB cable length (use active hub if needed)
4. Update firmware to latest version
5. Check PC USB hub power supply

---

## 🌡️ Environmental & Thermal Issues

### Issue: Robot Shuts Down in Cold

**Symptoms**: Works indoors, stops working when outside in winter

**Explanation**: Lithium batteries have limited cold-weather performance

**Solutions**:
1. Keep robot at 5°C or warmer
2. Insulate battery (neoprene wrap)
3. Pre-warm battery before use
4. Use battery heater module (optional, see hardware/)
5. Operate in warmer location

---

### Issue: Robot Slows Down Over Time

**Symptoms**: Starts fast, gradually slows down during operation

**Causes**:
- Motor controller overheating (thermal throttling)
- Battery voltage dropping under load
- Motor temperature rising

**Solutions**:
1. **Reduce continuous operation**
   - Add rest periods
   - Reduce speed setting
   - Let motors cool

2. **Improve cooling**
   - Ensure ventilation around controller
   - Remove any debris blocking airflow
   - Check thermal pads are installed

3. **Check battery**
   - Voltage dropping = battery exhausted
   - Replace battery
   - Use higher capacity battery (if available)

4. **Reduce load**
   - Remove unnecessary payload
   - Reduce motor duty cycle
   - Use slower speed setting

---

## 🛠️ Hardware Assembly Issues

### Issue: Loose Fasteners/Rattling Noise

**Symptoms**: Creaking, rattling sounds during movement

**Solution**:
1. Locate source of noise by visual inspection
2. Identify loose fastener (try to wiggle each bolt)
3. Tighten with appropriate wrench
4. Verify no wires caught under fastener
5. Test movement again

*See [Assembly Guide](./assembly-guide.md) for torque specifications*

---

### Issue: Wheel Won't Stay on Shaft

**Symptoms**: Wheel slides off or wobbles

**Solution**:
1. Power OFF
2. Remove wheel completely
3. Inspect hub and shaft for damage
4. Check set screw is tight (hex wrench)
5. Verify hub collar is flush with motor shaft
6. Reinstall with firm push
7. Tighten set screw(s) firmly

---

## 📊 LED Status Indicators

### LED Color Meanings

| Color | Meaning | Action |
|-------|---------|--------|
| 🟢 Green | Normal operation | No action needed |
| 🟡 Yellow | Warning (overtemp/low battery) | Check diagnostics |
| 🔴 Red | Error (motor fault/power loss) | Power off, diagnose |
| ⚫ Off | No power or controller offline | Check power connections |
| 🟢 Blinking | Initializing/calibrating | Wait for completion |

---

## 📞 Getting Help

### Before Contacting Support

1. Gather information:
   - Model number (Komodo-ZERO, 01, or 02)
   - Firmware version (send `V` command)
   - Describe symptoms clearly
   - Take photos of connections

2. Try all troubleshooting steps in this guide

3. Check [GitHub Issues](../../issues) for similar problems

4. Search [GitHub Discussions](../../discussions)

### How to Report an Issue

1. Create a [GitHub Issue](../../issues) with:
   - Clear title
   - Detailed description
   - Steps to reproduce
   - What you've already tried
   - Photos/videos if helpful

2. Email: support@jcrobot.com with:
   - Subject: "[Komodo-XX] Issue description"
   - Detailed explanation
   - Serial output/logs
   - Photos of hardware

3. Join [GitHub Discussions](../../discussions) to chat with community

---

## 🔧 Advanced Diagnostics

### Serial Commands for Diagnostics

```
S           - Show status (voltage, temps, motor speeds)
V           - Show firmware version
E           - Read encoder values
M 0 0       - Stop all motors (emergency)
M 100 100   - Test forward at full speed
M -100 -100 - Test backward at full speed
CAL         - Run calibration procedure
RST         - Reset controller
```

### Log File Analysis

If you've captured serial output:
1. Save as .txt file
2. Look for ERROR keywords
3. Note timestamp of failures
4. Check error codes (see firmware documentation)

---

## 💡 Common Mistakes

❌ **Don't**:
- Power on while holding wheels (locked rotor can damage motor)
- Use wrong voltage power supply
- Mix different battery types
- Force connectors (can damage pins)
- Operate in extremely wet conditions (unless waterproofed)

✅ **Do**:
- Double-check polarity before connecting power
- Use appropriate torque when tightening fasteners
- Keep motors cool with breaks
- Test on safe surface before autonomous operation
- Regular maintenance and inspection

---

**Last Updated**: 2026-07-09  
**Still need help?** Open an issue or contact support@jcrobot.com
