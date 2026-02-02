
# Chargeback Message Result Response

## Structure

`ChargebackMessageResultResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `chargebackMessage` | string\|[ChargebackMessageResponse](../../doc/models/chargeback-message-response.md)\|null | Optional | The identifier of the chargebackMessage resource that this chargebackMessageResult relates to. | getChargebackMessage(): | setChargebackMessage( chargebackMessage): void |
| `type` | [`?string(ChargebackMessageResultTypeEnum)`](../../doc/models/chargeback-message-result-type-enum.md) | Optional | The type of this chargebackMessageResult.<br><br><details><br><summary>Valid Values</summary><br>- `general` - **A general type of result.**<br>- `platform` - **Platform message.**<br></details><br> | getType(): ?string | setType(?string type): void |
| `message` | `?string` | Optional | The Chargeback message itself. | getMessage(): ?string | setMessage(?string message): void |

## Example (as JSON)

```json
{
  "id": "id6",
  "created": "created6",
  "modified": "modified4",
  "creator": "String5",
  "modifier": "modifier0"
}
```

