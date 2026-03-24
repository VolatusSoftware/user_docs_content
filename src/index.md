# Volatus User Guide

*Volatus: Latin for Flight.*

Volatus is a data acquisition and control software stack with use-cases covering simple CompactDAQ based data acquisition systems, to integrating with external systems, and all the way up to multiple operator distributed rocket engine test stands. Initially developed in LabVIEW, there is already a Python API to enable writing Python scripts that can automate & control a Volatus based system and work has started to create a C++ implementation to overcome a few LabVIEW limitations and provide cleaner integration with other C++ code bases.

To accomplish this, Volatus is a highly configuration driven software stack that enables tight configuration management schemes and rapid iteration around test system changes. Volatus software is configured via VJSON files (files with a .vjson extension) that follow standard JSON formatting.

VJSON files follow a high level standardized organization described in [Configuration: Basics](config/basics.md) while still allowing enough organizational flexibility to not impeded future feature development. A single VJSON file describes an entire Volatus based test system and is shared throughout the entire system. A Volatus system (and its VJSON configuration) is organized into **Nodes**, an application running on a machine such as a CompactRIO, PC, or server. These nodes are then further broken up into **Tasks** which perform the data generation, output, automation, or some combination of all of these. Some examples of tasks are DAQmx Analog Input, Plugin no-code GUIs, event/debug log viewer, etc.

As hinted, Volatus also provides no-code GUI capabilities so that complex process GUIs can be created without needing to implement any logic to get the telemetry data into indicators and commands sent to update system state.

An example of this in use can be seen at Vast's vacuum hotfire test stand:
![Vast's Vacuum Test Stand](img/vast-vacuum-chamber.jpg)
*Source: <a href="https://x.com/vast/status/2003231282998988820" target="_blank">https://x.com/vast/status/2003231282998988820</a>*
