# set-max-bit-rate

**Ybrid® API v2 Specifications / Player / Session Management / Setting of Maximum Bit-Rate**

## Setting of Maximum Bit-Rate

| Path | Method | Allowed Contents | Description |
| :--- | :---: | :---: | :---: |
| `<ALIAS>/ctrl/v2/session/set-max-bit-rate` | `GET` |  |  |

| Parameter | Use | Description | Example |
| :---: | :---: | :--- | :--- |
| `session-id` | _required_ | Id of Session | `session-id=f1ff64b0-cdf2-466c-89c6-4146bca64e41` |
| `value` | _required_ | Bit-Rate in bits per second (bps) | `value=128000` |

#### Example Call URL

```text
https://cast.ybrid.io/alias/ctrl/v2/session/set-max-bit-rate?session-id=f1ff64b0-cdf2-466c-89c6-4146bca64e41&value=128000
```

#### Example cURL Call with JSON Body

```bash
curl -v \
     -X GET "https://cast.ybrid.io/alias/ctrl/v2/session/set-max-bit-rate?session-id=f1ff64b0-cdf2-466c-89c6-4146bca64e41&value=128000"
```

### Response

#### Specification

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

**Ybrid® API v2 Specifications / Player / Session Management / Setting of Maximum Bit-Rate**

**api-specs, © by nacamar GmbH, Germany, 2019-2022. See GNU LESSER GENERAL PUBLIC LICENSE Version 2.1 for details. Ybrid® is a registered trademark of nacamar GmbH, Germany**

