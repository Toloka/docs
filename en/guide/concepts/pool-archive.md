# Archiving a pool

A [pool](../../glossary.md#pool) with the “Archived” status can't be started or edited and isn't available for the [task review](accept.md).

By default, archived pools are not visible in the list of [project](../../glossary.md#project) pools. To view them:

1. Open the project page.

1. In the **Pools** tab, select **Archived**.

## Manual archiving {#manual-archiving}

{% list tabs %}

- In the interface

  To archive a pool, click **![Drop-down button](../_images/drop-down.svg) → Archive** at the top of the pool page, or ![](../_images/other/pool-action-archive.svg) in the list of pools on the project page.

  {% note info %}

  To [archive the training pool](train.md), first archive all the main pools to which it is linked.

  {% endnote %}

- Via Toloka API

  To archive a pool using Toloka API, send a `POST` request with the specified ID of the pool you want to archive:

  ```bash
  curl -X POST 'https://toloka.dev/api/v1/pools/32267581/archive' \
       -H 'Authorization: ApiKey PlaceYourRealApiKey_Here'
  ```

  {% note tip "Visit Toloka API reference" %}

  Refer to the [Archive pool](https://toloka.ai/docs/api/api-reference/#post-/pools/-id-/archive) section of the Toloka API documentation for more details about the request, its parameters, and possible responses. You will find examples of the requests for [Toloka-Kit](../../toloka-kit/index.md) and other code samples there.

  {% endnote %}

{% endlist %}

## Automatic archiving {#automatic-archiving}

**General tasks** type pools are automatically archived if none of the following actions is performed in them for **30 days**:

- Editing.
- Uploading tasks.
- Changing status.
- Completing a task.

The automatic archiving will be delayed for **90 days** if the pool:

- Contains only control and training tasks.
- Contains no tasks in it.
- Is cloned via the [Toloka API](https://toloka.ai/docs/api/api-reference/#post-/pools/-id-/clone).
- Belongs to one of the following types: **Exam**, **Training**, **Retry**, or **Other**.

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

- [Toloka API: Moving pool to archive](https://toloka.ai/docs/api/api-reference/#post-/pools/-id-/archive)
- [Toloka-Kit recipe: Archive pool](../../toloka-kit/recipes/archive-pool.md)

## Troubleshooting {#troubleshooting}

{% include [faq-delete-pool](../_includes/faq/pool-n-project-archive/delete-pool.md) %}

{% include [faq-pool-storage-time](../_includes/faq/pool-n-project-archive/pool-storage-time.md) %}

{% include [faq-where-closed-pool](../_includes/faq/pool-n-project-archive/where-closed-pool.md) %}

{% include [faq-pool-archiving-parameters](../_includes/faq/pool-n-project-archive/pool-archiving-parameters.md) %}

{% include [faq-accept-tasks-from-archived-pool](../_includes/faq/pool-n-project-archive/accept-tasks-from-archived-pool.md) %}

{% include [contact-support](../_includes/contact-support.md) %}