##### [**Ybrid<sup>®</sup> API v2 Specifications**](../../) / [**Player**](../) / [**Content Control**](./) / Injection
---

# Injection of Remote On-Demand Asset

It is possible to inject any remote on-demand content as long it is accessible via HTTP. If 
the content allready has been cached by the system, injection will work immediately. For pre-registration of 
such content, please use [**Registration**](/v2/backend/media-asset-management/registration.md).

Path | Method | Allowed Contents | Description
------------- | :-------------: | :-------------: | :-------------:
`/ctrl/v2/playout/inject/item` | `POST` | `application/json` | 
  
Parameter | Use | Description | Example
:---: | :---: | --- | :--- 
`session-id` | *required* | Id of Session | `session-id=41ea9e95-ce20-4da8-85e1-4f9da688af3c`
`mode` | *required* | Injection Mode. One of `( inflate \| overwrite \| replaceEnd2end \| replaceFade2end \| replaceFull )`. Defaults to `overwrite`.<br/><dl><dt>`inflate`</dt><dd>Injects the asset by *inflating* the stream. That means, that the current stream content gets buffered and played after the injected content.</dd><dt>`overwrite`</dt><dd>The injected content overwrites the content of the current stream.</dd><dt>`replaceEnd2end`</dt><dd>The injected content gets trimmed from start to fit the remaining time until the next item in the main stream start.</dd><dt>`replaceFade2end`</dt><dd>The injected content ends simultanousely with the current item in the main content stream. Therefore its content gets trimmed at the end and faded out.</dd><dt>`replaceFull`</dt><dd>The injected content will be played fully by overwriting the current main content item and inflating the main stream. The main stream will start with the exact beginning of the next item.</dd></dl> | `mode=replaceEnd2end`

### Example Call URL
```text
https://cast.ybrid.io/ctrl/v2/playout/inject/item?session-id=41ea9e95-ce20-4da8-85e1-4f9da688af3c&mode=replaceEnd2end
```

### Example cURL Call with JSON Body
```bash
curl -v \
     -d '{"mediaURL":"https://my-storage.superhoster.com/assets/michael_jackson-thriller.mp3"}' \
     -H "Content-Type: application/json" \
     -X POST "https://cast.ybrid.io/ctrl/v2/playout/inject/item?session-id=41ea9e95-ce20-4da8-85e1-4f9da688af3c&mode=replaceEnd2end"
```

## Request Body
### Specification
```json
{
    "mediaURL": MEDIA_URL
}
```
```ini
MEDIA_URL   = URL
```

### Example
```json
{
    "mediaURL":"https://my-storage.superhoster.com/assets/michael_jackson-thriller.mp3"
}
```

## Response
### Specification
```json
{
   "injectionWasSuccessful": INJECTION_RESULT
}
```
```ini
INJECTION_RESULT   = BOOL; TRUE if injection was successful.
```
### Example
```json
{
   "injectionWasSuccessful":true
}
```

---
##### [**Ybrid<sup>®</sup> API v2 Specifications**](../../) / [**Player**](../) / [**Content Control**](./) / Injection
###### api-specs, © by nacamar GmbH, Germany, 2019. See [GNU LESSER GENERAL PUBLIC LICENSE Version 2.1](/LICENSE) for details. Ybrid<sup>®</sup> is a registered trademark of nacamar GmbH, Germany 
