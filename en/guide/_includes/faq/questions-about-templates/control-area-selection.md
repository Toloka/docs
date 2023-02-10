{% cut "How do I use control and training tasks in the standard preset with an area selection editor?" %}

In the standard preset with an area selection editor, you can't use the control tasks. In order for the assignment to be accepted by the system as correct, the object selected by the Toloker must exactly match the control object. This is almost impossible. Therefore, you can leave the `GOLDEN` field empty in the task file or simply delete all the columns except `INPUT`.

You can't use [training](../../../../glossary.md#training-pool) and the main pool with the **Training** type in an area selection project because for the response to be correct, the object selected by the Toloker must exactly match the control object. This is almost impossible.

Such tasks are usually run with manual review: the Toloker submits an assignment, and then the assignment is rejected or accepted after the review.

For pre-selection of Tolokers, you can use “examination tasks”. Review the assignments and assign skills based on the percentage of accepted assignments. For this purpose, add the “Results of manual review” rule to the pool. To make sure that only the good Tolokers are admitted to the main pool, put a skill-based filter to the pool.

{% endcut %}