{% cut "How are the correct responses to control questions counted?" %}

The Control tasks rule starts working after the Toloker completes the number of control tasks you specified. If your pool contains both [training](../../../../glossary.md#training-task) and control tasks, you can take into account the responses in both of them (the **Number of responses** parameter) or only in control tasks (the **Number of control responses** parameter).

As soon as the needed number of responses is collected, Toloka calculates the percentage of correct and incorrect responses and performs an action (assigns a skill, or blocks the Toloker in the pool or in the project). Then this percentage is updated as the tasks are completed by the Toloker. The number of the Toloker's recent responses that's used in the calculation is set in the **Recent control task responses to use** field. If you leave it empty, all the responses from the Toloker in the pool are counted.

{% endcut %}