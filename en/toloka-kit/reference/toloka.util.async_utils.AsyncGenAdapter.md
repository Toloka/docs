# AsyncGenAdapter
`toloka.util.async_utils.AsyncGenAdapter` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/util/async_utils.py#L358)

```python
AsyncGenAdapter(self, gen: AsyncGenerator[TypeVar('YieldType'), TypeVar('SendType')])
```

Adapter class that enables alternative syntax for iteration over async generator.


This class is used for backwards compatibility. Please use "async for" syntax in new code.


**Examples:**

main syntax
```python
async for value in AsyncGenAdapter(async_gen): ...
```

alternative syntax (please do not use in new code):
```python
for value in await AsyncGenAdapter(async_gen): ...
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[as_sync_gen](toloka.util.async_utils.AsyncGenAdapter.as_sync_gen.md)| None
