# IPS
Impedance Positioning System

Idea: Create an AC impedence-based positioning system. Electrical currents in 3-axis configuration create an impedance field within a conducting saline tank that can be read by electrode. Esentially an engineering one-off, proof-of-concept of an impedance based cardiac mapping system.

Systems needed to develop:

Easy/trivial

1) Saline tank - plexiglass container filled with saline

2) surface electrodes - repurpose old electrodes

3) positioning electrode - repurpose old catheter

nontrivial

1) Current delivery

2) Impedence detection

3) determining positional coordinates

4) real-time model creation


Process
=======

Here is the idea: send a known current (say 20mA) through an impedence field (say 0.9% Normal Saline Solution). V=I/R and we know I, and we can detect the voltage drop across the field. Then the Impedance varies depending on position within the field. As the current passes from left to right the Impedance goes from minimum to maximum. this linear (in a saline bath) relationship can be exploited to create a coordinate system. Since we are working with AC, repeat the process for two more axis (with different ac frequencies) and you have an x,y,z coordinate system. There is an electrode located within the field that can read the impedence. I believe I can use an FFT to isolate the three frequencies, and then use relative amplitudes to determine the amount of impedence. I know there are a few parts to ac impedence (inductance and reactance, as well as a real and imaginary part) so more background theory will be needed here. Use python for the fft and coordinate math as well as find out a way to real-time coordinate display. Stretch goal would be to store and real-time 3d model the position.

Few thoughts: Hardware is expensive. I need to model as much as possible beforehand. I can use exsisting bioimpedence measuring device algorithms and arduino projects to get some working theory for a single plane of impedence detection. I also want to attempt to model the impedence field in a SPICE program. That may be the first step.