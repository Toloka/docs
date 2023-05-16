{% cut "How do I add a mask for the input field, like dd.mm.yyyy for the date field or numbers only (10 or 12) for INN (Taxpayer Identification Number)?" %}

To validate the input data format, you can use the output field type, specifying the acceptable or minimum/maximum values. For example, create an output field for the taxpayer number with the "string" type and enter its minimum and maximum length (like 10 and 12). To use a more sophisticated validation in the template, use RegExp.

To enter a date, you can add a calendar to the task interface. See an [example of a calendar]({{ how-to-insert-a-calendar }}).

{% endcut %}