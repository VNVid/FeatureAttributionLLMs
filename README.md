# Feature Attribution for Fine-Tuned Large Language Models (LLMs)

This repository explores feature-attribution (FA) techniques applied to fine-tuned large language models (LLMs). It combines a survey of FA methods with a practical experiment, offering insights into their computational efficiency and explanatory power.

## Project Overview

Understanding how LLMs make decisions is critical for building transparent and trustworthy AI systems. Feature-attribution methods assign importance scores to input features, highlighting their contribution to a model's predictions. This project investigates four major categories of FA techniques and evaluates their applicability to modern fine-tuned LLMs.

### Key Components:
1. **Survey of Feature Attribution Techniques**:
   - Covers perturbation-based, gradient-based, surrogate model, and decomposition-based methods.
   - Highlights principles, challenges, and adaptations for LLMs.
2. **Experimentation**:
   - Compares two FA methods: **Feature Ablation** and **Shapley Value Sampling**.
   - Evaluates their performance on the **Stanford Sentiment Treebank (SST-2)** dataset.
   - Focuses on computation time and sufficiency metrics to assess the quality of explanations.

## Methodology

### Survey
The survey systematically explores existing literature, identifying gaps and promising research directions. It emphasizes the computational trade-offs and alignment challenges of applying FA methods to generative LLMs with large input contexts.

### Experiment
An experiment was conducted using the [Mistral-7B-Instruct-v0.2](https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.2) model to analyze two FA methods:
- **Feature Ablation**: Removes input features sequentially to measure their impact.
- **Shapley Value Sampling**: Estimates feature importance using cooperative game theory principles.

### Setup
- **Platform**: Google Colab with memory-efficient quantization (BitsAndBytes).
- **Task**: Sentiment classification on SST-2.
- **Prompts**: Explicitly structured to ensure consistent responses.
- **Metrics**:
  - **Computation Time**: Time taken to compute saliency scores.
  - **Sufficiency**: Model accuracy using only the most salient tokens.

### Results
| Method                 | Avg. Computation Time (s) | Sufficiency |
|------------------------|---------------------------|-------------|
| Feature Ablation       | 71.6                      | 0.2         |
| Shapley Value Sampling | 354.5                     | 0.0         |

- **Key Findings**:
  - Feature Ablation is faster and moderately effective compared to Shapley Value Sampling.
  - Shapley Value Sampling struggles with computation time and accuracy under limited sampling.

  ## Repository Structure

- `survey/`
  - `feature_attribution_survey.pdf`: Comprehensive review of FA methods.
- `experiment/`
  - `experiment.ipynb`: Implementation of FA methods experiment.
  - `results/`: Experimental results and visualizations.
- `README.md`: Project documentation and instructions.
