# Alarm Clock — Fitts’ Law Experiment

## Live Website

**[Open the interactive experiment on GitHub Pages](https://yenyunliu.github.io/alarm-fitts-experiment/)**

**Course:** Human–Computer Interaction — Assignment 1, Part II

## Project Overview

This AI-assisted web experiment investigates how target distance and button width affect pointing and selection time in a simulated alarm clock interface. Participants use a desktop mouse to select the instructed **Snooze** or **Stop** button while the target distance and size vary systematically.

## Step 4. Report

### Scenario

The experiment simulates a morning smartphone alarm interface with two buttons: **Snooze** and **Stop**. When an alarm rings, a user must identify and select the intended action quickly and accurately. The experiment examines how the distance to the target (**A**) and its width (**W**) relate to the time required to select it.

### Innovation

Unlike conventional Fitts’ Law tasks that present a single abstract target, this experiment uses two recognizable alarm controls displayed simultaneously. Each trial specifies which button to select, while the other remains visible as a distractor. Target distance and width are systematically varied across **60 trials**, combining a familiar interaction scenario with controlled pointing conditions.

### Application and Design Motivation

I chose an alarm clock because it represents a familiar everyday interaction where quick and accurate selection matters. Small buttons or inconvenient placement can make it harder to choose the intended action and may increase accidental selections.

The real-world HCI problem explored here is **how button size and placement affect the efficiency and accuracy of selecting time-sensitive interface controls**. The findings may inform more usable alarm interfaces and other interfaces with frequently used action buttons. However, because this experiment uses a desktop mouse, its results should not be treated as direct evidence about smartphone touch interaction or users who have just awakened.

### Custom Fitts’ Law Formula

Using the Shannon formulation:

\[
ID = \log_2\left(1+\frac{A}{W}\right)
\]

\[
MT = a + b\log_2\left(1+\frac{A}{W}\right)
\]

Linear regression of the **60 recorded trials** produced:

- **Intercept (a):** 506.060 ms
- **Slope (b):** 140.445 ms/bit
- **Coefficient of determination (R²):** 0.3814

Therefore, the **empirically derived Fitts’ Law equation** is:

\[
\boxed{MT\; (\mathrm{ms}) = 506.060 + 140.445\log_2\left(1+\frac{A}{W}\right)}
\]

Here, **MT** is measured selection time in milliseconds; **A** is the center-to-center target distance in CSS pixels; **W** is the target width in CSS pixels; and **ID** is measured in bits.

### Results and Interpretation

The positive regression slope indicates that selection time generally increased with the Index of Difficulty, consistent with the direction predicted by Fitts’ Law. The **R² of 0.3814** means that ID explained approximately **38.14%** of the observed variation in selection time in this dataset.

The fit is moderate rather than strong. This may reflect additional time for visual recognition and choosing between the two buttons, as well as individual trial variability. The results suggest that distance and size matter, but they do not fully explain performance in this dual-button task.

## Experimental Method

- **Target widths (W):** 40, 60, 80 CSS px
- **Target distances (A):** 120, 200, 280, 360 CSS px
- **Repetitions:** 5 per A/W combination, giving **60 successful trials** in total
- **Target balance:** 30 Snooze and 30 Stop trials
- **Input device:** Desktop mouse; browser zoom at 100%
- **Procedure:** Click **Begin / Restart Session**, click **START** once, and continuously select the instructed button without returning to START between trials
- **Timing:** Each trial runs from the previous correct click (or initial START click) to the next correct click. Time for recognizing the target and any incorrect attempts is included
- **Data:** Exported CSV records the trial number, target, `A_px`, `W_px`, `ID_bits`, `MT_ms`, and error count

## Fitts’ Law and Results

The experiment plots **Movement/Selection Time (MT)** against the **Index of Difficulty (ID)**, with a least-squares regression line and R². The published website can load `results.csv` to display the recorded dataset and fitted coefficients.

**Final fitted equation:** `MT = 506.060 + 140.445 × log₂(1 + A/W)` (MT in ms).

The recorded trial data are available in [`results.csv`](results.csv).

## Experiment Recording

[Watch the experiment recording on YouTube](https://youtu.be/vjmu-BSm7yE). The recording is also embedded in the interactive website.

## Discussion and Limitations

Both Snooze and Stop remain visible during each trial, requiring participants to identify the instructed control before clicking. Consequently, the measured time can include visual attention, target recognition, decision-making, and motor movement—not just isolated movement time. These additional components may affect the fitted intercept, slope, and R².

The experiment uses a mouse in a desktop browser rather than direct finger touch on a phone. Differences in pointing precision, finger occlusion, hand posture, and screen size mean the results cannot be generalized directly to touchscreen interaction. The simulated interface also does not measure behavior immediately after waking up.

## Run Locally

1. Open `index.html` in a desktop browser at **100% zoom**.
2. Click **Begin / Restart Session** and then **START** once.
3. Complete all **60 trials**, selecting the instructed Snooze or Stop button.
4. Export the CSV and review the scatter plot, regression line, coefficients, and R².
5. For the published results, keep `results.csv` alongside `index.html` in the GitHub repository.
