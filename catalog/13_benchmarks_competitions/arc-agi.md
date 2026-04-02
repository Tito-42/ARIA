# ARC-AGI (Abstraction and Reasoning Corpus)

> The leading benchmark for measuring artificial general intelligence through visual pattern recognition and abstract reasoning tasks.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 13 - Benchmarks & Competitions |
| **URL** | https://arcprize.org |
| **GitHub** | https://github.com/fchollet/ARC-AGI (v1) / https://github.com/arcprize/ARC-AGI (v3 toolkit) |
| **Stars** | ~3,300+ (combined) |
| **License** | Apache 2.0 |
| **Pricing** | Free (open benchmark); $1M+ prize fund |
| **Last Verified** | 2026-04-01 |
| **Status** | Active (ARC-AGI-3 is current iteration) |
| **Maturity** | Production |

## What It Does
ARC-AGI (Abstraction and Reasoning Corpus for Artificial General Intelligence) is a benchmark created by Francois Chollet to measure general fluid intelligence in AI systems. It presents grid-based visual puzzles where AI systems must infer abstract rules from a small number of input-output demonstration pairs and apply those rules to novel test inputs.

The benchmark is designed to resist "shortcut" solutions -- tasks require genuine abstraction and reasoning rather than pattern matching from training data. Each task uses integer grids (0-9 representing colors, 1x1 to 30x30) with typically 3 training pairs and 1-2 test pairs. A task is solved only when the AI produces exact correct outputs on first viewing (up to 2-3 attempts).

## Versions
- **ARC-AGI-1**: Original 800-task benchmark (400 training + 400 evaluation)
- **ARC-AGI-2**: 1,000 public training + 120 evaluation + private test sets; human performance ~66%
- **ARC-AGI-3**: Current iteration with interactive environments and API-based toolkit (v0.9.6, March 2026)

## Key Features
- **Grid-based puzzles**: Visual pattern recognition requiring abstract reasoning
- **Few-shot format**: Typically 3 examples, then solve new test cases
- **Core Knowledge priors**: Based on objectness, goal-directedness, arithmetic, geometry
- **Multiple difficulty levels**: Tasks range from simple to extremely challenging
- **Human-validated**: Average human performance ~66% on evaluation set
- **Resistance to shortcuts**: Designed to require genuine reasoning, not memorization
- **ARC-AGI-3 toolkit**: Python API for building and testing agents (local + competition modes)

## Scoring (ARC-AGI-3)
- Individual level scores are squared, then weighted by level index
- Competition mode requires level resets (not full game resets) and single-game interactions
- Scorecard tracking via `get_scorecard()` method

## Winning Approaches and State of the Art
The benchmark has driven innovation in several approaches:

1. **Program synthesis**: Generating and testing programs that transform inputs to outputs
2. **Neural program induction**: Learning to induce programs from examples
3. **LLM-based reasoning**: Using large language models with chain-of-thought reasoning
4. **Hybrid approaches**: Combining neural networks with symbolic reasoning
5. **Test-time compute**: Generating many candidate solutions and selecting the best
6. **Domain-specific languages**: Creating DSLs for grid transformations

As of early 2026, no approach has achieved human-level performance, though the gap is narrowing with each competition cycle. The $1M+ ARC Prize continues to incentivize research.

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Research Value** | 5 | The definitive benchmark for measuring reasoning capability |
| **Practical Impact** | 4 | Solutions advance general-purpose reasoning in AI systems |
| **Community** | 4 | Active competition community; Kaggle integration |
| **Reproducibility** | 5 | Public datasets; standardized evaluation |

## Use Cases
1. **AI research** - Measuring progress toward artificial general intelligence
2. **Agent evaluation** - Testing agent reasoning and abstraction capabilities
3. **Competition** - Kaggle and ARC Prize competitions with significant prize pools
4. **Benchmark** - Comparing reasoning capabilities across LLMs and approaches

## References
- https://arcprize.org
- https://github.com/fchollet/ARC-AGI
- https://github.com/arcprize/ARC-AGI
- https://arxiv.org/abs/1911.01547 (On the Measure of Intelligence - Chollet)
- https://www.kaggle.com/competitions/arc-prize-2024

## Notes
ARC-AGI remains the gold standard for measuring genuine AI reasoning capability. Unlike saturated benchmarks (MMLU, HumanEval), ARC-AGI continues to challenge state-of-the-art systems. The progression from ARC-AGI-1 to ARC-AGI-3 (with interactive environments) shows the benchmark evolving alongside AI capabilities. For agent framework developers, ARC-AGI performance is a meaningful signal of reasoning quality. The competition's prize fund and community continue to drive innovation in reasoning, program synthesis, and abstraction.
