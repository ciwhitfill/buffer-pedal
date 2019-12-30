# JFET Buffer

This project documents the design and construction of a JFET buffer guitar pedal.

## Design

The circuit consists of a JFET source follower with an active load. Compared to passive biasing, an active load provides an operating point that is stable over a much larger range of voltages. This allows the amplifier to drive lower impedance loads at lower supply voltages.

<img src="./images/schematic.png" width="475">

## Simulation Results
The following simulations were conducted in LTspice. For the schematic file and simulation results, [see the simulation folder.](./simulation)

### Input Impedance 
A high input impedance is necessary to avoid loading passive guitar pickups. Generally, an input impedance of at least 1 MΩ is desired. The design provides this impedance throughout the audio range.

<img src="./images/input_impedance.png" width="660">

### Output Impedance
The design provides a low enough output impedance to drive line-level inputs. While the coupling capacitor dominates at low frequencies, the output impedance asymptotes to 100 Ω, which is more than sufficient for instrument level applications.

<img src="./images/output_impedance.png" width="660">

### Gain
A good voltage buffer has as close to a gain of 1 as possible. Due to the higher impedance of the active load, the design comes within 0.1 dB of this.

<img src="./images/gain.png" width="660">

### Power Supply Rejection
The design has a PSRR of -43dB at DC, and the power supply capacitor further filters supply noise at high frequencies.

<img src="./images/psrr.png" width="600">

### Noise
Noise simulation results in 171.18 nV in the audio range. Even if actual circuit noise is many times worse, it will be negligible compared to other noise sources in the signal chain.

<img src="./images/output_referred_noise.png" width="600">

