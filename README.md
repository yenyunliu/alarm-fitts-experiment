# Alarm Clock — Fitts’ Law Experiment

## Live Website

`https://yenyunliu.github.io/alarm-fitts-experiment/`


## Project Overview

**Course:** Human–Computer Interaction — Assignment 1, Part II

**Scenario:** This project simulates a morning alarm interface with two buttons, Snooze and Stop. The participant selects the instructed control as quickly and accurately as possible.

**Innovation:** Unlike a conventional single-target Fitts’ Law task, this experiment presents a familiar two-button alarm interface while systematically varying target distance and width. The other button remains visible as a distractor.

**Application:** The study explores how button size and placement relate to pointing efficiency and selection errors in an everyday interface. The experiment uses a desktop mouse; results do not directly measure touchscreen interaction or behavior immediately after waking.

## Experimental Method

- Target widths (W): **40, 60, 80 CSS px**
- Target distances (A): **120, 200, 280, 360 CSS px**
- Repetitions: **5 per A/W combination**, **60 successful trials total**
- Snooze / Stop: **30 trials each**
- One initial START click; then continuous target selection
- Each trial measures elapsed time from the preceding correct click to the next correct click, including recognition and possible errors
- Data export: `A_px`, `W_px`, `ID_bits`, `MT_ms`, target, and error count

## Fitts’ Law and Results

Shannon formulation:

`ID = log2(1 + A/W)`

`MT = a + b × log2(1 + A/W)`

The live page calculates **a**, **b**, and **R²** from recorded trials and plots movement/selection time against index of difficulty. **Actual coefficients must come from the completed experiment; no results have been assumed.**

## Experiment Recording

The recording will then be embedded in the live page.

## Discussion and Limitations

The simultaneous Snooze and Stop buttons may introduce visual attention, target recognition, and decision-making time beyond motor movement. These factors may affect the fitted parameters and R². The task uses mouse input, so the findings cannot be directly generalized to finger touch or actual waking-up conditions. 

## Run Locally

Open `index.html` in a desktop browser at 100% zoom. Click **Begin / Restart Session**, click START once, and continue until 60 trials are complete. Export the CSV. For a hosted version, publish with GitHub Pages.


