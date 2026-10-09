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

Current findings:
- Time-varying harmonic modelling provides a more realistic representation than fixed-amplitude additive synthesis.
- Multi-start constrained FM fitting substantially reduces spectral cost compared with the initial unconstrained FM fitting.
- Different FM initialisations converge to different local solutions, showing the importance of multi-start optimisation.

## Next Steps
- Organise quantitative comparison metrics across synthesis methods
- Compare additive and FM results more systematically
- Integrate a pretrained DDSP baseline
- Perform cross-pitch timbre transfer and residual analysis


## Platform

- MATLAB for signal analysis, classical synthesis, optimisation, and evaluation
- Python / command line only where required for the pretrained DDSP baseline

## Project Proposal

The original project proposal is available in this repository.

## Project Status

Project implementation in progress.
