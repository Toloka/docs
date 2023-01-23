# get_operations
`toloka.async_client.client.AsyncTolokaClient.get_operations` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/__init__.py#L0)

Finds all operations that match certain rules and returns them in an iterable object


`get_operations` returns a generator. You can iterate over all found operations using the generator. Several requests to the Toloka server are possible while iterating.

 If you need to sort operations use the [find_operations](toloka.client.TolokaClient.find_operations.md) method.

 Args:
     request: Search criteria.
     batch_size: Returned operations limit for each request. The default batch_size is 50. The maximum allowed batch_size is 500.

 Yields:
     Operation: The next matching operations.

 Example:
     >>> bonuses = list(toloka_client.get_operations(submitted_lt='2021-06-01T00:00:00'))
     ...

