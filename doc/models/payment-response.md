
# Payment Response

## Structure

`PaymentResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `method` | [`?int(PaymentMethodEnum)`](../../doc/models/payment-method-enum.md) | Optional | The payment method for this Transaction. | getMethod(): ?int | setMethod(?int method): void |
| `number` | `?string` | Optional | For credit payment method, the card number of the credit card associated with this Transaction.<br>For eCheck payment method, the bank account number associated with this Transaction. | getNumber(): ?string | setNumber(?string number): void |
| `routing` | `?string` | Optional | The routing code for the eCheck or bank account payment associated with this Transaction. | getRouting(): ?string | setRouting(?string routing): void |
| `bin` | string\|[BinsResponse](../../doc/models/bins-response.md)\|null | Optional | Bin identifier for this payment. | getBin(): | setBin( bin): void |
| `payment` | `?string` | Optional | - | getPayment(): ?string | setPayment(?string payment): void |
| `lastChecked` | `?string` | Optional | Times timestamp with last time payment was checked. | getLastChecked(): ?string | setLastChecked(?string lastChecked): void |
| `last4` | `?string` | Optional | - | getLast4(): ?string | setLast4(?string last4): void |
| `mask` | `?string` | Optional | - | getMask(): ?string | setMask(?string mask): void |
| `plaidConsumerAccount` | `?string` | Optional | - | getPlaidConsumerAccount(): ?string | setPlaidConsumerAccount(?string plaidConsumerAccount): void |

## Example (as JSON)

```json
{
  "id": "id8",
  "method": 0,
  "number": "number4",
  "routing": "routing4",
  "bin": "String9"
}
```

