# Attention-Mechanism

Implementing the General Attention Mechanism with NumPy and SciPy

The attention mechanism is a machine learning technique that was introduced to improve the performance of the encoder-decoder model for machine translation. The idea behind the attention mechanism is to permit the decoder to utilize the most relevant parts of the input sequence in a flexible manner, by a weighted combination of all the encoded input vectors, with the most relevant vectors being attributed the highest weights. The attention mechanism can be generalized for tasks where the information may not necessarily be related in a sequential fashion.

The attention mechanism is an Encoder-Decoder kind of neural network architecture that allows the model to focus on specific sections of the input while executing a task. It dynamically assigns weights to different elements in the input, indicating their relative importance or relevance.

![Attention-Mechanism](/images/Attention-Mechanism.png)

The attention mechanism is a powerful concept in machine learning, particularly in the context of sequence-to-sequence tasks.

The attention mechanism was introduced by Bahdanau et al. in 2014 to address a limitation in the use of fixed-length encoding vectors in sequence-to-sequence models. In traditional models, such as those based on recurrent neural networks (RNNs), a fixed-length context vector is used to summarize the entire input sequence. However, this approach becomes problematic for long or complex sequences, where compressing all relevant information into a fixed-size vector is challenging.
Here’s how the attention mechanism works:


**1. Alignment Scores:**

- The attention model computes alignment scores between the encoded hidden states (mathbfhi​) and the previous decoder output (mathbfst−1​).
- These scores indicate how well each element of the input sequence aligns with the current output position (t).
- The alignment model uses a function (often implemented as a feedforward neural network) to compute these scores:

  ![Formula-01](/images/01.png)




**2. Weights:**

- The alignment scores are then transformed into weights (alphat,i​) using a softmax operation:

  ![Formula-02](/images/02.png)

- These weights represent the importance of each encoded input vector in contributing to the context vector.



**3. Context Vector:**

- At each time step, a unique context vector (mathbfct​) is computed.
- The context vector is a weighted sum of all the encoder hidden states:

  ![Formula-03](/images/03.png)​

- Here, T represents the total number of time steps in the input sequence.


The context vector is then fed into the decoder, allowing it to focus on relevant parts of the input sequence during decoding. Unlike fixed-length context vectors, attention-based context vectors adaptively attend to different parts of the input sequence based on the decoder’s needs.
Generalization and Implementation
The attention mechanism is not limited to sequential data. It can be generalized for tasks where information may not necessarily be related sequentially. For example, it has been successfully applied to natural language translation, image captioning, and more.

To implement the attention mechanism, you can follow these steps:

1. Compute alignment scores using an alignment function (usually an MLP).
2. Transform alignment scores into weights using softmax.
3. Compute the context vector as a weighted sum of encoder hidden states.
