StreamShark.io REST API
====================

StreamShark.io has a REST based API that can be used to create, read, update and delete all service elements. These include:

* Media (On-demand video and audio)
* Live Streams
* Live [Event](sections/event.md)
* [Keys](sections/keys.md) 
* Branding (player templates) 

This is a REST-style API that uses JSON for serialization and Basic auth (over HTTPS) for user authentication.

Making a request
----------------

All URLs start with 'https://secure.metacdn.com/api2/'. HTTPS must be used at all times.

Authentication
--------------

If you're making an integration with StreamShark.io for your own purposes, you can use HTTP Basic authentication. This is secure since all requests use SSL. You must supply your *API User* as the username, and your *Secret Key* as the password. These can be found in the StreamShark.io portal, under the *Account Settings* -> *Account Details*. 

No XML, just JSON
-----------------

We only support JSON for serialization of data. This means that you have to send `Content-Type: application/json` when you're POSTing or PUTing data into StreamShark.io. When GETing an end-point that returns JSON, you should send `Accept: application/json` in your request.
