# Edit proxy server data

To edit the server data, log in as a requester and send an AJAX request from your browser console.

## Request {#request}

```json
$.ajax({
      url: '/api/new/requester/proxy/proxy/{id}',
      method: 'PATCH',
      contentType: 'application/json',
      data: JSON.stringify({
        "params": {
          "accessRights": "ASSIGNMENT_PRIVATE",
          "type": "HTTP",
          "additionalHeaders": {},
          "additionalQueryArgs": {},
          "baseUrl": "example.com/some-path"
        },
        "name": "test-proxy"
     )
});
```

#| 
|| Parameter | Overview ||
|| **id** | **string \| required**

The requester's server ID. ||
|| **accessRights** | **string \| required**

Level of access to files hosted on the requester's server. Acceptable values:

- ASSIGNMENT_PRIVATE — Access is only granted to the Tolokers whose tasks contain a server link. Suitable for task content.
    
    #### Example
    
    The following is called in Toloka: `toloka.yandex.com/api/proxy/test-proxy/test-path`.
    
    If the task contains an input field with the URL or String type and its value is:
    - `proxy/test-proxy/example-id`,
    
    - `test-proxy/example-id`,
    
    - `example-id`,
    
    the request will be proxied to the requester's server.
    
    If the task does not have a field with one of these values, no request proxying is done.
    
- PRIVATE — Access is only granted to Tolokers who are doing tasks for this requester (server owner). The task itself is not checked for a link to the server. Appropriate for general actions in tasks.
    
- PUBLIC — Access is granted to all Toloka Tolokers. Appropriate for files with instructions. ||
|| **type** | **string \| required**

Data transfer protocol. Possible value: `HTTP`. ||
|| **baseUrl** | **string \| required**

The requester's server URL.

For example, a server [named](#name) "test-proxy" is hosted at `example.com/some-path`.

In this case, when calling an HTTP method in Toloka at the URL `toloka.yandex.com/api/proxy/test-proxy/test-path`, a request to the requester's server will be sent to the URL `example.com/some-path/test-path`.

If a method call is made within a template, [assignmentId](#assignmentId) will be added to the URL. This ensures that information about the task the request was made within is also passed to the requester's server. Example: `example.com/some-path/test-path?assignmentId=12831298712937213`. ||
|| **name** {#name} | **string \| required**

The name of the requester's server. The name will be inserted in the request URL. Allowed characters in the name: Latin letters, numbers, and dashes ("-").

Must be unique within Toloka.

For example, a server named "test-proxy" can be accessed in Toloka at: `toloka.yandex.com/api/proxy/test-proxy`. ||
|| **additionalHeaders[]** | **array of strings**

Additional headers that will be passed in the request to the requester's server. Example:``` "additionalHeaders":{"Authorization":["Basic
       --//--TOKEN--//--"]} ``` ||
|| **additionalQueryArgs[]** | **array of strings**

Additional parameters that will be passed in the request to the requester's server. Example:
``` "additionalQueryArgs":{"test-arg":["12345"]} ```
||
|#

## Response {#response}

Contains server parameters (both updated and not) in JSON format.

