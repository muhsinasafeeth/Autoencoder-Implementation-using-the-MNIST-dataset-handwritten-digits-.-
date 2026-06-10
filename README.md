# Autoencoder Implementation using the MNIST dataset .

## Project Overview

This assignment implements an Autoencoder using the MNIST handwritten digits dataset. The objective was to design, train, and evaluate an autoencoder capable of learning a compressed representation of handwritten digit images and reconstructing them from the learned latent space.

The model was developed using TensorFlow/Keras and evaluated based on reconstruction performance using the MNIST test dataset.

---

## Assignment Objectives

The following tasks were completed as part of this assignment:

### 1. Model Design

* Implemented an encoder to compress 28 × 28 grayscale images into a lower-dimensional latent representation.
* Implemented a decoder to reconstruct the original images from the latent representation.

### 2. Model Training

* Trained the autoencoder using the MNIST training dataset.
* Evaluated the trained model using the MNIST test dataset.

### 3. Model Evaluation and Visualization

* Displayed the summaries of the encoder, decoder, and complete autoencoder.
* Plotted the training and validation loss curves.
* Generated side-by-side comparisons of original and reconstructed test images.

---

## Dataset

The MNIST handwritten digits dataset was used for this assignment.

### Dataset Details

* Training Samples: 60,000 images
* Test Samples: 10,000 images
* Image Size: 28 × 28 pixels
* Image Type: Grayscale
* Digit Classes: 0–9

The dataset was loaded directly using TensorFlow/Keras.

---

## Data Preprocessing

The following preprocessing steps were performed:

* Loaded the MNIST dataset.
* Ignored class labels since autoencoders perform unsupervised learning.
* Converted image data to floating-point format.
* Normalized pixel values from the range 0–255 to 0–1.

---

## Model Architecture

### Encoder

The encoder compresses the input image into a latent representation.

Architecture:

Input (28 × 28)
→ Flatten
→ Dense Layer (128 units, ReLU)
→ Latent Layer (32 units, ReLU)

### Decoder

The decoder reconstructs the original image from the latent representation.

Architecture:

Latent Vector (32)
→ Dense Layer (128 units, ReLU)
→ Dense Layer (784 units, Sigmoid)
→ Reshape to 28 × 28

---

## Model Summary

### Encoder Parameters

* Total Parameters: 104,608

### Decoder Parameters

* Total Parameters: 105,360

### Complete Autoencoder

* Total Trainable Parameters: 209,968
* Non-Trainable Parameters: 0

### Latent Dimension

* 32 features

### Compression Ratio

* Original Input: 784 features
* Latent Representation: 32 features
* Compression Ratio: Approximately 24.5 : 1

---

## Training Configuration

The autoencoder was trained using the following settings:

* Optimizer: Adam
* Loss Function: Binary Cross-Entropy
* Epochs: 20
* Batch Size: 256
* Shuffle: Enabled
* Validation Dataset: MNIST Test Set

During training, the input images were used as both the input data and the target output data.

---

## Model Evaluation

The trained model was evaluated using the MNIST test dataset.

### Final Results

* Final Training Loss: 0.0893
* Final Validation Loss: 0.0882

These values indicate successful learning and good generalization performance.

It should be noted that accuracy is not considered a meaningful evaluation metric for autoencoders because the objective is image reconstruction rather than classification.

---

## Reconstruction Results

The trained autoencoder successfully reconstructed handwritten digit images from the compressed latent representations.

Observations from the reconstructed outputs include:

* The reconstructed digits closely resembled the original images.
* The overall structure and shape of the digits were preserved.
* Minor smoothing effects were observed due to dimensionality reduction.
* The reconstructed digits remained clearly recognizable.

---

## Results Discussion

The autoencoder effectively learned a compact representation of the MNIST handwritten digits by compressing each 784-dimensional input image into a 32-dimensional latent vector. Despite this significant reduction in dimensionality, the decoder was able to reconstruct images that retained the important visual characteristics of the original digits.

The final training and validation losses were very close to each other, indicating that the model generalized well to unseen data and did not exhibit significant overfitting. The reconstruction results demonstrated that the learned latent representation captured sufficient information to produce high-quality reconstructed images.

---

## Conclusion

This assignment successfully demonstrated the implementation and evaluation of an autoencoder using the MNIST handwritten digits dataset. The model achieved effective dimensionality reduction while maintaining the ability to reconstruct recognizable handwritten digits. The results highlight the capability of autoencoders in unsupervised feature learning, image compression, and reconstruction tasks.
