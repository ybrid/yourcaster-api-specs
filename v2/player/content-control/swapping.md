# Swapping

**Ybrid® API v2 Specifications / Player / Content Control / Swapping**

## Swapping Current Item for any Predefined Alternative

| Path | Method | Allowed Contents | Description |
| :--- | :---: | :---: | :---: |
| `/ctrl/v2/playout/swap/item` | `GET` | `none` |  |

| Parameter | Use | Description | Example |
| :---: | :---: | :--- | :--- |
| `session-id` | _required_ | Id of Session | `session-id=41ea9e95-ce20-4da8-85e1-4f9da688af3c` |

#### Example Call URL

```text
https://cast.ybrid.io/ctrl/v2/playout/swap/item?session-id=41ea9e95-ce20-4da8-85e1-4f9da688af3c
```

#### Example cURL Call

```bash
curl -v "https://cast.ybrid.io/ctrl/v2/playout/swap/item?session-id=41ea9e95-ce20-4da8-85e1-4f9da688af3c"
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

}
```

**Ybrid® API v2 Specifications / Player / Content Control / Swapping**

**api-specs, © by nacamar GmbH, Germany, 2019-2020. See GNU LESSER GENERAL PUBLIC LICENSE Version 2.1 for details. Ybrid® is a registered trademark of nacamar GmbH, Germany**

