# ☁️ Attention-Based Transformer Models for Cloud DDoS Detection

> **Masters Research Project** — Detecting cloud-based DDoS attacks using Machine Learning, Deep Learning, and Transformer-based architectures on real-world network traffic data.

---

## 📄 Abstract

With the increasing reliance on cloud computing, ensuring security against cyber threats such as malware and Distributed Denial-of-Service (DDoS) attacks has become a critical challenge. This project introduces a holistic approach to detecting cloud-based attacks by combining machine learning, deep learning, and transformer-based models on a high-dimensional network traffic dataset.

The **FT-Transformer** model achieved **96.18% accuracy** and **96.18% F1-score**, and **TabNet** achieved the best overall accuracy of **97.68%**, demonstrating that attention-based architectures significantly outperform traditional methods for cloud DDoS detection.

---

## 🏗️ Project Architecture

```
cloud-ddos-detection/
│
├── 📓 notebooks/
│   └── Cloud_Attacks_Code.ipynb       # Full experiment notebook
│
├── 📊 data/
│   └── AIS_Dataset_on_Cloud_DDoS_Attacks.csv   # Dataset (see note below)
│
├── 📝 Cloud_Attacks_Report.pdf        # Full IEEE-style research paper
├── 📋 requirements.txt                # Python dependencies
└── 📖 README.md
```

---

## 🧪 Models Implemented

| Model | Type | Accuracy | Precision | Recall | F1 Score |
|-------|------|----------|-----------|--------|----------|
| Decision Tree | Classical ML | 81.85% | 92.78% | 70.70% | 80.24% |
| Random Forest | Classical ML | 91.73% | 87.76% | 97.77% | 92.50% |
| Deep Neural Network (DNN) | Deep Learning | 95.35% | 99.70% | 91.37% | 95.35% |
| 3-Layer MLP | Deep Learning | 95.40% | 99.58% | 91.58% | 95.41% |
| **TabNet** | **Attention-Based** | **97.68%** | **97.75%** | **97.68%** | **97.68%** |
| **FT-Transformer** | **Attention-Based** | **96.18%** | **96.35%** | **96.18%** | **96.18%** |

---

## 📊 Dataset

**AIS Dataset on Cloud DDoS Attacks**
- **Source:** [Zenodo – Cloud DDoS Dataset](https://zenodo.org/records/14681803)
- **Records:** 52,318 network flows (51,557 after deduplication)
- **Features:** 80 network traffic attributes (flow-based, packet-based, statistical)
- **Classes:** `BENIGN` (normal traffic) vs `DDOS` (attack traffic)
- **Class Balance:** ~26,887 DDoS | ~24,670 Benign — near-balanced

> ⚠️ Due to file size, the dataset is not included in this repo. Please download it from the Zenodo link above and place it in the `data/` folder.

---

## 🔬 Methodology

### 1. Data Preprocessing
- Removed 761 duplicate records
- Handled missing values (none found)
- Correlation analysis to identify top discriminative features
- Multicollinearity check — removed highly correlated feature pairs (threshold > 0.8)

### 2. Exploratory Data Analysis (EDA)
- Class distribution analysis
- Packet length distribution by traffic type
- Forward packets per second comparison
- Flow duration distribution

### 3. Feature Engineering & Splitting
- Label encoding: `BENIGN → 0`, `DDOS → 1`
- 80/20 train-test split with **stratified sampling**
- Feature scaling using `StandardScaler` (mean=0, std=1)

### 4. Models
- **Baseline ML:** Decision Tree (entropy criterion), Random Forest (ensemble)
- **Deep Learning:** DNN and 3-Layer MLP with BatchNorm, Dropout, EarlyStopping
- **Transformer-based:** Custom FT-Transformer (PyTorch) with CLS token, self-attention heads; TabNet with sequential attention

---

## 🚀 Getting Started

### Prerequisites
```bash
pip install -r requirements.txt
```

### Run the Notebook
1. Clone this repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/cloud-ddos-detection.git
   cd cloud-ddos-detection
   ```

2. Download the dataset from [Zenodo](https://zenodo.org/records/14681803) and place it in `data/`

3. Open the notebook:
   ```bash
   jupyter notebook notebooks/Cloud_Attacks_Code.ipynb
   ```

   Or run on **Google Colab** (recommended for GPU support):
   
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/cloud-ddos-detection/blob/main/notebooks/Cloud_Attacks_Code.ipynb)

---

## 🔑 Key Findings

- **Transformer-based models outperform** traditional ML and standard deep learning models for structured tabular cloud traffic data
- **TabNet** achieves the best overall performance (97.68%) through sequential attention-based feature selection
- **FT-Transformer** achieves competitive performance (96.18%) with a lighter, more flexible architecture — making it a strong choice for scalable cloud deployments
- Key discriminative features: `Inbound`, `Min Packet Length`, `Fwd Packets/s`, `Flow Duration`, `URG Flag Count`
- DDoS traffic exhibits **higher packet rates**, **shorter flow durations**, and **distinct packet size patterns** compared to benign traffic

---

## 🛠️ Tech Stack

| Category | Tools |
|----------|-------|
| Language | Python 3.x |
| Data Processing | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| ML Models | Scikit-learn |
| Deep Learning | TensorFlow / Keras |
| Transformer | PyTorch |
| TabNet | pytorch-tabnet |
| Environment | Google Colab / Jupyter |

---

## 👥 Authors

| Contributor | Role |
|-------------|------|
| **[Your Name]** | Research design, literature review, methodology, preprocessing pipeline, Decision Tree & Random Forest, DNN integration, report writing (Introduction, Related Work, Methodology) |
| **[Classmate Name]** | Full data pipeline implementation, DNN & MLP coding, FT-Transformer (PyTorch) implementation & tuning, TabNet implementation, hyperparameter optimization, EDA visualizations, report writing (Results, Evaluation, Conclusion) |

---

## 📚 Citation

If you use this work, please cite:

```bibtex
@article{cloudddos2025,
  title     = {Attention-Based Transformer Models for Cloud Malware Detection Using Network Traffic Data},
  author    = {[Your Name] and [Classmate Name]},
  year      = {2025},
  note      = {Masters Research Project},
  url       = {https://github.com/YOUR_USERNAME/cloud-ddos-detection}
}
```

---

## 📜 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 🔗 References

- Abuowaida et al. (2025) — Evidence detection in cloud forensics using ML
- Long et al. (2024) — Transformer-based network intrusion detection for cloud security
- Liang (2024) — DDoS Attack Detection Model Based on Transformer Architecture
- Dataset: [Zenodo Cloud DDoS Dataset](https://zenodo.org/records/14681803)

> ⭐ If you found this project useful, please consider giving it a star!

Project updated by contributor.
