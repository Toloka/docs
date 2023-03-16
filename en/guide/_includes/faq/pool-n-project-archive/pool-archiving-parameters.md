{% cut "How do I find out the pool archiving parameters?" %}

To find out the archiving date, get a [list of operations](../../../../api/concepts/get-operations-list.md) with the `POOL.ARCHIVE` type. The response will contain the pool number and the archiving date. You can't get the method used to archive the pool via the API.

If less than a month passed between the activity in the pool and its archiving, you can assume that the pool was archived manually, and if it's been one month or more, then it was archived automatically.

{% endcut %}