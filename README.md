Analog Noise Cancellation System 

Course: EE322: Analog and Mixed Signal Circuits (IIT Gandhinagar)

Team: Waveform Wizards

Overview

This project implements a cost-effective, real-time Analog Active Noise Cancellation (ANC) system for headphones. Unlike complex digital solutions involving DSPs, this system utilizes purely analog circuitry to reduce ambient low-frequency noise (such as engine hum or fans) using destructive interference.

The circuit captures external noise via microphones, processes the signal to align phase and amplitude, and sums the inverted "anti-noise" with the user's audio playback.

Team Members

Swayam Borate

Parth Dembla

Shriniket Behera

System Architecture

The system is designed for a stereo application (Left/Right channels) and consists of five primary stages:

Microphone Input (Sensing): * Uses ECM-60PC-R Electret Microphones mounted on the earcups.

Biased at approx 4.5V DC with a low-pass filter to remove power supply ripple.

Pre-Amplifier: * LM741 Op-Amp configured as a non-inverting amplifier (Gain $\approx$ 23).

Filters unwanted DC offsets while boosting the weak microphone signal.

All-Pass Filter (Phase Delay):

Critical stage that introduces a controlled time delay without altering signal amplitude.

Synchronizes the electrical signal with the physical time it takes for sound to travel from the outside of the headphone to the ear canal.

Summing Amplifier (Inverter):

Inverts the noise signal to create "anti-noise."

Sums the Music Signal + Anti-Noise.

Includes a potentiometer to fine-tune the gain for maximum cancellation.

Output Driver:

Drives the headphones via a standard 3.5mm audio jack.

Hardware & Components

The design is optimized for standard Through-Hole (THT) components for ease of soldering and prototyping.

Component

Type

Function

Op-Amps

LT1056 (Sim) / LM741 (Hardware)

Amplification, Filtering, Summing

Microphone

ECM-60PC-R

Ambient noise capture

Potentiometers

500kΩ

Gain/Sensitivity tuning

Power Supply

±9V Dual Rail

System power

Passives

Various Resistors/Capacitors

Biasing and RC networks

Software Tools

LTspice: Used for initial circuit simulation, transient analysis, and verifying noise cancellation waveforms.

KiCad: Used for schematic capture, footprint assignment, and PCB layout (2-layer board, 100mm x 100mm).

Simulation & Results

Simulation: LTspice simulations demonstrated successful mixing of the random noise source (simulated ambient noise) with the inverted signal, resulting in significant amplitude reduction at the output node.

PCB Design: A custom PCB was designed in KiCad featuring a stereo layout. The design passed DRC (Design Rules Check) and generated Gerber files ready for fabrication.

PCB Fab Estimate: ~₹1901 for 5 boards (Lion Circuits).

 Setup & Usage

Power: Connect a dual-rail power supply (±9V) to the VCC+ and VCC- terminals.

Input: Connect your music source (Phone/PC) to the Music In 3.5mm jack.

Calibration:

Power on the circuit in a noisy environment.

Adjust the Potentiometer on the summing amplifier until the background noise is audibly minimized.

This aligns the amplitude of the anti-noise with the actual noise.






Thr Repository consists of KiCAD Files , Gerber Files for PCB , Proposal and simulation report
