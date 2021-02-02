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
| `/api/v1/livechat/visitor` | `no` | `POST` |

## Example payload

```javascript
{
  "visitor": {
    "name": "Livechat Visitor",
    "email": "visitor@rocket.chat",
    "token": "iNKE8a6k6cjbqWhWd",
    "phone": "55 51 5555-5555",
    "customFields": [{
      "key": "address",
      "value": "Rocket.Chat street",
      "overwrite": true
    }]
  }
}
```

## Example Call

```bash
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/visitor \
    -d '{"visitor": {"name": "Livechat Visitor", "email": "visitor@rocket.chat", "token": "iNKE8a6k6cjbqWhWd", "phone": "55 51 5555-5555", "customFields": [{ "key": "address", "value": "Rocket.Chat street", "overwrite": true }] }'
```

## Example Result

```javascript
{
  "visitor": {
    "_id": "sGtcfEYz852uguxaS",
    "username": "guest-7",
    "_updatedAt": "2018-09-21T16:12:32.808Z",
    "token": "iNKE8a6k6cjbqWhWd",
    "phone": [
      {
        "phoneNumber": "55 51 5555-5555"
      }
    ],
    "visitorEmails": [
      {
        "address": "visitor@rocket.chat"
      }
    ],
    "name": "Livechat Visitor",
    "livechatData": {
      "address": "Rocket.Chat street"
    }
  },
  "success": true
```

