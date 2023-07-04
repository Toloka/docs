# universal_decorator
`toloka.util._codegen.universal_decorator` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/util/_codegen.py#L62)

```python
universal_decorator(*, has_parameters)
```

Metadecorator used for writing universal decorators that does not change function-like object type.


Wrapped decorator will preserve function-like object type: plain functions, async functions, generators and
async generators will keep their type after being decorated. Warning: if your decorator changes the
type of the function-like object (e.g. yields plain function result) do NOT use this (meta)decorator.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`has_parameters`|**-**|<p>does wrapped decorator use parameters</p>
