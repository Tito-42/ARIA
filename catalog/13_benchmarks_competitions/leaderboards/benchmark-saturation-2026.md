# État des Benchmarks IA (Avril 2026) - Saturation et Nouveaux Frontières

> Synthèse des benchmarks saturés vs ceux qui discriminent encore les modèles

## Benchmarks Saturés (ne discriminent plus)

| Benchmark | Top Score | Modèle | Statut |
|-----------|-----------|--------|--------|
| **HumanEval** (code gen) | 99.3% | o4-mini-high | Essentiellement résolu |
| **MATH** | 98.2% | o4-mini-high | Essentiellement résolu |
| **MMLU** | 93.3% | o3-high | Saturé (85-93% pour frontier models) |
| **MGSM** (multilingue) | 93.5% | o4-mini-high | Quasi-saturé |

## Benchmarks Discriminants (la nouvelle frontière)

| Benchmark | Top Score | Modèle | Pourquoi c'est important |
|-----------|-----------|--------|-------------------------|
| **SWE-bench Pro** | 80.8% | Claude Opus 4.6 | Issues GitHub réelles, multi-step |
| **SWE-bench Verified** | ~80% | SE-Agent | Agents autonomes |
| **GPQA** (graduate-level) | 83.4% | o3-high | Questions niveau doctorat |
| **ARC-AGI-2** | ~53% (best) | Hybrid approaches | Intelligence fluide, loin de résolu |
| **SimpleQA** (factual) | 62.5% | GPT-4.5-preview | Exactitude factuelle, très dur |
| **DROP** (reading comp) | 90.2% | o1 | Compréhension de lecture avancée |

## OpenAI Simple-Evals - Tableau Complet

| Model | MMLU | GPQA | MATH | HumanEval | MGSM | DROP | SimpleQA |
|-------|------|------|------|-----------|------|------|----------|
| **o3-high** | 93.3 | 83.4 | 98.1 | 88.4 | 92.0 | 89.8 | 48.6 |
| **o4-mini-high** | 90.3 | 81.3 | 98.2 | **99.3** | 93.5 | 78.1 | 19.3 |
| **o1** | 91.8 | 75.7 | 96.4 | -- | 89.3 | **90.2** | 42.6 |
| **GPT-4.5-preview** | 90.8 | 69.5 | 87.1 | 88.6 | 86.9 | 83.4 | **62.5** |
| **gpt-4.1** | 90.2 | 66.3 | 82.1 | 94.5 | 86.9 | 79.4 | 41.6 |
| **Claude 3.5 Sonnet** | 88.3 | 59.4 | 71.1 | 92.0 | 91.6 | 87.1 | 28.9 |
| **Llama 3.1 405b** | 88.6 | 50.7 | 73.8 | 89.0 | 91.6 | 84.8 | n/a |

*Source: https://github.com/openai/simple-evals (maintenance mode depuis juillet 2025)*

## Tendances Clés pour l'Enterprise

1. **Ne plus évaluer sur MMLU/HumanEval** : tous les modèles frontier y excellent
2. **SWE-bench Pro** est le gold standard pour le coding agentique
3. **ARC-AGI** reste le test d'intelligence générale le plus dur
4. **SimpleQA** discrimine sur l'exactitude factuelle (important pour enterprise)
5. **GPQA** discrimine sur le raisonnement scientifique avancé
6. **Le coût par token** est devenu aussi important que la performance brute

## References
- [OpenAI Simple-Evals](https://github.com/openai/simple-evals)
- [SWE-bench](https://www.swebench.com)
- [LM Arena](https://lmarena.ai)
- [ARC Prize](https://arcprize.org)
