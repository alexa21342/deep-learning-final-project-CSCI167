# deep-learning-final-project-CSCI167
Deep Learning final project comparing SimpleCNN, ResNet18, and DistilBERT on CIFAR-10 and AG News.
**Alex Cortez — CSCI 167**

This project compares three deep learning architectures across two different data domains:  
- **Image classification** using CIFAR-10  
- **Text classification** using AG News  

The goal is to analyze how architecture depth, model families, and hyperparameter choices influence learning behavior, convergence, and generalization performance.


##  Project Overview

This project implements and evaluates the following models:

### **1. SimpleCNN (CIFAR-10)**
A custom convolutional neural network with:
- 3 convolutional blocks  
- Batch normalization  
- ReLU activations  
- Max pooling  
- Fully-connected classifier  

### **2. ResNet18 (CIFAR-10)**
A deeper architecture featuring residual skip connections to stabilize gradient flow.  
Trained with **SGD + StepLR scheduler**.

### **3. DistilBERT (AG News)**
A transformer-based pretrained NLP model fine-tuned for news topic classification.  
Uses the HuggingFace Transformers library.



##  Datasets

### **CIFAR-10**
- 60,000 RGB images (32×32)  
- 10 classes  
- Common benchmark for CNNs and ResNets  

### **AG News**
- 120,000 labeled news articles  
- 4 categories: World, Sports, Business, Sci/Tech  
- Ideal for transformer-based classification  

Both datasets are loaded directly using the HuggingFace Datasets API.


##  Experimental Setup

- Framework: **PyTorch**, **HuggingFace Transformers**, **Torchvision**
- Epochs:
  - SimpleCNN & ResNet18 → 5 epochs  
  - DistilBERT → 1 epoch (transfer learning)
- Optimizers tested:
  - **Adam**
  - **SGD**
- Batch sizes tested:
  - **32 vs 64**
- Learning rate schedule:
  - **StepLR** for ResNet18


##  Results (Validation Accuracy)

| Model | Dataset | Optimizer | Batch Size | Epochs | Val Accuracy |
|-------|----------|-----------|------------|--------|--------------|
| SimpleCNN | CIFAR-10 | Adam | 64 | 5 | **0.7095** |
| SimpleCNN | CIFAR-10 | SGD | 64 | 5 | **0.1000** |
| SimpleCNN | CIFAR-10 | Adam | 32 | 5 | **0.7288** |
| ResNet18 | CIFAR-10 | SGD + StepLR | 64 | 5 | **≈0.66** |
| DistilBERT | AG News | AdamW | 32 | 1 | **≈0.94** |


## Learning Curves

Add your figures in this section once uploaded:

