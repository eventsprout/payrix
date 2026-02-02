
# Messages Post Request

## Structure

`MessagesPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `messageThread` | `string` | Required | The identifier of the messageThreads that owns this Messages resource. | getMessageThread(): string | setMessageThread(string messageThread): void |
| `secure` | [`?int(MessagesSecureEnum)`](../../doc/models/messages-secure-enum.md) | Optional | Whether this resource is marked as secure.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Messages will protected in email notifications.**<br>- `1` - **Message will display entirely.**<br><br></details><br> | getSecure(): ?int | setSecure(?int secure): void |
| `read` | [`int(MessagesReadEnum)`](../../doc/models/messages-read-enum.md) | Required | Whether this resource is marked as read.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Message has not been read yet.**<br>- `1` - **Message has been read and a value.**<br><br></details><br> | getRead(): int | setRead(int read): void |
| `message` | `string` | Required | Free-form text for adding a message to a messageThread resource. | getMessage(): string | setMessage(string message): void |

## Example (as JSON)

```json
{
  "messageThread": "t1_mtd_10ca1fcf172a9ac47656a21",
  "secure": 1,
  "read": 0,
  "message": "This is a test message"
}
```

