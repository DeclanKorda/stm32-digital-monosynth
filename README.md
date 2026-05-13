



# Digital Monosynth Built With STM32-Nucleo 

<img width="540" height="720" alt="image" src="https://github.com/user-attachments/assets/d233721a-e5ea-4e99-aeca-4078c089c4ab" />


This is, as the name suggests, code for a digital monophonic synthesizer built using an stm32 nucleo board and a sparkfun MIDI shield. 

## Capabilities

This code implements a synthesizer with the following capabilities:
- 3 waveforms (sinewave, sawtooth, and squarewave)
- Low-Pass State-Variable Filter (SVF) with resonance
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

- The Nucleo's DAC produces audio that is just barely audible when plugged into my powered speakers. If you could run the output through a preamp first I imagine you would get much better audio quality.
- The filter seems to behave more like a band filter rather than a low-pass. This may be due to the limited volume output from the DAC. Perhaps only frequencies near the cutoff are loud enough to be heard due to the resonance?
- The filter envelope behaves strangely. I may need to adjust how attack and decay scales over time.
- All controls are done through MIDI. Envelope and filter controls are assigned to specific midi controls for the Arturia KeyLab mkII. If using a different keyboard you may need to either change the MIDI callback to listen for different CC values or remap your midi controller's faders and encoders. 

## Demo

Audio recordings were recorded on my phone with the microphone right in front of my powered speakers at max volume. In person it's quite hard to hear.

### Waveform Demo 
Sinwave, sawtooth, and squarewave in that order.

https://github.com/user-attachments/assets/490576e3-c57a-4847-8e2a-41147b34f508

### Filter Demonstration
Squarewave. filter sweep with no resonance, filter sweep with some resonance, and a filter sweep with maximum resonance (self oscilation).

https://github.com/user-attachments/assets/73308151-cba4-4716-9658-780850c0a3db

### Volume Envelope Demonstration
Squarewave. First example uses a short attack with max sustain, causing the notes to fade in. Second example uses a short decay and 0 sustain, producing plucky notes. The last example uses a short attack and a short decay, with about 50% sustain, causing notes to fade in and then fade out slightly. 

https://github.com/user-attachments/assets/4ac01f4e-ad70-4718-b334-19f0a4565f24

### Filter Envelope Demonstration
Squarewave with a slight boost to resonance. First example uses a short attack and max sustain. Second example uses a short decay and 0 sustain. Last Example uses a short attack and a short decay, with about 50% sustain. 

https://github.com/user-attachments/assets/bd48a7ad-47d6-40c8-ab6d-f8e031574dab

## Next Steps:
In order of importance
- Improve filter
- Fix envelope scaling
- Add filter key tracking
- Add LFO for pitch, volume and filter modulation
- Add release to the volume and filter envelopes
- Add glide/portamento
- Add second oscilator


