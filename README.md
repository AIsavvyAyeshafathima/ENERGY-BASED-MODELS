# ENERGY-BASED-MODELS

This project implements an Energy-Based Model (EBM) using the MNIST dataset. The EBM learns to distinguish between real and generated images using the Contrastive Divergence (CD) algorithm. The project involves building a custom neural network for the energy function, training the model using random noise and real images, and evaluating its performance based on the contrastive divergence loss.

**Table of Contents**

Overview
Dataset
Model Architecture
Training Process
Validation Process
Installation
Usage
Results

Overview
This project implements an energy function for the MNIST dataset using a custom Keras model. The primary goals are:

Train the model using the Contrastive Divergence algorithm.
Monitor the performance through training and validation loss curves.
Assess the model's ability to distinguish real MNIST images from random noise.
Dataset
We use the MNIST dataset, which consists of 70,000 grayscale images of handwritten digits. The images are 28x28 pixels and normalized to the range 
0
,
1
0,1.

Training Set: 60,000 images
Test Set: 10,000 images
For more information on MNIST: MNIST Dataset

**Model Architecture**

The energy-based model is composed of a simple feedforward neural network:

Input layer: 784 (28x28) neurons

Hidden layer: 128 neurons, ReLU activation

Output layer: 1 neuron, representing the energy value

The energy function is trained using Contrastive Divergence, where the loss is calculated as the difference in energy between real and generated (random noise) samples.

Training Process

The model is trained for 120 epochs using the Adam optimizer. The training loss (Contrastive Divergence) is computed for each epoch, comparing real images from the dataset against generated images from the model's buffer.

Key Components:

Contrastive Divergence: A method used to update the model parameters by comparing the energies of real and generated samples.
Learning Rate: 0.001
Batch Size: 64
Validation Process
To assess the model's performance, a validation process was implemented using random noise samples. The contrastive divergence is computed for random noise and real images, and the validation loss is tracked across epochs to see if the model is improving in distinguishing noise from real images.

Plotting the Loss Curve: After training, use the following script to generate the loss curve:

bash
Copy code
python plot_loss.py
Results
The model was trained for 120 epochs. The loss curve remained constant during the training process, reflecting the model's stabilization in distinguishing between real and generated images. The results are consistent with those in the Generative Deep Learning textbook.

