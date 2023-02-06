# CollectorConfig
`toloka.client.collectors.CollectorConfig` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/collectors.py#L41)

```python
CollectorConfig(self, *, uuid: Optional[UUID] = None)
```

Base class for all collectors.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`uuid`|**Optional\[UUID\]**|<p>The ID of a collector. Note that when you clone a pool, both pools start using the same collector, because it is not cloned. Usually, it is not an intended behavior. For example, in this case one collector gathers history size from both pools.</p>
## Methods Summary

| Method | Description |
| :------| :-----------|
[validate_condition](toloka.client.collectors.CollectorConfig.validate_condition.md)| None
