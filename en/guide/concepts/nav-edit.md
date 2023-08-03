# Editing a skill

You can both edit the skill itself and change the skill values for a specific Toloker.

## Changing the skill value for a Toloker {#value-edit}

{% list tabs %}

- In the interface

  1. Go to the [Tolokers]({{ users }}) page.

  1. Select the Tolokers to change the skill value for.

      {% include [select-tolokers](../_includes/select-tolokers.md) %}

  1. Hover over the skill line and click ![](../_images/edit.svg).

  1. Enter the new skill value.

  1. Click **Save**.

- Via Toloka API

  To edit a skill using Toloka API, send a `PUT` request with all the skill parameters including the ones you want to modify:

  ```bash
  curl -X PUT 'https://toloka.dev/api/v1/skills/11294' \
       -H 'Authorization: ApiKey PlaceYourRealApiKey_Here' \
       -H 'Content-Type: application/json' \
       -d '{"name":"Programmer","public_name":{"EN":"Programmer"},"public_requester_description":{"EN":"You are an expert in programming languages"},"private_comment":"Got at least 5 right responses on control tasks with C++ or Python","hidden":true,"deprecated":false}'
  ```

  {% note tip "Visit Toloka API reference" %}

  Refer to the [Edit skill](https://toloka.ai/docs/api/api-reference/#put-/skills/-id-) section of the Toloka API documentation for more details about the request, its parameters, and possible responses. You will find examples of the requests for [Toloka-Kit](../../toloka-kit/index.md) and other code samples there.

  {% endnote %}

{% endlist %}

## Editing the skill parameters {#reward-edit}

1. Open the **Skills** page.

1. Hover the cursor over the desired skill and click ![](../_images/edit.svg).

1. Change the skill name, type, or description and click **Save**.

## See also {#see-also}

- [{#T}](nav-create.md)
- [{#T}](nav-assign.md)
- [{#T}](nav-use.md)
- [{#T}](nav-delete.md)
- [{#T}](filters.md)

## For developers {#for-developers}

- [Toloka API: Setting skill value](https://toloka.ai/docs/api/api-reference/#put-/user-skills)
- [Toloka API: Editing skill](https://toloka.ai/docs/api/api-reference/#put-/skills/-id-)
- [Toloka-Kit recipe: Edit skill](../../toloka-kit/recipes/edit-skill.md)
- [Toloka-Kit recipe: Assign skill to Toloker](../../toloka-kit/recipes/assign-skill.md)

## Troubleshooting {#troubleshooting}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% include [troubleshooting-training](../_includes/troubleshooting/users/training.md) %}

{% include [contact-support](../_includes/contact-support.md) %}