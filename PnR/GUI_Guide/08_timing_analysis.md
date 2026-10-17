# 08 — Post-Route Timing Analysis in Cadence Innovus

## Objective

Review the timing performance of the routed RV-NPU design using Cadence Innovus.

Post-route timing analysis evaluates the design using routed interconnect parasitics, providing a more representative view of timing than pre-route estimates.

## 1. Prepare the Routed Design

Before starting timing analysis:

1. Confirm that routing has completed.
2. Open or restore the routed design database.
3. Verify that the appropriate timing constraints and analysis views are active.
4. Check the Innovus log for unresolved routing errors.

## 2. Extract Parasitics

After routing, extract the interconnect parasitics required for timing analysis.

Parasitic extraction estimates the resistance and capacitance of routed interconnects. These values are used to evaluate wire delay and its effect on path timing.

Use the extraction procedure configured for your project and technology.

## 3. Open the Timing Analysis Interface

In the Innovus GUI, open the timing-related controls or report interface.

Select the appropriate active analysis view and review the available timing reports.

The exact menu names and report options may vary by Innovus version.

## 4. Review Setup Timing

Setup analysis checks whether data reaches its destination sequential element within the required timing window.

Review the available reports for:

- Worst Negative Slack (WNS)
- Total Negative Slack (TNS)
- Critical timing paths
- Setup violations

For this project, the target clock period is **10 ns**, corresponding to **100 MHz**.

## 5. Review Hold Timing

Hold analysis checks whether data remains stable for the required interval after the capturing clock edge.

Review the available reports for:

- Worst Hold Slack (WHS)
- Hold violations
- Paths requiring hold-time correction

Investigate any unresolved hold violations before treating the implementation as timing-clean.

## 6. Review Timing Closure

Inspect the timing reports and determine whether the design satisfies the configured timing requirements.

If violations remain, use the appropriate optimization and timing-closure procedures for your flow, then rerun the relevant analysis.

Do not assume that a positive setup slack alone proves that every timing requirement has been met.

## 7. Record the Results

Record the final values from the appropriate post-route reports.

Useful metrics include:

| Metric | Purpose |
|---|---|
| WNS | Worst setup slack |
| TNS | Aggregate negative setup slack |
| WHS | Worst hold slack |
| Violating paths | Indicates reported timing failures |
| Critical path delay | Helps identify the limiting timing path |

Use the actual post-route values from your Innovus reports. Do not substitute synthesis-stage values for post-route results.

## Expected Outcome

The routed RV-NPU design has been evaluated against its timing constraints, and the post-route timing results are available for the project summary.

**Next:** [09 — GDS Export](./09_gds_export.md)
