# Kumo Develop Example

Kumo sample code, deployed with the help of Kumo.

## Usage

> Kumo is still in development, if it goes well there will be a beta test at the end of August or the begin of September.

### From API

1. Waiting for Kumo's limited test;
2. Register kumo account:

```python
import requests

result = requests.post(
    "http://127.0.0.1/user/register",
    json={
        "username": "username",
        "password": "password",
    }
).json()

assert result["code"] == 200
```

3. Login kumo account to get token:

```python
import requests

result = requests.post(
    "http://127.0.0.1/user/login",
    json={
        "username": "username",
        "password": "password",
    }
).json()

assert result["code"] == 200

token = result["data"]["token"]
```

> TODO

### From CLI

> TODO

### From Web

> TODO
