# Adversarial Robustness Toolbox (ART)

> Bibliothèque IBM pour la robustesse adversariale des modèles ML — attaques + défenses, multi-framework.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 16 - AI Security & Safety / Adversarial ML |
| **URL** | https://adversarial-robustness-toolbox.readthedocs.io |
| **GitHub** | https://github.com/Trusted-AI/adversarial-robustness-toolbox |
| **Stars** | ~5,900 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
ART est la bibliothèque de référence pour la robustesse adversariale des modèles ML. Développée par IBM et maintenue par la Linux Foundation, elle fournit des implémentations d'attaques adversariales ET de défenses pour PyTorch, TensorFlow et scikit-learn.

## Key Features
- **Attaques**: FGSM, PGD, C&W, DeepFool, etc.
- **Défenses**: Adversarial training, input preprocessing, detection
- **Multi-framework**: PyTorch, TensorFlow, scikit-learn
- **Académiquement rigoureux**: Implémentations de référence
- **MIT licence**: Aucune restriction
- **Certified defenses**: Défenses avec garanties

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, IBM/Linux Foundation |
| **Security** | 5 | MIT, référence académique |
| **Scalability** | 3 | Python, batch |
| **Support/Community** | 3 | 5.9k stars |
| **Documentation** | 4 | Docs complètes, notebooks |
| **Integration Ease** | 3 | Courbe d'apprentissage |

## Use Cases
1. **Adversarial testing** — Tester la robustesse des modèles ML
2. **Adversarial training** — Entraîner des modèles robustes
3. **Security audit** — Auditer la sécurité des modèles vision/NLP

## Getting Started
```python
from art.attacks.evasion import FastGradientMethod
from art.estimators.classification import PyTorchClassifier
classifier = PyTorchClassifier(model=model, loss=loss, input_shape=(3, 224, 224), nb_classes=10)
attack = FastGradientMethod(estimator=classifier, eps=0.3)
x_adv = attack.generate(x=x_test)
```

## Strengths
- Référence académique pour adversarial ML
- Attaques ET défenses
- Multi-framework
- MIT licence, IBM/Linux Foundation

## Limitations
- Plus orienté ML classique que LLM
- Courbe d'apprentissage
- Pas spécialisé GenAI

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Foolbox | Plus simple, PyTorch/TF |
| CleverHans | Google, plus ancien |

## References
- https://adversarial-robustness-toolbox.readthedocs.io
- https://github.com/Trusted-AI/adversarial-robustness-toolbox
