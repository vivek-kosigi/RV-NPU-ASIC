# 03 — Floorplanning in Cadence Innovus

## Objective

Define the core floorplan for the RV-NPU D6 design in Cadence Innovus before power planning and standard-cell placement.

Floorplanning establishes the initial physical dimensions and layout region in which the design will be implemented.

## 1. Open the Floorplan Tool

After importing the design and completing the timing setup:

1. Open the **Tools** menu in the Innovus GUI.
2. Navigate to **Floorplan**.
3. Select **Specify Floorplan**.

This opens the floorplan configuration interface.

## 2. Specify the Floorplan

Enter the floorplan parameters in the configuration dialog.

Depending on the options available in your Innovus version, these may include:

- Core or die dimensions
- Core utilization
- Aspect ratio
- Core-to-die spacing or margins

Use the values selected for your RV-NPU D6 implementation. The values should be based on the design size and the requirements of the physical-design flow.

> **Note:** The exact numerical settings are not reproduced here because they are not legible in the available notes. Use your original project settings rather than assuming example values.

## 3. Apply the Floorplan

After entering the required parameters:

1. Review the configured values.
2. Click **Apply** in the floorplan dialog.
3. Inspect the resulting floorplan in the Innovus layout window.

Confirm that the floorplan is created and that the design region is visible.

## 4. Inspect the Result

Check the generated floorplan before moving to the next stage.

Verify that:

- The core and die regions are defined.
- The core dimensions are appropriate for the design.
- The layout is visible in the Innovus window.
- No floorplan configuration errors are reported.

If the result is not as expected, review the parameters before proceeding.

## Expected Outcome

The RV-NPU design now has an initial physical floorplan.

This establishes the layout region for subsequent power planning, placement, clock-tree synthesis, and routing.

**Next:** [04 — Power Planning](./04_power_planning.md)
