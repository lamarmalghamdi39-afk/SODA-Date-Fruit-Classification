# 🌴 SODA Challenge: Date Fruit Image Classification

## 📌 Project Overview
A comprehensive Computer Vision project focused on classifying 13 different types of date fruits from images. The goal is to build an automatic system that can distinguish between visually similar date varieties, a task that is difficult and time-consuming to perform manually. The project compares classical machine learning models with deep learning approaches.

## 🛠️ Tech Stack
- **Language:** Python
- **Deep Learning:** TensorFlow, Keras (ResNet50)
- **Machine Learning:** Scikit-learn (Random Forest), XGBoost
- **Image Processing:** OpenCV
- **Data Handling:** NumPy, Pandas
- **Visualization:** Matplotlib, Seaborn
- **Environment:** Kaggle Notebook (GPU T4)

## ⚙️ Key Steps & Methodology
1.  **Data Preprocessing:** Images were resized to 224x224, converted from BGR to RGB, and normalized to [0,1]. Labels were adjusted from 1-13 to 0-12 for compatibility with the model's loss function.
2.  **Feature Extraction:** A pretrained ResNet50 model (ImageNet weights) was used to extract 2048-dimensional feature vectors from each image. These features were used to train the classical models.
3.  **Model Implementation:**
    *   **Random Forest:** Trained on the 2048-dim extracted features.
    *   **XGBoost:** An advanced ensemble model, also trained on the extracted features.
    *   **ResNet50 Transfer Learning:** The core deep learning model. The pretrained convolutional layers were frozen, and new classification layers (GlobalAveragePooling, Dense, Dropout) were added and trained.
4.  **Data Augmentation:** Random rotations, zooming, horizontal flips, and shifts were applied during the training of the ResNet50 model to improve generalization and reduce overfitting.
5.  **Evaluation Strategy:** The dataset was split into an 80/20 training/validation set using stratified sampling. Performance was evaluated using **Accuracy**, **Classification Report**, and **Confusion Matrix**.

## 📊 Key Results & Insights
- **Model Performance Comparison:**
    - **ResNet50 Transfer Learning:** 56.28% Validation Accuracy
    - **XGBoost:** 50.00% Validation Accuracy
    - **Random Forest:** 46.99% Validation Accuracy
- **Insight:** The ResNet50 Transfer Learning model outperformed the classical models. This is because it can fine-tune the learned visual features specifically for the date fruit dataset, whereas RF and XGBoost rely on fixed, generic ImageNet features.
- **Challenge:** The relatively low overall accuracy is attributed to the small dataset size (1,829 training images) and the high visual similarity between some date fruit classes. This highlights the difficulty of the task and the need for more data or advanced augmentation techniques.

## 📂 Repository Contents
- `SODA_Challenge_Code.ipynb`: The full Python code covering data preprocessing, feature extraction, model training, and evaluation.
- `SODA_Challenge_Report.pdf`: The detailed project report with full analysis and discussion.# SODA-Date-Fruit-Classification
