# FilamATrix Mod

<img src="https://raw.githubusercontent.com/thunderkeys/FilamATrix/refs/heads/main/images/filamatrix_cw2.png" width=40%> <img src="https://raw.githubusercontent.com/thunderkeys/FilamATrix/refs/heads/main/images/filamatrix_g2e.png" width=40%>

This an adapation of the [Filametrix](https://github.com/sorted01/Filametrix) mod for [BoxTurtle](https://github.com/ArmoredTurtle/BoxTurtle) Kit users (but use of BoxTurtle/AFC are not required - this mod can be used anywhere Filametrix/G2E-Filametrix are).

FilamATrix modifies the [VORON Design](https://www.vorondesign.com) [StealthBurner hotend and Clockwork 2 Extruder](https://github.com/VoronDesign/Voron-Stealthburner/) or [Galileo 2 Extruder](https://github.com/JaredC01/Galileo2/tree/main/galileo2_extruder) to support a kinematic-actuated cutting blade for cleaner, more reliable automated filament changes that also eliminates the need for tip forming.

FilamATrix consolidates the CAD for Filametrix and G2E-Filametrix into a single file and provides a reorganized repository with a clear structure of what files are needed to print.  

In addition, the print files have been modified from the upstream repo with the following changes:

- Hotend mounts/Printheads now use M3 threaded heat insert (instead of a M3 nut) for simpler installation and maintenance.  Many thanks to [hartk](https://github.com/hartk1213) for this idea!<br><img src="https://raw.githubusercontent.com/thunderkeys/FilamATrix/refs/heads/main/images/m3_heat_insert_hotend.png" width=50%>

- On Clockwork 2, there is an increased depth for the PTFE tubing to better help guide the filament towards the extruder gears and make insertion less position dependent.<br><img src="https://raw.githubusercontent.com/thunderkeys/FilamATrix/refs/heads/main/images/cw2_section_analysis.png" width=50%>

- Cutting arm has been modified to support a full length M2.5x16 FHCS.

- Inclusion of the Beefy Depressor mount as the default.


## Bill of Materials
BoxTurtle kits provided by LDO or Isik's Tech come with all of the physical hardware necessary for FilamATrix, but below is the BOM needed to build it.

 Item    | Quantity | Notes | Source
 ----   | -------- | ------ | -----
Loctite or Vibratite | 1        | Loctite Blue 242 or Vibra-Tite VC-3  | [Amazon Loctite](https://www.amazon.com/Loctite-Heavy-Duty-Threadlocker-Single/dp/B000I1RSNS) \| [Amazon Vibratite](https://www.amazon.com/Vibra-TITE-213-Threadmate-Threadlocker-Degree/dp/B0088YEGXM)
M3 hex nut | 1 | DIN934 | [McMaster-Carr](https://www.mcmaster.com/90591A250/) \| [AliExpress](https://www.aliexpress.us/item/2255800690659531.html)
M3 washer | 2 | 0.5mm thickness | [KB-3D](https://kb-3d.com/store/inserts-fasteners-adhesives/287-3x6x05mm-shim-ring-washer-pack-of-50-din988-1634423217623.html)
M3x16 BHCS | 1 | | [AliExpress](https://www.aliexpress.us/item/2251832624537980.html)
M3x18 SHCS | 1 | | [AliExpress](https://www.aliexpress.us/item/2251832624557792.html)
M3xD5xL4 Threaded Heatset insert | 5 | | [AliExpress](https://www.aliexpress.us/item/2255800046543591.html)
M3x18 FHCS | 1 | | [AliExpress](https://www.aliexpress.us/item/3256804926092900.html)
M3x8 SHCS | 1 | | [AliExpress](https://www.aliexpress.us/item/2251832624557792.html)
M3x10, M3x12 or M3x16 SHCS | 2 | 10mm - no backers, 12mm - titanium backers, 16mm - MGN9 rails | [AliExpress](https://www.aliexpress.us/item/3256804926092900.html)
M3 roll-in T-Nut | 2 | | [AliExpress](https://www.aliexpress.us/item/2251832618848960.html)
M2.5x16 | 1 |  | [AliExpress](https://www.aliexpress.us/item/2251832747871730.html)
0.5mm x 4mm x 25mm coil spring | 1 | A spring from a common ballpoint pen can also work | [Amazon](https://www.amazon.com/uxcell-Compression-Spring-Stainless-Length/dp/B0CGZRR4JT) \| [AliExpress](https://www.aliexpress.us/item/3256803316195677.html)
Type 4 metal hobby blade or OLFA KB4-F/5 8mm chisel blade | 1 | | [Amazon Hobby 4](https://www.amazon.com/HARFINGTON-Replacement-Precision-Refills-Scrapbooking/dp/B0CBLRNXSV) \| [OLFA Website](https://olfa.com/products/olfa-kb4-f-5-chisel-art-blades-5pk#shop) \| [Amazon OLFA](https://www.amazon.com/OLFA-9166-KB4-F-Chisel-5-Pack/dp/B000BNXOOU) \| [AliExpress OLFA](https://www.aliexpress.us/item/3256805333623451.html)

## Print settings
All files are to be printed using 'VORON Standard' parts settings/filaments:

- 3D Printing Process: Fused Deposition Modeling (FDM)
- Material: ABS/ASA
- Layer Height: 0.2mm
- Extrusion width: Forced 0.4mm
- Infill Type: Grid, Gyroid, Honeycomb, Triangle or Cubic
- Infill Percentage: 40%
- Wall Count: 4
- Solid Top/Bottom Layers: 5

## Files to print
**LDO Kit users** - If you are running a recent RevD LDO kit with the stock Revo Voron hotend, print [these files](https://github.com/thunderkeys/FilamATrix/tree/main/STLs/LDO).  

**Other users, print these files**
- [beefy_depressor_mount.stl](https://github.com/thunderkeys/FilamATrix/blob/main/STLs/beefy_depressor_mount.stl)
- [beefy_depressor.stl](https://github.com/thunderkeys/FilamATrix/blob/main/STLs/beefy_depressor.stl)
- [\[a\]\_knife_holder.stl](https://github.com/thunderkeys/FilamATrix/blob/main/STLs/%5Ba%5D_knife_holder.stl)
- Respective parts for your extruder - [Clockwork2](https://github.com/thunderkeys/FilamATrix/tree/main/STLs/Clockwork2) or [Galileo2_Extruder](https://github.com/thunderkeys/FilamATrix/tree/main/STLs/galileo2_extruder)
- [Stealthburner modified parts](https://github.com/thunderkeys/FilamATrix/tree/main/STLs/Stealthburner) - pick the set (front+rear) specific to your Printhead/Hotend
- [cutting jig for your hotend](https://github.com/thunderkeys/FilamATrix/blob/main/STLs/README.md) - use a razor blade to cut a section of 2mm ID PTFE to length for your hotend.

If you are using the OLFA KBF-4/5 chisel blades, you may need to slightly scale the knife holder up in the Z dimension in your slicer software to accomodate the wider tang. A good starting point for me was scaling Z to 105% (8.4mm total height).

## Assembly and Installation
Coming soon

## Preparing and mounting of the Beefy Depressor

Install an M3 heatset on both sides of the beefy depressor pin. Attach the pin to the mount using the M3x18 FHCS. Thread the M3 hexnut onto the M3x16 BHCS and install that on the end facing into the printer.  Use the hexnut to 'lock' the screw into position, you may wish to use the Loctite or VC-3 here on this screw. Careful not to get Loctite on any ABS/ASA printed parts!

Attach the assembled mount to the gantry using M3 screws (place M3 washers between the screws and the printed part).  The length of the screw will likely be printer-dependent, see above BOM for suggested sizes.

Once installed, adjust the height of the pin on the mount and the depth of the screw so it will depress the cutting arm when the toolhead hits against it (going from right to left).

Depending on your printer you may find it more advantageous to mount the beef depressor at the rear, or at the front.  See below for example mounting locations on an example Voron 2.4 printer gantry.

### Rear
<img src="https://raw.githubusercontent.com/thunderkeys/FilamATrix/refs/heads/main/images/gantry_mount_rear1.png" width=40%> <img src="https://raw.githubusercontent.com/thunderkeys/FilamATrix/refs/heads/main/images/gantry_mount_rear2.png" width=40%>

### Front
<img src="https://raw.githubusercontent.com/thunderkeys/FilamATrix/refs/heads/main/images/gantry_mount_front1.png" width=40%> <img src="https://raw.githubusercontent.com/thunderkeys/FilamATrix/refs/heads/main/images/gantry_mount_front2.png" width=40%>

## AFC Configuration

Now that FilamATrix is installed, we need to configure the [AFC Klipper Add-On](https://github.com/ArmoredTurtle/AFC-Klipper-Add-On) for the locations to actuate the cutter arm.

- Home all printer axes (e.g., using G28)
- Use mainsail/fluidd/klipperscreen/etc controls to jog the toolhead near the cutting pin.  This will likely be near X minimum (e.g. X=15-20) and Y maximum if installed in the default location.
- Move the toolhead in 1mm increments until you are just about to depress the pin.  Make note of these coordinates.
- Continue to move the toolhead in 1mm increments until the cutting arm is fully depressed. Make a note of the fully depressed coordinates.
- Ensure ``tool_cut: true`` is set in ``AFC/AFC.cfg`` (it is also recommended to enable the park, kick, poop and wipe macros)
- Update ``AFC/AFC_Macro_Vars.cfg`` with these values as per the comments in the ``_AFC_CUT_TIP_VARS`` section.


## Acknowledgements
- [Wondro](https://github.com/Wondro) and [ArmoredTurtle](https://github.com/ArmoredTurtle/) for the modified CAD for FilamATrix
- [hartk](https://github.com/hartk1213) for the idea to use an M3 threaded heat insert for the hotend mount
- [sorted01](https://github.com/sorted01) for the original [Filametrix](https://github.com/sorted01/Filametrix) project - you can [donate here](https://www.paypal.com/paypalme/sorted01) to him if interested
- [IRTrail](https://github.com/IRTrail) for the [G2E-Filametrix](https://github.com/IRTrail/G2E-Filametrix) project (now archived as read-only, as of 2024-12-12).
- [VORON Design](https://www.vorondesign.com) for Stealthburner and Clockwork2
- [JaredC01](https://github.com/JaredC01) for Galileo2
