# 🖐️ Sign Language Detection using MediaPipe & Random Forest

This project detects and classifies hand gestures (sign language letters) in real-time using **MediaPipe** for hand landmark detection and **Random Forest** for classification. It includes scripts for data collection, preprocessing, training, and live inference.

---

## 📁 Project Structure

```
├── collect_imgs.py          # Capture images for each gesture using webcam
├── create_dataset.py        # Extract hand landmarks and create dataset
├── train_classifier.py      # Train Random Forest model on extracted features
├── inference_classifier.py  # Real-time sign language detection using webcam
├── data/                    # Folder to store collected gesture images
├── data.pickle              # Processed dataset (generated)
└── model.p                  # Trained model (generated)
```

---

## ⚙️ Requirements

Install dependencies using pip:

```bash
pip install opencv-python mediapipe scikit-learn matplotlib numpy
```

---

## 🧩 Workflow Overview

### 1️⃣ Data Collection (`collect_imgs.py`)

This script captures gesture images through your webcam.

- Each class (gesture) will be saved as a folder in `./data/`.
- You can modify:
  ```python
  number_of_classes = 3
  dataset_size = 100
  ```
  to adjust how many gesture classes and images you want.

**Run:**
```bash
python collect_imgs.py
```
- Press **“Q”** to start collecting images for each gesture class.
- 100 images per class are captured automatically.

---

### 2️⃣ Dataset Creation (`create_dataset.py`)

This script extracts hand landmarks using **MediaPipe Hands** and stores them as numerical features.

**Run:**
```bash
python create_dataset.py
```

- Creates `data.pickle`, containing:
  ```python
  {'data': [list of features], 'labels': [class labels]}
  ```

---

### 3️⃣ Model Training (`train_classifier.py`)

Trains a **Random Forest Classifier** on the processed dataset.

**Run:**
```bash
python train_classifier.py
```

- Displays model accuracy:
  ```
  95.0% of samples were classified correctly !
  ```
- Saves the model as `model.p`.

---

### 4️⃣ Real-Time Inference (`inference_classifier.py`)

Runs real-time hand gesture detection and classification using your webcam.

**Run:**
```bash
python inference_classifier.py
```

- The model detects hand landmarks, predicts the gesture, and displays the corresponding **sign language letter** on the video feed.
- You can update `labels_dict` to map your class indices to specific letters:
  ```python
  labels_dict = {0: 'A', 1: 'B', 2: 'L'}
  ```

---

## 📊 Model Summary

- **Model:** Random Forest Classifier  
- **Input:** Normalized hand landmark coordinates (x, y)  
- **Output:** Predicted sign class (A, B, L, etc.)  
- **Dataset:** Custom webcam-captured gestures  

---

## 🧠 Future Enhancements

- Add more gesture classes (e.g., entire alphabet or words)
- Use CNN or LSTM models for improved accuracy
- Implement GUI for user-friendly interaction
- Optimize landmark normalization for multi-hand gestures

---
<img width="1024" height="1536" alt="ChatGPT Image Oct 31, 2025, 07_29_59 PM" src="https://github.com/user-attachments/assets/ac67df23-2e25-4c16-ac75-f34aac176e7e" />

