# Stateflow Exercises

This folder contains three Simulink models that use **Stateflow charts** to represent event-driven and time-based behavior.

## Models

### 1. `Es_stateflow.slx` — Timed ON/OFF State Machine

This model implements a simple two-state machine:

- **OFF**: sets the output `button` to `0` on state entry.
- **ON**: sets the output `button` to `1` on state entry.

The transition between the two states is controlled by the temporal condition `after(5, sec)`. The chart therefore demonstrates how Stateflow can use elapsed time to trigger state transitions and update an output.

### 2. `Es2_stateflow.slx` — Timed Alarm State Machine

This model contains two states that control the output `alarm`:

- **DISACTIVATE**: sets `alarm = 0` on entry.
- **ACTIVATE**: sets `alarm = 1` on entry.

The transitions use temporal conditions `after(1, sec)` and `after(5, sec)`, demonstrating state changes driven by different time delays.

### 3. `Es3_stateflow.slx` — Age Tracking and Adult Check

This model represents a simple age progression:

- **Birth**: initializes `age` to `0` on entry.
- **Growth**: increments `age` by `1` during each execution of the state.
- **Response**: evaluates the age using the chart function `CheckIfAdult(age)`.

The chart function checks whether the supplied age is at least 18 and returns one of two messages:
- `You're an adult now`
- `You're not an adult yet`

A transition condition `after(3, tick)` is used in the chart to control progression from the growth stage. The model illustrates state actions, temporal transitions, local data, and a reusable Stateflow function.

## Repository Structure

```text
Stateflow/
├── Es_stateflow.slx
├── Es2_stateflow.slx
└── Es3_stateflow.slx
```

## Requirements

- MATLAB
- Simulink
- Stateflow

The models are provided as `.slx` files and should be opened with a compatible MATLAB installation.

## How to Run

1. Open MATLAB.
2. Set the current folder to this directory, or add it to the MATLAB path.
3. Open the desired `.slx` model.
4. Inspect the Stateflow chart and the connected Simulink blocks.
5. Run the model using **Run** in the Simulink toolstrip.

## Notes

- The descriptions above are based on the contents of the three supplied Simulink/Stateflow models.
- No separate assignment text, explanatory report, or additional MATLAB source files were included in the archive.
- Simulation results may depend on the model configuration and solver settings in the installed MATLAB version.
