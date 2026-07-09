# Assembly Guide - Komodo Series Chassis

Complete step-by-step assembly instructions for all Komodo chassis variants.

## ⚠️ Safety First

Before beginning assembly:
- [ ] Read all instructions completely
- [ ] Gather all required tools
- [ ] Work on a clean, flat, well-lit workspace
- [ ] Remove all power sources
- [ ] Wear ESD wrist strap when handling electronics
- [ ] Keep small parts away from children and pets

## 🔧 Tools Required

### Basic Tools
- Phillips head screwdriver
- Hex wrench set (2mm, 2.5mm, 3mm)
- Flat head screwdriver (for battery connector)
- Needle-nose pliers
- Wire strippers (for custom connections)
- Small hammer (plastic mallet preferred)

### Specialized Tools (Optional)
- Multimeter (for voltage verification)
- Torque wrench (for critical fasteners)
- ESD mat and wrist strap
- Flux pen (for soldering, if needed)

## 📦 Parts Checklist

Before assembly, verify you have all components. See `/hardware/BOM/` for complete parts list for your model.

**Common Parts Across All Models**:
- ✓ Chassis frame (1)
- ✓ Wheels (2)
- ✓ Motors with encoders (2)
- ✓ Motor controller board (1)
- ✓ Battery (1)
- ✓ Caster wheel (1, if applicable)
- ✓ Various fasteners (bolts, nuts, washers)
- ✓ Connector cables (power, motor, sensor)
- ✓ Documentation and warranty card (1)

## 🏗️ Assembly Steps - All Models

### Phase 1: Frame Preparation

**Time**: 10-15 minutes

1. **Inspect Frame**
   - Check for cracks or deformation
   - Verify all mounting holes are clear
   - Clean any debris or protective coatings

2. **Attach Motor Mounting Brackets** (if not pre-installed)
   - Locate motor bracket attachment points on frame
   - Insert bracket bolts through frame (from inside)
   - Secure with washers and lock nuts
   - Torque: 2.5 N⋅m (snug, not over-tight)

   ![Motor Bracket Installation]
   ```
   Frame side view:
   [===] ← Motor mounting bracket
   |   |
   |   |
   [===]
   ```

3. **Install Motor Mounting Rails**
   - Slide motor mounting rails into frame slots
   - Ensure smooth horizontal movement
   - Test bracket can slide 5-10mm for motor alignment

### Phase 2: Motor Installation

**Time**: 15-20 minutes

1. **Prepare Motors**
   - Inspect motor shaft and coupling
   - Clean shaft of any oil or debris
   - Check encoder cable for damage

2. **Mount First Motor**
   - Position motor into bracket
   - Align motor shaft with wheel hub location
   - Insert mounting bolts through bracket into motor
   - **Do NOT fully tighten yet**

3. **Wheel Hub Alignment**
   - Mount wheel hub onto motor shaft
   - Ensure hub collar is flush with motor shaft
   - Verify no gap between motor and hub
   - Tighten hub set screw(s) with hex wrench
   - Torque: 1.5-2.0 N⋅m

4. **Secure Motor**
   - Now fully tighten motor mounting bolts
   - Torque: 3.0 N⋅m
   - Verify motor cannot shift or rotate in bracket

5. **Repeat for Second Motor**
   - Follow steps 2-4 for opposite side motor
   - Ensure both motors are at same height and angle
   - **Critical**: Motors must be parallel (wheel bases aligned)

### Phase 3: Wheel Installation

**Time**: 10 minutes

1. **Prepare Wheels**
   - Verify wheel is not cracked or deformed
   - Check bearing rotates freely
   - Clean wheel surface

2. **Mount Wheel on Hub**
   - Slide wheel onto motor hub
   - Align key or flat spot if applicable
   - Insert retaining pin or secure bolt
   - Torque wheel bolt: 2.5-3.0 N⋅m

3. **Test Wheel Rotation**
   - Manually spin each wheel
   - Should rotate smoothly with minimal resistance
   - Check for wobble or rubbing

4. **Install Caster/Support Wheel** (if applicable)
   - Locate caster mounting bracket on frame
   - Secure caster wheel bracket
   - Ensure caster height matches drive wheels
   - Verify caster can rotate freely

### Phase 4: Controller Installation

**Time**: 10-15 minutes

1. **Prepare Mounting Surface**
   - Identify controller mounting location (typically above motors)
   - Clean mounting surface
   - Apply self-adhesive rubber isolators to four corners

