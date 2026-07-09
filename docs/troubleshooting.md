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

## 🚗 Motor & Movement Issues

### Issue: One Wheel Won't Move

**Symptoms**: Robot pulls to one side, one motor silent

**Solutions**:
1. Check motor power connections
2. Free stuck wheel
3. Verify encoder feedback
4. Swap motor connections to test
5. Update firmware if needed

---

## 🔌 Connectivity Issues

### Issue: No Serial Communication

**Symptoms**: USB connected but no response

**Solutions**:
1. Verify USB connection
2. Check baud rate (115200)
3. Install proper USB drivers
4. Try different USB cable
5. Try different USB port

---

## 📞 Getting Help

- Create a [GitHub Issue](../../issues)
- Join [GitHub Discussions](../../discussions)
- Email: support@jcrobot.com

---

**Last Updated**: 2026-07-09
