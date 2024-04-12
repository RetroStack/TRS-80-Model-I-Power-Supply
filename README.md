# TRS-80 Model 1 Power Supply

This project is a reimplementation of the TRS-80 Model 1 Power Supply that replicates the DC and AC voltages needed to run the original system. This revision is based on the original design and uses some of the findings from [www.shockrisk.com](https://www.shockrisk.com/index.php/2023/10/14/trs-80-model-1-power-supply/). The entire project is available under the MIT license.

**NOTE**: There is [another power supply](https://github.com/maboytim/TRS-80_Model1_Power_Supply) available by Matt Boytim that appears to be smaller and cheaper. Consider using that design.

**WARNING**: Since this project works with high voltages, please only do this if you know what you are doing. Working on high voltages can kill you! Additionally, doing things incorrectly could burn down your house.

![E1 Replica](/Latest/TRS80_Model_I_Power_Supply_Photo.png)

## Project Details

### Latest Files

In the "Latest" folder, you'll find the most up-to-date design files, including:

- Gerber files suitable for popular online PCB manufacturers like [PCBWay](/Latest/TRS80_Model_I_Power_Supply_Gerber_PCBWay.zip) and [JLCPCB](/Latest/TRS80_Model_I_Power_Supply_Gerber_JLCPCB.zip). Most manufacturers should be fine with either.
- A Bill of Materials (BOM) in both [CSV](/Latest/TRS80_Model_I_Power_Supply_BOM.csv) and [PDF](/Latest/TRS80_Model_I_Power_Supply_BOM.pdf) formats. (Also, see the list below.)
- The [full schematics](/Latest/TRS80_Model_I_Power_Supply_Schematics.pdf).
- 3D Objects of [Base](/3DPrint/Base.stl) and [Lid](/3DPrint/Lid.stl) for 3D printing.

### Bill of Materials (BOM)

Below is a list of materials needed to assemble a complete power supply. Please note that the links and prices (as of March 31st, 2024) will not be updated in the future and should only be used as a reference for locating the correct items.

Note: Links and alternatives are provided to assist you in finding the necessary components. I cannot guarantee the complete accuracy or reliability of all these links and alternatives. Please check it for yourself!

|Reference|Quantity|Value|Component Name|Description|Source Comment|Source Cost USD|Source Total Cost USD|Source|
|-|-|-|-|-|-|-|-|-|
|D1, D2|2|1N4001|50V 1A General Purpose Rectifier Diode, DO-41|Rectifying diodes||$0.10|$0.20|[Mouser](https://www.mouser.com/ProductDetail/637-1N4001)|
|F1|1|~|250V 1A Fast Blow 5x20mm|||$0.36|$0.36|[Mouser](https://www.mouser.com/ProductDetail/504-BK1-S500-1-R)|
|T1|1||F-241U|Transformer, single primary, dual secondary||$25.10|$25.10|[Mouser](https://www.mouser.com/ProductDetail/553-F241U)|
||1||PCB||Lot of 5|~$0.40|~$0.40|-|
||8|M3 3x5mm|Knurled Nut||Kit|~$0.00|~$0.00|[Amazon](https://www.amazon.com/Ktehloy-Threaded-Assortment-Printing-Components/dp/B0CLKDPN65/)|
||2|M3 4mm|Screw /w Sunk head,For Power unit||||-|
||2|M3 6mm|Screw|For PCB||||-|
||4|M3 8mm|Screw|For Lid||||-|
||4|M4 4x6mm|Knurled Nut|All 4 to hold transformer in place|Kit|~$0.00|~$0.00|[Amazon](https://www.amazon.com/Ktehloy-Threaded-Assortment-Printing-Components/dp/B0CLKDPN65/)|
||4|M4 6mm|Screw|Transformer||||-|
||6|FDFD1.25-187|Female Insulating Spade Connector|Cables for terminals of the power unit|Lot of 100|~$0.00|~$0.00|[AliExpress](https://www.aliexpress.us/item/2251832640697906.html)|
||1||Power Unit|With switch and Fuse holder||$3.30|$3.30|[AliExpress](https://www.aliexpress.us/item/3256805889410008.html)|
||1||Strain Relief|Cable Strain Relief|Lot of 10|$0.68|$0.68|[Amazon](https://www.amazon.com/gp/product/B08T6DZB4C/)|
||1||Lid|3D Printed||||-|
||1||Base|3D Printed||||-|

### Assembly

**Prepare Case**
1. 3D print case (lid and base) or order from manufacturer.
2. (a) If 3D printed with PLA and similar, use a soldering iron to set the knurled nuts. You can buy a set of tools to simplify this, but a soldering iron is enough.
3. (b) If 3D printed with resin, drill out a bit more space on all the 6 places and set the knurled nuts with super glue. Make sure to not cover the threads as it would give you trouble later to screw things in. Wait for it to get really solid before moving on.

![3D Case](/Images/3DPrint_Model.png)

4. Paint the lettering on the top. I was able to do this nicely with a foam brush. Optionally add a clear coat to protect the paint from rubbing off.
5. Screw in the transformer with the M4 screws.

**Electronics**
1. Crimp two short wires to add a jumper between the neutral to the switch and another from the fuse to the switch. One side of the switch will be the terminals of the light (you can often see the leads for the lightbulb). You want the one side not for the light so the light only turns on when switch is turned on. You can swap them around later if you find it isn't correct. For the wire, I used AWG 26.

![Power Unit](/Images/Power_Unit.png)

2. Crimp two more wires on one side, each connecting to ther other side of the switch and carrying the 110V AC. For the wire, I used AWG 26.
3. Solder the last two wires into place on the side of the transformer with only two terminals. This is the primary side.
4. Solder 6 wires to the secondary side of the transformer. Make sure that each wire can reach to the PCB area.
5. Add the two diodes on the PCB. Make sure to put them into the correct direction as indicated on the PCB and the line on the diodes. Both diodes are oriented in the same direction.
6. Solder all 6 wires to the PCB sequentially as shown. First, SA# are the top 3 terminals from left to right. Second, SB# are the bottom 3 terminals from left to right.

![PCB](/Images/PCB_Overview.png)

7. Solder the two AC wires (marked "~") from the cable going to the computer. Confirm that these are the right wires with the graphic shown below.
8. Solder the two other wires (marked "+" and "-") from the cable going to the computer. Confirm that these are the right wires with the graphic shown below.

![PCB](/Images/DIN-5_Connector.png)

9. (optional) Add some glue to add some kind of strain relief on the wires themselves.
10. (optional) Add a cable-tie around the cable to add an additional way of strain relief.
11. Finally, add the plastic grommet which is used as the main method of strain relief.
12. Screw in PCB
13. Screw in Power Unit
14. Screw the lid to the top
15. Add fuse to the fuse holder

### Implementation

E1 has been implemented using KiCAD 7. The KiCAD project files are included in this repository.

![Front](/Latest/TRS80_Model_I_Power_Supply_3D_Front.png)
![Back](/Latest/TRS80_Model_I_Power_Supply_3D_Back.png)

### RetroStack Libraries

To work with this KiCAD project, you'll need the RetroStack libraries for KiCAD. Please [follow this link](https://www.github.com/RetroStack/KiCAD-Libraries) to access and install these libraries.

## Main TRS-80 Model 1 Repository

For additional resources related to the TRS-80 Model 1, be sure to check out the central page for the TRS-80 Model 1 on RetroStack. You can find it [here](https://www.github.com/RetroStack/TRS-80-Model-I).

## Support this Project

RetroStack is passionate about exploring and preserving the legacy of older computer systems. My work involves creating detailed documentation and videos to share the knowledge. I am also dedicated to reviving these classic systems by reimplementing them and offering replacement parts at no cost. If you're keen on supporting this unique project, I invite you to visit my [Patreon page](https://www.patreon.com/RetroStack). Your support would be immensely valuable and greatly appreciated!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
