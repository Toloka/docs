# CrowdLayer
`crowdkit.learning.crowd_layer.CrowdLayer` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/learning/crowd_layer.py#L87)

```python
CrowdLayer(
    self,
    num_labels: int,
    n_workers: int,
    conn_type: str = 'mw',
    device: Optional[device] = None,
    dtype: Optional[dtype] = None
)
```

CrowdLayer module for classification tasks.


This method applies a worker-specific transformation of the logits. There are four types of transformations:
- MW: Multiplication on the worker's confusion matrix.
- VW: Element-wise multiplication with the worker's weight vector.
- VB: Element-wise addition with the worker's bias vector.
- VW + b: Combination of VW and VB: VW * logits + b.

Filipe Rodrigues and Francisco Pereira. Deep Learning from Crowds.
*Proceedings of the AAAI Conference on Artificial Intelligence, 32(1),* 2018.
https://doi.org/10.1609/aaai.v32i1.11506


**Examples:**


```python
from crowdkit.learning import CrowdLayer
import torch
input = torch.randn(3, 5)
workers = torch.tensor([0, 1, 0])
cl = CrowdLayer(5, 2, conn_type="mw")
cl(input, workers)
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[forward](crowdkit.learning.crowd_layer.CrowdLayer.forward.md)| Forward pass.
