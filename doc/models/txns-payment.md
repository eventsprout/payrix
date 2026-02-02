
# Txns Payment

The payment method associated with this Transaction, including the card details.

## Structure

`TxnsPayment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `method` | [`int(TxnPaymentMethodEnum)`](../../doc/models/txn-payment-method-enum.md) | Required | The payment method for this Transaction. | getMethod(): int | setMethod(int method): void |
| `number` | `string` | Required | For credit payment method, the card number of the credit card associated with this Transaction.<br>For eCheck payment method, the bank account number associated with this Transaction. | getNumber(): string | setNumber(string number): void |
| `routing` | `?string` | Optional | The routing code for the eCheck or bank account payment associated with this Transaction. | getRouting(): ?string | setRouting(?string routing): void |
| `expiration` | `?string` | Optional | The expiration date of the credit card associated with this Transaction.<br>This field is stored as a text string in 'MMYY' format, where 'MM' is the number of a month and 'YY' is the last two digits of a year. For example, '0623' for June 2023. | getExpiration(): ?string | setExpiration(?string expiration): void |
| `cvv` | `?string` | Optional | The Card Verification Value (CVV) number of the credit card associated with this Transaction.<br>This field is expressed as an integer.<br><br>**Default**: `'0'` | getCvv(): ?string | setCvv(?string cvv): void |
| `track` | `?array` | Optional | The 'Track' data (either Track 1, Track 2, or both) of the card associated with this Transaction.<br>This field is stored as a text string. | getTrack(): ?array | setTrack(?array track): void |

## Example (as JSON)

```json
{
  "method": 15,
  "number": "number4",
  "cvv": "0",
  "routing": "routing2",
  "expiration": "expiration0",
  "track": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

