# Electrical Circuit Monitoring & Protection System Using LabVIEW

**Electrical Engineering · Automation & Instrumentation · LabVIEW 2020**

Academic engineering project focused on **continuous circuit monitoring, threshold-based fault detection, alarm indications and operator-interface design**. This is a **software-based DC circuit simulation**, not a PLC-connected or live-data-acquisition system.

## Project overview

**Figure 1 — LabVIEW Front Panel (idle state).** Operator interface showing resistance and voltage inputs, measurement gauges, circuit selection, and system status with the application switched off. The original screenshot will appear below after `images/front%20panel.jpg` is uploaded.

![Figure 1 — LabVIEW Front Panel idle state](images/front%20panel.jpg)


The application models a four-resistor DC circuit consisting of R1 and R2 in series with a parallel network (R3 || R4). An interactive LabVIEW Front Panel accepts a supply voltage and four resistor values, calculates the electrical quantities, and shows measurements, status and warning/error indicators while the program is running.

**Automation-relevant features**
- Continuous parameter evaluation in a LabVIEW **While Loop**
- Electrical calculations via **Formula Node**
- User-set resistance and DC voltage values
- Computed equivalent resistance, main/branch currents, voltage and dissipated power
- Individual-resistor or full-circuit measurement selection (0–4)
- Operating ON/OFF control and status feedback
- Current and power warning/error indicators based on predefined limits
- Input-voltage limit handling described in the project report

## Graphical programming & monitoring logic

**Figure 2 — LabVIEW Block Diagram, Formula Node excerpt.** The graphical programming view shows circuit inputs, equations, selected measurements and warning/error outputs. It is a *close-up of the Formula Node* rather than a screenshot of the entire Block Diagram.

![Figure 2 — LabVIEW Formula Node in Block Diagram](images/blok%20diyagram.jpg)

## Example: monitored fault condition

With **R1 = 0.5 kΩ, R2 = 0.5 kΩ, R3 = 1.2 kΩ, R4 = 1.2 kΩ and Vin = 26 V**, the Front Panel screenshot records:

| Measurement | Observed value |
| --- | ---: |
| Equivalent resistance | 1.6 kΩ |
| Total current | 16.25 mA |
| Current in each parallel branch | 8.125 mA |
| Total power | 422.5 mW |

Both **Hata 1 (overcurrent)** and **Hata 2 (excessive displayed power)** were visibly active. These demonstrate calculation and fault indication for this tested condition, not comprehensive verification of every protection case.

**Figure 3 — Monitoring & Fault Detection.** Actual Front Panel screenshot at 26 V: 16.25 mA and 422.5 mW with two red error indicators and relevant operator messages.

![Figure 3 — Current and power alarms triggered at 26 V](images/monitor%20and%20alarms.jpg)

## Engineering relevance

This exercise develops principles transferable to **PLC / HMI / industrial automation**: input handling, cyclic monitoring, threshold evaluation, operating-state logic, alarm messages, and displaying process information. **No physical PLC, actual instrumentation, industrial network or hardware protection device was used.**

## Documentation

- [System architecture & circuit equations](docs/system-architecture.md)
- [Monitoring thresholds & limits](docs/monitoring-and-protection.md)
- [Functional tests & validation status](docs/verification.md)
- [Screenshot captions & portfolio notes](docs/portfolio-presentation.md)
- [Source files & supporting assets checklist](docs/source-assets.md)

## Technology

- NI LabVIEW 2020
- Graphical **Front Panel** and **Block Diagram**
- **While Loop**, **Formula Node**, conditional/alarm logic
- DC series/parallel circuit analysis

## Source and supporting files

The original [LabVIEW VI](source/Electrical%20Circuit%20Monitoring%20%26%20Protection%20System.vi), [PDF engineering report](report/LabVIEW_Electrical_Circuit_Monitoring_Report.pdf), and all three authentic screenshots are uploaded to this repository. See [source assets](docs/source-assets.md) for the filenames and usage notes.

## Validation scope

A known numerical example and a visible over-limit Front Panel state have been documented. The entire alarm, timing, voltage correction, start/stop and later per-resistor 0.25 W revision have **not** been independently tested. The detailed project report lists those requirements and the recommended verification cases.

## Portfolio

[This project's Notion portfolio page](https://guttural-galliform-d52.notion.site/Electrical-Circuit-Monitoring-Protection-System-417920417b9d80489ab3f41235d920e9)

[Engineering portfolio homepage](https://guttural-galliform-d52.notion.site/Engineering-Portfolio-414920417b9d8034a902d6caa11becf1)

*Academic software simulation; for educational demonstration only. Not a certified electrical protection system.*
