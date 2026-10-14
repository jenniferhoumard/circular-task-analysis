
# Circular Task Analysis

## 1. Project Overview

This project analyses mouse movements recorded during a circular steering task using Python, NumPy, Matplotlib, and Quarto.

Based on Fauviaux et al. (2021), the objective is to understand the MouseReMoCo data, reproduce the required graphs, recalculate movement statistics, and validate the results.

## 2. Assignment Objectives

- Understand the circular steering task and MouseReMoCo data structure.
- Import and analyse CSV data using NumPy (without Pandas).
- Reproduce the required graphs using Matplotlib.
- Recalculate and validate statistics from the marker file.
- Record and analyse at least one new experiment using MouseReMoCo.
- Collaborate using Git branches, pull requests, and peer reviews.
- Submit a one-page PDF documenting the group workflow and three critical problems and solutions.

## 3. Project Structure

```text
circular-task-analysis
│
├── master.qmd
├── submission.qmd
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
└── data
    ├── 001MoDe_R1.csv
    └── 001MoDe_R1.marker.csv
```

The `master.qmd` combines all seven sections and contains the YAML configuration, shared Python imports, and table of contents.

The `submission.qmd` generates the separate one-page PDF required for Moodle.

## 4. Group Organisation

| Member | Assigned Quarto Documents |
|---|---|
| Jennifer Houmard | xxxxxxx |
| Alexis Lagarde | xxxxxxxxxx|
| Sarah Durand | xxxxxxxxxxx |

All members participate in testing, reviewing, and validating the final analysis.

## 5. Git Branching Strategy

One branch is created for each Quarto document.

| Branch | Assigned Member |
|---|---|
| `01-introduction` | xx |
| `02-data-exploration` | xx |
| `03-visualisation` | xx |
| `04-statistical-analysis` | xx |
| `05-new-experiment` | xx |
| `06-discussion` | xx |
| `07-references` | xx |

### Workflow

1. Create each branch from the latest `main`.
2. Develop the assigned `.qmd` section.
3. Commit and push changes to the corresponding branch.
4. Open a pull request into `main`.
5. Another member reviews the changes.
6. Only the project manager merges approved pull requests.

Direct pushes to `main` are avoided after the initial setup.

## 6. References

**Research Poster:** Fauviaux et al. (2021). *Can a circular steering task quantify sensorimotor integration in persons with stroke?*

https://hal.science/hal-03834500

**MouseReMoCo Software:**

https://github.com/DenisMot/MouseReMoCo