# What is overlap?

Overlap is the number of Tolokers who should complete each [task](../../glossary.md#task) in the [pool](pool-edit.md).

You can set overlap in the [pool settings](pool-edit.md):

![](../_images/location-job/overlap.png)

## Tips and recommendations

| Task type                            | Recommended overlap |
|--------------------------------------|---------------------|
| Most tasks have automatic acceptance | from 3 to 5         |
| Simple task                          | 3                   |
| Reviewed task                        | 1                   |

You can change overlap after the pool is started. To do this, open the pool editing mode and set the new overlap value. You don't need to restart the pool. Updating the settings is usually fast, but if there are many tasks, it may take several minutes.

## Advanced overlap types

- Dynamic overlap lets you change [overlap](dynamic-overlap.md) depending on:

    - How well the Tolokers do on the task.
    - How well Tolokers' responses match each other.

    This type of overlap helps you save money without reducing the quality of data labeling.

- [Selective majority vote verification](selective-mvote.md) allows you to set up [majority vote check](mvote.md) for only a portion of tasks.

    This type of overlap helps you save money and speed up pool completion.

## For developers {#for-developers}

- [Toloka API: Changing task suite overlap](https://toloka.ai/docs/api/api-reference/#patch-/task-suites/-id-)
- [Toloka-Kit recipe: Set overlap](../../toloka-kit/recipes/set-overlap.md)

## Troubleshooting {#troubleshooting}

{% include [faq-basic-overlap](../_includes/faq/pool-setup/basic-overlap.md) %}

{% include [faq-cross-check](../_includes/faq/pool-setup/cross-check.md) %}

{% include [troubleshooting-max-number](../_includes/troubleshooting/pool-setup/max-number.md) %}

{% include [faq-counting-work](../_includes/faq/pool-setup/counting-work.md) %}

{% include [contact-support](../_includes/contact-support.md) %}