# GAN-Based Image Synthesis
This project implements a Generative Adversarial Network (GAN) for image synthesis using PyTorch. The GAN is designed to generate realistic synthetic images based on a training dataset.


## Features

1. Customizable GAN architecture

2. Training on a variety of image datasets (e.g., Chest X-ray images)

3. Support for both CPU and GPU training

4. Progressive image resolution enhancement

5. Evaluation using Structural Similarity Index Measure (SSIM)


## Training Process

- The training loop alternates between:

- Training the Discriminator: Optimizes the ability to distinguish between real and fake images.

- Training the Generator: Optimizes the ability to generate images that fool the discriminator

## Evaluation:

- To evaluate the model, use SSIM to compare generated and real images:

A higher SSIM score indicates better similarity.

Low SSIM: Continue training or adjust the GAN architecture.

Out-of-memory errors: Reduce batch size or switch to CPU training.
