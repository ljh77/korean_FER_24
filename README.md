# Korean FER Classification Accuracy Improve(2024) - CNN Computer Vision

## 1. Overview

This repository provides an experimental framework for **facial emotion recognition (FER) focused on improving classification accuracy for Koreans and East Asians.**

This work is based on the following paper:

**Comparison and Analysis of CNN Models to Improve a Facial Emotion Classification Accuracy for Koreans and East Asians**

The primary objective is to:

* Compare multiple CNN architectures under identical conditions
* Evaluate the impact of dataset diversity
* Improve performance on East Asian facial data

Key findings:

* Xception and VGG16 show the highest performance
* Dataset diversity significantly improves accuracy
* Models trained only on Western datasets underperform on Asian faces

---
## 2. Project Structure (Not Ready)
```
**Each dataset must be downloaded from the original author’s GitHub or website, or accessed after obtaining permission.**

korean_FER_24/
│
├── datasets/
│   ├── FER2013/
│   ├── CK+/
│   ├── KFE/
│   └── JAFFE/
│
├── ipynb/
│   ├── mobilenet(new_1~)
│   ├── vgg16(new_3~)
│   ├── resnet50(new_5~)
│   ├── xception(new_2~)
│   └── densenet(new_4~)
│
├── train.py (Not Ready)
├── evaluate.py (Not Ready)
├── config.yaml (Not Ready)
├── run_all_experiments.py (Not Ready)
└── README.md
```

---

## 3. Dataset

This project uses the following datasets:

| Dataset | Description                                           |
| ------- | ----------------------------------------------------- |
| FER2013 | Large-scale facial emotion dataset |
| CK+     | Controlled facial expression dataset                  |
| KFE     | Korean Facial Emotion dataset (AI Hub in korea)                |
| JAFFE   | Japanese female facial expression dataset             |

### Preprocessing

All datasets are standardized as follows:

* Face detection using Haarcascade
* Face cropping
* Resize to 48×48
* Grayscale conversion

---

## 4. Models

The following CNN models are implemented:

* MobileNetV2 (lightweight)
* VGG16
* ResNet50V2
* Xception
* DenseNet121

All models:

* Use ImageNet pretrained weights
* Share identical output structure (7 emotion classes)
* Include:

  * Global Average Pooling
  * Dense layers
  * Dropout

---

## 5. Experimental Settings
* Image size: 48×48
* Batch size: 64 / 10
* Epochs: 30
* Optimizer: Adam
* Loss: Categorical Crossentropy
* Class imbalance handled via class weights
---

## 6. How to Run (Not Ready)

### 1. Install dependencies

```
pip install -r requirements.txt
```
### 2. Configure experiment
Edit `config.yaml`:
```
model: xception
dataset: [FER2013, CK+, KFE]
batch_size: 64
epoch: 30
```
### 3. Train
```
python train.py --config config.yaml
```
### 4. Evaluate
```
python evaluate.py
```
---

## 7. Run Full Experiments(Not Ready)
To reproduce all experiments:
```
python run_all_experiments.py
```
This will automatically run:

* FER2013 only
* FER2013 + CK+
* FER2013 + CK+ + KFE
---

## 8. Results
Observations:

* Xception performs best overall
* VGG16 performs similarly with fewer parameters
* Dataset diversity improves performance across all models

---

## 9. Key Contributions

* Systematic comparison of CNN models for FER
* Integration of Korean facial emotion dataset (KFE)
* Demonstration of dataset bias in FER models
* Reproducible experimental framework

---

## 10. Reproducibility

* Fixed random seed
* Unified preprocessing pipeline
* Identical training conditions across models

---

## 12. Reference

If you use this repository, please cite:

```
@article{lee2024fer,
  title={Comparison and Analysis of CNN Models to Improve a Facial Emotion Classification Accuracy for Koreans and East Asians},
  author={Lee, Jun-Hyeong and Song, Ki-Sang},
  journal={IJASEIT},
  year={2024}
}
```

---

## 13. GitHub


Project repository:

https://github.com/ljh77/korean_FER_24

##Contact
Jun-Hyeong Lee

yjhboky@gmail.com
