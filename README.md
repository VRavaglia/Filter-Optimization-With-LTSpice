# Circuit Optimization using Genetic Algorithm and LTSpice

This repository presents Pythons scripts that optimize electronic circuits using Genetic Algorithm (GA) and LTSpice. The scripts call LTSpice in batch mode (via command line interface), which simulates a given circuit schematic. A template circuit schematic diagram is manually created and then modified by the script. 

There are two folders: one with the script used to optimize a MOSFET-c filter; and other containing a documented example on how to integrate LTSpice with Python and optimize a simple comparator with GA. The authors strongly suggest that the reader checks out the tutorial before trying to understand the filter optimization. The follwing filter is optimized in the first folder:

![MOSFET-c Filter](https://i.imgur.com/3VvlUA5.png)

The reader may notice that the filter optimization does not include the LTSpice schematic diagram of the filter. We chose not to disclose this file to avoid possible infringements in non-disclosure agreements that we have with the foundries that gave us the transistor models.

The Python script creates a copy of a template schematic diagram for each run and each generation of the GA. Then the Python script calls LTSpice, which executes a parametric simulation where each parametric point corresponds to a different individual of the GA (*i.e.* each parametric simulation has *mu* points). The Python library *ltspice* (the library has the same name as the circuit simulator) reads the simulations results and converts them to numerical vectors.
