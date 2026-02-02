
# Orgs VAS Pinless Debit Conversions Response Result

## Structure

`OrgsVASPinlessDebitConversionsResponseResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `response` | [`?OrgsVASPinlessDebitConversionsResponseItem`](../../doc/models/orgs-vas-pinless-debit-conversions-response-item.md) | Optional | - | getResponse(): ?OrgsVASPinlessDebitConversionsResponseItem | setResponse(?OrgsVASPinlessDebitConversionsResponseItem response): void |

## Example (as JSON)

```json
{
  "response": {
    "data": [
      {
        "id": "id0",
        "created": "created0",
        "modified": "modified8",
        "creator": "String9",
        "modifier": "modifier4"
      },
      {
        "id": "id0",
        "created": "created0",
        "modified": "modified8",
        "creator": "String9",
        "modifier": "modifier4"
      },
      {
        "id": "id0",
        "created": "created0",
        "modified": "modified8",
        "creator": "String9",
        "modifier": "modifier4"
      }
    ],
    "details": {
      "requestId": 240,
      "totals": {
        "key1": "val1",
        "key2": "val2"
      },
      "page": {
        "current": 164,
        "last": 78,
        "hasMore": false
      }
    },
    "errors": [
      {
        "code": 144,
        "severity": 6,
        "msg": "msg6",
        "field": "field4",
        "errorCode": "errorCode6"
      }
    ]
  }
}
```

