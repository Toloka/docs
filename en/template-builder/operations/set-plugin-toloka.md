# Configuring task display

Use the `plugin.toloka` plugin to manage the settings for displaying tasks on the suite:
```json
{
  "type": "plugin.toloka",
  "layout": {
    "kind": "scroll",
    "taskWidth": 300
  }
}
```

Display methods are set in the `kind` property:

- `scroll` (default): Displaying multiple tasks on the suite at the same time.
- `pager`: Displaying only one task per suite, but with a button at the bottom to switch between tasks.

Use the `taskWidth` property to set up the task width. By default, the task is displayed in full-screen mode.


## Examples {#concept_gqw_zr5_wlb}

#### Arrange multiple tasks in a row

Let's say you want to display 2 tasks in each row on the screen. To do this, set the value of `taskWidth` so that 2 tasks fit in the screen for most performers. For example, specify the value of `500` to display 2 tasks on every screen larger than 1000 pixels wide. In the `kind` property, specify the `scroll` value.

[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBuAhgE4DOeyWG2OuIAnoVACYCmAHhVZrbXgC70ADqy54AFqwA2I4gDpSrEmHEBaAI4BXVsXp4AND151WUBHCiiUdRiw4GjvPFp17r1Y3xCCRYkM0J+QjkLIU1+BxpPPCFA8T8XXQB9fg4IkEdaAF9MrMMougQICAQpK0oPYwFhcrpJGR0FJWIVDW1dSOiQRLcKzKdvGr8AoJCoMPT8zxwYuIT2+hS0vH6sPNW8U3NLPyKSspWCnJp1mjx8OFYAdy5KmcHfa3PLq7kpOFJJzLw4VIBbcjWADaqzuVQetWe1zehAARtJWMxVO9Pp1png-hYAOpwZj8eLWAAMU3RIF+rABXBBBU8YOmdCkcOkfgAys0VFgesg0fT7pAoKkBbdVvTqo9KFDXn8SABrZgQK5QHm8vnQQXpPo0lV0HyQkD1WRyABWEAsyu1dHJlOBIu1eAAVPbzRbuFqXTqhk9-IFgqFws73bN8fNXEt2OlbSrTu6Bo7DjGsABdEmBkCw3p0eMu44WnO86O8umkxnwqR+ABKrHM0G5IBTvLw-PVwrdpN1fgu0NS4YDpKbpg1roTYr1BsaJrNdcjpKtgMo1ITOCLqfbXpGvvG-qnrYtQYJEu6CySxCrcGgSSghD+Vmn9ILw5AWAAFL2VcuXSPhj6xhNX3aQLEwZej0SSQJoAodBkO75vWqYAJRZu6ya3uC6Z+Ih2p5lG05YcYiarPetDvp+Xqdq8KJfK2eDMHAJ5gPwZ5Kl64gQMQcAAF5qoQZbbqKZL-HOWALoWKEkQeZFyIQ9GMaosLhPw0B-vcJbMl6ACaTBsOwWCKMoBKwaSUkMYp7gofcq4HkZjFyBAIhQMiFgykpXixPQUgQIQzAtg+AAkJ4wB2JCkHIthaRh2HQTguGeIRtKiRCHYvJJ0nQLJ8kmQZXQqTxB4AOLFKUrA6ey+nxVZJmaiunqWSlUA2XZDlQE5vEfgBhBuR5XmmZF4J+awAWkUFch7IV4X5ih0XGJNOD4VqsVDm21V0PA0jMHIxCeWeqgIMQECaEIvZ4NlfgAJKkFg+IfFghBYJAfzXi0cDccVemcgsz4noyqTMBdEBYHJ9AWAgWCscVUjvGYcEAPyHSAtnGVAgnCfS74DMdXoAMIQPdOhgE9PGZeCRBSNoXD8MQpPQfNvCo146MHgAcqld0PXj3HOec3Gk9YMDcYoOG2shVHekE3kNgla7fnt-C-i1fGAfudAs7j+NjVFhOc+8IyMWLfEWUr0A0Qj62sFotGIn+EgWIOeAACriFdfyaJ8-1FfA4OIlgk62pNuGzerRgxCT2xI5kRZ4AAjLr4L63g5V1YolF8eu0ddLHIvBNLsuE-cCt+Mrj3s1Bd4a21HWeWTFOiHNBl4AATKnXjp-HTRJ6SKfdSqYl0OuNnhNn057vn2Os6rxfTNTdCue5Fc83z1cxbXIA3J3i3inQLe2aYjXNaX0+dY3Ax9QN4lDaF9jjzFBFL4JxESzVxtb-ZEO77aszl11lXi8fgVkMNBUHEvlNa+Gx75T2DhYOQLF+AylYPQQEuR6zhzAUHTQ2w5AKXcjKQgzojrtWlofOgMoLCfzoKQMAu1wawyCKQGUOI8SKwAKyEkJARXIRhZpZDrGSTc-AUBoEDoeUM3YbZpk0PQLACIhDiCYG3ZwR4wIQQzHgcsztSBPTRPI0MJ5qxQAvFePUABVKQtgID4FoYcLhWQgA).

