
# Payment Post Request

## Structure

`PaymentPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `method` | [`?int(PaymentMethodEnum)`](../../doc/models/payment-method-enum.md) | Optional | The payment method for this Transaction. | getMethod(): ?int | setMethod(?int method): void |
| `number` | `?string` | Optional | For credit payment method, the card number of the credit card associated with this Transaction.<br>For eCheck payment method, the bank account number associated with this Transaction. | getNumber(): ?string | setNumber(?string number): void |
| `last4` | `?string` | Optional | - | getLast4(): ?string | setLast4(?string last4): void |
| `routing` | `?string` | Optional | The routing code for the eCheck or bank account payment associated with this Transaction. | getRouting(): ?string | setRouting(?string routing): void |
| `bin` | `?string` | Optional | - | getBin(): ?string | setBin(?string bin): void |
| `payment` | `?string` | Optional | - | getPayment(): ?string | setPayment(?string payment): void |
| `lastChecked` | `?string` | Optional | - | getLastChecked(): ?string | setLastChecked(?string lastChecked): void |
| `mask` | `?string` | Optional | - | getMask(): ?string | setMask(?string mask): void |
| `plaidConsumerAccount` | `?string` | Optional | - | getPlaidConsumerAccount(): ?string | setPlaidConsumerAccount(?string plaidConsumerAccount): void |

## Example (as JSON)

```json
{
  "method": 16,
  "number": "number4",
  "last4": "last42",
  "routing": "routing2",
  "bin": "bin6"
}
```

