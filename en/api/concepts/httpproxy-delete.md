# Remove a proxy server registration

To delete a registered requester server, log in as a requester and send an AJAX request from your browser console.

## Request {#request}

```json
$.ajax({
      url: '/api/new/requester/proxy/proxy/{id}',
      method: 'DELETE'
});
```

## Response {#response}

If the request is successful, the server returns the "204 No Content" or "404 Not Found" HTTP operation status.

