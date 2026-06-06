# Speech Emotion Recognition (SER) using MLP and Acoustic Feature Extraction

## Project Overview
This repository contains a robust **Speech Emotion Recognition (SER)** system designed to automatically detect and classify human emotions from audio signals. The project focuses on high-precision acoustic feature extraction and leverages a multi-layer neural network to identify complex patterns in vocal expressions.

## What is this Project?
The project provides an end-to-end framework for analyzing emotional states through voice:
- **Acoustic Fingerprinting:** Uses advanced signal processing to extract a comprehensive set of features from raw audio.
- **Real-Time Analysis:** Features a live recording module that captures audio from the microphone, processes it on-the-fly, and predicts the emotional content.
- **Robust Preprocessing:** Implements custom logic for silence removal, audio normalization, and signal trimming to ensure consistent model input.

## How it was done (Deep Technical Details)
- **Neural Network Architecture:**
    - **Model:** A **Multi-Layer Perceptron (MLP) Classifier** from the `Scikit-learn` ecosystem.
    - **Design:** The MLP is configured as a deep feed-forward network, trained to map high-dimensional acoustic feature vectors to specific emotional categories.
- **Acoustic Feature Engineering (The Librosa Pipeline):**
    - **MFCC (Mel-frequency cepstral coefficients):** Extracts 40 coefficients that represent the short-term power spectrum of the sound, capturing the 'texture' of the voice.
    - **Chroma STFT (Short-time Fourier transform):** Analyzes the 12 distinct pitch classes (semitones), providing insights into the musical and tonal quality of the speech.
    - **Mel Spectrogram:** Generates a representation of the signal's power spectrum mapped to the Mel scale, closely mimicking the non-linear frequency perception of the human ear.
- **Audio Processing Workflow:**
    - **Signal Acquisition:** Uses **PyAudio** for low-latency microphone streaming and **Wave** for file-based processing.
    - **Noise Management:** Custom `is_silent` and `trim` functions automatically identify and remove silence from the beginning and end of recordings.
    - **Normalization:** Rescales the audio amplitude to a fixed maximum level to maintain signal consistency across different recording environments.
- **Inference Pipeline:**
    - Features are extracted using **Librosa** and **Soundfile**, reshaped into the model's required input dimensions, and fed into the pre-trained MLP for real-time classification.

## Why it was done
- To explore the effectiveness of various acoustic features in characterizing human emotion.
- To build a practical tool for human-computer interaction (HCI) that can adapt based on a user's emotional state.
- To demonstrate proficiency in audio signal processing and machine learning integration.

## Tech Stack
- **Language:** Python
- **Machine Learning:** Scikit-learn (MLPClassifier)
- **Audio Signal Processing:** Librosa, Soundfile, PyAudio, Wave
- **Numerical Analysis:** NumPy, SciPy (for array manipulation and normalization)
- **Serialization:** Pickle (for model persistence)

## Key Features
- **End-to-End Inference:** From microphone input to emotional prediction in seconds.
- **Multi-Feature Fusion:** Combines MFCC, Chroma, and Mel features for a multi-faceted view of the audio signal.
- **Live Recording Dashboard:** Interactive script (`prediction.py`) that guides the user through the recording and analysis process.

## File Structure
- `prediction.py`: The main execution script for live recording and real-time emotion prediction.
- `emotion_recognition.ipynb`: Research notebook documenting the data exploration and model training phases.
- `mlp_classifier.model`: The final, pre-trained multi-layer perceptron model.
- `test.wav`: Sample audio file used for validation and testing.

## Local Setup
1.  **Clone the repository:**
    ```bash
    git clone [repository-url]
    ```
2.  **Install dependencies:**
    ```bash
    pip install librosa pyaudio soundfile scikit-learn numpy
    ```
3.  **Run the Prediction script:**
    ```bash
    python prediction.py
    ```
    *Note: Ensure your microphone is connected and configured.*
