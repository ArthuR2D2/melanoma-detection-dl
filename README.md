# melanoma-detection-dl
Deep Learning Esemble for Melanoma Detection using EfficientNet, CoAtNet and Swin-T on ISIC 2018/HAM1000.

# Melanoma Detection with Deep Learning Ensembles

Binary melanoma classification on the ISIC 2018 / HAM10000 dataset using
an ablation study across three architectures (EfficientNet-B0-NS, CoAtNet-Lite Mini, Swin-T)
combined into a soft-voting ensemble.

**Course:** Machine Learning 2  
**Author:** Jose Arturo Reza Quezada — Universidad Panamericana  
**Dataset:** [HAM10000 on Kaggle](https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000)

---

## Results summary

| Model | Best AUROC | FN @ θ=0.05 |
|---|---|---|
| EfficientNet-B0-NS | 0.894 | 2 |
| CoAtNet-Lite Mini | 0.921 | 4 |
| Swin-T | 0.915 | 1 |
| **Ensemble** | **—** | **0** |

Zero false negatives achieved by the ensemble at threshold θ = 0.05.

---

## Repository structure
melanoma-detection-dl/
├── notebooks/
│   └── MelanomaDetection_ArturoReza.ipynb   # Main training notebook
├── requirements.txt                           # Python dependencies
├── checkpoints/                               # Placeholder (models not tracked by Git)
└── README.md

---

## Setup and reproduction

### 1. Clone the repository
```bash
git clone https://github.com/ArthuR2D2/melanoma-detection-dl.git
cd melanoma-detection-dl
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Set up Kaggle credentials
Create a Kaggle account, go to **Account → API → Create New Token**,
and place the downloaded `kaggle.json` in `~/.kaggle/`:
```bash
mkdir -p ~/.kaggle
cp kaggle.json ~/.kaggle/
chmod 600 ~/.kaggle/kaggle.json
```
> ⚠️ Never commit `kaggle.json` to the repository.

### 4. Run the notebook
Open the notebook in Google Colab (recommended) or locally:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ArthuR2D2/melanoma-detection-dl/blob/main/notebooks/MelanomaDetection_ArturoReza.ipynb)

The notebook is self-contained and will:
1. Mount Google Drive and create the folder structure
2. Download HAM10000 from Kaggle automatically
3. Train all three models with checkpoint saving
4. Run the ensemble and generate all evaluation figures

### 5. Checkpoints
Pre-trained model weights are not stored in this repository due to file size limits.
To reproduce the results from scratch, run the notebook from cell 1.
Training takes approximately **50 minutes** on an NVIDIA L4 GPU (Google Colab).

---

## License
MIT
