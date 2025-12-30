# Hybrid Quantum–Classical Decoder Transformer

This project explores a **hybrid quantum–classical decoder-only Transformer architecture** in which the classical **Feed-Forward Network (FFN)** inside each Transformer block is replaced with a **Quantum Neural Network (QNN)**.

The model is implemented using **PyTorch** and **PennyLane**, and trained end-to-end using standard gradient-based optimization.

---

## Motivation

Transformers are highly expressive sequence models, but they are also **computationally expensive**. A major contributor to this cost is the **Feed-Forward Network (FFN)** inside each Transformer block, which often dominates parameter count and compute.

This project investigates whether a **Quantum Neural Network (QNN)** can serve as a **compact alternative** to the classical FFN, while preserving the overall Transformer structure.

---

## High-Level Idea

The core idea is simple:

- Keep the **standard decoder-only Transformer**
- Replace the **classical FFN** with a **parameterized quantum circuit**
- Train the entire model jointly using classical optimization

Importantly, this work **does not claim quantum advantage**. Instead, it explores:
- Representational efficiency
- Parameter compression
- Hybrid quantum–classical design patterns

---

## Transformer Overview (Conceptual)

The model follows a standard **decoder-only Transformer** architecture:

- Causal (autoregressive) self-attention
- Multi-head attention
- Residual connections and layer normalization
- A feed-forward transformation (classical or quantum)

Tokens are processed using a **sliding context window**, and the model predicts the next token autoregressively.

---

## Hybrid Quantum–Classical Design

In the hybrid variant:

- Attention, embeddings, and residual structure remain **fully classical**
- The FFN is replaced by a **Quantum Neural Network**
- The QNN operates on a **low-dimensional projection** of each token
- Measurement results are mapped back to the model dimension via a linear layer

The QNN is implemented with **PennyLane**, while training and optimization are handled in **PyTorch** using **AdamW**.

---

## Implementation Notes

- Decoder-only Transformer
- Hybrid quantum–classical training loop
- Modular FFN / QNN swap
- Designed for experimentation and research exploration

---

## Mathematical Details

A full mathematical description of:
- Transformer attention
- Multi-head attention
- QNN encoding, circuit structure, and measurement

is provided in:

👉 **[`docs/paper.pdf`](docs/paper.pdf)**

This separation keeps the README clean while preserving full technical detail.
