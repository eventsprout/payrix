
# Message Threads Response

## Structure

`MessageThreadsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that owns this messageThreads resource. | getLogin(): | setLogin( login): void |
| `forlogin` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the receiving Login of this messageThreads resource. | getForlogin(): | setForlogin( forlogin): void |
| `hold` | string\|[HoldsResponse](../../doc/models/holds-response.md)\|null | Optional | The identifier of the Hold that is related to this messageThread. | getHold(): | setHold( hold): void |
| `entityReturn` | string\|[EntityReturnsResponse](../../doc/models/entity-returns-response.md)\|null | Optional | The identifier of the EntityReturn that is related to this messageThread. | getEntityReturn(): | setEntityReturn( entityReturn): void |
| `opposingMessageThreads` | [`?MessageThreadsResponse`](../../doc/models/message-threads-response.md) | Optional | - | getOpposingMessageThreads(): ?MessageThreadsResponse | setOpposingMessageThreads(?MessageThreadsResponse opposingMessageThreads): void |
| `folder` | `?string` | Optional | Free-form text. By default, a messageThread resource is set as 'default'. | getFolder(): ?string | setFolder(?string folder): void |
| `sender` | `?string` | Optional | Free-form text that represents the name of the sender of a messageThread resource. | getSender(): ?string | setSender(?string sender): void |
| `recipient` | `?string` | Optional | Free-form text that represents the name of the recipient of a messageThread resource. | getRecipient(): ?string | setRecipient(?string recipient): void |
| `subject` | `?string` | Optional | Free-form text for adding a subject to a messageThread resource. | getSubject(): ?string | setSubject(?string subject): void |
| `messages` | [`?(MessagesResponse[])`](../../doc/models/messages-response.md) | Optional | - | getMessages(): ?array | setMessages(?array messages): void |
| `opposingMessageThread` | string\|[MessageThreadsResponse](../../doc/models/message-threads-response.md)\|null | Optional | Specifies whether this is the opposing MessageThread. | getOpposingMessageThread(): | setOpposingMessageThread( opposingMessageThread): void |

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

