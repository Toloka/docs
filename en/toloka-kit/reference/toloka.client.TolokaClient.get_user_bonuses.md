# get_user_bonuses
`toloka.client.TolokaClient.get_user_bonuses` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/__init__.py#L2990)

Finds all Tolokers' rewards that match certain rules and returns them in an iterable object


`get_user_bonuses` returns a generator. You can iterate over all found Tolokers' rewards using the generator. Several requests to the Toloka server are possible while iterating.

 If you need to sort rewards use the [find_user_bonuses](toloka.client.TolokaClient.find_user_bonuses.md) method.

 Args:
     request: Search criteria.

 Yields:
     UserBonus: The next matching Toloker's reward.

 Example:
     >>> bonuses = list(toloka_client.get_user_bonuses(created_lt='2021-06-01T00:00:00'))
     ...

