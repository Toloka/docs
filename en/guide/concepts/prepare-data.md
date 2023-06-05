# Yandex Disk

{% include [yandex-disk-warning](../../_includes/yandex-disk-warning.md) %}

To use files from Yandex Disk in tasks:

1. [Add links to files to the task interface](#interface).

1. [Add links to files to the instructions](#instruction).

## Add files to the task interface {#interface}

To add a file to the [task interface](spec.md):

{% list tabs %}

- Template Builder

  1. Select the component type. For example, `"view.image"` — to insert a picture, `"view.audio"` — for audio files, `"view.video"` — for video files.

  1. In the `"url"` property, select the `"@toloka/helper.proxy"` type.

  1. In the `"path"` property, enter the structure `/<proxy name>/<file name>.<type>` with your data.

  [View an example with image classification](https://ya.cc/t/c2viz8T_4FAL9p)

  An example where files have been added from Yandex Disk in Template Builder:

  ```json
  {
  "type": "view.image",
  "url": {
    "type": "@toloka/helper.proxy",
    "path": "/my-proxy/example.jpg"
    }
  }
  ```

  You can also add links to files in the `/<proxy name>/<file name>.<type>` format to the input data and refer to them in the configuration.

  {% cut "Single image" %}

  ```json
  {
  "type": "view.image",
  "url": {
    "type": "@toloka/helper.proxy",
    "path": {
      "type": "data.input",
      "path": "image"
      }
    }
  }
  ```

  [View example in the sandbox](https://ya.cc/t/gnPtsSaq4FAZYa)

  {% endcut %}

  {% cut "Multiple images" %}

  {% note tip %}

  Don't forget that array elements start from zero.

  {% endnote %}

  ```json
  {
  "type": "view.image",
  "url": {
    "type": "@toloka/helper.proxy",
    "path": {
      "type": "data.input",
      "path": "images.0"
      }
    }
  }
  ```

  [View example in the sandbox](https://ya.cc/t/wB1pCU8D4FALz3)

  {% endcut %}

- HTML/JS/CSS interface editor

  1. Set the **string** data type for the [input data field](incoming.md) in which you will pass the file link.

  1. Insert the file. Note the format that specifies the field name: `proxy <field with the file link>`

      {% cut "Image" %}

      Add an image in the HTML block using one of the methods:

      - Using the [Picture](t-components/img.md) component: `{{img src=(proxy image)}}`.

      - Using an HTML tag: `<img src="not_var{{proxy image}}">`.

      {% endcut %}

      {% cut "Audio or video" %}

      Add the HTML tag:

      - To insert an audio recording in the player: `<audio src="not_var{{proxy audio}}" controls>`,

      - To embed a video recording in the player: `<video src="not_var{{proxy video}}" controls>`.

      {% endcut %}

      {% cut "Editor for image area selection" %}

      Add the [Image with area selection](t-components/image-annotation.md#adding_editor) component: `{{field type="image-annotation" name="result" src=(proxy image)}}`.

      {% endcut %}

  1. Provide relative links to Yandex Disk files in the [file with tasks](../../glossary.md#tsv) in the following format: `/<proxy name>/<folder name>/<filename>.<type>`. For example, `/my-proxy/example.jpg` or with the folder name — `/my-proxy/photos/example.jpg`.

      {% note info %}

      Note that the folder name is not always required. Sometimes it's enough to specify the proxy name and file name separated by a slash ("/").

      {% endnote %}

{% endlist %}

## Add files to the instructions {#instruction}

{% note warning %}

Set the access rights for the folder with instructions to “Public”.

{% endnote %}

To add an image to the [project instructions](instruction.md):

1. Upload files to the `Applications/Toloka/<folder name>` folder using the [web interface]({{ yadisk-client }}) or [Yandex Disk]({{ yadisk-app }}) app.

1. Select a method of adding the file to the instructions.

    {% list tabs %}

    - Visual editor

      1. In the **Instructions for Tolokers** field on the toolbar, click ![](../_images/img3.svg).

      1. Insert `/api/proxy/<proxy name>/<file name>.<type>` in the field that appears. For example: `/api/proxy/my-proxy/example.jpg`.

      1. Press **Enter**.

    - Use links

      1. On the toolbar, click ![](../_images/code.svg).

      1. Add the HTML tag `<img src="/api/proxy/proxy name/file name.type">` in the input field. For example: `<img src="/api/proxy/my-proxy/example.jpg">`.

    {% endlist %}

## Frequently asked questions {#faq}

{% cut "I am a new client. Can I connect Yandex Disk?" %}

Unfortunately, no. As Toloka no longer supports Yandex Disk integration for new users, you can't connect it. Please use one of the photo hosting services: [wampi]({{ wampi }}), [imgbb]({{ imgbb }}), [ImageShack]({{ imageshack }}), or [imgur]({{ imgur }}).

{% endcut %}

{% cut "I have a Yandex Disk integration, but want to manage the proxy. How can I do that?" %}

Please [contact our support team](../troubleshooting/support.md?form-topic1=other) for any actions with Yandex Disk proxy.

{% endcut %}

{% cut "I have a Yandex Disk integration, but want to disconnect it. How can I do that?" %}

Please [contact our support team](../troubleshooting/support.md?form-topic1=other) for any actions with Yandex Disk proxy.

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}