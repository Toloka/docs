# Filters

You can use filters to select Tolokers for your project. Tasks will only be shown to matching Tolokers rather than all of them. Properly configured filters help you send tasks to a target group of Tolokers. As a result, you'll get your results faster and spend less money.

To select Tolokers for a [pool](../../glossary.md#pool-ru), click {% if locale == "en-com" %}**Add filter**{% endif %} on the pool editing page.

From the drop-down list, select filters by profile data and device specifications.

{% note info %}

To add filters faster, copy them from another pool (the {% if locale == "en-com" %}**Copy settings from…**{% endif %} button).

{% endnote %}


All filters added to the pool are applied simultaneously. The criteria within a single filter are combined with the logical OR operator.

{% note info %}

Tasks in pools are automatically available in the web version of Toloka and the mobile app. If you want to change the default settings and limit the visibility of the task for any of the versions, add the {% if locale == "en-com" %}**Client**{% endif %} filter and select the desired value: {% if locale == "en-com" %}**Toloka web version**{% endif %} or {% if locale == "en-com" %}**Toloka for mobile**{% endif %}.

{% endnote %}


## Skill {#filter-skill}

You can select Tolokers with or without a [skill](../../glossary.md#skill-ru) and filter them by skill value.

You can use [global skills](nav-cross-project.md) as a filter to recruit Tolokers who are good at certain types of tasks. To do this, select  and specify the restriction for the selected skill in the filter.

Examples of using a skill filter:

{% cut "I need Tolokers without a skill" %}

Use the `=` operator and leave the value empty.

![](../_images/location-job/filters/filter-skill-1.png)

{% endcut %}

{% cut "I need Tolokers with a skill and the skill level doesn't matter" %}

Use the `≠` operator and leave the value empty. For example, use this to choose Tolokers who are already familiar with the type of tasks like those in your pool.

![](../_images/location-job/filters/filter-skill-2.png)

{% endcut %}

{% cut "I need Tolokers with a skill of a certain level" %}

Add a filter, enter a value from 0 to 100, and use a set of operators. For example, you can select only those Tolokers who previously completed a certain number of tasks of the type like in your pool.
![](../_images/location-job/filters/filter-skill-3.png)

{% endcut %}

{% cut "I need Tolokers with a global skill of a certain level" %}

Add a global level filter, enter a value from 0 to 100, and use a set of operators. For example, you can select only those Tolokers whose responses were on average better than the responses of 80% of annotators in similar projects.
![](../_images/location-job/filters/filter-skill-4.png)

{% endcut %}


## Toloker profile {#filter-user-profile}

Use filters from this group to select Tolokers by the main profile data.

{% cut "Languages" %}

Make sure to add the {% if locale == "en-com" %}**Languages**{% endif %} filter and specify the language of the [instructions](../../glossary.md#task-instruction-ru) and text in the task.

If you want to be sure that Tolokers can read and understand the basic vocabulary, select those who passed a language test.

{% endcut %}

{% cut "Adult content" %}

If there is adult content in the pool tasks, they will only be shown to Tolokers who have agreed to see them. To select such Tolokers, add the **Adult content** filter and select the **On** option.

{% endcut %}

{% cut "City" %}

You can choose Tolokers who live in certain cities. Use this filter for field tasks or to search for data online.

{% endcut %}

{% cut "Citizenship" %}

Use this filter when the Toloker's citizenship may affect the quality of responses, like if your project asks Tolokers to complete a survey, transcribe audio, or search for information online. You can also use this filter to restrict Tolokers' access to tasks.

{% endcut %}

{% cut "Date of birth" %}

Using a set of operators, you can select an age-based audience among available Tolokers.

{% endcut %}

{% cut "Education" %}

Add this filter if the Toloker's education may affect the quality of responses. Use the `=` or `≠` operator and select **Secondary**, **Vocational secondary**, or **Higher** education from the drop-down list.

{% endcut %}

{% cut "Gender" %}

You can choose Tolokers of a certain gender if this matters for your project.

{% endcut %}

{% cut "Country" %}

Add this filter to restrict the audience by region.

{% endcut %}

{% cut "Verified" %}

Use this filter if you need additional guarantees when selecting Tolokers. Your tasks will only be available to Tolokers whose personal details are verified in Toloka.

{% endcut %}

## Calculated data {#filter-calc-data}

Use filters from this group to select Tolokers by device type, browser, or software versions.

{% cut "Browser" %}

Use this filter if your tasks are intended for users with certain web browsers.

{% endcut %}

{% cut "Device type" %}

If the type of the Toloker's device matters, use the `=` and `≠` operators to set the requirements.

{% endcut %}

{% cut "Client" %}

Tasks in pools will automatically be available in the web version of Toloka and the mobile app. If you want to change the default settings and limit the visibility of the task for any of the versions, add the {% if locale == "en-com" %}**Client**{% endif %} filter and select the desired value: {% if locale == "en-com" %}**Toloka web version**{% endif %} or {% if locale == "en-com" %}**Toloka for mobile**{% endif %}.

If your project contains field tasks, you need to select mobile Toloka users among the Tolokers.

{% endcut %}

{% cut "Operating system" %}

Add this filter to select users of certain operating systems.

{% note info %}

To select the most popular desktop operating systems — MacOS, Windows, and Linux, add the {% if locale == "en-com" %}**Operating system**{% endif %} filter. Use the `=` operator to set the value as `Windows`. Use the ![](../_images/add.svg) button to add the second value, `MacOS`. Then click ![](../_images/add.svg) again and set the third value, `Linux`.

{% endnote %}

{% endcut %}

{% cut "Region by IP" %}

To make a task available to users with IP addresses of a particular region, add the {% if locale == "en-com" %}**Region by IP**{% endif %} filter and enter the region name. This is useful for field tasks.

{% endcut %}

{% cut "Region by phone number" %}

To more effectively choose Tolokers by location, add the {% if locale == "en-com" %}**Region by phone**{% endif %} filter.

{% endcut %}

{% cut "Type of client application" %}

Select this filter if the browser type determines whether Tolokers match your project tasks.

{% endcut %}

## What's next {#what_next}

- [Add tasks to the pool](pool.md)
- Learn more about how to set up a pool:
    - [Setting up pricing](dynamic-pricing.md).
    - [Dynamic overlap](dynamic-overlap.md).
    - Selective [majority vote](selective-mvote.md) control.
    - [Speed/quality balance](adjust.md).
    - [Setting up quality control](qa-pool-settings.md).
    - [Reviewed assignments](offline-accept.md).



### Troubleshooting {#troubleshooting}

{% cut "Tolokers" %}

{% cut "Why can't I find the Toloker's gender in the Toloker data, although I can filter people by this attribute in the pool settings?" %}

Requesters can't see the full details about specific Tolokers. So you can't see information like the date of birth, gender, last name, or first name. However, you can use filters by date of birth and gender (in the pool settings). This way you can select a group of Tolokers without accessing the personal information of individual Tolokers. This decreases the risk of user de-anonymization.

{% endcut %}

{% cut "Can I set up a task to be visible to Tolokers with certain demographic and geo parameters? For example, ’Moscow only, 30-45 years old’." %}

You can do that. To select Tolokers for the pool, use [filters](filters.md).

{% endcut %}

{% cut "Can I add an arbitrary user as a Toloker?" %}

If the Toloker mismatches your preset filter, they can't see the task. You can only remove the restricting filter from the pool. You can test the task in the [Sandbox](sandbox.md) by adding the desired user to your trusted list.

{% endcut %}

{% cut "Can I somehow limit the number of Tolokers who can take tasks from the pool at the same time?" %}

Tasks from an open pool are available to all Tolokers matching your pool [filters](filters.md). You can restrict access, like by using a skill.

{% endcut %}

{% cut "Can I select Tolokers from a specific city of residence or is the only option ’Region by IP’?" %}

Yes, you can do that. In the [filters](filters.md), select **Profile → City**. Please note that the profile data is entered by the Toloker when they register in Toloka. We recommended that you use the filters **Region by phone number** and **Region by IP**.

{% endcut %}

{% cut "Can I use a skill beyond a particular pool or project and apply it to other projects as well?" %}

Yes, of course — you can use the same skill for different projects. But most often, a skill is intended for a specific project. If the Toloker completes a certain task well, this doesn't mean that they will complete other ones successfully. Another disadvantage is that if you filter by skills that were set long ago, you will artificially limit the number of available Tolokers.

{% endcut %}

{% endcut %}

{% cut "Skill" %}

{% cut "I want to calculate a skill based on performance in multiple projects. Is that possible? If it is, can I use "Aggregation by skill"?" %}

If you mean multiple different projects, you can't do that.

You can merge all the projects into one and use **History size** in the quality control rules. See examples in the [Control tasks](goldenset.md) post.

You can use **Aggregation by skill**, but you'll need to list all the possible values, which is probably not the best choice. Perhaps you'll find [another method of aggregation](result-aggregation.md) helpful.

{% endcut %}

{% cut "Are there any easy ways to assign a certain Toloker a skill in Toloka, even if they didn't do any tasks (like I can do in the Sandbox)?" %}

In the main Toloka version, you can only assign a skill to Tolokers who have completed at least one of your tasks. There is no way to assign a skill to just any annotator. To limit the visibility of your project, use [filters](filters.md). For example, specify the city, date of birth, gender, or some other parameters of your target Tolokers.

{% endcut %}

{% cut "The Tolokers completed training for the first pool and got the skill. A week later, we cloned the pool, but all Tolokers lost their skill. Which parameter affects skill expiration? Do all the Tolokers need to complete the training again?" %}

The validity period of the training skills is controlled by the **Retry after** parameter. The skill is deleted after a period specified in days in the **Retry after** field, if the Toloker:
- Has a skill value lower than the one specified in the **Level required** field.
- Didn't complete any tasks linked to training during this period.

Your Tolokers will need to complete the training again.

{% endcut %}

{% cut "Can I select specific Tolokers for my tasks because I liked their results in my previous pools?" %}

You can assign a skill to these people based on their performance in the previous pools. Use this skill as a [filter](filters.md) in the new pool.

{% endcut %}

{% cut "How do I set up a filter so that the pool is available to Tolokers who don't have a specific skill (like a "spammer")?" %}

Specify this skill as a [filter](filters.md), but leave the value field empty (this is equivalent to absence of the skill).

{% endcut %}

{% cut "How can I raise the skill value for a Toloker, if they already have the skill?" %}

If the Toloker already has a skill, you can't add the same skill to them from the task review interface. You can open the Toloker's profile and edit the skill value.

{% endcut %}

{% cut "Can Tolokers see that they were assigned a skill?" %}

If it's a public or training skill, they see it and they get a message about it.

{% endcut %}

{% cut "Can I show a skill in the task interface?" %}

There is no such option. If the skill is public, the Toloker sees it in their profile.

{% endcut %}

{% cut "How do I automatically assign skills based on Toloker responses to my questions?" %}

You can do that using the [Control tasks](goldenset.md) rule.
1. Upload the task file using **Smart mixing**.
1. Specify `student` as the correct answer to the question. Don't take other questions into account (leave the fields empty or unselected).
1. Add the [Control tasks](goldenset.md) rule to the pool: `if the percentage of correct control answers = 100, then set the skill value Student = 1`.

{% cut "See the screenshot" %}

![](../_images/troubleshooting/set-questionnaire-skill-student.png)

{% endcut %}

{% endcut %}

{% endcut %}

{% cut "How do I make the task available not only from desktops, but also from mobile devices?" %}

Tasks in pools are automatically available in the web version of Toloka and the mobile app. Check the pool settings. You might have the `Client = Mobile Toloka`[filter](filters.md) on.

{% endcut %}

{% cut "Why is my project not available in the mobile version of Toloka?" %}

Tasks in pools are automatically available in the web version of Toloka and the mobile app. Check the pool settings. You might have the `Client = Toloka web version`[filter](filters.md) on.

{% endcut %}

{% include [contact-support](../_includes/contact-support-help.md) %}
