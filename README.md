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

## Next Steps

- Perform leave-one-pitch-out timbre transfer using C4, E4, and A4
- Evaluate shared additive and FM timbre parameters on held-out pitches
- Integrate a pretrained DDSP flute baseline
- Compare Additive, FM, and DDSP using the same held-out-pitch evaluation framework
- Perform residual spectral analysis
- Prepare final comparison figures, discussion, and project documentation

## Platform

- MATLAB for signal analysis, classical synthesis, optimisation, and evaluation
- Python / command line only where required for the pretrained DDSP baseline

## Project Proposal

The original project proposal is available in this repository.

## Project Status

Project implementation in progress.
