# ClosestToAverage
`crowdkit.aggregation.embeddings.closest_to_average.ClosestToAverage` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.2.1/crowdkit/aggregation/embeddings/closest_to_average.py#L13)

```python
ClosestToAverage(self, distance: Callable[[..., ...], float])
```

The **Closest to Average** aggregation model chooses the output with the embedding that's closest to the average embedding.


This method takes a `DataFrame` containing four columns: `task`, `worker`, `output`, and `embedding`.
Here the `embedding` is a vector containing a representation of the `output` which might be any
type of data such as text, images, NumPy arrays, etc. As a result, the method returns the output which
embedding is the closest one to the average embedding of the task responses.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`distance`|**Callable\[\[..., ...\], float\]**|<p>A callable that takes two NumPy arrays (the task embedding and the aggregated embedding) and returns a single `float` number — the distance between these two vectors.</p>
`embeddings_and_outputs_`|**DataFrame**|<p>The task embeddings and outputs. The `pandas.DataFrame` data is indexed by `task` and has the `embedding` and `output` columns.</p>
`scores_`|**DataFrame**|<p>The task label scores. The `pandas.DataFrame` data is indexed by `task` so that `result.loc[task, label]` is a score of `label` for `task`.</p>
## Methods Summary

| Method | Description |
| :------| :-----------|
[fit](crowdkit.aggregation.embeddings.closest_to_average.ClosestToAverage.fit.md)| Fits the model to the training data.
[fit_predict](crowdkit.aggregation.embeddings.closest_to_average.ClosestToAverage.fit_predict.md)| Fits the model to the training data and returns the aggregated outputs.
[fit_predict_scores](crowdkit.aggregation.embeddings.closest_to_average.ClosestToAverage.fit_predict_scores.md)| Fits the model to the training data and returns the estimated scores.
