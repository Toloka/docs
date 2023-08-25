# get_operation_log
`toloka.client.TolokaClient.get_operation_log` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L3056)

```python
get_operation_log(self, operation_id: str)
```

Gets an operation log.


You can get the log for operations: creating one or multiple tasks or task suites, or issuing bonuses to Tolokers.

If the operation was successful, the log contains the IDs of the created objects, otherwise it contains the details of validation errors.

Logs are available only for the last month.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operation_id`|**str**|<p>The ID of the operation.</p>

* **Returns:**

  A list with log items.

* **Return type:**

  List\[[OperationLogItem](toloka.client.operation_log.OperationLogItem.md)\]

**Examples:**


```python
operation_log = toloka_client.get_operation_log(operation_id='6d84114f-fcfc-473d-8249-1a4f3ea550eb')
```
