# Filametrix-BT Mod

![](https://raw.githubusercontent.com/thunderkeys/Filametrix-BT/refs/heads/main/images/filametrix-bt.png)

This an adapation of the [Filametrix](https://github.com/sorted01/Filametrix) mod for [LDO](https://ldomotors.com) [BoxTurtle](https://github.com/ArmoredTurtle/BoxTurtle) Kit users.
n
Filametrix modifies the [VORON Design](https://www.vorondesign.com) [StealthBurner hotend and Clockwork 2 Extruder](https://github.com/VoronDesign/Voron-Stealthburner/) to support a kinematic-actuated cutting blade for cleaner, more reliable automated filament changes that also eliminates the need for tip forming.

Filametrix-BT consolidates the CAD into a single file and provides a reorganized repository with a clear structure of what files are needed to print.  Additionally, the Hotend mounts have been modified by the ArmoredTurtle team to support the chamfered M3 nut that is included with the LDO BoxTurtle kits.

![](https://raw.githubusercontent.com/thunderkeys/Filametrix-BT/refs/heads/main/images/m3_nut_hotend.png)

## Bill of Materials
LDO kits come with all of the physical hardware necessary for Filametrix-BT, but below is the BOM needed to build it.

Item    | Quantity | Notes
-----   | -------- | ------
Loctite or Vibratite | 1        | Loctite Blue 242 or Vibra-Tite VC-3 
M3 nut  | 2 | DIN934
M3 washer | 2 | 0.5mm thickness
M3x16 BHCS | 1 |
M3x18 SHCS | 1 |
M3x5x4 Threaded Heatset insert | 4 |
M3x18 FHCS | 1 |
M3x8 SHCS | 1 |
M3x6, M3x10 or M3x12 FHCS | 2 | 6mm - no backers, 10mm - titanium backers, 12mm - MGN9 rails
M2.5x16 | 1 | 15-18mm will work
0.4mm x 4mm x 15mm spring | 1 | A spring from a common ballpoint pen can also work
Type 4 metal hobby blade | 1 |

## Files to print
### Toolhead
- [Hotend mounts](https://github.com/thunderkeys/Filametrix-BT/tree/main/STLs/Hotend%20Mounts) (front and rear) - one pair, specific to your hotend
- [Latch with ECAS support](https://github.com/thunderkeys/Filametrix-BT/blob/main/STLs/CW2/%5Ba%5D_latch_ecas.stl)
- Main body - [single](https://github.com/thunderkeys/Filametrix-BT/blob/main/STLs/CW2/main_body_single_switch.stl) or [dual](https://github.com/thunderkeys/Filametrix-BT/blob/main/STLs/CW2/main_body_dual_switch.stl) filament sensor options. LDO kits come with parts to build the dual filament sensor version, so we recommend that but if you only have GPIO pins for a single sensor, the option is provided for that as well.
- If you are not on an older Clockwork 2 before official release you may also need a new [motor plate](https://github.com/thunderkeys/Filametrix-BT/blob/main/STLs/CW2/motor_plate.stl)
- [cutting arm](https://github.com/thunderkeys/Filametrix-BT/blob/main/STLs/%5Ba%5D_cutting_arm.stl)
- [knife holder](https://github.com/thunderkeys/Filametrix-BT/blob/main/STLs/%5Ba%5D_knife_holder.stl)
- If this is a new build, you will also need to print the Stealthburner [https://github.com/thunderkeys/Filametrix-BT/tree/main/STLs/Stealthburner](front face), [guidler](https://github.com/thunderkeys/Filametrix-BT/blob/main/STLs/CW2/%5Ba%5D_guidler_a.stl) [halves](https://github.com/thunderkeys/Filametrix-BT/blob/main/STLs/CW2/%5Ba%5D_guidler_b.stl), [shuttle](https://github.com/thunderkeys/Filametrix-BT/blob/main/STLs/CW2/%5Ba%5D_shuttle.stl), [pcb spacer](https://github.com/thunderkeys/Filametrix-BT/blob/main/STLs/CW2/%5Ba%5D_pcb_spacer.stl) and [cable cover](https://github.com/thunderkeys/Filametrix-BT/tree/main/STLs/CW2).

#### Cutting point on gantry
- [depressor_mount](https://github.com/thunderkeys/Filametrix-BT/blob/main/STLs/depressor_mount.stl)
- [depressor](https://github.com/thunderkeys/Filametrix-BT/blob/main/STLs/depressor.stl)

## Assembly and Installation
Updated instructions to come.

## AFC Configuration

Now that Filametrix-BT is installed, we need to configure the [AFC Klipper Add-On](https://github.com/ArmoredTurtle/AFC-Klipper-Add-On) for the locations to actuate the cutter arm.

- Home all printer axes (e.g., using G28)
- Use mainsail/fluidd/etc controls to jog the toolhead near the cutting pin.  This will likely be near X minimum (e.g. X=15-20) and Y maximum if installed in the default location.
- Move the toolhead in 1mm increments until you are just about to depress the pin.  Make note of these coordinates.
- Continue to move the toolhead in 1mm increments until the cutting arm is fully depressed. Make a note of the fully depressed coordinates.
- Update ``AFC/AFC_Macro_Vars.cfg`` with these values.

