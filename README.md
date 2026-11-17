# Road Segmentation from Satellite Images Using Deep Learning

Deep Learning course group project using the DeepGlobe Road Extraction Dataset.

## Project Aim

Train a U-Net model to identify road pixels in satellite images and investigate
whether data augmentation improves segmentation performance.

## Dataset

DeepGlobe Road Extraction Dataset:
https://www.kaggle.com/datasets/balraj98/deepglobe-road-extraction-dataset

The full dataset is accessed through Kaggle and is not uploaded here.

## Team Responsibilities

- Member 1: Paired image-and-mask augmentation and visual verification.
- Member 2: Dataset inspection, preprocessing, and shared data splits.
- Member 3: Baseline U-Net training without augmentation.
- Member 4: U-Net training with augmentation.
- Member 5: Evaluation, comparisons, and error analysis.

## Notebook Order

1. 01_data_preparation.ipynb
2. 02_data_augmentation.ipynb
3. 03_baseline_unet.ipynb
4. 04_augmented_unet.ipynb
5. 05_evaluation.ipynb

Notebooks will be added as each stage is completed.

## Current Progress

The augmentation demonstration is available. It includes paired flips and
rotations, mask checks, and visual alignment examples. No model is trained
in this notebook.

## How to Run

1. Download the required notebook from this repository.
2. Open or upload it in Kaggle.
3. Attach the DeepGlobe Road Extraction Dataset.
4. Run the cells in order.

## Shared Experiment Rules

- Use the same final training, validation, and test splits.
- Split original images before generating patches.
- Apply augmentation only to training images and their matching masks.
- Keep validation and test data unchanged.
- Keep other training settings consistent for the augmentation comparison.
- Document dependencies, settings, and output locations.

## Repository Contents

- notebooks/: implementation notebooks.
- data/: dataset instructions and shared split lists.
- results/: selected figures and evaluation results.
- report/: final research paper.
