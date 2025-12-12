# two_compartment_SNN

# Two-Compartment Spiking Neurons for Timing and Context

This project explores a simple question:

> If real neurons use **dendritic compartments** and **precise spike timing** to learn,  
> can adding these features to artificial neurons change how they solve tasks?

What's implemented:

- A **standard single-compartment spiking neuron** (LIF)
- A **two-compartment spiking neuron** with separate basal and apical inputs

This is evaluated on:

1. A **toy temporal coincidence task** (timing-based prediction)
2. The **MNIST** handwritten digit dataset with spiking dynamics

All models are implemented in **PyTorch** using **snnTorch** for spiking neuron primitives and surrogate gradients.

---

## Repository structure

- `Two_Compartment_Neuron_Toy_Problem_Global.ipynb`  
  Toy 1D timing task with:
  - Synthetic **BasalApicalDataset** (apical predicts basal with a delay)
  - Single-compartment SNN baseline
  - Two-compartment SNN
  - Ablation experiments (removing basal or apical input at test time)
  - Discussion of timing and compartment effects

- `Two_Compartment_Neuron_MNIST.ipynb`  
  MNIST task with:
  - Single-compartment SNN baseline
  - Two-compartment SNN where:
    - Basal and apical receive different pixel subsets
    - Or apical receives a **blurred / low-res** version of the image
    - Or apical receives **teacher predictions** as a context signal
  - Ablations: removing apical or basal input
  - Discussion of how apical “context” changes computation

> Both notebooks are designed to be **self-contained** and readable:  
> they include markdown explanations of the data, models, and experiments.

---

```bash
pip install torch torchvision snntorch matplotlib
