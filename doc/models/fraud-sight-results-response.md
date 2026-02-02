
# Fraud Sight Results Response

## Structure

`FraudSightResultsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `status` | `?int` | Optional | The Fraudsight status mapped to internal status (PASS, REVIEW, or FAIL). | getStatus(): ?int | setStatus(?int status): void |
| `txn` | `?string` | Optional | The identifier of the Txn that Fraudsight rules were run on. | getTxn(): ?string | setTxn(?string txn): void |
| `originalStatus` | `?string` | Optional | The raw value of the status returned from Fraudsight. | getOriginalStatus(): ?string | setOriginalStatus(?string originalStatus): void |
| `score` | `?int` | Optional | The score returned from Fraudsight, 0-1000. | getScore(): ?int | setScore(?int score): void |

## Example (as JSON)

```json
{
  "id": "id0",
  "created": "created0",
  "modified": "modified2",
  "creator": "String9",
  "modifier": "modifier6"
}
```

