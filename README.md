# Digital Monosynth Built With STM32-Nucleo 

This is, as the name suggests, code for a digital monophonic synthesizer built using an stm32 nucleo board and a sparkfun MIDI shield. 

## Capabilities

This code implements a synthesizer with the following capabilities:
- 3 waveforms (sinewave, sawtooth, and squarewave)
- State-Variable Filter (SVF) with resonance
- Communication over MIDI
- ADS envelopes for both volume and filter
- real time 48kHz audio generation

## Setup

To build this project, you need:

- STM32 Nucleo Board (NUH503RB)
- SparkFun MIDI Shield
- Pin Headers for MIDI Shield
- 3.5mm aux cable breakout board

### Steps
1. Connect the MIDI shield to the Nucleo's Arduino expansion connectors
2. Connect the tip and ring1 of the aux breakout board to pin 11 of the Nucleo's CN10 Morpho expansion connector
3. Connect the sleeve and ring2 of the aux breakout board to pin 9 of the Nucleo's CN10 Morpho expansion connector
4. Build and flash the code in this repository to your Nucleo board using the STM32CubeIDE software
5. Run and enjoy!

## Limitations

The Nucleo's DAC produces audio that is just barely audible when plugged into my powered speakers. If you could run the output through a preamp first I imagine you would get much better audio quality.

## Demo

Audio recordings were recorded on my phone with the microphone right in front of my powered speakers at max volume. In person it's quite hard to hear.

### Waveform Demo (Sinwave, Sawtooth, and Squarewave in that order).

### Filter Demonstration

### Volume Envelope Demonstration

### Filter Envelope Demonstration
