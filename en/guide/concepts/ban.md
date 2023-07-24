# Ban

Tolokers can be banned in two ways:

1. [By the requester](#ban-yourself).
1. [By the platform](#ban-platform).

## How to ban a Toloker {#ban-yourself}

You can block a Toloker's access to one or more [projects](../../glossary.md#project). This lets you control manually which Tolokers will complete tasks. For example, you can choose all Tolokers with a [skill](../../glossary.md#skill) value lower than N and block their access to tasks. You can also unblock access.

{% note warning %}

The assignments submitted by banned Tolokers will be taken into account if they are not rejected using manual review. They can be reassigned by setting up the [Recompletion of assignments from banned users](restore-task-overlap.md) rule.

{% endnote %}

#### In the interface

To block access to tasks for a single Toloker:

1. Select a Toloker on the [Tolokers]({{ users }}) page.

1. Click **Actions → Ban**, then fill in the fields:

    #|
    || Field | Overview ||
    || **Ban type** | Where to apply the ban:

    - **In all my projects** — All projects.
    - **In the project** — A single project (choose one from the list).||
    || **Ban expires** | Set when to lift the ban.

    We recommend blocking access temporarily in order to maintain the desired number of Tolokers for completing tasks.||
    || **Reason** | The reason for banning (only seen by the requester).||
    |#

To block access to tasks for multiple Tolokers:

1. Select Tolokers by using the [filters](../../glossary.md#filters) on the [Tolokers]({{ users }}) page or upload a TSV file:

    ```plaintext
    <annotator id 1>
    <annotator id 2>
    ...
    <annotator id n>
    ```

1. Click **Ban**, then fill in the fields (see the table above).

You can view information about access to tasks on the Toloker's page (on the [Tolokers]({{ users }}) page, go to the **Bans** tab). To unblock access to tasks, hover over the ban line and click ![](../_images/location-job/task-edit/task-action-delete.svg).

{% note tip "How to work via Toloka API" %}

To block a Toloker's access using Toloka API, send a `PUT` request with the information about the ban:

```bash
curl -X PUT 'https://toloka.dev/api/v1/user-restrictions' \
     -H 'Authorization: ApiKey PlaceYourRealApiKey_Here' \
     -H 'Content-Type: application/json' \
     -d '{"scope":"ALL_PROJECTS","user_id":"1ad097faba0eff85a04fe30bc04d53db","will_expire":"2030-01-01T00:00:00.000Z"}'
```

Refer to the [Block access to tasks](https://toloka.ai/docs/api/api-reference/#put-/user-restrictions) section of the Toloka API documentation for more details about the request, its parameters, and possible responses. You will find examples of the requests for [Toloka-Kit](../../toloka-kit/index.md) and other code samples there.

{% endnote %}

## Banning on the platform {#ban-platform}

Toloka has dedicated [anti-fraud system](https://toloka.ai/anti-fraud/) for banning dishonest Tolokers. It monitors user behavior and blocks suspicious accounts.

The main reasons for banning:

1. Disclosure of confidential information.
1. Using scripts and bots or any form of cheating.
1. Poor response quality.
1. Providing false data during registration.
1. Frequently skipping captchas or entering them incorrectly.
1. Using multiple accounts.
1. Location cheating.

{% note info %}

If a Toloker's behavior seems suspicious, [write to support](../troubleshooting/support.md#cheater). We'll conduct an additional review. If the Toloker is violating the user agreement, they'll be blocked in the system and will no longer be able to complete tasks.

You can also [ban](#ban) this Toloker from your project.

{% endnote %}

## For developers {#for-developers}

- [Toloka API: Blocking access to tasks](https://toloka.ai/docs/api/api-reference/#put-/user-restrictions)
- [Toloka-Kit: Banning Tolokers](../../toloka-kit/reference/toloka.client.TolokaClient.set_user_restriction.md)
- [Toloka-Kit recipe: Ban Tolokers](../../toloka-kit/recipes/ban-tolokers.md)
- [Toloka-Kit recipe: Remove ban from Toloker](../../toloka-kit/recipes/delete-restriction.md)
- [Toloka-Kit recipe: Get list of bans](../../toloka-kit/recipes/get-restrictions.md)

## Troubleshooting {#troubleshooting}

{% include [troubleshooting-trusted-user-banned](../_includes/troubleshooting/users/trusted-user-banned.md) %}

{% include [faq-disable-tasks](../_includes/faq/result-questions/disable-tasks.md) %}

{% include [faq-redo-task](../_includes/faq/users/redo-task.md) %}

{% include [faq-fix-myself](../_includes/faq/result-questions/fix-myself.md) %}

{% include [faq-empty-response](../_includes/faq/users/empty-response.md) %}

{% include [faq-cheaters-paid](../_includes/faq/users/cheaters-paid.md) %}

{% include [troubleshooting-poor-results](../_includes/troubleshooting/users/poor-results.md) %}

{% include [troubleshooting-include-responses](../_includes/troubleshooting/users/include-responses.md) %}

{% include [faq-ban-and-reject](../_includes/faq/users/ban-and-reject.md) %}

{% cut "Report suspicious Tolokers" %}

<iframe width="100%" frameborder="0" src="https://forms.yandex.com/surveys/10035353.388b5c1d02f16762f4a79b515beaa9740148362a/?lang=en&iframe=1&service=toloka-ai"></iframe>

{% endcut %}