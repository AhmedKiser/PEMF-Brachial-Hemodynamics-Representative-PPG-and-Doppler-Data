# PEMF–Brachial Hemodynamics: Representative PPG and Doppler Data

This repository accompanies the article:

**Pulsed Electromagnetic Field Driven Perturbation of Peripheral Arterial Hemodynamics: Integrated Evidence from Doppler Ultrasound and Photoplethysmographic Signal Analysis**

**Article DOI:** [10.1088/2057-1976/aeb382](https://doi.org/10.1088/2057-1976/aeb382)  
**Journal:** Biomedical Physics & Engineering Express, 2026  
**Repository name:** `PEMF-Brachial-Hemodynamics`  
**Data license:** [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/)

The repository contains example photoplethysmography (PPG) and Doppler data from a study of peripheral arterial hemodynamics during pulsed electromagnetic field (PEMF) exposure. It explains how to obtain the PPG waveform from the raw export, preprocess it, and interpret the accepted cardiac cycles.

**Only example data are provided here. For the full dataset, please email the corresponding author. The full processing and analysis code can be made publicly available upon request.**

## 1. Authors, affiliations, and contact

**Authors:** Ahmed Kiser (1), Md Tarikul Islam (1), Jubair Ibn Omar Hamza (1), Sumaiya Tabassum Dipty (1, 2), Sayed Salman Aziz (1, 3), Mahbubur Rahman (4), Jamil H Karami (5), Rashal Chowdhury (6), Shahnaj Latif (7), Muhammad E. H. Chowdhury (8), Khondkar Siddique-e Rabbani (3), and Zaid Bin Mahbub (1, corresponding author).

| No. | Affiliation |
| --- | --- |
| 1 | Department of Mathematics and Physics, North South University, Dhaka, Bangladesh |
| 2 | Department of Biomedical Engineering, University of Utah, Salt Lake City, USA |
| 3 | Department of Biomedical Physics and Technology, University of Dhaka, Bangladesh |
| 4 | Department of Pharmaceutical Sciences, North South University, Dhaka, Bangladesh |
| 5 | Department of Statistics, University of Dhaka, Bangladesh |
| 6 | Department of Vascular Surgery, Bangabandhu Sheikh Mujib Medical University, Dhaka, Bangladesh |
| 7 | City University of New York (CUNY), New York, NY, USA |
| 8 | Department of Electrical Engineering, Qatar University, Doha, Qatar |

### Corresponding author

**Zaid Bin Mahbub, Associate Professor**  
Room SAC1065B, Department of Mathematics and Physics  
North South University, Dhaka 1229, Bangladesh  
Email: [zaid.mahbub@northsouth.edu](mailto:zaid.mahbub@northsouth.edu)  
Phone: +880-2-55668200  
Fax: +880-2-55668202

## 2. Repository organization

All paths below are relative to `PEMF-Brachial-Hemodynamics/`.

| Path | Contents |
| --- | --- |
| `README.md` | Study information, data dictionary, processing instructions, access information, ethics, and license |
| `Representative_Signals/PPG/` | Example PPG data, including raw signal data and the supplied accepted-cycle data |
| `Representative_Signals/Doppler/` | Example Doppler data from radial-artery recordings |

Start with the **raw signal data under the PPG folder**. The raw tabular export contains the following columns, in the supplied order:

| index | timestamp | deviceId | battery | ppgSignal | heartRate | spO2 | redAdc | irAdc | spO2Status | perfusionIndex |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

Select **`ppgSignal`** as the waveform to preprocess. The supplied processed data show the retained pulses in the **accepted cycles** column/table, where **each row represents one accepted cardiac cycle**.

## 3. Study participants and experimental conditions

### Participants

Twenty healthy adults participated in the complete study.

| Characteristic | Value |
| --- | --- |
| Participants | 20: 14 males and 6 females |
| Age | 24.95 ± 2.37 years |
| Height | 1.65 ± 0.05 m |
| Body mass | 75.05 ± 9.45 kg |
| Body mass index | 27.50 ± 2.61 kg/m² |
| Resting heart rate | 74.25 ± 6.09 beats/min |

Values are mean ± standard deviation where applicable. Volunteers were screened to exclude known cardiovascular, metabolic, or chronic systemic conditions. They avoided caffeine, nicotine, and strenuous physical activity for at least 2 hours before testing and rested quietly for 10 minutes before the experiment.

The number of participants in the complete study does not imply that recordings from all 20 participants are included in the public examples.

### PEMF stimulation

The applicator was jointly developed by the Department of Biomedical Physics & Technology, University of Dhaka, and BiBEAT Limited.

| Parameter | Setting |
| --- | --- |
| Coil | Circular multi-turn coil |
| Turns | 200 |
| Radius | 0.04 m |
| Pulse amplitude | 15 V |
| Pulse duration | 100 µs |
| Repetition frequency | 10 Hz |
| Measured coil inductance | Approximately 5 mH |
| Measured coil resistance | Approximately 5 Ω |
| Placement | Over the brachial artery on the distal anterior upper arm, just proximal to the elbow |
| Coil-to-skin distance | Approximately 1 cm |
| Stabilization | Non-metallic support and straps, with care to minimize pressure on the underlying tissue |

Metallic and ferromagnetic materials were kept away from the exposure region. Coil location and nominal stimulation parameters were maintained across the two configurations.

### Forward, Reverse, and baseline recordings

| Configuration / condition | Definition |
| --- | --- |
| Forward | Coil arrangement intended to align the local induced electric-field component projected along the arterial axis with physiological blood flow toward the forearm |
| Reverse | Applicator orientation reversed so that this induced electric-field component was intended to oppose physiological blood flow |
| No-PEMF / baseline | Recording obtained before the corresponding active exposure, with stimulation off |
| PEMF / exposure | Recording obtained during active stimulation in the corresponding Forward or Reverse configuration |

Each participant underwent both configurations in randomized order. A separate No-PEMF baseline was recorded before each exposure. A minimum rest of 20 minutes separated the trials, and participants were unaware of the applied field orientation.

Forward and Reverse describe the PEMF arrangement, not reversal of physiological blood flow. The 100 µs pulse duration and the 20-minute rest interval must not be interpreted as the total active exposure duration; that duration was not specified in the supplied study information.

## 4. Signal acquisition, time, and units

| Signal | Acquisition details | Sampling frequency |
| --- | --- | --- |
| PPG | SmartCare reflective finger-clip sensor with an approximately 660 nm red LED and photodiode, placed on the index finger of the same upper limb used for Doppler assessment | 100 Hz |
| Doppler audio | 8 MHz continuous-wave probe over the radial artery at the wrist, approximately 60° target insonation angle, ultrasound gel, and USB audio interface | 48,000 Hz |

The PEMF coil was positioned over the brachial artery, with PPG and Doppler measurements obtained downstream. Doppler probe position, orientation, and pressure were maintained as consistently as practicable. Insonation angle and contact pressure were not instrumentally monitored.

### PPG time and duration

At 100 Hz, consecutive PPG samples are separated by **0.01 s**. For a continuous recording containing `N` samples, a relative analysis time vector can be constructed as:

`t[n] = n / 100 seconds, for n = 0, 1, ..., N−1`

The elapsed span between the first and last samples is `(N−1)/100` seconds. This describes the supplied signal segment, not necessarily the complete acquisition or exposure duration.

The raw `timestamp` field is retained as an acquisition timestamp. Its encoding and units were not specified in the supplied information, so it must not automatically be interpreted as seconds, milliseconds, or a Unix timestamp. The relative time vector above provides the documented 100 Hz analysis time base.

### Amplitude and derived signals

- **Raw `ppgSignal`:** Native device-reported digital waveform amplitude. No conversion to calibrated voltage or blood volume is specified.
- **Normalized PPG:** Dimensionless amplitude between 0 and 1 after the processing below.
- **Doppler audio:** Native recorded digital audio amplitude. A calibrated audio-amplitude unit was not supplied.
- **Derived Doppler velocity:** Interpret its units and time grid from the supplied export or the study implementation. The 48,000 Hz audio rate must not automatically be assigned to reconstructed velocity samples.

A shared hardware synchronization scheme was not specified in the supplied information. Do not infer beat-to-beat alignment between PPG and Doppler solely from file order or nominal recording start.

## 5. How to process the PPG data

### Step 1 — Open the raw PPG recording

Go to `Representative_Signals/PPG/` and open the raw signal data. Locate the column named **`ppgSignal`**.

Read its values in their original row order. In the raw recording, successive rows represent successive acquisition samples. The `heartRate`, `spO2`, `redAdc`, and `irAdc` columns are additional device outputs; the waveform input for this processing procedure is `ppgSignal`.

### Step 2 — Use the 100 Hz sampling frequency

Set the analysis sampling frequency to **100 Hz**. Use the sample order to construct relative time in seconds as described in Section 4.

Keep each recording associated with its original participant code, Forward/Reverse configuration, and baseline/exposure condition.

### Step 3 — Estimate the slow baseline variation

Fit a **sixth-order polynomial** to the complete raw PPG recording. The fitted polynomial estimates the slow baseline variation across the recording.

### Step 4 — Subtract the fitted baseline

Subtract the fitted polynomial from the raw waveform:

`PPG_corrected(t) = ppgSignal(t) − polynomial_6(t)`

This produces the baseline-corrected PPG signal.

### Step 5 — Normalize the complete corrected recording

Apply min–max normalization to the complete baseline-corrected recording:

`PPG_normalized = (PPG_corrected − min(PPG_corrected)) / (max(PPG_corrected) − min(PPG_corrected))`

Perform this operation **before segmenting individual cardiac cycles**. The resulting waveform ranges from 0 to 1.

The minimum and maximum refer to the complete corrected recording, not to each separately extracted cycle. The resulting amplitudes describe waveform shape relative to that recording and do not preserve calibrated absolute optical amplitude across recordings.

### Step 6 — Identify candidate cycle boundaries

Identify local minima of the normalized waveform. Candidate cycle-boundary minima must have normalized amplitude **≤ 0.20**.

Consecutive accepted minima define a candidate PPG cycle.

### Step 7 — Apply the cycle-length acceptance criterion

Retain candidate cycles containing **60–120 samples**, equivalent to **0.60–1.20 s** at 100 Hz.

Segments outside this range are excluded from the accepted-cycle set.

### Step 8 — Read the supplied accepted cycles

After preprocessing and segmentation, the retained cycles are shown in the supplied **accepted cycles** column/table.

**Each row means one complete accepted cardiac cycle.**

| Data representation | Meaning of a row |
| --- | --- |
| Raw signal data containing `ppgSignal` | One acquisition sample at a particular point in the continuous recording |
| Accepted-cycle data | One retained PPG pulse/cardiac cycle, containing its waveform samples |

Read or plot each accepted-cycle row as an individual pulse, preserving the stored sample order. The number of accepted-cycle rows gives the number of accepted cycles represented in that table, not the number of participants.

This acceptance step uses the stated boundary and cycle-length criteria; it does not establish that every retained cycle is free of all recording artefacts.

### Step 9 — Extract features from individual cycles

Calculate the time-domain, morphological, amplitude, area, and timing features defined in Table 1 of the article for each accepted cycle.

**Processing order matters:** If a shared raw file is an excerpt of a longer acquisition, refitting the polynomial and recalculating the normalization limits on that excerpt can produce different values from preprocessing the original complete recording. The corresponding author can provide the implementation and source-recording context on request.

## 6. Doppler processing: step by step

1. **Load the recording.** Read the Doppler audio acquired at 48,000 Hz.
2. **Filter the audio.** Apply a second-order Butterworth high-pass filter with a 100 Hz cutoff using forward–backward filtering to obtain effectively zero-phase filtering.
3. **Calculate the STFT.** Use a 1024-sample Hann window, 75% overlap, a 1024-point FFT, and a one-sided spectrum.
4. **Improve spectral continuity.** Apply Gaussian smoothing, adaptive thresholding, and median filtering to suppress background noise and improve spectral-envelope continuity.
5. **Extract the envelope and reconstruct the waveform.** Use the study's Doppler-frequency envelope extraction and velocity-reconstruction implementation.
6. **Assess cycle quality.** Use signal-quality assessment and visual inspection to exclude cycles with inadequate spectral-envelope quality or physiologically implausible waveform morphology.
7. **Extract Doppler features.** Apply the article's waveform-feature definitions to the retained cycles.

| STFT parameter | Setting |
| --- | --- |
| Input audio rate | 48,000 Hz |
| Window | Hann |
| Window length | 1024 samples |
| Overlap | 768 samples, equivalent to 75% |
| Hop size | 256 samples |
| FFT length | 1024 points |
| Spectrum | One-sided |

These settings correspond to an approximately 21.33 ms window and 5.33 ms between frames. The nominal frame cadence is 187.5 frames/s before any further resampling.

The 100 Hz high-pass filter applies to the **audio**, not directly to the reconstructed cardiac velocity waveform. Exact envelope extraction, conversion constants, smoothing settings, segmentation rules, and export units should be obtained from the study implementation. The full code can be made publicly available upon request to the corresponding author.

## 7. Raw PPG data dictionary

The following names match the columns supplied for the raw PPG export.

| Column | Meaning | Interpretation for this workflow |
| --- | --- | --- |
| `index` | Exported row or sample index | A sample-order reference; not a participant identifier |
| `timestamp` | Acquisition timestamp reported by the device/export | Encoding and units are not specified here; use the documented 100 Hz rate to construct relative analysis time |
| `deviceId` | Device identifier recorded by the acquisition system | Device metadata; not a PPG amplitude or participant label |
| `battery` | Device-reported battery indicator | Device-specific scale; not used in the waveform preprocessing |
| `ppgSignal` | Recorded PPG waveform channel | **Select this column as the preprocessing input**; amplitude remains in native device units until normalization |
| `heartRate` | Device-reported heart-rate estimate | Beats/min; an accompanying device output |
| `spO2` | Device-reported peripheral oxygen-saturation estimate | Percent; an accompanying device output |
| `redAdc` | Red-channel analog-to-digital converter reading | Digital counts; an auxiliary channel |
| `irAdc` | Infrared-channel analog-to-digital converter reading | Digital counts; an auxiliary channel |
| `spO2Status` | Device-specific status associated with the oxygen-saturation output | Status-code meanings depend on the acquisition device and are not defined by the supplied information |
| `perfusionIndex` | Device-reported perfusion index | Device-specific output and scale; not used in the stated PPG preprocessing |

### Accepted-cycle data dictionary

| Entry | Meaning |
| --- | --- |
| Accepted cycles | Retained PPG cardiac cycles obtained after the stated preprocessing, boundary detection, and cycle-length acceptance steps |
| One row | One accepted cardiac cycle |
| Waveform samples within a row | Samples describing that cycle in the stored order |
| Normalized waveform amplitude | Dimensionless, derived from full-recording min–max normalization |
| Accepted duration range | 0.60–1.20 s, corresponding to 60–120 samples at 100 Hz |

**Abbreviations:** PEMF = pulsed electromagnetic field; PPG = photoplethysmography; ADC = analog-to-digital converter; SpO₂ = peripheral oxygen saturation; PSD = power spectral density; DFT = discrete Fourier transform; STFT = short-time Fourier transform; FFT = fast Fourier transform; DC = zero-frequency component; KDE-L1 = kernel-density-based L1 distribution comparison; IRB = Institutional Review Board.

## 8. Example-data selection and scope

The repository supplies examples to illustrate the recordings, the raw PPG export, and the accepted-cycle representation. It contains an **illustrative subset**, not the full study dataset.

A formal random-sampling or population-representativeness claim is not made for these examples. The supplied description does not specify a quantitative subset-selection rule, so no such rule is asserted here.

The examples should not be used alone to recalculate all article statistics, estimate population effects, or infer how frequently a particular waveform response occurred across the complete cohort. For the full dataset and details of the example selection, contact the corresponding author.

## 9. Ethics, consent, and public release

The study received ethical approval from the **North South University Institutional Review Board, Approval No. 2020/ORNSU/IRB/1112**. All participants provided written informed consent before participation.

The supplied information documents study approval and participation consent. It does not document a separate file-level de-identification review or authorization for unrestricted public release of the specific exported recordings. Confirmation of these release-specific matters should be obtained from the corresponding author; this README does not independently certify them.

Device identifiers, timestamps, filenames, and embedded metadata require consideration in a de-identification review. A device identifier is not automatically an anonymous participant code.

## 10. License

The example research data and original dataset documentation in this repository are released under the **Creative Commons CC0 1.0 Universal Public Domain Dedication**.

To the extent permitted by applicable law, contributors waive their copyright and related rights in these materials. They may be copied, modified, redistributed, and reused, including for commercial purposes, without requesting copyright permission.

- [CC0 1.0 summary](https://creativecommons.org/publicdomain/zero/1.0/)
- [CC0 1.0 legal code](https://creativecommons.org/publicdomain/zero/1.0/legalcode.en)

Citation is requested as scholarly practice, not as a condition of CC0 reuse. The dedication does not change the publication terms of the associated journal article or waive other people's privacy rights. It applies to the data and documentation shared here, not to analysis code that has not been released in this repository.

## 11. Citation, full-dataset access, and code

### Article citation

Kiser, A., et al. (2026). *Pulsed Electromagnetic Field Driven Perturbation of Peripheral Arterial Hemodynamics: Integrated Evidence from Doppler Ultrasound and Photoplethysmographic Signal Analysis*. Biomedical Physics & Engineering Express. [https://doi.org/10.1088/2057-1976/aeb382](https://doi.org/10.1088/2057-1976/aeb382).

When using these examples, please cite the article and identify the `PEMF-Brachial-Hemodynamics` repository. Use the URL of the repository from which the files were obtained; a permanent repository URL or separate dataset DOI was not supplied for this documentation.

### Full dataset

Only example recordings are included in the public folders. **To request the full dataset, please email the corresponding author, Zaid Bin Mahbub, at [zaid.mahbub@northsouth.edu](mailto:zaid.mahbub@northsouth.edu).**

### Processing and analysis code

**The full processing and analysis code can be made publicly available upon request.** Please email the corresponding author to request the code for PPG preprocessing, accepted-cycle extraction, Doppler processing, feature extraction, and analysis.
