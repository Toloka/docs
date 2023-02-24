# get_user_bonuses
`toloka.async_client.client.AsyncTolokaClient.get_user_bonuses` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/__init__.py#L0)

Finds all Tolokers' rewards that match certain rules and returns them in an iterable object


`get_user_bonuses` returns a generator. You can iterate over all found Tolokers' rewards using the generator. Several requests to the Toloka server are possible while iterating.

 If you need to sort rewards use the [find_user_bonuses](toloka.client.TolokaClient.find_user_bonuses.md) method.

 Args:
     request: Search criteria.
     batch_size: Returned Tolokers' rewards limit for each request. The maximum allowed batch_size is 300.

 Yields:
     UserBonus: The next matching Toloker's reward.

 Example:
     >>> bonuses = list(toloka_client.get_user_bonuses(created_lt='2021-06-01T00:00:00'))
     ...

