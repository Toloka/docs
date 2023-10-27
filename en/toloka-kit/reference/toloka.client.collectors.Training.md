# Training
`toloka.client.collectors.Training` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/collectors.py#L489)

```python
Training(self, *, uuid: Optional[UUID] = None)
```

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`uuid`|**Optional\[UUID\]**|<p>The ID of a collector. Note that when you clone a pool, both pools start using the same collector, because it is not cloned. Usually, it is not an intended behavior. For example, in this case one collector gathers history size from both pools.</p>
