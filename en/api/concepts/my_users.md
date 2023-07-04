# Toloker selection

You can control which type of Tolokers are completing your tasks. For instance, you can select Tolokers by region or assign tasks to Tolokers whose responses have passed quality control tests.

You can filter Tolokers by the following criteria:

- Information in the profile, device characteristics (IP address, OS used, and so on), and the Toloker rating in Toloka. To do this, set up [filters](filters.md) in the pool.

- Quality of task completion. You can filter out Tolokers who enter incorrect responses, often skip tasks, and so on. To do this, set up a [quality control rule](quality_control.md). To set up Toloker selection using control tasks or the majority vote, you must create a [skill](https://toloka.ai/docs/api/api-reference/#tag--skill). The skill is used for storing information about a Toloker's correct responses.

- Individually. You can [block a Toloker's access](https://toloka.ai/docs/api/api-reference/#tag--user-restriction) to one or more projects.

## How to select Tolokers {#select-users}

- [Using skills](https://toloka.ai/docs/api/api-reference/#tag--skill)
- [Using quality control rules](quality_control.md)
- [Using filters](filters.md)
- [Using bans](https://toloka.ai/docs/api/api-reference/#tag--user-restriction)

## Learn more {#links}

- [Viewing Tolokers](../../guide/concepts/users.md)
- [Description of skills](../../guide/concepts/nav.md)
- [Quality control rules](../../guide/concepts/check-performers.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}