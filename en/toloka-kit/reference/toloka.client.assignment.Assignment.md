# Assignment
`toloka.client.assignment.Assignment` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/assignment.py#L20)

```python
Assignment(
    self,
    *,
    id: Optional[str] = None,
    task_suite_id: Optional[str] = None,
    pool_id: Optional[str] = None,
    user_id: Optional[str] = None,
    status: Union[Status, str, None] = None,
    reward: Optional[Decimal] = None,
    bonus_ids: Optional[List[str]] = None,
    tasks: Optional[List[Task]] = None,
    automerged: Optional[bool] = None,
    created: Optional[datetime] = None,
    submitted: Optional[datetime] = None,
    accepted: Optional[datetime] = None,
    rejected: Optional[datetime] = None,
    skipped: Optional[datetime] = None,
    expired: Optional[datetime] = None,
    first_declined_solution_attempt: Optional[List[Solution]] = None,
    solutions: Optional[List[Solution]] = None,
    mixed: Optional[bool] = None,
    owner: Optional[Owner] = None,
    public_comment: Optional[str] = None
)
```

Information about an assigned task suite.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the assignment.</p>
`task_suite_id`|**Optional\[str\]**|<p>The ID of the assigned task suite.</p>
`pool_id`|**Optional\[str\]**|<p>The ID of the pool containing the task suite.</p>
`user_id`|**Optional\[str\]**|<p>The ID of the Toloker who was assigned the task suite.</p>
`status`|**Optional\[[Status](toloka.client.assignment.Assignment.Status.md)\]**|<p>Status of the assignment.</p> <ul> <li>`ACTIVE` — The task suite is assigned but it isn&#x27;t completed yet.</li> <li>`SUBMITTED` — The task suite is completed but it isn&#x27;t checked.</li> <li>`ACCEPTED` — The task suite is accepted by the requester.</li> <li>`REJECTED` — The task suite is rejected by the requester.</li> <li>`SKIPPED` — The task suite is skipped by the Toloker.</li> <li>`EXPIRED` — Time for completing the tasks has expired.</li> </ul>
`reward`|**Optional\[Decimal\]**|<p>Payment received by the Toloker.</p>
`bonus_ids`|**Optional\[List\[str\]\]**|<p>IDs of bonuses issued for the task.</p>
`tasks`|**Optional\[List\[[Task](toloka.client.task.Task.md)\]\]**|<p>Data for the tasks.</p>
`automerged`|**Optional\[bool\]**|<p>Flag of the response received as a result of merging identical tasks. Value:</p> <ul> <li>`True` — The response was recorded when identical tasks were merged.</li> <li>`False` — Normal Toloker response.</li> </ul>
`created`|**Optional\[datetime\]**|<p>The date and time when the task suite was assigned to a Toloker.</p>
`submitted`|**Optional\[datetime\]**|<p>The date and time when the task suite was completed by a Toloker.</p>
`accepted`|**Optional\[datetime\]**|<p>The date and time when the responses for the task suite were accepted by the requester.</p>
`rejected`|**Optional\[datetime\]**|<p>The date and time when the responses for the task suite were rejected by the requester.</p>
`skipped`|**Optional\[datetime\]**|<p>The date and time when the task suite was skipped by the Toloker.</p>
`expired`|**Optional\[datetime\]**|<p>The date and time when the time for completing the task suite expired.</p>
`first_declined_solution_attempt`|**Optional\[List\[[Solution](toloka.client.solution.Solution.md)\]\]**|<p>For training tasks. The Toloker&#x27;s first responses in the training task (only if these were the wrong answers). If the Toloker answered correctly on the first try, the first_declined_solution_attempt array is omitted. Arrays with the responses (output_values) are arranged in the same order as the task data in the tasks array.</p>
`solutions`|**Optional\[List\[[Solution](toloka.client.solution.Solution.md)\]\]**|<p>Toloker responses. Arranged in the same order as the data for tasks in the tasks array.</p>
`mixed`|**Optional\[bool\]**|<p>Type of operation for creating a task suite:</p> <ul> <li>`True` — Smart mixing was used.</li> <li>`False` — The tasks were grouped manually, smart mixing was not used.</li> </ul>
`owner`|**Optional\[[Owner](toloka.client.owner.Owner.md)\]**|<p>Properties of Requester.</p>
`public_comment`|**Optional\[str\]**|<p>A public comment that is set when accepting or rejecting the assignment.</p>

**Examples:**


```python
for assignment in toloka_client.get_assignments(pool_id='1240045', status='SUBMITTED'):
    print(assignment.id)
    for solution in assignment.solutions:
        print(solution)
```
