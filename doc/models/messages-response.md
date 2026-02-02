
# Messages Response

## Structure

`MessagesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `messageThread` | string\|[MessageThreadsResponse](../../doc/models/message-threads-response.md)\|null | Optional | The identifier of the messageThreads that owns this Messages resource. | getMessageThread(): | setMessageThread( messageThread): void |
| `opposingMessage` | string\|[MessagesResponse](../../doc/models/messages-response.md)\|null | Optional | Specifies whether this is the opposingMessage or not. | getOpposingMessage(): | setOpposingMessage( opposingMessage): void |
| `type` | [`?string(MessageTypeEnum)`](../../doc/models/message-type-enum.md) | Optional | Whether this resource is incoming or outgoing.<br><br><details><br><summary>Valid Values</summary><br>- `incoming` - **Incoming messages is assigned.**<br>- `outgoing` - **Outgoing message is assigned.**<br>  <br>  </details><br> | getType(): ?string | setType(?string type): void |
| `generated` | [`?int(MessagesGeneratedEnum)`](../../doc/models/messages-generated-enum.md) | Optional | Whether this resource was automatically generated or not.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Message was automatically generated and a value of '0' means it was manually generated.**<br>- `1` - **Message was manually generated.**<br>  <br>  </details><br> | getGenerated(): ?int | setGenerated(?int generated): void |
| `secure` | [`?int(MessagesSecureEnum)`](../../doc/models/messages-secure-enum.md) | Optional | Whether this resource is marked as secure.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Messages will protected in email notifications.**<br>- `1` - **Message will display entirely.**<br><br></details><br> | getSecure(): ?int | setSecure(?int secure): void |
| `read` | [`?int(MessagesReadEnum)`](../../doc/models/messages-read-enum.md) | Optional | Whether this resource is marked as read.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Message has not been read yet.**<br>- `1` - **Message has been read and a value.**<br><br></details><br> | getRead(): ?int | setRead(?int read): void |
| `message` | `?string` | Optional | Free-form text for adding a message to a messageThread resource. | getMessage(): ?string | setMessage(?string message): void |
| `opposingMessages` | [`?MessagesResponse`](../../doc/models/messages-response.md) | Optional | - | getOpposingMessages(): ?MessagesResponse | setOpposingMessages(?MessagesResponse opposingMessages): void |

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

