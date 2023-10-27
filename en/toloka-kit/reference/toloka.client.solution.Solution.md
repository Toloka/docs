# Solution
`toloka.client.solution.Solution` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/solution.py#L6)

```python
Solution(self, output_values: Dict[str, Any])
```

A Toloker's response to a single task.


A solution contains values for output fields specified in a [TaskSpec](toloka.client.project.task_spec.TaskSpec.md) when a project was created.

Solutions can be accessed via the [Assignment](toloka.client.assignment.Assignment.md) class.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`output_values`|**Dict\[str, Any\]**|<p>A dictionary with keys named as output fields.</p>
