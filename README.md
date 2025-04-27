# vae-gan-learned-similarity

# Autoencoding Beyond Pixels Using a Learned Similarity Metric

This repository implements a **VAE/GAN hybrid model** based on the paper:  
**"Autoencoding Beyond Pixels Using a Learned Similarity Metric"**  
([Larsen et al., ICML 2016](https://arxiv.org/abs/1512.09300)).

The model improves image reconstruction quality by using **feature-wise loss** extracted from a GAN discriminator, instead of traditional pixel-wise reconstruction loss.

We apply this approach to facial images, demonstrating both high-quality reconstructions and **semantic attribute manipulations** like adding eyeglasses or changing hair color.

---

## 📂 Project Structure

vae-gan-beyond-pixels/

├── faces.ipynb # Main code: training, attribute vector computation, visualization

├── requirements.txt # List of dependencies

├── README.md # This file

text

---

## 📚 Contents

- [vae-gan-learned-similarity](#vae-gan-learned-similarity)
- [Autoencoding Beyond Pixels Using a Learned Similarity Metric](#autoencoding-beyond-pixels-using-a-learned-similarity-metric)
  - [📂 Project Structure](#-project-structure)
  - [📚 Contents](#-contents)
  - [✨ Features](#-features)
  - [🛠️ Setup Instructions](#️-setup-instructions)
  - [▶️ How to Run](#️-how-to-run)
  - [⚙️ Training Details](#️-training-details)
  - [🖼️ Results](#️-results)
  - [⚡ Known Limitations](#-known-limitations)
  - [📚 References](#-references)
  - [Acknowledgements](#acknowledgements)

---

## ✨ Features

- VAE and GAN are combined into a hybrid model.
- Latent space regularization using KL Divergence loss.
- Feature-wise reconstruction loss instead of pixel-wise error.
- Semantic attribute editing through attribute vector arithmetic.
- Visualization of input, reconstruction, and attribute-modified outputs.

---

## 🛠️ Setup Instructions

1. **Clone this repository**
git clone https://github.com/your-username/vae-gan-beyond-pixels.git
cd vae-gan-beyond-pixels

text

2. **(Optional) Create a virtual environment**
python3 -m venv venv
source venv/bin/activate # On Windows: venv\Scripts\activate

text

3. **Install dependencies**
pip install -r requirements.txt

text

4. **Prepare Dataset**
- Download and organize your dataset locally.
- Example structure:
  ```
  /path/to/your/dataset/
      ├── img1.jpg
      ├── img2.jpg
      ├── ...
  ```
- Update the img_dir path in faces.ipynb:
  ```
  img_dir = "/path/to/your/dataset"
  ```

## ▶️ How to Run

All steps can be run directly through the faces.ipynb notebook:

1. **Train the VAE/GAN model**
- Train encoder, decoder, and discriminator.

2. **Compute Attribute Vectors**
- Generate and save vectors for attributes like "Eyeglasses", "Bangs", "Blond Hair", etc.

3. **Visualize Attribute Manipulation**
- Create a grid showing input images, reconstructions, and attribute modifications.

4. **Evaluate Model**
- Calculate cosine similarity and reconstruction MSE.

## ⚙️ Training Details

| Setting | Value |
|---------|-------|
| Image Size | 64×64 pixels |
| Latent Dimension | 256 |
| Batch Size | 128 |
| Optimizer | RMSProp |
| Learning Rate | 3e-4 |
| Epochs | 300 (adjustable) |

**Loss Functions:**
- KL Divergence Loss (L_prior)
- Feature-wise Reconstruction Loss (L_like^Dis_l)
- GAN Loss (L_GAN)

## 🖼️ Results

- Reconstructions preserve face identity.
- Attribute vectors successfully modify features without major distortions.

## ⚡ Known Limitations

- Some outputs are slightly blurrier than the original paper results.
- Attribute entanglement (e.g., "Male" attribute might correlate with "Mustache").
- Longer training with more powerful hardware can further improve quality.

## 📚 References

- Larsen, A. B. L., Sønderby, S. K., Larochelle, H., & Winther, O. (2016).
Autoencoding Beyond Pixels Using a Learned Similarity Metric.
International Conference on Machine Learning (ICML).
arXiv:1512.09300

##  Acknowledgements

- CelebA Dataset
- PyTorch Framework
- Paper authors: Anders Boesen Lindbo Larsen, Søren Kaae Sønderby, Hugo Larochelle, Ole Winther