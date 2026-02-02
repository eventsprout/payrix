
# Decisions Put Request

## Structure

`DecisionsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `?string` | Optional | The identifier of the Login that owns this decisions resource. | getLogin(): ?string | setLogin(?string login): void |
| `org` | `?string` | Optional | If this decision resource relates to an Org, then this field stores the identifier of the Org. | getOrg(): ?string | setOrg(?string org): void |
| `entity` | `?string` | Optional | If this decision resource relates to an Entity, then this field stores the identifier of the Entity. | getEntity(): ?string | setEntity(?string entity): void |
| `decision` | `?string` | Optional | The identifier of a linked decision resource that acts in coordination with this decision. When you define a decision attribute here, the referenced decision becomes the 'parent' resource. The action field set on the 'parent' resource determines the action that occurs if all of the linked decisions fail. | getDecision(): ?string | setDecision(?string decision): void |
| `division` | `?string` | Optional | Identifier of the division to which the decision resource belongs. | getDivision(): ?string | setDivision(?string division): void |
| `partition` | `?string` | Optional | Identifier of the partition to which the decision resource belongs. | getPartition(): ?string | setPartition(?string partition): void |
| `application` | [`?string(DecisionActionsApplicationEnum)`](../../doc/models/decision-actions-application-enum.md) | Optional | Where the action defined by this DecisionAction should apply.<br><br><details><br><summary>Valid Values</summary><br>- `account` - **Account type Decision.**<br>- `txn` - **Txn type Decision.**<br>- `entity` - **Entity type Decision.**<br></details><br> | getApplication(): ?string | setApplication(?string application): void |
| `level` | `?string` | Optional | The levels of decision admin, merchant, division, partition. | getLevel(): ?string | setLevel(?string level): void |
| `type` | [`?string(DecisionTypeEnum)`](../../doc/models/decision-type-enum.md) | Optional | The type of check to perform.<br><br><details><br><summary>Valid Values</summary><br>- `merchantFailureLimit` - **Exceeded the maximum number of allowed failed authorizations.**<br>- `merchantFailureRatio` - **Exceeded the maximum ratio of allowed failed authorizations.**<br>- `saleTotalLimit` - **Exceeded the maximum allowed sale total value.**<br>- `refundTotalLimit` - **Exceeded the maximum allowed refund total value.**<br>- `averageSaleCountLimit` - **Exceeded the allowed maximum payment size (individual transaction amount).**<br>- `merchantRefundSaleRatio` - **Exceeded the maximum allowed ratio of refunds to sales.**<br>- `merchantPaymentSuccessLimit` - **This is used to check if the merchant has charged the same payment more than X times on a given period of time.**<br>- `ipFailureLimit` - **Exceeded the maximum allowed number of failed authorizations for a particular IP address.**<br>- `ipFailureRatio` - **Exceeded the maximum allowed ratio of failed authorizations for a particular IP address.**<br>- `inactiveMerchant` - **The Merchant is not active.**<br>- `merchantPaymentFailureLimit` - **Exceeded the maximum allowed number of failed transactions.**<br>- `merchantCaptureWithoutAuthLimit` - **Exceeded the maximum allowed number of transactions without authorizations.**<br>- `refundWithoutSale` - **Refund transaction does not have an associated sale transaction.**<br>- `refundWithoutSaleLimit` - **Exceeded the maximum number of refund transactions that do not have associated sale transactions.**<br>- `captureAboveAuthLimit` - **Exceeded the maximum authorized value for transactions with failed authorizations.**<br>- `fraudScore` - **Transaction fraud score.**<br>- `cvv` - **CVV.**<br>- `avs` - **AVS.**<br>- `aavs` - **AAVS.**<br>- `duplicateTxn` - **Duplicate transaction.**<br>- `merchantMatch` - **Transaction matches merchant details.**<br>- `currencyConversion` - **Transaction triggers currency conversion.**<br>- `settledCurrencyMismatch` - **Transaction settled currency mismatch.**<br>- `initialTxn` - **Initial transaction of this type.**<br>- `similarTotalLimit` - **Exceeded the limit of transactions with equal totals.**<br>- `similarTotalRatio` - **Exceeded the ratio of transactions with equal totals.**<br>- `saleTotalMinimum` - **Minimum transaction amount.**<br>- `limit` - **Exceeded the maximum allowed number of authorizations.**<br>- `ratio` - **This is used to check if similar transactions have reached the ratio of auth transactions in a given period of time.**<br>- `txnWatchlist` - **Check the transaction data against a custom watchlist.**<br>- `balanceRefundLimit` - **This is used to check if a merchant has enough balance to process a REFUND transaction and it is within the scope of the threshold.**<br></details><br> | getType(): ?string | setType(?string type): void |
| `target` | [`?string(DecisionsTargetEnum)`](../../doc/models/decisions-target-enum.md) | Optional | The target that this decision should apply at.<br><br><details><br><summary>Valid Values</summary><br>- `activation` - **Terminal activation.**<br>- `auth` - **Apply this decision during transaction authorization.**<br>- `postauth` - **Immediately after authorization.**<br>- `capture` - **Apply this decision during transaction capture.**<br>- `refund` - **Apply this decision when processing a refund.**<br>- `createEntity` - **createEntity. Process decisions during entity creation.**<br>- `underwriting` - **Underwriting. Check the members before they are boarded.**<br>- `preboard` - **Preboard. Check the Merchant before they are boarded.**<br>- `postboard` - **Check the Merchant after they are boarded.**<br>- `txn` - **Check the Merchant when they process a Transaction.**<br>- `txnVolume` - **Check the Merchant when their transaction volume hits a certain amount.**<br>- `payout` - **Check the Merchant when a Payout occurs.**<br>- `payoutVolume` - **Check the Merchant when the volume of Payouts to the Merchant hits a certain amount.**<br></details><br> | getTarget(): ?string | setTarget(?string target): void |
| `action` | [`?int(DescisionActionEnum)`](../../doc/models/descision-action-enum.md) | Optional | The action to take when this check fails.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **No action.**<br>- `1` - **Block txn, will never be processed. The Entity is sent to the manual review queue.**<br>- `3` - **Hold txn, will not be captured.**<br>- `4` - **Reserve txn, funds should be reserved.**<br>- `5` - **Block current activity, no change for merchant.**<br>- `6` - **Passed decision(s). Will not be set anywhere, will only be used for integration purposes.**<br>- `7` - **We did not have policies to process.**<br>- `8` - **We onboard the merchant and wait for manual check later.**<br>- `9` - **Schedule the automatic release of the reserve.**<br>- `10` - **Hold txn, will not be captured. Automatic release when the associated sale is done.**<br></details><br> | getAction(): ?int | setAction(?int action): void |
| `sequence` | `?int` | Optional | A sequence number to use when applying multiple linked decisions: When two or more decisions are linked using their 'decision' fields, the checks with lower 'sequence' numbers are applied first; this field is specified as an integer. | getSequence(): ?int | setSequence(?int sequence): void |
| `amount` | `?int` | Optional | The minimum value that the Transaction must be to target this decision, The unit of measure is determined by the type of check. | getAmount(): ?int | setAmount(?int amount): void |
| `value` | `?string` | Optional | The amount that the associated Transaction should be compared against. The units for this field depend on the type of check: for checks that are based on a ratio, specify the amount as a percentage in basis points; for checks that are based on a dollar amount, specify the amount in cents; for checks that are based on a count, specify the exact value as an integer. | getValue(): ?string | setValue(?string value): void |
| `period` | [`?string(DecisionsPeriodEnum)`](../../doc/models/decisions-period-enum.md) | Optional | A date indicator that determines how far back in time time-based checks should be checked. This field works in conjunction with the 'periodFactor' field, which multiplies this basic period.<br><br><details><br><summary>Valid Values</summary><br>- `days` - **Days. The basic value for the date range is set in days.**<br>- `weeks` - **Weeks. The basic value for the date range is set in weeks.**<br>- `months` - **Months. The basic value for the date range is set in months.**<br>- `years` - **Years. The basic value for the date range is set in years.**<br>- `seconds` - **Seconds. The basic value for the date range is set in seconds.**<br>- `minutes` - **Minutes. The basic value for the date range is set in minutes.**<br>- `hours` - **Hours. The basic value for the date range is set in hours.**<br></details><br> | getPeriod(): ?string | setPeriod(?string period): void |
| `periodFactor` | `?int` | Optional | A multiplier that you can use to adjust the basic date range set in the 'period' field, such as daily, weekly, monthly, or annually; this field is specified as an integer and its value determines how the interval is multiplied. | getPeriodFactor(): ?int | setPeriodFactor(?int periodFactor): void |
| `schedule` | `?string` | Optional | The schedule that determines when this Decision is triggered to check entities. | getSchedule(): ?string | setSchedule(?string schedule): void |
| `scheduleFactor` | `?int` | Optional | A multiplier that you can use to adjust the schedule set in the 'schedule' field, if it is set to a duration-based trigger, such as daily, weekly, monthly, or annually. This field is specified as an integer and its value determines how the interval is multiplied. | getScheduleFactor(): ?int | setScheduleFactor(?int scheduleFactor): void |
| `start` | `?int` | Optional | The date on which checking of the Decision should start is specified as an eight digit string in YYYYMMDD format, for example, '20160120' for January 20, 2016; the value of this field must represent a date in the future, or the present date. | getStart(): ?int | setStart(?int start): void |
| `finish` | `?int` | Optional | The date on which checking of the Decision should end. The date is specified as an eight digit string in YYYYMMDD format, for example, '20160120' for January 20, 2016. The value of this field must represent a date in the future. | getFinish(): ?int | setFinish(?int finish): void |
| `low` | `?int` | Optional | A lower cut-off value for the score in this decision; the check fails if the score is equal to or below this value. | getLow(): ?int | setLow(?int low): void |
| `high` | `?int` | Optional | An upper cut-off value for the score in this decision; the check fails if the score is equal to or above this value. | getHigh(): ?int | setHigh(?int high): void |
| `useCache` | [`?int(DecisionsUseCacheEnum)`](../../doc/models/decisions-use-cache-enum.md) | Optional | Whether to check for and use existing Verifications and Verification Results for this decision.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Disabled**<br>- `1` - **Enabled**<br></details><br> | getUseCache(): ?int | setUseCache(?int useCache): void |
| `cacheTime` | `?int` | Optional | The time caching limit to check for existing verification. | getCacheTime(): ?int | setCacheTime(?int cacheTime): void |
| `options` | `?int` | Optional | The options for the Verification are specified as a sum of the desired options. | getOptions(): ?int | setOptions(?int options): void |
| `additionalOptions` | `?int` | Optional | The additionalOptions for the Verification are specified as a sum of the desired options. | getAdditionalOptions(): ?int | setAdditionalOptions(?int additionalOptions): void |
| `errorMessage` | `?string` | Optional | The error message for the decision: If the field is null the error message will be a generic failure message, if the field is empty the error message will be a specific error message, if the field is set to a string the error message will be that string. | getErrorMessage(): ?string | setErrorMessage(?string errorMessage): void |
| `reason` | `?string` | Optional | The reason for the decision. If the field is null the error message will be a generic message, if the field is set to a string the reason message will be that string. | getReason(): ?string | setReason(?string reason): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "login": "t1_log_61e72ab44fd39df9483aa2c",
  "application": "txn",
  "level": "partition",
  "type": "cvv",
  "target": "postauth",
  "action": 1,
  "value": "1",
  "period": "days",
  "periodFactor": 1,
  "scheduleFactor": 1,
  "start": 20160120,
  "finish": 20160120,
  "low": 1,
  "useCache": 0,
  "org": "t1_org_5fada4629c317f80bc9cb12",
  "entity": "t1_ent_67d86dfd3442f3e2927ecbd",
  "division": "t1_div_67c56806728fbbf0bae0b00",
  "partition": "t1_ptn_000111d4d504f21414978f0",
  "decision": "t1_dcs_6789a1b36647513d66cf30a",
  "sequence": 0,
  "amount": 1,
  "high": 2,
  "cacheTime": 0,
  "options": 0,
  "additionalOptions": 0,
  "errorMessage": "Unable to accept without CVV",
  "inactive": 0,
  "frozen": 0
}
```

