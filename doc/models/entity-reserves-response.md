
# Entity Reserves Response

## Structure

`EntityReservesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The Login that owns this resource. | getLogin(): | setLogin( login): void |
| `fund` | string\|[FundsResponse](../../doc/models/funds-response.md)\|null | Optional | The identifier of the Fund that this entityReserves resource relates to. | getFund(): | setFund( fund): void |
| `total` | `?int` | Optional | The amount held in this entityReserve.<br>This field is specified as an integer in cents. | getTotal(): ?int | setTotal(?int total): void |
| `requestSequence` | `?int` | Optional | The current sequentially numbered activity requested for this entityReserve. | getRequestSequence(): ?int | setRequestSequence(?int requestSequence): void |
| `processedSequence` | `?int` | Optional | The current sequentially numbered activity processed for this entityReserve. | getProcessedSequence(): ?int | setProcessedSequence(?int processedSequence): void |
| `name` | `?string` | Optional | The name of this EntityReserve.<br>This field is stored as a text string and must be between 0 and 50 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this EntityReserve.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `reserveEntries` | [`?(ReserveEntriesResponse[])`](../../doc/models/reserve-entries-response.md) | Optional | - | getReserveEntries(): ?array | setReserveEntries(?array reserveEntries): void |

## Example (as JSON)

```json
{
  "id": "id4",
  "created": "created4",
  "modified": "modified8",
  "creator": "String3",
  "modifier": "modifier2"
}
```

