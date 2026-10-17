# 06 — Clock-Tree Synthesis (CTS) in Cadence Innovus

## Objective

Perform clock-tree synthesis for the RV-NPU design using the Cadence Innovus GUI.

CTS builds the physical clock-distribution network connecting the clock source to the sequential elements of the design. The objective is to manage clock latency and skew while meeting the design's timing requirements.

## 1. Prepare the Design

Before starting CTS:

1. Confirm that standard-cell placement has completed.
2. Check the Innovus log and resolve any outstanding placement errors that prevent CTS.
3. Confirm that the clock is defined correctly in the timing constraints.
4. Verify that the required clock-tree cells and technology information are available.

For this project, the target clock period is **10 ns**, corresponding to **100 MHz**.

## 2. Open the CTS Interface

In the Innovus GUI, locate the clock-tree synthesis controls.

The notes for this project identify the **CCOpt Design** operation as the relevant clock-tree implementation step.

Open the corresponding interface and review the available clock-tree configuration options.

> The exact menu location and dialog labels may vary between Innovus versions.

## 3. Configure the Clock Tree

Review the available configuration options for clock-tree construction.

The project notes identify the following concepts:

- Clock-tree clustering
- Balanced-tree construction
- Balanced fanout

These options relate to distributing the clock to sequential elements while managing the clock network's structure and loading.

Use the configuration selected for the actual RV-NPU implementation. The exact numerical settings and selection values are not specified in the available notes.

## 4. Run Clock-Tree Synthesis

Start the CTS operation through the Innovus GUI.

Allow Innovus to construct the clock-distribution network and perform the configured clock-tree optimization.

Monitor the tool messages and review any reported errors or warnings.

## 5. Inspect the CTS Result

After CTS completes, inspect the clock network in the layout window.

Review the available reports for:

- Clock-tree construction status
- Clock latency
- Clock skew
- Setup timing
- Hold timing
- Clock-related design-rule violations

Confirm that the clock network was created successfully and investigate any unresolved violations before proceeding.

## 6. Save the Design

Save the design database after CTS completes.

Use the project's naming convention to distinguish this stage from the placement and routed databases.

For example:

```text
rv_npu_cts.enc
```

This is an example filename; use the actual filename and save procedure from your flow.

## Expected Outcome

The RV-NPU design has a synthesized clock-distribution network and is ready for the subsequent routing and timing-analysis stages.

**Next:** [07 — Routing](./07_routing.md)
