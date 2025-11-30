# Hybrid-Quantum-Classical-Transformer
Designed and implemented a full Decoder Transformer with a Quantum Neural Network (QNN) to replace the Feed-Forward Network (FNN).
Implemented with Pennylane and Pytorch using parameterized quantum circuits and variational optimization.
Pipelined output of Multi-Head Self-Attention into qubit dimension space with a linear transformation and encoded it into a quantum state using angle encoding. After QNN runs, the output is mapped back into the model’s hidden dimension.
Compared validation perplexity of the classical FFN and the QNN-augmented model; observed that despite the QNN’s dramatically lower dimensionality, its perplexity converges toward the classical model, suggesting that a dimension-constrained quantum network can still extract expressive, model-relevant features.
