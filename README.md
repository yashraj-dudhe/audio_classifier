
# 🎧 Audio Classification Model: Scream, Ambient, and Conversation Detection

This project presents an end-to-end audio classification system designed to detect **screams**, **ambient sounds**, and **normal conversations** from audio files, including `.wav` and `.mp4` formats of variable lengths. The model is designed to be robust across a wide range of real-world scenarios, supporting long audio durations and multiple input types.

---

## 🧠 Model Architecture and Approach

- **Model Type**: Convolutional Neural Network (CNN)
- **Backend**: TensorFlow/Keras
- **Input**: Log-Mel Spectrograms from audio segments
- **Architecture**:
  - Conv2D Layers with ReLU activation
  - MaxPooling Layers for feature downsampling
  - Dense Layers for classification
  - Softmax output layer (3 classes: scream, ambient, conversation)
- **Segment-based Inference**:
  - Audio files are split into 3-second chunks
  - Each chunk is independently classified and results are aggregated

---

## 🧹 Data Preprocessing Steps

- **Supported File Formats**: `.wav`, `.mp4`
- **Audio Preprocessing**:
  - Convert MP4 to WAV if needed (using `moviepy`)
  - Resample audio to 22050 Hz
  - Segment into 3-second windows
  - Convert each segment to log-mel spectrogram using `librosa`
- **Feature Shape**: `(128, Time, 1)` per segment, padded or trimmed for consistency

---

## 🏋️ Training & Testing Strategy

- **Dataset**: Custom-labeled or open dataset with scream, ambient, and conversation samples
- **Splitting**:
  - Train/Validation/Test Split: 70% / 15% / 15%
- **Augmentations**:
  - Time-shifting, background noise injection, pitch shifting (optional)
- **Hyperparameters**:
  - Epochs: 30–50
  - Batch Size: 32
  - Optimizer: Adam
  - Loss Function: Categorical Crossentropy

---

## 📊 Evaluation Metrics

- **Accuracy**
- **Precision, Recall, F1-Score**
- **Confusion Matrix**
- **Per-Class Performance**
- **Segment-based Aggregated Accuracy** (for full audio)

---
## 📝 Note

Some of the functionalities are yet to be added 

## 🔁 How to Reproduce the Results

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/audio-classifier.git
   cd audio-classifier