#### Show one task out of multiple tasks

You can show just one task out of multiple tasks and add a button for switching tasks at the bottom of the page. To do this, in the `kind` property, specify the `pager` value. If you omit the task width, the task is expanded to full screen.

[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IAOANgK4JxQDOeyWA2pjjhtozngAzVbOut4AuAT3wBTLngCGYfnGgA6CiP54ANA15sQAEwn8JXHhsYDhYlLm26JciMX747q9UYv5dAC3EgATiIrFCZRBnXgBfNRYNPDdBQggJLS8YCTgSXzwQnHDMiwBGAxzNIVEvKRl5RSCIlzwdPQLIoxMS81qrGzsHKsLjAg8vX39AjMbWbNHemLiE0pGNcaiQACYGmpBisxpJaVkoBSUnCc06-XNDNY2vE477RxBql1d+1p8-AKCehaa+2PjEl4ARnMwg8+OtTF4iKRyHJ3BB+ABrESCKjBRpfJg5ZqbVwkMh7fgQOII06g3qECSCWxBGjnXh4BHkf5bPoIETeQ4XCQUBEAdTgWn4nnMuXYYpyoRCkpYAF0HngAG5wEQAd1WvUuLwpVLsCgFIgAtADBAaKPrOb04PwRABbVE0egTOlgzUspWquRwG0SNkWxbEbyEdUXCEva7kLp+75uIVeL0+kQAfVOnzJYJgAUIAAkRIh3DSsPxvMQxBMMYxnRrQ27lSrPd7ffcengA0Gzj0itWLOGoJGm0dJs8WfG2YmgWiXOX05mc3mC0WSxKQnKQnhIFAi0T7dwseCWjWPYQ4BRuhM8FbbdvHS5Ky6u3h4CJCFo5N4ErIDQhvLZ8FHFhSASfLxeXcOAwHcLB8DhQksC0CAsB1LAjyRLBAJPAB+P96RACB8HKSguGvR5MQHf8JEAtsWQAQSwtYFQkEgcUkYFiKnIxb2+ACgJeAAhWjvnoxivHHDtGDYjQOLIiivAASQbPxYIFKAAHJ+CQv5+MWQTFxeZJUgDMxRKyUSV1I7srGDR5sSudpqT7NNoyHCxBneFijGlScHJI4jrN05Vnzka0AA89F8UlRLwLjKIsAAFQgRG5EQsBEIKiBSbAVXcXQENsJC4BQ8jqSwK05E08z6nbMzO33crrDsu4vOwmNhRZTLBDc+ZGs0QSBV0XZLJDGq12gLQrV2V8RAAR2IOBfH+LrelAjcvAAFVAigsBtYgT1QpL4EIeKtGKqAOrCT4chlKV1GlUJ7hACM7BQNB1HPeTky8fN7AoZAAHofpHPw5FEIKnwoORIBtH6oPhCAKB+3IAFYllyABmdgABYoZS0GDWhwkDUR5G0fRuQACtRAQC1XoTMcPv4L7fv++SweB0HwYgSG8dh+GkdR9gADYsZBwgKFx6CIAJ3m0f5smKZGW7QiAA).

[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
