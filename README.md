# Histopathologic Cancer Detection



This project tackles the \*\*Histopathologic Cancer Detection\*\* Kaggle competition, where the goal is to predict whether a small patch of tissue (image) contains metastatic cancer.



Competition: https://www.kaggle.com/competitions/histopathologic-cancer-detection



---



## 1. Problem Overview



Each sample is a 96x96 pixel histopathology image.  

The task is a \*\*binary classification\*\* problem:



- `label = 1` → image contains metastatic tissue  

- `label = 0` → image is normal



The goal is to build a model that can accurately classify these images and generate a submission file for Kaggle.



---



## 2. Data \& Preprocessing



- Training data: labeled image patches with `train\_labels.csv`

- Test data: unlabeled image patches used for final evaluation

- Key steps:

&nbsp; - Load images using a custom `Dataset` + `DataLoader`

&nbsp; - Apply torchvision transforms (normalization, augmentation, resize/crop as needed)

&nbsp; - Split training set into train/validation for offline evaluation



---



## 3. Model



- Framework: \*\*PyTorch\*\*

- Approach:

&nbsp; - Start from a pretrained CNN (e.g., ResNet)

&nbsp; - Replace the final layer with a binary classifier (single output with sigmoid)

&nbsp; - Train with:

&nbsp;   - Binary cross entropy loss / BCEWithLogitsLoss

&nbsp;   - Adam optimizer

&nbsp;   - Metrics: ROC AUC, accuracy, confusion matrix



---



## 4. Training \& Evaluation



The notebook includes:



- Training loop with epoch-wise logging

- Validation AUC and loss tracking

- Basic error analysis (e.g., confusion matrix, classification report)



---

