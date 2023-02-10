{% cut "How do I view the processing log?" %}

To view the processing log, click **More on uploading errors**. The processing log is written in JSON format. Objects inside `result` match the line number of the uploaded file. Lines that were processed with an error have the status `"success": false`.

{% note info %}

To work with a large log conveniently, copy it to the text editor.

{% endnote %}

{% endcut %}