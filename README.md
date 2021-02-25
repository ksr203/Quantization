# Quantization

Quantization attempts to reduce the bit-width of the data in Neural Network, mapping input values from a large set (often a continuous set) to output values in a (countable) smaller set

With this, we can achieve Memory saving, Simplification of computation

But quantization causes accuracy drop.

It is important to think about the trade-off between compression and an accuracy drop

Quantization is conducted in 3 steps,

1. Choose the representable range

2. Determine the discrete level

3. how to project the (input) data

# Choose the representable range

Generally, clipping 0.01~0.001% highest & lowest parameters performs well

(https://developer.nvidia.com/gtc/2020/video/s22075)

But, it depends on dataset and model

# Determine the discrete level

Uniform quantization is widely used because it is easy to implementation ex) INT quantization

except for uniform quantization, logarithmic or other non-uniform quantization can be used.

Logarithmic convert costly MUL operation to simple ADD operation but consequent accumulation operation becomes non-straightforward

The other non-uniform distribution have an irregular distribution pattern, so it has Stronger adaptivity but is more complex than other methods 

# how to project the (input) data

Deterministic quantization Projects high-precision data to the nearest discrete level

It is most widely used because it makes less quantization loss.

On the other hand, stochastic quantization can be used.

Stochastic quantization calculates a possibility to approach one of the two nearest discrete levels Statistically, expect better results due to unbiased estimation

It is mostly used in quantization on training.
