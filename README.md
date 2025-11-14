🚗 Driver Drowsiness Detection Using Deep Learning
👨‍💻 Authors

Mridul Pathania — B.Tech CSE, Lovely Professional University

Midhun KP — B.Tech CSE, Lovely Professional University

Ashutosh Chauhan — B.Tech CSE, Lovely Professional University

📌 Overview

Driver fatigue is a major cause of road accidents worldwide. This project presents a real-time Driver Drowsiness Detection System using Deep Learning and Computer Vision techniques.

The system classifies a driver’s state as Drowsy or Alert using facial cues such as eye closure and yawning, captured via a webcam.

We implemented and compared three different models:

🧠 Baseline CNN (Conv2D) — Highest accuracy (96.7%)

📱 MobileNetV2 — Lightweight, good for mobile/embedded systems

⚡ EfficientNetB0 — Underperformed (51%) due to convergence issues

The best-performing model is deployed using OpenCV for real-time monitoring.

✨ Key Features

✔ Real-time driver monitoring using webcam
✔ Deep learning-based eye & facial analysis
✔ Three model architectures compared
✔ Data augmentation for better generalization
✔ Class weighting to handle dataset imbalance
✔ 22 FPS real-time performance on CPU
✔ Robust to lighting and head pose variations

📂 Dataset

Dataset used: Yashar Jebraeily’s Drowsy Detection Dataset (Kaggle)

Training Images: 5,859

Testing Images: 1,483

Two categories: DROWSY, NATURAL (Alert)

Includes multiple lighting conditions & facial orientations

Preprocessing:

Images resized to 64×64 (CNN) or 128×128 (MobileNetV2/EfficientNetB0)

Normalized (0–1)

Augmentation: rotation, zoom, shift, flip

Class-weighting applied

🧠 Model Architectures
1️⃣ Baseline CNN (Best Model)

3 Convolution Blocks (16, 32, 64 filters)

MaxPooling2D

Batch Normalization

Dense layers + Dropout (0.4)

L2 Regularization

Adam optimizer (LR = 0.0001)

Accuracy: 96.7%

2️⃣ MobileNetV2 (Transfer Learning)

Pretrained ImageNet base

Frozen base layers

Added GAP, Dense, Dropout layers

Good performance with low computation

Accuracy: 93.5%

3️⃣ EfficientNetB0 (Transfer Learning)

Fine-tuned with custom head

Suffered convergence issues

Accuracy: 51%

🚀 Real-Time System (OpenCV)

Steps followed in real-time pipeline:

Capture webcam frames

Detect face using Haar Cascade

Crop ROI → resize → normalize

Predict using trained CNN

Display bounding box + state label

Runs at ~22 FPS on CPU

🛠️ Technologies Used

Python

TensorFlow / Keras

OpenCV

NumPy

Matplotlib

Kaggle Dataset
