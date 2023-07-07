|
## Introduction

The Toloka API lets you create or delete projects, configure them as accurately as possible, and receive a list of these projects.

You can:

- Set up a [project](#tag--project) with a description of task settings (visual appearance, input fields, and so on).

- Create a [pool](#tag--pool) of tasks.

- Define the logic for selecting users who will complete the tasks.

- Import [data for tasks](#tag--task) (image URLs, text, and so on).

- [Receive and review](#tag--assignment) responses.

Requests are sent to the Toloka API over the HTTPS protocol. The service returns data in JSON format.

For debugging tasks, Toloka provides a testing environment — the sandbox. Once you have tested the settings, you can use the project and pool in the production version of Toloka (the only thing you need to change is the request URL and the OAuth token).

<aside class="note">If you use <a href="https://toloka.ai/pricing">bespoke solutions</a> and want to integrate your application with them or automate your requests, visit the <a href="https://toloka.ai/docs/api/apps-reference/">apps API documentation</a> to learn how you can do that.</aside>

## Accessing the API

Working with the Toloka API requires an OAuth access token. [Register](https://toloka.ai/docs/guide/access) in Toloka and get an OAuth token in the requester interface:

- In the sandbox for debugging tasks: [Profile → Integrations → Get OAuth token](https://sandbox.toloka.yandex.com/requester/profile/integration).

- In the production version of Toloka: [Profile → Integrations → Get OAuth token](https://platform.toloka.ai/requester/profile/integration).

![Get OAuth token](https://tlkfrontprod.azureedge.net/portal-production/static/uploaded/images/5f63afe572e474f714d22bfea90da628/5f63afe572e474f714d22bfea90da628_original_jpeg.jpeg)

Specify the received token in your requests as a part of the `Authorization` header, for example:

```bash
curl -X GET 'https://toloka.dev/api/v1/projects' \
     -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here'
```

## Filtering requests

Some `GET` methods allow you to filter the requests using special parameters. Such methods include most of the requests which return a list of items, for example, [`GET /projects`](#get-/projects), [`GET /pools`](#get-/pools), [`GET /tasks`](#get-/tasks), and other similar methods.

#### Example

```shell
curl -X GET 'https://toloka.dev/api/v1/projects?limit=100&overlap_gte=3' \
     -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here'
```

Parameter | Overview
:-------- | :-------
<span class="param-name">limit</span> <span class="key-type int">int64</span> | Limit on the number of results to return. By default — **50**; maximum — **300**.
<span class="param-name">id_gt</span> <span class="key-type stri">string</span> | Objects with an ID greater than the specified value.
<span class="param-name">id_gte</span> <span class="key-type stri">string</span> | Objects with an ID greater than or equal to the specified value.
<span class="param-name">id_lt</span> <span class="key-type stri">string</span> | Objects with an ID less than the specified value.
<span class="param-name">id_lte</span> <span class="key-type stri">string</span> | Objects with an ID less than or equal to the specified value.
<span class="param-name">overlap_gt</span> <span class="key-type stri">string</span> | Objects with an overlap greater than the specified value.
<span class="param-name">overlap_gte</span> <span class="key-type stri">string</span> | Objects with an overlap greater than or equal to the specified value.
<span class="param-name">overlap_lt</span> <span class="key-type stri">string</span> | Objects with an overlap less than the specified value.
<span class="param-name">overlap_lte</span> <span class="key-type stri">string</span> | Objects with an overlap less than or equal to the specified value.
<span class="param-name">task_id_gt</span> <span class="key-type stri">string</span> | Tasks with an ID greater than the specified value.
<span class="param-name">task_id_gte</span> <span class="key-type stri">string</span> | Tasks with an ID greater than or equal to the specified value.
<span class="param-name">task_id_lt</span> <span class="key-type stri">string</span> | Tasks with an ID less than the specified value.
<span class="param-name">task_id_lte</span> <span class="key-type stri">string</span> | Tasks with an ID less than or equal to the specified value.

### Parameters with a date

<aside class="note">The date is specified in UTC in the ISO 8601 format: <code>YYYY-MM-DDThh:mm:ss[.sss]</code>. The values must be URL-encoded, refer to the example below.</aside>

#### Example

```shell
curl -X GET 'https://toloka.dev/api/v1/projects?accepted_gt=2022-05-17T12%3A34%3A56&created_lte=2022-01-01T00%3A00%3A00' \
     -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here'
```

Parameter | Overview
:-------- | :-------
<span class="param-name">accepted_gt</span> <span class="key-type stri">string</span> | Objects accepted by the requester after the specified date.
<span class="param-name">accepted_gte</span> <span class="key-type stri">string</span> | Objects accepted by the requester after or on the specified date.
<span class="param-name">accepted_lt</span> <span class="key-type stri">string</span> | Objects accepted by the requester before the specified date.
<span class="param-name">accepted_lte</span> <span class="key-type stri">string</span> | Objects accepted by the requester before or on the specified date.
<span class="param-name">created_gt</span> <span class="key-type stri">string</span> | Objects issued or created after the specified date.
<span class="param-name">created_gte</span> <span class="key-type stri">string</span> | Objects issued or created on or after the specified date.
<span class="param-name">created_lt</span> <span class="key-type stri">string</span> | Objects issued or created before the specified date.
<span class="param-name">created_lte</span> <span class="key-type stri">string</span> | Objects issued or created on or before the specified date.
<span class="param-name">expired_gt</span> <span class="key-type stri">string</span> | Objects that expire after the specified date.
<span class="param-name">expired_gte</span> <span class="key-type stri">string</span> | Objects that expire after or on the specified date.
<span class="param-name">expired_lt</span> <span class="key-type stri">string</span> | Objects that expire before the specified date.
<span class="param-name">expired_lte</span> <span class="key-type stri">string</span> | Objects that expire before or on the specified date.
<span class="param-name">finished_gt</span> <span class="key-type stri">string</span> | Objects completed after the specified date.
<span class="param-name">finished_gte</span> <span class="key-type stri">string</span> | Objects completed after or on the specified date.
<span class="param-name">finished_lt</span> <span class="key-type stri">string</span> | Objects completed before the specified date.
<span class="param-name">finished_lte</span> <span class="key-type stri">string</span> | Objects completed on or before the specified date.
<span class="param-name">last_started_gt</span> <span class="key-type stri">string</span> | Objects that were last opened after the specified date.
<span class="param-name">last_started_gte</span> <span class="key-type stri">string</span> | Objects that were last opened on or after the specified date.
<span class="param-name">last_started_lt</span> <span class="key-type stri">string</span> | Objects that were last opened before the specified date.
<span class="param-name">last_started_lte</span> <span class="key-type stri">string</span> | Objects that were last opened on or before the specified date.
<span class="param-name">modified_gt</span> <span class="key-type stri">string</span> | Objects modified after the specified date.
<span class="param-name">modified_gte</span> <span class="key-type stri">string</span> | Objects modified on or after the specified date.
<span class="param-name">modified_lt</span> <span class="key-type stri">string</span> | Objects modified before the specified date.
<span class="param-name">modified_lte</span> <span class="key-type stri">string</span> | Objects modified on or before the specified date.
<span class="param-name">rejected_gt</span> <span class="key-type stri">string</span> | Objects rejected by the requester after the specified date.
<span class="param-name">rejected_gte</span> <span class="key-type stri">string</span> | Objects rejected by the requester after or on the specified date.
<span class="param-name">rejected_lt</span> <span class="key-type stri">string</span> | Objects rejected by the requester before the specified date.
<span class="param-name">rejected_lte</span> <span class="key-type stri">string</span> | Objects rejected by the requester before or on the specified date.
<span class="param-name">skipped_gt</span> <span class="key-type stri">string</span> | Objects skipped after the specified date.
<span class="param-name">skipped_gte</span> <span class="key-type stri">string</span> | Objects skipped after or on the specified date.
<span class="param-name">skipped_lt</span> <span class="key-type stri">string</span> | Objects skipped before the specified date.
<span class="param-name">skipped_lte</span> <span class="key-type stri">string</span> | Objects skipped before or on the specified date.
<span class="param-name">submitted_gt</span> <span class="key-type stri">string</span> | Objects issued or created after the specified date.
<span class="param-name">submitted_gte</span> <span class="key-type stri">string</span> | Objects issued or created on or after the specified date.
<span class="param-name">submitted_lt</span> <span class="key-type stri">string</span> | Objects issued or created before the specified date.
<span class="param-name">submitted_lte</span> <span class="key-type stri">string</span> | Objects issued or created on or before the specified date.

## Sorting responses

When you request a list of objects using the `GET` method, you can specify the parameters to sort the list by. Sorting is set in the request using the `sort` query parameter.

<aside class="note">Lists of objects support various sorting options. For more information about the parameters, see the <code>GET</code> request description for each object.</aside>

Toloka objects that can be sorted:

- [Projects](#get-/projects)
- [Pools](#get-/pools)
- [Trainings](#get-/trainings)
- [Subscriptions to events](#get-/webhook-subscriptions)
- [Skills](#get-/skills)
- [User skills](#get-/user-skills)
- [Task access bans](#get-/user-restrictions)
- [Tasks](#get-/tasks)
- [Task suites](#get-/task-suites)
- [Operations](#get-/operations)
- [Responses](#get-/assignments)
- [Files in responses](#get-/attachments)
- [Aggregated responses](#get-/aggregated-solutions/-operationId-)
- [Rewards](#get-/user-bonuses)
- [Threads of messages to users](#get-/message-threads)

#### Example

```shell
curl -X GET 'https://toloka.dev/api/v1/projects?sort=id,-created' \
     -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here'
```

### Sorting direction

You can sort values in the ascending or descending order.

For example, when using `sort=id`, the list is sorted by identifier values in ascending order. To change the sorting direction to descending, add a hyphen before the parameter: `sort=-id`.

### Sorting by multiple parameters

When sorting, you can use one or multiple parameters at once. Simply specify them separated by a comma: `param1,param2`.

<aside class="note">The order of parameters affects the sorting sequence.</aside>

For example, when using `sort=param1,param2`, the list is sorted in ascending order by the `param1` values first, and then by the `param2` values. To change the sorting sequence, switch the parameters around: `sort=param2,param1`.

## HTTP status codes

Any error returned by Toloka has an HTTP response status and response body with error details. Errors are self-documenting, that is, it should be clear from them what the cause is.

Sample error with HTTP status code `409`:

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

- `request_id`: Internal ID of the HTTP request where the error occurred. It needs to be specified when contacting support.

- `code`: String error code. Errors specific to different operations have the same codes. Different error codes can be used for the same HTTP status. Specific errors for specific operations have their own unique codes.

- `message`: Error details. The content of the field may be different for the same error code.

- `payload`: Additional information about the error. For example, a field from the request and the cause of the error in it. This field is optional and may be omitted.

### List of common status codes

The Toloka API uses the following HTTP status codes:

Status code | Message | Description
:---------- | :------ | :----------
<span class="status-code-2xx">2xx</span> | **Success** |
<span class="param-name">200</span> | OK | The request has succeeded. The result will be a returned JSON object or a link to download a file.
<span class="param-name">201</span> | Created | The request succeeded, and a new resource was created as a result. This is typically the response sent after `POST` requests when new objects are created.
<span class="param-name">202</span> | Accepted | The request has been received but not yet acted upon. This is typically the response sent after some `POST`, `PATCH`, or `PUT` requests when object properties are changed.
<span class="param-name">204</span> | No Content | The server has successfully fulfilled the request. There is no additional content to send in the response payload body. This is typically the response sent after `DELETE` requests.
<span class="status-code-4xx">4xx</span> | **Client errors** |
<span class="param-name">400</span> | Bad Request | The request could not be understood by the server due to malformed request syntax. The client should not repeat the request without modifications.
<span class="param-name">403</span> | Forbidden | The server understood the request, but is refusing to fulfill it. The request requires user authentication.
<span class="param-name">404</span> | Not Found | The requested resource was not found on the server.
<span class="param-name">405</span> | Method Not Allowed | The request method is known by the server but is not supported by the target resource.
<span class="param-name">409</span> | Conflict | The request couldn't be processed because of conflict in the current state of the resource. For example, you can't open a pool that is archived.
<span class="param-name">413</span> | Payload Too Large | The number of items in the request exceeds the allowed value.
<span class="param-name">415</span> | Unsupported Media Type | The media format of the requested data is not supported by the server, so the server is rejecting the request. Make sure you do not forget to add the `Content-Type: application/json` header to the `POST`, `PUT`, or `PATCH` request when needed.
<span class="param-name">429</span> | Too Many Requests | The allowed number of requests per time unit exceeded. Refer to the [Rate limiting](#overview--rate-limiting) section for more information about current Toloka API methods limitations.
<span class="status-code-5xx">5xx</span> | **Server errors** |
<span class="param-name">500</span> | Internal Server Error | The server encountered an unexpected condition which prevented it from fulfilling the request.
<span class="param-name">503</span> | Service Unavailable | The service is temporarily unavailable, you can repeat the request in a little while.

The above status codes are common for all requests.

## Rate limiting

Toloka applies the following rate limiting to the requests from clients to the Toloka API.

### Requests per second

Toloka limits the number of requests that clients can send per second. If you exceed **300** requests to the Toloka API per second, the platform will return an error with the `429 Too Many Requests` HTTP status code. If the problem persists, please lower the number of requests per second and try and repeat your requests in a couple of seconds.

### API methods request limiting

Some of the API methods have their own additional limitations for the methods that allow you to create or edit objects during a minute, hour, or day. Once you reach the limit, the platform will return an error with the `429 Too Many Requests` HTTP status code and the reason for the error in the response body.

Method | Minute | Hour | Day
:----- | :----- | :--- | :--
[Aggregate results](#tag--aggregated-solution) | **5** requests | **30** requests | **200** requests
[Assign skills](#put-/user-skills) | – | – | **100,000** requests
[Change overlap](#put-/pools/-id-) | – | **10** requests | –
[Clone pools](#post-/pools/-id-/clone) | **20** requests | – | **100** requests
[Clone training pools](#post-/trainings/-id-/clone) | **20** requests | – | **100** requests
[Create pools](#post-/pools) | **20** requests | – | **100** requests
[Create projects](#post-/projects) | **20** requests | – | **100** requests
[Create skills](#post-/skills) | **10** requests | – | **100** requests
[Create tasks](#post-/tasks) | **200,000** requests | – | **4,000,000** requests
[Create task suites](#post-/task-suites) | **100,000** requests | – | **2,000,000** requests
[Create training pools](#post-/trainings) | **20** requests | – | **100** requests
[Issue bonuses](#post-/user-bonuses) | – | – | **10,000** requests
[Message all Tolokers](#post-/message-threads/compose) | – | – | **1** message
[Message specific Tolokers](#post-/message-threads/compose) | – | – | **100,000** requests

### Input and output data size limitations

The table below shows the limitation for the size of the `input_values` and `output_values` fields when creating [tasks](#post-/tasks) or [task suites](#post-/task-suites).

Action | Limitation
:----- | :---------
Total size of all `input_values` fields | **1,048,576** bytes per request
Total size of all `output_values` fields | **4,194,304** bytes per request

### Additional actions limitations

The actions below don't have public API methods, but they affect the actions in the interface and also apply some limitations.

Action | Minute | Hour | Day
:----- | :----- | :--- | :--
Give access to account | – | – | **100** requests
Mass actions with users | – | – | **10,000** operations
Upload files | – | – | **1000** files
Uploaded file size | – | – | **5,242,880** KB
Size of files uploaded by Tolokers | – | – | **1,073,741,824** KB

<aside class="note">If you need to increase some of the above limits, please <a href="https://toloka.ai/docs/guide/troubleshooting/support/?form-source=openapi-rate-limiting">contact our support</a>.</aside>

## Using Toloka SDK

### Python library

Toloka allows you to use its open source [Toloka-Kit](https://toloka.ai/docs/toloka-kit) Python library which makes it easier to integrate the API into your own application written in the Python programming language.

To install Toloka-Kit library, use the following command:

```shell
$ pip install toloka-kit
```

After that, you need to import the library using the following code in your Python script:

```python
import toloka.client
```

Refer to the specific methods below to learn more about Toloka-Kit usage in your requests. The documentation provides Toloka-Kit examples for most of the methods.

Find more information about the Toloka-Kit Python library in [our documentation](https://toloka.ai/docs/toloka-kit/python-sdk).