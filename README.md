# ADP5071-regulated-breakout-board
# Overview
The ADP5070/5071 are integrated dual rail switching power supplies that can generate outputs of up to -39V - 39V from an input voltage of 2.85V - 15V. As an alternative to low current charge pumps, the ADP5071 is specced to deliver up to 2A on the positive rail and 1.2A on the negative rail (compared to ~50-100mV out of a typical charge pump). This makes it great for use in a system requiring high current dual rail inputs, like high-power op amps or ADCs.

Additionally, the chip has flexibility in what kind of switching architecture is employed. Typically, the chip operates in a boost architecture, and the inverting converter works on the boosted voltage. However, the chip can also employ a modern SEPIC design, where the chip can either boost *OR* buck automatically based on the board configuration. **The current configuration of the board is as a SEPIC converter.** There are two LDOs (one for each rail) at the output to regulate the output as well. _Note that the selected LDOs (LT3094 and LT3042/4) are only specced for 500mA on each regulator_. If you don't require low-noise, but do require high current, I recommend changing these out for higher current LDOs!

You can find the official documentation for the [ADP5071 chip here,]https://www.analog.com/en/products/adp5071.html) for the [LT3094 here,](https://www.analog.com/en/products/lt3094.html) and for [the LT3045 here](https://www.analog.com/en/products/lt3045.html#product-overview). This is a breakout board made in Kicad with a barrel jack power input [(the PJ-037A)](https://www.digikey.com/product-detail/en/cui-inc/PJ-037A/CP-037A-ND/1644545) and [SMA connectors for each output](https://www.amazon.com/gp/product/B00G94UK74/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) (+/- rail for switching supply, and +/- rail for LDOs).

*_Note_*: The board is currently designed for a +/- 6V rail for a 9V battery input, which *only* works in a SEPIC design. 

# Navigating this repo
The main folder contains relevant Kicad files (.pro, .pcb, .sch). The `gerber` directory has a PCB-fabrication ready set of gerber files. The `library` directory contains a custom kicad footprint for the PJ-037A, SMA connector and LPD3015 power inductor.   

# Board images
PCB Layout:
![PCB Layout](https://i.imgur.com/OFgfoFc.png)

Schematic:
![Schematic](https://i.imgur.com/oarrINt.png)
