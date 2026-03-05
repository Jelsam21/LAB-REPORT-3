# 📘 Emona Telecoms Trainer – Experiments 11–20

This repository contains summarized notes and outputs from experiments on digital transmission, PCM, bandwidth effects, and digital modulation techniques using the **Emona Telecoms Trainer**. Each experiment is explained in essay form for clarity and continuity.

---

## 📡 Experiment 11 – Sampling and Reconstruction
### 🎯 Objectives
The objective of this experiment is to become familiar with digital transmission and to understand the principles of Pulse Amplitude Modulation (PAM) and quantization.

### 📖 Introduction
Digital transmission involves converting analog signals into discrete-time signals through sampling. Natural sampling multiplies the analog signal with a pulse train, while sample-and-hold (S&H) maintains each sampled value constant until the next clock pulse. These techniques demonstrate how continuous signals can be represented in discrete form.

### 📊 Block Diagram Explanation
In natural sampling, a dual analog switch controlled by an 8 kHz clock allows a 2 kHz input signal to pass only during clock peaks. In S&H, the switch is replaced by a circuit that holds each amplitude until the next pulse, producing a staircase-like waveform. Both methods illustrate different approaches to sampling.

### 📈 Output Explanation
The output of natural sampling showed signals passing only during clock peaks, while S&H produced a stepped waveform. Applying a low-pass filter smoothed the steps, reconstructing the original message. Increasing the sampling frequency improved reconstruction quality and reduced aliasing.

---

## 🎛️ Experiment 12 – PCM Encoding
### 🎯 Objectives
The objective is to familiarize with PCM encoding, understand the principle of Pulse Code Modulation, and analyze PCM output for both 0V and variable DC input.

### 📖 Introduction
Pulse Code Modulation (PCM) converts analog signals into binary sequences using sampling, quantization, and encoding. The EMONA trainer simplifies this process with a 7-bit encoder, making it easier to observe the relationship between analog input and digital output.

### 📊 Block Diagram Explanation
The PCM encoder integrates sampling, quantization, and encoding into one block. The analog input and an 8 kHz clock serve as the sources, and frame synchronization ensures proper alignment of data frames.

### 📈 Output Explanation
The output revealed frame synchronization pulses marking the start of each data frame. PCM data varied according to input voltage, with higher DC inputs producing higher binary codes. At 0V, the output was not all zeros due to bipolar encoding and quantization levels, showing how PCM represents signals digitally.

---

## 🔄 Experiment 13 – PCM Decoding
### 🎯 Objectives
The objective is to understand PCM decoding, reconstruct signals, and compare the decoded output with the original input.

### 📖 Introduction
PCM decoding reconstructs analog signals from PCM data using synchronization and clock signals. Filtering plays a crucial role in smoothing the reconstructed waveform.

### 📊 Block Diagram Explanation
The decoder receives PCM data, clock, and frame synchronization signals. A low-pass filter is added to smooth the reconstructed signal, ensuring it closely resembles the original input.

### 📈 Output Explanation
Without filtering, the decoded signal appeared as discrete steps, reflecting quantization. With filtering, the waveform was smoothed and closely matched the original input, demonstrating the effectiveness of PCM decoding.

---

## 📶 Experiment 14 – Bandwidth Limiting
### 🎯 Objectives
The objective is to understand bandwidth limiting, observe its effects on digital transmission, and restore distorted signals using comparators.

### 📖 Introduction
Bandwidth limiting reduces high-frequency components, which can distort digital signals. Restoration techniques, such as comparators, can recover clean digital pulses from distorted signals.

### 📊 Block Diagram Explanation
PCM decoding was tested with and without a low-pass filter acting as a bandwidth limiter. The filter restricted high-frequency components, altering the signal’s shape.

### 📈 Output Explanation
Without filtering, the decoded signals varied smoothly. With filtering, distortion occurred, but comparators restored clean digital pulses. This experiment highlighted the impact of bandwidth on signal quality and recovery.

---

## 🔊 Experiment 15 – Amplitude Shift Keying (ASK)
### 🎯 Objectives
The objective is to understand ASK modulation, implement it, and restore digital signals into their original form.

