# Comparing video clips

This section describes how to [compare two videos](#video-side-by-side), how to make them [start and pause simultaneously](#same-time-video), and how to put [multiple videos on a page](#compare-more-video).

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

## Two videos side-by-side {#video-side-by-side}

To place two videos next to each other, you can use the [layout.side-by-side](../reference/layout.side-by-side.md) component. Add components with video ([view.video](../reference/view.video.md)) to the `items` property, and fields for responses to the `controls` property.

{% note info %}

Unlike other components, [layout.side-by-side](../reference/layout.side-by-side.md) has options allowing you to hide or display any of the elements in `items`.

{% endnote %}



[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm0A2AhgxAK50A6AM5wAJkQC0AIwYSR4vABpMNWnDpEAtkLYBtFasoHDtRizZ5CpAYXEQlxw3l4AndmyonVeM6xS1RTjpOATgoJn4Hai9aJiCACwsCMSIIAH0AQTxHVQBfZWinEBhednYACSJEeLo2OhdeVkKcfJyjZpofZj8KS2ISGxT7EAKY5zcPNu96bqTA4NDwyJGpzpA4ukT-Prs0gCFsjpbRrzwSssrq2v96xrbcxwBdE5w8SCh6iHYdf08i3yS8CI7FEAhcnFEcAgEgQLj4TCiJjwXCkwKSAHV4nAwPEsLZUlh4pwhFhNkQsKihHQsABHXicdjqBgAfkRRXmnEmR1Ms22IA5Aj4dAi1xeRQ2W16IDpDKZhxMrQ6eAgTDoUKgPwo+m5fzGIBRaL5ACUrmy9fgGXc+ZyQKtFTFdad9ZxUe4+QAZIgwUWrV4ES09WhSeVee1eR1I52upIAZU4mj8YsjFvYVqlUGgfjtbWebUssvm6q5eoBfPekLV0DBRDpcBcRFEZqKWI+SQAKliSZpeFSKeT4GUG1gwiG8o4HtQJ7kRiAwiKUGgDDtUpkkjVhUJkAB6LcDyREAAe8aY7CIQgkkE0AgQ6nivCkoQgW94J4gEKEW4ATAAGACMAHYt2-AAWXc4FPNJD2PCCAFkAAVgLSAA2YDvzSABmGCAHEBE0JhgLZZd0gOPl1yYTcdz3CQoLw09z0va9b3vR9n1fd8vz-AAOIDQL3SCj1oog0hggB5AA1ZDULSTjv2-ABrPZcIgfBDmnXIgA).


Instead of [layout.side-by-side](../reference/layout.side-by-side.md), you can use other components, for example:
- [view.list](../reference/view.list.md): A list of any elements, vertical or horizontal.
- [layout.columns](../reference/layout.columns.md): A set of horizontal columns that you can put the videos in. As opposed to [view.list](../reference/view.list.md), this component provides more options for column width setup.


## Parallel playback of two videos {#same-time-video}

You can sync playback and pause for both videos.

To do this, add a button ([view.action-button](../reference/view.action-button.md)) that will trigger the [action.play-pause](../reference/action.play-pause.md) action for both videos. To call two actions using one button (for each video), use the [action.bulk](../reference/action.bulk.md) component.


[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm0A2AhgxAK50A6AM5wAJkQC0AIwYSR4vABpMNWnDpEAtkLYBtFasoHDtRizZ5CpAYXEQlxw3l4AndmyonVeM6xS1RTjpOATgoJn4Hai9aJiCACwsCMSIIAH0AQTxHVQBfZWinEBhednYACSJEeLo2OhdeVkKcfJyjZpofZj8KS2ISGxT7EAKY5zcPNu96bqTA4NDwyJGpzpA4ukT-Prs0gCFsjpbRrzwSssrq2v96xrbcxwBdE5w8SCh6iHYdf08i3ySVgG7DgQmuLzW6i0Pwo+iO7Rirxm5m2xWI7FEAhcnFEcAgEgQLj4TCiiI4nCkRHcqIA6vE4GB4lhbKksPFOEIsJsiFhKWCsABHXicEGMAD8pMReHmnEm8OmANRMoEfDoEXBq2mGy2vRAQpF6gYhzJrXltAgTDoeKgMKwcLJOD+DvJlOpuoASldJc7LCK7qjZSBNTRTc6nQ68FxXUkADJEGAas3TfB+nq0KTGh2hh3hsmRilUpIAZU4mj8ELzBFTSSg0D8wZaweewd9IPm1rlPuRabe0FxVugWKIQrgLiIom9UpA9I+SQAKvTOZpePzKVh4GVx1gwpmYg94dmTLn-rNUUCBJwwAOoNJ+HRoJOTPno6ii-emAB6AAKXCNKzNeCXtenYRt2SRAdaAhSKUADWj6nOs3DsBAOJ6A2NDHpWiq6hBg5ML+EhxCu5bocm-Qgc60wACRjjAgL9KEGjaAIAAMu6UfulFYIeOakWs2G0LhUACPh3CEZwxHwZWQIUVxtA0fG9HWFCzEAIzsc6nEcehjzBlpJj6TQzYdNKo5EFeHaovEEAuHAABe0DBNSjhafuuQjCAYTqigaAGDsqSZEkNRqkIyAfh+G6SEQAAepb4UQQgSJAmgCAg6jxLwUihBAH68PhKGiEIH4AEwsapADsH4sQALBFcDsEQaQxXFDVpAAsl+1VpAAbNVLFpAAzG1ADiAiaEw1WSv56QHFZdAhWFdUNRIzXjQ1iXJal6WZdluX5TiRWlapAAcVW1ZFTWxWtjVtQA8gAaj1fVpMdLEsTBexjRA+CHO5uRAA).


You can also trigger playback using a hotkey. The button's shortcut will be shown on the button label.

Use [plugin.hotkeys](../reference/plugin.hotkeys.md) for this. To assign a shortcut to the button, do the same thing with the shortcut.

{% note tip %}

To call the same action from different parts of the code, put it in a separate variable inside `vars`. Then reference this variable using the `$ref` structure. For more information, see [Reuse code](../best-practices/reuse.md).

{% endnote %}


[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm0A2AhgxAK50A6AM5wAJkQC0AIwYSR4vABpMNWnDpEAtkLYBtFasoHDtRizZ5CpAYXEQlxw3l4AndmyonVeM6xS1RTjpOATgoJn4Hai9aJiCACwsCMSIIAH0AQTxHVQBfZWinEBhednYACSJEeLo2OhdeVkKcfJyjZpofZj8KS2ISGxT7EAKY5zcPNu96bqTA4NDwyJGpzpA4ukT-Prs0gCFsjpbRrzwSssrq2v96xrbcxwBdE5w8SCh6iHYdf08i3ySVgG7DgQmuLzW6i0Pwo+iO7Rirxm5m2xWI7FEAhcnFEcAgEgQLj4TCiiI4nCkRHcqIA6nAwPEsLZUlh4pwhFhNkQsJSwVgAI68TggxgAflJiLw804k3h0wBqOlAj4dAi4NW0w2W16IEFwvUDEOZNactoECYdDxUBhWDhZJwf3t5Mp1J1ACUrhKnZZhXdUTKQBqaCanY77XguC6kgAZIgwdWm6b4X09WhSI32kP2sNkiMUqlJADKnE0fghuYIKaSUGgfiDLSDzyDPpB8ytsu9yNTb2guMt0CxREFcBcRFEXslIHiYWuOoAKtOOZpeHzKVh4GUx1gwhmYg94VmTDn-rNUUCBJwwP2oNJ+HRoBOTHmo6jC-emAB6AAKXENK1NeCXteHbhiAAAko4wICnAuEIAhML+u5ePue5tE2HRSiORBXu2qLxBALhwAAXtAwTUo4KFYFmeAIbwCBhDado0MeXQojqtH0VAAj4XQADWRAMD85a0Dax5IhBcbQbB8GIYGHSUQ21DoUiyawSBSIIdw6lrAqOpAVaAhSKUvGPrE3DsBAOJ6KsYk6aeek4QOmmyHEK5ls2ySkNpYzgZBgL9KEGjaAIAAMSEmAphiHoYtlIrptD6U5v4SK5QjuQBnlkL89a0BJUFngFULBQAjOFUWrJFOCPBRBj7rkIwgGEaooGgBg7KkmRJDUqpCMgH4fhukhEAAHiWCFEEIEiQJoAj0ZsvBSKEEAfrwCGWaIQgfgATCFxUAOwfiFAAsA1wOwRBpCNY3nWkACyX5HWkABsR0hWkADMt0AOICJoTBHRK7XpAceF0D1fWnedEhXX952TdNs3qPEC1LSta04ptO3FQAHIdJ2DZdo2wxdt0APIAGrPa9aTYyFIW8Xsv0QPghz1bkQA).


## Compare multiple videos {#compare-more-video}

In the examples above, you can add as many video components as you like using the `items` property.


[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm0A2AhgxAK50A6AM5wAJkQC0AIwYSR4vABpMNWnDpEAtkLYBtFasoHDtRizZ5CpAYXEQlxw3l4AndmyonVeM6xS1RTjpOATgoJn4Hai9aJiCACwsCMSIIAH0AQTxHVQBfZWinEBhednYACSJEeLo2OhdeVkKcfJyjZpofZj8KS2ISGxT7EAKY5zcPNu96bqTA4NDwyJGpzpA4ukT-Prs0gCFsjpbRrzwSssrq2v96xrbWjs9TmfNt5OtbVKixkFd3fyeP18cyCITCEWuJx+Gy2vWSuwAwocYg8fucKlUEDU6g0miZco4ALpQ2iQKD1CDsHQAtpdV5w+BEdiiAQuTiiOAQCQIFx8JjfIpcKRMpIAdTgYHiWE+ECw8U4QiwmyIWGFQjoWAAjrxOOx1AwAPwC6bzTiTI6mWZvU0CPh0CHGoowpLa3X65GGVFFCBMOicqDUij6C2A55CkVvLIrC04Sy6u5vM0gVZekyhkx4cP-OEHaMxWMEeM9WhSD34kmqdOCzjC7O0JF5-Nx9gJuFgMueis0KvTLNJADKnE0fi703wRaSUGgfhTbWJtMLevm-vNQKtbegHL90FZRG1cBcRFEjum8TC1zhABUz4rNLx1aqVfAykesGEOy1HATqN-ciMQOC-AoGgBg7KkmRJDU9pCMgAD0sHPpIRAAB5Dkw7BEEIEiQJoAgIOo8S8FIoQQLBvDoRA7JCLBABMAAMACMADssF0QALAhcAYWkKFodxACyAAKbFpAAbGxdFpAAzPxADiAiaEwbECmB6S5nCUFMDB8GIRIvGKRhWE4XhBFESRZEUVRtGMQAHKxHGITxqEGUQaT8QA8gAamJElpDZdF0QA1nsCkQPgKnwuBDYaXQ0FwZxGF6c56GYdhEC4fhmxmZyFnsJRojUfR9GsVJCWufpKVpKKACiez8T5kkMWkbH8SFJBEFImiHH+uRAA).


If you want to add multiple videos that the user doesn't have to view at the same time, position them vertically using the [view.list](../reference/view.list.md) component. To make sure that the response selection buttons don't get lost, use the [layout.sidebar](../reference/layout.sidebar.md) component.


[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm0A2AhgxAK50A6AM5wAJkQBGnAE54ANJhq1IUOkVVsqSnHkYs2eQqQHs4QuvMXa8cNQFshbANpXtlV29p7WKWkZIChOIQltSetLzS7Joe4brMPhR4opx0nAJwUEz8oeFKeEypABYGBGJEEAD6AIJ4sdoAvgphnngwvOzsABJEiEUWvnTSvKwtSk31OFp58fq+hsQBQRW5MyCR0b7TeV4JpSlpGVk5IM07OiCFdCXzZcGVAEJ1Y41na+2dPX0DFEMjk1gJi8pgCLt5Sv5AuUQqdQREojFgdZ6Htbgd0plsgM3jsCsUIdDKgBhZ47IG4kAfbq9BD9Nh-UbhBr1AC6HnJNDwKiGEHYji29VmiVo8CI7FEAmknFEcAgAFoENI+ExVvkQFwJGLSgARCBYTidLDXIhCIhYZYQIRYIRFCAkLB8aRYJhcKBEOgAflVnJA6MRcRRcySvtS6T4dCx3rVVxuwYAjrwDbYGKTXoKQBAmHRZVB+RQXEjtq11ZxNZtgwBNE1R5H4A3-W4MasgAEctxFtx4DVa24AORhOOLdfYDeDUBhrdZg4uw7EqRz-uL4NuKhl2egkqICbg0iIohrFyKmR+tAAKkerXZeOYsJqsPBOnusJlU+N2YOudAeXyAOpia5sAATAADMBVjMlADSnCAmL8CgaBWAs9y1Lc-QRkIyAAPSYQ+RBykQAAenB2C6JpypAdgCAgthFLwEgZBAmG8C6EDSkImEgQAjAA7JhwEACw4XA7BEJUhHEaRlQALIAAr8ZUABs-HAZUADMUkAOICCR-GrEhFSPKUaFMBh2G4fhREkSJQjkRAlHUdcdEMUxLFsRxwGcQAHHxgm4WJlmSVJADyABqinKZUnmgQA1g82kQPgel3AZJKoXQ6FYUJIkWRJ1m2fZNFObKLnsKxojsSBIF8apWWieJVmiT+ACiDxSeFKmcZU-FSXFJCSHYzxQQ0QA).



[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
