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
- Project topic and initial proposal
- Literature review of additive synthesis, FM synthesis, timbre modelling, and spectral modelling
- Revised research question based on project feedback
- Defined flute C4, E4, and A4 as the primary experimental notes
- Defined additive synthesis, FM synthesis, and pretrained DDSP as the main comparison framework

Currently in progress:
- Collecting and preparing isolated flute recordings
- MATLAB analysis of waveform, spectrum, spectrogram, harmonics, and amplitude envelope
- Initial implementation of additive and FM synthesis

## Next Steps

1. Analyse the real flute C4, E4, and A4 recordings.
2. Implement additive synthesis in MATLAB.
3. Implement two-operator FM synthesis in MATLAB.
4. Generate preliminary synthesis results.
5. Compare the generated tones with the real recordings.
6. Add automatic parameter fitting.
7. Perform leave-one-pitch-out timbre transfer experiments.
8. Add the pretrained DDSP flute baseline.
9. Perform residual analysis and final evaluation.

## Platform

- MATLAB for signal analysis, classical synthesis, optimisation, and evaluation
- Python / command line only where required for the pretrained DDSP baseline

## Project Proposal

The original project proposal is available in this repository.

## Project Status

Project implementation in progress.
