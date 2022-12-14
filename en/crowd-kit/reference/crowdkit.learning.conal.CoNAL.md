# CoNAL
`crowdkit.learning.conal.CoNAL` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.0/crowdkit/learning/conal.py#L38)

```python
CoNAL(
    self,
    num_labels: int,
    n_workers: int,
    com_emb_size: int = 20,
    user_feature: Optional[...] = None
)
```

Common Noise Adaptation Layers (CoNAL). This method introduces two types of confusions: worker-specific and


global. Each is parameterized by a confusion matrix. The ratio of the two confusions is determined by the
common noise adaptation layer. The common noise adaptation layer is a trainable function that takes the
instance embedding and the worker ID as input and outputs a scalar value between 0 and 1.

Zhendong Chu, Jing Ma, and Hongning Wang. Learning from Crowds by Modeling Common Confusions.
*Proceedings of the AAAI Conference on Artificial Intelligence*, 35(7), 5832-5840, 2021.
https://doi.org/10.1609/aaai.v35i7.16730


**Examples:**


```python
from crowdkit.learning import CoNAL
import torch
input = torch.randn(3, 5)
workers = torch.tensor([0, 1, 0])
embeddings = torch.randn(3, 5)
conal = CoNAL(5, 2)
conal(embeddings, input, workers)
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[forward](crowdkit.learning.conal.CoNAL.forward.md)| Forward pass of the CoNAL module.
[simple_common_module](crowdkit.learning.conal.CoNAL.simple_common_module.md)| Common noise adoptation module.
