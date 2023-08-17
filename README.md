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

4. Deploy

```python
import requests

result = requests.post(
    "http://127.0.0.1/instance/create/git",
    json={
        "repo_link": "https://github.com/Yazawazi/kumo-develop-example",
        "name": "kumo-application",
        "entry_point": "main.py",
    },
    headers={
        "Authorization": f"Bearer {token}"
    }
)

assert result["code"] == 200
```

### From CLI

```bash
tengoku user register USERNAME
tengoku user login USERNAME
tengoku instance git https://github.com/Yazawazi/kumo-develop-example kumoapp-test
```

### From Web

> TODO
