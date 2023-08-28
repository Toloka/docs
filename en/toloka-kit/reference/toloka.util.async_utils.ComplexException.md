# ComplexException
`toloka.util.async_utils.ComplexException` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/util/async_utils.py#L36)

```python
ComplexException(self, exceptions: List[Exception])
```

Exception to aggregate multiple exceptions occured.


Unnderlying exceptions are stored in the `exceptions` attribute.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`exceptions`|**List\[Exception\]**|<p>List of underlying exceptions.</p>
