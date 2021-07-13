# Basic Concepts

**Ybrid® API v2 Specifications / Basic Concepts**

## Basic Concepts

### API v2 Responses

The basic v2 response consists of a header and an optional body section. It is formatted as a JSON object as per JSON specification.

Implementations MUST NOT assume any order of the members within the response.

#### Response Header

The response header is a JSON object in the member `"__responseHeader"` of the v2 response.

**Header Members**

| Field Name | Status | Type | Nullable | Description |
| :--- | :--- | :--- | :--- | :--- |
| `responseVersion` | Required | string | No | MUST have the value of `"v2"` as of this specification. |
| `statusCode` | TBD | integer | No | HTTP status code. |
| `success` | TBD | boolean | No | Whether the request was successful. |
| `supportedVersions` | Optional | array | No | List of API versions supported by the sender. |
| `timestamp` | TBD | string | No | Timestamp as ISO-8601 in timezone UTC with timezone specified. |

**Versions**

This specification defines Version `"v2"`. All versions beginning with "v" followed by only digits are reserved for other versions of the Ybrid® API.

#### Response Body

The response holds the response body by the optional member `"__responseObject"`. Absence of the member and the member being `null` MUST be handled equivalently by the reader.

**Ybrid® API v2 Specifications / Basic Concepts**

**api-specs, © by nacamar GmbH, Germany, 2019-2020. See GNU LESSER GENERAL PUBLIC LICENSE Version 2.1 for details. Ybrid® is a registered trademark of nacamar GmbH, Germany**

