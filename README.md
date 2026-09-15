# Cervical Spine Fracture Detection Using Computer Vision

A deep learning and computer vision pipeline designed to automate the detection and localization of cervical spine fractures in CT scan images. Developed as a capstone project for the Master of Science in Applied Artificial Intelligence program at the University of San Diego (USD).

## 🚀 Project Overview
Cervical spine fractures are subtle, high-risk injuries where delayed or missed diagnosis can result in severe neurological complications. This project evaluates and benchmarks multiple architectures—ranging from a baseline CNN to advanced object detectors like **Faster R-CNN** and **DETR (DEtection TRansformer)**—to improve clinical diagnostic support and localization accuracy.

## 📺 Presentation
Feel free to checkout our [presentation](https://www.youtube.com/watch?v=rmchW63IFFU) walking through the project!

## 📊 Dataset & Setup
* **Source:** A curated subset of 28,868 CT scan slices from the RSNA 2022 Cervical Spine Fracture Detection dataset via the Kaggle API.
* **Kaggle Authentication:** To run the data ingestion notebooks, you will need a Kaggle API key. Follow the instructions in the [Kaggle Setup Guide]() to configure your kaggle.json credentials.
* Navigate to [Kaggle](https://www.kaggle.com/) and click "+ Create" on the left-hand side, then select "Notebook".
* There, you can import [**this notebook**](00_CreatePrivateDataset.ipynb) to get started. This notebook will walk you through step-by-step to create your own private Kaggle dataset.

## ⚠️ Preprocessing & Solutions
* **Image Normalization:** Resized images to (256 x 256) and normalized pixel intensities to [0, 1].
* **High Class Imbalance:** Mitigated severe imbalances between fractured and non-fractured CT slices via targeted undersampling (achieving a 1:3 positive-to-negative target ratio) and stratified group splitting.
* **Subtle Fracture Features:** Designed pipelines to capture fine-grained medical anomalies requiring high model sensitivity across complex anatomical structures.
* **Bounding-Box Formatting Alignment:** Addressed strict data structural requirements to ensure proper coordinate alignment for Faster R-CNN object detection.
* **Overfitting Mitigation:** Implemented regularization and frozen early backbone layers to stabilize high-capacity transformer models like DETR.
* **Clinical Interpretability:** Focused on localization-driven outputs (bounding boxes) rather than generic binary classification to deliver clinically meaningful detection results.
* **Exploratory Data Analysis:** Explore data distributions, pixel normalization checks, and bounding-box consistency in [EDA notebook](01_ExploratoryDataAnalysis.ipynb).

## 🛠️ Models Implemented
Each model was trained, validated, and tested on the same curated dataset, with steps including threshold tuning, early stopping, and bounding-box visualization.
* **[Baseline CNN](02_SimpleCNN.ipynb):** Custom binary classifier establishing foundational performance metrics.
* **[Faster R-CNN](04_Faster_R_CNN.ipynb):** Two-stage object detector featuring a ResNet-50 + FPN backbone optimized for small-object medical features.
* **[DETR](03_DETR.ipynb):** End-to-end transformer-based detection model fine-tuned with frozen early backbone layers for stability.

## 🖼️ Sample Fracture Prediction
<img width="908" height="435" alt="image" src="https://github.com/user-attachments/assets/d19cc1c5-2158-459e-9b75-6301d5b29bf3" />

## 💻 Tech Stack
* **Language:** Python
* **Deep Learning Frameworks:** PyTorch, TorchVision, Hugging Face Transformers
* **Data Science & Analytics:** NumPy, Pandas, Scikit-learn, Matplotlib, Seaborn
* **Environment:** Kaggle Notebooks, GPU Acceleration via CUDA

## 📂 Project Structure
* `00_CreatePrivateDataset.ipynb`: Pipeline script leveraging the Kaggle API to curate and structure the private subset.
* `01_ExploratoryDataAnalysis.ipynb`: Data distribution, bounding-box consistency, and pixel normalization audits.
* `02_SimpleCNN.ipynb`, `03_DETR.ipynb`, `04_Faster_R_CNN.ipynb`: Model training, threshold tuning, and evaluation notebooks.

## 👥 Contributors
* Andy Malinsky
* Devin Eror
* Christopher Alleyne

## 🏫 Acknowledgments
We thank our instructors at the University of San Diego’s Shiley-Marcos School of Engineering for their support and guidance. Additional thanks to Professor Anna Marbut, M.S., for direction throughout this capstone project.

## 📜 License
Distributed under the MIT License. See `LICENSE` for more information.
