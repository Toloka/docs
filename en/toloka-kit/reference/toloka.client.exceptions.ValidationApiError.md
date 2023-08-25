# ValidationApiError
`toloka.client.exceptions.ValidationApiError` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/exceptions.py#L92)

An exception for a field validation error returned by an API method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`request_id`|**Optional\[str\]**|<p>The ID of the request that returns an error.</p>
`code`|**Optional\[str\]**|<p>An error code.</p>
`message`|**Optional\[str\]**|<p>An error description.</p>
`payload`|**Optional\[Any\]**|<p>Additional data describing an error.</p>
`status_code`|**Optional\[int\]**|<p>A HTTP response status code.</p>
`invalid_fields`|**-**|<p>A list of invalid fields.</p>
