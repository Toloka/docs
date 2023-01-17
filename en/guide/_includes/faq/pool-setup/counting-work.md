{% cut "How does counting work if I set `overlap = 3` in the pool and `response threshold = 3` in the majority vote?" %}

In this case, if you don't have 3 identical responses for your task (response threshold), no user would be considered a good or poor Toloker, because the system can't see which of the Tolokers made an error.

But if you set `response threshold = 2` with `overlap = 3`, then two users with the same responses are considered good Tolokers, but the third user, who gives a different response, is a poor Toloker.

{% endcut %}