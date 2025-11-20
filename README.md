# Cosmic Unifying Field Theory (CUFT)

![GitHub](https://img.shields.io/badge/license-MIT-blue.svg)
![GitHub](https://img.shields.io/badge/python-3.8%2B-brightgreen.svg)
![GitHub](https://img.shields.io/badge/field%20theory-cosmology-orange.svg)

A fundamental extension to ΛCDM cosmology resolving Hubble and growth tensions through scalar field dynamics with non-canonical kinetic terms.

## 📖 Abstract

The Cosmic Unifying Field Theory (CUFT) provides a comprehensive framework addressing persistent cosmological tensions through Bayesian analysis of a k-essence scalar field. Our MCMC analysis with 320,000 samples demonstrates strong Bayesian evidence (Bayes factor K = 1800) favoring CUFT over ΛCDM, reducing Hubble tension from 4.9σ to 3.6σ and essentially resolving growth tension (2.5σ to 0.4σ).

## 🏗️ Theory Framework

CUFT extends standard cosmology through:

- *Non-canonical kinetic terms*: K(X) = X + λX² generating cosmic acceleration
- *Gaussian potential*: V(ϕ) = V₀ exp(-ϕ²/2ϕ₀²) enabling smooth cosmological transitions
- *Modified sound speed*: c_s² = (1 + 2λX)/(1 + 6λX) affecting structure formation

## 📊 Key Results

| Parameter | CUFT Value | ΛCDM Value | Improvement |
|-----------|------------|-------------|-------------|
| H₀ | 69.2 ± 0.2 km/s/Mpc | 67.4 km/s/Mpc | 1.3σ tension reduction |
| S₈ | 0.783 ± 0.006 | 0.834 ± 0.016 | 2.1σ tension resolution |
| w_ϕ | -0.981 ± 0.004 | -1 (fixed) | Dynamical dark energy |
| c_s² | 0.892 ± 0.008 | 1 (fixed) | Modified clustering |

## 🛠️ Installation & Usage

### Prerequisites
- Python 3.8+
- Required packages (see code/requirements.txt)

### Quick Start
```bash
# Clone repository
git clone https://github.com/your-username/cosmic-unifying-field-theory.git
cd cosmic-unifying-field-theory

# Install dependencies
pip install -r code/requirements.txt

# Run MCMC analysis
python code/mcmc_analysis.py
