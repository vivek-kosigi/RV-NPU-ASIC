# 07 — Routing in Cadence Innovus

## Objective

Perform signal routing for the RV-NPU design using the Cadence Innovus GUI.

Routing connects the placed standard cells through the available metal layers while respecting connectivity, design rules, and timing requirements.

## 1. Prepare the Design

Before routing:

1. Confirm that standard-cell placement is complete.
2. Confirm that clock-tree synthesis has completed.
3. Check the Innovus log for unresolved errors.
4. Verify that the required technology and routing-layer information is available.

## 2. Open the Routing Interface

In the Innovus GUI, locate the routing commands under the routing-related menus.

Depending on the Innovus version, the routing operation may be available through the **Route** menu and its NanoRoute options.

Review the available routing operations before proceeding.

## 3. Run Signal Routing

Start the appropriate routing operation for the design.

The routing process may include:

- **Global routing:** Estimates routing paths and resource usage across the design.
- **Detailed routing:** Creates actual wire geometries and vias while following technology design rules.

Use the routing stages and options appropriate to your project setup. Monitor the tool messages while routing runs.

## 4. Inspect Routing Progress

After routing, inspect the layout and review the tool messages.

Check for:

- Routing completion status
- Unconnected signal nets
- Routing violations
- Congestion or routing-resource issues
- Any unresolved errors reported by Innovus

Investigate problems before considering the design ready for post-route analysis.

## 5. Review the Routed Layout

Inspect the routed design in the layout window.

Confirm that the signal-routing geometry is visible and that the routing operation completed as expected.

The final routed layout image in this repository provides a visual reference for the physical implementation.

## 6. Save the Design

Save the design database after routing so that the routed implementation can be restored for subsequent analysis.

Use your project's existing database naming convention. For example:

```text
rv_npu_routed.enc
```

This is an example filename; use the actual filename and save procedure from your flow.

## Expected Outcome

The RV-NPU design has routed signal interconnects and is ready for post-route timing analysis, parasitic extraction, and physical-design checks.

**Next:** [08 — Timing Analysis](./08_timing_analysis.md)