### 📖 Introduction
Amplitude Shift Keying (ASK) encodes binary data by varying the amplitude of a carrier signal. It is one of the simplest digital modulation techniques.

### 📊 Block Diagram Explanation
A dual analog switch generates ASK using a carrier and digital input. An envelope detector demodulates the signal, and a comparator restores clean digital data.

### 📈 Output Explanation
The ASK waveform showed amplitude changes corresponding to binary 1s and 0s. The envelope detector extracted the binary pattern, and the comparator reconstructed the original digital signal, demonstrating ASK’s effectiveness.

---

## 📡 Experiment 16 – Frequency Shift Keying (FSK)
### 🎯 Objectives
The objective is to understand FSK modulation and implement an FSK modulator circuit.

### 📖 Introduction
Frequency Shift Keying (FSK) represents binary data by shifting the frequency of a carrier signal, with one frequency for logic 1 and another for logic 0.

### 📊 Block Diagram Explanation
A voltage-controlled oscillator (VCO) generates two frequencies based on digital input. A comparator restores the digital signal after modulation.

### 📈 Output Explanation
The output displayed frequency shifts corresponding to binary data. The restored signal matched the original input, showing FSK’s robustness compared to ASK.

---

## 🔄 Experiment 17 – Binary Phase Shift Keying (BPSK)
### 🎯 Objectives
The objective is to understand BPSK modulation, implement a BPSK modulator, and observe phase changes representing binary data.

### 📖 Introduction
BPSK encodes data by shifting the phase of a carrier signal, using 0° for logic 1 and 180° for logic 0. It is more efficient than ASK or FSK.

### 📊 Block Diagram Explanation
A balanced modulator multiplies the carrier sine wave with a bipolar digital signal, producing phase-reversed output.

### 📈 Output Explanation
The output waveform showed distinct phase reversals aligned with binary data, clearly demonstrating phase-based encoding.

---

## 🌀 Experiment 18 – Quadrature Phase Shift Keying (QPSK)
### 🎯 Objectives
The objective is to understand QPSK modulation, learn serial-to-parallel conversion, and implement a QPSK modulator.

### 📖 Introduction
QPSK transmits two bits per symbol using four phase states. The serial input data is split into even and odd streams, which modulate in-phase and quadrature carriers.

### 📊 Block Diagram Explanation
A serial-to-parallel converter separates the streams. The I channel modulates the cosine carrier, while the Q channel modulates the sine carrier. An adder combines both outputs, and product detectors with synchronized carriers recover the streams.

### 📈 Output Explanation
The QPSK waveform showed phase changes corresponding to two-bit symbols. Demodulation successfully reconstructed the even and odd streams, demonstrating QPSK’s efficiency.

---

## 🌐 Experiment 19 – Direct Sequence Spread Spectrum (DSSS)
### 🎯 Objectives
The objective is to understand DSSS modulation and implement a DSSS modulator using a PN sequence.

### 📖 Introduction
DSSS spreads digital data across a wide bandwidth using a pseudo-random noise (PN) sequence, making it resistant to interference and jamming.

### 📊 Block Diagram Explanation
Data is multiplied with a PN sequence to produce a spread signal, which modulates a carrier. At the receiver, the same PN sequence despreads the signal, collapsing it back to narrowband. A jammer can be added to test interference rejection.

### 📈 Output Explanation
Without jamming, the despread signal cleanly recovered the data. With jamming, DSSS suppressed interference by spreading its energy, especially with high processing gain, proving its robustness.

---

## 💻 Experiment 20 – Software Defined Radio (SDR)
### 🎯 Objectives
The objective is to understand SDR concepts and learn undersampling in SDR receivers.

### 📖 Introduction
SDR digitizes signals close to the antenna, shifting processing into software. Undersampling folds modulated signals into baseband, replacing traditional mixers.

### 📊 Block Diagram Explanation
A DSBSC signal is generated and undersampled. Controlled aliasing folds the signal into baseband, and a low-pass filter extracts the component. Replacing the fixed sampling clock with a VCO makes the system tunable.

### 📈 Output Explanation
Undersampling successfully demodulated the DSBSC signal into baseband. Using a VCO allowed dynamic tuning, showing SDR’s flexibility in handling different modulation schemes.

---
