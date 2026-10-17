# 02 — Timing Setup and MMMC Configuration

## Objective

Configure the timing analysis environment for the RV-NPU D6 design in Cadence Innovus.

The MMMC (Multi-Mode Multi-Corner) setup defines the timing libraries, operating conditions, RC corners, and analysis views used to evaluate the design under specified conditions.

## 1. Understand the Required Inputs

The timing setup typically uses the following files and information:

| Input | Purpose |
|---|---|
| Liberty (`.lib`) | Defines standard-cell timing, power, and functional characteristics |
| RC corner data | Defines interconnect resistance and capacitance conditions |
| SDC (`.sdc`) | Defines clocks and timing constraints |
| Timing analysis view | Combines the relevant delay corner and constraint mode |

Use files that match the target technology and the configuration used during synthesis.

## 2. Open the MMMC Setup

In the Innovus GUI, open the timing/MMMC configuration interface available in your version.

Locate the controls for configuring:

- Library sets
- RC corners
- Delay corners
- Constraint modes
- Setup and hold analysis views

Menu names and dialog layouts can vary between Innovus versions.

## 3. Configure the Timing Libraries

Specify the standard-cell Liberty files for the selected process corner.

For the RV-NPU implementation, use the appropriate timing libraries associated with the **90 nm standard-cell technology**.

Verify that the library files are accessible and that the tool recognizes the required cells.

## 4. Configure RC Corners

Select the interconnect parasitic corner data required by the project flow.

RC corners describe the resistance and capacitance assumptions used for interconnect delay estimation.

Ensure that the selected RC corner is compatible with the technology and the intended timing analysis.

## 5. Configure the Constraint Mode

Associate the project SDC file with the constraint mode.

The project timing target is:

| Parameter | Value |
|---|---:|
| Clock | `sys_clk` |
| Clock period | 10 ns |
| Target frequency | 100 MHz |
| Clock uncertainty | 0.5 ns |

The SDC also defines input/output delays and reset timing treatment.

## 6. Create Analysis Views

Create the required delay corners and analysis views by associating the library, RC corner, and constraint mode configurations.

Assign the relevant views for setup and hold analysis according to the project's MMMC configuration.

> **Important:** The exact number of corners and views must match the actual flow configuration. Do not create additional corners merely for completeness.

## 7. Validate the Configuration

Before proceeding, check that:

- The required Liberty files are loaded.
- The RC corner references valid technology data.
- The constraint mode includes the intended SDC.
- The analysis views reference valid corners and modes.
- No missing-library or unresolved configuration errors remain.

If available in your Innovus version, inspect the active analysis views and run an initial timing check.

## Expected Outcome

The RV-NPU design has a valid timing-analysis environment for subsequent physical-design stages.

This configuration is used when evaluating timing during placement, clock-tree synthesis, routing, and post-route analysis.

**Next:** [03 — Floorplanning](./03_floorplanning.md)
