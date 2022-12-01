# Communication

In Toloka, you can exchange information with Tolokers through messages and receive notifications about the progress of labeling and other events, as well as news and recommendations. To search, view, and send messages, go to the [Messages]({{ messages }}) page.

## Message types

There are several types of messages. To switch between them, select one of the following on the right of the screen:

- {% if locale == "ru-ru" %}**Inbox**{% elsif locale == "en-com" %}**Inbox**{% endif %}: Messages you received.

- {% if locale == "ru-ru" %}**Sent**{% elsif locale == "en-com" %}**Sent**{% endif %}: Messages you sent. Recipients can be:

    - Any Toloker who started at least two of your tasks.

    - A group of Tolokers that you can select using [filters](filters.md). To do this, click {% if locale == "ru-ru" %}**+ Add filter**{% elsif locale == "en-com" %}**+ Add filter**{% endif %}.

    - Individual Tolokers. In the {% if locale == "ru-ru" %}**To**{% elsif locale == "en-com" %}**To**{% endif %} field, specify the Toloker ID or several comma-separated IDs.

- {% if locale == "ru-ru" %}**Users**{% elsif locale == "en-com" %}**Users**{% endif %}: Messages from Tolokers.

- {% if locale == "ru-ru" %}**Administrator**{% elsif locale == "en-com" %}**Administrator**{% endif %}: Messages from the platform.

- {% if locale == "ru-ru" %}**Notifications**{% elsif locale == "en-com" %}**Notifications**{% endif %}: System notifications about pool or aggregation completion and other events, as well as messages from the Toloka team, news, and recommendations.

- {% if locale == "ru-ru" %}**Important**{% elsif locale == "en-com" %}**Important**{% endif %}: Messages that you marked as important (using the ![](../_images/other/important.svg) label).

{% note info %}

You can specify which messages you consider important. To do this, click ![](../_images/other/important-inactive.svg) under the message date.

{% endnote %}

## Searching for messages

To find all the messages received from a certain Toloker, enter their ID in the search box in the upper-right corner and click {% if locale == "ru-ru" %}**Search**{% elsif locale == "en-com" %}**Search**{% endif %}.
To find messages by keyword, enter a keyword or phrase in the search box.

## When to write to Tolokers

Send a message to Tolokers who performed your tasks if:

- You've made some changes to the tasks. For example, you edited the [instructions](../../glossary.md#instructions), changed the rule for calculating the [skill](../../glossary.md#skill), or need the Tolokers to do the training again.

- The Tolokers have questions about the task or instructions. Make sure to answer their questions because the labeling quality depends on how well the Tolokers understand the task. If some questions are repeated, add your answers to the instructions or add illustrative examples to the training pool.

- There is a new [project](../../glossary.md#project) to which you want to invite the Tolokers who successfully completed similar tasks. Or you added a new [pool](../../glossary.md#pool) to the project after a long break.

- A Toloker filed an [appeal](accept.md#appeal) after you reviewed their responses. If the responses were mistakenly rejected, accept them. Make sure to review all appeals and respond on time (within 9 days after the responses were rejected).

- Something was wrong with the task and now it's fixed.

{% note info %}

If the issue is related to how the platform works in general (such as money withdrawals), refer the Toloker to the [Toloka support]({{ toloka-support }}).

{% endnote %}

## How to write a message

1. [Assign a skill](nav-assign.md) to everyone who completed your tasks. The skill should be hidden.

1. Go to the [Messages]({{ messages }}) page and send notifications to Tolokers with the skill. To do this, click {% if locale == "ru-ru" %}**Contact** → **Group of Tolokers** → **+ Add filter**{% elsif locale == "en-com" %}**Contact** → **Group of Tolokers** → **+ Add filter**{% endif %}.

1. Specify the subject of your message in the {% if locale == "ru-ru" %}**Subject**{% elsif locale == "en-com" %}**Subject**{% endif %} field.

1. Fill in the {% if locale == "ru-ru" %}**Message text**{% elsif locale == "en-com" %}**Message text**{% endif %} field.

1. Select {% if locale == "ru-ru" %}**Allows replies**{% elsif locale == "en-com" %}**Allows replies**{% endif %}.

1. Click {% if locale == "ru-ru" %}**Submit**{% elsif locale == "en-com" %}**Submit**{% endif %}.

## Recommendations

- Only write to Tolokers who are not banned and who meet your project requirements. Otherwise, they won't be able to find your task and will have questions about that.

- Tolokers and requesters in Toloka are anonymous. Don't specify your contact details or request them from Tolokers. Contact information includes phone numbers, email addresses, and social network or messenger accounts.

- Show respect to Tolokers and use a business writing style. If you received an offensive message from a Toloker, contact the [Toloka support]({{ toloka-support }}).

- Don't send too many bulk emails to avoid alienating Tolokers.

- Make sure your messages don't contain any ads for websites, apps, products, or services.

- Don't offer Tolokers to do any tasks outside the platform. Don't use Toloka for recruiting new employees.

## Technical limitations

- If there are more than 1000 recipients in the mailing list, an error may occur when sending the message. To avoid this, use the [API](../../api/concepts/messages.md).

- Send your emails in small batches. To do this, use [filters](filters.md).

- Don't send links to your project copied from the browser address bar. They won't work for Tolokers because they use a different URL format. If you want to specify a project link, use the following format: `https://toloka.yandex.com/tasks?projectId=<ID of your project>`. For example, `https://toloka.yandex.com/tasks?projectId=112233`.

- Toloka doesn't let you attach photos and video files to messages. Use a photo hosting service or cloud storage for that. Insert a file link into the message using a visual editor. If you need a Toloker to send you a screenshot or photo, ask them to upload the file to a photo hosting service or cloud storage and send you a link.

- Don't use complex formatting or HTML. Some tags are not supported in emails. For more information, see [HTML markup](instruction.md#html). The mobile apps have even more technical restrictions. For example, the Android app doesn't display images.

## How to receive messages by email

Open the {% if locale == "ru-ru" %}**Notifications**{% endif %}{% if locale == "en-com" %}**Notifications**{% endif %} tab in the [requester profile]({{ profile }}) and enable {% if locale == "ru-ru" %}**Email**{% endif %}{% if locale == "en-com" %}**Email**{% endif %} for the **New message** event. Messages will be sent to the email address specified in the profile.

## Marking messages as read

To mark a message as read, click ![](../_images/other/read.svg) to the left of its subject.

To mark multiple messages at once, click {% if locale == "ru-ru" %}**Mark all as read**{% elsif locale == "en-com" %}**Mark all as read**{% endif %} above the message list.

## Troubleshooting {#troubleshooting}

{% cut "How can I notify the Toloker of changes in the instructions?" %}

Add a notification to the project description (for example: "Attention! The instructions have changed") and send a message to all the Tolokers who completed your tasks. To do this:

- Assign them a hidden skill or use an existing [skill](nav-assign.md) linked to the pool.

- Go to **Messages**, and click {% if locale == "ru-ru" %}**Contact** → **Group of Tolokers** → **+ Add filter** → **My skills** → **&lt;skill&gt;**{% elsif locale == "en-com" %}**Contact** → **Group of Tolokers** → **Add filter** → **My skills** → **&lt;skill&gt;**{% endif %}.

- If you created a new skill, specify the value you assigned to the chosen group (for example, 1). If you use an existing skill, specify the minimum value.

{% endcut %}

{% include [contact-support](../_includes/contact-support-help.md) %}
