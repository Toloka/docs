{% cut "How do I create a training and honey pots with an exam to get an output response other than the control value?" %}

For a control or training task response to be counted as correct, it must exactly match the control text. To do this, you need to normalize the task response text using JavaScript: remove spaces, punctuation marks, special characters, and capital letters, and write the result in a separate output field. Now you can match the processed text against your control text.

Another option for selecting Tolokers for a project of this type is manual review.

{% endcut %}