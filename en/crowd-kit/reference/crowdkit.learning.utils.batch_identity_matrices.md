# batch_identity_matrices
`crowdkit.learning.utils.batch_identity_matrices` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.0/crowdkit/learning/utils.py#L30)

```python
batch_identity_matrices(
    batch_size: int,
    dim_size: int,
    device: Optional[device] = None,
    dtype: Optional[dtype] = None
)
```

Creates a batch of identity matrices.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`batch_size`|**int**|<p>Batch size.</p>
`dim_size`|**int**|<p>Dimension size.</p>
`device`|**Optional\[device\]**|<p>Device to place the matrices on.</p>
`dtype`|**Optional\[dtype\]**|<p>Data type of the matrices.</p>

* **Returns:**

  Tensor of shape (batch_size, dim_size, dim_size)

* **Return type:**

  Tensor
