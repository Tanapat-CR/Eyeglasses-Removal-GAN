# Automatic Eyeglasses Removal from Face Images using GANs
**ขั้นตอนวิธีการลบแว่นตาออกจากภาพใบหน้าโดยอัตโนมัติ**

This repository contains the official implementation of the senior project: **Automatic Eyeglasses Removal from Face Images**. The proposed system utilizes Generative Adversarial Networks (GANs) with a 5-Channel input design and a dual-discriminator architecture to seamlessly remove eyeglasses and reconstruct eye regions while preserving the original facial identity.

## 🌟 Key Features
* **Eyeglasses Segmentation:** Utilizes U-Net with a ResNet34 backbone to accurately detect and mask eyeglasses.
* **5-Channel Input Representation:** Combines RGB image, Eyeglasses Mask, and MediaPipe Eye Landmarks to guide the generator.
* **Dual PatchGAN Discriminators:** Employs Global and Local discriminators to ensure both overall structural consistency and high-quality eye detail synthesis.
* **Biometric Preservation:** Evaluated using the ArcFace model to measure False Non-Match Rate (FNMR) at a strict 1.0% False Match Rate (FMR) on real-world datasets.

## 📂 Repository Structure

The project is divided into 4 main Jupyter Notebooks covering the entire pipeline:

1. `train_segment.ipynb`: 
   * Script for training the eyeglasses segmentation model (U-Net + ResNet34).
2. `train_gan_mediapipe_5ch.ipynb`: 
   * Core script for training the GAN model. Handles the 5-channel input preparation and the optimization of Generator, Global Discriminator, and Local Discriminator.
3. `test.ipynb`: 
   * End-to-end inference pipeline. Takes an input image with glasses, generates the mask, extracts landmarks, and outputs the final glasses-removed image.
4. `face_verification.ipynb`: 
   * Evaluation script for Biometric Preservation. Calculates FNMR and FMR using the ArcFace model on the MeGlass dataset.

## ⚙️ Installation

1. Clone this repository:
   ```bash
   git clone [https://github.com/YourUsername/Eyeglasses-Removal-GAN.git](https://github.com/YourUsername/Eyeglasses-Removal-GAN.git)
   cd Eyeglasses-Removal-GAN