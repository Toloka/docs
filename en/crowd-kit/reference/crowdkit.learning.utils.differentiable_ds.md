# differentiable_ds
`crowdkit.learning.utils.differentiable_ds` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/learning/utils.py#L10)

```python
differentiable_ds(outputs: Tensor, confusion_matrices: Tensor)
```

Differentiable Dawid-Skene logit transformation.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`outputs`|**Tensor**|<p>Tensor of shape (batch_size, input_dim)</p>
`confusion_matrices`|**Tensor**|<p>Tensor of shape (batch_size, input_dim, input_dim)</p>

* **Returns:**

  Tensor of shape (batch_size, input_dim)

* **Return type:**

  Tensor
