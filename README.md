# Computational Pathology Tutorial

<p align="center">
  <img src="assets/images/pipeline.svg" alt="Computational pathology pipeline" width="100%">
</p>

Beginner-friendly, project-based training for people with:
- limited computer science background, or
- limited medical/pathology background.

## Why This Project

Computational pathology is highly impactful, but most learning resources assume strong experience in either medicine or coding. This repository bridges both gaps with step-by-step modules, practical notebooks, and publishable outputs.

## Who This Is For

- Medical learners who want to learn coding and ML for pathology.
- Technical learners who want to understand pathology workflow and clinical context.
- Educators who want reusable materials for classes and workshops.

## Learning Outcomes

By completing this tutorial, learners should be able to:
- explain core pathology and machine learning concepts in plain language,
- run a reproducible baseline computational pathology pipeline,
- evaluate model outputs with clinically relevant reasoning,
- build a small capstone project and present/publicize it.

## Repository Map

```text
00_start_here/                   onboarding + learning pathways
01_foundations/                  medicine-for-CS and CS-for-medicine bridge modules
02_data_ethics_reproducibility/  bias, governance, and reproducible workflows
03_hands_on/                     notebooks, source code, configs, tests
04_case_studies/                 guided case studies + capstone projects
05_publish/                      website, slides, manuscript for impact
assets/                          figures and images used across the project
data/                            tutorial-safe sample data and datasheets
glossary/                        plain-language term definitions
references/                      reading lists and citations
community/                       contribution and learner support docs
```

## Quick Start

1. Read `00_start_here/README.md`.
2. Choose your path in `00_start_here/learning_paths.md`.
3. Start with `03_hands_on/notebooks/01_tutorial_starter.ipynb`.
4. Move to `04_case_studies/01_guided` and then `04_case_studies/02_capstone`.
5. Publish your outputs from `05_publish/`.

## Quick Taste (Single Code Block)

```python
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn.pipeline import make_pipeline
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score

np.random.seed(42)
X = np.random.normal(size=(200, 12))
y = (X[:, 0] + 0.5 * X[:, 1] > 0).astype(int)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, stratify=y, random_state=42)
model = make_pipeline(StandardScaler(), LogisticRegression(max_iter=1000))
model.fit(X_train, y_train)
print("Baseline accuracy:", round(accuracy_score(y_test, model.predict(X_test)), 3))
```

## Advanced Methods (Planned)

This tutorial will also include advanced modules for modern pathology AI:
- Self-supervised learning (SSL) encoders, including UNI and other foundation encoders.
- Diffusion-based models (for example, PixCell) to generate synthetic pathology tiles for augmentation and experimentation.
- Practical comparison of baseline vs foundation-model pipelines in realistic case studies.

## Publication-Ready Outputs

`05_publish/` is where final impact assets live:
- `website/`: public tutorial/docs site.
- `slides/`: workshop, class, or conference presentation.
- `manuscript/`: report, paper, or preprint draft.

## Project Status

- [x] Core folder scaffold created
- [x] Starter notebook template added
- [ ] First full foundations module
- [ ] First guided case study
- [ ] Public website and slide deck

## License

This project is released under the [MIT License](LICENSE).
