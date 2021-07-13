# create

**Ybrid® API v2 Specifications / Player / Session Management / Creation**

## Creation

| Path | Method | Allowed Contents | Description |
| :--- | :---: | :---: | :---: |
| `<ALIAS>/ctrl/v2/session/create` | `GET` |  |  |

| Parameter | Use | Description | Example |
| :---: | :---: | :--- | :--- |
| `service-id` | _required_ | Id of Service | `service-id=my-service-id` |

#### Example Call URL

```text
https://cast.ybrid.io/alias/ctrl/v2/session/create?service-id=my-service-id
```

#### Example cURL Call with JSON Body

```bash
curl -v \
     -X GET "https://cast.ybrid.io/alias/ctrl/v2/session/create?service-id=my-service-id"
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

**Ybrid® API v2 Specifications / Player / Session Management / Creation**

**api-specs, © by nacamar GmbH, Germany, 2019-2020. See GNU LESSER GENERAL PUBLIC LICENSE Version 2.1 for details. Ybrid® is a registered trademark of nacamar GmbH, Germany**

