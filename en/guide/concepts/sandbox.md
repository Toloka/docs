# Sandbox

The [Sandbox]({{ sandbox }}) is a testing environment for Toloka. This is where you can test your [project](../../glossary.md#project) settings as a Toloker before moving them to the [Toloka production version]({{ production-version }}) and running the project for real Tolokers. This helps you avoid making mistakes and spending money on a task that isn't working right.

## Getting access to the sandbox {#sandbox-access}

Please [contact our support team](../troubleshooting/support.md?form-topic1=sandbox) describing the projects you plan to use the sandbox for, types of tasks you plan to upload, the approximate number of trusted Tolokers who are going to complete tasks for you there, and other details.

Make sure the projects you plan to use in the sandbox meet the [usage rules](#usage-rules).

## Usage rules {#usage-rules}

1. The sandbox is intended for testing tasks with small batches of data. Labeling an entire dataset is considered unfair usage of the service, unless you have a special agreement with us.

1. The sandbox limits the number of trusted Tolokers and submitted tasks for testing your project. Limits are set by Toloka admins.

If you need a private data labeling environment for your own team, [request](../troubleshooting/support.md?form-topic1=sandbox) the in-house data labeling option.

## How to run a project in the sandbox {#section_zmz_t4z_mlb}

Once you have [access to the sandbox](#sandbox-access) approved, follow the steps below to run a project there.

1. [Register in the sandbox]({{ sandbox }}) as a requester.

    {% note tip %}

    To avoid confusion, use the same social account that you used in the Toloka production version to register as a requester.

    {% endnote %}

1. Configure and launch your project:

    - A list of instructions is provided in [Tutorials for popular tasks](../tutorials/usecases.md).

    - General instructions in the [Starting and tuning a project](main-steps.md) section.

## How to complete tasks {#self}

To complete your tasks in the sandbox:

1. Register as a Toloker (see the instructions in the [user documentation]({{ user-documentation }})).

    {% note alert %}

    Authorization via social media isn't allowed, so you need to [register]({{ register }}) a new user in Yandex.

    {% endnote %}

1. Log in to the [Sandbox]({{ sandbox }}) using the requester account.

1. Open the [Tolokers]({{ users }}) page and click **Add trusted Tolokers**.

1. Click **Add Toloker** and enter the case-sensitive username of the created Toloker.

    Only trusted Tolokers can access your tasks.

    The number of trusted Tolokers required for testing depends on the [overlap settings](dynamic-overlap.md).

    To test your project in the Sandbox, set [overlap](../../glossary.md#overlap) 1. If you increase the overlap, you will need to register more Tolokers and add trusted accounts.

    When exporting a project to the production version of [Toloka](#export), you can specify the necessary overlap in accordance with your project goals.

1. Log in to the sandbox using the Toloker account and test your tasks. Make sure that the buttons and response validation are set up correctly, and assess how long it takes to complete the tasks. Make sure that the [Toloker selection](filters.md) and [quality control](control.md) work.

## How to move a task to the production version of Toloka {#export}

{% note alert "Restriction" %}

Note that you can move only project and [pool](../../glossary.md#pool) settings. You can't move tasks and responses to them. The project's [quality control](../../glossary.md#quality-control) settings can't be moved, either.

{% endnote %}

To move tasks from the sandbox to the production version:

1. Link the sandbox and production version accounts:

    1. Open the **Integrations** tab in the production version on the [profile]({{ profile }}) page, click **Get OAuth token**, and copy the OAuth token displayed.

    1. Open the same tab in the sandbox on the [profile]({{ sandbox-profile }}) page, paste the copied token into the **Main Toloka OAuth token** field, and click **Add OAuth token**.

1. Go to the project page in the sandbox and click **![Drop-down button](../_images/drop-down.svg) → ![Export button](../_images/location-job/project/export.svg) Export**.

1. Choose the pools to export and click **Export**.

    If the pool has [linked training](train.md), it is exported automatically.

## Troubleshooting {#troubleshooting}

{% include [faq-work-with-sandbox](../_includes/faq/sandbox/work-with-sandbox.md) %}

{% include [faq-see-pool-as-toloker](../_includes/faq/sandbox/see-pool-as-toloker.md) %}

{% include [faq-same-account](../_includes/faq/sandbox/same-account.md) %}

{% include [troubleshooting-export-error](../_includes/troubleshooting/sandbox/export-error.md) %}

{% include [faq-check-mobile-version](../_includes/faq/sandbox/check-mobile-version.md) %}

{% include [faq-copy-from-sandbox](../_includes/faq/sandbox/copy-from-sandbox.md) %}

{% include [troubleshooting-submit](../_includes/troubleshooting/sandbox/submit.md) %}

{% include [faq-move-control-tasks](../_includes/faq/sandbox/move-control-tasks.md) %}

{% include [troubleshooting-dont-see-task](../_includes/troubleshooting/sandbox/dont-see-task.md) %}

{% include [troubleshooting-cant-add-trusted-user](../_includes/troubleshooting/sandbox/cant-add-trusted-user.md) %}

{% include [faq-overlap](../_includes/faq/pool-setup/overlap.md) %}

{% include [faq-change-overlap](../_includes/faq/pool-setup/change-overlap.md) %}

{% include [contact-support](../_includes/contact-support.md) %}