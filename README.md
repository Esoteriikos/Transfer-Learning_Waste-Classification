# Waste Classification Using Transfer Learning

## Overview

This project focuses on classifying different types of waste using deep learning and transfer learning techniques. The goal is to automate the process of waste sorting by leveraging pre-trained convolutional neural networks (CNNs) and fine-tuning them for the specific task of multi-class waste classification.

## Problem Statement

Manual waste sorting is time-consuming and error-prone. Automating this process can help improve recycling rates and reduce environmental impact. The dataset consists of images of waste items categorized into 9 classes, such as Cardboard, Food Organics, Glass, Metal, Miscellaneous Trash, Paper, Plastic, Textile Trash, and Vegetation.

## What I Did

- **Data Preparation:**  
  - Organized the dataset into class folders.
  - Scanned and listed all image files with their corresponding labels.
  - Split the data into training, validation, and test sets according to project requirements (80% train/val, 20% test, with 20% of train as validation).
  - Handled class imbalance using class weights.

- **Preprocessing:**  
  - Implemented image resizing and augmentation (random crop, flip, rotation, contrast, brightness, translation).
  - Used model-specific preprocessing functions for each pre-trained model.

- **Model Building:**  
  - Utilized transfer learning with four pre-trained models: ResNet50, ResNet101, EfficientNetB0, and VGG16.
  - Added custom classification heads to each model.
  - Compiled models with Adam optimizer and categorical cross-entropy loss.

- **Training & Evaluation:**  
  - Trained each model with early stopping, model checkpointing, and learning rate reduction on plateau.
  - Evaluated models on train, validation, and test sets.
  - Calculated metrics: accuracy, precision, recall, F1-score, and AUC.
  - Plotted training history and confusion matrices for each model.

- **Results & Analysis:**  
  - Compared all models and summarized their performance.
  - Identified EfficientNetB0 as the best-performing model based on F1-score, AUC, and accuracy.
  - Visualized sample predictions and analyzed misclassifications.

## What I Learned

- **Data Handling:**  
  - Importance of proper data splitting and stratification for robust evaluation.
  - Handling class imbalance using class weights instead of resampling.

- **Image Augmentation:**  
  - How augmentation techniques can help improve model generalization and robustness.

- **Transfer Learning:**  
  - How to leverage pre-trained CNNs for a new classification task.
  - Freezing base layers and training custom heads for efficient learning.

- **TensorFlow Data Pipelines:**  
  - Efficient data loading and preprocessing using `tf.data.Dataset` with parallelization and prefetching.

- **Model Evaluation:**  
  - How to interpret various metrics (accuracy, precision, recall, F1, AUC) for multi-class problems.
  - Visualizing confusion matrices to understand model strengths and weaknesses.

- **Experimentation:**  
  - Comparing different architectures and hyperparameters to select the best model.
  - The impact of batch size, regularization, and early stopping on training stability.

## How to Run

1. **Install Requirements:**  
   Install dependencies from [requirement.txt](requirement.txt).

2. **Prepare Data:**  
   Place the dataset in the correct folder structure as described above.

3. **Run Notebook:**  
   Open and execute all cells in [Notebook/Transfer-Learning.ipynb](Notebook/Transfer-Learning.ipynb).  
   - Edit the `DATASET_PATH` variable to your Data path.

4. **Results:**  
   The notebook will output training history, evaluation metrics, confusion matrices, and sample predictions.


## Conclusion

This project demonstrates the effectiveness of transfer learning for waste classification. By experimenting with multiple architectures and robust data pipelines, I achieved strong performance on a multi-class problem. The approach can be extended to other image classification tasks with similar data constraints.

---

*Author: Shubham Chaudhari*