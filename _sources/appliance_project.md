# Project 1
**Reverse Engineering a Household Appliance**

Ben Manning, Purdue University

Last Modified: 2025-12-04


## Introduction

In this course so far, you have reverse engineered an LED light bulb and
a general-use thermostat. By this point, you have hopefully realized
that a lot of the things that we use on a daily basis (and often take
for granted) are not *that* complicated. Take a power regulating system,
combine it with some sensors and lights, and you can make pretty much
every general appliance out there. This next project should help confirm
this notion with you, and give some freedom to explore different
appliances that you might find interesting, and then share it with the
rest of the class.

## The Project

Your task for this project is to reverse engineer and document a common
household appliance, preferably an appliance that you use fairly
regularly. There are some limitations on what you can select, but the
general rule is that the appliance cannot have a screen or digital
buttons. This will ideally prevent you from having to dive into digital
signals thus far, and focus on the different analog approaches to make
our lives easier.

Some appliances you may be interested in exploring can include, but are
not limited to:
||||
|---|---|---|
|Electric Kettle   |      Electric Fan        |         Toaster |
| Hair Dryer        |      Electric Iron       |         Blender |
|  Electric Space Heater |  Electric Coffee Maker  |      Slow Cooker |
|  Electric Mixer    |      Dimming lamp         |        Touch Lamp |
|  Electric Griddle   |     Power Drill (wall powered) |   Rice Cooker |


If there is something else that you would like to explore for this
project, please discuss with the instructor first. The appliance should
have the below functions:

-   Powered by being plugged into the wall (no batteries yet)

-   Should have buttons/slides/switches to adjust states other than a
    power button (heat level, motor speed, etc\...)

-   Should not have a screen or digital buttons. If the buttons 'click,'
    you should be fine.

## General Logistics

You are expected to work independently\*, but are welcome to ask for
guidance from your instructor and other students.

\*Name-brand appliances are also not necessary, however; you may pair
with a partner to reverse engineer a generic appliance versus a
name-brand appliance to observe potential differences and cost-cutting
measures. Example, a Great Value coffee maker versus a Mr. Coffee coffee
maker.

You are **not** encouraged to go and purchase a new appliance to take
apart. Instead, wander around your local thrift store, a rummage sale,
or anywhere else you may be able to find an appliance for cheap. It is
not recommended to spend more than \$20 on this project. That said,
depending on the appliance, you may be able to get a new one for under
\$20, which means you should be able to find one used for significantly
cheaper.

# Deliverables 

There will be two main deliverables for this project that will focus on
two forms of technical communication: a technical report in the form of
a data sheet and a technical presentation.

## Datasheet (7.5% of final grade) 
This document should read as if you are reading a datasheet of an IC or
other technical manual of an appliance or component. This document
should be 3-5 pages (single spaced, 12pt font) and have the below
information:

1.  Summary/general overview. This should include what the appliance is
    and its general use case.

2.  Pictures of critical parts of the appliance, both electrical and
    mechanical.

3.  List of mechanical components and their purpose in the device.

4.  List of electrical components with a description of the component
    and their purpose in the device. Links to datasheets for sensors and
    chips should be included.

5.  Reverse Engineered Schematic with breakouts and descriptions for
    sub-circuits. There should also be discussion about the sensors used
    in the system and how they impact the system.

This document should primarily be comprised of full sentences, tables,
and charts, and should be able to be read by someone with limited
electronics experience.

## Technical Presentation (10% of final grade) 

You are also tasked with presenting your project to the other students
in ECE39595, and answer questions regarding your reverse engineering
process and product. Your presentation should be between 5 and 10
minutes with time for questions in that time. You will get cut off if
your presentation extends beyond 13 minutes. You should also generate a
4-10 slide presentation as a visual guide for the presentation. You are
also expected to ask meaningful questions during other students'
presentations. Below are some expected talking points:

-   Summary/general overview. This should include what the appliance is
    and its general use case.

-   Pictures and discussion of critical parts of the appliance, both
    electrical and mechanical.

-   Reverse Engineered Schematic with breakouts and discussions for
    sub-circuits. There should also be discussion about the sensors used
    in the system and how they impact the system.

This presentation should not be a regurgitation of the technical report,
but instead highlighting the really important parts of the report.
Images, tables, and schematics will likely be similar if not identical,
but the way you discuss the information should be more personable.

## About the Deliverables

Taking a look at the rubrics below will show that the content asked for
in each deliverable is very similar, which is true. In fact, the first
five categories of the rubrics are nearly identical except for the grade
weights. The main difference between the deliverables will be how the
content is presented. The datasheet should focus on the in-depth
technical information, whereas the presentation should be more of an
overview of the technical data with room for discussion and questions.
While the formatting of the datasheet will likely look fairly similar
between student submissions, the presentations can, and should be unique
to the presenter, their preferred presenting style, and should allow for
the presenter's enthusiasm to be present and engaging.

