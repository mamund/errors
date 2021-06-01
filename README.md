# RFC7807 Error Objects


This is a set of common error objects/extensions I use in my APIs. These are all extensions of the [RFC7870](https://datatracker.ietf.org/doc/html/rfc7807) specification.

The simplest form of RFC7807 error my apps produce looks like thissimple example:

```
{
  "type": "https://datatracker.ietf.org/doc/html/rfc7807#section-3",
  "title": "SimpleStorage: [company]",
  "detail": "Not Found [xxx]",
  "status": "400",
  "instance": "http://localhost:8484/xxx"
}
```

The default RFC7807 extension you can expect is `mamund`:

```
{
  "type": "https://datatracker.ietf.org/doc/html/rfc7807#section-3",
  "title": "SimpleStorage: [company]",
  "detail": "Not Found [xxx]",
  "status": "400",
  "instance": "http://localhost:8484/xxx",
  "mamund": {
    "dateTime": "2021-06-01T16:55:52.481Z",
    "appName": "bigco-company",
    "serverID": "EYC-01",
    "internalCode": "{local error code}",
    "stackTrace": "{full stack trace}",
  }
}
```
**NOTE**: Additional properties/objects MAY appear within the `mamund` extension. Client apps SHOULD ignore any properties they do not recognize or understand. 
