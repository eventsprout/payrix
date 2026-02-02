
# Profit Share Results Response

## Structure

`ProfitShareResultsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `profitShare` | string\|[ProfitSharesResponse](../../doc/models/profit-shares-response.md)\|null | Optional | The identifier of the ProfitShare that this ProfitShareResult refers to. | getProfitShare(): | setProfitShare( profitShare): void |
| `entry` | string\|[EntriesResponse](../../doc/models/entries-response.md)\|null | Optional | The identifier of the Entry that this ProfitShareResult refers to. | getEntry(): | setEntry( entry): void |
| `amount` | `?float` | Optional | The amount that could not be shared between entities, This field is specified in cents(up to three decimal points) | getAmount(): ?float | setAmount(?float amount): void |
| `message` | `?string` | Optional | A message regarding the failure of the ProfitShare process.<br>This field is stored as a text string and must be between 0 and 200 characters long. | getMessage(): ?string | setMessage(?string message): void |

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

