# AppBatch
`toloka.client.app.AppBatch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/app/__init__.py#L295)

```python
AppBatch(
    self,
    *,
    id: Optional[str] = None,
    app_project_id: Optional[str] = None,
    name: Optional[str] = None,
    status: Union[Status, str, None] = None,
    items_count: Optional[int] = None,
    item_price: Optional[Decimal] = None,
    cost: Optional[Decimal] = None,
    cost_of_processed: Optional[Decimal] = None,
    created_at: Optional[datetime] = None,
    started_at: Optional[datetime] = None,
    finished_at: Optional[datetime] = None,
    read_only: Optional[bool] = None,
    priority_order: Optional[PriorityOrder] = None,
    last_items_import: Optional[AppItemImport] = None,
    confidence_avg: Optional[float] = None,
    items_processed_count: Optional[int] = None,
    eta: Optional[datetime] = None,
    etd: Optional[datetime] = None,
    app_project_eta: Optional[datetime] = None,
    items_per_state: Optional[Dict] = None,
    current_time: Optional[datetime] = None
)
```

An App batch.


A batch contains task items that are sent for labeling together.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the batch.</p>
`app_project_id`|**Optional\[str\]**|<p>The ID of the project containing the batch.</p>
`name`|**Optional\[str\]**|<p>The batch name.</p>
`status`|**Optional\[[Status](toloka.client.app.AppBatch.Status.md)\]**|<p>The batch [status](toloka.client.app.AppBatch.Status.md).</p>
`items_count`|**Optional\[int\]**|<p>The number of items in the batch.</p>
`item_price`|**Optional\[Decimal\]**|<p>The cost of processing a single item in the batch.</p>
`cost`|**Optional\[Decimal\]**|<p>The cost of processing the batch.</p>
`cost_of_processed`|**Optional\[Decimal\]**|<p>Cost of already processed task items.</p>
`created_at`|**Optional\[datetime\]**|<p>The date and time when the batch was created.</p>
`started_at`|**Optional\[datetime\]**|<p>The date and time when batch processing started.</p>
`finished_at`|**Optional\[datetime\]**|<p>The date and time when batch processing was completed.</p>
`read_only`|**Optional\[bool\]**|<p>Whether the batch can be updated or not.</p>
`priority_order`|**Optional\[[PriorityOrder](toloka.client.app.AppBatch.PriorityOrder.md)\]**|<p>The batch priority. See [PriorityOrder](toloka.client.app.AppBatch.PriorityOrder.md) for details. Default is `FIVE`.</p>
`last_items_import`|**Optional\[[AppItemImport](toloka.client.app.AppItemImport.md)\]**|<p>Information about the last operation that added items.</p>
`confidence_avg`|**Optional\[float\]**|<p>Average labeling quality.</p>
`items_processed_count`|**Optional\[int\]**|<p>The number of labeled items.</p>
`eta`|**Optional\[datetime\]**|<p>Expected date and time when batch processing will be completed.</p>
`etd`|**Optional\[datetime\]**|<p>The expected date and time when processing of the queued batch will be started. The parameter is present in the response when the batch status is equal to `QUEUED`, otherwise it&#x27;s `None`.</p>
`app_project_eta`|**Optional\[datetime\]**|<p>The expected date and time when processing of all the batches associated with the project will be completed. The parameter is present in the response when the project contains batches in the status equal to `QUEUED` or `PROCESSING`, otherwise it&#x27;s `None`.</p>
`items_per_state`|**Optional\[Dict\]**|<p>Statistics on the number of items in each state.</p>
`current_time`|**Optional\[datetime\]**|<p>The server-side date and time when the response was formed.</p>

**Examples:**


```python
batches = toloka_client.get_app_batches(app_project_id='Q2d15QBjpwWuDz8Z321g', status='NEW')
for batch in batches:
    print(batch.id, batch.status, batch.items_count)
```
