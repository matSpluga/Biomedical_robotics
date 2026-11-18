# Simulink Exercises

## Overview

This folder contains five MATLAB Simulink models (`Es1_simulink.slx` to `Es5_simulink.slx`). The models cover introductory signal generation, signal processing, basic mathematical operations, and the use of MATLAB Function blocks within Simulink.

The descriptions below are based on the blocks and subsystem structures stored in the supplied `.slx` files.

## Models

### Es1 – Basic Signal Operations

**File:** `Es1_simulink.slx`

The model contains:
- A sine-wave signal source (`Segnale`).
- A modulo/absolute-value processing block (`Modulo`).
- A Scope (`Output`) to visualize the resulting signal.

It provides a simple example of generating a signal, processing it with a mathematical operation and observing the output.

### Es2 – Signal with Noise and Low-Pass Filtering

**File:** `Es2_simulink.slx`

The top-level model includes:
- A sinusoidal reference signal (`Signal`).
- A noise source (`Noise`).
- A summation block (`Add`) combining the signal and noise.
- A low-pass filter subsystem.
- A Scope for observing the signals.

The low-pass filter subsystem receives the noisy signal and implements a discrete filter structure containing two gains (both set to `1/2`), a summation block and a Unit Delay. Its output is exposed as `Filtered Signal`.

This model illustrates the effect of adding noise to a signal and filtering the resulting measurement.

### Es3 – Ramp, Threshold Comparison and Signal Monitoring

**File:** `Es3_simulink.slx`

The model contains:
- A Ramp reference signal.
- A Constant block with value `3`.
- A comparison-to-zero reference block.
- A Sum block configured for subtraction.
- A square-root block.
- Two Scopes for signal visualization.

The model combines reference signals and basic mathematical/logic operations. The Scopes allow the intermediate and resulting signals to be inspected during simulation.

### Es4 – MATLAB Function Block with Ramp and Step Inputs

**File:** `Es4_simulink.slx`

The top-level model provides:
- A Ramp source.
- A Step source.
- Two Constant blocks whose values are supplied through the workspace variables `const_expr1` and `const_expr2`.
- Separate Gain blocks controlled by `ramp_gain` and `step_gain`.
- A MATLAB Function subsystem.
- A Scope to display the result.

Inside the MATLAB Function subsystem, the inputs are named `ramp`, `step`, `const1` and `const2`. The subsystem uses a Demux and an S-Function associated with the MATLAB Function implementation, and exposes an output named `result`.

The model demonstrates how different input signals and workspace parameters can be passed into a MATLAB Function block and how its result can be monitored.

### Es5 – MATLAB Function Block with Sinusoidal Inputs

**File:** `Es5_simulink.slx`

The top-level model contains:
- Two sine-wave sources (`Sin1` and `Sin2`).
- A MATLAB Function subsystem.
- A comparison-to-constant reference block.
- Two Scopes for observing signals.

The MATLAB Function subsystem receives inputs named `sine` and `cosine` and exposes an output named `y`. This model provides an example of processing two periodic inputs through a MATLAB Function block and examining the output.

## Repository Structure

```text
Simulink/
├── Es1_simulink.slx
├── Es2_simulink.slx
├── Es3_simulink.slx
├── Es4_simulink.slx
└── Es5_simulink.slx
```

## Requirements

- MATLAB.
- Simulink.
- For models containing MATLAB Function blocks, a MATLAB/Simulink installation that supports MATLAB Function block execution.

Some model blocks use workspace variables. In particular, `Es4_simulink.slx` references:

- `const_expr1`
- `const_expr2`
- `ramp_gain`
- `step_gain`

Define these variables in the MATLAB base workspace before running Es4, if they are not already defined by an accompanying script or model initialization callback.

## How to Run

1. Extract the project folder.
2. Open MATLAB and navigate to the `Simulink/` directory.
3. Open the desired `.slx` file.
4. Check whether the model requires workspace variables or other initialization data.
5. Press **Run** in Simulink.
6. Open the Scope blocks to inspect the simulation signals.

## Notes

- The archive contains the five Simulink model files only; no separate assignment specification, report or initialization script is included.
- The exact mathematical expression implemented inside the MATLAB Function blocks is not described here because it is stored in the model's internal function implementation and is not exposed as a standalone MATLAB source file in the archive.
- The names above describe the model structure and visible block configuration; consult the original assignment instructions, if available, for the intended exercises and expected results.
