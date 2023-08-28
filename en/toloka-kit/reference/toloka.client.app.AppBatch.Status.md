# Status
`toloka.client.app.AppBatch.Status` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/app/__init__.py#L288)

The status of an App batch.

## Attributes Description

| Name | Value | Description |
| :------| :-----------| :----------| 
`NEW`|'NEW'|<p>The processing of the batch items is not started.</p>
`PROCESSING`|'PROCESSING'|<p>Batch items are being processed by Tolokers.</p>
`COMPLETED`|'COMPLETED'|<p>Annotation of all batch items is completed.</p>
`ERROR`|'ERROR'|<p>An error occurred during processing.</p>
`CANCELLED`|'CANCELLED'|<p>Batch processing cancelled.</p>
`NO_MONEY`|'NO_MONEY'|<p>There is not enough money for processing.</p>
`ARCHIVE`|'ARCHIVE'|<p>The batch is archived.</p>
`LOADING`|'LOADING'|<p>Tasks are loading to the batch.</p>
`STOPPING`|'STOPPING'|<p>The batch is stopping.</p>
`STOPPED`|'STOPPED'|<p>The batch has stopped.</p>
