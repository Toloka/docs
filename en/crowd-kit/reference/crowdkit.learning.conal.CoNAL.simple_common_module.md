# simple_common_module
`crowdkit.learning.conal.CoNAL.simple_common_module` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.0/crowdkit/learning/conal.py#L94)

```python
simple_common_module(
    self,
    input: Tensor,
    workers: Tensor
)
```

Common noise adoptation module.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`input`|**Tensor**|<p>Tensor of shape (batch_size, embedding_size)</p>
`workers`|**Tensor**|<p>Tensor of shape (batch_size,) containing the worker IDs.</p>

* **Returns:**

  Tensor of shape (batch_size, 1) containing the common noise rate.

* **Return type:**

  Tensor
