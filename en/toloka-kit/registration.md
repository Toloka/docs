# Getting OAuth token

Before you start using Toloka-Kit library, register in either the production or sandbox Toloka web version, get your OAuth token for the API access, and top up your account.

## Registration

1. [Register](../guide/concepts/access.md) in Toloka as a requester.

1. Toloka has two versions:

    - The [production](https://platform.toloka.ai/for-requesters/) version is used by default in [this example](./recipes/learn-basics.md).

    - The [sandbox](https://platform.sandbox.toloka.ai/for-requesters/) version is a testing environment for Toloka. [Learn more](../guide/concepts/sandbox.md)

## Getting OAuth token {#oauth-token}

Get an OAuth token for your version. Go to **Profile → Integrations** (or click [this link](https://platform.toloka.ai/requester/profile/integration)):

![List of tokens](../guide/_images/sso/token-list.png =700x)

Refer to the [Generating API tokens](../guide/concepts/api-token.md) section to learn how to issue OAuth tokens.

## Top up account {#top-up}

If you're going to use the production version, [add funds](../guide/concepts/refill.md) to your Toloka account.

## What's next {#what-next}

- [Install Toloka-Kit library](./quick-start.md)
- [Start your first simple project](./recipes/learn-basics.md)

{% include [image-styles-internal](../../_includes/image-styles-internal.md) %}