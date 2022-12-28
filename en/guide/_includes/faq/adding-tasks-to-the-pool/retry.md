{% cut "How do I set up a retry pool for my project?" %}

You can create a retry pool similarly to an exam pool. In the pool settings, select the type **Retry**. In the retry pool filters, specify the upper and lower values of the <main skill> that the Tolokers must get in order to be admitted to the retry pool.

For example, if the main pool admits users with a skill of 70 or higher, then you can route the people with a skill between 40 and 69 to the retry pool.

To get a valid “range”, enter the skill twice: with an upper and lower value. For example: `<basic skill > <70 and main skill >=40`.
We recommend that you don't make your exam and retry pools too lengthy, because Tolokers don't like to do zero-price tasks. 10–20 tasks is enough, depending on complexity.

{% endcut %}