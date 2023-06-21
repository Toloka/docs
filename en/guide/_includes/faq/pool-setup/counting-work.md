{% cut "How does counting work if I set `overlap = 3` in the pool and `task response threshold = 3` in the majority vote?" %}

In this case, if you don't have 3 identical task responses for your task (task response threshold), no Toloker would be considered a good or poor Toloker, because the system can't see which of the Tolokers made an error.

But if you set `task response threshold = 2` with `overlap = 3`, then two Tolokers with the same task responses are considered good Tolokers, but the third user, who gives a different task response, is a poor Toloker.

{% endcut %}