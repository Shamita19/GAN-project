GAN-Based Image Synthesis Project

This project implements a Generative Adversarial Network (GAN) for image synthesis using PyTorch. The GAN is designed to generate realistic synthetic images based on a training dataset.

Project Overview

The project focuses on generating synthetic images using a GAN architecture, consisting of a Generator and a Discriminator. The generator creates images from random noise, while the discriminator attempts to distinguish between real and generated images. The two models are trained in opposition to improve image quality.

Features

Customizable GAN architecture

Training on a variety of image datasets (e.g., Chest X-ray images)

Support for both CPU and GPU training

Progressive image resolution enhancement

Evaluation using Structural Similarity Index Measure (SSIM)

Installation

Prerequisites

Ensure the following are installed on your system:

Python 3.8+

Git

VS Code

Pip

Virtual environment (optional)

Clone the Repository

git clone https://github.com/username/repo-name.git
cd repo-name

Install Dependencies

pip install -r requirements.txt

Dependencies include:

torch

torchvision

matplotlib

scikit-image

numpy

Dataset

This project can work with various image datasets. For example, if using the Chest X-ray Images dataset:

Download the dataset from Kaggle.

Place the dataset in the data/ directory.

Ensure the directory structure is as follows:

data/
    train/
        NORMAL/
        PNEUMONIA/
    test/
        NORMAL/
        PNEUMONIA/
    val/
        NORMAL/
        PNEUMONIA/

Usage

Train the Model

Open the project in VS Code.

Run the following command to start training:

python train.py

Monitor Training Progress

Use TensorBoard to visualize training metrics:

tensorboard --logdir logs/

Generated images and logs are saved periodically.

Modify Hyperparameters

You can adjust hyperparameters (e.g., learning rate, batch size) in config.py.

Training Process

The training loop alternates between:

Training the Discriminator: Optimizes the ability to distinguish between real and fake images.

Training the Generator: Optimizes the ability to generate images that fool the discriminator

Evaluation:

To evaluate the model, use SSIM to compare generated and real images:

from skimage.metrics import structural_similarity as ssim

real_img = real_imgs[0].cpu().numpy().squeeze()
fake_img = fake_imgs[0].cpu().numpy().squeeze()
score = ssim(real_img, fake_img, data_range=fake_img.max() - fake_img.min())
print(f"SSIM: {score}")

A higher SSIM score indicates better similarity.

Troubleshooting

High Loss Values: Reduce the learning rate or implement gradient clipping.

Low SSIM: Continue training or adjust the GAN architecture.

Out-of-memory errors: Reduce batch size or switch to CPU training.
