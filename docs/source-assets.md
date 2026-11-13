# Original Source & Screenshot Assets

The main documentation is tracked in this repository. To make the project fully reproducible and presentation-ready, the **original binary files** below must also be uploaded.

## Recommended repository paths

| Source | Target path | Notes |
| --- | --- | --- |
| Original LabVIEW program | `source/Electrical Circuit Monitoring & Protection System.vi` | Original, editable NI LabVIEW VI |
| Original PDF technical report | `report/LabVIEW_Electrical_Circuit_Monitoring_Report.pdf` | Original supplied engineering report |
| Screenshot of full Front Panel | `images/front panel.jpg` | Show the normal operator interface |
| Screenshot of Block Diagram | `images/blok diyagram.jpg` | Show readable calculation and monitoring logic |
| Screenshot of fault condition | `images/monitor and alarms.jpg` | 26 V, current/power errors illuminated |

**Screenshot status:** All three JPEG images have been uploaded and verified in the repository. The VI and report remain separate items; check their folders before claiming they are available.

## How to run the VI (after the file has been uploaded)

1. Install a compatible National Instruments LabVIEW environment (developed with **LabVIEW 2020**).
2. Download and open `source/Electrical Circuit Monitoring & Protection System.vi`.
3. Inspect the Front Panel and Block Diagram (`Ctrl+E` toggles between the two windows).
4. Enter R1–R4 in kΩ and Vin in V; use the operating switch and selection control.
5. Observe computed values and indicators; refer to [verification.md](verification.md) for documented cases.

The VI has not been executed in the repository publishing environment; do not treat the package as deployment-validated.
