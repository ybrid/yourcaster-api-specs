##### [**Ybrid<sup>®</sup> API v2 Specifications**](../../) / [**Backend**](../) / [**Media Asset Management**](./) / Registration
---

# Registration

Path | Method | Allowed Contents | Description
------------- | :-------------: | :-------------: | :-------------:
`/ctrl/v2/admin/services/service/item/register` | `POST` | `application/json` | 
  
Parameter | Use | Description | Example
:-------------: | :-------------: | :------------- | :------------- 
`token` | *required* | Service Administration Token | `token=392m2U937x5Up6VUhVG79gw8ynz7337w`
`id` | *required* | Id of Service | `id=my-service-id`

#### Example Call URL
```text
https://cast.ybrid.io/ctrl/v2/admin/services/service/item/register?token=392m2U937x5Up6VUhVG79gw8ynz7337w&id=my-service-id
```

#### Example cURL Call with JSON Body
```bash
curl -v \
     -d '{"assetsToRegister":[{"mediaURL":"https://my-storage.superhoster.com/assets/michael_jackson-thriller.mp3","item":{"artist":"Michael Jackson", "title":"Thriller"}}]}' \
     -H "Content-Type: application/json" \
     -X POST "https://cast.ybrid.io/ctrl/v2/admin/services/service/item/register?token=392m2U937x5Up6VUhVG79gw8ynz7337w&id=my-service-id"
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
      "mediaURL": SOURCE-URL
    },
    {
      "item": {
        ...
      },
      "mediaURL": URL
    },
    ...
  ]
}
```
```text
ID               = *TEXT
ARTIST           = *TEXT
TITLE            = *TEXT
DESCRIPTION      = *TEXT
DURATION-MILLIS  = *TEXT
TYPE             = *TEXT
URL              = *TEXT
MEDIA-URL        = *TEXT
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
      "mediaURL": "https://my-storage.superhoster.com/assets/michael_jackson-thriller.mp3"
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
      "mediaURL": "https://my-storage.superhoster.com/assets/madonna-like_a_prayer.mp3"
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
    "__responseHeader": {
        "responseVersion":"v2",
        "statusCode":200,
        "success":true,
        "supportedVersions":["v1","v2"]
    }
}
```


---
##### [**Ybrid<sup>®</sup> API v2 Specifications**](../../) / [**Backend**](../) / [**Media Asset Management**](./) / Registration
###### api-specs, © by nacamar GmbH, Germany, 2019. See [GNU LESSER GENERAL PUBLIC LICENSE Version 2.1](/LICENSE) for details. Ybrid<sup>®</sup> is a registered trademark of nacamar GmbH, Germany 
