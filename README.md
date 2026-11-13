
# American Option Pricing Using Reinforcement Learning

**Master's Thesis | M.Sc. Operations Research and Business Analytics | 2023**

This repository contains the Python implementations associated with my master's thesis, *American Option Pricing by using Reinforcement Learning*, submitted at Otto von Guericke University Magdeburg in February 2023.

The research explores the valuation of American put options and the optimal early-exercise decision using traditional numerical pricing methods, Monte Carlo simulation, and reinforcement-learning techniques.

> **Project status:** Historical academic research and portfolio demonstration. The original notebooks and their saved outputs are preserved. The implementations have not been independently reproduced or validated as production-grade pricing models.

## Research Objective

American options allow their holders to exercise at any point up to maturity. This flexibility introduces an optimal stopping problem: at each time step, the holder must decide whether to exercise the option or continue holding it.

This thesis investigates:

- The pricing of American and European put options using binomial trees.
- Simulation of possible underlying stock-price paths using Monte Carlo methods.
- Visualization of optimal exercise boundaries.
- Reinforcement-learning approaches to American put option exercise decisions.
- Comparison of historical numerical outputs and the estimated value associated with early exercise.

## Methodology

### 1. Binomial Tree Pricing
Construct binomial pricing models for American and European put options, accounting for the early-exercise decision in the American case.

### 2. Monte Carlo Simulation and Exercise Boundaries
Simulate underlying stock-price paths and examine the exercise-versus-continuation decision for American put options.

### 3. Reinforcement Learning
Model the exercise decision in a custom OpenAI Gym environment, with discrete hold/exercise actions and a PyTorch neural network used in the agent implementation.

The thesis describes this approach as a Deep Q-Network (DQN). However, the preserved notebook uses a policy/value network with policy-gradient-style losses, and its implementation requires additional verification before it can be treated as a validated DQN algorithm.

### 4. Comparative Evaluation
Compare the historical numerical results from the binomial, simulation, and reinforcement-learning experiments.

## Results Reported in the Thesis

The following values are from Table 4 of the submitted thesis (Chapter 5). They are illustrative historical results, not newly reproduced benchmarks.

| Method | Option Type | Reported Value |
| --- | --- | ---: |
| Binomial Tree | American Put | €3.96 |
| Binomial Tree | European Put | €3.84 |
| Reinforcement Learning (thesis-labelled DQN) | American Put | €4.09 |
| Monte Carlo Simulation | European Put | €3.58 |

The thesis reports a €0.51 difference between the reinforcement-learning American put estimate and the Monte Carlo European put estimate, and a €0.12 difference between the corresponding binomial estimates.

These differences are descriptive comparisons of the reported outputs; they do not by themselves establish superior pricing accuracy or trading profitability. Simulation results may vary across runs.

## Repository Contents

| File | Description |
| --- | --- |
| [Code for American Option Pricing by using Reinforcement Learning.ipynb](Code%20for%20American%20Option%20Pricing%20by%20using%20Reinforcement%20Learning.ipynb) | Binomial pricing, Monte Carlo simulation, exercise-boundary analysis, and the reinforcement-learning experiment |
| [American option graph.ipynb](American%20option%20graph.ipynb) | Visualizations related to option positions and payoff diagrams |

## Tools and Technologies

- Python and Jupyter Notebook
- NumPy, SciPy, Matplotlib, and Seaborn
- PyTorch for the neural-network implementation
- OpenAI Gym for the custom option-exercise environment
- Binomial tree methods and Monte Carlo simulation

## Reproducibility and Limitations

The notebooks represent the original historical research environment rather than a fully reproducible modern software package.

- The reinforcement-learning notebook explicitly requires Gym 0.25.2, and current library versions may require code changes.
- Randomized simulations can produce different numerical outputs on repeated runs.
- Some implementation details, including the reinforcement-learning update, action selection, and payoff estimation, require verification.
- The method referred to as DQN in the thesis does not correspond directly to a conventional DQN implementation in the saved notebook.
- The original comparisons do not independently establish pricing accuracy against a converged benchmark.

The project is intended for research communication, learning, and portfolio demonstration, not for live trading or investment decisions.

## Academic Context

**Thesis:** American Option Pricing by using Reinforcement Learning  
**Degree:** Master of Science, Operations Research and Business Analytics  
**University:** Otto von Guericke University Magdeburg  
**Submission date:** 27 February 2023  
**Supervisor:** Professor Dr. Elmar Lukas


## Thesis Availability

This repository provides the Python notebooks, methodology overview, and selected historical results associated with my master's thesis. The complete thesis document is not publicly distributed through this repository.

The research summary and implementation details are provided for academic discussion, technical review, and portfolio demonstration.

## Future Research Directions

- Review and correct the reinforcement-learning implementation and algorithm classification.
- Establish reproducible environments and random seeds.
- Compare prices against converged binomial-tree or other validated numerical benchmarks.
- Evaluate pricing errors, exercise-policy quality, variance, and computational efficiency across multiple parameter scenarios.
- Extend the analysis to broader option-pricing environments.

## Acknowledgments

I am grateful to Professor Dr. Elmar Lukas for his academic supervision and guidance. The research also draws on the academic literature and technical resources cited in the original thesis.
  
