# OpenCV and ML Project - Sign Language Recognition

This is a Python-based project that utilizes OpenCV and machine learning (ML) to recognize sign language symbols in real-time using a webcam. The ML model used in this project is a Keras-based neural network, trained on more than 300 images per sign. Currently, the project can recognize individual letters, but future work is aimed at expanding it to recognize whole words using the chain method.

## Project Structure

The project consists of two Python files:

### `datacollection.py`
This file is used to collect data for training the ML model. It captures webcam frames, detects hands in the frames using the `cvzone.HandTrackingModule` library, and crops the hand region of interest (ROI). The cropped images are then resized to a fixed `imgSize` and saved to the folder "Data/X" with an incremental counter as the file name. The data collected with this file is used for training the ML model.

### `test.py`
This is the main file that runs the sign language recognition system in real-time. It captures webcam frames, detects hands using the `cvzone.HandTrackingModule` library, and crops the hand region of interest (ROI). The cropped images are then resized to the same `imgSize` used during data collection. The ML model loaded from "Model/keras_model.h5" predicts the sign label from the cropped and resized image. The recognized sign label is displayed on the screen using OpenCV's `cv2.putText` function along with a rectangle highlighting the detected hand. The labels used for prediction are defined in "Model/labels.txt".

## Usage

To use this sign language recognition system:

1. Ensure you have the required libraries installed:
   - OpenCV
   - cvzone (Install using: `pip install cvzone`)
   - Keras (For ML model loading and prediction)

2. Prepare the data (optional if you need to make your own model):
   - Run `datacollection.py` to collect data for training the ML model. The collected images will be saved in the "Data/X" folder.

3. Train the ML model (optional):
   - Train a Keras-based neural network using the collected data and save the model to "Model/keras_model.h5".
   - Ensure you have a text file "Model/labels.txt" containing the labels corresponding to each class index in the ML model.

4. Run the main sign language recognition system:
   - Simply run `test.py`.
   - The system will use the webcam feed to detect signs and display the recognized sign label on the screen in real-time.

## Future Aspects

The current implementation of the project is focused on recognizing individual letters. However, future work aims to enhance the system to recognize entire words using the chain method. This will provide more practical and comprehensive sign language recognition capabilities.

For any suggestions, improvements, or issues, please feel free to contribute to this project.

Enjoy using the Sign Language Recognition system! 🤟👋

(Note: This README assumes you are using Python 3.x for running the project.)