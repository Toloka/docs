# KnownSolution
`toloka.client.task.BaseTask.KnownSolution` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/task.py#L30)

```python
KnownSolution(
    self,
    *,
    output_values: Optional[Dict[str, Any]] = None,
    correctness_weight: Optional[float] = None
)
```

A correct response for a control or training task.


Responses have a correctness weight.
For example, if `correctness_weight` is 0.5,
then half of the error is counted to the Toloker.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`output_values`|**Optional\[Dict\[str, Any\]\]**|<p>Correct values of output fields.</p>
`correctness_weight`|**Optional\[float\]**|<p>The correctness weight of the response.</p>
