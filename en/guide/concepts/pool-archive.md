# Archiving a pool

A [pool](../../glossary.md#pool) with the “Archived” status can't be started or edited and isn't available for the [task review](accept.md).

By default, archived pools are not visible in the list of [project](../../glossary.md#project) pools. To view them:

1. Open the project page.

1. In the **Pools** tab, select **Archived**.

The pool is automatically archived if none of the following actions is performed in the pool for a month:

- Editing.
- Uploading tasks.
- Changing status.
- Completing a task.
- Cloning via the Toloka API.

To archive a pool, click **![Drop-down button](../_images/drop-down.svg) → Archive** at the top of the pool page, or ![](../_images/other/pool-action-archive.svg) in the list of pools on the project page.

{% note info %}

To [archive the training pool](train.md), first archive all the main pools to which it is linked.

{% endnote %}

## What's next {#what-next}

- [Add tasks to the pool](pool.md)
- Learn more about how to set up a pool:

    - [Setting up pricing](dynamic-pricing.md).
    - [Dynamic overlap](dynamic-overlap.md).
    - Selective [majority vote](selective-mvote.md) control.
    - [Filters](filters.md).
    - [Speed/quality balance](adjust.md).
    - [Reviewed assignments](offline-accept.md).

## For developers {#for-developers}

- [Toloka API: Moving pool to archive](../../api/concepts/archive-pool.md)
- [Toloka-Kit recipe: Archive pool](../../toloka-kit/recipes/archive-pool.md)

## Troubleshooting {#troubleshooting}

{% include [faq-delete-pool](../_includes/faq/pool-n-project-archive/delete-pool.md) %}

{% include [faq-pool-storage-time](../_includes/faq/pool-n-project-archive/pool-storage-time.md) %}

{% include [faq-where-closed-pool](../_includes/faq/pool-n-project-archive/where-closed-pool.md) %}

{% include [faq-pool-archiving-parameters](../_includes/faq/pool-n-project-archive/pool-archiving-parameters.md) %}

{% include [faq-accept-tasks-from-archived-pool](../_includes/faq/pool-n-project-archive/accept-tasks-from-archived-pool.md) %}

{% include [contact-support](../_includes/contact-support.md) %}