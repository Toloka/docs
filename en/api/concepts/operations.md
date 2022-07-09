# Overview

Some API requests (opening and closing a pool, archiving a pool or project, loading task suites, issuing rewards) are processed as asynchronous operations that run in the background. Operation details (for example, status and creation time) are passed in JSON format.

You can use the API for tracking operation progress.

## Methods {#methods}

Method | Endpoint | Overview
----- | ----- | -----
GET | [/operations](get-operations-list.md) | Gets the list of operations.
GET | [/operations/<operation_id>](get-operation.md) | Gets operation details.
GET | [/operations/<operation_id>/log](get-operation-log.md) | Gets the operation log.