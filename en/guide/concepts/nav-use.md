# Using the skill

You can use skills to filter and select Tolokers when assigning tasks, issuing bonuses, and sending out messages.

## Selecting Tolokers for tasks {#selection}

When setting up a pool, you can use skills in [filters](filters.md) to:

- Select Tolokers without a skill. To do this, use the `=`, and leave the value empty.
- Select Tolokers with any skill value. Use the `≠` operator, and leave the value empty.
- Select Tolokers who have a skill value greater than or less than the specified one.

For example, you can select only those Tolokers whose skill is more than 66 or is missing:

![](../_images/other/qcr-control_example_filter.png)

For [global skills](nav-cross-project.md), the restrictions of the `skill >80`type are used to select “Tolokers who completed similar projects 80% better on average than other Tolokers”.

## Extra bonuses {#awarding}

To select Tolokers by skill and give them [bonuses](../../glossary.md#bonus):

1. Go to the [Tolokers]({{ users }}) page.

1. Select Tolokers using the skill filter. To do this, use [filters](../../glossary.md#filters):

    1. Click **Add filter**.

    1. Scroll down and choose **Choose skill**.

    1. Specify the skill and the required skill value.

1. To credit bonuses to one Toloker, click the link to their ID in the **Toloker ID** field.

    On the page that opens, click **Actions → Issue bonus**.

    To credit bonuses to a group of Tolokers click **Issue bonus**.

1. Fill in the fields in the **Issue bonus** window that appears:

    - **Bonus per user** in dollars.

    - **Topic** and **Message** for Tolokers. Specify the projects and accomplishments the bonus was granted for. To send messages in different languages, use the button for switching languages.

1. Click **Grant**.

    Before doing this, check the number of people who will receive the bonus, and the total amount.

    {% cut "Example" %}

    ![](../_images/bonus/bonus-group-performers-1.png)

    {% endcut %}

## Sending out messages {#messaging}

To select Tolokers for [sending messages](qa-assign.md) about changes in the project or new tasks:

1. Go to the **Messages** page.

1. Click **Compose → To users group → Add filter → Choose skill**.

1. Enter the skill name.

## What's next {#what-next}

If necessary, you can:

- [Edit](nav-edit.md) the skill value manually.
- [Remove](nav-delete.md) skill for a specific Toloker.
- [View the history](nav-history.md) of skill changes.

## See also {#see-also}

- [{#T}](nav-create.md)
- [{#T}](nav-assign.md)
- [{#T}](filters.md)

## Troubleshooting {#troubleshooting}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% include [troubleshooting-training](../_includes/troubleshooting/users/training.md) %}

{% include [contact-support](../_includes/contact-support.md) %}