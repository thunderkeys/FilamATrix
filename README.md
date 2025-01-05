# FilamAtrix Mod

| <img src="https://raw.githubusercontent.com/thunderkeys/FilamAtrix/refs/heads/main/images/filamatrix_cw2.png" width=40%> | <img src="https://raw.githubusercontent.com/thunderkeys/FilamAtrix/refs/heads/main/images/filamatrix_g2e.png" width=40%> |

This an adapation of the [Filametrix](https://github.com/sorted01/Filametrix) mod for [BoxTurtle](https://github.com/ArmoredTurtle/BoxTurtle) Kit users.
n
FilamAtrix modifies the [VORON Design](https://www.vorondesign.com) [StealthBurner hotend and Clockwork 2 Extruder](https://github.com/VoronDesign/Voron-Stealthburner/) or [Galileo 2 Extruder](https://github.com/JaredC01/Galileo2/tree/main/galileo2_extruder) to support a kinematic-actuated cutting blade for cleaner, more reliable automated filament changes that also eliminates the need for tip forming.

FilamAtrix consolidates the CAD for Filametrix and G2E-Filametrix into a single file and provides a reorganized repository with a clear structure of what files are needed to print.  

In addition, the print files have been modified from the upstream repo with the following changes:

- Hotend mounts/Printheads now use M3 threaded heat insert (instead of a M3 nut) for simpler installation and maintenance.  Many thanks to [hartk](https://github.com/hartk1213) for this idea!
<img src="https://raw.githubusercontent.com/thunderkeys/FilamAtrix/refs/heads/main/images/m3_heat_insert_hotend.png" width=50%>
- On Clockwork 2, there is an increased depth for the PTFE tubing to better help guide the filament towards the extruder gears and make insertion less position dependent. <img src="https://raw.githubusercontent.com/thunderkeys/FilamAtrix/refs/heads/main/images/cw2_section_analysis.png" width=50%>
- Cutting arm has been modified to support a full length M2.5x16 FHCS.
- Inclusion of the Beefy Depressor mount as the default.


## Bill of Materials
BoxTurtle kits provided by LDO or Isik's Tech come with all of the physical hardware necessary for FilamAtrix, but below is the BOM needed to build it.

 Item    | Quantity | Notes | Source
 ----   | -------- | ------ | -----
Loctite or Vibratite | 1        | Loctite Blue 242 or Vibra-Tite VC-3  |
M3 nut  | 2 | DIN934 | [McMaster-Carr](https://www.mcmaster.com/90591A250/) [AliExpress](https://www.aliexpress.us/item/2255800690659531.html)
M3 washer | 2 | 0.5mm thickness | [KB-3D](https://kb-3d.com/store/inserts-fasteners-adhesives/287-3x6x05mm-shim-ring-washer-pack-of-50-din988-1634423217623.html)
M3x16 BHCS | 1 | | [AliExpress](https://www.aliexpress.us/item/2251832624537980.html)
M3x18 SHCS | 1 | | [AliExpress](https://www.aliexpress.us/item/2251832624557792.html)
M3xD5xL4 Threaded Heatset insert | 5 | [AliExpress](https://www.aliexpress.us/item/2255800046543591.html)
M3x18 FHCS | 1 | | [AliExpress](https://www.aliexpress.us/item/3256804926092900.html)
M3x8 SHCS | 1 | | [AliExpress](https://www.aliexpress.us/item/2251832624557792.html)
M3x6, M3x10 or M3x12 FHCS | 2 | 6mm - no backers, 10mm - titanium backers, 12mm - MGN9 rails | [AliExpress](https://www.aliexpress.us/item/3256804926092900.html)
M2.5x16 | 1 |  | [AliExpress](https://www.aliexpress.us/item/2251832747871730.html)
0.4mm x 4mm x 15mm spring | 1 | A spring from a common ballpoint pen can also work |
Type 4 metal hobby blade | 1 | |

## Files to print

- [beefy_depressor_mount.stl](https://github.com/thunderkeys/FilamAtrix/blob/main/STLs/beefy_depressor_mount.stl)
- [beefy_depressor.stl](https://github.com/thunderkeys/FilamAtrix/blob/main/STLs/beefy_depressor.stl)
- Respective parts for your extruder - [Clockwork2](https://github.com/thunderkeys/FilamAtrix/tree/main/STLs/Clockwork2) or [Galileo2_Extruder](https://github.com/thunderkeys/FilamAtrix/tree/main/STLs/galileo2_extruder)
- [Stealthburner modified parts](https://github.com/thunderkeys/FilamAtrix/tree/main/STLs/Stealthburner) - pick the set (front+rear) specific to your Printhead/Hotend

## Assembly and Installation
Coming soon

## AFC Configuration

Now that FilamAtrix is installed, we need to configure the [AFC Klipper Add-On](https://github.com/ArmoredTurtle/AFC-Klipper-Add-On) for the locations to actuate the cutter arm.

- Home all printer axes (e.g., using G28)
- Use mainsail/fluidd/klipperscreen/etc controls to jog the toolhead near the cutting pin.  This will likely be near X minimum (e.g. X=15-20) and Y maximum if installed in the default location.
- Move the toolhead in 1mm increments until you are just about to depress the pin.  Make note of these coordinates.
- Continue to move the toolhead in 1mm increments until the cutting arm is fully depressed. Make a note of the fully depressed coordinates.
- Update ``AFC/AFC_Macro_Vars.cfg`` with these values as per the comments in the ``_AFC_CUT_TIP_VARS`` section.


## Acknowledgements
- [Wondro](https://github.com/Wondro) and [ArmoredTurtle](https://github.com/ArmoredTurtle/) for the modified CAD for FilamAtrix
- [hartk](https://github.com/hartk1213) for the idea to use an M3 threaded heat insert for the hotend mount
- [sorted01](https://github.com/sorted01) for the original [Filametrix](https://github.com/sorted01/Filametrix) project - you can [donate here](https://www.paypal.com/paypalme/sorted01) to him if interested
- [IRTrail](https://github.com/IRTrail) for the [G2E-Filametrix](https://github.com/IRTrail/G2E-Filametrix) project (now archived as read-only, as of 2024-12-12).
