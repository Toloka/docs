# clone_aggregator
`crowdkit.aggregation.utils.clone_aggregator` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/utils.py#L23)

```python
clone_aggregator(aggregator: BaseClassificationAggregator)
```

Construct a new unfitted aggregator with the same parameters.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`aggregator`|**[BaseClassificationAggregator](crowdkit.aggregation.base.BaseClassificationAggregator.md)**|<p>aggregator instance to be cloned</p>

* **Returns:**

  cloned aggregator's instance. Its params are same to input,
except for the results of previous fit (private attributes).

* **Return type:**

  [BaseClassificationAggregator](crowdkit.aggregation.base.BaseClassificationAggregator.md)
