
# Entity Reserves Put Request

## Structure

`EntityReservesPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `total` | `?int` | Optional | The amount held in this entityReserve.<br>This field is specified as an integer in cents. | getTotal(): ?int | setTotal(?int total): void |
| `name` | `?string` | Optional | The name of this EntityReserve.<br>This field is stored as a text string and must be between 0 and 50 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this EntityReserve.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |

## Example (as JSON)

```json
{
  "total": 0,
  "name": "EntityReserve1",
  "description": "EntityReserve"
}
```

