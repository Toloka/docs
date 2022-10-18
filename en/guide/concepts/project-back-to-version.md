# Returning to a previous version of a project

All changes made to the [project](../../glossary.md#project) are saved in the version history. You can view previous versions or return to any of them.

The version number (for example, **1.2**) consists of two numbers:

1. The major version (the first number) appears when you change a [required field](incoming.md#required) in the input or output data:
    - Add, remove or rename a required field.
    - Change the field from optional to required.
    - Change the field parameters that aren't compatible with the current specification:
    - Reduce the maximum or increase the minimum number of items in the array.
    - Change allowed string values.
    - Reduce the maximum or increase the minimum length of a string.
    - Reduce the maximum or increase the minimum value for a number.

1. The minor version (the second number) appears when you make any other changes to the project.

{% note warning %}

Changes to the major version of the project don't affect existing [pools](../../glossary.md#pool).

{% endnote %}


To go back to the previous version of the project:
1. Go to the project editing.
1. Click **Select previous version** at the bottom of the page.

   {% cut "Project version example" %}

   ![](../_images/location-job/project/project_versions.png)

   {% endcut %}

1. Choose a version. The project parameters return to the chosen version.
1. Save the project to use the chosen project version as current.


## What's next {#what_next}

- [Create a task pool in the project](pool-main.md).


{% include [contact-support](../_includes/contact-support-help.md) %}
