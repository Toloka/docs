# Filter by computed data

You can use data received from or computed by Toloka to select Tolokers. For example, a device technical characteristics or the type of client app.

Define the `assignments_issuing_config.filter` object in the [pool parameters](https://toloka.ai/docs/api/api-reference/#tag--pool).

## Sample filter in JSON {#request-example}

This example selects Tolokers with the Windows OS and Chrome browser.

```json
{
  "filter": {
    "and": [
      {
        "operator": "EQ",
        "category": "computed",
        "key": "os_family",
        "value": "WINDOWS"
      },
      {
        "operator": "EQ",
        "category": "computed",
        "key": "user_agent_family",
        "value": "CHROME"
      }
    ]
  }
}
```

## Key and value parameters {#params}

#|
|| Key parameter | Value description ||
|| `region_by_phone` | _integer_

The Toloker's region detected from the mobile phone number (the [region ID in the search database](regions.md)).

Value of `operator`:

- `IN` — The region is equal to the one specified or is a part of it.
- `NOT_IN` — The region is not equal to the one specified and is not a part of it.

Value of `value` if data couldn't be extracted — `null`. ||
|| `region_by_ip` | _integer_

The Toloker's region detected from the IP address (the [region ID in the search database](regions.md)).

Value of `operator`:

- `IN` — The region is equal to the one specified or is a part of it.
- `NOT_IN` — The region is not equal to the one specified and is not a part of it.

Value of `value` if data couldn't be extracted — `null`. ||
|| `device_category` | _string_

Type of device:

- `PERSONAL_COMPUTER` — A personal computer.
- `SMARTPHONE` — A smartphone.
- `TABLET` — A tablet.

The complete list is available on the [UADetector library page](http://uadetector.sourceforge.net/modules/uadetector-core/apidocs/net/sf/uadetector/ReadableDeviceCategory.Category.html).

Value of `operator`:

- `EQ` — Equal to.
- `NE` — Not equal to.

Value of `value` if data couldn't be extracted — `UNKNOWN`. ||
|| `client_type` | _string_

Type of client application:

- `BROWSER` — A web browser.
- `TOLOKA_APP` — Toloka mobile app.

Value of `operator`:

- `EQ` — Equal to.
- `NE` — Not equal to.

Value of `value` if data couldn't be extracted — `UNKNOWN`. ||
|| `os_family` | _string_

The OS family, for example:

- `WINDOWS`: Microsoft Windows operating system developed and marketed by Microsoft for personal computers.
- `ANDROID`: Android mobile operating system based on a modified version of the Linux kernel, designed primarily for touchscreen mobile devices.
- `IOS`: iOS mobile operating system developed by Apple Inc. exclusively for its mobile devices.
- `OS_X`: macOS operating system developed by Apple Inc. since 2001 for Mac computers.
- `LINUX`: A family of open-source Unix-like operating systems based on the Linux kernel.

The complete list is available on the [UADetector library page](http://uadetector.sourceforge.net/modules/uadetector-core/apidocs/net/sf/uadetector/OperatingSystemFamily.html).

Value of `operator`:

- `EQ` — Equal to.
- `NE` — Not equal to.

Value of `value` if data couldn't be extracted — `UNKNOWN`. ||
|| `user_agent_type` | _string_

Browser type:

- `BROWSER` — Desktop browser.
- `MOBILE_BROWSER` — Mobile browser.
- `OTHER` — Other.

The complete list is available on the [UADetector library page](http://uadetector.sourceforge.net/modules/uadetector-core/apidocs/net/sf/uadetector/UserAgentType.html).

Value of `operator`:

- `EQ` — Equal to.
- `NE` — Not equal to.

Value of `value` if data couldn't be extracted — `UNKNOWN`. ||
|| `user_agent_family` | _string_

The browser family, for example:

- `CHROME`
- `CHROME_MOBILE`
- `CHROMIUM`
- `FIREFOX`
- `IE`
- `IE_MOBILE`
- `MOBILE_FIREFOX`
- `MOBILE_SAFARI`
- `SAFARI`
- `YANDEX_BROWSER`

The complete list is available on the [UADetector library page](http://uadetector.sourceforge.net/modules/uadetector-core/apidocs/net/sf/uadetector/UserAgentFamily.html).

Value of `operator`:

- `EQ` — Equal to.
- `NE` — Not equal to.

Value of `value` if data couldn't be extracted — `UNKNOWN`. ||
|| `user_agent_version` | _float_

Full browser version: `<Major version>.<Minor version>.`

Value of `operator`:

- `EQ` — Equal to.
- `NE` — Not equal to.
- `GT` — Greater than.
- `LT` — Less than.
- `GTE` — Greater than or equal to.
- `LTE` — Less than or equal to.

Value of `value` if data couldn't be extracted — `null`.||
|#

## See also {#see-also}

- [{#T}](../../guide/concepts/filters.md)
- [Toloka-Kit recipe: Filter Tolokers](../../toloka-kit/recipes/filter-tolokers.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}