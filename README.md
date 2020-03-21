# stream-data
Data Streaming application using Django Channels
It provides API endpoints for your Django application that can push data to connected clients. Data is sent using the Server-Sent Events protocol (SSE), in which data is streamed over a never-ending HTTP response.

For example, endpoint, `/events/`, that a client could connect to with a GET request:

```http
GET /events/ HTTP/1.1
Host: api.example.com
Accept: text/event-stream
```

The client would receive a streaming HTTP response with content looking like this:

```http
HTTP/1.1 200 OK
Transfer-Encoding: chunked
Connection: Transfer-Encoding
Content-Type: text/event-stream

event: message
data: {"foo": "bar"}

event: message
data: {"bar": "baz"}

...
```

## Features:

* Easy to consume from browsers or native applications.
* Highly reliable. Events can be persisted to your database, so clients can recover if they get disconnected.
* Set per-user channel permissions.

## How to Setup:
python3 is assumed to be installed, if not do the same
```
virtualenv venv
pip install django django-restframework django-eventstream
python manage.py runserver
```
