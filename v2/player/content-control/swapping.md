##### [**Ybrid<sup>®</sup> API v2 Specifications**](../../) / [**Player**](../) / [**Content Control**](./) / Swapping
---

# Swapping

## Swapping Current Item for any Predefined Alternative

Path | Method | Allowed Contents | Description
------------- | :-------------: | :-------------: | :-------------:
`/ctrl/v2/playout/swap/item` | `GET` | `none` | 
  
Parameter | Use | Description | Example
:-------------: | :-------------: | :------------- | :------------- 
`session-id` | *required* | Id of Session | `session-id=41ea9e95-ce20-4da8-85e1-4f9da688af3c`

#### Example Call URL
```text
https://cast.ybrid.io/ctrl/v2/playout swap/item?session-id=41ea9e95-ce20-4da8-85e1-4f9da688af3c
```

#### Example cURL Call
```bash
curl -v "https://cast.ybrid.io/ctrl/v2/playout swap/item?session-id=41ea9e95-ce20-4da8-85e1-4f9da688af3c"
```

### Response
#### Specification
```json
{

}
```
#### Example
```json
{

}
```


## Swapping Current Item for Given Asset

It is possible to swap current content for any remote on-demand content as long it is accessible via HTTP. If 
the content allready has been cached by the system, swapping will work iimediately. For pre-registration of 
such content, please use [**Registration**](/v2/backend/media-asset-management/registration.md).

Path | Method | Allowed Contents | Description
------------- | :-------------: | :-------------: | :-------------:
`/ctrl/v2/playout/swap/item` | `POST` | `application/json` | 
  
Parameter | Use | Description | Example
:-------------: | :-------------: | :------------- | :------------- 
`session-id` | *required* | Id of Session | `session-id=41ea9e95-ce20-4da8-85e1-4f9da688af3c`

#### Example Call URL
```text
https://cast.ybrid.io/ctrl/v2/playout swap/item?session-id=41ea9e95-ce20-4da8-85e1-4f9da688af3c
```

#### Example cURL Call with JSON Body
```bash
curl -v \
     -d '{"mediaURL":"https://my-storage.superhoster.com/assets/michael_jackson-thriller.mp3"}' \
     -H "Content-Type: application/json" \
     -X POST "https://cast.ybrid.io/ctrl/v2/playout swap/item?session-id=41ea9e95-ce20-4da8-85e1-4f9da688af3c"
```

### Request Body
#### Specification
```json
{
    "mediaURL": MEDIA_URL
}
```
```ini
MEDIA_URL   = URL
```

#### Example
```json
{
    "mediaURL":"https://my-storage.superhoster.com/assets/michael_jackson-thriller.mp3"
}
```

### Response
#### Specification
```json
{

}
```
#### Example
```json
{

}
```

---
##### [**Ybrid<sup>®</sup> API v2 Specifications**](../../) / [**Player**](../) / [**Content Control**](./) / Swapping
###### api-specs, © by nacamar GmbH, Germany, 2019. See [GNU LESSER GENERAL PUBLIC LICENSE Version 2.1](/LICENSE) for details. Ybrid<sup>®</sup> is a registered trademark of nacamar GmbH, Germany 
