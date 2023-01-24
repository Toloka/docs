# Training
`toloka.client.training.Training` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/training.py#L11)

```python
Training(
    self,
    *,
    project_id: Optional[str] = None,
    private_name: Optional[str] = None,
    may_contain_adult_content: Optional[bool] = None,
    assignment_max_duration_seconds: Optional[int] = None,
    mix_tasks_in_creation_order: Optional[bool] = None,
    shuffle_tasks_in_task_suite: Optional[bool] = None,
    training_tasks_in_task_suite_count: Optional[int] = None,
    task_suites_required_to_pass: Optional[int] = None,
    retry_training_after_days: Optional[int] = None,
    inherited_instructions: Optional[bool] = None,
    public_instructions: Optional[str] = None,
    metadata: Optional[Dict[str, List[str]]] = None,
    owner: Optional[Owner] = None,
    id: Optional[str] = None,
    status: Optional[Status] = None,
    last_close_reason: Optional[CloseReason] = None,
    created: Optional[datetime] = None,
    last_started: Optional[datetime] = None,
    last_stopped: Optional[datetime] = None
)
```

A training.


A training is a pool containing tasks with known solutions and hints for Tolokers. Use trainings:
- To train Tolokers so they solve general tasks better.
- To select Tolokers who successfully completed training tasks and to give them access to a general pool.

To link a training to a general pool set the
[Pool](toloka.client.pool.Pool.md).[quality_control](toloka.client.quality_control.QualityControl.md).[training_requirement](toloka.client.quality_control.QualityControl.TrainingRequirement.md)
parameter.

For more information, see [Adding a training](https://toloka.ai/en/docs/guide/concepts/train).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`project_id`|**Optional\[str\]**|<p>The ID of the project containing the training.</p>
`private_name`|**Optional\[str\]**|<p>The training name. It is visible to the requester only.</p>
`may_contain_adult_content`|**Optional\[bool\]**|<p>The presence of adult content.</p>
`assignment_max_duration_seconds`|**Optional\[int\]**|<p>Time limit to complete a task suite. Take into account loading a page with a task suite and sending responses to the server. It is recommended that you set at least 60 seconds.</p>
`mix_tasks_in_creation_order`|**Optional\[bool\]**|<ul> <li>True — Tasks are grouped in suites in the order they were created.</li> <li>False — Tasks are chosen for a task suite in a random order.</li> </ul> <p>Default: `True`.</p>
`shuffle_tasks_in_task_suite`|**Optional\[bool\]**|<ul> <li>True — Tasks from a task suite are shuffled on the page.</li> <li>False — Tasks from a task suite are placed on the page in the order they were created.</li> </ul> <p>Default: `True`.</p>
`training_tasks_in_task_suite_count`|**Optional\[int\]**|<p>The number of training tasks in one task suite.</p>
`task_suites_required_to_pass`|**Optional\[int\]**|<p>The number of task suites that must be completed by a Toloker to get a training skill.</p>
`retry_training_after_days`|**Optional\[int\]**|<p>The training can be completed again after the specified number of days to update the training skill. If the parameter is not specified, then the training skill is issued for an unlimited time.</p>
`inherited_instructions`|**Optional\[bool\]**|<ul> <li>True — Project instructions are used in the training.</li> <li>False — Instruction, specified in the `public_instructions` parameter, are used.</li> </ul> <p>Default: `False`.</p>
`public_instructions`|**Optional\[str\]**|<p>Instructions for Tolokers used when the `inherited_instructions` parameter is False. Describe in the instructions how to complete training tasks. You can use HTML markup inside `public_instructions`.</p>
`metadata`|**Optional\[Dict\[str, List\[str\]\]\]**|<p>A dictionary with metadata.</p>
`owner`|**Optional\[[Owner](toloka.client.owner.Owner.md)\]**|<p>The training owner.</p>
`id`|**Optional\[str\]**|<p>The ID of the training. Read only.</p>
`status`|**Optional\[[Status](toloka.client.training.Training.Status.md)\]**|<p>The training status. Read only.</p>
`last_close_reason`|**Optional\[[CloseReason](toloka.client.training.Training.CloseReason.md)\]**|<p>A reason why the training was closed last time. Read only.</p>
`created`|**Optional\[datetime\]**|<p>The UTC date and time when the training was created. Read only.</p>
`last_started`|**Optional\[datetime\]**|<p>The UTC date and time when the training was started last time. Read only.</p>
`last_stopped`|**Optional\[datetime\]**|<p>The UTC date and time when the training was stopped last time. Read only.</p>
## Methods Summary

| Method | Description |
| :------| :-----------|
[is_archived](toloka.client.training.Training.is_archived.md)| None
[is_closed](toloka.client.training.Training.is_closed.md)| None
[is_locked](toloka.client.training.Training.is_locked.md)| None
[is_open](toloka.client.training.Training.is_open.md)| None
[set_owner](toloka.client.training.codegen_setter_for_owner.md)| A shortcut setter for owner
