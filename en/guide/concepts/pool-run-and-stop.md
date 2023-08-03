# Starting and stopping a task pool

{% list tabs %}

- In the interface

  You can start a [pool](../../glossary.md#pool) if:

  1. You uploaded tasks into it.

  1. You have enough money in [your account](budget.md) to pay for the pool tasks, including the [overlap](../../glossary.md#overlap).

  To start the pool, click ![](../_images/other/b-start-pool.svg) on the pool page or ![](../_images/tutorials/content-moderation/pool-action-play.svg) in the list of pools on the [project](../../glossary.md#project) page.

  A started pool has the **Labeling** status. When all pool tasks are completed, the pool automatically switches to the **Labeled** status.

  To stop assigning the pool tasks before all of them are completed, click ![](../_images/other/b-pause-pool.svg) on the pool page or ![](../_images/tutorials/content-moderation/pool-action-pause.svg) in the list of pools on the project page.

  {% note tip %}

  New tasks can be uploaded to an open or closed pool.

  {% endnote %}

- Via Toloka API

  To start a pool using Toloka API, send a `POST` request with the ID of the pool specified:

  ```bash
  curl -X POST 'https://toloka.dev/api/v1/pools/32267581/open' \
       -H 'Authorization: ApiKey PlaceYourRealApiKey_Here'
  ```

  To stop a pool using Toloka API, send a `POST` request with the ID of the pool specified:

  ```bash
  curl -X POST 'https://toloka.dev/api/v1/pools/32267581/close' \
       -H 'Authorization: ApiKey PlaceYourRealApiKey_Here'
  ```

  {% note tip "Visit Toloka API reference" %}

  Refer to the [Open pool](https://toloka.ai/docs/api/api-reference/#post-/pools/-id-/open) and [Close pool](https://toloka.ai/docs/api/api-reference/#post-/pools/-id-/close) sections of the Toloka API documentation for more details about the requests, their parameters, and possible responses. You will find examples of the requests for [Toloka-Kit](../../toloka-kit/index.md) and other code samples there.

  {% endnote %}

{% endlist %}

## What's next {#what_next}

- [Get and process the results](result-of-eval.md).

## Troubleshooting {#troubleshooting}

{% include [troubleshooting-submit-doesnt-work](../_includes/troubleshooting/project-settings/submit-doesnt-work.md) %}

{% include [troubleshooting-next-doesnt-work](../_includes/troubleshooting/project-settings/next-doesnt-work.md) %}

{% include [troubleshooting-cant-complete-tasks](../_includes/troubleshooting/project-settings/cant-complete-tasks.md) %}

{% include [faq-overlap](../_includes/faq/pool-setup/overlap.md) %}

{% include [faq-change-overlap](../_includes/faq/pool-setup/change-overlap.md) %}

{% include [faq-dynamic-overlap](../_includes/faq/pool-setup/dynamic-overlap.md) %}

{% include [contact-support](../_includes/contact-support.md) %}