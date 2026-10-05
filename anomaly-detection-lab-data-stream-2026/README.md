# Spark lab: monitoring API latency with MLlib

A 90-minute practical for the Data Stream course. We parse raw API latency
reports with Spark DataFrames, flag anomalies with K-Means, and predict the next
minute's latency with linear regression and a random forest.

Everything runs on your laptop with **two Spark worker threads** (`local[2]`).
No external services are needed.

## Before the practical

Complete these steps **before class**.

### 1. The environment

This lab uses **the same environment as the previous Spark lab**
(`data-stream-spark`). If you already created it, there is nothing to install:
from this directory, activate it and check it.

```bash
conda activate data-stream-spark
python check_environment.py
```

Otherwise, install Miniforge as in the previous lab, then from this directory:

```bash
conda env create -f environment.yml
conda activate data-stream-spark
python check_environment.py
```

In both cases, wait for **Environment ready.** On Windows, use **Miniforge
Prompt** for every command.

### 2. The data

Download `api_latency_data.parquet` (336 MB) from
[this Proton Drive folder](https://drive.proton.me/urls/HD0DQBCFHR#JWzAUUkExXg7)
and place it in `data/`, so that its path is `data/api_latency_data.parquet`.

## Starting the lab

From the repository directory:

```bash
conda activate data-stream-spark
jupyter lab
```

Open **`lab.ipynb`** and choose **Python 3 (ipykernel)**. Run the cells in order.
**Given** cells provide boilerplate. **TODO** cells are executable starting
points: their provisional values and missing analyses are intentional; follow
the nearby instructions to complete them. Running every starter cell is safe,
but does not mean you have answered every exercise.

Use one notebook kernel at a time to keep laptop memory usage modest.

| Topic | Minutes |
| --- | ---: |
| Setup and data exploration | 16 |
| Anomaly detection with clustering | 31 |
| Latency prediction with regression | 35 |
| Buffer | 8 |

Your deliverables are written to `artifacts/`: submit them with your notebook.

## Troubleshooting

- **Environment not activated / wrong Python:** run `conda activate
  data-stream-spark`, then `python check_environment.py` in the same terminal.
- **Jupyter uses another environment:** stop Jupyter, activate this environment
  and launch `jupyter lab` again. The setup cell prints its interpreter path.
- **The data file is not found:** check that it is saved as
  `data/api_latency_data.parquet` inside this directory, not in your downloads.
- **Java heap space / out of memory:** restart the kernel, close other notebook
  kernels, and run the cells from the top.

Failed checks point to `validation-results/environment-spark.log`. Send it to
your instructor if you need help.
