# Circular Task Analysis

## 1. Project Overview

This project analyses mouse movements recorded during a circular steering task, using Python (NumPy, Matplotlib) and Quarto.

Based on Fauviaux et al. (2021), the objective is to understand the data recorded by MouseReMoCo, reproduce the required graphs, recalculate the movement statistics of the software, and validate the results on a new recording.

## 2. Assignment Objectives

- Understand the circular steering task and the structure of the MouseReMoCo data.
- Import and analyse the CSV data using NumPy (without Pandas).
- Reproduce the required graphs using Matplotlib.
- Recalculate and validate the statistics of the marker file.
- Record and analyse at least one new experiment using MouseReMoCo.
- Collaborate using Git branches, pull requests and peer reviews.
- Submit a one-page PDF documenting the group workflow and three critical problems and solutions.

## 3. Main Results

- The figures of the assignment were reproduced from the raw data.
- The 8 metrics of MouseReMoCo (`nLaps`, `Re`, `Te`, `error`, `MT/lap`, `IDe/lap`, `Be`, `IPe`) were recomputed and are **identical to the software for all 11 recordings** (5 in the provided dataset, 6 in our new recording).
- Main findings along the way: MouseReMoCo uses an angle-based error, keeps a sample recorded 4 ms before the start of a recording, and, from version 1.3.0, also saves the samples of the pauses, which requires a specific rule to select the samples of each recording (Section 5.3.1).

## 4. Project Structure

```text
circular-task-analysis
│
├── master.qmd                 # main report: combines the 7 sections
├── submission.qmd             # one-page PDF for Moodle
├── README.md
├── .gitignore
├── LICENSE
│
├── sections
│   ├── 01_introduction.qmd
│   ├── 02_data_exploration.qmd
│   ├── 03_data_visualisation.qmd
│   ├── 04_statistical_analysis.qmd
│   ├── 05_new_experiment.qmd
│   ├── 06_discussion.qmd
│   └── 07_references.qmd
│
├── data
│   ├── 001MoDe_R1.csv             # provided dataset (MouseReMoCo 1.2.0rc5)
│   ├── 001MoDe_R1.marker.csv
│   ├── 002SaDu_R1.csv             # new recording (MouseReMoCo 1.3.0)
│   └── 002SaDu_R1.marker.csv
│
└── figures                        # diagrams used in the report
    ├── circular_task_diagram.png
    ├── track_parameters.png
    ├── cursor_angle.png
    ├── arctan.png
    └── cursor_error.png
```

`master.qmd` contains the YAML configuration, the shared Python imports and the table of contents, and includes the seven sections in order. The sections share their variables, so they must be run in this order.

`submission.qmd` generates the separate one-page PDF required for Moodle.

## 5. How to Render the Report

Requirements:

- [Quarto](https://quarto.org/docs/download/) and a LaTeX distribution for the PDF (`quarto install tinytex`)
- Python 3 with `numpy`, `matplotlib`, `jupyter` and `pyyaml`

From the root of the repository:

```bash
quarto render master.qmd
```

To run the cells interactively in VS Code, set `"jupyter.notebookFileRoot": "${workspaceFolder}"` in the settings, so that the `data/...` paths are found, and run the sections in order (02 → 06).

## 6. Group Organisation

| Member | Assigned Quarto Documents |
|---|---|
| Jennifer Houmard (project manager) | 01 Introduction, 04 Statistical Analysis |
| Sarah Durand | 02 Data Exploration, 05 New Experiment |
| Alexis Lagarde | 03 Data Visualisation, 06 Discussion and Conclusion |
| All members | 07 References |

All members participate in testing, reviewing and validating the final analysis.

## 7. Git Branching Strategy

One branch is created for each Quarto document.

| Branch | Assigned Member |
|---|---|
| `01_introduction` | Jennifer Houmard |
| `02_data_exploration` | Sarah Durand |
| `03_data_visualisation` | Alexis Lagarde |
| `04_statistical_analysis` | Jennifer Houmard |
| `05_new_experiment` | Sarah Durand |
| `06_discussion` | Alexis Lagarde |
| `07_references` | All members |

### Workflow

1. Create each branch from the latest `main`.
2. Develop the assigned `.qmd` section.
3. Commit and push the changes to the corresponding branch.
4. Open a pull request into `main`.
5. The other members review the changes.
6. Only the project manager merges approved pull requests.

Direct pushes to `main` are avoided after the initial setup.

## 8. References

**Research poster:** Fauviaux et al. (2021). *Can a circular steering task quantify sensorimotor integration in persons with stroke?*
https://hal.science/hal-03834500

**MouseReMoCo software:**
https://github.com/DenisMot/MouseReMoCo
(release notes of version 1.3.0: https://github.com/DenisMot/mouseReMoCo/releases/tag/v1.3.0-release)
