# Injection

**Ybrid® API v2 Specifications / Player / Content Control / Injection**

## Injection of Remote On-Demand Asset

It is possible to inject any remote on-demand content as long it is accessible via HTTP. If the content allready has been cached by the system, injection will work immediately. For pre-registration of such content, please use [**Registration**](../../backend/media-asset-management/registration.md).

| Path | Method | Allowed Contents | Description |
| :--- | :---: | :---: | :---: |
| `/ctrl/v2/playout/inject/item` | `POST` | `application/json` |  |

| Parameter | Use | Description | Example |
| :---: | :---: | :--- | :--- |
| `session-id` | _required_ | Id of Session | `session-id=41ea9e95-ce20-4da8-85e1-4f9da688af3c` |
| `mode` | _required_ | Injection Mode. One of `( inflate \| overwrite \| replaceEnd2end \| replaceFade2end \| replaceFull )`. Defaults to `overwrite`. \`inflate\`Injects the asset by \*inflating\* the stream. That means, that the current stream content gets buffered and played after the injected content.\`overwrite\`The injected content overwrites the content of the current stream.\`replaceEnd2end\`The injected content gets trimmed from start to fit the remaining time until the next item in the main stream start.\`replaceFade2end\`The injected content ends simultanousely with the current item in the main content stream. Therefore its content gets trimmed at the end and faded out.\`replaceFull\`The injected content will be played fully by overwriting the current main content item and inflating the main stream. The main stream will start with the exact beginning of the next item. | `mode=replaceEnd2end` |

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

```javascript
{
    "mediaURL": MEDIA_URL
}
```

```text
MEDIA_URL   = URL
```

#### Example

```javascript
{
    "mediaURL":"https://my-storage.superhoster.com/assets/michael_jackson-thriller.mp3"
}
```

### Response

#### Specification

```javascript
{
   "injectionWasSuccessful": INJECTION_RESULT
}
```

```text
INJECTION_RESULT   = BOOL; TRUE if injection was successful.
```

#### Example

```javascript
{
   "injectionWasSuccessful":true
}
```

**Ybrid® API v2 Specifications / Player / Content Control / Injection**

**api-specs, © by nacamar GmbH, Germany, 2019-2020. See GNU LESSER GENERAL PUBLIC LICENSE Version 2.1 for details. Ybrid® is a registered trademark of nacamar GmbH, Germany**