# Rubrics

## Report Rubric

 | **Category** | **Exceeds Expectations**| **Meets Expectations** | **Approaching Expectations** | **Not Meeting Expectations**|
|:---|:---|:---|:---|:---|
|**Introduction<br>(10 pts)**|Provides an in-depth, engaging overview of the appliance, its significance, and objectives, demonstrating exceptional clarity.|   Clearly describes the appliance, provides context, states objective, and defines scope.| Missing one or two elements, or descriptions are vague.| Lacks description, context, objective, or scope.|
|**Methodology<br>(20 pts)** | Exceptionally detailed and well-justified methodology, including advanced considerations.| Detailed explanation, lists tools, step-by-step procedures, and justifies each step. |Some steps are unclear or missing, minimal |   No clear methodology, missing key steps.|
| **Analysis & Findings<br>(30 pts)**|Provides an outstanding analysis with deep insights, comprehensive diagrams, and professional presentation.| Identifies components accurately, includes diagrams/photos, detailed circuit analysis, explains functionality, and addresses challenges.|   Some missing components or unclear explanations, diagrams lack clarity, minimal discussion of challenges.|   No significant findings, missing diagrams, or little analysis.|
|**Schematics & Diagrams<br>(15 pts)**|      Exceptional, highly detailed schematics with professional clarity and layout.| Clear, labeled schematics supporting analysis. |  Some labeling errors or diagrams are unclear.|  Poorly labeled or missing schematics.|
|**Discussion<br>(15 pts)** |  Provides deep insights and innovative suggestions with thorough comparisons and applications.| Interprets results, compares expected vs. actual functionality, suggests improvements and applications.| Lacks depth in comparison, minimal improvement suggestions. | No clear interpretation, lacks comparisons or insights.|
|**Conclusion<br>(5 pts)** | Summarizes findings with exceptional clarity and depth, providing forward-thinking reflections.| Summarizes key findings and reflections.| Brief summary with minimal reflection.| No meaningful summary.|
 | **Presentation & Formatting<br>(5 pts)**|   Exceptionally well-structured, polished, and highly professional writing.|Well-organized, free of grammar/spelling errors, professional writing. |    Some organization/grammar issues, but still understandable. | Poorly structured, many errors.|
  |**References & Citations<br>(5 pts)**| High-quality sources, consistent format (IEEE, APA).|      Some citation errors or weak |No citations or improper formatting.|
:::

## presentation Rubric

 | **Category** | **Exceeds Expectations**| **Meets Expectations** | **Approaching Expectations** | **Not Meeting Expectations**|
|:---|:---|:---|:---|:---|
|**Introduction<br>(5 pts)**|Provides a compelling and well-contextualized introduction, engaging the audience. | Briefly discusses the appliance, its use, and selection reasoning.|  Missing one element or lacks depth.| No introduction or vague explanation.|
| **Methodology<br>(10 pts)** | Demonstrates an advanced understanding with highly detailed reverse engineering methods.| Explains reverse engineering approach, steps taken, and errors encountered. | Some missing details or unclear steps. | No clear methodology or missing major steps.|
|**Analysis & Findings<br>(10 pts)**| Presents findings in an exceptionally clear, insightful, and well-organized manner. | Identifies components, organizes discussion, provides insights, and discusses challenges.| Some missing insights, vague organization. |  No clear findings, lacks discussion.|
|**Schematics & Diagrams<br>(10 pts)**|Exceptionally well-labeled and structured diagrams, with innovative visualization techniques. | Clear, well-labeled diagrams with appropriate breakdown for readability.|  Some labeling issues or unclear schematics.| Poorly presented, missing schematics.|
|**Discussion<br>(25 pts)**| Provides advanced insights, innovative comparisons, and actionable recommendations. | Interprets results, compares expected vs. actual, suggests improvements, and considers applications.  | Lacks depth or some missing elements.| No meaningful discussion or comparison.|
|**Presentation<br>(25 pts)** | Exceptionally engaging, well-structured, confident, and professionally delivered. | Engaging, confident, well-structured slides, speaks clearly, answers questions professionally.| Some hesitation, minor slide issues, difficulty answering questions.|Poor organization, lacks confidence, difficult to follow.|
|**Asks Effective Questions (15 pts)**|   Asks insightful, thought-provoking questions that drive deeper discussions. | Asks 3 high-quality questions that further discussion.  | Asks some questions, but they lack depth. |  No meaningful questions or asks surface-level ones.|
