
# Chargeback Message Post Request

## Structure

`ChargebackMessagePostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `chargeback` | `string` | Required | The identifier of the Chargeback resource that this chargebackMessage relates to. | getChargeback(): string | setChargeback(string chargeback): void |
| `date` | `?string` | Optional | The date of this chargebackMessage.<br>The date is specified as an eight digit string in YYYYMMDD format, for example, '20160120' for January 20, 2016. | getDate(): ?string | setDate(?string date): void |
| `type` | [`string(ChargebackMessageTypeEnum)`](../../doc/models/chargeback-message-type-enum.md) | Required | The type of this chargebackMessage.<br><br><details><br><summary>Valid Values</summary><br>- `assign` - **Assign the chargeback.**<br>- `notate` - **Add a note to the chargeback.**<br>- `acceptLiability` - **Accept Liability for the Chargeback amount.**<br>- `createPreArbitration` - **Create a pre-arbitration case.**<br>- `represent` - **Represent the chargeback.**<br>- `respond` - **Respond to the chargeback.**<br>- `requestArbitration` - **Request Arbitration. The Merchant wishes to enter arbitration to determine the outcome of the Chargeback.**<br>- `createArbitration` - **Create an arbitration case.**<br>- `requestPreArbitration` - **Request a pre-arbitration case.**<br>- `requestResolutionToPreArbitration` - **Request resolution to a pre-arbitration case.**<br>- `respondToDispute` - **Respond to a dispute.**<br>- `respondToPreArbitration` - **Respond to a pre-arbitration case.**<br>- `unaccept` - **Unaccept the chargeback.**<br></details><br> | getType(): string | setType(string type): void |
| `fromQueue` | `?string` | Optional | The fromQueue element that specifies the queue in which the chargeback resided prior to the performance of the specified activity. | getFromQueue(): ?string | setFromQueue(?string fromQueue): void |
| `toQueue` | `?string` | Optional | The toQueue element that specifies queue to which the chargeback moved after the performance of the specified activity. | getToQueue(): ?string | setToQueue(?string toQueue): void |
| `contact` | `?string` | Optional | The identifier of the Contact for this chargebackMessage. | getContact(): ?string | setContact(?string contact): void |
| `amount` | `?int` | Optional | The amount that this chargebackMessage corresponds to.<br>For example, if the 'type' is set to '3' (Accept Liability), then this amount indicates that the liability should be for this amount.<br>This field is specified as an integer in cents. | getAmount(): ?int | setAmount(?int amount): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The currency of the amount in this resource. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `note` | `?string` | Optional | A free-text note relating to this chargebackMessage. | getNote(): ?string | setNote(?string note): void |
| `status` | [`?string(ChargebackMessageStatusEnum)`](../../doc/models/chargeback-message-status-enum.md) | Optional | The current status of the Chargeback.<br><br><details><br><summary>Valid Values</summary><br>- `requested` - **The chargeback has been requested.**<br>- `processing` - **The chargeback is currently being processed.**<br>- `failed` - **The chargeback process has failed.**<br>- `denied` - **The chargeback has been denied.**<br>- `processed` - **The chargeback has been successfully processed.**<br></details><br>**Default**: `ChargebackMessageStatusEnum::REQUESTED`<br> | getStatus(): ?string | setStatus(?string status): void |
| `imported` | [`?int(ChargebackMessageImportedEnum)`](../../doc/models/chargeback-message-imported-enum.md) | Optional | Whether the chargeback message was imported.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not imported.**<br>- `1` - **Imported.**<br></details><br> | getImported(): ?int | setImported(?int imported): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "chargeback": "t1_chb_2c2443d86f1c94d3846f85b",
  "type": "respond",
  "status": "processed",
  "imported": 1,
  "date": "20190908",
  "fromQueue": "specifies queue",
  "toQueue": "specifies queue",
  "contact": "identifier of Contact",
  "amount": 1,
  "currency": "USD",
  "note": "Charge Merchant",
  "inactive": 0,
  "frozen": 0
}
```

