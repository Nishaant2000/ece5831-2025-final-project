# Interpretable Hybrid Model for Visual Pattern Recognition  
**ECE 5831 – Pattern Recognition and Neural Networks (PRNN)**  
University of Michigan–Dearborn  


---

## 📌 Project Overview

This project investigates **visual pattern recognition** using both **neural networks** and **classical pattern recognition techniques**, with a strong emphasis on **model interpretability**.

We begin with a **baseline Convolutional Neural Network (CNN)** trained on the Fashion-MNIST dataset to learn hierarchical visual representations. While CNNs achieve strong classification performance, they often behave as **black-box models**, making it difficult to understand how predictions are formed.

To address this limitation, the project proposes a **hybrid model** that combines:
- **Learned CNN embeddings (deep features)**  
- **Handcrafted visual descriptors** such as **HOG** and **GLCM**

These features are fused and classified using a **Random Forest classifier**, enabling both strong performance and enhanced interpretability. This approach aligns directly with core principles of **Pattern Recognition and Neural Networks**.

---

## 🎯 Project Objectives

- Train and evaluate a baseline CNN for image classification  
- Analyze CNN behavior using **Grad-CAM**, **Saliency Maps**, and **Integrated Gradients**  
- Extract handcrafted features for classical pattern recognition  
- Build a hybrid feature-fusion model combining CNN and handcrafted features  
- Improve interpretability using **feature importance analysis** and **SHAP explanations**  
- Compare performance and interpretability between baseline and hybrid models  

---

## 📊 Dataset

The project uses the **Fashion-MNIST** dataset, a standard benchmark dataset consisting of:
- 28×28 grayscale images  
- 10 clothing categories  
- 60,000 training samples and 10,000 test samples  

The dataset is automatically downloaded using  
`torchvision.datasets.FashionMNIST`.

Due to size constraints, raw data files, outputs and processed tensors are **not included in this GitHub repository**.

---

## How to Run
1. Open final-project.ipynb
2. Run all cells sequentially
3. Generated outputs will appear in the outputs directory


## Links
- 📽 Presentation Video: https://drive.google.com/file/d/1uVmxxZvdvLm3vVbBx8ACJC4Ch0EhR6G2/view?usp=drive_link
- 📊 Presentation Slides: (https://docs.google.com/presentation/d/1I18H0U4Wn70LrOTuI0y9eWfhSGlObeM-/edit?usp=sharing&ouid=110052246928755423511&rtpof=true&sd=true)
- 📄 Final Report: https://drive.google.com/drive/folders/1TzyslFxhS1RPKGIaRgxkrwTxk5etHXzl?usp=drive_link
- 📂 Dataset: (https://drive.google.com/drive/folders/1gTOnX7QkJH7V7CyaiiYCUw0ro0zqx4vv?usp=drive_link)
- 🎥 Demo Video: (https://youtu.be/Wgf_A_jeKxM)
