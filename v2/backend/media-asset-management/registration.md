##### [**Ybrid® API v2 Specifications**](../../) / [**Backend**](../) / [**Media Asset Management**](./) / Registration
---

# Registration

Path | Method | Allowed Contents | Description
------------- | :-------------: | :-------------: | :-------------:
**/ctrl/v2/admin/services/service/item/register** | `POST` | `application/json` | 
  
Parameter | Use | Description | Example
:-------------: | :-------------: | :------------- | :------------- 
**token** | *required* | Service Administration Token | `token=392m2U937x5Up6VUhVG79gw8ynz7337w`
**id** | *required* | Id of Service | `id=my-service-id`

#### Example Call
```http
https://cast.ybrid.io/ctrl/v2/admin/services/service/item/register?token=392m2U937x5Up6VUhVG79gw8ynz7337w&id=my-service-id
```

## Request Body
### Specification
```json
{
  "assetsToRegister": [
    {
      "item": {
        "id": ID,
        "artist": ARTIST,
        "title": TITLE,
        "description": DESCRIPTION,
        "durationMillis": DURATION-MILLIS,
        "type": TYPE,
        "url": URL
      },
      "srcURL": SOURCE-URL
    },
    {
      "item": {
        ...
      },
      "srcURL": URL
    },
    ...
  ]
}
```
```ini
ID               = *TEXT
ARTIST           = *TEXT
TITLE            = *TEXT
DESCRIPTION      = *TEXT
DURATION-MILLIS  = *TEXT
TYPE             = *TEXT
URL              = *TEXT
SOURCE-URL       = *TEXT
```

### Example
```json
{
  "assetsToRegister": [
    {
      "item": {
        "artist": "Michael Jackson",
        "description": "",
        "title": "Thriller",
        "url": "",
        "durationMillis": 209345,
        "id": "mt-12345",
        "type": "MUSIC"
      },
      "srcURL": "https://my-storage.superhoster.com/assets/michael_jackson-thriller.mp3"
    },
    {
      "item": {
        "artist": "Madonna",
        "description": "",
        "title": "Like a Prayer",
        "url": "",
        "durationMillis": 199545,
        "id": "mt-12378",
        "type": "MUSIC"
      },
      "srcURL": "https://my-storage.superhoster.com/assets/madonna-like_a_prayer.mp3"
    }
  ]
}
```

## Response
### Specification
```json
{

}
```
### Example
```json
{

}
```


---
##### [**Ybrid® API v2 Specifications**](../../) / [**Backend**](../) / [**Media Asset Management**](./) / Registration
##### api-specs, © by nacamar GmbH, Germany, 2019. See [GNU LESSER GENERAL PUBLIC LICENSE Version 2.1](/LICENSE) for details. Ybrid® is a registered trademark of nacamar GmbH, Germany 
