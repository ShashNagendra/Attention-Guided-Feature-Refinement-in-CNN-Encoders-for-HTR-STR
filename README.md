# Attention-Guided-Feature-Refinement-in-CNN-Encoders-for-HTR-STR
Implementation of the paper: Attention-Guided Feature Refinement in Convolutional Neural Network Encoders for Handwritten and Scene Text Recognition

🔶 Overview

This repository presents an enhanced framework for Handwritten Text Recognition (HTR) and Scene Text Recognition (STR) by incorporating attention-guided feature refinement within CNN-based encoders.

The implementation is built upon the baseline from
handwritten-text-recognition
and extends it with multiple attention mechanisms and efficient sequence modeling strategies.

The core idea is to improve feature representation before sequence modeling by inserting attention modules within convolutional blocks.

🔶 Motivation

Traditional CRNN-based HTR/STR models:

Treat all feature channels equally
Lack adaptive feature recalibration
Rely heavily on recurrent layers

This work addresses these limitations by:

Enhancing feature discrimination via attention
Introducing efficient gated convolutional blocks
Leveraging TCN-based sequence modeling to reduce recurrence dependency
🔶 Key Contributions
🔹 1. Attention-Guided Feature Refinement

Multiple attention mechanisms are integrated into the CNN encoder:

Squeeze-and-Excitation (SE)
CBAM (with and without spatial attention)
Efficient Channel Attention (ECA – k=3, k=5)
Global Context (GC) Block
Spatial SE and Channel-Spatial SE

📌 These modules are inserted before gated convolution layers, enabling:

Channel-wise recalibration
Spatial attention refinement
Improved character-level feature discrimination
🔹 2. Gated Convolutional Encoder

The encoder is enhanced using:

FullGatedConv2D
GatedConv2D

✔ Benefits:

Controlled feature propagation
Better handling of complex handwriting patterns
Improved robustness to noise and distortions
🔹 3. TCN-based Sequence Modeling

Instead of relying solely on recurrent networks:

Temporal Convolutional Networks (TCN) are used with:
Dilations: [1, 2, 4]
Residual connections
WaveNet-style gated activation

✔ Advantages:

Parallel computation
Long-range dependency modeling
Reduced training time compared to RNNs
🔹 4. Hybrid Architectures

The repository includes multiple model variants for systematic evaluation:

EfficientGated_HTR
SeNet_model
CBAM_model / CBAM_noSpatial
ECA3_model, ECA5_model
GCNet_model
Dual Attention (SE + ECA)
Channel-Spatial SE
No Attention baseline

📌 This enables controlled comparison of attention mechanisms under a unified pipeline.
