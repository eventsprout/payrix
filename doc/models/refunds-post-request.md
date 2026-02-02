
# Refunds Post Request

## Structure

`RefundsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entry` | `string` | Required | The identifier of the Entries resource that is being refunded. | getEntry(): string | setEntry(string entry): void |
| `description` | `?string` | Optional | A description of this Refund.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `amount` | `float` | Required | The amount of this Refund.<br>This field is specified in cents(up to three decimal points)<br>This field is optional. If it is not set, then the API uses the amount that is specified in the related Entry resource. | getAmount(): float | setAmount(float amount): void |

## Example (as JSON)

```json
{
  "entry": "t1_etr_6785d50e925b93e699f1234",
  "description": "Negative Tax Reimbursement",
  "amount": 248.0
}
```

