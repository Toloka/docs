# CloseReason
`toloka.client.training.Training.CloseReason` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/training.py#L62)

A reason for closing a training.

## Attributes Description

| Name | Value | Description |
| :------| :-----------| :----------| 
`MANUAL`|'MANUAL'|<p>A training was closed by a requester.</p>
`EXPIRED`|'EXPIRED'|
`COMPLETED`|'COMPLETED'|<p>All linked pool tasks were completed.</p>
`NOT_ENOUGH_BALANCE`|'NOT_ENOUGH_BALANCE'|
`ASSIGNMENTS_LIMIT_EXCEEDED`|'ASSIGNMENTS_LIMIT_EXCEEDED'|<p>A limit of 2 millions assignments is reached.</p>
`BLOCKED`|'BLOCKED'|<p>The requester&#x27;s account was blocked.</p>
`FOR_UPDATE`|'FOR_UPDATE'|
