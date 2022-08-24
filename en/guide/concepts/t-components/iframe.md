# Iframe

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating an iframe in {% if locale == "en-com" %}[Template Builder](https://toloka.ai/en/docs/template-builder/reference/view.iframe){% endif %}.

{% endnote %}


To add an inline frame to a task, use the `{{iframe src=<object URL>}}` component. Example:

```no-highlight
{{iframe src=url width="100px" height="100px"}}
```

#### Parameters


Parameter
 |
Description
 |
Required
 |
Default value

----- | ----- | ----- | -----
``` src ``` | Page URL. | yes | no
``` width ``` | Width of the frame. Set in the following units:<br/><br/>- Pixels. For example, `width="100px"`.<br/>    <br/>- Percentage of the size of the parent element. For example, `width="100%"`.<br/>    <br/><br/>You can also use a formula for setting the width. For example, `width="calc(100%-30px)"`. | no | ``` "300px" ```
``` height ``` | Height of the frame in pixels. Set in the following units:<br/><br/>- Pixels. For example, `height="100px"`;<br/>    <br/>- Percentage of the size of the parent element. For example, `height="100%"`.<br/>    <br/><br/>You can also use a formula for setting the width. For example, `height="calc(100%-30px)"`. | no | ``` "500px" ```
``` content-width ``` | The width of the content in the frame, in pixels. For example, `content-width="700`".<br/><br/>To make the frame the width of the screen, set `content-width="false".` | no | ``` "1280" ```
``` zoom ``` | Button for increasing the frame to the size of the browser window.<br/><br/>- `zoom=true` — Increase frame to the browser window.<br/>- `zoom=false` — Keep the set size of frame. | no | ``` false ```
``` class ``` | CSS class for the frame. | no | ``` ".iframe" ```
``` sandbox ``` | Enables [sandbox](../../../glossary.md#sandbox-ru) mode, which restricts working in the frame.<br/><br/>To disable certain restrictions, you can use the following values (separate with spaces if combining them):<br/><br/>- `"allow-forms"` allows frame content to submit forms.<br/>    <br/>- `"allow-modules"` allows opening modal windows (for example, using an `alert`).<br/>    <br/>- `"allow-orientation-lock"` allows `lock` and `unlock` methods from the [Screen Orientation API](https://w3c.github.io/screen-orientation/).<br/>- `"allow-pointer-lock"` allows the [Pointer lock API](https://w3c.github.io/pointerlock/).<br/>- `"allow-popups"` allows popup windows (for example, using `window.open` or `target="_blank"`).<br/>- `"allow-popups-to-escape-sandbox"` allows pop-ups not to inherit sandbox mode (for example, so that in a popup window with JavaScript it is allowed without `"allow-scripts"` for a frame).<br/>- `"allow-presentation"` allows using the [Presentation API](https://w3c.github.io/presentation-api/).<br/>- `"allow-same-origin"`allows loading frame content (interprets this as content from the same source as the parent document). Blocks popup windows, so it can be used to open content safely.<br/>    <br/>- `"allow-scripts"` allows running and executing scripts. However, creating popup windows is prohibited.<br/>- `"allow-top-navigation"` allows opening frame links in the parent document.<br/>    <br/>- `"allow-top-navigation-by-user-activation"` allows opening a frame link clicked by the Toloker in the parent document.<br/>- `"false"` disables the restrictions listed. | no | ``` "allow-scripts allow-same-origin" ```

{% include [contact-support](../../_includes/contact-support-help.md) %}