
# Chargeback Statuses Response

## Structure

`ChargebackStatusesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `chargeback` | string\|[ChargebacksResponse](../../doc/models/chargebacks-response.md)\|null | Optional | ID of the related chargeback. | getChargeback(): | setChargeback( chargeback): void |
| `chargebackMessage` | string\|[ChargebackMessageResponse](../../doc/models/chargeback-message-response.md)\|null | Optional | ID of the chargeback message associated with this chargeback. | getChargebackMessage(): | setChargebackMessage( chargebackMessage): void |
| `status` | [`?string(ChargebackStatusesStatusEnum)`](../../doc/models/chargeback-statuses-status-enum.md) | Optional | The Chargeback's status. <details><summary>Valid Values</summary><br><br>- `open` - **Chargeback is open, responses may be submitted.**<br><br>- `closed` - **Chargeback is closed, responses may no longer be submitted.**<br><br>- `won` - **Chargeback won.**<br><br>- `lost` - **Chargeback lost.**<br><br> </details><br>**Default**: `ChargebackStatusesStatusEnum::OPEN`<br> | getStatus(): ?string | setStatus(?string status): void |

## Example (as JSON)

```json
{
  "status": "open",
  "id": "id4",
  "created": "created4",
  "modified": "modified8",
  "creator": "String3",
  "modifier": "modifier2"
}
```

