
# Messages Put Request

## Structure

`MessagesPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `read` | [`?int(MessagesReadEnum)`](../../doc/models/messages-read-enum.md) | Optional | Whether this resource is marked as read.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Message has not been read yet.**<br>- `1` - **Message has been read and a value.**<br><br></details><br> | getRead(): ?int | setRead(?int read): void |

## Example (as JSON)

```json
{
  "read": 1
}
```

