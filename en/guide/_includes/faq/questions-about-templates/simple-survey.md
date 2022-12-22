{% cut "How do I create a simple survey with no options, where the Toloker answers an open-ended question?" %}

1. Create a project from an empty preset.

1. Write your question in the HTML block.

1. If you need an [extensive](../concepts/t-components/text.md) response, add the required number of text entry components.

1. If you need a [short](../concepts/t-components/string.md) response, add the required number of string entry components.

1. Come up with a name for each of the components and create a matching number of string-type output fields with the same names. They will be used to save responses.

1. Make all the output fields mandatory.

1. Make the input field auxiliary. It will only be used to create a file with tasks.

1. Come up with a name for the input field and set the string type for it (see the step-by-step [guide on creating a survey](../tutorials/questionnaire-toloka.md)).

{% endcut %}