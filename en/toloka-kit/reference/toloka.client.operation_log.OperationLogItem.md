# OperationLogItem
`toloka.client.operation_log.OperationLogItem` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/operation_log.py#L9)

```python
OperationLogItem(
    self,
    *,
    type: Optional[str] = None,
    success: Optional[bool] = None,
    input: Optional[Dict[str, Any]] = None,
    output: Optional[Dict[str, Any]] = None
)
```

An operation log item.


If the operation was successful, the log contains the IDs of created objects, otherwise it contains validation errors details.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`type`|**Optional\[str\]**|<p>The type of the operation.</p> <ul> <li>`USER_BONUS_PERSIST` — Successfully issuing a bonus.</li> <li>`TASK_CREATE` — Successfully creating a task.</li> <li>`TASK_SUITE_CREATE` — Successfully creating a task suite.</li> <li>`USER_BONUS_VALIDATE` — Issuing a bonus that failed.</li> <li>`TASK_VALIDATE` — Creating a task that failed.</li> <li>`TASK_SUITE_VALIDATE` — Creating a task suite that failed.</li> </ul>
`success`|**Optional\[bool\]**|<p>The operation result: success or failure.</p>
`input`|**Optional\[Dict\[str, Any\]\]**|<p>Input operation data.</p>
`output`|**Optional\[Dict\[str, Any\]\]**|<p>Operation output data. The content depends on the log item `type`.</p>
