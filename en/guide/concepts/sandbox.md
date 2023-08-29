# Sandbox

The [sandbox]({{ sandbox }}) is a testing environment for Toloka. This is where you can test your [project](../../glossary.md#project) settings as a Toloker before moving them to the [Toloka production version]({{ production-version }}) and running the project for real Tolokers. This helps you avoid making mistakes and spending money on a task that isn't working right.

Toloka clients register and access Toloka sandbox using social authorization. If you registered in the sandbox using an email address, [migrate to the new social authorization](migrate-new-auth-sandbox.md) scheme, or you won't be able to use the sandbox.

Make sure the projects you plan to use in the sandbox meet the [usage rules](#usage-rules).

## Usage rules {#usage-rules}

1. The sandbox is intended for testing tasks with small batches of data. Labeling an entire dataset is considered unfair usage of the service, unless you have a special agreement with us.

1. The sandbox limits the number of trusted Tolokers and submitted tasks for testing your project. Limits are set by Toloka admins.

If you need a private data labeling environment for your own team, [request](../troubleshooting/support.md?form-topic1=sandbox) the in-house data labeling option.

## How to run a project in the sandbox {#section_zmz_t4z_mlb}

To register in the sandbox as a client and post tasks for Tolokers, you need to have one of the following supported social accounts:

{% include [register-social-list](../_includes/register/social-list.md) %}

{% include [register-social-list-note](../_includes/register/social-list-note.md) %}

Follow the steps below to run a project there.

1. Register in the sandbox as a requester.

    Toloka uses social authorization both for the **registration** and **signing in** to the sandbox.

    To authorize in Toloka sandbox using one of the social accounts, go to the [sign-in page]({{ sandbox }}).

    {% include [register-social-auth](../_includes/register/social-auth.md) %}

    {% note tip %}

    To avoid confusion, use the same social account that you used in the Toloka production version to register as a requester.

    {% endnote %}

1. Configure and launch your project:

    - A list of instructions is provided in [Tutorials for popular tasks](../tutorials/usecases.md).

    - General instructions in the [Starting and tuning a project](main-steps.md) section.

## How to complete tasks {#self}

To complete your tasks in the sandbox:

1. Register in the sandbox as a Toloker:

    1. Go to the [Toloker sandbox sign-in page](https://we.sandbox.toloka.ai/auth?role=TOLOKER).

    1. Click a social service where you have an account.

    1. You will be redirected to the selected service authorization page. Follow the service steps to sign in using your social account.

    1. Once you sign in to the selected service, you will be redirected back to Toloka. The system will invite you to enter your phone number and will send you a confirmation code to make sure that the phone number you entered is correct and belongs to you.

    1. If all is good, you will get access to the sandbox as a Toloker.

1. Now log in to the [sandbox]({{ sandbox }}) using the requester account.

1. Open the [Users](https://platform.sandbox.toloka.ai/requester/workers) page and click **Add trusted Tolokers**.

1. Click **Add Toloker** and enter the phone number of the created Toloker or the Toloker ID.

    {% cut "Where to get the Toloker ID" %}

    You can get the Toloker ID together with the phone number on the Toloker **sandbox** [Profile](https://we.sandbox.toloka.ai/profile) page:

    ![Getting Toloker ID](../_images/register/add-trusted-toloker.png =370x)

    {% endcut %}

    Only trusted Tolokers can access your tasks. The number of trusted Tolokers required for testing depends on the [overlap settings](dynamic-overlap.md).

    {% cut "Overlap settings" %}

    To test your project in the sandbox with only one Toloker, set [overlap](../../glossary.md#overlap) value to **1**. If you increase the overlap, you will need to register more Tolokers and add trusted accounts: the overlap value will be equal to the number of trusted Tolokers you need to complete your tasks.

    When [exporting a project](#export) to the production version of Toloka, you can specify the necessary overlap in accordance with your project goals.

    {% endcut %}

1. [Log in to the sandbox](https://we.sandbox.toloka.ai/auth?role=TOLOKER) using the Toloker account and test your tasks. Make sure that the buttons and task response validation are set up correctly, and assess how long it takes to complete the tasks. Make sure that the [Toloker selection](filters.md) and [quality control](control.md) work.

## How to move projects to the production version of Toloka {#export}

{% note alert "Restriction" %}

Note that you can move only project and [pool](../../glossary.md#pool) settings. You can't move tasks and responses to them. The project's [quality control](../../glossary.md#quality-control) settings can't be moved, either.

{% endnote %}

To move projects from the sandbox to the production version:

1. Link the sandbox and production version accounts:

    1. Open the **Integrations** tab in the production version on the [profile](https://platform.toloka.ai/requester/profile/integration) page, click **![Plus sign](../_images/plus-sign.svg) Generate token**, create a new API key, and copy it.

    1. Open the same tab in the sandbox on the [profile]({{ sandbox-profile }}) page, paste the copied token into the **Main Toloka API token** field, and click **Add token**.

1. Go to the project page in the sandbox and click **![Drop-down button](../_images/drop-down.svg) → ![Export button](../_images/location-job/project/export.svg) Export**.

1. Choose the pools to export and click **Export**.

    If the pool has [linked training](train.md), it is exported automatically.

## Troubleshooting {#troubleshooting}

{% include [faq-see-pool-as-toloker](../_includes/faq/sandbox/see-pool-as-toloker.md) %}

{% include [faq-same-account](../_includes/faq/sandbox/same-account.md) %}

{% include [troubleshooting-export-error](../_includes/troubleshooting/sandbox/export-error.md) %}

{% include [faq-check-mobile-version](../_includes/faq/sandbox/check-mobile-version.md) %}

{% include [faq-copy-from-sandbox](../_includes/faq/sandbox/copy-from-sandbox.md) %}

{% include [troubleshooting-submit](../_includes/troubleshooting/sandbox/submit.md) %}

{% include [faq-move-control-tasks](../_includes/faq/sandbox/move-control-tasks.md) %}

{% include [troubleshooting-dont-see-task](../_includes/troubleshooting/sandbox/dont-see-task.md) %}

{% include [troubleshooting-cant-add-trusted-user](../_includes/troubleshooting/sandbox/cant-add-trusted-user.md) %}

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles-internal.md) %}