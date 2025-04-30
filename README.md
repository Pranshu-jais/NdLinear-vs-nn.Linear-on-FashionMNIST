# 🔍 NdLinear vs nn.Linear on FashionMNIST

This project benchmarks [NdLinear](https://github.com/ensemble-core/NdLinear), an open-source drop-in replacement for PyTorch’s `nn.Linear`, by evaluating its parameter efficiency and performance on the FashionMNIST dataset.

It was created as part of an application to Ensemble’s ML Research Internship (Summer/Fall 2025), focusing on demonstrating practical use and benchmarking of open-source ML tooling.

---

## 📁 Project Structure

- `ndlinear_fashionmnist.ipynb`: Main notebook containing the experiment and results
- `README.md`: Project overview
- `requirements.txt`: Dependencies (optional)

---

## 🧠 Objective

Evaluate how replacing `nn.Linear` layers with `NdLinear` affects:

- Model parameter count
- Training time
- Inference time
- Final classification accuracy

---

## ⚙️ Experimental Setup

### Models Compared:
1. **BaselineNN** – MLP with standard `nn.Linear` layers
2. **NdLinearNN** – Same architecture but uses `NdLinear` with reduced hidden dimensions for parameter efficiency

### Dataset:
- [FashionMNIST](https://github.com/zalandoresearch/fashion-mnist)
- 28x28 grayscale images, 10 clothing categories

---

## 📊 Results Summary

| Metric                | BaselineNN | NdLinearNN |
|-----------------------|------------|------------|
| **Parameter Count**   | 109,386    | 104,938    |
| **Training Time (s)** | 17.96      | 17.53      |
| **Inference Time (s)**| 2.33       | 2.32       |
| **Final Accuracy (%)**| 89.36%     | 89.49%     |

---

## ✅ Key Findings

- **NdLinear** preserved or slightly improved accuracy while reducing parameter count by ~4%.
- Training and inference times remained stable or slightly faster with NdLinear.
- This validates NdLinear as a practical alternative to `nn.Linear`, particularly when resource constraints or deployment efficiency are a concern.

---

## 💡 Why NdLinear?

NdLinear is designed to be a flexible, efficient replacement for `nn.Linear`, potentially enabling:

- Lower memory usage
- Faster inference on-device
- Layer compression through rank reduction (optional in advanced use cases)

🔗 Learn more: [https://github.com/ensemble-core/NdLinear](https://github.com/ensemble-core/NdLinear)

---

## 🚀 Getting Started

```bash
# Clone the repo
git clone https://github.com/yourusername/ndlinear-fmnist.git
cd ndlinear-fmnist

# Install dependencies
pip install torch torchvision matplotlib pandas ndlinear

# Run the notebook
jupyter notebook ndlinear_fashionmnist.ipynb
