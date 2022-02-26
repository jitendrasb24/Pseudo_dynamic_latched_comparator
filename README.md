# Pseudo_dynamic_latched_comparator
This repository presents the design of Pseudo dynamic latched comparator implemented using Synopsis Custom Compiler on 28nm CMOS Technology.

## ABSTRACT
A 28 NM CMOS Pseudo Dynamic Latched Comparator is proposed designed and Implemented using Synopsys Software. The comparator is a key building block for applications where digital information needs to be recovered from analog signals, such as analog-to-digital (A/D) converters, I/O data receivers, memory bit line detectors, etc. The trend of achieving both higher speed and lower power consumption in these applications makes dynamic latch comparators very attractive. We can verify the output using Circuit Waveforms. This complete design and implementation are done using VLSI technology which has features such as high speed, low power, low cost and small size.

## TOOLS USED
* **Synopsys Custom Compiler**
* **Synopsys Primewave**
* **Synopsys 28nm PDK**

## REFERENCE CIRCUIT DETAILS
The proposed preamplifier consists of transistors M0 to M4.
Since the input differential pair uses NMOS transistors M0 and
M1, while the load transistor uses PMOS transistors M2 and
M3, the gain of this preamplifier easily reaches an acceptable
value with small size of input differential pair. The Latch is the
most sensitive part in the comparator design. It consists of two
inverters connected back-to-back with each other forming a
differential comparator and an NMOS transistor are connected
between the two differential nodes of the latch. The schematic
of latch consists of transistors M5 to M13 which includes
cross coupled inverter pair M5-M6 and M7-M8 and the charge
imbalance circuitry M9-M11. Transistors M5-M8 forms the
main regenerative loop for the latch. For least capacitive
effects, width and lengths of transistors M5-M8 are kept
minimum and W/L ratio is kept as for an ideal inverter.
Sizes are further optimized to set the meta-stable trip point
of the inverter to half of the supply voltage. The switching
transistor M11 short circuits the latch’s differential nodes to
a common DC level. An ad-vantage of increasing its width is
that it brings the DC level on both nodes close to each other.
Transistors M9-M10 are used to avoid the clock feed through
and kickback effects from the latch to the input. Width of
these transistors also affects the performance of the latch. If
the width is increased, it adds to the equivalent capacitance on
the nodes of the latch and increases the effect of clock feed
through on the input; resulting in degradation in sensitivity
of the latch. If the width is decreased, then input signal has
to be increased otherwise charge imbalance on the latch is
not properly created. The latch operates in two phases; reset
and regeneration. In the Reset phase, the charge imbalance
is created on the differential nodes of the latch proportional
to the variation in the input signal. In regeneration mode, the
voltage imbalance on the nodes is amplified to the rail-to-rail
digital levels by the NMOS and PMOS regeneration loops.

### REFERENCE CIRCUIT
! [Pseudo Dynamic Latched Comparator Circuit] (C:\Users\Lenovo\Downloads\Screenshot 2022-02-26 210655.jpg)
