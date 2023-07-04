{% cut "What output format do I use for the review results to filter out mismatching Tolokers based on the “Majority vote”?" %}

To perform actions with Tolokers (assign a skill or ban them) based on the majority vote, add a relevant [rule](../../../concepts/mvote.md) to the pool.

Don't forget to enable **Keep task order from uploaded data** in the [pool parameters](../../../concepts/pool-main.md#pool-params). Majority vote is used in the projects with preset options (radio buttons or checkboxes). This rule won't apply to the text entry or file upload fields.

{% endcut %}