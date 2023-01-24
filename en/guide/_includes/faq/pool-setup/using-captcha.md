{% cut "Can I get more details on the best practices for using captchas? For which projects is it better to use captchas and how often?" %}

[Captcha](../../../../guide/concepts/captcha.md) is usually used in simple projects with automatic acceptance, like classification, categorization, or information search. These are cases where there are few response options and Tolokers don't need to upload files or write texts. It helps you filter out bots and sloppy Tolokers.

The frequency of issuing captchas is configured in the pool.

No

: Don't show captchas.

Low

: Show a captcha after every 20 assignments.

Average/High

: Show a captcha after every 10 assignments.

{% endcut %}