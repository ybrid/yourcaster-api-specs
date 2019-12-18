##### [**Ybrid<sup>®</sup> API v2 Specifications**](../../) / [**Player**](../) / [**Content Control**](./) / Injection
---

# Injection

## Injection of Given Asset

It is possible to inject any remote on-demand content as long it is accessible via HTTP. If 
the content allready has been cached by the system, injection will work immediately. For pre-registration of 
such content, please use [**Registration**](/v2/backend/media-asset-management/registration.md).

Path | Method | Allowed Contents | Description
------------- | :-------------: | :-------------: | :-------------:
`/ctrl/v2/playout/inject/item` | `POST` | `application/json` | 
  
Parameter | Use | Description | Example
:---: | :---: | --- | :--- 
`session-id` | *required* | Id of Session | `session-id=41ea9e95-ce20-4da8-85e1-4f9da688af3c`
`mode` | *required* | Injection Mode. One of `( inflate | overwrite | replaceEnd2end | replaceFade2end | replaceFull )`. Defaults to `overwrite`. | `mode=replaceEnd2end`

#### Example Call URL
```text
https://cast.ybrid.io/ctrl/v2/playout/inject/item?session-id=41ea9e95-ce20-4da8-85e1-4f9da688af3c&mode=replaceEnd2end
```

#### Example cURL Call with JSON Body
```bash
curl -v \
     -d '{"mediaURL":"https://my-storage.superhoster.com/assets/michael_jackson-thriller.mp3"}' \
     -H "Content-Type: application/json" \
     -X POST "https://cast.ybrid.io/ctrl/v2/playout/inject/item?session-id=41ea9e95-ce20-4da8-85e1-4f9da688af3c&mode=replaceEnd2end"
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
##### [**Ybrid<sup>®</sup> API v2 Specifications**](../../) / [**Player**](../) / [**Content Control**](./) / Injection
###### api-specs, © by nacamar GmbH, Germany, 2019. See [GNU LESSER GENERAL PUBLIC LICENSE Version 2.1](/LICENSE) for details. Ybrid<sup>®</sup> is a registered trademark of nacamar GmbH, Germany 
