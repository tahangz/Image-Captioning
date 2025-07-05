# 🖼️ Image Captioning with ResNet101 + LSTM

This project implements an image captioning model that generates natural language descriptions from images using a CNN encoder (ResNet101) and RNN decoder  (LSTM).

- **Encoder**: Pretrained ResNet-101 extracts visual features
- **Decoder**: LSTM generates captions from image features
- **Dataset**: [Flickr8k](https://www.kaggle.com/datasets/adityajn105/flickr8k)
- **Framework**: PyTorch

---

## 🧠 Model Architecture

- **Encoder**: `ResNet101` (pretrained, removing FC layer)
- **Decoder**: `LSTM` with embedding + attention
- **Loss**: CrossEntropy with padding mask
- **Optimizer**: Adam

### 🔧 Hyperparameters

| Parameter           | Value     |
|---------------------|-----------|
| Embedding size      | 512       |
| Hidden size (LSTM)  | 512       |
| Dropout             | 0.5       |
| Batch size          | 32        |
| Learning rate       | 4e-4      |
| Max caption length  | 50 tokens |

---

## 🚀 Usage

```bash
# Clone and install dependencies
pip install -r requirements.txt

# Train the model
python train.py

# Evaluate or generate captions
python evaluate.py --image <path_to_image>
````

## 🗂 Dataset Preparation
Flickr8k can be downloaded via Kaggle API:

```bash
kaggle datasets download -d adityajn105/flickr8k
unzip flickr8k.zip
````
Make sure your directory contains:

- Images/ folder with .jpg files

- captions.txt

## 📜 Inspired By
This work is inspired by the [Show and Tell: A Neural Image Caption Generator (Google, 2015)](https://arxiv.org/abs/1411.4555) and the [Show, Attend and Tell](https://arxiv.org/abs/1502.03044) papers.
