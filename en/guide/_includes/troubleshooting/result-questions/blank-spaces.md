{% cut "Why do I get blank spaces inside my TSV file?" %}

When you upload a file with rows, double quotes indicate an area where you can use special characters (tabs or line breaks). Toloka merges everything in between the quotes into one row to make up one task. To use double quotes inside such an area, you need to escape them with another quote. [Read more here](../../../../guide/concepts/pool_csv.md#string).

{% endcut %}