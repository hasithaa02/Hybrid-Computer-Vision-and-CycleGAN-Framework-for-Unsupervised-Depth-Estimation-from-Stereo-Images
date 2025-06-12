# Cycle-GAN for Depth Map Generation

This project implements a Cycle-GAN architecture to translate **RGB images to Depth maps** and vice versa. The core objective is to use unpaired image-to-image translation to generate high-quality depth maps from RGB input without needing paired datasets.

---

## 📌 Project Highlights

- Implements **Cycle-Consistent Adversarial Networks (CycleGAN)** using PyTorch
- Supports RGB ↔ Depth map translation with unpaired data
- Uses custom modules for:
  - Generator & Discriminator
  - Image scaling and normalization
  - Custom loss functions (MSE, cycle-consistency)
  - Learning rate scheduling
  - Model checkpointing and sample saving
- Generates and saves intermediate output images to monitor training progress

---

## 🧠 Model Architecture

- Two **Generators**:  
  - `gen_A2B`: RGB → Depth  
  - `gen_B2A`: Depth → RGB  

- Two **Discriminators**:  
  - `disc_A`: RGB Discriminator  
  - `disc_B`: Depth Discriminator

- Training uses:
  - **Adversarial Loss** (MSE)
  - **Cycle Consistency Loss**
  - **Adam Optimizer**
  - **Learning rate decay scheduler**

---

## 🏗️ Folder Structure
## 📁 Project Structure
```
project_root/
│
├── createArchitecture.py    # Model creation and GPU assignment
├── datasets.py              # Dataset-related utilities (e.g., custom dataset class)
├── desktop.ini              # System file (can be ignored)
├── getDataLoader.py         # Custom dataset loader with transformations
├── helper.py                # Custom loss functions, utility functions
├── model.py                 # Generator and Discriminator classes
├── testing.py               # Inference or evaluation script
├── Training.py              # Main training script

```

---

## 🧪 Training Details

- **Batch size**: 16  
- **Image size**: 128×128  
- **Epochs**: 5000  
- **Learning rate**: 0.001  
- **Decay start**: 60% of total epochs  
- **Optimizers**: Adam (`β1 = 0.55`, `β2 = 0.999`)

> ⚠️ Make sure to adjust the batch size based on your GPU’s capacity.

---
## ✍️ Author
- Developed by Hasitha Reddy
- Symbiosis Institute of Technology, Pune
- Cycle-GAN core adapted for RGB–Depth domain translation
