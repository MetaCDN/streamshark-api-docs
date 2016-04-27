Key API
====================

Get HLS key for Event  
-------------

* `GET /users/{username}/keys/hls/{eventname}` will return a AES128 key in binary format if a key is configured for an [event](event.md)

```http
GET /api2/users/joebloggs/keys/hls/enc-api-test HTTP/1.1

HTTP/1.1 200 OK
Vary: Accept-Charset, Accept-Encoding, Accept-Language, Accept
Content-Type: binary/octet-stream
Server: Google Frontend
Alt-Svc: quic=":443"; ma=2592000; v="32,31,30,29,28,27,26,25"
Connection: close
Date: Wed, 27 Apr 2016 01:28:20 GMT
Accept-Ranges: bytes
Content-Length: 16
Cache-Control: private, max-age=300, must-revalidate
Access-Control-Allow-Origin: *

<binary data>
```
