# RV-NPU-ASIC

**Decoupled RISC-V Neural Processing Unit — RTL-to-GDSII ASIC Implementation**

An ASIC implementation study of a RISC-V processor integrated with a neural processing unit (NPU), focusing on decoupled CPU–NPU execution, architectural ablation, physical design, and technology scaling.

## Overview

This project explores the integration of neural processing capabilities into a RISC-V processor while allowing the CPU and NPU to execute independently.

The central architectural concept is **decoupled CPU–NPU execution**: the CPU can continue executing scalar instructions while the NPU processes neural workloads, rather than requiring the CPU to remain idle throughout neural computation.

The project covers RTL simulation, logic synthesis, physical design, post-route analysis, architectural ablation, and technology scaling.

## Architecture

The design combines a RISC-V processor with dedicated neural-processing hardware and supporting modules.

<!-- Add the architecture diagram from Architecture/ using its actual filename. -->

For detailed diagrams, see [Architecture](Architecture/README.md).

## Implementation Flow

The design follows an RTL-to-GDSII implementation workflow:

1. **RTL design and simulation** — functional verification of the processor and NPU behavior.
2. **Logic synthesis** — synthesis using Cadence Genus.
3. **Physical design** — floorplanning, power planning, placement, clock-tree synthesis, and routing using Cadence Innovus.
4. **Post-route analysis** — timing, area, power, and routing analysis.
5. **Architectural ablation** — PPA comparison across design variants.
6. **Technology scaling** — comparison of the final D6 design across 45 nm, 90 nm, and 180 nm technologies.

## Final ASIC Implementation

The following values represent the **D6 implementation at 90 nm**, based on the post-route reports.

| Metric | Result |
|---|---:|
| Technology | 90 nm |
| Target Frequency | 100 MHz |
| Clock Period | 10 ns |
| Instance Count | 7,431 |
| Cell Area | 91,730.225 µm² |
| Estimated Total Power | 8.696 mW |
| Setup WNS | +0.107 ns |
| Hold WNS | 0.000 ns |

*Power is tool-estimated under the activity assumptions used in the reports. The timing results are subject to the reported analysis constraints; the hold WNS is at the reported zero-slack boundary.*

See [Physical Design (PnR)](PnR/README.md) for implementation images, detailed results, and the GUI workflow guide.

## Project Contents

| Directory | Description |
|---|---|
| [Architecture](Architecture/README.md) | System architecture and CPU–NPU execution diagrams |
| [Simulation](Simulation/README.md) | RTL simulation, testbench, and waveform results |
| [Synthesis](Synthesis/README.md) | Genus synthesis scripts, timing constraints, and synthesis results |
| [PnR](PnR/README.md) | Innovus physical design, final layout, CTS, and post-route analysis |
| [Ablation Study](Ablation_Study/README.md) | PPA comparison across architectural variants |
| [Technology Scaling](Technology_Scaling/README.md) | D6 implementation comparison across 45 nm, 90 nm, and 180 nm |


## Tools and Technologies

- **HDL:** Verilog
- **Synthesis:** Cadence Genus
- **Physical Design:** Cadence Innovus
- **Verification and Analysis:** RTL simulation, timing analysis, and post-route PPA evaluation
- **Implementation Target:** Standard-cell ASIC flow

## Research Focus

- Decoupled CPU–NPU execution
- RISC-V processor integration with neural-processing hardware
- Architectural ablation and PPA trade-offs
- Post-route timing, area, power, and routing analysis
- Technology scaling across multiple process nodes

## Publication

Still in process of publishing ....

## License

This repository is distributed under the MIT License. See [LICENSE](LICENSE) for details.

*This repository documents an academic hardware design and implementation study. Tool-reported results are implementation estimates and do not represent measurements from fabricated silicon.*
