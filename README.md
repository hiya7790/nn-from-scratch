# NN-from-scratch
Neural network from scratch using NumPy with manual backpropagation, trained on MNIST for digit classification.


## Overview
This project implements a fully connected neural network using only NumPy. The goal was to gain a deep understanding of how neural networks work internally, including forward propagation, backpropagation, and optimization.

The model is trained on the MNIST dataset to perform digit classification.

## Highlights
- No deep learning frameworks used
- Manual implementation of forward & backward propagation
- ReLU and Softmax activation functions
- Cross-entropy loss
- Gradient descent optimization
- Debugged numerical instability and gradient issues

## Architecture
- Input Layer: 784 features (28×28 images)
- Hidden Layer: 10 neurons (ReLU activation)
- Output Layer: 10 neurons (Softmax activation)

## Implementation Details
- Forward propagation using matrix multiplication
- Backpropagation implemented manually using chain rule
- Numerically stable softmax (max-shift trick)
- One-hot encoding for labels
- Vectorized operations for efficiency

## Challenges & Debugging
During development, the model initially failed to learn and was stuck at ~10% accuracy (random guessing). Key issues identified and fixed:
- Incorrect softmax implementation causing overflow
- Bias gradients computed as scalars instead of vectors
- Shape mismatches in matrix operations
- Incorrect parameter ordering in training loop

After resolving these issues, the model successfully learned meaningful patterns.

## Results
- Initial accuracy: ~10% (random baseline)
- Final accuracy: significantly improved after debugging and training

## How to Run
```bash
pip install -r requirements.txt
python src/train.py
```

## Project Sturcture
```bash
neural-network-from-scratch/
│── src/
│   ├── model.py
│   ├── train.py
│   ├── utils.py
│
│── notebook/
│   └── mnist_training.ipynb
│
│── README.md
│── requirements.txt
```

## Dataset
MNIST Digit Recognizer dataset (Kaggle)

## Learnings
- Understanding backpropagation at a mathematical level
- Importance of numerical stability in ML models
- Debugging neural networks using shape and gradient analysis
- How implementation details impact learning behavior

## Future Improvements
- Mini-batch gradient descent
- Deeper architectures
- Regularization techniques
- Visualization of loss and accuracy curves
