
# Refunds Response

## Structure

`RefundsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `entry` | string\|[EntriesResponse](../../doc/models/entries-response.md)\|null | Optional | The identifier of the Entries resource that is being refunded. | getEntry(): | setEntry( entry): void |
| `description` | `?string` | Optional | A description of this Refund.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `amount` | `?float` | Optional | The amount of this Refund.<br>This field is specified in cents(up to three decimal points).<br>This field is optional. If it is not set, then the API uses the amount that is specified in the related Entry resource. | getAmount(): ?float | setAmount(?float amount): void |
| `entries` | [`?EntriesResponse`](../../doc/models/entries-response.md) | Optional | - | getEntries(): ?EntriesResponse | setEntries(?EntriesResponse entries): void |
| `pendingEntries` | [`?PendingEntriesResponse`](../../doc/models/pending-entries-response.md) | Optional | - | getPendingEntries(): ?PendingEntriesResponse | setPendingEntries(?PendingEntriesResponse pendingEntries): void |

## Example (as JSON)

```json
{
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier6"
}
```

