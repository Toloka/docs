# Get information about a registered proxy server

To get information about all servers registered for a particular requester, log in as a requester and send an AJAX request from your browser console.

## Request {#request}

```json
$.ajax({
      url: '/api/new/requester/proxy/proxy',
      method: 'GET'
});
```

## Response {#response}

Contains a list and parameters of all servers registered for the requester, in JSON format.

