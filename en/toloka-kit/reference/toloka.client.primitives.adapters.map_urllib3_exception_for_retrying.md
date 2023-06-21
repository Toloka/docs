# map_urllib3_exception_for_retrying
`toloka.client.primitives.adapters.map_urllib3_exception_for_retrying` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/primitives/adapters.py#L181)

```python
map_urllib3_exception_for_retrying(exception: BaseException)
```

Follows the exception mapping logic from the urllib3.connectionpool.HTTPConnectionPool.urlopen as of


urllib3==1.26.15

SSL-related exceptions are not supported.

