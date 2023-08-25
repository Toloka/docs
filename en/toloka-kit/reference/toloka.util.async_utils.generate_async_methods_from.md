# generate_async_methods_from
`toloka.util.async_utils.generate_async_methods_from` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/util/async_utils.py#L223)

```python
generate_async_methods_from(cls)
```

Class decorator that generates asynchronous versions of methods using the provided class.


This class assumes that every method of the resulting class is either an async gen or async function. In case of
the naming collision (decorated class already has the method that would have been created by the decorator)
the new method is not generated. This allows you to custom implement asynchronous versions of non-trivial methods
while automatically generating boilerplate code.

