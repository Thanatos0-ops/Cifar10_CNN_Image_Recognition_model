# CIFAR-10 CNN Image Recognition Model

This repository contains a Convolutional Neural Network (CNN) project for CIFAR-10 image classification, including the training notebook and exported model artifacts.

## Repository Structure

- `notebook/CNN_model_creation.ipynb` — end-to-end notebook for data preparation, training, evaluation, and model export.
- `CNN_model_saved/` — saved model artifacts:
  - `cnn_cifar10_model.keras`
  - `cnn_cifar10_model.h5`
  - `cnn_cifar10_savedmodel/` (TensorFlow SavedModel)
  - `preprocessing.pkl`

## Dataset

- Dataset: **CIFAR-10** (10 classes, 32x32 RGB images)
- Classes: airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck

## Model Summary

The notebook builds a deep CNN with repeated Conv2D + BatchNormalization blocks, MaxPooling, and Dropout regularization, followed by a final softmax classifier.

- Loss: `categorical_crossentropy`
- Optimizer: `Adam(learning_rate=0.0005)`
- Callbacks: `ReduceLROnPlateau`, `EarlyStopping`
- Total params: **1,186,346**

## Data Processing

- Train/validation split with `train_test_split` (80/20 from training set)
- Label encoding with `to_categorical`
- Data augmentation with `ImageDataGenerator`
- Saved preprocessing stats in `preprocessing.pkl`:
  - mean: `[0.4914, 0.4822, 0.4465]`
  - std: `[0.2023, 0.1994, 0.2010]`

## Results

Notebook test performance:

- Test Accuracy: **0.8977**
- Test Loss: **0.4360**

## How to Use

1. Open and run `notebook/CNN_model_creation.ipynb` to reproduce training and evaluation.
2. Use artifacts in `CNN_model_saved/` for inference/deployment.
3. Load `preprocessing.pkl` to apply the same normalization settings used during training.

## Main Libraries

- TensorFlow / Keras
- NumPy
- scikit-learn
- Matplotlib
- OpenCV (`cv2`)
