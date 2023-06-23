{% cut "How do I automatically assign skills based on Toloker responses to my questions?" %}

You can do that using the [Control tasks](../../../../guide/concepts/goldenset.md) rule.

1. Upload the task file using **Smart mixing**.

1. Specify `student` as the correct answer to the question. Don't take other questions into account (leave the fields empty or unselected).

1. Add the [Control tasks](../../../../guide/concepts/goldenset.md) rule to the pool: `if the percentage of correct control answers = 100, then set the skill value Student = 1`.

{% cut "See the screenshot" %}

![](../../../_images/troubleshooting/set-questionnaire-skill-student.png)

{% endcut %}

{% endcut %}