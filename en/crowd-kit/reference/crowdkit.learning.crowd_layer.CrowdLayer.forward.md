# forward
`crowdkit.learning.crowd_layer.CrowdLayer.forward` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.0/crowdkit/learning/crowd_layer.py#L154)

```python
forward(
    self,
    outputs: Tensor,
    workers: Tensor
)
```

Forward pass.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`outputs`|**Tensor**|<p>Tensor of shape (batch_size, input_dim)</p>
`workers`|**Tensor**|<p>Tensor of shape (batch_size,) containing the worker IDs.</p>

* **Returns:**

  Tensor of shape (batch_size, num_labels)

* **Return type:**

  Tensor
