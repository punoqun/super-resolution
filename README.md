# super-resolution

A PyTorch-based image super-resolution neural network that produces high-quality color images.

## Overview

This project implements a super-resolution neural network using the Sub-Pixel Convolutional Neural Network (ESPCN) architecture. The model processes images in the YCbCr color space, where:

- **Y channel (luminance)**: Processed through the neural network for super-resolution
- **Cb and Cr channels (chrominance)**: Upscaled using bicubic interpolation

This approach produces full-color super-resolved images while maintaining computational efficiency.

## Features

- YCbCr color space processing for better quality
- Sub-pixel convolution (PixelShuffle) for efficient upscaling
- Training and testing functions with PSNR metrics
- Color image reconstruction utilities

## Usage

The main implementation is in `SuperResolution-Prototype.ipynb`, which includes:

1. Data loading with YCbCr color space support
2. Neural network architecture with 4 convolutional layers
3. Training loop with loss tracking
4. Testing with PSNR evaluation
5. Color image reconstruction function

## Model Architecture

- **Input**: Single-channel (Y) downsampled image
- **Conv layers**: 1→64→64→32→(upscale_factor²) channels
- **Output**: Super-resolved Y channel
- **Activation**: ReLU
- **Upsampling**: Sub-pixel convolution (PixelShuffle)