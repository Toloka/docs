# forward
`crowdkit.learning.conal.CoNAL.forward` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/learning/conal.py#L117)

```python
forward(
    self,
    embeddings: Tensor,
    logits: Tensor,
    workers: Tensor
)
```

Forward pass of the CoNAL module.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`embeddings`|**Tensor**|<p>Tensor of shape (batch_size, embedding_size)</p>
`logits`|**Tensor**|<p>Tensor of shape (batch_size, num_classes)</p>
`workers`|**Tensor**|<p>Tensor of shape (batch_size,) containing the worker IDs.</p>

* **Returns:**

  Tensor of shape (batch_size, 1) containing the predicted output probabilities.

* **Return type:**

  Tensor
