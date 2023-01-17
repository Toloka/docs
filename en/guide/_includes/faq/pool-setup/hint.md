{% cut "I created a training pool with one task containing a hint. The Toloker fails to complete the task on the first attempt, but finally succeeds. The Toloker gets the skill `0`. How do I grant to the Toloker access to my tasks? The minimum required level that you can set is `10`." %}

Technically, if you have only one task in your training pool, you don't have this option. The skill will be either `0` or `100`. We recommend that you add several tasks, or at least 2 so that the Toloker will practice on the first task and will be able to do the second task correctly. In this case, you can admit users to your main pool starting from the skill value of `50`.

You can also create a training pool based on the main pool. Assign a skill using the [Control tasks](../../../../guide/concepts/goldenset.md) rule: in this case, you can admit users with any skill level to your main pool, even if the value is zero. But we don't advise giving tasks to people who failed training.

{% endcut %}