
# Fraud Sight Available Rule Groups Response Result

## Structure

`FraudSightAvailableRuleGroupsResponseResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `response` | [`?FraudSightAvailableRuleGroupsResponseItem`](../../doc/models/fraud-sight-available-rule-groups-response-item.md) | Optional | - | getResponse(): ?FraudSightAvailableRuleGroupsResponseItem | setResponse(?FraudSightAvailableRuleGroupsResponseItem response): void |

## Example (as JSON)

```json
{
  "response": {
    "data": [
      {
        "ruleGroups": [
          {
            "key1": "val1",
            "key2": "val2"
          }
        ],
        "httpStatusCode": "httpStatusCode6",
        "httpStatusMessage": "httpStatusMessage0",
        "correlationId": 154
      },
      {
        "ruleGroups": [
          {
            "key1": "val1",
            "key2": "val2"
          }
        ],
        "httpStatusCode": "httpStatusCode6",
        "httpStatusMessage": "httpStatusMessage0",
        "correlationId": 154
      },
      {
        "ruleGroups": [
          {
            "key1": "val1",
            "key2": "val2"
          }
        ],
        "httpStatusCode": "httpStatusCode6",
        "httpStatusMessage": "httpStatusMessage0",
        "correlationId": 154
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

