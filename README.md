# PEMF–Brachial Hemodynamics: Representative PPG and Doppler Data

## Overview

This repository accompanies the research article:

*Kiser A et al. (2026).* Pulsed Electromagnetic Field Driven Perturbation of Peripheral Arterial Hemodynamics: Integrated Evidence from Doppler Ultrasound and Photoplethysmographic Signal Analysis. Biomedical Physics & Engineering Express.

*Article DOI:* https://doi.org/10.1088/2057-1976/aeb382

The study investigated acute peripheral vascular responses to pulsed electromagnetic field (PEMF) exposure in 20 healthy adults, using photoplethysmography (PPG) and Doppler ultrasound. Two PEMF configurations, Forward and Reverse, were examined to assess orientation-dependent vascular waveform responses.

## Repository Contents

| Directory | Description |
|---|---|
| Representative_Signals/PPG/ | Example raw PPG recordings and processed, accepted cardiac cycles |
| Representative_Signals/Doppler/ | Example radial-artery Doppler recordings |

*Data scope:* The repository contains illustrative recordings only, not the complete dataset used for statistical analysis.

## Experimental Conditions

PEMF was applied over the brachial artery using a circular coil (200 turns, 4 cm radius), with nominal stimulation parameters of 15 V, 100 µs pulse duration and 10 Hz repetition frequency.

- *Forward:* Induced electric-field component intended to align with physiological arterial blood flow.
- *Reverse:* Induced electric-field component intended to oppose physiological arterial blood flow.
- *Baseline:* Corresponding recordings obtained without active PEMF stimulation.

PPG was recorded from the index finger at *100 Hz, and Doppler audio was acquired from the radial artery at **48 kHz*.

## Data Format and Processing

*PPG:* The raw data contain the ppgSignal waveform and accompanying device outputs. Processing involved sixth-order polynomial baseline correction, min–max normalization, and cardiac-cycle segmentation. Accepted cycles were identified using waveform minima and a cycle-duration criterion of 0.60–1.20 s.

*Doppler:* Audio recordings were processed using high-pass filtering, short-time Fourier analysis, spectral-envelope extraction and waveform-quality screening.

Detailed acquisition, processing and statistical methods are provided in the associated article. PPG and Doppler recordings were not hardware-synchronized.

## Data Availability

Only representative PPG and Doppler recordings are publicly provided. These examples are intended to illustrate the acquired signals and should not be used independently to reproduce the complete statistical findings.

The underlying research datasets and processing or analysis code may be requested from the corresponding author, subject to applicable ethical and institutional requirements.

## Ethics and Data Use

The study was approved by the North South University Institutional Review Board (Approval No. 2020/ORNSU/IRB/1112), and participants provided written informed consent.

The publicly shared data must be appropriately de-identified and authorized for release.

*License:* Creative Commons CC0 1.0 Universal, as indicated in the repository.

## Citation

*Dataset:* Kiser A et al. (2026). Representative PPG and Doppler Data from a PEMF Study of Peripheral Arterial Hemodynamics. GitHub.

https://github.com/AhmedKiser/PEMF-Brachial-Hemodynamics-Representative-PPG-and-Doppler-Data

Please also cite the associated journal article.

## Contact

*Zaid Bin Mahbub*  
Corresponding Author  
Department of Mathematics and Physics  
North South University, Dhaka, Bangladesh  
zaid.mahbub@northsouth.edu

*Repository maintained by:* Ahmed Kiser.