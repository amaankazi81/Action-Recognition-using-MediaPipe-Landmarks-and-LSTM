# 🏃‍♂️ Action Recognition using MediaPipe Landmarks and LSTM

This project performs human action recognition on video data using **MediaPipe** to extract body landmarks and an **LSTM (Long Short-Term Memory)** neural network for classification.

🎯 It focuses on classifying **three actions**:
- 🥋 TaiChi  
- 🤸‍♂️ Jumping Jack  
- 💪 Pushups  

Achieves **90%+ accuracy** on both `(30, 225)` and `(45, 225)` LSTM configurations.

---

## 📌 Features

- ✅ Action classification using temporal body movement
- 🎥 Landmark extraction from videos using MediaPipe Holistic (Pose + Hands)
- 🔁 Sequential data modeling with LSTM
- 📈 High accuracy on UCF50 subset
- 🔍 Tested with unseen videos

---

## 📁 Dataset

Used selected actions from the [UCF50 dataset](https://www.crcv.ucf.edu/data/UCF50.php):

- Only 3 actions: `TaiChi`, `JumpingJack`, and `Pushups` (You can take any Actions from Dataset)
- Converted each video into a Sequence Length of 30 or 45 landmark frames
- Each frame represented as a 225-dimensional vector (33 pose + 21x2 hand landmarks × 3D)

---

## 🧠 Model Architecture

**Input Shape:** (30 or 45, 225)

**Model:**

    1st LSTM Layer (128 units)
    
    Dropout
    
    2nd LSTM Layer (64 units)
    
    Fully Coonected Layers-
    
    Dense (32 units)
    
    Dense (number of classes = 3) with Softmax

---

## 🚀 How to Run

You can run this project directly in Google Colab — no setup required!

- Open the notebook in Colab
📔 Click here to Run in Colab:

  **[LSTM (30, 225) Model]**(https://colab.research.google.com/drive/1wUnjqtoo_IaevqSaxQH2dekszx7PZWG_?usp=sharing)

  **[LSTM (45, 225) MOdel]**(https://colab.research.google.com/drive/11JM7CIZq-6QOBbZ3P9L7kuuzaDWsiJsu?usp=sharing)

- Follow the cells step by step

- Select Action you want to train

- Extract landmarks using MediaPipe

- Train the LSTM model

- Predict on new videos

- Upload your own video (optional)
    Use the file upload option in Colab to test on new videos.

- ℹ️ Make sure to select GPU Runtime in Colab:
    Runtime > Change Runtime Type > Hardware Accelerator: GPU


## 🛠 Tech Stack

    - Python

    - OpenCV

    - MediaPipe

    - NumPy

    - TensorFlow / Keras

    - UCF50 Dataset


## 📊 Results

| Sequence Shape | Accuracy |
| -------------- | -------- |
| (30, 225)      | 96.35%   |
| (45, 225)      | 94.83%   |



**License**

This project is licensed under the MIT License.


