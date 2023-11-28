# Dashtoon-Gen-AI-Assignment
This is the Assignment solution for the Dashtoon Gen AI PS (https://dashtoon.notion.site/Engineer-Generative-AI-1a3a0d0195ee4e7fb32d4d914e57fdb0)
----

# Neural Style Transfer (NST) Model

## Overview

This repository contains an implementation of Neural Style Transfer (NST), a deep learning technique that merges the content of one image with the style of another. The model is built using PyTorch and is designed to be customizable for various content and style images.

## Installation

To use the NST model, follow these steps:

1. **Clone the repository:**

   ```bash
   git clone https://github.com/ablokitj20/Dashtoon-Gen-AI-Assignment.git
   cd Dashtoon-Gen-AI-Assignment
   ```
2. **Install the Requirements**
   ```bash
   pip install -r requirements.txt
   ```
3. **Run the Python file**
   ```bash
   python NST.py
   ```
4. **Add the Content and Style Directory, and wait for magic**

   # Theory
<img src="https://github.com/ablokitj20/Dashtoon-Gen-AI-Assignment/assets/84399246/3f906309-70b2-4966-a65c-d813a1b47fe0" width="400"> &#9; <br> <img src="https://github.com/ablokitj20/Dashtoon-Gen-AI-Assignment/assets/84399246/d4da2dfa-ca27-4acf-9a8c-37b66a25a36b" width="200"> <img src="https://github.com/ablokitj20/Dashtoon-Gen-AI-Assignment/assets/84399246/9b5cd522-34a7-494d-a022-c64b001b3152" width="200">

# Neural Style Transfer (NST) using VGG19

Neural Style Transfer is a fascinating deep learning technique that combines the content of one image with the artistic style of another. This repository implements NST using the VGG19 architecture. Let's delve into the theoretical background, feature maps, and the loss function used.

## Theory

### Basic Idea

NST is based on the idea of separating and recombining content and style features of images. Given a content image `C` and a style image `S`, the algorithm generates a new image `G` that preserves the content of `C` while adopting the artistic style of `S`.

### Feature Maps

To achieve this, feature maps from different layers of a pre-trained convolutional neural network (CNN) are utilized. For content reconstruction, the feature maps from a chosen content layer are employed, and for style reconstruction, feature maps from multiple style layers are used.

#### Content Feature Maps
Let $F^{(l)}_c$ represent the content feature maps from layer $\ l \$.

#### Style Feature Maps
Let $F^{(l)}_s$ represent the style feature maps from layer $\ l \$

### Formulas

#### Content Loss
The content loss is a measure of the difference between the content features of the generated image and the content image.

<img src="https://github.com/ablokitj20/Dashtoon-Gen-AI-Assignment/assets/84399246/0362f8e2-2cf0-49c2-b2da-e8fd6e77f386" width="300">


#### Style Loss
The style loss measures the difference in the Gram matrices of the style features between the style image and the generated image.

<img src="https://github.com/ablokitj20/Dashtoon-Gen-AI-Assignment/assets/84399246/171459c8-4fe2-4a7c-a7d1-0f13fa9d2c80" width="300">

where $G^{(l)}\$ and $S^{(l)}$ are the Gram matrices for the generated and style images at layer $\ l\$, respectively, and $N_l\$ is the number of filters and $M_l$ is the size of the feature maps at layer $l$.

#### Total Loss
The total loss is a combination of the content loss and the style loss, controlled by hyperparameters \(\alpha\) and \(\beta\).

<img src="https://github.com/ablokitj20/Dashtoon-Gen-AI-Assignment/assets/84399246/7b39a520-6c4b-4636-abe6-437bc8a05d35" width="300">


## VGG19 Architecture

VGG19 is a deep CNN architecture that has shown excellent performance in image classification tasks. It consists of 19 layers, including 16 convolutional layers and 3 fully connected layers. The use of VGG19 in NST is advantageous due to its ability to capture both low-level and high-level features, making it well-suited for extracting content and style information.

Feel free to experiment with different layers and hyperparameters($\alpha$ and $\beta$) to achieve diverse and visually appealing stylized images using this implementation of NST!

### Model based on best performance as seen by me
1. I have chosen the values of $\alpha$ and $\beta$ which gives better result. Content weight is taken lesser than Style weight, as I wanted the styling to be more vibrant 
2. Choice of Optimizers between Adam and L-BFGS:<br>
   <img src="https://github.com/ablokitj20/Dashtoon-Gen-AI-Assignment/assets/84399246/64e77205-46f1-4716-9f99-4ca655a880b9" width="500">

   
