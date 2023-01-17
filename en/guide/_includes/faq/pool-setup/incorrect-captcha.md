{% cut "I set up a rule to ban users after the first incorrect captcha. This is to eliminate any bots. Is this too strict? What rule do most projects use?" %}

Indeed, this rule is probably too strict. Even the most careful user can make a mistake, so you probably want to relax the rule. Besides the requester-specific bans, we have system processes that ban users who regularly fail captcha checks in Toloka.

{% endcut %}