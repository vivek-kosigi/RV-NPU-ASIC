# 09 — GDSII Export in Cadence Innovus

## Objective

Export the completed RV-NPU physical implementation from Cadence Innovus
to GDSII format.

GDSII represents the final physical layout geometry and is the standard layout
data format used for downstream physical verification and fabrication-related
handoff.

## 1. Check the Final Design

Before exporting the layout, confirm that the intended physical-design stages
have been completed:

- Floorplanning
- Power planning
- Standard-cell placement
- Clock-tree synthesis
- Signal routing
- Post-route timing analysis

Review the Innovus log and relevant reports before generating the final layout
file.

## 2. Open the GDS Export Interface

In the Innovus GUI, open the design export or stream-out interface used for
GDSII generation.

Depending on the Innovus version, the exact menu name and location may vary.

Select the option for exporting or streaming the layout to **GDSII**.

## 3. Configure the GDSII Output

Specify the required output information.

This typically includes:

- Output GDSII filename
- Top-level design
- Layer-map information
- Required technology/library layout data

Use the files and settings associated with the technology used for the
RV-NPU implementation.

> Do not substitute layer-map or technology files from a different process
> technology.

## 4. Generate the GDSII

Run the GDSII export operation.

Monitor the Innovus messages while the layout is being written and check for
errors or warnings related to missing layers, cells, or technology data.

An example output filename could be:

```text
rv_npu.gds
```

## 5. Verify the Export
After the export completes, confirm that:
- The GDSII file was generated successfully.
- The expected top-level design was exported.
- No critical stream-out errors were reported.
- The final layout corresponds to the completed routed design.
