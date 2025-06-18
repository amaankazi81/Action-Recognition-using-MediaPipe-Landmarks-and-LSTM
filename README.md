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

```text
Input Shape: (30 or 45, 225)

Model:
    LSTM Layer (128 units)
    Dropout
    LSTM Layer (64 units)
    Dense (32 units)
    Dense (number of classes = 3) with Softmax

---

## 🚀 How to Run
1. **Clone the repository:**
    ```bash
    git clone https://github.com/yourusername/action-recognition-lstm.git
    cd action-recognition-lstm

2. **Setup Environment:**
    ```bash
    pip install -r requirements.txt

3. **Prepare Dataset:**
  - Download and extract UCF50 dataset

  - Modify selected_actions = ['TaiChi', 'JumpingJack', 'Pushups']

  - Run landmark_extraction.py to extract and save .npy landmark files

4. **Train the Model:**
    ```bash
    python train_model.py

5. **Predict a Video:**
    ```bash
    sequence = process_video('your_video.avi')
    prediction = model.predict(sequence)


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


