# Functional Testing & Evidence

## Test A — Baseline circuit calculation

The supplied report records a Front Panel observation consistent with these inputs:

| Input | Value |
| --- | ---: |
| R1 | 1 kΩ |
| R2 | 2 kΩ |
| R3 | 3 kΩ |
| R4 | 6 kΩ |
| Vin | 10 V |
| Selection | 0 (whole circuit) |

Expected / reported:
- Equivalent resistance = **5 kΩ**
- Main current = **2 mA**
- Parallel branch currents = **1.333 mA** and **0.667 mA**
- Total power = **20 mW**
- Selected voltage = **10 V**

## Test B — Overcurrent and power alarm screenshot

The user supplied a screenshot of the **running Front Panel** with:
- Inputs: R1 = 0.5 kΩ, R2 = 0.5 kΩ, R3 = 1.2 kΩ, R4 = 1.2 kΩ, Vin = 26 V, selection = 0
- Displayed resistance = 1.6 kΩ
- Displayed current = **16.25 mA**
- Displayed total power = **422.5 mW**
- Illuminated **Hata 1** (current) and **Hata 2** (power) indicators
- Visible messages explaining instrument-limit exceedance

This supports **one tested over-limit state**. It does not, by itself, establish the precise switching behavior at *every* boundary or the implementation of later revisions.

## Further verification checklist

- [ ] Check all selection positions (0–4) against independent circuit calculations
- [ ] Check current warning threshold at 13.5 mA and error transition at 15 mA
- [ ] Check displayed-power warning at 315 mW and error transition at 350 mW
- [ ] Check 0–32 V input handling and any timed correction behavior
- [ ] Check OFF-state indicator behavior and input controls
- [ ] Check zero-resistance and other divide-by-zero edge cases
- [ ] Independently check the later 0.25 W per-resistor requirement, if implemented

**Scope:** LabVIEW software simulation; no field data, PLC or physical protective relay tested.
