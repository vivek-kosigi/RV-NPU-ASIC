# 01 — Design Import in Cadence Innovus

## Objective

Launch Cadence Innovus and import the synthesized RV-NPU design along with the required physical-design files.

This is the initial stage of the ASIC physical-design flow. Once the design is imported, the technology libraries, timing corners, and analysis views can be configured before proceeding to floorplanning.

## 1. Launch Innovus

Open a terminal and navigate to your physical-design working directory.

```bash
cd <your_PnR_working_directory>
```

Initialize the Cadence environment and launch Innovus using the setup used in your installation:

```csh
source /home/install/FOUNDRY/digital/90nm/cshrc
innovus
```

> **Note:** The setup-script path above follows the path recorded in the project notes. Installation paths and shell configuration may differ between systems. Use the appropriate setup file for your environment.

Wait for the Innovus GUI to open.

## 2. Open the Design Import Interface

In the Innovus GUI:

1. Open the **File** menu.
2. Select **Import Design**.
3. Use the import interface to specify the design files required by the flow.

The exact dialog layout may vary with the Innovus version.

## 3. Import the Synthesized Netlist

Select the synthesized Verilog netlist generated during the Cadence Genus synthesis stage.

For this project, the design is the RV-NPU D6 implementation.

Example filename:

```text
rv_npu_D6.v
```

The netlist contains the technology-independent or technology-mapped design connectivity produced by synthesis, depending on the selected output stage. For physical implementation, use the synthesized gate-level netlist.

## 4. Add the Timing Constraints

Select the Synopsys Design Constraints (SDC) file used for the design.

Example filename:

```text
rv.sdc
```

The SDC specifies the timing environment, including the clock period, input/output delays, and other timing constraints.

For this project, the target clock period is **10 ns**, corresponding to **100 MHz**.

## 5. Add the Physical Technology Files

Provide the required LEF files for the target technology.

LEF files describe physical information needed by the physical-design tool, such as cell dimensions, pin locations, and routing-layer information.

Depending on the PDK and flow setup, the required files may include:

- Technology LEF
- Standard-cell LEF

Use the LEF files corresponding to the selected 90 nm technology library.

## 6. Check the Imported Design

After importing the design, check the Innovus interface and messages to confirm that:

- The design was loaded successfully.
- The expected top-level design is present.
- The standard-cell instances and hierarchy are available.
- The required constraints and physical technology files were accepted.
- No unresolved missing-file or library errors remain.

Resolve import errors before proceeding to the next stage.

## Expected Outcome

At the end of this stage, Innovus should have the RV-NPU D6 design loaded with its synthesized netlist, timing constraints, and required physical technology information.

The next step is to configure the timing libraries and analysis views through the **MMMC setup**.

**Next:** [02 — Timing Setup](./02_timing_setup.md)
