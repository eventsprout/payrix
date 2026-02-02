
# Fraud Sight Available Rule Groups Response

## Structure

`FraudSightAvailableRuleGroupsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ruleGroups` | `?(array[])` | Optional | A list of FraudSight rule groups available for the specified entity. Each rule group includes a `groupName` and `description` that define how FraudSight decisions are applied. For example, for card-not-present (CNP), card-present (CP), or both transaction types. These values can be reused when enabling FraudSight for additional Merchants or Orgs. | getRuleGroups(): ?array | setRuleGroups(?array ruleGroups): void |
| `httpStatusCode` | `?string` | Optional | The status code returned from the internal FraudSight service call, indicating whether the request was successful or encountered an error. | getHttpStatusCode(): ?string | setHttpStatusCode(?string httpStatusCode): void |
| `httpStatusMessage` | `?string` | Optional | A brief message returned from the internal FraudSight service call, describing the outcome of the request. For example, `OK` or `Bad Request`. | getHttpStatusMessage(): ?string | setHttpStatusMessage(?string httpStatusMessage): void |
| `correlationId` | `?int` | Optional | A UUID generated for the FraudSight service that traces transactions during processing, enabling request tracking from submission to response. | getCorrelationId(): ?int | setCorrelationId(?int correlationId): void |

## Example (as JSON)

```json
{
  "ruleGroups": [
    {
      "key1": "val1",
      "key2": "val2"
    },
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "httpStatusCode": "httpStatusCode6",
  "httpStatusMessage": "httpStatusMessage8",
  "correlationId": 18
}
```

