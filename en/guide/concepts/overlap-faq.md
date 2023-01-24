# What is overlap?

Overlap is the number of Tolokers who should complete each task in the [pool](../../glossary.md#pool).

You can set overlap in the pool settings:

![](../_images/location-job/overlap.png)

#### Tips and recommendations

| Task type                            | Recommended overlap |
|--------------------------------------|---------------------|
| Most tasks have automatic acceptance | from 3 to 5         |
| Simple task                          | 3                   |
| Reviewed task                        | 1                   |

You can change overlap after the pool is started. To do this, open the pool editing mode and set the new overlap value. You don't need to restart the pool. Updating the settings is usually fast, but if there are many tasks, it may take several minutes.

#### Advanced overlap types

- Dynamic overlap lets you change [overlap](dynamic-overlap.md) depending on:

    - How well the Tolokers do on the task.
    - How well Tolokers' responses match each other.

    This type of overlap helps you save money without reducing the quality of data labeling.

- [Selective majority vote verification](selective-mvote.md) allows you to set up [majority vote check](mvote.md) for only a portion of tasks.

    This type of overlap helps you save money and speed up pool completion.

## For developers {#for-developers}

- [Toloka API: Changing task suite overlap](../../api/concepts/edit-overlap.md)
- [Toloka-Kit recipe: Set overlap](../../toloka-kit/recipes/set-overlap.md)

## Troubleshooting {#troubleshooting}

{% include [faq-basic-overlap](../_includes/faq/pool-setup/basic-overlap.md) %}

{% include [faq-cross-check](../_includes/faq/pool-setup/cross-check.md) %}

{% include [troubleshooting-max-number](../_includes/troubleshooting/pool-setup/max-number.md) %}

{% cut "How does counting work if I set `overlap = 3` in the pool and `response threshold = 3` in the majority vote?" %}

In this case, if you don't have 3 identical responses for your task (response threshold), no user would be considered a good or poor Toloker, because the system can't see which of the Tolokers made an error.

But if you set `response threshold = 2` with `overlap = 3`, then two users with the same responses are considered good Tolokers, but the third user, who gives a different response, is a poor Toloker.

{% endcut %}

{% include [faq-counting-work](../_includes/faq/pool-setup/counting-work.md) %}