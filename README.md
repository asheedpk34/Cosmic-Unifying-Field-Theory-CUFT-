#!/usr/bin/env python3
"""
GitHub Repository Setup Script for Cosmic Unifying Field Theory
Automates the entire process of creating a professional GitHub repository
"""

import os
import subprocess
import sys
from pathlib import Path

def run_command(command, check=True):
    """Run a shell command and return the result"""
    try:
        result = subprocess.run(command, shell=True, capture_output=True, text=True, check=check)
        return result
    except subprocess.CalledProcessError as e:
        print(f"Error running command: {command}")
        print(f"Error: {e}")
        return None

def check_prerequisites():
    """Check if required tools are installed"""
    print("🔍 Checking prerequisites...")
    
    # Check if git is installed
    git_check = run_command("git --version", check=False)
    if git_check and git_check.returncode == 0:
        print("✅ Git is installed")
    else:
        print("❌ Git is not installed. Please install Git first.")
        return False
    
    # Check if GitHub CLI is installed (optional but recommended)
    gh_check = run_command("gh --version", check=False)
    if gh_check and gh_check.returncode == 0:
        print("✅ GitHub CLI is installed")
        return True
    else:
        print("⚠️  GitHub CLI is not installed. Will use manual GitHub setup.")
        return True

def create_directory_structure(base_path):
    """Create the complete directory structure"""
    print("📁 Creating directory structure...")
    
    directories = [
        "manuscript/figures",
        "code", 
        "data/processed",
        "docs",
        "tests"
    ]
    
    for directory in directories:
        dir_path = base_path / directory
        dir_path.mkdir(parents=True, exist_ok=True)
        print(f"  Created: {dir_path}")

def create_readme(base_path):
    """Create the comprehensive README.md file"""
    readme_content = '''# Cosmic Unifying Field Theory (CUFT)

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
git clone https://github.com/{username}/cosmic-unifying-field-theory.git
cd cosmic-unifying-field-theory

# Install dependencies
pip install -r code/requirements.txt

# Run MCMC analysis
python code/mcmc_analysis.py
