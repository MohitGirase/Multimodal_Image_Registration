# 🛰️ Multimodal Satellite Image Registration using GAN

This project presents a deep learning-based approach for **multimodal image registration** using a **Generative Adversarial Network (GAN)**. The model aligns **infrared (IR)** and **visible spectrum** satellite images to enable seamless integration of different imaging modalities, which is crucial for tasks like surveillance, environmental monitoring, and urban planning.

## 🧠 Project Objective

- Accurately align unregistered infrared images with visible spectrum satellite images.
- Handle challenges due to variations in texture, contrast, and noise across modalities.
- Improve registration quality using a GAN with attention and perceptual learning.

---

## 🧰 Methodology

### 🔄 GAN Architecture

- **Generator**:
  - Inputs: Visible image (RGB) and unregistered IR image (Grayscale)
  - Outputs: Aligned IR image
  - Components:
    - Encoder: 3 convolutional layers to extract features
    - Residual Blocks: 4 blocks to refine features
    - Attention Mechanisms:
      - Channel Attention
      - Spatial Attention
    - Decoder: Upsamples features to create the aligned image

- **Discriminator**:
  - Classifies whether the aligned IR image is real or generated
  - Architecture: PatchGAN with LeakyReLU and Sigmoid activations

---

### 📊 Loss Functions

1. **Adversarial Loss**: Encourages realistic aligned IR image generation
2. **Reconstruction Loss**: Enforces similarity to the target aligned IR image
3. **Perceptual Loss**: Ensures high-level feature consistency using VGG16
4. **Edge Loss**: Sharpens image alignment by preserving edges

---

## 📦 Dataset

- **Infrared (IR)**: 1,000 noisy, low-contrast images
- **Unregistered IR**: 1,000 images
- **Visible**: 1,000 images with varying sharpness

All images are preprocessed and normalized to [-1, 1].

---

## 🧪 Evaluation

- **Quantitative**: Metrics compare generated and ground-truth images
- **Qualitative**: Visualizations of visible, IR, and aligned outputs

---

## 🖼️ Visualization

A visualization function compares:
- Input visible and IR images
- Generated aligned IR image
- Ground truth aligned image

---

## 🔧 Implementation Details

- **Framework**: PyTorch
- **Attention Modules**:
  - `ChannelAttentionModule`
  - `SpatialAttentionModule`
- **Network Components**:
  - `ResidualBlock`
  - `Generator`
  - `Discriminator`
- **Custom Dataset Class**: Loads and transforms image triplets
- **Transformations**: Tensor conversion and normalization

---

 
