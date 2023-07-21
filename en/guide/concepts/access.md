# Registration

## Social authorization in Toloka {#social-auth}

Toloka clients can to register and access Toloka using social authorization. If you registered in Toloka using Yandex ID, please [migrate to the new social authorization](migrate-new-auth.md) scheme.

To register in Toloka as a client and post tasks for Tolokers, you need to have one of the following supported social accounts:

- Google
- Facebook
- GitHub
- Microsoft

{% note info %}

Depending on your current location the list of the available social accounts might differ and include or exclude some of the social services.

{% endnote %}

Some of the clients can also authorize in Toloka using SSO authentication. Read the [Toloka SSO authentication](../sso/authentication.md) section which contains the detailed description of this method and its restrictions.

## Where should I register? {#register}

Toloka has two versions: production and sandbox. You need to register in each one separately to get access to them:

- **[Production version]({{ yandex-toloka }})**

    This is your usual workspace in Toloka. Here you [create projects](project.md), [upload tasks](task_upload.md) for Tolokers, and [get results](result-of-eval.md).

- **[Sandbox]({{ sandbox }})**

    This is a place to test your projects and tasks. It can be useful to test complex projects before launching them. Learn more about [working in the sandbox](sandbox.md).

The registration and sign-in processes are similar for both versions.

## Authorizing in Toloka with social services {#authorize}

Toloka uses social authorization both for the **registration** and **signing in**.

To authorize in Toloka production version using one of the social accounts, go to the [sign-in page]({{ yandex-toloka }}).

{% list tabs %}

- Registering

  1. Click the button with the social service name.

  1. You will be redirected to the selected service authorization page. Follow the service steps to sign in using your social account.

  1. Once you sign in to the selected service, you will be redirected back to Toloka. The system will invite you to enter some additional information (email address used for notifications, company name, country of origin, and some other optional information).

  1. When done, accept the Toloka Terms of Use and click **Get started**.

- Signing in

  1. Click the button with the social service name.

  1. You will be redirected to the selected service authorization page. Follow the service steps to sign in using your social account.

  1. Once you sign in to the selected service, you will be redirected to your Toloka dashboard.

{% endlist %}

## Recommendations {#concept_pkf_nks_vlb}

- To avoid confusion, use the same social service to register as a requester both in the production version and sandbox.

- If you plan to share projects with coworkers or need help setting up your account, read our [Shared access to the account](multiple-access.md) instructions.

## See also {#see-also}

- [Migrating to new social authorization](migrate-new-auth.md)
- [{#T}](overview.md)
- [{#T}](multiple-access.md)
- [{#T}](sandbox.md)
- [Learn how to post tasks](first-project.md)

## Troubleshooting {#troubleshooting}

{% include [faq-task-suitable](../_includes/faq/register-and-start/task-suitable.md) %}

{% include [faq-change-account-type](../_includes/faq/register-and-start/change-account-type.md) %}

{% include [faq-email-authorization](../_includes/faq/register-and-start/email-authorization.md) %}

{% include [faq-same-email-registration](../_includes/faq/register-and-start/same-email-registration.md) %}

{% include [troubleshooting-microsoft-sso](../_includes/troubleshooting/register-and-start/microsoft-sso.md) %}

{% include [troubleshooting-facebook-problem](../_includes/troubleshooting/register-and-start/facebook-problem.md) %}

{% include [faq-start-new-project](../_includes/faq/register-and-start/start-new-project.md) %}

{% include [contact-support](../_includes/contact-support.md) %}