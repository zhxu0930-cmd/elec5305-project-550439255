# ELEC5305 Project

## From Additive and FM Synthesis to DDSP: Modelling Musical Instrument Timbre

This project investigates musical instrument timbre modelling using both classical and modern synthesis approaches.

The project compares:

- Additive synthesis
- Frequency modulation (FM) synthesis
- A pretrained DDSP-based instrument synthesis model

The main focus is flute timbre modelling across multiple pitches, with piano retained as a secondary classical comparison.

## Revised Research Question

How do classical additive and FM synthesis compare with a modern DDSP-based instrument model in reconstructing and transferring musical-instrument timbre across pitch?

A secondary question is:

What does the learned DDSP model capture that remains in the residual error of compact additive and FM models?

## Target Instrument and Notes

### Primary instrument
- Flute

### Target notes
- C4
- E4
- A4

### Secondary instrument
- Piano, for classical additive and FM comparison where time permits

## Planned Methods

### Classical synthesis
- Additive synthesis
- Two-operator FM synthesis
- Time-varying amplitude envelopes

### Signal analysis
- Waveform analysis
- Fourier spectrum
- STFT and spectrogram
- Harmonic amplitude analysis
- Amplitude-envelope extraction

### Evaluation
- Log-spectral distance
- Multi-resolution STFT error
- Harmonic amplitude error
- Temporal-envelope error
- Residual signal analysis

### Modern baseline
- Pretrained DDSP instrument synthesis model
- Flute will be used for the main Additive vs FM vs DDSP comparison

## Current Progress

Completed:
- Reference flute recordings collected for C4, E4, and A4
- Waveform, FFT, STFT, harmonic and amplitude-envelope analysis
- Basic additive synthesis
- Envelope-based additive synthesis
- Time-varying harmonic additive synthesis
- Basic two-operator FM synthesis
- Automatic FM parameter fitting
- Constrained multi-start FM optimisation
- Preliminary audio and spectral comparison results
- Log-spectral distance evaluation
- Multi-resolution STFT error evaluation
- Harmonic amplitude error evaluation
- Temporal-envelope error evaluation

Current findings:
- Time-varying harmonic modelling provides a more realistic representation than fixed-amplitude additive synthesis.
- Multi-start constrained FM fitting substantially reduces spectral cost compared with the initial unconstrained FM fitting.
- Different FM initialisations converge to different local solutions, showing the importance of multi-start optimisation.

## Preliminary Results

Preliminary experiments have been completed for flute notes C4, E4, and A4.

The current implementation includes:

- Waveform and FFT analysis
- STFT spectrogram analysis
- Harmonic amplitude extraction
- Amplitude-envelope extraction
- Basic additive synthesis
- Envelope-based additive synthesis
- Time-varying harmonic additive synthesis
- Basic two-operator FM synthesis
- Automatic FM parameter fitting
- Constrained multi-start FM optimisation

Selected figures are available in the `results` folder, and representative synthesized audio files are available in the `audio_output` folder.

The current results show that time-varying harmonic modelling better captures the temporal evolution of the reference flute tones than fixed-amplitude additive synthesis. For FM synthesis, constrained multi-start optimisation produces lower spectral error than the initial unconstrained fitting approach.

## Quantitative Evaluation

Independent reconstruction performance was evaluated for flute notes C4, E4, and A4 using four complementary metrics: log-spectral distance (LSD), multi-resolution STFT error, harmonic amplitude error, and temporal-envelope error.

The results show different strengths for the two classical synthesis approaches. Multi-start FM achieved lower log-spectral distance and slightly lower temporal-envelope error, while time-varying additive synthesis achieved substantially lower multi-resolution STFT error and harmonic amplitude error.

Across the three notes, the mean multi-resolution STFT error was 0.1718 for time-varying additive synthesis and 1.6511 for multi-start FM. The mean harmonic amplitude error was 0.0189 for additive synthesis and 0.2590 for FM. The mean temporal-envelope error was 0.0201 for additive synthesis and 0.0132 for FM.

These results suggest that additive synthesis more accurately represents explicit harmonic and time-frequency structure, whereas the fitted FM model can reproduce some global spectral and temporal characteristics with a more compact parameterisation.

This stage evaluates independently fitted tones. The next experiment uses leave-one-pitch-out testing to determine whether the learned timbre parameters transfer to an unseen pitch.

## Cross-Pitch Timbre Transfer

Leave-one-pitch-out experiments were conducted to test whether the classical synthesis models capture pitch-independent flute timbre rather than only reconstructing individually fitted notes.

Three transfer folds were evaluated: C4 and E4 were used to predict A4, C4 and A4 were used to predict E4, and E4 and A4 were used to predict C4. For additive synthesis, shared relative harmonic amplitudes and a shared temporal-envelope profile were estimated from the two training pitches. For FM synthesis, shared carrier ratio, modulator ratio, and modulation index parameters were derived from the training pitches and transferred to the held-out fundamental frequency.

Under leave-one-pitch-out evaluation, additive synthesis retained substantially lower multi-resolution STFT error and harmonic amplitude error than FM synthesis. The mean multi-resolution STFT errors were 0.5676 for additive synthesis and 1.6828 for FM, while the corresponding harmonic amplitude errors were 0.0523 and 0.2218.

Residual spectral analysis also showed a substantially larger overall missing spectral-energy measure for FM than for additive synthesis. However, the mean missing energy in the 2--5 kHz region was similar between the two methods, indicating that the perceptual difference is better explained by broader harmonic and spectral-structure mismatch than by high-frequency attenuation alone.

The comparison between independently fitted reconstruction and leave-one-pitch-out transfer demonstrates that good reconstruction of a known pitch does not necessarily imply robust cross-pitch timbre transfer.

## Next Steps

- Integrate a pretrained DDSP flute baseline
- Evaluate DDSP on the same C4, E4, and A4 reference tones
- Compare Additive, FM, and DDSP using common evaluation metrics
- Compare residual spectral structure across the three modelling approaches
- Prepare final figures, discussion, and project documentation

## Platform

- MATLAB for signal analysis, classical synthesis, optimisation, and evaluation
- Python / command line only where required for the pretrained DDSP baseline

## Project Proposal

The original project proposal is available in this repository.

## Project Status

Project implementation in progress.
