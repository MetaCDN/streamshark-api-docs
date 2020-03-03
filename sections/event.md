Event API
====================

Get all events
-------------

* `GET /users/{username}/event/basic` will return all events

* `GET /users/{username}/event/basic/page/{pagenumber}` if pagination is required

```json
{
    "cursor": "CkkKGAoLY3JlYXRlZFRpbWUSCQjQ54SHx9nHAhIpahNzfm1ldGFjZG4tbWV0YXN0YWdlchILEgVFdmVudBiAgICYnK6ACgwYACAB",
    "size": 5,
    "events": [{
        "name": "new-dedicated",
        "title": "testing again",
        "description": "",
        "template": "Default2",
        "createdTime": 1461732309961,
        "lastUpdatedTime": null,
        "status": "READY",
        "eventUrl": "https://stage.metacdn.com/r/e/vorjbrr/new-dedicated",
        "sources": null,
        "activeSource": "main",
        "gaId": null,
        "embedRestrictions": null,
        "hiveEnabled": false,
        "isInternal": false,
        "aesKey": null,
        "aesKeyServer": null
    }, {
        "name": "enc-api-test",
        "title": "asdadasd",
        "description": "",
        "template": "Default2",
        "createdTime": 1461719694320,
        "lastUpdatedTime": null,
        "status": "READY",
        "eventUrl": "https://stage.metacdn.com/r/e/vorjbrr/enc-api-test",
        "activeSource": "main",
        "gaId": null,
        "embedRestrictions": null,
        "hiveEnabled": false,
        "isInternal": true,
        "aesKey": "43214321432143214321432143214321",
        "aesKeyServer": "https://stage.metacdn.com/r/ssdrm/keys/hls/vorjbrr/enc-api-test/sDV9Y8gUS%2Fy2CvwpahlqDA%3D%3D"
    },
    ...
    {
        "name": "test",
        "title": "testttt",
        "description": "",
        "template": "Default2",
        "createdTime": 1449455640940,
        "lastUpdatedTime": 1449456486285,
        "status": "READY",
        "eventUrl": "http://stage.metacdn.com/r/e/vorjbrr/test",
        "sources": null,
        "activeSource": "post",
        "gaId": null,
        "embedRestrictions": null,
        "hiveEnabled": false,
        "isInternal": false,
        "aesKey": null,
        "aesKeyServer": null
    }],
    "moreResult": false
}
```
Filtering Events
-------------

The GET request accepts couple of query parameters as well to filter the response based on our requirements

1. *last* = If interested in events created in last X days. Value must be an integer, for example `GET /users/{username}/event/basic?last=10` will return all the events created by the given user in last 10 days. **Note** - If the value is 0, then the response only contains the events created today.
2. *from* and *to* = If interested in events created within the specific date range. The dates should be in yyyyMMdd format. For example, `GET /users/{username}/event/basic?from=20160110&last=20160215` will return all the events created by the given user from 10th January 2016 to 15th February 2016 (inclusive). **Note** - If any *from* or *to* query parameters are included in the request then these take precedence over the *last* query parameter.

Get a specific event
-------------

* `GET /users/{username}/event/basic/{name}` will return a specific event.

```json
{
    "name": "enc-api-test",
        "title": "asdadasd",
        "description": "",
        "template": "Default2",
        "createdTime": 1461719694320,
        "lastUpdatedTime": null,
        "status": "READY",
        "eventUrl": "https://stage.metacdn.com/r/e/vorjbrr/enc-api-test",
        "sources": null,
        "activeSource": "main",
        "gaId": null,
        "embedRestrictions": null,
        "hiveEnabled": false,
        "isInternal": true,
        "aesKey": "43214321432143214321432143214321",
        "aesKeyServer": "https://stage.metacdn.com/r/ssdrm/keys/hls/vorjbrr/enc-api-test/sDV9Y8gUS%2Fy2CvwpahlqDA%3D%3D"
}
```

Update the key and keyserver for a specific event
-------------

* `POST /users/{username}/event/{name}` will update a specific event

```json
{
    "isInternal": true,
        "aesKey": "43214321432143214321432143214321",
        "aesKeyServer": "https://mykeyserver/is/here"
}
```
