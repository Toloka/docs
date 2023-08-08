{% cut "How do I create two active training pools: the first one for practice and the second one to admit the Tolokers to the main pool?" %}

Create the first pool based on the [training pool](../../../../glossary.md#training-pool) and the second pool based on the main pool with the pool type set to **Exam**. If a pool contains only control and/or training tasks, the price can be set to zero.

In the exam pool, you can create a skill reflecting the exam result and granting admission to the main pool. For example, `If the number of task responses is ≥ 10, set the skill value in the <exam skill> as % of correct task responses.`

In your exam pool requirements, specify: `<exam skill> <80 or = is missing>`.

In the main pool, set up a filter: `<exam skill> >= 80 and <main skill> >= 70 or = Is missing>`. You can choose the skill values depending on how well the Tolokers handle your task.

{% endcut %}