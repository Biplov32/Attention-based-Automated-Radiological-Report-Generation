# Radiology Report Generation using ChexNet and GRU with Attention

This project presents a deep learning-based approach for automated radiology report generation from chest X-ray images. Leveraging a pretrained **ChexNet** model for feature extraction and a **GRU-based sequence generator with attention mechanism**, this system aims to generate meaningful and accurate clinical findings.

## Project Overview

Radiological reporting is a time-consuming and skill-intensive task. Automating report generation can assist radiologists by saving time and reducing human error. This project utilizes the **Indiana University Chest X-ray dataset** to train and evaluate a model that translates chest X-ray images into coherent diagnostic reports.

## Model Architecture

### 1. **Image Feature Extraction**
- **Model**: Pretrained [ChexNet](https://arxiv.org/abs/1711.05225)
- **Base Network**: DenseNet-121
- **Output**: 1024-dimensional feature vector for each image

### 2. **Report Generation**
- **Model**: GRU (Gated Recurrent Unit)
- **Embedding Dimension**: 300
- **GRU Units**: 256
- **Attention Layer**: 64 units
- **Decoder**: Generates word-by-word report conditioned on visual features
- **Framework**: TensorFlow / Keras

## Dataset

- **Source**: [Indiana University Chest X-ray Collection](https://openi.nlm.nih.gov/)
- **Total Images**: ~7,000 chest X-ray images (Frontal and Lateral)
- **Reports**: ~3,000 textual reports
- **Fields Used**: `findings` and `impression`

## Performance Metrics

Evaluation was done using BLEU scores, which measure the similarity between the generated report and the reference report.

| Metric   | Score   |
|----------|---------|
| BLEU-1   | 0.3787  |
| BLEU-2   | 0.2418  |
| BLEU-3   | 0.1735  |
| BLEU-4   | 0.1026  |

These results indicate that the model generates clinically coherent sentences with a reasonable degree of overlap with the ground truth.
