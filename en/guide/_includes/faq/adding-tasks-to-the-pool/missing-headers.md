{% cut "If there are no headers for some input columns in the file with tasks, are they going to be skipped during import? Will they be skipped if they have headers without the "INPUT:.." prefix?" %}

No. If you try to upload a file with missing headers to the pool, the system issues an upload error. All the INPUT fields required in the specification must be present in the file with tasks. There must be no extra fields or columns.

If you don't want to show some data to Tolokers, but you still need this data in the file, create the optional hidden input fields for such data in the project.

{% endcut %}