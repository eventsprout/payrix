
# Account Verification Response

## Structure

`AccountVerificationResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `account` | `?string` | Optional | The identifier of the Account that you want to verify. | getAccount(): ?string | setAccount(?string account): void |
| `type` | [`?string(AccountVerificationTypeEnum)`](../../doc/models/account-verification-type-enum.md) | Optional | The type of an account verification you want to perform.<br><br><details><br><summary>Valid Values</summary><br>- `debit` - **Makes two challenge debits (debit1 and debit2).**<br>- `credentials` - **Uses a bank account credential (username/password).**<br></details><br> | getType(): ?string | setType(?string type): void |
| `debit1` | `?int` | Optional | The first verification amount debited in cents. | getDebit1(): ?int | setDebit1(?int debit1): void |
| `debit2` | `?int` | Optional | The second verification amount debited in cents. | getDebit2(): ?int | setDebit2(?int debit2): void |
| `trials` | `?int` | Optional | The number of verification challenge responses attempted. | getTrials(): ?int | setTrials(?int trials): void |
| `toaccount` | `?string` | Optional | Account that will be deposited with both amounts: debit1 and debit2. | getToaccount(): ?string | setToaccount(?string toaccount): void |

## Example (as JSON)

```json
{
  "id": "id6",
  "created": "created6",
  "modified": "modified6",
  "creator": "String5",
  "modifier": "modifier0"
}
```

