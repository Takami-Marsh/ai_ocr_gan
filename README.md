# Handwriting Recognition with GAN Enhancement

A Python-based handwriting recognition system that uses Generative Adversarial Networks (GANs) to improve OCR accuracy for individual writing styles. The project combines CNN-based digit recognition with GAN-enhanced data augmentation, achieving significant improvements in recognition accuracy. Particularly focused on healthcare applications, this system helps bridge communication gaps for patients with speech or hearing impairments by making written communication more reliable and accessible.

## Overview

This project investigates how Generative Adversarial Networks (GANs) can enhance Optical Character Recognition (OCR) accuracy for individual handwriting styles. The research focuses on improving digit recognition through data augmentation techniques including rotation and GAN-generated samples.

## Motivation

In healthcare settings, written communication is crucial for patients with speech or hearing impairments. According to research, about 30% of communication in these settings relies on written notes. However, handwriting can become a barrier when it's unclear or when users aren't comfortable with written communication. This project aims to improve handwriting recognition accuracy by adapting to individual writing styles using GANs.

## Key Features

- Default MNIST-based digit recognition
- Enhanced recognition with rotation-augmented training
- GAN-based data augmentation
- Personalized model refinement using individual samples
- Conditional GAN (CGAN) implementation for generating digit samples

## Implementation Details

### Core Components

1. **Base CNN Model** (`train_default.py`)
   - Improved CNN architecture with BatchNorm
   - Data augmentation with random rotation
   - MNIST dataset integration
   - Training and validation pipeline

2. **Conditional GAN** (`cgan.py`)
   - Class-conditional Generator and Discriminator
   - MNIST-based training
   - Support for generating digit samples
   - Model weight saving for transfer learning

### Training Methods

The project implements several training approaches:
1. `default`: Basic MNIST training
2. `rotate`: Training with rotated MNIST samples (±30°)
3. `rotate+gan`: Enhanced with GAN-generated samples (1000 per digit)
4. `rotate+gan+n`: Further refined with user-specific samples

## Results

The research demonstrates:
- Improved recognition accuracy with rotation-augmented training
- Enhanced performance when using GAN-generated samples
- Statistical significance in accuracy improvements (p < 0.05)
- Successful adaptation to individual writing styles

## Project Structure

```
.
├── train_default.py          # Default training implementation
├── train_rotate.py          # Rotation-augmented training
├── train_rotate+gan.py      # GAN-enhanced training
├── cgan.py                  # Conditional GAN implementation
├── benchmark.py             # Performance evaluation
├── transform_dataset.py     # Dataset transformation utilities
└── rl_gan_training.py       # Reinforcement learning GAN training
```

## Model Architecture

### CNN Model
- 3 Convolutional layers with BatchNorm
- Max pooling layers
- Dropout for regularization
- Fully connected layers for classification

### CGAN Architecture
- Generator: 4-layer network with BatchNorm and LeakyReLU
- Discriminator: 3-layer network with LeakyReLU
- Conditional input: One-hot encoded digit classes

## Future Work

1. Investigation of alternative generative models:
   - Variational Autoencoders (VAE)
   - Diffusion models

2. Model improvements:
   - Architecture optimization
   - Training duration studies
   - Sample size impact analysis

3. Applications:
   - Medical documentation systems
   - Personalized handwriting synthesis
   - Digital accessibility tools

## Research Paper

For detailed methodology and results, refer to the accompanying research paper: ["Improving Handwriting Recognition Using GAN-Enhanced Techniques with User-Specific Data"](AI-OCR_Research.pdf)

## License

See the [LICENSE](LICENSE) file for license rights and limitations.
