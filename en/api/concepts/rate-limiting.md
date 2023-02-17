# Rate limiting

Toloka applies the following rate limiting to the requests from clients to the Toloka API.

## Requests per second

Toloka limits the number of requests that clients can send per second. If you exceed **300** requests to the Toloka API per second, the platform will return an error with the `429 Too Many Requests` HTTP status code. If the problem persists, please lower the number of requests per second or [contact our support team](../../guide/troubleshooting/support.md) in case you really need to send more than 300 requests per second.

## API methods request limiting

Some of the API methods have their own additional limitations for the methods that allow you to create or edit objects during a minute, hour, or day. Once you reach the limit, the platform will return an error with the `429 Too Many Requests` HTTP status code and the reason for the error in the response body.

Method | Minute | Hour | Day
------ | ------ | ---- | ---
[Aggregate results](aggregated-solutions.md) | 5 | 30 | 200
[Assign skills](set-skill.md) | – | – | 100,000
[Change overlap](edit-pool.md) | – | 10 | –
[Clone pools](clone-pool.md) | 20 | – | 100
[Clone training pools](clone-training.md) | 20 | – | 100
[Create pools](create-pool.md) | 20 | – | 100
[Create projects](create-prj.md) | 20 | – | 100
[Create skills](create-skill.md) | 10 | – | 100
[Create tasks](create-task.md) | 200,000 | – | 4,000,000
[Create task suites](create-task-suite.md) | 100,000 | – | 2,000,000
[Create training pools](create-training.md) | 20 | – | 100
[Issue rewards](create-bonus.md) | – | – | 10,000
[Message all Tolokers](message-send.md) | – | – | 1 message
[Message specific Tolokers](message-send.md) | – | – | 100,000

## Additional actions limitations

The actions below don't have public API methods, but they affect the actions in the interface and also apply some limitations.

Action | Minute | Hour | Day
------ | ------ | ---- | ---
Give access to account | – | – | 100
Mass actions with users | – | – | 10,000 operations
Upload files | – | – | 1000 files
Uploaded file size | – | – | 5,242,880 KB
Size of files uploaded by Tolokers | – | – | 1,073,741,824 KB

{% note info %}

If you need to increase some of the above limits, please [contact our support](../../guide/troubleshooting/support.md).

{% endnote %}