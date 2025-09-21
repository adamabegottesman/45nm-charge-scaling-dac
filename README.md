# 8-bit Split-Array Charge-Scaling DAC in 45 nm CMOS

**Author:** Adam Gottesman • **Coursework:** Full Custom IC Design • **Institution:** Imperial College London

This repo hosts the final PDF describing the design and implementation of an **8-bit split-array charge-scaling DAC** in **45 nm CMOS** with a compact **~60 µm²** layout and verified DRC/LVS. The report covers system targets, topology selection, circuit details (DAC core + rail-to-rail buffer), layout, and simulated performance. :contentReference[oaicite:0]{index=0} :contentReference[oaicite:1]{index=1}

## File
- [`45nm_charge_scaling_DAC.pdf`](45nm_charge_scaling_DAC.pdf) — complete report with specs, design, layout and results. :contentReference[oaicite:2]{index=2}

## Why this topology?
A **split-array charge-scaling DAC** was chosen to cut area and parasitics versus conventional charge-scaling, while meeting tight power/linearity goals for 8-bit resolution. Alternatives (string, R-2R, current-steering) were assessed and rejected based on area, monotonicity/mismatch, or unnecessary complexity for the spec. :contentReference[oaicite:3]{index=3}

## System targets (given)
- 8-bit, ≤ **2.5 µs** per conversion  
- Relative error **< 2 LSB** (INL + DNL)  
- Output **0.1–1.0 V**, load **10 kΩ // 10 pF**  
- Power **< 5 mW**, delay **< 1 µs**, area **< 0.5 mm²**. :contentReference[oaicite:4]{index=4}

## Implementation highlights
- **Split-array DAC** with attenuation capacitor (**Catten = 16/15 of unit-cap sum** split) to emulate full 8-bit array with half the units. :contentReference[oaicite:5]{index=5}  
- **Bias-assisted discharge** to **Vmin** (not GND) to maintain the 0.1 V offset; EN-gated MUX + transmission-gate scheme for deterministic sampling. :contentReference[oaicite:6]{index=6}  
- **Rail-to-rail output buffer** (complementary differential input, Miller-compensated) preserves linearity and range into the load. :contentReference[oaicite:7]{index=7}  
- **Layout:** finalized DAC core; overall footprint around **60 µm²**; digital (S/P) and analog (buffer) blocks separated to reduce coupling; DRC/LVS passed on the DAC section. :contentReference[oaicite:8]{index=8}

## Results (simulation)
- **Linearity:** max **DNL ≈ 1.13 LSB**, max **INL ≈ 1.62 LSB** (within <2 LSB spec). Output range ~**0.105–0.994 V**. :contentReference[oaicite:9]{index=9}  
- **Timing:** propagation delay **≈ 4.3 ns**, settling **≈ 150 ns** (both ≪ 1 µs target). :contentReference[oaicite:10]{index=10}  
- **Power:** **RMS ≈ 0.52 mW** (static ≈ 0.18 mW), within 5 mW budget. :contentReference[oaicite:11]{index=11}  
- **Conclusion:** targets met; compact, power-efficient 8-bit DAC suitable for mixed-signal ICs. :contentReference[oaicite:12]{index=12}

## How to cite
> Gottesman, A. *Design and Implementation of an 8-bit Split-Array Charge-Scaling DAC in 45 nm CMOS Technology*. Imperial College London, 2024. :contentReference[oaicite:13]{index=13}

## Keywords
split-array DAC, charge-scaling, 45 nm CMOS, INL/DNL, rail-to-rail buffer, compact layout, low-power mixed-signal. :contentReference[oaicite:14]{index=14}
