# Microsoft SSO authentication

Toloka allows its clients to use a single sign-on (SSO) authentication method to access the platform.

## Managing account access

Microsoft employees can use the following ways to gain SSO access for their Toloka accounts:

- Contact Toloka team and ask them to enable SSO authentication for their Toloka account.

OR

- Ask the account owner to give access to the account with SSO authentication (through the **Profile → Account access** tab). The account owner must give access to the employees using their _@microsoft.com_ business email addresses.

OR

- Microsoft employees who have proper permissions and already have SSO authentication enabled can grant access to their colleagues with _@microsoft.com_ business email addresses (through the **Profile → Account access** tab).

In this case, the clients don't need to create their Toloka account prior to gaining SSO access. They will be able to [log in](#sso-authentication) using their _@microsoft.com_ business email address.

## Logging in using SSO {#sso-authentication}

If your account has SSO authentication enabled, you can log in using your _@microsoft.com_ business email address.

1. Go to the Toloka login page [here](https://passport.toloka.ai/auth/list?origin=toloka_requesters&retpath=https%3A%2F%2Fplatform.toloka.ai%2Fsignup%2Frequester%3FauthRole%3Drequester).

1. Click **Login with SSO**:

    [![Login with SSO](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/sso/toloka-login.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/sso/toloka-login.png)

1. At the next screen, enter your business email address (for example, _john.smith@microsoft.com_) and click **Log in**:

    [![Enter email and log in](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/sso/toloka-ms-sso-login.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/sso/toloka-ms-sso-login.png)

1. You will be redirected to the Microsoft sign-in page. Enter your email address once again and click **Next**:

    [![Microsoft sign in](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/sso/microsoft-login.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/sso/microsoft-login.png)

Once you pass Microsoft authentication, you will be redirected back to Toloka.

Now you can create projects, pools, and upload tasks. You can also [generate API tokens](./api-token.md) for your applications.

## Next steps

- [Generate API tokens](./api-token.md)

{% include [image-styles](../../../_includes/image-styles.md) %}