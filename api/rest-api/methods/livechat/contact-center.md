# Contact Center

## Get the contact info

Retrieve the contact info

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/omnichannel/contact` | `yes` | `GET` |

## Query Parameter

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `contactId` | `gAoxwhBGgEh8cyKx4` | Required | The contact's id. |

## Example Call

```bash
curl http://localhost:3000/api/v1/omnichannel/contact?contactId=gAoxwhBGgEh8cyKx4
```

## Example Result

```javascript
{
    "contact": {
        "_id": "gAoxwhBGgEh8cyKx4",
        "username": "guest-4",
        "_updatedAt": "2021-10-21T19:36:47.960Z",
        "token": "hzf48867bv9lwjzigk2tk"
    },
    "success": true
}
```

## Register a new Contact

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/omnichannel/contact` | `yes` | `POST` |

## Example payload

```javascript
{
  "name": "Livechat Contact",
  "email": "contact@rocket.chat",
  "token": "iNKE8a6k6cjbqWhWd",
  "phone": "55 51 5555-5555",
  "customFields": [{
    "key": "address",
    "value": "Rocket.Chat street",
    "overwrite": true
  }],
  "contactManager": {
		"username": "name.username"
	},
}
```

## Example Call

```bash
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/omnichannel/contact \
    -d '{ "name": "Livechat Contact", "email": "contact@rocket.chat", "token": "iNKE8a6k6cjbqWhWd", "phone": "55 51 5555-5555", "customFields": [{ "key": "address", "value": "Rocket.Chat street", "overwrite": true }], "contactManager": { "username": "name.username" } }'
```

## Example Result

```javascript
{
  "contact": "RZttBAjYwHjjcgusr",
  "success": true
```

