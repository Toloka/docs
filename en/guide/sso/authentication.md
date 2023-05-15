# Toloka SSO authentication

Toloka allows its clients to use a single sign-on (SSO) authentication method to access the platform.

## SSO authentication advantages

- **Improved security**

    SSO gives organizations centralized control over who has access to their systems. You can immediately grant new employees access to Toloka. And, when someone leaves, you can immediately revoke access at once.

    You can set company-wide rules on how often team members need to change their passwords, password length, and other standards that ensure team members use secure passwords only. This isn't possible if team members register in Toloka themselves and have credentials set in accordance with their own understanding of security.

- **Reduced password fatigue**

    When clients use SSO to access Toloka, they only need to login on a device once to get access not only to Toloka, but to all the other apps that also use SSO.

    Without SSO, each additional app requires that people remember their credentials, and go through different authentication processes for each. With single sign-on, logins are automatic — one click and you're in.

- **Reinforced separation between personal and work accounts**

    One more benefit of SSO is its ability to reduce friction between work and personal applications. By requiring every employee to use SSO, admins gain control over access across all platforms used within their organization, including personal laptops or mobile devices owned by employees.

    No matter what industry you operate in or how robust security controls are within your organization, allowing employees unrestricted access through multiple doors doesn't strengthen security. Single sign-on lets your employees use one login/password combination across all their business-related apps separated from their personal apps.

## Toloka SSO authentication restrictions

- Toloka gives access to SSO authentication to **enterprise** clients only.

- You need to register as a company, not as an individual, and have a created company in Toloka platform. Please [contact our support team](../troubleshooting/support.md?form-topic1=other) to learn how you can do this.

- Currently, Toloka supports only SAML protocol for SSO authentication. OpenID Connect (OIDC) is not supported.

{% note info %}

Please contact your dedicated Toloka manager to help set up SSO authentication for your account.

{% endnote %}

## Managing account access

Employees of the companies for which Toloka enabled SSO authentication can use the following ways to gain SSO access for their Toloka accounts:

- Contact Toloka team and ask them to enable SSO authentication for their Toloka account.

OR

- Ask the account owner to give access to the account with SSO authentication (through the **Profile → Account access** tab). The account owner must give access to the employees using their business email addresses.

OR

- Employees of the companies who have proper permissions and already have SSO authentication enabled can grant access to their colleagues with business email addresses (through the **Profile → Account access** tab).

In this case, the clients don't need to create their Toloka account prior to gaining SSO access. They will be able to [log in](#sso-authentication) using their business email address.

{% note warning %}

Please note, that any user with full access rights to the account can manage the access to the account: grant access using either their email address or their colleague business email address for SSO authentication, and revoke access from other users.

{% endnote %}

## Logging in using SSO {#sso-authentication}

If your account has SSO authentication enabled, you can log in using your business email address.

1. Go to the Toloka login page [here]({{ yandex-toloka }}).

1. Click **Continue with SSO**:

    ![Continue with SSO](../_images/sso/toloka-login.png =465x)

1. At the next screen, enter your business email address (for example, `john.smith@microsoft.com`) and click **Log in**:

    ![Enter email and log in](../_images/sso/toloka-ms-sso-login.png =465x)

1. You will be redirected to your company SSO sign-in page. Follow the page steps to sign in using your business email address.

Once you pass the company authentication, you will be redirected back to Toloka.

Now you can create projects, pools, and upload tasks. You can also [generate API tokens](../concepts/api-token.md) for your applications.

## What's next {#what-next}

- [Generate API tokens](../concepts/api-token.md)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles-internal](../../../_includes/image-styles-internal.md) %}
