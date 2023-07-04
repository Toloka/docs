# AppBatch
`toloka.client.app.AppBatch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/app/__init__.py#L201)

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
    last_items_import: Optional[AppItemImport] = None,
    confidence_avg: Optional[float] = None,
    items_processed_count: Optional[int] = None,
    eta: Optional[datetime] = None,
    items_per_state: Optional[Dict] = None
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
`status`|**Optional\[[Status](toloka.client.app.AppBatch.Status.md)\]**|<p>The batch status:</p> <ul> <li>`NEW` — The processing of the batch items is not started.</li> <li>`PROCESSING` — Batch items are being processed by Tolokers.</li> <li>`COMPLETED` — Annotation of all batch items is completed.</li> <li>`ERROR` — An error occurred during processing.</li> <li>`CANCELLED` — Batch processing cancelled.</li> <li>`ARCHIVE` — The batch is archived.</li> <li>`NO_MONEY` — There are not enough money for processing.</li> </ul>
`items_count`|**Optional\[int\]**|<p>The number of items in the batch.</p>
`item_price`|**Optional\[Decimal\]**|<p>The cost of processing a single item in the batch.</p>
`cost`|**Optional\[Decimal\]**|<p>The cost of processing the batch.</p>
`cost_of_processed`|**Optional\[Decimal\]**|<p>Cost of already processed task items.</p>
`created_at`|**Optional\[datetime\]**|<p>The date and time when the batch was created.</p>
`started_at`|**Optional\[datetime\]**|<p>The date and time when batch processing started.</p>
`finished_at`|**Optional\[datetime\]**|<p>The date and time when batch processing was completed.</p>
`read_only`|**Optional\[bool\]**|
`last_items_import`|**Optional\[[AppItemImport](toloka.client.app.AppItemImport.md)\]**|<p>Meta-information on asynchronous loading operation (possible via UI).</p>
`confidence_avg`|**Optional\[float\]**|<p>Average labeling quality.</p>
`items_processed_count`|**Optional\[int\]**|<p>The number of labeled items.</p>
`eta`|**Optional\[datetime\]**|<p>Expected date and time when batch processing will be completed.</p>
`items_per_state`|**Optional\[Dict\]**|<p>Statistics on the number of items in each state.</p>
