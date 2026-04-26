# mnist-digit-classifier

This project is a simple Handwritten Digit Classifier using the MNIST dataset and TensorFlow/Keras.

## How it works

The `project` script performs the following operations:

1.  **Data Loading:** It loads the MNIST dataset of handwritten digits using `tf.keras.datasets.mnist`.
2.  **Data Preprocessing:** It normalizes the pixel values of the images from a scale of 0-255 to 0-1 for better training performance.
3.  **Model Building:** It defines a simple sequential Neural Network architecture:
    *   A Flatten layer to convert the 28x28 images into a 1D array.
    *   Two Dense (hidden) layers with 128 neurons each and ReLU activation.
    *   A Dense output layer with 10 neurons (one for each digit 0-9) and softmax activation to output probabilities.
4.  **Model Training:** The model is compiled with the Adam optimizer and trained on the training dataset for 3 epochs.
5.  **Model Saving:** After training, the model is saved to a file named `handwritten.keras`.
6.  **Evaluation:** It evaluates the model on the test dataset and prints the loss and accuracy.
7.  **Custom Prediction:** It iteratively reads custom digit images from the `digits/` directory (e.g., `digit1.png`, `digit2.png`, etc.), preprocesses them (inverts colors to match MNIST), and uses the trained model to predict the digit in the image, displaying the image and the predicted result.

## How to run

### Prerequisites

Ensure you have Python 3 installed. You will need to install the following dependencies. You can use the provided `requirements.txt` file:

```bash
pip install -r requirements.txt
```

Alternatively, install them manually:

```bash
pip install tensorflow opencv-python-headless numpy matplotlib
```

*(Note: `opencv-python-headless` is used here instead of `opencv-python` to avoid GUI dependencies in some environments, but either will work if OpenCV is properly installed.)*

### Execution

To run the project and see the model training and custom predictions, simply run the Python script:

```bash
python3 project
```

The script will train the model and then attempt to show plots for predictions. If you are running this in an environment without a display (like a remote server or a basic Docker container), the `plt.show()` commands for the custom digit images might cause an error or require a non-interactive backend for Matplotlib, though the script will still attempt to print the predictions to the console.
