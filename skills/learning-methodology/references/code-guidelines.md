# Code Guidelines — Progressive Python Examples

## General Principles

### Every Script Must Be Runnable
- Include all imports at the top
- Include a `if __name__ == "__main__":` block
- Use `main()` function for the entry point
- Print intermediate results so learners can see what's happening
- Include expected output as comments at the bottom

### Comment Philosophy
- Explain **why**, not **what** (the code shows what)
- Use section headers with `# ===` separators for major sections
- Add shape annotations for tensor operations: `# (batch, channels, height, width)`
- Explain mathematical connections: `# This is the reconstruction loss from L4 eq. 3`

### Code Structure Template

```python
"""
<Concept> — <Level Description>

This script demonstrates <what it does>.
Prerequisites: pip install <packages>

Corresponds to: <which .md level>
"""

import numpy as np
# ... other imports

# ============================================================
# Section 1: <Name>
# ============================================================

# ... code with inline comments

# ============================================================
# Section 2: <Name>
# ============================================================

# ... code with inline comments

# ============================================================
# Main: Run the full example
# ============================================================

def main():
    """Run the complete example with explanatory prints."""
    print("=" * 60)
    print("<Concept> — <Level>")
    print("=" * 60)

    # Step 1: ...
    print("\n--- Step 1: <Name> ---")
    # ... code
    print(f"Result: {result}")
    print(f"Shape: {result.shape}")

    # Step 2: ...
    print("\n--- Step 2: <Name> ---")
    # ... code

if __name__ == "__main__":
    main()
```

## High-Level Code (Level 5) Guidelines

### Framework Usage
- Use PyTorch as the primary framework
- Use sklearn for classical ML concepts
- Use matplotlib for visualizations
- Keep dependencies minimal and standard

### Structure
```python
"""
<Concept> — High-Level Implementation (PyTorch)
"""
import torch
import torch.nn as nn
import torch.optim as optim

# ============================================================
# Model Definition
# ============================================================
class ConceptModel(nn.Module):
    """
    <Brief description of the model>.

    Architecture:
        Input -> [layers] -> Output
    """
    def __init__(self, input_dim, hidden_dim, latent_dim):
        super().__init__()
        # ... define layers with comments explaining each

    def forward(self, x):
        # ... forward pass with shape comments

# ============================================================
# Training
# ============================================================
def train(model, data_loader, epochs=50, lr=1e-3):
    """Train the model and print progress."""
    optimizer = optim.Adam(model.parameters(), lr=lr)

    for epoch in range(epochs):
        # ... training loop
        if epoch % 10 == 0:
            print(f"Epoch {epoch}: Loss = {loss:.4f}")

# ============================================================
# Evaluation & Visualization
# ============================================================
def evaluate(model, test_data):
    """Evaluate and visualize results."""
    # ... evaluation with printed metrics

# ============================================================
# Main
# ============================================================
def main():
    # Use a simple, well-known dataset
    # Print architecture summary
    # Train with visible progress
    # Show results
    pass

if __name__ == "__main__":
    main()
```

### Key Principles
- Use `nn.Module` properly with `__init__` and `forward`
- Print model architecture using `print(model)`
- Show tensor shapes at key points
- Use small datasets for fast execution (MNIST, synthetic data)
- Training should complete in < 2 minutes on CPU
- Include visualization if relevant (matplotlib)

## From-Scratch Code (Level 6) Guidelines

### No Framework Abstractions
- Use only NumPy (and matplotlib for visualization)
- Implement forward pass manually
- Implement backward pass / gradient computation manually
- Implement optimizer step manually

### Structure
```python
"""
<Concept> — From Scratch (NumPy only)

This builds <concept> without any ML framework to reveal
what happens under the hood.

What we implement manually:
- Forward pass (matrix multiplications, activations)
- Loss computation
- Backward pass (gradient calculation via chain rule)
- Parameter updates (gradient descent)
"""
import numpy as np

# ============================================================
# Building Blocks (what nn.Module hides)
# ============================================================

def linear(x, W, b):
    """
    Manual linear layer: y = xW + b

    What nn.Linear does internally.
    """
    return x @ W + b  # (batch, in) @ (in, out) + (out,) -> (batch, out)

def relu(x):
    """
    ReLU activation: max(0, x)

    What nn.ReLU does internally.
    """
    return np.maximum(0, x)

def relu_grad(x):
    """Gradient of ReLU: 1 if x > 0, else 0."""
    return (x > 0).astype(float)

# ============================================================
# Model
# ============================================================
class ManualModel:
    """
    <Concept> implemented with raw NumPy.

    Compare with the PyTorch version in 01_<concept>_highlevel.py
    """
    def __init__(self, dims):
        # Xavier initialization (what PyTorch does by default)
        self.weights = []
        self.biases = []
        for i in range(len(dims) - 1):
            scale = np.sqrt(2.0 / dims[i])
            self.weights.append(np.random.randn(dims[i], dims[i+1]) * scale)
            self.biases.append(np.zeros(dims[i+1]))

    def forward(self, x):
        """Forward pass — store intermediates for backward pass."""
        self.activations = [x]
        for W, b in zip(self.weights, self.biases):
            x = linear(x, W, b)
            x = relu(x)
            self.activations.append(x)
        return x

    def backward(self, grad_output, learning_rate=0.001):
        """
        Backward pass — compute gradients via chain rule.

        This is what loss.backward() + optimizer.step() does.
        """
        # ... manual gradient computation

# ============================================================
# Main
# ============================================================
def main():
    print("Building <concept> from scratch with NumPy")
    print("This reveals what PyTorch hides behind nn.Module\n")
    # ... run example with explanatory prints
```

### Key Principles
- Comment every operation with its mathematical meaning
- Show shapes at every step: `# (batch, 784) @ (784, 128) -> (batch, 128)`
- Compare output with the high-level version to verify correctness
- Explain WHY each gradient term exists (connect to chain rule)
- Use smaller data/epochs since NumPy is slower
- Print loss values to show convergence

## Naming Conventions

### File Names
- `01_<concept>_highlevel.py` — PyTorch/framework version
- `02_<concept>_from_scratch.py` — NumPy-only version
- `03_<concept>_<variation>.py` — Variations (e.g., `03_variational_ae.py`)
- Use underscores, lowercase, no spaces
- Number prefix for ordering

### Variable Names
- Use descriptive names: `encoder_output` not `enc_out`
- Match mathematical notation where sensible: `z` for latent, `x_hat` for reconstruction
- Add `_grad` suffix for gradient variables: `loss_grad`, `w1_grad`

## Dataset Guidelines

### For Deep Learning Concepts
- MNIST (28x28 grayscale, 10 classes) — fast, universally known
- Synthetic data (random gaussians, spirals) — for pure concept demos
- CIFAR-10 only if color channels matter for the concept

### For Classical ML Concepts
- Iris dataset — for classification
- Boston/California housing — for regression
- Synthetic 2D data — for visualization-friendly demos

### Rules
- Dataset must be downloadable via code (no manual downloads)
- Include a fallback to synthetic data if download fails
- Keep data small enough for CPU-only execution
