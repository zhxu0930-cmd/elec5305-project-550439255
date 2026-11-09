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

## Final Implementation

The final project focuses on flute timbre modelling using three synthesis approaches:

- Time-varying additive synthesis
- Constrained multi-start two-operator FM synthesis
- A pretrained DDSP flute model

Experiments were conducted using non-vibrato flute recordings at three target pitches:

- C4
- E4
- A4

The implementation includes:

- Waveform and FFT analysis
- STFT and spectrogram analysis
- Harmonic amplitude extraction
- Amplitude-envelope extraction
- Basic additive synthesis
- Envelope-based additive synthesis
- Time-varying harmonic additive synthesis
- Basic two-operator FM synthesis
- Automatic FM parameter fitting
- Constrained multi-start FM optimisation
- Pretrained DDSP flute resynthesis
- Leave-one-pitch-out timbre-transfer experiments
- Quantitative and residual spectral evaluation

## Quantitative Evaluation

The final comparison evaluates Time-Varying Additive, Multi-Start FM, and DDSP using:

- Log-Spectral Distance (LSD)
- Multi-Resolution STFT Error
- Harmonic Amplitude Error
- Temporal-Envelope Error
- Missing Spectral Energy
- Missing High-Frequency Energy between 2 and 5 kHz

All synthesis outputs are peak-normalised before the final quantitative comparison so that differences in output gain do not dominate the evaluation.

The results show that the three models capture different aspects of flute timbre.

DDSP achieved the lowest mean Log-Spectral Distance, indicating the closest overall spectral match to the reference recordings.

Time-varying additive synthesis achieved substantially lower multi-resolution STFT and harmonic-amplitude errors, reflecting its explicit modelling of the measured harmonic structure and temporal evolution of each reference tone.

Residual spectral analysis further showed that additive synthesis retained the lowest mean total missing spectral energy, while DDSP retained more high-frequency information in the 2--5 kHz region, particularly for the higher target pitches.

The compact two-operator FM model produced a valid controllable synthesis baseline but showed larger spectral and time-frequency reconstruction errors under the current model configuration.

## Leave-One-Pitch-Out Evaluation

A leave-one-pitch-out experiment was also conducted to test whether timbre parameters estimated from two pitches could be transferred to a third unseen pitch.

For additive synthesis, shared harmonic profiles were derived from the two available training pitches and applied to the held-out pitch.

For FM synthesis, shared carrier/modulator relationships and modulation-index parameters were estimated from the available training pitches and transferred to the held-out pitch.

The leave-one-pitch-out results show a clear reduction in reconstruction accuracy compared with independently fitted models, demonstrating that compact classical timbre parameters do not transfer perfectly across pitch.

## DDSP Baseline

A pretrained DDSP flute model was evaluated as the modern synthesis baseline.

The original DDSP automatic adjustment changed the input pitch range substantially for the lower flute tone. Therefore, the final comparison uses pitch-preserving inference with automatic adjustment disabled.

The final DDSP outputs preserve the original target pitches C4, E4, and A4.

The DDSP outputs exhibit different attack and decay behaviour from the reference recordings. An alignment check confirmed that this was primarily a difference in temporal-envelope reconstruction rather than a simple global timing offset.

## Repository Structure

```text
audio_output/
    Synthesised Additive, FM, LOPO, and DDSP audio

results/
    Preliminary analysis and synthesis figures

results_02/
    Final quantitative evaluation, LOPO, residual, and three-model results

flute_analysis_01.mlx
    Initial flute analysis and classical synthesis experiments

final_evaluation_02.mlx
    Final quantitative evaluation and leave-one-pitch-out experiments

ddsp_timbre_transfer.ipynb
    Pretrained DDSP flute timbre-transfer experiment
```

## Main Findings

The results do not indicate that one synthesis method is uniformly superior.

Time-varying additive synthesis provides strong reconstruction of explicitly measured harmonic and temporal structure.

DDSP provides the closest overall spectral match and captures additional high-frequency spectral characteristics, but its temporal envelope differs more strongly from the reference recordings.

Two-operator FM synthesis offers a compact parametric representation, although its restricted model structure leads to larger reconstruction errors for the flute tones used in this study.

The leave-one-pitch-out experiment further demonstrates that pitch-independent timbre transfer is more difficult than independent fitting of individual notes.

## Platform

- MATLAB for signal analysis, additive synthesis, FM synthesis, optimisation, quantitative evaluation, and leave-one-pitch-out experiments
- Google Colab / Python for the pretrained DDSP flute model

## Project Proposal

The original project proposal is available in this repository.

## Project Status

Final implementation and quantitative evaluation completed.
