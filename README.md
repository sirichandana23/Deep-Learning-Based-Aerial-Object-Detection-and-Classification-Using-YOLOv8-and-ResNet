# Aerial Object Detection and Classification

Deep-learning workflows for detecting aerial objects with YOLOv8 and classifying drone models with PyTorch image classifiers.

## Project structure

```text
.
|-- .github/workflows/       # GitHub Actions checks
|-- configs/                 # Dataset configuration files
|-- data/                    # Local datasets (ignored by Git)
|-- notebooks/               # Detection and classification notebooks
|-- models/                  # Local model weights (ignored by Git)
|-- requirements.txt
`-- README.md
```

## Dataset layout

The local workspace is arranged as follows:

```text
data/
|-- detection/AOD_4/
|   |-- images/{train,val}/
|   `-- labels/{train,val}/
`-- classification/
    |-- train/{dji_inspire,dji_mavic,dji_phantom,no_drone}/
    `-- val/{dji_inspire,dji_mavic,dji_phantom,no_drone}/
```

Datasets, trained weights, and experiment outputs are excluded from Git because they are large. Anyone cloning the repository should reproduce this layout before running the notebooks.

## Setup

Python 3.10 or newer is recommended.

```bash
python -m venv .venv
# Activate the environment, then:
python -m pip install --upgrade pip
pip install -r requirements.txt
jupyter lab
```

Run notebooks from the repository root. The original work was developed in Google Colab and may contain Colab-specific paths; replace those with `data/detection/AOD_4` or `data/classification` for local runs.

## Workflows

- **Detection:** use `notebooks/aerial_object_detection_yolov8.ipynb` with `configs/aod4.yaml`.
- **Classification:** use `notebooks/drone_classification.ipynb` with `data/classification`.

## Contributing

Do not commit datasets, model weights, credentials, or generated runs. Keep reusable configuration in `configs/`, and clear unnecessary notebook output before commits when it contains large logs or local paths.
