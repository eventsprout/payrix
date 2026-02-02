
# Orgs Put Request

## Structure

`OrgsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `?string` | Optional | The Login that owns this Org. | getLogin(): ?string | setLogin(?string login): void |
| `name` | `?string` | Optional | The name of this Org.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Org.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |

## Example (as JSON)

```json
{
  "login": "t1_log_656d51cd565edf13a27c494",
  "name": "Leora44",
  "description": "description of Org"
}
```

