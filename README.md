# IMU Filtering: Pendulum and Free Fall

This repository contains the final report, notebooks, and small datasets for IMU-based pendulum and free-fall filtering experiments. The notebooks cover synthetic pendulum EKF and Madgwick filtering, synthetic free-fall Kalman filtering, and real free-fall IMU measurements.

## Repository structure

```text
.
├── data/
│   ├── raw/
│   │   └── imu_drop_v3.csv
│   └── synthetic/
│       └── synthetic_data_pendulum_seed*.npz
├── docs/
│   ├── MCM_Project_IMU.pdf
│   └── original_README.txt
├── notebooks/
│   ├── FreeFall_StandardKF_5Trials.ipynb
│   ├── Pendulum_EKF_5Trials.ipynb
│   ├── Pendulum_EKF_Synthetic_Data.ipynb
│   ├── Pendulum_Madgwick_1Trial.ipynb
│   └── RealLife_FreeFall.ipynb
├── src/
│   └── README.md
├── .gitignore
├── README.md
└── requirements.txt
```

## Setup

Create and activate a Python environment, then install dependencies:

```bash
pip install -r requirements.txt
```

## Report

The final project report is included at `docs/MCM_Project_IMU.pdf`.

## Recommended run order

1. `notebooks/Pendulum_EKF_Synthetic_Data.ipynb`
   - Generates five synthetic pendulum IMU datasets in `data/synthetic/`.
2. `notebooks/Pendulum_EKF_5Trials.ipynb`
   - Applies and compares the augmented 12-D EKF and non-augmented 6-D EKF on the synthetic pendulum trials.
3. `notebooks/Pendulum_Madgwick_1Trial.ipynb`
   - Applies the Madgwick filter to one synthetic pendulum trial.
4. `notebooks/FreeFall_StandardKF_5Trials.ipynb`
   - Generates synthetic free-fall trials and applies the standard Kalman filter.
5. `notebooks/RealLife_FreeFall.ipynb`
   - Loads `data/raw/imu_drop_v3.csv` and visualizes Kalman filter results on real IMU measurements.

## Data

The included data files are small enough to be tracked directly in Git:

- `data/synthetic/synthetic_data_pendulum_seed*.npz`
- `data/raw/imu_drop_v3.csv`

If future datasets become large, place them outside Git tracking and document download or generation steps here.
