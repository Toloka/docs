{% cut "How do I create a training pool so that the Toloker might fail it but still be admitted to the general task pool?" %}

Create a main pool of the **Training** type. Add only [training tasks](../../../../glossary.md#training-task). To assign a skill, use the **Control tasks** rule. To allow access to the general tasks to Tolokers with any skill level, set up the following filter in the main pool: `<skill> >= 0` or `<skill> ≠ 0`.

However, we don't advise giving access to general tasks to Tolokers who failed training.

{% endcut %}