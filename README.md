# Sign Language Detection using MediaPipe & Random Forest

This project detects and classifies hand gestures (sign language letters) in real-time using MediaPipe for hand landmark detection and Random Forest for classification. It includes scripts for data collection, preprocessing, training, and live inference.

## 📁 Project Structure
├── collect_imgs.py          # Capture images for each gesture using webcam
├── create_dataset.py        # Extract hand landmarks and create dataset
├── train_classifier.py      # Train Random Forest model on extracted features
├── inference_classifier.py  # Real-time sign language detection using webcam
├── data/                    # Folder to store collected gesture images
├── data.pickle              # Processed dataset (generated)
└── model.p                  # Trained model (generated)
