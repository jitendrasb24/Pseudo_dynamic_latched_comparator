# Design of a Pseudo Dynamic Latched Comparator in 28nm CMOS Technology
This repository presents the design of Pseudo dynamic latched comparator implemented using Synopsis Custom Compiler on 28nm CMOS Technology.

## **ABSTRACT**
A 28 NM CMOS Pseudo Dynamic Latched Comparator is proposed designed and Implemented using Synopsys Software. The comparator is a key building block for applications where digital information needs to be recovered from analog signals, such as analog-to-digital (A/D) converters, I/O data receivers, memory bit line detectors, etc. The trend of achieving both higher speed and lower power consumption in these applications makes dynamic latch comparators very attractive. We can verify the output using Circuit Waveforms. This complete design and implementation are done using VLSI technology which has features such as high speed, low power, low cost and small size.

## **TOOLS USED**
* **Synopsys Custom Compiler**
* **Synopsys Primewave**
* **Synopsys 28nm PDK**

## **REFERENCE CIRCUIT DETAILS**
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
![Reference Circuit](https://user-images.githubusercontent.com/86667690/155850929-5136c619-5c11-4382-97c8-df8bab03057f.jpg)

## **SIMULATION IN SYNOPSYS**

### TRANSIENT SETTINGS
![ta](https://user-images.githubusercontent.com/86667690/155851308-0b5351df-8094-468b-8720-fd4d8cf2a187.jpg)

### IMPLEMENTED CIRCUIT SCHEMATIC
![Schematic](https://user-images.githubusercontent.com/86667690/155851025-3e80ff17-9c20-48e6-bcd9-16f721f90fdb.jpg)

### IMPLEMENTED CIRCUIT WAVEFORM
![Waveform](https://user-images.githubusercontent.com/86667690/155851052-19fb1fbf-7640-4bfc-b3db-6bcb7995a2d8.jpg)

## **NETLIST**
```
*  Generated for: PrimeSim
*  Design library name: pldc_lib
*  Design cell name: pldc_tb
*  Design view name: schematic
.lib 'saed32nm.lib' TT

*Custom Compiler Version S-2021.09
*Sat Feb 26 16:40:14 2022

.global gnd! vcc!
********************************************************************************
* Library          : pldc_lib
* Cell             : pldc
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt pldc clk in+ in- out vo+ vo-
v8 net22 gnd! dc=1.8
v1 vcc! gnd! dc=1.8
xm18 vo+ clk vo- vo- n18 w=0.24u l=0.18u nf=1 m=1
xm17 vo+ vo- gnd! gnd! n18 w=0.24u l=0.18u nf=1 m=1
xm16 vo- vo+ gnd! gnd! n18 w=0.24u l=0.18u nf=1 m=1
xm14 net40 net21 gnd! gnd! n18 w=0.24u l=0.18u nf=1 m=1
xm13 vo+ clk net40 gnd! n18 w=0.24u l=0.18u nf=1 m=1
xm12 vo- clk net33 gnd! n18 w=0.24u l=0.18u nf=1 m=1
xm11 net33 out gnd! gnd! n18 w=0.24u l=0.18u nf=1 m=1
xm5 net9 net22 gnd! gnd! n18 w=0.24u l=0.18u nf=1 m=1
xm4 out in- net9 net9 n18 w=0.24u l=0.18u nf=1 m=1
xm3 net21 in+ net9 net9 n18 w=0.24u l=0.18u nf=1 m=1
xm20 vo+ vo- vcc! vcc! p18 w=0.24u l=0.18u nf=1 m=1
xm19 vo- vo+ vcc! vcc! p18 w=0.24u l=0.18u nf=1 m=1
xm7 out net21 vcc! vcc! p18 w=0.24u l=0.18u nf=1 m=1
xm6 net21 net21 vcc! vcc! p18 w=0.24u l=0.18u nf=1 m=1
.ends pldc

********************************************************************************
* Library          : pldc_lib
* Cell             : pldc_tb
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xi0 net24 net34 net42 net13 net32 net37 pldc
v49 net42 gnd! dc=1
v50 net37 gnd! dc=1
v29 net32 gnd! dc=1 pulse ( 0 1 0 0.1u 0.1u 5u 10u )
v27 net24 gnd! dc=1 pulse ( 0 1 0 0.1u 0.1u 5u 10u )
v28 net34 gnd! dc=1 pulse ( 0 1 0 0.1u 0.1u 5u 10u )
c9 net13 gnd! c=1p








.tran '1u' '200us' name=tran

.option primesim_remove_probe_prefix = 0
.probe v(*) i(*) level=1
.probe tran v(net13) v(net24)

.temp 25



.option primesim_output=wdf


.option parhier = LOCAL






.end
```

## **AUTHOR**

**JITENDRA SINGH BISHT**

**Bachelor of Technology(B.TECH)**

**3rd year Student**

**Bipin Tripathi Kumaon Institute of Technology, Dwarahat**

## **ACKNOWLEDGEMENT**

1. Cloud Based Analog IC Design Hackathon
2. Synopsys India
3. VLSI System Design (VSD) Corp. Pvt. Ltd India
4. Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.
5. Chinmay panda, IIT Hyderabad
6. Sameer Durgoji, NIT Karnataka

## **REFERENCES**

1. Khan Mohammed Salim Maksud Ali, ”Design of 4-bit Flash ADC” Project Dissertation Report, Department of Electronics and Telecommunication Engineering, AIKTC.
2. Kotresh Honagannavar, ”Dynamic latch-based comparator” International Journal of Computer Science and Mobile Computing, Vol.6, Issue. 8, August 2017, pg.32 – 35.
3. Sandeep Kumar and Varun Datta, ”A dynamic latched comparator for low supply voltages down to 0.45 V in 45 NM CMOS used in flash ADC” International Journal of Electronics, Communication and Instrumentation Engineering Research and Development (IJECIERD), Vol.5, Issue 4, Aug 2015, pg.9-20
