{% cut "Can I create two active training pools, one for practice and the other for admitting users to the main pool? In other words, one pool is for users to practice and the other pool tests them." %}

Yes, you can do that. In this case, create the first pool based on the [training pool](../../../../glossary.md#training-pool) and the exam pool based on your main pool. If a pool contains only control and/or training tasks, the price can be set to zero.

In the exam pool, you can create a skill reflecting the exam result and granting admission to the main pool. For example, `if the number of responses is ≥ 10, set the skill value in the <exam skill> as % of correct responses`. In your exam pool user requirements, specify: `<exam skill> < 80 or = Is missing>`. In the main pool, set up a filter: `<exam skill> >= 80 and (<main skill> >= 70 or = Is missing)`. You can choose the skill values depending on how well the Tolokers handle your task.

{% endcut %}