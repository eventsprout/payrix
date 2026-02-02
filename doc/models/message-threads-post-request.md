
# Message Threads Post Request

## Structure

`MessageThreadsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `string` | Required | The identifier of the Login that owns this messageThreads resource. | getLogin(): string | setLogin(string login): void |
| `forlogin` | `?string` | Optional | The identifier of the receiving Login of this messageThreads resource. | getForlogin(): ?string | setForlogin(?string forlogin): void |
| `hold` | `?string` | Optional | The identifier of the Hold that is related to this messageThread. | getHold(): ?string | setHold(?string hold): void |
| `entityReturn` | `?string` | Optional | This field has the ID from the EntityReturns table that hold ACH returns for disbursements or eCheck txns. | getEntityReturn(): ?string | setEntityReturn(?string entityReturn): void |
| `opposingMessageThread` | `?string` | Optional | Specifies whether this is the opposing MessageThread. | getOpposingMessageThread(): ?string | setOpposingMessageThread(?string opposingMessageThread): void |
| `folder` | `?string` | Optional | Free-form text. By default, a messageThread resource is set as 'default'.<br><br>**Default**: `'default'` | getFolder(): ?string | setFolder(?string folder): void |
| `sender` | `string` | Required | Free-form text that represents the name of the sender of a messageThread resource. | getSender(): string | setSender(string sender): void |
| `recipient` | `string` | Required | Free-form text that represents the name of the recipient of a messageThread resource. | getRecipient(): string | setRecipient(string recipient): void |
| `subject` | `string` | Required | Free-form text for adding a subject to a messageThread resource. | getSubject(): string | setSubject(string subject): void |
| `messages` | [`?(MessagesPostRequest[])`](../../doc/models/messages-post-request.md) | Optional | - | getMessages(): ?array | setMessages(?array messages): void |

## Example (as JSON)

```json
{
  "login": "t1_mtd_67ef5bad402b6b61e701e0z",
  "forlogin": "t1_log_61e9b7302360fbf12999d63",
  "hold": "t1_hld_67ef5bad3be038935902204",
  "entityReturn": "entityReturn",
  "opposingMessageThread": "t1_mtd_67ef5bad40f7e68822ac0c7",
  "folder": "default",
  "sender": "testnewmerchant",
  "recipient": "testnewmerchant1",
  "subject": "Transaction was put on hold"
}
```

