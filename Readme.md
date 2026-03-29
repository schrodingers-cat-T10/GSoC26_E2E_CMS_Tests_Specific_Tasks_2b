# Jet Image Super-Resolution using Diffusion and GANs

This project explores super-resolution for jet images from high-energy physics using deep learning. The goal is to reconstruct high-resolution (HR) jet images from low-resolution (LR) inputs while preserving fine spatial structures and physically meaningful patterns.

Two approaches are implemented:
- A **conditional diffusion model** (primary focus)
- A **GAN-based baseline (SRGAN-style)**

---

## Motivation

Jet images represent energy deposits across detector components. Due to detector limitations, these images are often low resolution, which affects downstream tasks such as jet classification and substructure analysis.

Instead of relying on hardware improvements, this project investigates whether **learning-based super-resolution** can recover missing spatial detail.

---

## Implemented Approaches

### 1. Diffusion Model (Primary)

The diffusion model learns to reconstruct images by predicting noise added during a forward process.

#### Key Ideas
- Add noise to HR images over multiple timesteps
- Train a model to predict that noise
- Iteratively denoise to generate high-resolution outputs

#### Architecture
- U-Net backbone
- Residual blocks with time conditioning
- Self-attention (Transformer blocks)
- Sinusoidal timestep embeddings

#### Conditioning Strategy
The model is conditioned on LR inputs using: