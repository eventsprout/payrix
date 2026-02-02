
# Chargebacks Response

## Structure

`ChargebacksResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `merchant` | string\|[MerchantsResponse](../../doc/models/merchants-response.md)\|null | Optional | The ID of the merchant associated with the Chargeback. | getMerchant(): | setMerchant( merchant): void |
| `txn` | string\|[TxnsResponse](../../doc/models/txns-response.md)\|null | Optional | The ID of the Transaction associated with the Chargeback. | getTxn(): | setTxn( txn): void |
| `mid` | `?string` | Optional | The Merchant's processing MID. | getMid(): ?string | setMid(?string mid): void |
| `description` | `?string` | Optional | Description of the chargeback. | getDescription(): ?string | setDescription(?string description): void |
| `total` | `?int` | Optional | The total amount of the Chargeback. | getTotal(): ?int | setTotal(?int total): void |
| `representedTotal` | `?int` | Optional | The representedTotal for this Chargeback if it has been represented. | getRepresentedTotal(): ?int | setRepresentedTotal(?int representedTotal): void |
| `cycle` | [`?string(CycleEnum)`](../../doc/models/cycle-enum.md) | Optional | <details><summary>Valid Values</summary><br>- `retrieval` - **Initial request from the issuer for more information on this Transaction.**<br>- `first` - **First Chargeback from issuer for this Transaction.**<br><br>- `arbitration` - **Arbitration is being sought for this Chargeback.**<br><br>- `reversal` - **Chargeback was reversed.**<br><br>- `representment` - **Merchant is being represented to the issuer with the Chargeback response posted.**<br><br>- `preArbitration` - **Chargeback is no longer representable. Merchant must choose to accept or arbitrate with the card brand.**<br><br>- `arbitrationLost` - **Arbitration lost.**<br><br>- `arbitrationSplit` - **Arbitration split.**<br><br>- `arbitrationWon` - **Arbitration won.**<br><br>- `issuerAcceptPreArbitration` - **Issuer accepted the pre-arbitration response.**<br><br>- `issuerDeclinedPreArbitration` - **Issuer declined pre-arbitration.**<br><br>- `responseToIssuerPreArbitration` - **Response to issuer pre-arbitration.**<br><br>- `merchantAcceptedPreArbitration` - **Merchant accepted the pre-arbitration response.**<br><br>- `merchantDeclinedPreArbitration` - **Merchant declined the pre-arbitration response.**<br><br>- `preCompliance` - **Pre-compliance.**<br><br>- `compliance` - **Compliance.** </details> | getCycle(): ?string | setCycle(?string cycle): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The currency for this statement. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `platform` | [`?string(ChargebackPlatformEnum)`](../../doc/models/chargeback-platform-enum.md) | Optional | The platform used for the adjustment. This field is required if the adjustment is not between entities. | getPlatform(): ?string | setPlatform(?string platform): void |
| `paymentMethod` | [`?int(ChargebackPaymentMethodEnum)`](../../doc/models/chargeback-payment-method-enum.md) | Optional | The type of payment method used for the transaction.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **No payment method specified.**<br>- `1` - **American Express.**<br>- `2` - **Visa.**<br>- `3` - **MasterCard.**<br>- `4` - **Diners Club.**<br>- `5` - **Discover.**<br>- `6` - **PayPal.**<br>- `7` - **Debit card.**<br>- `8` - **Checking account.**<br>- `9` - **Savings account.**<br>- `10` - **Corporate checking account.**<br>- `11` - **Corporate savings account.**<br>- `12` - **Gift card.**<br>- `13` - **EBT card.**<br>- `14` - **WIC card.**<br></details><br> | getPaymentMethod(): ?int | setPaymentMethod(?int paymentMethod): void |
| `ref` | `?string` | Optional | The processing reference number for this Chargeback. | getRef(): ?string | setRef(?string ref): void |
| `reason` | `?string` | Optional | The reason description for this Chargeback. | getReason(): ?string | setReason(?string reason): void |
| `reasonCode` | `?string` | Optional | The reason code for this Chargeback. | getReasonCode(): ?string | setReasonCode(?string reasonCode): void |
| `issued` | `?int` | Optional | The date when the Chargeback was issued. | getIssued(): ?int | setIssued(?int issued): void |
| `received` | `?int` | Optional | The date when the Chargeback was received. | getReceived(): ?int | setReceived(?int received): void |
| `reply` | `?int` | Optional | The deadline to submit a reply for the Chargeback. | getReply(): ?int | setReply(?int reply): void |
| `bankRef` | `?string` | Optional | The issuing bank's reference number for this Chargeback. | getBankRef(): ?string | setBankRef(?string bankRef): void |
| `chargebackRef` | `?string` | Optional | Chargeback reference number. | getChargebackRef(): ?string | setChargebackRef(?string chargebackRef): void |
| `status` | [`?string(ChargebackStatusEnum)`](../../doc/models/chargeback-status-enum.md) | Optional | The Chargeback's status.<br><br><details><br><summary>Valid Values</summary><br>- `open` - **Chargeback is open, responses may be submitted.**<br>- `closed` - **Chargeback is closed, responses may no longer be submitted.**<br>- `won` - **Chargeback won.**<br>- `lost` - **Chargeback lost.**<br></details><br>**Default**: `ChargebackStatusEnum::OPEN`<br> | getStatus(): ?string | setStatus(?string status): void |
| `lastStatusChange` | string\|[ChargebackStatusesResponse](../../doc/models/chargeback-statuses-response.md)\|null | Optional | The ChargebackStatus representing the latest status change for this Chargeback. | getLastStatusChange(): | setLastStatusChange( lastStatusChange): void |
| `actionable` | [`?int(ChargebacksActionableEnum)`](../../doc/models/chargebacks-actionable-enum.md) | Optional | Whether the Chargeback is actionable and can be responded to.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not actionable**<br>- `1` - **Actionable**<br><br></details><br> | getActionable(): ?int | setActionable(?int actionable): void |
| `shadow` | [`?int(ChargebacksShadowEnum)`](../../doc/models/chargebacks-shadow-enum.md) | Optional | <details><br><summary>Valid Values</summary><br>- `0` - **Not shadowed.**<br>- `1` - **Shadowed.**<br><br></details><br> | getShadow(): ?int | setShadow(?int shadow): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `assessments` | [`?(AssessmentsResponse[])`](../../doc/models/assessments-response.md) | Optional | - | getAssessments(): ?array | setAssessments(?array assessments): void |
| `chargebackDocuments` | [`?(ChargebackDocumentsResponse[])`](../../doc/models/chargeback-documents-response.md) | Optional | - | getChargebackDocuments(): ?array | setChargebackDocuments(?array chargebackDocuments): void |
| `chargebackMessages` | [`?(ChargebackMessageResponse[])`](../../doc/models/chargeback-message-response.md) | Optional | - | getChargebackMessages(): ?array | setChargebackMessages(?array chargebackMessages): void |
| `chargebackStatuses` | [`?(ChargebackStatusesResponse[])`](../../doc/models/chargeback-statuses-response.md) | Optional | - | getChargebackStatuses(): ?array | setChargebackStatuses(?array chargebackStatuses): void |
| `entries` | [`?(EntriesResponse[])`](../../doc/models/entries-response.md) | Optional | - | getEntries(): ?array | setEntries(?array entries): void |
| `pendingEntry` | [`?PendingEntriesResponse`](../../doc/models/pending-entries-response.md) | Optional | - | getPendingEntry(): ?PendingEntriesResponse | setPendingEntry(?PendingEntriesResponse pendingEntry): void |

## Example (as JSON)

```json
{
  "currency": "USD",
  "platform": "VCORE",
  "status": "open",
  "inactive": 0,
  "frozen": 0,
  "id": "id2",
  "created": "created2",
  "modified": "modified0",
  "creator": "String1",
  "modifier": "modifier6"
}
```

