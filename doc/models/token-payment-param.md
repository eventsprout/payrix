
# Token Payment Param

The payment method that is associated with this Token.

## Structure

`TokenPaymentParam`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `method` | [`?int(TokenPaymentMethodEnum)`](../../doc/models/token-payment-method-enum.md) | Optional | The method used to make this payment.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **American Express**<br>- `2` - **Visa**<br>- `3` - **MasterCard**<br>- `4` - **Diners Club**<br>- `5` - **Discover**<br>- `6` - **PayPal**<br>- `7` - **Debit Card**<br>- `8` - **Checking Account**<br>- `9` - **Savings Account**<br>- `10` - **Corporate Checking Account**<br>- `11` - **Corporate Savings Account**<br>- `12` - **Gift Card**<br>- `13` - **EBT (Electronic Benefits Transfer) Card**<br>- `14` - **WIC (Women, Infants and Children) Card**<br>- `15` - **Accel**<br>- `16` - **ATH**<br>- `17` - **AFFN**<br>- `18` - **Culiance**<br>- `19` - **Interlink**<br>- `20` - **Jeanie**<br>- `21` - **Maestro**<br>- `22` - **NYCE**<br>- `23` - **Pulse**<br>- `24` - **Shazam**<br>- `25` - **Star**<br>- `26` - **Interac**<br>- `27` - **OmniToken**<br></details><br> | getMethod(): ?int | setMethod(?int method): void |
| `number` | `?string` | Optional | For credit payment method, the card number of the credit card associated with this Token.<br>For eCheck payment method, the bank account number associated with this Token. | getNumber(): ?string | setNumber(?string number): void |
| `routing` | `?string` | Optional | If the payment method associated with this Token is a bank account, then this field contains the routing code for the bank account. | getRouting(): ?string | setRouting(?string routing): void |

## Example (as JSON)

```json
{
  "method": 1,
  "number": "number0",
  "routing": "routing8"
}
```

