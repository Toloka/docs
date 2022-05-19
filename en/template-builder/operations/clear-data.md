# Clearing the entered values

Sometimes, you need to clear a value that the user entered by mistake. You might need it when you have multiple "branches" of questions, each having multiple response options. The user might first give answers triggering one branch, and then change their mind and give another answer.

To clear the entered values, use the [action.set](../reference/action.set.md) action and the `{ "$empty": true }` structure. You can call this action using a [button](../reference/view.action-button.md) or [trigger](../reference/plugin.trigger.md).

## Example {#section_t1s_fgt_xmb}

Let's say you ask a user whether they prefer cats or dogs. Then you ask them to select their favorite breed, and this field is mandatory.

It's possible that after selecting a breed, the user changes their choice of animal, and you get this response: animal — cat, breed — dachshund.

[View an example with an error in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNnnhFuAE04AnAIa64EALQIDEAK5NhKpXm5GARjs0gA6gAsIWXX8GWyxuCHwiLCkIAyIAfgdqVTwIJjozKFkULAUk1WU8-NoXd25PAGEjOiyRQvy8fCNuG1ZsvDAqrMdVAF9aopwqAZpnNw82kAARCAQa7vqCJpbPQNm8ebEejawAXX6F3SqjNiGBvHVWijxDuiNOWzomG0EQfaK8JiqfTyMoOCkmus6jg+tsGk04DcMidtjhzsxLrRIFBTOloIYiABHGxwWK6RLDPA+OBQF5XEAAFWJfCiNgEWHcWHg3G4RF0WBJQKKWzqoLqp2S9ARnh8OhYBk4fBIEjA31eYPARj4RCyFFywwFZ3A0FR0OymsJQo0E2RuvRWJsTTmwIORxhNveRsR1yO92eTxeb2GIxAnzocvJv3+gJAsKUfO9ProEE8HWqXO9Ee9eFifBs3DJBUjcKdnm0ekMJjMlmsdgJ2dGpU8viqHJpwRsBiZRnwtgMEkirlibIS8odThAqTRmXkYdUBorIBK43JAFkjCTIpBoOXsz7Gs1nSAAYuAPrLqAJtdJtcTyOVme0ADKcCMUlXa-YSy3fFv99D-d6XsjZ+TU7GZQTAAQkQUAICG36ThuywTO4YEhmO4aQRqiGCtOgHkgA8v6RAGA+a7gpungQDheEfo+WA8mueyobQNzHPqtE5hcKyug8Hr4X+foBrQXZEGyR6JshCwbpCVR6hQv6OixJo6hIGQYtiuICeR2ZUYmYYnvkUk+qa8kroxn5RsKskovpUCcBaVqcY69H2hR8LGuS9Fuo8zw2Vq3E-H8AKAbRWmGtGKwzF0RkBQsqbppmOliI5W75voximBYVi2PYfYEf+VYTDWdB1lgDZNjALZth2DLdrovbCYKQ4ZKqORMVmFHFABnhXqKTCigY+IZc1hEweSfAdV1PWNeFKFGWhrUTJMRiykNNgoh5hrQVuhzzT4i2jZNNDjQMMULOhnhAemegzMtWqrZ4rinasgmRntRQHVN2VYaRF2OldEwkV190aTtNE7S6tz2Y+cWsbcrkcb1mVebBFV-dy1UDqJUIGZJjXg6ZZoWbESl4oj+TqcMxNE9sOzzKTFPUDyPSvCAJIeigaB0z0QA).

To fix this, add the code to clear the `breed` data when the `animal` choice changes:

```json
"plugins": [
  {
    "type": "plugin.trigger",
    "onChangeOf": {
      "type": "data.output",
      "path": "animal"
    },
    "action": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "breed"
      },
      "payload": {
        "$empty": true
      }
    }
  }
]
```

[See the updated example with clearing by trigger](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNnnhFuAE04AnAIa64EALQIDEAK5NhKpXm5GARjs0gA6gAsIWXX8GWyxuCHwiLCkIAyIAfgdqVTwIJjozKFkULAUk1WU8-NoXd25PAGEjOiyRQvy8fCNuG1ZsvDAqrMdVAF9aopwqAZpnNw82kAARCAQa7vqCJpbPQNm8ebEejawAXX6F3SqjNiGBvHVWijxDuiNOWzomG0EQfaK8JiqfTyMoOCkmus6jg+tsGk04DcMidtjhzsxLrRIFBTOloIYiABHGxwWK6RLDPA+OBQF5XEAAFWJfCiNgEWHcWHg3G4RF0WBJQKKWzqoLqp2S9ARnh8OhYBk4fBIEjA31eYPARj4RCyFFywwFZ3A0FR0OymsJQo0E2RuvRWJsTTmwIORxhNveRsR1yO92eTxeb2GIxAnzocvJv3+gJAsKUfO9ProEE8HWqXO9Ee9eFifBs3DJBUjcKdnm0ekMJjMlmsdgJ2dGpU8viqHJpwRsBiZRnwtgMEkirlibIS8odThAqTRmXkYdUBorIBK43JAFkjCTIpBoOXsz7Gs1nSAAYuAPrLqAJtdJtcTyOVme0ADKcCMUlXa-YSy3fFv99D-d6XsjZ+TU7GZQTAAQkQUAICG36ThuywTO4YEhmO4aQRqiGCtOgHkgA8v6RAGA+a7gpungQDheEfo+WA8mueyobQNzHPqtE5hcKyug8Hr4X+foBrQXZEGyR6JshCwbpCVR6hQv6OixJo6hIGQYtiuICeR2ZUYmYYnvkUk+qa8kroxn5RsKskovpUCcBaVqcY69H2hR8LGuS9Fuo8zw2Vq3E-H8AKAbRWmGtGKwzF0RkBQsqbppmOliI5W75voximBYVi2PYfYEf+VYTDWdB1lgDZNjALZth2DLdrovbCYKQ4ZKqORMVmFHFABnhXqKTCigY+IZc1hEweSfAdV1PWNeFKFGWhrUTJMRiykNNgoh5hrQVuhzzT4i2jZNNDjQMMULOhnhAemegzMtWqrZ4rinasgmRntRQHVN2VYaRF2OldEwkV190aTtNE7S6tz2Y+cWsbcrkcb1mVebBFV-dy1UDqJUIGZJjXg6ZZoWbESl4oj+TqcMxNE9sOzzKTFPUEmHzNAgJL1eqNATlj5JMPTJKcHQ7YIAguGcSkUDlD4vz85hMCg4KMnOWx7ruTDA5w4GPkIbykF4HNw5SwOMu0FrCnKp6Cp2YZgUmbLkPsQryMfF810I6pX4Kp8DBhCYOuCgAJNIaQMGwPPLDapMgo46nUz0rwgCSHooGgkc9EAA).


[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
