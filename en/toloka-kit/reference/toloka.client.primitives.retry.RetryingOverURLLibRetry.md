# RetryingOverURLLibRetry
`toloka.client.primitives.retry.RetryingOverURLLibRetry` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/primitives/retry.py#L108)

```python
RetryingOverURLLibRetry(
    self,
    base_url: str,
    retry: Retry,
    exception_to_retry: Tuple[Type[Exception], ...] = ...,
    **kwargs
)
```

Adapter class that allows usage of the urllib3 Retry class in httpx using the tenacity retrying mechanism.


Wrapped function should make a single request using HTTPX library and either return httpx.Response or raise an
exception.

This class tries to follow the behavior of urllib3.connectionpool.HTTPConnectionPool.urlopen as close as possible:
* If an exception is raised during the request:
    * urllib3 catches a subset of all possible exceptions, calls `Retry.increment` with the raised error and
        recursively calls urlopen;
    * this class matches the raised exception against exception_to_retry field in retry callback: if the exception
        is not matched the retry callback returns False and the exception is raised in user code. Otherwise, retry
        callback returns True and the `Retry.increment` is called inside the `after` callback with the
        corresponding urllib3 exception.
* If request returned a response:
    * urllib3 checks if retry should happen using `Retry.is_retry` method, calls `Retry.increment` with the
        received urllib3.Response object and makes recursive call with the new `Retry` instance. If not retry
        should happen the response object is returned;
    * this class calls `Retry.is_retry` method in `retry` callback. If no retry should happen `retry` callback
        returns False and the execution control is returned to the user code. If retry should happen, this class
        increments `Retry` instance using the `urllib3.Response` object constructed from the `httpx.Response`.
* Retrying is stopped when `Retry.is_exhausted` returns False:
    * urllib3 achieves this by raising an exception inside `Retry.increment`;
    * this class catches this exception when calling `Retry.increment` inside the `after` callback and explicitly
        calls `is_exhausted` inside the `stop` callback.

Usage of proxies is currently not supported

## Methods Summary

| Method | Description |
| :------| :-----------|
[wraps](toloka.client.primitives.retry.RetryingOverURLLibRetry.wraps.md)| None
