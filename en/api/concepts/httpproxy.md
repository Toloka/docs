# Overview

You can set up your own server and access it with requests from Toloka tasks.

This is useful if:

- You need images or other files for your tasks, and you want to store them on your own server.
- You need to load dynamic data in the tasks.
- You want to log Toloker actions and so on.

The browser will block AJAX requests made from a Toloka task directly to your server. To get around this restriction, you need to [register](httpproxy-registration.md) your server in Toloka. Template requests will then be executed on the Toloka domain, and the system will redirect them to your server.

Limitations to consider when configuring the server:

#### Data type

If the type of data in the requester's server response is different from the one specified in the list, the response is converted to `text/plain`.

- `image/gif`
- `image/jpeg`
- `image/pjpeg`
- `image/png`
- `image/tiff`
- `audio`
- `application/octet-stream`
- `application/json`
- `text/plain`
- `video/mpeg`
- `video/mp4`
- `video/ogg`
- `video/webm`
- `video/x-flv`
- `video/3gpp`
- `video/3gpp2`

#### Headers

When proxying the requester's server responses, the following HTTP headers are ignored:

- `connection`
- `keep-alive`
- `transfer-encoding`
- `set-cookie`
- `content-type`

When proxying requests to the requester's server, the following HTTP headers are ignored:

- `cookie`
- `x-csrf-token`
- `authorization`
- `x-forwarded-for-y`
- `x-forwarded-for`
- `x-real-ip`

You can use the API to:

- [Register](httpproxy-registration.md) servers of requesters.
- [Get information](httpproxy-get-info.md) about all registered servers of a requester.
- [Update](httpproxy-edit.md) the data of a previously registered server.
- [Remove](httpproxy-delete.md) a server registration if you no longer need it.

{% include [contact-support](../../guide/_includes/contact-support.md) %}