# Lab1-LED Lightbulb
**ECE39595: Reverse Engineering an LED Light Bulb**

Ben Manning, Purdue University

Last Modified: 2025-12-04



## Introduction

Welcome to ECE39595! In this lab, we will be looking at a variety of
commercial devices to see how they work, why manufacturers made the
design decisions they did, and how we can potentially improve the
devices.\
\
We are going to be starting with a device that is literally all around
us, the LED light bulb. As the world moves more into semiconductor
technology, incorporating LEDs instead of incandescent, florescent, or
halogen lights allow for a variety of advantages for our every-day
lighting, but it also comes with some drawbacks that are definitely
worth discussing.\
\
This first lab will be a general guide for how students will be expected
to perform future reverse engineering labs in this course. The actual
reverse engineering process will follow the corresponding guide for the
lab, but students will also be expected to provide some initial research
and reflection before and after the reverse engineering.

## What do you know already?

One of the great things about modern appliances and commercial products
is that the vast majority of the circuits can be understood with
fundamental electronics knowledge. Since we are starting with LED light
bulbs, let's think about the theory and knowledge that we may know, or
can quickly look up with an internet search. (Document these questions
in your lab journal, and answer/provide
equations/simulations/explanations where necessary)

1.  Since they are "Light-Emitting-Diode light Bulbs,\" we can probably
    assume that LEDs are involved. What is the fundamental purpose of a
    diode? Does this differ for an LED?

2.  What is unique about an LED compared to a standard diode?

3.  When using a diode in a circuit, what are the main limitations of
    diodes we must keep in mind? How do we monitor/regulate these
    limitations?

4.  LED light bulbs are directly connected to AC power coming from a
    wall outlet; what type of circuit will likely be inside of the bulb
    in order to use as much power from the source as possible? Draw a
    quick schematic and label components as necessary. Why is this
    circuit necessary?

5.  Do some quick research on other commercial limitations on LED light
    bulbs. What checks or devices can be used to mitigate these
    limitations? The following keywords might be helpful:\
    "Frequency\"\
    "Heat\"

## Preparation and Safety

1.  **Gather Tools and Equipment**:

    -   **Basic Tools:** Screwdrivers (flat and Phillips), pliers, wire
        cutters, tweezers, and a multimeter.

    -   **Cutting Tools:** utility knife, safety glasses, and
        cut-resistant gloves.

    -   **Documentation Tools:** Camera for documenting each step,
        notebook for sketches and notes.

2.  **Power Off:** Ensure the LED bulb is unplugged and has been off for
    some time to avoid any risk of electric shock or burns.

3.  **Protective Gear:** Wear safety goggles and gloves to protect
    against broken glass and sharp components.

## During Reverse Engineering: Steps and Considerations

### Documentation and Initial Inspection

1.  **Photograph the Device**: Take detailed photos of the device from
    various angles before and after disassembly.

2.  **Record Model and Serial Numbers**: Document any identifying
    information on the device.

3.  **Take Notes**: Document the mechanical design of the enclosure,
    sensor positions, power connections, and other points about the
    physical design as you see fit.

### Disassembly

-   **Open the Casing:** Carefully open the bulb casing. It might be
    screwed, glued, or snapped together. Be gentle to avoid damaging
    internal components.

-   **Label Components**: As you disassemble: label, sort, and document
    each component for easier reassembly. It may be worth taking more
    pictures here to help with documentation and reassembly.

-   **Document Each Step:** Take photos and make notes at each stage of
    disassembly. This documentation will help in understanding how parts
    are interconnected.

#### Specific for this Lab:

##### Removing the main housing and PCB (Printed Circuit Board)

The light bulb that we are taking apart has a plastic bulb and housing
that are glued in place with silicone caulk.\
\
**With cut-resistant gloves on,** use a utility blade to loosen the seam
between the bulb and housing. Once the blade can be moved around the
bulb with slight bending of the bulb, firmly pry the bulb from the
housing by holding the bulb in one hand and the housing in the other and
firmly twisting and flexing the two parts. This will expose the printed
circuit board.\
\
The PCB is attached to the base using more caulk. Carefully run a
utility blade around the PCB to loosen caulk. Use a small flat-head
screwdriver or spreader, or jimmy tool to remove the PCB from the
housing. **DO NOT PULL THE PCB FROM THE HOUSING YET!**\
\
The PCB is attached to the live and neutral connections on the bottom of
the housing. Carefully cut the two wires connecting the PBC to the
housing to remove the PCB.

### Component Identification

-   **Chips:** Identify the type and arrangement of LED chips. Note the
    number of chips and their configuration.

    ::: itemize
    **Note:** The chip found in these bulbs does not have a public
    datasheet. There are general links around and some videos that work
    to explain what the chip is doing. There is also a datasheet for
    *part* of the chip that conveniently discusses the other part as an
    external part. Keep this in mind when exploring the chip.
    :::

-   **Heat Sink:** Examine the heat sink. LEDs produce heat, and
    efficient heat dissipation is crucial for longevity.

-   **Diffuser:** Note the presence and type of diffuser, which helps in
    spreading light evenly.

### Circuit Analysis

-   **Trace the Circuit:** Using the multimeter, trace the circuit
    paths. Identify connections between the driver, LEDs, and any other
    components.

-   **Component Values:** Record values of resistors, capacitors, and
    any other discrete components. This information is crucial for
    understanding the electrical design.

-   **Schematic Diagram:** Create a schematic diagram of the circuit.
    This visual representation will aid in comprehending the overall
    design.

-   **Understand Sub-circuits**: Break down the circuit into functional
    blocks (e.g., power supply, signal processing, communication).

-   **Analyze Functions**: Study how each block contributes to the
    overall operation of the device.

-   **Compare with Known Designs**: Compare your schematic with similar
    existing designs or reference schematics.

-   **Simulation**: Use simulation tools (SPICE) to simulate the
    circuit's behavior and validate your schematic.

### Reflection and Analysis

-   **Design Insights:** Consider the design choices made by the
    manufacturer. Reflect on the efficiency, durability, and
    cost-effectiveness of the design.

-   **Improvements:** Think about potential improvements or alternative
    designs that could enhance performance or reduce cost.

## Documentation and Reporting

1.  **Finalize Schematic**: Complete a detailed schematic diagram.

2.  **Formalize Your Work**: Document your findings, including the
    function of each component and block, signal analysis, and any
    deviations from expected behavior.

3.  **Photographic Record**: Include annotated photos of the PCB and
    components.

## Review and Iteration

1.  **Peer Review**: Have your schematic and findings reviewed by at
    least one other colleague.

2.  **Iterate**: Make any necessary revisions based on feedback and
    further testing. (Go back to the "Reflection and Analysis\" and
    "Documentation and Reporting\" sections as necessary.)
