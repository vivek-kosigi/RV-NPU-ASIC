# Cadence Innovus GUI Guide

This guide documents the GUI-driven physical-design workflow used for the RV-NPU ASIC implementation.

It is based on my project notes and describes the major stages of taking a synthesized design through physical implementation and GDSII export using Cadence Innovus.

## Workflow

| Step | Guide | Description |
|---:|---|---|
| 1 | [Design Import](./01_design_import.md) | Import the synthesized netlist, constraints, and physical technology files |
| 2 | [Timing Setup](./02_timing_setup.md) | Configure timing libraries, RC corners, and MMMC analysis views |
| 3 | [Floorplanning](./03_floorplanning.md) | Define the initial core and die floorplan |
| 4 | [Power Planning](./04_power_planning.md) | Configure VDD/VSS connections and power routing |
| 5 | [Placement](./05_placement.md) | Place standard cells within the floorplanned core |
| 6 | [Clock-Tree Synthesis](./06_clock_tree_synthesis.md) | Build the clock-distribution network |
| 7 | [Routing](./07_routing.md) | Route signal interconnects |
| 8 | [Timing Analysis](./08_timing_analysis.md) | Review post-route timing and violations |
| 9 | [GDSII Export](./09_gds_export.md) | Export the completed physical layout |

## Intended Audience

This guide is intended for students and engineers learning the ASIC physical-design flow through the Cadence Innovus graphical user interface.

Basic familiarity with RTL synthesis, timing constraints, standard-cell libraries, and ASIC implementation is helpful.

## Important Notes

- The guide describes a project-specific workflow, not a universal flow for every technology or Innovus version.
- Menu names, available options, and configuration requirements may vary by installation and PDK.
- Use the libraries, constraints, technology files, and settings appropriate for your own design.
- This is independent educational documentation, not official Cadence documentation.

## Related Project

Return to the [RV-NPU ASIC project](../../README.md) for the architecture, simulation results, synthesis summary, physical-design results, ablation study, and technology-scaling evaluation.
