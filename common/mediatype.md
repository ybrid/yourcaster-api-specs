# MediaType

**Ybrid® API Common Specifications / Media Type**

## Media Type

This specification defines the media type `TBA`.

### Registration

For the registration see TBA.

### Encoding

The encoding of messages of this type is 8 bit JSON.

### Parameters

#### Required parameters

This media type does not define any required parameters.

#### Optional parameters

| Parameter | Default value | Description |
| :--- | :--- | :--- |
| `charset` | `UTF-8` | Defines the charset of the message. The only valid value is `UTF-8`. |
| `version` | none/auto detect | Defines the version of the outer framing format. See below. |

#### Versions

At this point this specification only allows for `version` with a value of `v2`. Additional versions might be added later. A reader MUST NOT assume the response is a version `v2` response when no version is provided. The reader MUST preform proper auto-detection.

For version `v2` see: [API v2 Responses](../v2/basic-concepts.md).

**Ybrid® API Common Specifications / Media Type**

**api-specs, © by nacamar GmbH, Germany, 2019-2020. See GNU LESSER GENERAL PUBLIC LICENSE Version 2.1 for details. Ybrid® is a registered trademark of nacamar GmbH, Germany**

