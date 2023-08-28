# Condition
`toloka.client.filter.Condition` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/filter.py#L146)

```python
Condition(
    self,
    *,
    operator: Any,
    value: Any
)
```

A base class that supports filter conditions.


Any condition belongs to some category and has a condition operator and a value. These attributes are mapped to API parameters.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**Any**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**Any**|<p>A value to compare with. For example, the minimum value of some skill, or a language specified in a Toloker&#x27;s profile.</p>
