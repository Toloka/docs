# Attributes
`toloka.client.user.User.Attributes` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/user.py#L24)

```python
Attributes(
    self,
    *,
    country_by_phone: Optional[str] = None,
    country_by_ip: Optional[str] = None,
    client_type: Optional[str] = None,
    user_agent_type: Optional[str] = None,
    device_category: Optional[str] = None,
    os_family: Optional[str] = None,
    os_version: Optional[float] = None,
    os_version_major: Optional[int] = None,
    os_version_minor: Optional[int] = None,
    os_version_bugfix: Optional[int] = None
)
```

Information obtained from the Toloker's device.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`country_by_phone`|**Optional\[str\]**|<p>The country determined based on the phone number.</p>
`country_by_ip`|**Optional\[str\]**|<p>The country determined based on the IP address.</p>
`client_type`|**Optional\[str\]**|<p>The client which the Toloker uses to access the platform:</p> <ul> <li>`TOLOKA_APP` — A mobile application.</li> <li>`BROWSER` — A browser.</li> </ul>
`user_agent_type`|**Optional\[str\]**|<p>The user agent type which the client application uses to identify itself:</p> <ul> <li>`BROWSER` — The desktop browser user agent.</li> <li>`MOBILE_BROWSER` — The mobile browser user agent.</li> <li>`OTHER` — User agents which could not be identified as either desktop or mobile browsers.   Normally, the Toloka mobile application identifies itself as `OTHER`.</li> </ul>
`device_category`|**Optional\[str\]**|<p>The category of the device:</p> <ul> <li>`PERSONAL_COMPUTER` — A personal computer.</li> <li>`SMARTPHONE` — A smartphone.</li> <li>`TABLET` — A tablet device.</li> <li>`WEARABLE_COMPUTER` — A wearable device, such as a smart watch.</li> </ul>
`os_family`|**Optional\[str\]**|<p>The operating system family installed on the device:</p> <ul> <li>`ANDROID` — Android mobile operating system based on a modified version of the Linux kernel, designed primarily for touchscreen mobile devices.</li> <li>`BLACKBERRY` — BlackBerry OS mobile operating system developed by BlackBerry Limited for its BlackBerry smartphone devices.</li> <li>`BSD` — An operating system based on Research Unix, developed and distributed by the CSRG, and its open-source descendants like FreeBSD, OpenBSD, NetBSD, and DragonFly BSD.</li> <li>`IOS` — iOS mobile operating system developed by Apple Inc. exclusively for its mobile devices.</li> <li>`LINUX` — A family of open-source Unix-like operating systems based on the Linux kernel.</li> <li>`MAC_OS` — Classic Mac OS operating system developed by Apple Inc. before 2001 for the Macintosh family of personal computers.</li> <li>`OS_X` — macOS operating system developed by Apple Inc. since 2001 for Mac computers.</li> <li>`WINDOWS` — Microsoft Windows operating system developed and marketed by Microsoft for personal computers.</li> </ul>
`os_version`|**Optional\[float\]**|<p>The version of the OS. The version consists of major and minor version numbers and is represented as a single floating point number, for example, `14.4`.</p>
`os_version_major`|**Optional\[int\]**|<p>The major version of the OS.</p>
`os_version_minor`|**Optional\[int\]**|<p>The minor version of the OS.</p>
`os_version_bugfix`|**Optional\[int\]**|<p>The build number or the bugfix version of the OS.</p>
