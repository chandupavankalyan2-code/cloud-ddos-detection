# Contributing

This repository is a collaborative academic project by two co-authors. Below is how we structured our collaboration.

## Co-Authors

**Contributor 1 — Research & Theory**
- Conceptual design and literature-driven foundation
- Identified the research gap in cloud DDoS detection
- Proposed the use of FT-Transformer and TabNet models
- Structured the preprocessing pipeline methodology
- Implemented Decision Tree and Random Forest baseline models
- Assisted in DNN architecture design and validation
- Comparative analysis and interpretation
- Report: Introduction, Related Work, Methodology sections

**Contributor 2 — Implementation & Optimization**
- Full data pipeline: loading, preprocessing, feature selection, scaling
- Deep learning models: DNN and 3-layer MLP (with BatchNorm, Dropout, EarlyStopping)
- FT-Transformer implementation in PyTorch (embeddings, attention heads, LR scheduling)
- TabNet model implementation and tuning
- Hyperparameter tuning and optimization
- EDA visualizations and confusion matrices
- Report: Results, Evaluation, Conclusion sections

## How to Collaborate on GitHub

If you'd like to contribute bug fixes or improvements:

1. Fork this repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m "Add: short description"`
4. Push to your fork: `git push origin feature/your-feature-name`
5. Open a Pull Request

Please open an Issue first if you're proposing major changes.
