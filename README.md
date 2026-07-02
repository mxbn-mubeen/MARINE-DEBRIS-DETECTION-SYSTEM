# 🌊 Marine Debris Detection System

A deep learning-based image classification system that detects marine debris (plastic waste and pollutants) in ocean imagery using Convolutional Neural Networks (CNN), Random Forest, and hybrid ML approaches — built and trained on Google Colab.

---

## 📁 Project Structure

```
MARINE-DEBRIS-DETECTION-SYSTEM/
├── README.md
├── notebooks/
│   └── Marine_Debris_Detection.ipynb   # Main notebook (all code)
├── reports/
│   ├── Batch-1_Report_(FINAL).docx
│   └── Batch-1_Report_(FINAL).pdf
├── presentations/
│   ├── Batch - 01.pdf
│   └── Batch - 01.pptx
└── poster/
    ├── POSTER.pdf
    └── POSTER.pptx
```

---

## 🧠 How It Works

The system classifies images into two categories:
- ✅ **With Debris** — ocean images containing plastic/marine waste
- ❌ **Without Debris** — clean ocean images

### Pipeline Overview

```
Raw Images
    ↓
Data Splitting (train / test / validate)
    ↓
Image Augmentation (imgaug)
    ↓
Model Training (CNN / Random Forest / Hybrid)
    ↓
Evaluation (Accuracy, F1 Score, Confusion Matrix)
    ↓
Object Identification (Clarifai API)
    ↓
Interactive App (Voila / Streamlit)
```

### Models Implemented

| Model | Description |
|---|---|
| **Simple CNN** | Custom Convolutional Neural Network trained on augmented images |
| **Random Forest** | Classical ML classifier using image features |
| **CNN + Random Forest** | CNN used as feature extractor, Random Forest as classifier |
| **CNN + UMAP** | Dimensionality reduction with UMAP before classification |
| **Clarifai API** | Pre-trained object detection for debris identification in images |

---

## ⚙️ How to Run

### Prerequisites

This project runs on **Google Colab** and requires a Google Drive dataset.

**Required Libraries** (auto-installed in notebook):
```
tensorflow
scikit-learn
opencv-python (cv2)
imgaug
umap-learn
clarifai
streamlit
voila
matplotlib
tqdm
```

### Step-by-Step

**1. Open the Notebook**

Upload or open `notebooks/Marine_Debris_Detection.ipynb` in [Google Colab](https://colab.research.google.com/).

**2. Mount Google Drive**

```python
from google.colab import drive
drive.mount("/content/drive", force_remount=True)
```

**3. Set Up Dataset**

Download the dataset from Google Drive and place it in your Drive:

📂 **[Dataset – Google Drive Link](https://drive.google.com/drive/folders/1_zXqFG5J3rW07aRHf-NclbIePtdtbzOP?usp=drive_link)**

Expected folder structure in your Drive:
```
MyDrive/Marine_Debris/
├── with debris/
│   ├── train/
│   ├── test/
│   └── validate/
└── without debris/
    ├── train/
    ├── test/
    └── validate/
```

**4. Run Cells in Order**

| Step | Cell | Description |
|------|------|-------------|
| 1 | Mount Drive | Connect Google Drive |
| 2 | Data Split | Split images into train/test/validate (80/10/10) |
| 3 | Augmentation | Generate augmented training images via `imgaug` |
| 4 | CNN Training | Train the Simple CNN model |
| 5 | Random Forest | Train the Random Forest classifier |
| 6 | CNN + RF | Train the hybrid CNN + Random Forest model |
| 7 | UMAP | Run UMAP-based visualization and classification |
| 8 | Clarifai | Object detection using Clarifai API |
| 9 | Voila App | Launch interactive image classification UI |

---

## 📊 Evaluation Metrics

The models are evaluated using:

- **Accuracy** — overall correct predictions
- **Precision & Recall** — per-class performance
- **F1 Score** — harmonic mean of precision and recall
- **Confusion Matrix** — visual breakdown of TP, TN, FP, FN

---

## 🖥️ Interactive App

Two UI options are available:

- **Voila** — Jupyter-based interactive widget for uploading images and viewing classification results in-browser
- **Streamlit** — Lightweight web app for real-time classification

To launch Voila in Colab:
```python
!pip install voila
!jupyter serverextension enable --sys-prefix voila
```

---

## 📝 Project Components

Marine Debris Detection System project is impressive! Let's dive into the details of each component:

1. **Data Preparation:**
   - The "Splitting Data" scripts are crucial for dividing your dataset into training, testing, and validation sets. Proper data splitting ensures robust model performance.
   - "Image Augmentation" scripts enhance dataset diversity by creating variations of existing images. This helps prevent overfitting and improves generalization.

2. **Model Training:**
   - Implementing a **Convolutional Neural Network (CNN)** is an excellent choice for image classification. CNNs learn hierarchical features from images effectively.
   - Your "Training Script" trains the CNN model using the augmented dataset. Fine-tune hyperparameters and monitor training progress.
   - The "Evaluation Script" assesses the trained model using metrics like accuracy, precision, recall, and the **F1 score**.

3. **Model Evaluation:**
   - The "Confusion Matrix" visually represents model predictions (true positives, true negatives, false positives, false negatives).
   - The **F1 score** balances precision and recall. Aim for a high F1 score to achieve both accuracy and completeness.

4. **Object Identification (Future Work):**
   - Integrating the **Clarifai API** for object identification within images is exciting. It can enhance your system's capabilities by identifying specific debris types.
   - Developing an interactive **Voila app** for image upload and classification results will make your project user-friendly.

5. **Project Database:**
   - Access the dataset via the **[Google Drive link](https://drive.google.com/drive/folders/1_zXqFG5J3rW07aRHf-NclbIePtdtbzOP?usp=drive_link)** for transparency and reproducibility.

---

## 👥 Team

**Batch 1 — Marine Debris Detection System**

> For full details, see [`reports/Batch-1_Report_(FINAL).pdf`](reports/Batch-1_Report_(FINAL).pdf)

---

## 📄 License

This project is for academic and research purposes. 🚀🌊
