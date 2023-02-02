Designs go through several phases of development:
- Design space exploration and modelling
- RTL design
- Logic synthesis
- Layout/Place and Route
- Electrical checking

## Physical Instantiation
'Wish list' for going from a theoretical functional design to a physical one. Here are some constraints:
- Clock period (performance)
- Floorplan/pinout
- Area/density (cost)
- Power

These are often **antagonistic** so an acceptable **trade-off** needs to be sought.

## Post-layout tools
- DRC: Design Rule Check
- ERC: Electrical Rule Check
- LVS: Layout Versus Schematic

## Placement in chip design
• Chip placement is one of the most complex and time-consuming stages of the chip design process.
• The process of determining the exact locations of the various circuit elements in a chip. 
• It involves placing the netlist onto a chip canvas (a 2D grid), such that power, performance, and area (PPA) are minimized, while adhering to constraints on density and routing congestion. An optimisation with multi-faceted design criteria.