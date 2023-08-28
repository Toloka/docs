# CloseReason
`toloka.client.pool.Pool.CloseReason` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/pool/__init__.py#L128)

The reason for closing the pool.

## Attributes Description

| Name | Value | Description |
| :------| :-----------| :----------| 
`MANUAL`|'MANUAL'|<p>A pool was closed by a requester.</p>
`EXPIRED`|'EXPIRED'|<p>The lifetime of the pool expired.</p>
`COMPLETED`|'COMPLETED'|<p>All tasks were completed.</p>
`NOT_ENOUGH_BALANCE`|'NOT_ENOUGH_BALANCE'|<p>There is not enough money to run the pool.</p>
`ASSIGNMENTS_LIMIT_EXCEEDED`|'ASSIGNMENTS_LIMIT_EXCEEDED'|<p>A limit of 2 million assignments is reached.</p>
`BLOCKED`|'BLOCKED'|<p>The requester&#x27;s account was blocked.</p>
`FOR_UPDATE`|'FOR_UPDATE'|<p>Pool parameters are changing at the moment.</p>
