# Rooftop Solar PV Design: Layout Optimization Under Partial Shading

A rooftop solar PV system design and shading study, combining PVsyst simulation with AutoCAD electrical drawings and a bill of materials.

## Project summary

- **System size:** 78.3 kWp DC (135 modules x 580 Wp), 80 kWac inverter
- **Orientation:** Fixed tilt 21 degrees, azimuth -4 degrees (panels rotated slightly east of true south to match the building's axis)
- **Tools used:** PVsyst (evaluation version) for energy simulation, AutoCAD for array layout and single-line diagram

## The shading study

The roof has two stair-room structures and a water tank that cast partial shade on parts of the array. Three design variants were simulated to see how layout choices affect annual output:

| Variant | Row spacing | Layout | Produced Energy (kWh/yr) | Specific Yield (kWh/kWp/yr) | Performance Ratio |
|---|---|---|---|---|---|
| A | 3.0 m | Single block, all 9 rows together | 102,661 | 1,311 | 73.3% |
| B | 3.5 m | Single block, all 9 rows together | 104,858 | 1,339 | 74.9% |
| C | 3.5 m | Rows split into two groups, moved away from obstacles | 111,924 | 1,429 | 79.9% |

**Key finding:** widening row spacing from 3.0 m to 3.5 m recovered about 2% more energy by reducing row-to-row shading. Repositioning the array into two groups, clear of the stair rooms and tank, recovered a further ~6.7%, for a total gain of about 9% over the original layout. The improvement is most visible in winter months, where Variant A's Performance Ratio dropped as low as 0.53 (December), while Variant C stayed above 0.79 all year.

Full PVsyst reports for all three variants are in `/pvsyst_reports`.

## Drawings

- `drawings/array_layout.dwg` / `.pdf` — roof outline, obstacle positions, panel array layout, inverter and ACDB placement, cable routing
- `drawings/single_line_diagram.dwg` / `.pdf` — electrical single-line diagram: array strings, inverter, ACDB (SPD + MCCB), grid connection, earthing

## Bill of Materials

See `bom/bill_of_materials.csv` for the full parts list (modules, inverter, cabling, protection devices, mounting structure, earthing).

## Assumptions and limitations

- Roof and obstacle dimensions were measured from satellite imagery (Google Earth), traced and scaled in AutoCAD. Expect a few percent measurement error.
- Obstacle heights (stair rooms, tank) were assumed where they could not be measured directly.
- Weather data is PVsyst's synthetic Meteonorm 9.0 dataset, not on-site measured data.
- Simulations were run using PVsyst's evaluation (trial) version.
- PV module and inverter models (HYPERSOL, Sungrow SH80CX) are drawn from PVsyst's generic/database entries and should be cross-checked against real datasheets before use in an actual installation.
- Exact site coordinates and the institution's name have been withheld from all published files.

## Author

Soham Pandit
