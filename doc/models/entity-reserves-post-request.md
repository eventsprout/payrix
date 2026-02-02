
# Entity Reserves Post Request

## Structure

`EntityReservesPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `string` | Required | The Login that owns this resource. | getLogin(): string | setLogin(string login): void |
| `fund` | `string` | Required | The identifier of the Fund that this entityReserves resource relates to. | getFund(): string | setFund(string fund): void |
| `total` | `int` | Required | The amount held in this entityReserve.<br>This field is specified as an integer in cents. | getTotal(): int | setTotal(int total): void |
| `name` | `?string` | Optional | The name of this EntityReserve.<br>This field is stored as a text string and must be between 0 and 50 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this EntityReserve.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |

## Example (as JSON)

```json
{
  "login": "t1_log_5f2d5e3e67a6fb5b3521361",
  "fund": "t1_fun_5f20126254c14a171b8d2d0",
  "total": 0,
  "name": "EntityReserve1",
  "description": "EntityReserve"
}
```

