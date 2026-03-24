

## Xfoil Direct Design Analysis


## Overview

This study uses XFLR5 to parametrically justify four key design parameters for a hand-launched glider:

| Parameter | Method | Result |
|---|---|---|
| Camber | XFoil Direct Analysis — 10 airfoils | NACA 5412 |
| Best AoA | Cl/Cd vs Alpha curve | 7.5° |
| Taper ratio λ | VLM2 spanwise Cl distribution | λ = 0.5 |
| Sweep angle Λ | VLM2 Cm vs Alpha slope | Λ = 15° |

---

## Design Constraints

| Parameter | Value |
|---|---|
| Wingspan | 1.0 m |
| Launch speed | 10 m/s |
| Target aspect ratio | ~15 |
| Analysis AoA | 7.5° (best glide) |

---

## Airfoil & AoA Selection -XFoil Direct Analysis

### Method

Ten NACA four-digit airfoils were analysed using XFoil Direct Analysis in XFLR5, varying camber from 0% to 9% while holding thickness constant at 12%:

- **Airfoils tested:** NACA 0012, 1412, 2412, 3412, 4412, 5412, 6412, 7412, 8412, 9412
- **Reynolds number:** 200,000
- **NCrit:** 9.0
- **AoA sweep:** −10° to +20° in 0.5° increments
- **Analysis type:** Viscous, Type 1 (fixed speed)

### Results

Cl/Cd was plotted against Alpha. Peak glide efficiency was clustered across NACA 2412–6412, within 1% of each other. NACA 5412 had the higest peak.

**Selected: NACA 5412**
- Peak Cl/Cd = **80** at **7.5° AoA**
- Cl = **1.35** at best glide angle

### Figures

| Figure | Description |
|---|---|
| `1[](results/XFoil_direct_design_graphs/cl_vs_alpha.png)` | Cl vs Alpha — all 10 airfoils |
| `results/Xfoil-direct_design_graphs/clcd_vs_alpha.png` | Cl/Cd vs Alpha — all 10 airfoils |
| `results/Xfoil-direct_design_graphs/cl_vs_cd.png` | Drag polar — all 10 airfoils |
| `results/Xfoil-direct_design_graphs/legend.png` | Airfoil colour legend |

---

## Taper Ratio Selection -VLM2 Inviscid

### Method

Five taper ratios were evaluated using VLM2 Inviscid analysis in XFLR5. All wings used NACA 5412,  the same wingspan of 1m and aspect ratio of around 15, and were analysed at the AoA of 7.5° with zero sweep to isolate the taper effect.

- **Taper ratios tested:** 0.0, 0.2, 0.4, 0.5, 0.6, 0.8 1.0
- **Sweep angle:** 0° 
- **Analysis:** VLM2 Inviscid, Type 1, 10 m/s, 7.5° AoA

### Evaluation Criterion

Spanwise Cl distribution was plotted for each wing. The optimal taper ratio produces a smooth, evenly distributed Cl curve across the span.

### Result

**Selected: λ = 0.5**
- Produced the smoothest spanwise Cl distribution, closest to elliptical

---

## Sweep Angle Selection (VLM2 Inviscid)

### Method

Four sweep angles were evaluated using VLM2 Inviscid analysis, holding taper ratio fixed at λ = 0.5 from Part 2.

- **Sweep angles tested:** 0°, 5°, 10°, 15°
- **Taper ratio:** λ = 0.5 
- **Analysis:** VLM2 Inviscid, Type 1, 10 m/s
- **AoA sweep:** −5° to +° 15in 0.5° increments

### Evaluation Criterion

Pitching moment coefficient Cm was plotted against AoA for each sweep angle. Static pitch stability has a negative slop. 15° produced the steepest slope.

### Result

**Selected: Λ = 15°**
- Produced the most negative dCm/dAoA slope across the tested range