2. **Mount Motor Controller**
   - Carefully place controller on mounting surface
   - Align with mounting holes
   - Secure with M3 bolts and spacers
   - Torque: 1.0 N⋅m (gentle - don't crack PCB)

3. **Connect Motor Power**
   - Locate motor A and B connectors on controller
   - Connect Motor 1 power cable to Motor A output
   - Connect Motor 2 power cable to Motor B output
   - **Verify polarity**: Red = +, Black = −
   - Secure connectors firmly

4. **Connect Encoder Feedback** (if not integrated)
   - Locate encoder input connectors
   - Connect Motor 1 encoder to Encoder A input
   - Connect Motor 2 encoder to Encoder B input
   - Color code: Yellow = signal, Green = reference, Black = ground

5. **Verify Connections**
   - Visually inspect all connections
   - Gently tug each connector to verify secure seating
   - No exposed pins should be visible

### Phase 5: Power System

**Time**: 10-15 minutes

1. **Battery Positioning**
   - Locate battery compartment or mounting bracket
   - Verify adequate ventilation around battery
   - Install battery mounting straps
   - **Do NOT mount upside down**

2. **Battery Connections**
   - Locate battery connector (XT60, XT90-S, or Anderson)
   - Connect positive (red) wire to controller + input
   - Connect negative (black) wire to controller - input
   - **Critical**: Double-check polarity before connecting

   ```
   Battery (+)  →  Controller VBat(+)
   Battery (−)  →  Controller GND(−)
   ```

3. **Power Distribution** (if multiple components)
   - Connect power to sensor hub (if present)
   - Connect power to onboard computer (if present)
   - Ensure all power cables secured and insulated

4. **Voltage Verification**
   - **Power OFF** initially
   - Use multimeter to verify battery voltage (24V nominal)
   - Verify no shorts exist
   - Only then proceed to power-on

### Phase 6: Cable Management

**Time**: 5-10 minutes

1. **Route Cables**
   - Keep encoder cables away from motor power cables
   - Bundle sensor cables together
   - Keep all cables above/away from rotating wheels
   - Use cable ties or spiral wrap

2. **Secure Loose Cables**
   - Attach cables to frame with adhesive mounts or ties
   - Ensure cables cannot get pinched
   - Leave loop for vibration absorption
   - No cable should pull under tension

3. **Label Connectors** (recommended)
   - Use masking tape + marker to label cables
   - Example: "Motor A", "Encoder B", "Sensor Power"
   - Saves troubleshooting time later

### Phase 7: Final Assembly Checks

**Time**: 10 minutes

**Visual Inspection**:
- [ ] All fasteners present and tight
- [ ] No loose wires or connectors
- [ ] Motors aligned and level
- [ ] Wheels spin freely
- [ ] Caster wheel (if present) moves smoothly
- [ ] Controller securely mounted
- [ ] Battery secured in place
- [ ] All cables routed safely

**Mechanical Test** (Power OFF):
- [ ] Manually spin each wheel - should be smooth
- [ ] Push chassis gently - should not rock or shift
- [ ] Rock chassis side-to-side - no looseness
- [ ] Try to shift motor mounting - should not move

**Electrical Verification** (Still Power OFF):
- [ ] Multimeter shows ~24V at battery
- [ ] All connectors seated firmly
- [ ] No exposed pins or wires
- [ ] No visible damage to PCBs
- [ ] No burn marks or corrosion

### Phase 8: Ready for Power-On

Once all checks complete:
- [ ] Assembly complete
- [ ] All safety checks passed
- [ ] Ready to proceed to [Getting Started Guide](./getting-started.md)

## 🔧 Model-Specific Notes

### Komodo-ZERO Assembly
- Lightweight design - minimal fastener torque required
- All mounting points use 2mm hex wrenches
- Simple 2-motor configuration ideal for beginners
- Estimated assembly time: 45 minutes

### Komodo-01 Assembly
- Mid-range complexity
- Some M12 circular connectors (weatherproof)
- CAN bus optional (requires soldering if adding)
- Estimated assembly time: 1-1.5 hours

### Komodo-02 Assembly
- Heavy-duty components require careful handling
- Dual motor controllers possible (for higher power)
- Anderson connector requires proper crimping tools
- Estimated assembly time: 1.5-2 hours

## 🚨 Common Assembly Mistakes

### ❌ Incorrect Motor Polarity
**Problem**: Motors spin backwards
**Solution**: Swap one motor's power connections (swap red and black)

### ❌ Misaligned Motor Mounting
**Problem**: Wheels not parallel, robot pulls to one side
**Solution**: Measure motor heights and adjust brackets for parallel alignment

### ❌ Loose Fasteners
**Problem**: Components shift or rattle during operation
**Solution**: Go back through all bolts and ensure proper torque

### ❌ Encoder Cable Damage
**Problem**: No encoder feedback, motor speeds uncontrolled
**Solution**: Inspect encoder cables for pinching, repair or replace if damaged

### ❌ Power Connector Reversed
**Problem**: Smoke/fire, component damage
**Solution**: ALWAYS verify battery polarity before connecting

## 📸 Photo Documentation

Take photos at each assembly phase for reference:
1. Frame preparation
2. Motors installed
3. Wheels mounted
4. Controller connected
5. Power connections
6. Final assembly

Save these photos for troubleshooting or warranty claims if issues arise.

## 🎯 Troubleshooting Assembly

**If assembly doesn't work:**

1. **Review this guide** completely
2. **Compare with 3D model** in `/3d-models/` for your variant
3. **Check BOM** in `/hardware/BOM/` to verify correct parts
4. **Take photos** and ask in [GitHub Discussions](../../discussions)
5. **Contact support**: support@jcrobot.com

## ✅ Post-Assembly Steps

After assembly completion:
1. Follow [Getting Started Guide](./getting-started.md)
2. Perform firmware flashing if required
3. Run initial motor tests
4. Perform calibration procedure
5. Test movement in safe area

## 📞 Need Help?

- **Detailed Video Tutorials**: Available at [JCROBOT YouTube Channel]
- **CAD Models**: See `/3d-models/` directory for visual reference
- **Community Help**: Post in [GitHub Discussions](../../discussions)
- **Technical Support**: Email support@jcrobot.com

---

**Estimated Total Assembly Time**:
- Komodo-ZERO: 45 minutes
- Komodo-01: 1-1.5 hours
- Komodo-02: 1.5-2 hours

**Next Steps**: Proceed to [Getting Started Guide](./getting-started.md)

---

**Last Updated**: 2026-07-09
