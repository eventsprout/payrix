
# Verifications Response

## Structure

`VerificationsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | `?string` | Optional | The Login that owns this resource. | getLogin(): ?string | setLogin(?string login): void |
| `entity` | `?string` | Optional | The identifier of the Entity that you want to verify. | getEntity(): ?string | setEntity(?string entity): void |
| `member` | `?string` | Optional | The identifier of the Member that you want to verify. | getMember(): ?string | setMember(?string member): void |
| `txn` | `?string` | Optional | The Txn id in which this Verification belongs to. | getTxn(): ?string | setTxn(?string txn): void |
| `terminalTxn` | `?string` | Optional | The TerminalTxn id in which this Verification belongs to. | getTerminalTxn(): ?string | setTerminalTxn(?string terminalTxn): void |
| `account` | `?string` | Optional | The Account id in which this Verification belongs to. | getAccount(): ?string | setAccount(?string account): void |
| `decision` | `?string` | Optional | Used to link multiple decisions together. | getDecision(): ?string | setDecision(?string decision): void |
| `type` | [`?string(VerificationTypeEnum)`](../../doc/models/verification-type-enum.md) | Optional | The type of check to perform on the Entity, Member or Txn.<br><br><details><br>  <summary>Entity Types - Valid Values</summary><br>  <ul><br>    <li>`advancedEntity` - <b>Advanced Entity Verification</b></li><br>    <li>`ofac` - <b>OFAC Watchlist Verification</b></li><br>    <li>`entity` - <b>Entity Verification</b></li><br>    <li>`overall` - <b>Overall Entity Verification</b></li><br>    <li>`watchlist` - <b>Watchlist Verification</b></li><br>    <li>`dataVerification` - <b>Data Verification</b></li><br>    <li>`advancedMerchant` - <b>Advanced Merchant Verification</b></li><br>  </ul><br></details><br><details><br>  <summary>Member Types - Valid Values</summary><br>  <ul><br>    <li>`advancedMember` - <b>Advanced Member Verification</b></li><br>    <li>`association` - <b>Association Verification</b></li><br>    <li>`member` - <b>Member Verification</b></li><br>    <li>`ofac` - <b>OFAC Watchlist Verification</b></li><br>    <li>`watchlist` - <b>Watchlist Verification</b></li><br>  </ul><br></details><br><details><br>  <summary>Transaction Types - Valid Values</summary><br>  <ul><br>    <li>`merchantFailureLimit` - <b>Merchant Failure Limit</b></li><br>    <li>`merchantPaymentFailureLimit` - <b>Merchant Payment Failure Limit</b></li><br>    <li>`saleTotalLimit` - <b>Sale Total Limit</b></li><br>    <li>`saleTotalMinimum` - <b>Sale Total Minimum</b></li><br>    <li>`merchantCaptureWithoutAuthLimit` - <b>Merchant Capture Without Auth Limit</b></li><br>    <li>`refundTotalLimit` - <b>Refund Total Limit</b></li><br>    <li>`averageSaleCountLimit` - <b>Average Sale Count Limit</b></li><br>    <li>`merchantRefundSaleRatio` - <b>Merchant Refund Sale Ratio</b></li><br>    <li>`merchantPaymentSuccessLimit` - <b>Merchant Payment Success Limit</b></li><br>    <li>`ipFailureLimit` - <b>IP Failure Limit</b></li><br>    <li>`ipFailureRatio` - <b>IP Failure Ratio</b></li><br>    <li>`inactiveMerchant` - <b>Inactive Merchant</b></li><br>    <li>`refundWithoutSale` - <b>Refund Without Sale</b></li><br>    <li>`refundWithoutSaleLimit` - <b>Refund Without Sale Limit</b></li><br>    <li>`captureAboveAuthLimit` - <b>Capture Above Auth Limit</b></li><br>    <li>`cvv` - <b>CVV Verification</b></li><br>    <li>`avs` - <b>AVS Verification</b></li><br>    <li>`aavs` - <b>AAVS Verification</b></li><br>    <li>`duplicateTxn` - <b>Duplicate Transaction</b></li><br>    <li>`merchantMatch` - <b>Merchant Match</b></li><br>    <li>`currencyConversion` - <b>Currency Conversion</b></li><br>    <li>`settledCurrencyMismatch` - <b>Settled Currency Mismatch</b></li><br>    <li>`initialTxn` - <b>Initial Transaction</b></li><br>    <li>`similarTotalLimit` - <b>Similar Total Limit</b></li><br>    <li>`similarTotalRatio` - <b>Similar Total Ratio</b></li><br>    <li>`limit` - <b>Limit</b></li><br>    <li>`ratio` - <b>Ratio</b></li><br>    <li>`txnWatchlist` - <b>Transaction Watchlist</b></li><br>    <li>`balanceRefundLimit` - <b>Balance Refund Limit</b></li><br>    <li>`saleApprovedLimit` - <b>Sale Approved Limit</b></li><br>    <li>`refundApprovedLimit` - <b>Refund Approved Limit</b></li><br>  </ul><br></details><br> | getType(): ?string | setType(?string type): void |
| `fromCache` | `?string` | Optional | Whether this verification was created from cache. The format should be YYYY-MM-DD HH:MM:SS.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getFromCache(): ?string | setFromCache(?string fromCache): void |
| `options` | `?int` | Optional | The Options for this Verification. | getOptions(): ?int | setOptions(?int options): void |
| `additionalOptions` | `?int` | Optional | The Additional Options for this Verification. | getAdditionalOptions(): ?int | setAdditionalOptions(?int additionalOptions): void |
| `level` | `?string` | Optional | Level conditions. | getLevel(): ?string | setLevel(?string level): void |
| `value` | `?string` | Optional | The value for this Verification. This is used to associate a Verification to a Watchlist for Watchlist Verifications. | getValue(): ?string | setValue(?string value): void |
| `score` | `?int` | Optional | The score for this Verification.<br>This field is specified as an integer between 0 and 100. | getScore(): ?int | setScore(?int score): void |
| `description` | `?string` | Optional | Description of the verification. | getDescription(): ?string | setDescription(?string description): void |
| `ref` | `?string` | Optional | The reference number for this verification. | getRef(): ?string | setRef(?string ref): void |
| `generated` | [`?int(VerificationsGeneratedEnum)`](../../doc/models/verifications-generated-enum.md) | Optional | <details><br><summary>Valid Values</summary> <br>- `0` - **OFF**<br>- `1` - **ON**<br><br> </details><br>**Default**: `VerificationsGeneratedEnum::OFF`<br> | getGenerated(): ?int | setGenerated(?int generated): void |

## Example (as JSON)

```json
{
  "generated": 0,
  "id": "id4",
  "created": "created4",
  "modified": "modified2",
  "creator": "String3",
  "modifier": "modifier8"
}
```

