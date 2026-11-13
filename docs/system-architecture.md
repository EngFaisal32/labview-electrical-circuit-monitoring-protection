# System Architecture & Electrical Model

## Application flow
1. The operator enters R1–R4 (kΩ) and supply voltage Vin (V) on the LabVIEW Front Panel.
2. An ON/OFF control sets the simulated operating state.
3. While the VI runs, a While Loop updates circuit calculations and display values.
4. A Formula Node computes equivalent resistance, currents, voltages and powers.
5. The selected measurement (0 = whole circuit, 1–4 = resistor) is displayed.
6. Monitoring logic evaluates conditions and updates gauges, status text and warning/error indicators.

## Modeled circuit
R1 and R2 are in series with the parallel pair R3 and R4:

```text
      +--- R1 --- R2 ---+--- R3 ---+
      |                |          |
     Vin               +--- R4 ---+
      |                           |
      +---------------------------+
```

`R_eq = R1 + R2 + (R3 * R4)/(R3 + R4)`

Using resistance in **kΩ**, voltage in **V**, current is naturally obtained in **mA**:

`I_main (mA) = Vin (V) / R_eq (kΩ)`

`I_R3 = I_main * R4/(R3 + R4)`

`I_R4 = I_main * R3/(R3 + R4)`

`P_total (mW) = Vin (V) * I_main (mA)`

`P_resistor (mW) = V_resistor (V) * I_resistor (mA)`

The **0 selection** reports the whole circuit; **1–4** select individual resistors.

## Notes on safety & assumptions
- This is *calculated* behavior in a software model, not a direct voltage/current measurement.
- The report warns that zero-denominator cases need special handling; behavior at zero resistance is not verified.
- These equations and units come from the supplied project report.
- No physical PLC or DAQ hardware was integrated.
