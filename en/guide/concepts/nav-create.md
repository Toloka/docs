# Creating a skill

To create a skill:

{% list tabs %}

- In the interface

  1. Click **+ Add skill** on the [Skills]({{ skills }}) page.

  1. Enter the name of a new skill into the **Title** field. The skill name should be short, clear and easy to distinguish from the names of other skills.

  1. Describe the skill in the **Description** field.

  1. Choose the value of the **Public?** option:

      - **No** — The default value. Tolokers will not be able to see the information about the skill.

      - **Yes** — Tolokers will see the name and the value of the assigned skill.

  1. Click **Add**.

  {% note tip %}

  To better motivate Tolokers, make the skill public and set [dynamic pricing](../../glossary.md#dynamic-pricing) based on this skill. In the task instructions, write what affects the skill value. Tolokers will know how the skill affects the price, and try to perform the tasks well.

  {% endnote %}

- Via Toloka API

  To create a skill using Toloka API, send a `POST` request with the information about the skill:

  ```bash
  curl -X POST 'https://toloka.dev/api/v1/skills' \
       -H 'Authorization: ApiKey PlaceYourRealApiKey_Here' \
       -H 'Content-Type: application/json' \
       -d '{"name":"Programmer","public_name":{"EN":"Programmer"},"public_requester_description":{"EN":"You are an expert in programming languages"}}'
  ```

  {% note tip "Visit Toloka API reference" %}

  Refer to the [Create skill](https://toloka.ai/docs/api/api-reference/#post-/skills) section of the Toloka API documentation for more details about the request, its parameters, and possible responses. You will find examples of the requests for [Toloka-Kit](../../toloka-kit/index.md) and other code samples there.

  {% endnote %}

{% endlist %}

## What's next {#what-next}

[Assign a skill](nav-assign.md) either manually or automatically.

## See also {#see-also}

- [{#T}](nav-use.md)
- [{#T}](nav-edit.md)
- [{#T}](nav-delete.md)
- [{#T}](filters.md)

## For developers {#for-developers}

- [Toloka API: Creating skill](https://toloka.ai/docs/api/api-reference/#post-/skills)
- [Toloka-Kit recipe: Create skill](../../toloka-kit/recipes/create-skill.md)

## Troubleshooting {#troubleshooting}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% include [troubleshooting-training](../_includes/troubleshooting/users/training.md) %}

{% include [contact-support](../_includes/contact-support.md) %}