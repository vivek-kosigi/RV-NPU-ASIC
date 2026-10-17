# Technology Scaling

## Objective

Technology scaling evaluates the physical implementation of the final D5 RV-NPU design across 180 nm, 90 nm, and 45 nm technology nodes.

The comparison focuses on post-route cell area and estimated power consumption.

## Post-Route Results

| Parameter | 180 nm | 90 nm | 45 nm |
|---|---:|---:|---:|
| Technology | SCL 180 nm | 90 nm | 45 nm |
| Supply Voltage | 1.98 V | 1.10 V | 1.32 V |
| Instance Count | 5,380 | 7,431 | 6,927 |
| Cell Area (µm²) | 169,447.488 | 91,730.225 | 42,428.546 |
| Total Power (mW) | 25.477 | 8.696 | 5.845 |
| Target Frequency | 100 MHz | 100 MHz | 100 MHz |

## Observations

- **Area:** The 45 nm implementation has the smallest reported cell area.
- **Power:** The 45 nm implementation has the lowest reported power consumption.
- **Scaling trend:** Compared with the 180 nm implementation, the 45 nm implementation reduces cell area by approximately 75% and estimated power by approximately 77%.

## Notes

- Results are from Cadence Innovus post-route reports.
- Power values are tool estimates using the activity assumptions recorded in the reports, not measured silicon power.
- Supply voltages and technology libraries differ across the implementations, so the results reflect the complete implementation conditions rather than technology-node scaling alone.
