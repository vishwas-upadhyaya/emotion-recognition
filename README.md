# emotion-recognition

## Project Overview
An artificial intelligence project aimed at recognizing human emotions from audio speech files.

## What is this Project?
This system analyzes audio recordings to classify the underlying emotion (such as happiness, sadness, anger, etc.). It uses an MLP (Multi-Layer Perceptron) classifier trained on audio features.

## How it was done
The project uses Python to extract audio features (like MFCCs, chroma, and mel spectrograms) using libraries such as `librosa`. An MLP classifier model (`mlp_classifier.model`) was trained using `scikit-learn` in the provided Jupyter Notebook (`emotion_recognition.ipynb`), and `prediction.py` is used to infer emotions from new audio files.

## Why it was done
To explore speech processing and audio-based machine learning, demonstrating how acoustic features correlate with human emotions.

## Tech Stack
- Python
- Scikit-learn (MLP Classifier)
- Librosa (Audio Processing)
- Jupyter Notebook

## Key Features
- Audio feature extraction from `.wav` files.
- Pre-trained Multi-Layer Perceptron model for emotion classification.
- Scripts to test and predict emotions on custom audio recordings.

## File Structure
- `emotion_recognition.ipynb`: Notebook for data exploration and model training.
- `prediction.py`: Script to process audio and predict its emotion.
- `mlp_classifier.model`: The saved pre-trained model.
- `*.wav` / `*.m4a`: Sample audio files for testing the model.

## Local Setup (if applicable)
1. Clone the repository.
2. Install the necessary libraries: `pip install scikit-learn librosa numpy pandas jupyter`.
3. Run the notebook to see the training process, or use `prediction.py` to test the `.wav` files.