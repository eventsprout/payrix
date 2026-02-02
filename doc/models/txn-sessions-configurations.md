
# Txn Sessions Configurations

Configurable data to be used to enhance security.

## Structure

`TxnSessionsConfigurations`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `duration` | `?int` | Optional | duration refers to How many minutes this key should live (automated voided when tried to use after expired). | getDuration(): ?int | setDuration(?int duration): void |
| `maxTimesApproved` | `?int` | Optional | maxTimesApproved refers to how many approved transactions related it can be used. | getMaxTimesApproved(): ?int | setMaxTimesApproved(?int maxTimesApproved): void |
| `maxTimesUse` | `?int` | Optional | maxTimesUse refers to how many times we can make request with this key. | getMaxTimesUse(): ?int | setMaxTimesUse(?int maxTimesUse): void |

## Example (as JSON)

```json
{
  "duration": 112,
  "maxTimesApproved": 32,
  "maxTimesUse": 34
}
```

