|
## Introduction

If you need to quickly solve a problem and you do not want to spend time on preparing a project, you can use Toloka [bespoke solutions](https://toloka.ai/pricing), which were specifically developed to ease the work with the platform.

Select the problem to solve and fill out an [application form](https://toloka.ai/talk-to-us/) for creating a project: the Toloka CSA team will configure the project for you, create a task interface, and the platform will find Tolokers. All you have to do is prepare and upload your data, run the project, and get the labeling results.

In Toloka, bespoke solutions have the apps API technology under the hood. That's why anyone who uses bespoke solutions and wants to integrate them into their own application needs to deal with the [apps](#tag--app), [app-projects](#tag--app-project), [items](#tag--item), and [batches](#tag--batch).

<aside class="note">If you are looking for Toloka API and want to integrate your application or automate your requests without bespoke solutions, please refer to the <a href="https://toloka.ai/docs/api/api-reference/">documentation here</a>.</aside>

## Accessing the API

Working with the apps API requires an OAuth access token. [Register](https://toloka.ai/docs/guide/access) in Toloka and get an OAuth token in the requester interface:

- In the sandbox for debugging tasks: [Profile → Integrations → Get OAuth token](https://sandbox.toloka.yandex.com/requester/profile/integration).

- In the production version of Toloka: [Profile → Integrations → Get OAuth token](https://platform.toloka.ai/requester/profile/integration).

![Get OAuth token](https://tlkfrontprod.azureedge.net/portal-production/static/uploaded/images/5f63afe572e474f714d22bfea90da628/5f63afe572e474f714d22bfea90da628_original_jpeg.jpeg)

Specify the received token in your requests as a part of the `Authorization` header, for example:

```bash
curl -X GET 'https://toloka.dev/api/app/v0/apps' \
     -H 'Authorization: OAuth AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE'
```

## Filtering requests

Some `GET` methods allow you to filter the requests using special parameters. Such methods include most of the requests which return a list of items, for example, [`GET /apps`](#get-/apps), [`GET /app-projects`](#get-/app-projects), and other similar methods.

#### Example

```shell
curl -X GET 'https://toloka.dev/api/app/v0/apps?limit=100' \
     -H 'Authorization: OAuth AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE'
```

Parameter | Overview
:-------- | :-------
<span class="param-name">limit</span> <span class="key-type int">integer</span> | Limit on the number of results to return. By default — **50**; maximum — **300**.
<span class="param-name">id_gt</span> <span class="key-type stri">string</span> | Objects with an ID greater than the specified value.
<span class="param-name">id_gte</span> <span class="key-type stri">string</span> | Objects with an ID greater than or equal to the specified value.
<span class="param-name">id_lt</span> <span class="key-type stri">string</span> | Objects with an ID less than the specified value.
<span class="param-name">id_lte</span> <span class="key-type stri">string</span> | Objects with an ID less than or equal to the specified value.
<span class="param-name">name_gt</span> <span class="key-type stri">string</span> | Objects with a name lexicographically greater than the specified value.
<span class="param-name">name_gte</span> <span class="key-type stri">string</span> | Objects with a name lexicographically greater than or equal to the specified value.
<span class="param-name">name_lt</span> <span class="key-type stri">string</span> | Objects with a name lexicographically less than the specified value.
<span class="param-name">name_lte</span> <span class="key-type stri">string</span> | Objects with a name lexicographically less than or equal to the specified value.

### Parameters with a date

<aside class="note">The date is specified in UTC in the ISO 8601 format: <code>YYYY-MM-DDThh:mm:ss[.sss]</code>. The values must be URL-encoded, refer to the example below.</aside>

#### Example

```shell
curl -X GET 'https://toloka.dev/api/app/v0/app-projects?created_lte=2022-01-01T00%3A00%3A00' \
     -H 'Authorization: OAuth AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE'
```

Parameter | Overview
:-------- | :-------
<span class="param-name">created_gt</span> <span class="key-type stri">string</span> | Objects issued or created after the specified date.
<span class="param-name">created_gte</span> <span class="key-type stri">string</span> | Objects issued or created on or after the specified date.
<span class="param-name">created_lt</span> <span class="key-type stri">string</span> | Objects issued or created before the specified date.
<span class="param-name">created_lte</span> <span class="key-type stri">string</span> | Objects issued or created on or before the specified date.
<span class="param-name">finished_gt</span> <span class="key-type stri">string</span> | Objects completed after the specified date.
<span class="param-name">finished_gte</span> <span class="key-type stri">string</span> | Objects completed after or on the specified date.
<span class="param-name">finished_lt</span> <span class="key-type stri">string</span> | Objects completed before the specified date.
<span class="param-name">finished_lte</span> <span class="key-type stri">string</span> | Objects completed on or before the specified date.

## Sorting responses

When you request a list of objects using the `GET` method, you can specify the parameters to sort the list by. Sorting is set in the request using the `sort` query parameter.

<aside class="note">Lists of objects support various sorting options. For more information about the parameters, see the <code>GET</code> request description for each object.</aside>

Toloka objects that can be sorted:

- [App projects](#get-/app-projects)
- [Apps](#get-/apps)
- [Items](#get-/app-projects/-app_project_id-/items)
- [Batches](#get-/app-projects/-app_project_id-/batches)

#### Example

```shell
curl -X GET 'https://toloka.dev/api/app/v0/app-projects?sort=id,-created' \
     -H 'Authorization: OAuth AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE'
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
<span class="param-name">429</span> | Too Many Requests | The allowed number of requests per time unit exceeded.
<span class="status-code-5xx">5xx</span> | **Server errors** |
<span class="param-name">500</span> | Internal Server Error | The server encountered an unexpected condition which prevented it from fulfilling the request.
<span class="param-name">503</span> | Service Unavailable | The service is temporarily unavailable, you can repeat the request in a little while.

The above status codes are common for all requests.

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