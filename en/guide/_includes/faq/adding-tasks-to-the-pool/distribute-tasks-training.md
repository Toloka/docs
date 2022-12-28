{% cut "Why is only Smart Mixing available in Training?" %}

This is a technical limitation of [training pools](../../../../glossary.md#training-pool). If you want to use the {% if locale == "en-com" %}**Set manually**{% endif %} option in the training, create the main pool, set the pool type as {% if locale == "en-com" %}**Training**{% endif %}, and set the cost to zero.

{% endcut %}