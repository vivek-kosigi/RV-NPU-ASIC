# Ablation Study

## Objective

The ablation study evaluates how successive architectural features affect the physical implementation of the RV-NPU design. Multiple design variants were implemented and compared using post-route Power, Performance and Area (PPA) reports.

## Design Variants

| Design | Description |
|---|---|
| D0 | Baseline scalar RISC-V processor |
| D1 | RISC-V with neural instruction support |
| D2 | Addition of SWAR SIMD processing |
| D3 | Addition of persistent accumulation |
| D5 | Integrated RV-NPU design with command-queue logic |
| D6 | Decoupled CPU–NPU execution architecture |

Each variant represents a different architectural configuration, allowing the impact of additional functionality and execution architecture to be evaluated.

## Post-Route PPA Comparison

All values below are from the 90 nm implementation reports.

| Design | Instances | Area (µm²) | Total Power (mW) |
|---|---:|---:|---:|
| D0 | 553 | 9,128.971 | 0.917 |
| D1 | 2,298 | 31,519.587 | 2.739 |
| D2 | 6,105 | 78,721.385 | 7.250 |
| D3 | 6,185 | 80,445.603 | 7.298 |
| D4 | 6,630 | 80,224.000 | 7.491 |
| D5 | 7,431 | 91,730.225 | 8.696 |

## Observations

- Adding neural-processing functionality increases the implementation area and power relative to the baseline processor.
- The successive design variants allow the physical cost of additional processing features to be evaluated.
- D6 has the largest implementation among the listed variants, reflecting its additional decoupled CPU–NPU architecture.
- D6 is the final architecture of interest because it allows the CPU to continue scalar execution while the NPU processes neural workloads independently.

## Implementation Conditions

- **Technology:** 90 nm
- **Supply voltage:** 1.1 V
- **Target frequency:** 100 MHz
- **Implementation stage:** Post-route

*Note: PPA values are tool-reported estimates under the activity assumptions used in the implementation reports. The comparison reflects the reported implementation configurations and should not be interpreted as an isolated measurement of each individual module's cost.*
