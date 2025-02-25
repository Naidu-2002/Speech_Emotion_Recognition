# Emotion Recognition from Speech Using LSTM

This project implements an emotion recognition system using speech data. It extracts features from audio files and predicts the emotion from the speech using a Long Short-Term Memory (LSTM) neural network model.

## Table of Contents
1. [Installation](#installation)
2. [Dependencies](#dependencies)
3. [How to Use](#how-to-use)
4. [File Structure](#file-structure)
5. [Model Architecture](#model-architecture)
6. [Results](#results)

## Installation

To run this project, clone the repository and install the dependencies listed below.

```bash
git clone https://github.com/your-username/emotion-recognition-speech.git
cd emotion-recognition-speech
```

### Dependencies

This project requires the following Python libraries:

- `tensorflow` (for LSTM model)
- `librosa` (for audio processing)
- `numpy` (for numerical operations)
- `pandas` (optional, for data handling)

You can install these dependencies by running:

```bash
pip install -r requirements.txt
```

Alternatively, you can install the dependencies individually using:

```bash
pip install tensorflow librosa numpy pandas
```

## How to Use

### 1. Prepare your audio files

The system processes `.wav` audio files. Place your audio file in the `input_audio` folder or provide the file path to the script.

### 2. Feature Extraction

Run the feature extraction script to extract MFCC features from the audio file.

```bash
python extract_features.py path_to_your_audio.wav
```

This script will extract the MFCC features and ensure the correct shape of the data. The output features will be used for emotion prediction.

### 3. Emotion Prediction

To predict the emotion from the extracted features:

```bash
python predict_emotion.py path_to_your_audio.wav
```

This will output the predicted emotion label based on the speech's characteristics.

## File Structure

The repository is organized as follows:

```
emotion-recognition-speech/
│
├── data/                         # Folder for storing datasets (optional)
│
├── input_audio/                  # Folder for input audio files
│
├── output/                        # Folder for model predictions and logs
│
├── models/                        # Folder for storing pre-trained models
│
├── extract_features.py            # Script to extract MFCC features from audio
├── predict_emotion.py             # Script to predict emotion using LSTM model
├── requirements.txt               # List of dependencies
├── README.md                     # This file
```

## Model Architecture

The emotion recognition model is based on a Long Short-Term Memory (LSTM) network. The architecture is as follows:

1. **LSTM Layer**: The first layer is an LSTM with 123 units, which processes the sequential data (MFCC features).
2. **Dense Layers**: After the LSTM layer, there are two fully connected (Dense) layers with 64 and 32 units, respectively.
3. **Output Layer**: The output layer has 7 units representing 7 different emotion classes.

The model is trained using categorical cross-entropy loss and Adam optimizer.

## Results

The model achieves an accuracy of **X%** on the emotion recognition task. Further optimization and training with additional data can help improve the performance.

### Supported Emotions
The model recognizes the following emotions from speech:
- Anger
- Disgust
- Fear
- Happiness
- Sadness
- Surprise
- Neutral

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [librosa](https://librosa.org/) for audio processing.
- [TensorFlow](https://www.tensorflow.org/) for building the LSTM model.
- [Emotion Dataset](https://www.kaggle.com/datasets/ejlok1/toronto-emotional-speech-set-tess/data) for providing the labeled speech data.

