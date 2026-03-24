

## Xfoil Direct Design Analysis
Overview
This study uses XFLR5 to parametrically justify four key design parameters for a hand-launched glider:
Parameter	Method	Result
Camber	XFoil Direct Analysis — 10 airfoils	NACA 5412
Best AoA	Cl/Cd vs Alpha curve	7.5°
Taper ratio λ	VLM2 spanwise Cl distribution	λ = 0.5
Sweep angle Λ	VLM2 Cm vs Alpha slope	Λ = 15°
# Glider Camber & AoA Study
**Parametric aerodynamic justification of airfoil camber, angle of attack, taper ratio, and sweep angle using XFLR5.**

Completed as part of the LEAD & FLY application at Embry-Riddle Aeronautical University.

---

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

Cl/Cd was plotted against Alpha for all ten airfoils. Peak glide efficiency was closely clustered across NACA 2412–6412, within 1% of each other. NACA 5412 had the higest peak.

**Selected: NACA 5412**
- Peak Cl/Cd = **80** at **7.5° AoA**
- Cl = **1.35** at best glide angle

### Figures

| Figure | Description |
|---|---|
| `results/Xfoil-direct_design_graphs/cl_vs_alpha.png` | Cl vs Alpha — all 10 airfoils |
| `results/Xfoil-direct_design_graphs/clcd_vs_alpha.png` | Cl/Cd vs Alpha — all 10 airfoils |
| `results/Xfoil-direct_design_graphs/cl_vs_cd.png` | Drag polar — all 10 airfoils |
| `results/Xfoil-direct_design_graphs/legend.png` | Airfoil colour legend |

---

## Taper Ratio Selection -VLM2 Inviscid

### Method

Five taper ratios were evaluated using VLM2 Inviscid analysis in XFLR5. All wings used NACA 5412, shared the same wingspan of 1m and an aspect ratio of around 15, and were analysed at the AoA of 7.5° with zero sweep to isolate the taper effect.

- **Taper ratios tested:** 0.0, 0.2, 0.4, 0.5, 0.6, 0.8 1.0
- **Sweep angle:** 0° (held constant)
- **Analysis:** VLM2 Inviscid, Type 1, 10 m/s, 7.5° AoA

### Evaluation Criterion

Spanwise Cl distribution was plotted for each wing. The optimal taper ratio produces a smooth, near-elliptical bell-shaped Cl curve across the span. A flat distribution (rectangular wing) produces higher induced drag; an over-tapered wing risks tip stall.

### Result

**Selected: λ = 0.5**
- Produced the smoothest spanwise Cl distribution, closest to elliptical

---

## Sweep Angle Selection (VLM2 Inviscid)

### Method

Four sweep angles were evaluated using VLM2 Inviscid analysis, holding taper ratio fixed at λ = 0.5 from Part 2.

- **Sweep angles tested:** 0°, 5°, 10°, 15°
- **Taper ratio:** λ = 0.5 (fixed)
- **Analysis:** VLM2 Inviscid, Type 1, 10 m/s

### Evaluation Criterion

Pitching moment coefficient Cm was plotted against AoA for each sweep angle. Static pitch stability requires a **negative slope** (dCm/dAoA < 0) — a disturbance in pitch must produce a restoring moment, not a diverging one.

### Result

**Selected: Λ = 15°**
- Produced the most negative dCm/dAoA slope across the tested range

