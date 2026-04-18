Crude Oil Atmospheric Distillation: Simulation & Energy Optimization
Tool: Aspen HYSYS V14  |  EOS: Peng-Robinson  |  Feedstock: Arabian Light Crude  |  Result: 53.6% Furnace Duty Reduction (−81.3 MW)

Abstract
Steady-state simulation of an atmospheric crude oil distillation unit (CDU) processing Arabian Light crude (API 33.4°, SG 0.858) using Aspen HYSYS V14. Feed was characterized via the HYSYS Oil Manager using a TBP distillation curve, generating 30 pseudo-components. A 35-stage atmospheric column (CDU-100) with full reflux condenser and three liquid side draws was configured and converged. Two pump-around circuits were integrated for internal heat distribution. An energy optimization study — supported by conceptual Pinch Analysis and exergy assessment — achieved a 53.6% furnace duty reduction (5.46 × 10⁸ → 2.54 × 10⁸ kJ/h; −81.3 MW) through feed preheating to 200°C using hot product stream heat recovery.

Simulation Basis
ParameterValueSoftwareAspen HYSYS V14 (aspenONE Engineering Suite)Thermodynamic ModelPeng-Robinson (PR) EOSFeedstockArabian Light Crude OilAPI Gravity33.4°Specific Gravity0.858 (60°F/60°F)Feed Flow Rate662 m³/h (100,000 BPSD)Feed Inlet Condition25°C, 101.3 kPaColumn IdentifierCDU-100Number of Stages35 (theoretical)Condenser TypeFull RefluxCondenser Pressure150 kPaReboiler Pressure170 kPaFeed StageStage 20
Why Peng-Robinson EOS? PR was selected over SRK and RK alternatives for its superior liquid density predictions for heavier hydrocarbons (Zc = 0.307 vs SRK's 0.333) and improved accuracy near the critical region — both critical for modeling the full boiling range of crude fractions from light naphtha to atmospheric residue.

Feed Characterization
Arabian Light crude was characterized using the HYSYS Oil Manager with a True Boiling Point (TBP) distillation curve on a liquid volume basis:
Cumulative Volume (%)TBP Temperature (°C)01810982017530248403165038260445705108057290638100720
The Oil Manager generated 30 pseudo-components (NBP[0]99 through NBP[0]682), with mole fractions decreasing monotonically from 0.0384 (lightest) to 0.0158 (heaviest). Total mole fractions summed to 1.0000, confirming a valid and complete feed characterization.

Column Configuration & Products
Three liquid side draws were configured alongside overhead gas and bottoms:
Product StreamDraw StageTarget TBP RangeConverged Flow (kgmole/h)Overhead Gas—Light ends / LPG1,133NaphthaStage 535 – 180°C154.0KeroseneStage 12180 – 240°C88.0Diesel / AGOStage 20240 – 370°C130.0Atmospheric Residue—>370°C841.6
Converged stream conditions (optimized simulation):
StreamTemp (°C)Pressure (kPa)Mass Flow (kg/h)Liq. Vol. (m³/h)Furnace_Out (Feed)200.0101.3567,000662.2Overhead_Gas158.4150.0115,100157.3Naphtha208.9152.426,36033.35Kerosene225.6156.516,62020.77Diesel / AGO242.9161.237,49043.39Atm_Residue410.3170.0371,400407.4
Column converged using the HYSYS inside-out algorithm. Product boiling ranges are broadly consistent with commercial ASTM D86 specifications.

Pump-Around Circuit Design
Two pump-around circuits were integrated to reduce overhead condenser duty and make heat available at useful temperature levels for crude preheating:
ParameterPA_NaphthaPA_KeroseneDraw Stage411Return Stage29Flow Rate200 kgmole/h150 kgmole/hTemperature Drop (ΔT)30°C30°CDraw Temperature~205°C~226°C
Heat extracted by each pump-around is recovered for crude preheating, directly contributing to furnace duty reduction.

Energy Optimization
Strategy
Cold crude (25°C) is preheated using hot product streams before entering the fired furnace, reducing the furnace temperature rise and duty. Hot streams were prioritized by exergy quality (Carnot factor) for optimal sequencing:
Hot StreamSupply Temp (°C)Carnot Factor (1 − T₀/T)PriorityAtmospheric Residue4100.563Highest — first exchanger in trainDiesel / AGO2430.422HighPA_Kerosene Draw2260.403HighNaphtha2090.381ModerateOverhead Gas1580.308Lowest
A conceptual Pinch Analysis (ΔT_min = 20°C) confirmed the maximum achievable preheat temperature of ~200–220°C, consistent with the optimized feed temperature of 200°C applied in this study.
Results
ParameterBaselineOptimizedChangeFeed Temp at Furnace Inlet25°C25°C—Furnace Outlet Temperature360°C200°C−160°CTemperature Rise in Furnace335°C175°C−160°CFurnace Duty5.46 × 10⁸ kJ/h2.54 × 10⁸ kJ/h−2.93 × 10⁸ kJ/h Equivalent Thermal Power Saved151.8 MW70.6 MW−81.3 MWDuty Reduction——53.6%

The 160°C of feed preheating required is entirely recoverable from hot product streams within the unit — no external utility input required. Full column convergence was maintained under optimized conditions.


Future Work
The current configuration achieves 53.6% furnace duty reduction using a conceptual heat integration strategy. The following phases are scoped for future development:

Rigorous HEN Design — Full Heat Exchanger Network design in Aspen Energy Analyzer (AEA), followed by individual exchanger sizing in Aspen EDR (shell-and-tube, crude service fouling factors). Target: 68% furnace duty reduction.
Economic Analysis — At 81.3 MW thermal saving, assuming fired heater efficiency of 85% and fuel gas price ~USD 5.50/GJ, estimated annual saving is USD 14–18 million for a 100,000 BPD unit.
Dynamic Simulation — Extend to HYSYS Dynamics to evaluate transient response to feed composition changes, throughput upsets, and control scheme design (pressure, side draw flow, furnace outlet temperature loops).
Side Stripper Integration — Steam-stripped side strippers for Naphtha, Kerosene, and Diesel to improve cut sharpness and reduce ASTM D86 overlap.
Sulfur Distribution Modeling — Extend component list to include organosulfur compounds (thiophenes, benzothiophenes) for quantitative sulfur partitioning across all cuts, providing design basis for downstream hydrotreating units.


References

Peng & Robinson (1976) — PR EOS, Industrial & Engineering Chemistry Fundamentals, 15(1), 59–64
Soave (1972) — SRK EOS, Chemical Engineering Science, 27(6), 1197–1203
Linnhoff & Hindmarsh (1983) — Pinch Design Method, Chemical Engineering Science, 38(5), 745–763
Gary, Handwerk & Kaiser — Petroleum Refining: Technology and Economics, 5th ed., CRC Press, 2007
Fahim, Al-Sahhaf & Elkilani — Fundamentals of Petroleum Refining, Elsevier, 2010
Dincer & Rosen — Exergy: Energy, Environment and Sustainable Development, 2nd ed., Elsevier, 2013
Saudi Aramco — Arabian Light Crude Oil Assay, Technical Reference Data, 2020
Aspen Technology Inc. — Aspen HYSYS V14 Operations Guide, 2023


Author
Shahriar Hossain Suny
Department of Chemical Engineering
Jashore University of Science and Technology (JUST), Bangladesh
AIChE Member ID: 009905932744
LinkedIn · GitHub
