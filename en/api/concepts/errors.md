# Handling errors

Any error returned by Toloka has an HTTP response status and response body with error details. Errors are self-documenting, that is, it should be clear from them what the cause is.

Sample error with HTTP status code 409:

```json
{
  "request_id": "337d68d1-974d-42b1-a2d0-6234f6373eed",
  "code": "INAPPROPRIATE_STATUS",
  "message": "This or related resource is in inappropriate status, operation is not allowed",
  "payload": {
    "appropriate_statuses": [
      "OPEN",
      "CLOSED"
    ]
  }
}
```

Each error text has the following fields:

- **request_id**: Internal ID of the HTTP request where the error occurred. It needs to be specified when contacting support.
- **code**: String error code. Errors specific to different operations have the same codes. Different error codes can be used for the same HTTP status. Specific errors for specific operations have their own unique codes.
- **message**: Error details. The content of the field may be different for the same error code.
- **payload**: Additional information about the error. For example, a field from the request and the cause of the error in it. This field is optional and may be omitted.

## List of common errors {#common-errors}

The following HTTP status codes describe error classes, with examples of common errors.

#### 400: Error in the data that is passed in the request.

```json
{
  "code": "VALIDATION_ERROR",
  "message": "Validation failed",
}
```

#### 403: No permission to perform the operation.

```json
{
  "code": "ACCESS_DENIED",
  "message": "Access denied"
}
```

#### 404: The requested object doesn't exist.

```json
{
  "code": "DOES_NOT_EXIST",
  "message": "There are no results for such parameters"
}
```

#### 409: The operation can't be performed due to its logic. For example, you can't open a pool that is archived.

```json
{
  "code": "CONFLICT_STATE",
  "message": "Conflict state"
}
```

#### 429: The allowed number of requests per time unit exceeded.

```json
{
  "code": "TOO_MANY_REQUESTS",
  "message": "Too many requests"
}
```

#### 500: An unexpected error in the service. To fix it, [contact support](https://toloka.ai/docs/guide/troubleshooting/support.html#troubleshooting__help) and specify the request_id.

```json
{
  "code": "INTERNAL_ERROR",
  "message": "Internal Error"
}
```

#### 503: The service is temporarily unavailable, you can repeat the request in a little while.

```json
{
  "code": "REMOTE_SERVICE_UNAVAILABLE",
  "message": "Service is temporary unavailable"
}
```