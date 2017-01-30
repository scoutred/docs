---
date: 2017-01-26T19:56:50+01:00
title: Authentication
weight: 10
---

ScoutRED uses API tokens to manage access to the API. Every account on ScoutRED is returned a token when they authenticate. In order to obtain an API token all you need to do is <a href="https://scoutred.com/signup">signup</a> on ScoutRED and then use the authentication endpoint.


## /api/login

The `/api/login` endpoint is necessary to obtain the token required for all subsequent requests.

### Example Request

```bash
# POST the email and password to receive an API token.
$ curl -X POST https://scoutred.com/api/login \
	-d '{"email":"hello@scoutred.com","password":"auth123"}'
```

### Example Response
```json
{
	"token": "eyJhbGciOiJSUzI1Ni..."
}
```