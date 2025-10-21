# handwritten-digits-recognition-dl
A Jupyter notebook to create model to detect handwritten digits

# Handwritten Digits Recognition (MNIST)

A simple deep-learning project using Keras/TensorFlow to recognize handwritten digits from the MNIST dataset. The core work lives in the Jupyter notebook `handwritten_digit_recognition.ipynb`.

## Overview
- Uses the MNIST dataset (`keras.datasets.mnist`).
- Preprocesses images and labels for training and evaluation.
- Builds a Keras `Sequential` model with fully connected `Dense` layers.
- Trains and evaluates the model, reporting accuracy and loss.

## Dataset
- MNIST: 60,000 training images and 10,000 test images of handwritten digits (28x28 grayscale).
- Automatically downloaded via Keras on first use.

## Model Architecture (as implemented)
- `Sequential` model with:
  - Hidden layers: `Dense(50, activation='relu')` followed by another `Dense(50, activation='relu')`
  - Output layer: `Dense(10, activation='sigmoid')`
- Loss/metrics configured with `metrics=['accuracy']` in `model.compile(...)`.

Note: For multi-class classification, `softmax` is a common choice for the output activation with `categorical_crossentropy` or `sparse_categorical_crossentropy`. This notebook currently uses `sigmoid` on the final layer; it still works but you may experiment with `softmax` for potentially clearer probabilistic outputs.

## Results
- Training accuracy progresses to ~0.988.
- Test accuracy observed around ~0.972.

These values are derived from the notebook run logs embedded in `handwritten_digit_recognition.ipynb`.

## Environment Setup
Recommended Python 3.9+.

1) Create and activate a virtual environment (optional but recommended):
   - macOS/Linux:
     ```bash
     python3 -m venv .venv
     source .venv/bin/activate
     ```
   - Windows (PowerShell):
     ```powershell
     python -m venv .venv
     .venv\Scripts\Activate.ps1
     ```

2) Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3) Launch Jupyter and open the notebook:
   ```bash
   jupyter notebook
   ```
   Then open `handwritten_digit_recognition.ipynb` and run the cells.

## Project Structure
```
.
├── LICENSE
├── README.md
├── requirements.txt
└── handwritten_digit_recognition.ipynb
```

## Notes and Tips
- First run will download MNIST automatically.
- If you encounter GPU/CPU warnings with TensorFlow, the model still trains on CPU.
- Consider switching the final activation to `softmax` and using `sparse_categorical_crossentropy` if you want the typical multi-class setup.

## License
This project is licensed under the terms of the license in `LICENSE`.
