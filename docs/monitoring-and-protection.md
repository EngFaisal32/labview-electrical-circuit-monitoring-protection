# Monitoring, Limits & Alarm Logic

The LabVIEW Front Panel presents values and fault indicators intended to alert the operator to abnormal calculated current or power.

| Calculated quantity | Warning threshold | Error threshold or limit | Source / confidence |
| --- | ---: | ---: | --- |
| Current | >13.5 mA (90% of 15 mA) | >15 mA, **Hata 1** | Documented; 26 V error state observed |
| Displayed power | >315 mW (90% of 350 mW) | >350 mW, **Hata 2** | Documented; 26 V error state observed |
| Input voltage | Outside permitted 0–32 V input interval | Report describes a warning and correction down to 32 V above maximum | Described in report, not independently verified |

### Confirmed example of alarm indication

Using `R1 = 0.5 kΩ`, `R2 = 0.5 kΩ`, `R3 = 1.2 kΩ`, `R4 = 1.2 kΩ`, `Vin = 26 V`, selection `0`:

- Equivalent resistance: **1.6 kΩ**
- Current: **16.25 mA** (greater than 15 mA)
- Power: **422.5 mW** (greater than 350 mW)
- The user-supplied Front Panel screenshot shows **Hata 1** and **Hata 2** illuminated, with related messages.

The ON/OFF and selection controls are visible in the interface. Complete input-boundary and OFF-state tests are not independently evidenced.

### Separate 0.25 W requirement — not verified
A later academic assignment revision called for a **0.25 W (250 mW) rating per resistor**, with a **225 mW** warning level (90%). This is distinct from the **350 mW displayed-power gauge limit**. The provided report does **not** establish that the per-resistor revision was implemented and fully tested in the final VI.

Do not conflate a *software alarm* with certified physical circuit protection.
