# Procedure for Reverse Engineering Electric Components
Ben Manning, Purdue University

Last modified: 2025-12-04

## Introduction

Reverse engineering electric components involves analyzing and
understanding the design and functionality of an existing electronic
device or system. This process can be complex and requires a systematic
approach. Below is the general approach that will be followed in ECE
39595. Note that this is a generic procedure and should be adapted as
necessary depending on the device that is being analyzed.

## Preparation and Safety

1.  **Gather Tools and Equipment**: Multimeter, oscilloscope,
    soldering/desoldering tools, magnifying glass, digital camera, SPICE
    software, etc.

2.  **Safety Measures**: Ensure the device is powered off and unplugged.
    Use anti-static measures to protect components.

    **Important!** If the device is something with a large power supply,
    or if you notice that a light stays on for a long time after being
    unplugged, make sure to wait a few minutes to continue. This is
    evidence of large capacitors that can store charge and be dangerous
    if accidentally touched.
    

## Gather Information- DO NOT SKIP!

1.  **Research about the product**:

    -   What is the general function of the device? (Light bulb,
        thermostat) How do these devices generally work?

    -   What should you expect inside? Are there known sub circuits you
        should expect to find? (If the device is plugged into the wall,
        there is likely a rectifier and/or transformers)

    -   Are there specific precautions to take when taking apart the
        device?

## Documentation

1.  **Photograph the Device**: Take detailed photos of the device from
    various angles before and after disassembly.

2.  **Record Model and Serial Numbers**: Document any identifying
    information on the device.

3.  **Take Notes:** Document the mechanical design of the enclosure,
    sensor positions, power connections, and other points about the
    physical design as you see fit.

## Disassembly

1.  **Remove the Enclosure**: Carefully open the device, noting the type
    and placement of screws or clips.

2.  **Label Components**: As you disassemble: label, sort, and document
    each component for easier reassembly. It may be worth taking more
    pictures here to help with documentation and reassembly.

## Visual Inspection

1.  **Identify Components**: Look for recognizable components such as
    resistors, capacitors, ICs, transistors, connectors, etc. Do not
    worry about determining specific component values at this time.

2.  **Inspect PCB**: Note the layout, traces, and any multi-layer
    configurations.

## Component Identification

1.  **Catalog Components**: List all components, including their
    markings and package types.

2.  **Datasheets**: Look up datasheets for ICs and other components to
    understand their specifications and functions.

## Functional Analysis and Circuit Tracing

1.  **Understand Sub-circuits**: Break down the circuit into functional
    blocks (e.g., power supply, signal processing, communication\...).
    Create a block diagram/flow chart of the device. Break sub-circuits
    down further as needed.

2.  **Analyze Functions**: Study how each block contributes to the
    overall operation of the device. This may involve researching and
    simulating different sub-circuits to observe their behavior if you
    are not familiar with them. If you are having trouble finding
    information, make sure to ask a colleague.\
    \
    **For sub-circuits you are more interested in:**

3.  **Trace Connections**: Using a multimeter, trace and document the
    connections between components.

4.  **Create a Schematic(s)**: Begin drafting schematic diagrams based
    on your traced connections.

5.  **Identify known sub-circuits**: As you notice different circuit
    patterns, such as voltage dividers, filters, bridges, and
    amplifiers, document them in notes and schematic draft. It may be
    worth making notes about what their function might be in this
    specific case. Do not spend too much time exploring sub-circuits you
    do not know at this point.

## Verification

1.  **Compare with Known Designs**: Compare your schematic with similar
    existing designs or reference schematics.

2.  **Simulation**: Use simulation tools (SPICE) to simulate the
    circuit's behavior and validate your schematic.

3.  **Replication**: Replicate the process done by the device using a
    microcontroller, timers, or other tools to verify your understanding
    of the device

## Review and Iteration

1.  **Peer Review**: Have your schematic and findings reviewed by other
    colleagues.

2.  **Iterate**: Make any necessary revisions based on feedback and
    further testing.

## Documentation and Reporting

1.  **Finalize Schematic**: Complete a detailed schematic diagram.

2.  **Formalize Your Work**: Document your findings, including the
    function of each component and block, signal analysis, and any
    deviations from expected behavior.

3.  **Photographic Record**: Include annotated photos of the PCB and
    components.

## Optional Steps

1.  **Signal Analysis**:

    1.  **Power Up (if safe)**: If possible, power the device on and use
        an oscilloscope/Multimeter to analyze signals at various points
        in the circuit.

    2.  **Establish a Reference Ground**: Just like every other time we
        measure electric circuits, we need a reference for every
        measurement. In DC, this will likely be the negative terminal of
        a battery or supply. In AC, this can be a ground lead or the
        neutral terminal of an AC source. Keep in mind that if you are
        using the neutral terminal of a source, you will only be
        observing half of the signal!

    3.  **Record Behavior**: Note the behavior and interaction of
        components under different operating conditions.

2.  **PCB Layout Reconstruction**: If needed, reconstruct the PCB layout
    using PCB design software.

3.  **Prototype Building**: Build a prototype based on your schematic to
    further test and validate the design.

This is a generic procedure that provides a structured approach to
reverse engineering electric components, which can be adapted based on
the complexity and specific requirements of the device in question.
