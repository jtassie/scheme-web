# scheme-web

## Overview

This is a web-service that demos the functionality of the [scheme-jtassie](https://github.com/jtassie/scheme-jtassie) library.

This web-service offers the following [JSON Schema](https://json-schema.org/) contracts:
- [IM](https://github.com/jtassie/scheme-web/blob/master/public/schemes/im.json) with type "IM"
- [SMS](https://github.com/jtassie/scheme-web/blob/master/public/schemes/sms.json) with type "SMS"

## Running It

```
$ npm install
$ npm start
```

## Endpoints

The following endpoints are served by the web-service:

```
  GET  /spec         -- returns all the service contracts
  GET  /spec/:type   -- returns the service contract 'type' or 404 if none exist
  POST /validate     -- accepts and validates a JSON object instance against the service contracts
  GET  /test         -- demos the new object creation using the generated builders
```

## Example

POST the following against the validate endpoint: 
```
{
    "type": "SMS",
    "phoneNumber": "3434534",
    "body": {
        "text": "sdfsdfsd",
        "timestamp": "2018-12-16T23:39:49.157Z"
    }
}
```

returns a 200 OK
