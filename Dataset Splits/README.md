# Dataset Splits

## Overview

This directory contains the dataset split lists and metadata prepared by **Member 2 – Data Preparation** for the Road Segmentation project.

The dataset is divided into three subsets using a reproducible random split:

- Training: 70%
- Validation: 15%
- Internal Testing: 15%

A fixed random seed (`random_state = 42`) is used to ensure that the same split can be reproduced.

## Dataset Statistics

The split was created from **6,226 labeled image-mask pairs**.

| Split | Number of Samples | Percentage |
|---|---:|---:|
| Training | 4,358 | 70% |
| Validation | 934 | 15% |
| Internal Testing | 934 | 15% |
| **Total** | **6,226** | **100%** |

## Files Description

| File | Description |
|---|---|
| `train.txt` | Contains the satellite image filenames assigned to the training set. |
| `validation.txt` | Contains the satellite image filenames assigned to the validation set. |
| `test.txt` | Contains the satellite image filenames assigned to the internal test set. |
| `manifest.csv` | Contains the split assignment, sample ID, image filename, and corresponding mask filename for every sample. |
| `split_summary.json` | Stores the split ratios, sample counts, random seed, and filename conventions. |

## Image-Mask Pairing

Each satellite image is paired with its corresponding road segmentation mask using the filename convention:

- Satellite images: `_sat.jpg`
- Ground-truth masks: `_mask.png`

For example:

```text
12345_sat.jpg
12345_mask.png
```

Each image and its corresponding mask are assigned to the same subset to prevent image-mask pair separation.

## Important Clarification About the Test Set

The `test.txt` file represents an **internal hold-out test set** created from the labeled training data.

These 934 samples have corresponding ground-truth masks and are reserved for internal model evaluation.

This internal test set is different from the original unlabeled test images provided separately with the dataset, which are reserved for final inference.

## Preprocessing Notes

- Image-mask dimensions are checked before including a pair in the split.
- Satellite images use the RGB format during preprocessing.
- Ground-truth masks are handled separately from satellite images.
- A threshold of 128 is specified for binary mask conversion.
- Images and masks are not resized or saved as augmented copies in this directory.

**Note:** The threshold value is preprocessing metadata; the original dataset masks are not modified by the split files.

## Usage

All team members should use the same split lists to ensure consistent training, validation, and evaluation.

The image filenames in each `.txt` file can be matched with their corresponding masks by replacing `_sat.jpg` with `_mask.png`.

The actual dataset files must be available locally or through the configured dataset input directory. This repository directory contains split information only, not the original image or mask files.

## Reproducibility

The dataset split was generated using:

```python
random_state = 42

train_ratio = 0.70
validation_ratio = 0.15
test_ratio = 0.15
```

The split lists should remain unchanged across team members and model experiments to ensure fair and consistent comparisons.
