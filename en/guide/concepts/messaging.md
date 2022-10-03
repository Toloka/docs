# Communication

Answer questions about tasks. Send out a group message if there are changes in the tasks (for example, the [instructions](../../glossary.md#task-instruction-ru) were edited, or [skill](../../glossary.md#skill-ru) calculation has changed).

{% note info %}

If a question is related to how the platform works in general (like a question about withdrawals), refer the Toloker to the [Toloka support service]({{ toloka-support }}).

{% endnote %}


## Getting and sending messages {#private}

To receive and send messages, go to the [Messages]({{ messages }}) page.

Recipients can be:

- Tolokers who completed your tasks or were interested in them.

- Group of Tolokers (use [filters](filters.md)).

- Selected Tolokers (specify the Toloker IDs separated with space).


If there are changes in the [project](../../glossary.md#project-ru) (for example, you edited the instructions or changed skill calculation), notify all Tolokers who completed your tasks.

1. [Set the skill level](nav-assign.md) for everyone who completed your tasks. The skill should be private.

1. Go to the [Messages]({{ messages }}) page and send notifications to Tolokers with the skill you set. To do this, use filters ({% if locale == "en-com" %}{% endif %}).


You can receive copies of incoming messages by email. Go to the {% if locale == "en-com" %}**Notifications**{% endif %} tab in the [requester profile]({{ profile }}) and select the option {% if locale == "en-com" %}**Send copies of messages by email**{% endif %} for the **New message** event.


## Troubleshooting {#troubleshooting}

#### How can I notify the Toloker of changes in the instructions?

Add the notification to the project description (for example: “Attention! The instructions changed”) and send a message to all the people who completed your tasks. To do this:
- Assign them a hidden skill, or use an existing [skill](nav-assign.md) linked to the pool.
- Go to **Messages** and click **Write** → **Group** → **Add filter** → **Choose your skill** → **<skill name>**.
- If you created a new skill, specify the value you assigned to the chosen group, (for example, 1). If you use an existing skill, specify the minimum value.


{% include [contact-support](../_includes/contact-support-help.md) %}
