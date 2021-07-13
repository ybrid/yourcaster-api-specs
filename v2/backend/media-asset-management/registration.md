# Registration

| Path | Method | Allowed Contents | Description |
| :--- | :---: | :---: | :---: |
| `/ctrl/v2/admin/services/service/item/register` | `POST` | `application/json` |  |

| Parameter | Use | Description | Example |
| :---: | :---: | :--- | :--- |
| `token` | _required_ | Service Administration Token | `token=392m2U937x5Up6VUhVG79gw8ynz7337w` |
| `service-id` | _required_ | Id of Service | `service-id=my-service-id` |

### Example Call URL

```text
https://cast.ybrid.io/ctrl/v2/admin/services/service/item/register?token=392m2U937x5Up6VUhVG79gw8ynz7337w&service-id=my-service-id
```

### Example cURL Call with JSON Body

```bash
curl -v \
     -d '{"assetsToRegister":[{"mediaURL":"https://my-storage.superhoster.com/assets/michael_jackson-thriller.mp3","item":{"artist":"Michael Jackson", "title":"Thriller"}}]}' \
     -H "Content-Type: application/json" \
     -X POST "https://cast.ybrid.io/ctrl/v2/admin/services/service/item/register?token=392m2U937x5Up6VUhVG79gw8ynz7337w&service-id=my-service-id"
```

## Request Body

### Specification

```javascript
{
  "assetsToRegister": [
    {
      "item": {
        "id": <ID>,
        "artist": <ARTIST>,
        "title": <TITLE>,
        "description": <DESCRIPTION>,
        "durationMillis": <DURATION-MILLIS>,
        "cuePoints": {
          <CUE_POINT_TYPE>: <CUE_POINT_POSITION_IN_MILLISECONDS>,
          ...
          <CUE_POINT_TYPE>: <CUE_POINT_POSITION_IN_MILLISECONDS>
        },
        "type": <TYPE>,
        "url": <URL>
      },
      "mediaURL": <SOURCE-URL>
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
ID                                 = *TEXT
ARTIST                             = *TEXT
TITLE                              = *TEXT
DESCRIPTION                        = *TEXT
DURATION-MILLIS                    = *TEXT 
TYPE                               = *TEXT
CUE_POINT_TYPE                     = *TEXT, value of ( FADE_IN_1 | FADE_IN_2 | BEAT_START | VOCALS_START | FADE_OUT_1 | FADE_OUT_2 )
CUE_POINT_POSITION_IN_MILLISECONDS = *DIGIT, position of cuepoint in milliseconds from the beginning of the media
URL                                = *TEXT
MEDIA-URL                          = *TEXT
```

#### Example

```javascript
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

```javascript
{

}
```

#### Example

```javascript
{
    "__responseHeader": {
        "responseVersion":"v2",
        "statusCode":200,
        "success":true,
        "supportedVersions":["v1","v2"]
    }
}
```

\*\*\*\*

