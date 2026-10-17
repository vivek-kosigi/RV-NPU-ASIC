# 05 — Standard-Cell Placement in Cadence Innovus

## Objective

Perform standard-cell placement for the RV-NPU design using the Cadence Innovus GUI.

Placement assigns physical locations to the synthesized standard cells within the floorplanned core while considering timing, congestion, and physical-design constraints.

## 1. Open the Placement Interface

After completing floorplanning and power planning:

1. Open the placement controls in the Innovus GUI.
2. Locate the standard-cell placement options.
3. Review the available placement settings before starting the operation.

The exact menu names and options depend on the Innovus version and project configuration.

## 2. Configure Placement

Review the placement settings required by your flow.

These may include:

- Placement mode and optimization settings
- Timing-driven placement options
- Congestion-related settings
- Placement density or utilization controls

Use the settings selected for your actual RV-NPU implementation. Do not change these parameters without checking their impact on timing and congestion.

## 3. Run Placement

Start the placement operation through the GUI.

Allow Innovus to place the standard cells within the floorplanned core. Monitor the tool messages for errors or warnings.

## 4. Inspect the Placement Result

After placement completes, inspect the layout in the Innovus window.

Check that:

- Standard cells are placed within the core.
- Placement completed without unresolved errors.
- The design remains consistent with the floorplan.
- No obvious placement or congestion problems are visible.

If the tool reports placement violations, investigate them before continuing.

## 5. Review Placement Quality

Review the available placement-stage reports and indicators, where applicable.

Useful checks include:

- Placement status
- Cell utilization
- Congestion estimates
- Timing estimates
- Design-rule or placement violations

These checks help determine whether the design is ready for clock-tree synthesis.

## 6. Save the Design

Save the placement-stage database using your project's naming convention so that the design can be restored or inspected later.

For example:

```text
rv_npu_placement.enc
```

This is an example filename; use the actual naming convention from your flow.

## Expected Outcome

The RV-NPU standard cells are placed within the floorplanned core, providing the physical arrangement needed for clock-tree synthesis.

**Next:** [06 — Clock-Tree Synthesis](./06_clock_tree_synthesis.md)
