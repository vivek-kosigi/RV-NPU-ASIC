# 04 — Power Planning in Cadence Innovus

## Objective

Set up the power-distribution connections for the RV-NPU D6 design in Cadence Innovus.

Power planning establishes the VDD and VSS connections needed to supply power and ground to the standard cells during physical implementation.

## 1. Open the Power Planning Interface

After completing floorplanning:

1. Open the power-planning or special-routing interface available in your Innovus version.
2. Locate the controls for defining power nets and creating special routes.
3. Identify the VDD and VSS nets used by the design.

The exact menu names may vary with the Innovus version and design setup.

## 2. Define the Power Nets

Configure the power and ground nets:

| Net | Function |
|---|---|
| `VDD` | Power supply |
| `VSS` | Ground reference |

Ensure that these names match the power and ground nets defined in the design and technology setup.

## 3. Configure Power Rails

In the power-planning interface, configure the relevant routing options for the standard-cell power rails.

Your notes identify the following settings:

- Special routing
- VDD and VSS nets
- Routing layer selection for standard-cell rails

Select the appropriate layer according to the technology LEF and the project's power-planning configuration.

> **Important:** The correct routing layer and rail configuration depend on the technology and standard-cell layout. Use the settings from your actual design rather than assuming a universal layer name.

## 4. Create Special Routes

Apply the configured special-routing operation to establish the power connections.

After routing, inspect the layout to confirm that the power rails or routes have been created as expected.

Check the Innovus messages for errors or warnings related to missing nets, invalid layers, or routing failures.

## 5. Save the Design

Save the design database after completing the power-planning stage.

Your notes indicate using the Innovus design-save interface and an `.enc` database filename.

Use a descriptive name that identifies the stage, for example:

```text
rv_npu_powerplan.enc
```

The exact filename and save options can follow your existing project convention.

## Verification Checklist

Before moving to placement, confirm that:

- VDD and VSS are defined correctly.
- The required power rails or special routes have been created.
- The selected routing layers are valid for the technology.
- No unresolved power-planning errors remain.
- The design database has been saved.

## Expected Outcome

The RV-NPU design has its initial power-distribution connections established and is ready for standard-cell placement.

**Next:** [05 — Standard-Cell Placement](./05_placement.md)
