# Remove a skill

{% list tabs %}

- In the interface

  You can remove a skill only manually. It can't be done using quality control rules.

  1. Go to the [Tolokers]({{ users }}) page.

  1. Select the Tolokers to remove the skill from.

      {% include [select-tolokers](../_includes/select-tolokers.md) %}

  1. Click **-Skill**.

  1. Select a skill.

  1. Click **Delete**.

- Via Toloka API

  To remove a skill from a Toloker using Toloka API, send a `DELETE` request with the specified ID of the skill you want to remove that is assigned to the "skill-Toloker" pair:

  ```bash
  curl -X DELETE 'https://toloka.dev/api/v1/user-skills/54116339' \
       -H 'Authorization: ApiKey PlaceYourRealApiKey_Here'
  ```

  {% note tip "Visit Toloka API reference" %}

  Refer to the [Remove skill from Toloker](https://toloka.ai/docs/api/api-reference/#delete-/user-skills/-id-) section of the Toloka API documentation for more details about the request, its parameters, and possible responses. You will find examples of the requests for [Toloka-Kit](../../toloka-kit/index.md) and other code samples there.

  {% endnote %}

{% endlist %}

## See also {#see-also}

- [{#T}](nav-create.md)
- [{#T}](nav-assign.md)
- [{#T}](nav-use.md)
- [{#T}](nav-edit.md)
- [{#T}](filters.md)

## For developers {#for-developers}

- [Toloka API: Removing skill from Toloker](https://toloka.ai/docs/api/api-reference/#delete-/user-skills/-id-)
- [Toloka-Kit recipe: Remove skill from Toloker](../../toloka-kit/recipes/delete-user-skill.md)

## Troubleshooting {#troubleshooting}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% include [troubleshooting-training](../_includes/troubleshooting/users/training.md) %}

{% include [contact-support](../_includes/contact-support.md) %}