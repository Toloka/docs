{% cut "How do I create the task file properly so that there are no errors?" %}

In the file with the general tasks, the columns with the `INPUT` headers must be filled out. You can see those headers if you download a sample file from the pool.

If you are creating control tasks, fill out the `GOLDEN` columns with the correct task responses.

If you are creating a training task, you also need to fill in the `HINT:text` column. For the general tasks you don't need any columns other than `INPUT`, so feel free to delete them.

The file format must be TSV, XLSX or JSON, and the encoding must be UTF-8.

For more information about creating the file, see this [guide](../../../../guide/concepts/pool_csv.md). If there are errors during the upload, look up the error description on this [page](../../../../guide/concepts/task_upload.md#table-with-errors).

{% endcut %}