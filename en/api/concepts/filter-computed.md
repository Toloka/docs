# Filter by computed data

You can use data received from or computed by Toloka to select Tolokers. For example, a device's technical characteristics or the type of client app.

Define the `filter` object in the pool parameters.

## Sample filter in JSON {#request-example}

This example selects Tolokers with the Windows OS and Yandex Browser.

```json
{
  "filter" : {
    "and" : [ {
      "operator" : "EQ",
      "category" : "computed",
      "key" : "os_family",
      "value" : "WINDOWS"
    }, {
      "operator" : "EQ",
      "category" : "computed",
      "key" : "user_agent_family",
      "value" : "YANDEX_BROWSER"
    } ]
  }
}
```

## Key and value parameters {#params}

#|
|| Key parameter | Value description ||
|| **region_by_phone** | **integer**

The Toloker's region detected from the mobile phone number (the [region ID in the search database](https://tech.yandex.com/xml/doc/dg/reference/regions-docpage/)).

Value of "operator":

- `IN` — The region is equal to the one specified or is a part of it.
- `NOT_IN` — The region is not equal to the one specified and is not a part of it.

Value of "value" if data couldn't be extracted — `null`. ||
|| **region_by_ip** | **integer**

The Toloker's region detected from the IP address (the [region ID in the search database](https://tech.yandex.com/xml/doc/dg/reference/regions-docpage/)).

Value of "operator":

- `IN` — The region is equal to the one specified or is a part of it.
- `NOT_IN` — The region is not equal to the one specified and is not a part of it.

Value of "value" if data couldn't be extracted — `null`. ||
|| **device_category** | **string**

Type of device:

- `PERSONAL_COMPUTER` — A personal computer.
- `SMARTPHONE` — A smartphone.
- `TABLET` — A tablet.

The complete list is available on the [UADetector library page](http://uadetector.sourceforge.net/modules/uadetector-core/apidocs/net/sf/uadetector/ReadableDeviceCategory.Category.html).

Value of "operator":

- `EQ` — Equal to.
- `NE` — Not equal to.

Value of "value" if data couldn't be extracted — `UNKNOWN`. ||
|| **client_type** | **string**

Type of client application:

- `BROWSER` — Web browser.
- `TOLOKA_APP` — Toloka mobile app.

Value of "operator":

- `EQ` — Equal to.
- `NE` — Not equal to.

Value of "value" if data couldn't be extracted — `UNKNOWN`. ||
|| **os_family** | **string**

The OS family, for example:

- `WINDOWS`
- `ANDROID`
- `IOS`
- `OS X`
- `LINUX`.

The complete list is available on the [UADetector library page](http://uadetector.sourceforge.net/modules/uadetector-core/apidocs/net/sf/uadetector/OperatingSystemFamily.html).

Value of "operator":

- `EQ` — Equal to.
- `NE` — Not equal to.

Value of "value" if data couldn't be extracted — `UNKNOWN`. ||
|| **user_agent_type** | **string**

Browser type:

- `BROWSER` — Desktop browser.
- `MOBILE_BROWSER` — Mobile browser.
- `OTHER` — Other.

The complete list is available on the [UADetector library page](http://uadetector.sourceforge.net/modules/uadetector-core/apidocs/net/sf/uadetector/UserAgentType.html).

Value of "operator":

- `EQ` — Equal to.
- `NE` — Not equal to.

Value of "value" if data couldn't be extracted — `UNKNOWN`. ||
|| **user_agent_family** | **string**

The browser family, for example:

- `IE`
- `IE_MOBILE`
- `YANDEX_BROWSER`
- `FIREFOX`
- `MOBILE_FIREFOX`
- `CHROME`
- `CHROME_MOBILE`
- `CHROMIUM`
- `SAFARI`
- `MOBILE_SAFARI`

The complete list is available on the [UADetector library page](http://uadetector.sourceforge.net/modules/uadetector-core/apidocs/net/sf/uadetector/UserAgentFamily.html).

Value of "operator":

- `EQ` — Equal to.
- `NE` — Not equal to.

Value of "value" if data couldn't be extracted — `UNKNOWN`. ||
|| **user_agent_version** | **float**

Full browser version: `<Major version>.<Minor version>.`

Value of "operator":

- `EQ` — Equal to.
- `NE` — Not equal to.
- `GT` — Greater than.
- `LT` — Less than.
- `GTE` — Greater than or equal to.
- `LTE` — Less than or equal to.

Value of "value" if data couldn't be extracted — `null`.||
|#