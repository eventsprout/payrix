
# Payouts Response

## Structure

`PayoutsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The Login that owns this resource. | getLogin(): | setLogin( login): void |
| `account` | string\|[AccountsResponse](../../doc/models/accounts-response.md)\|null | Optional | The token of the Account that this Payout is associated with.<br>This account will either receive the funds or be debited for the funds every time a Disbursement occurs, depending on the direction of the Disbursement. | getAccount(): | setAccount( account): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity that this Payout is associated with. | getEntity(): | setEntity( entity): void |
| `billing` | string\|[BillingsResponse](../../doc/models/billings-response.md)\|null | Optional | The identifier of a Billing that this Payout is associated with. Payout associated with a Billing record will be used to pay for Statements. | getBilling(): | setBilling( billing): void |
| `payoutFlow` | string\|[PayoutFlowsResponse](../../doc/models/payout-flows-response.md)\|null | Optional | The identifier of the PayoutFlow associated with this Payout. | getPayoutFlow(): | setPayoutFlow( payoutFlow): void |
| `name` | `?string` | Optional | The name of this Payout.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Payout.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `schedule` | [`?int(PayoutScheduleEnum)`](../../doc/models/payout-schedule-enum.md) | Optional | The schedule that determines when the Payout resource that is created should be triggered to be paid.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Daily.** The Payout is paid every day.<br>- `2` - **Weekly.** The Payout is paid every week.<br>- `3` - **Monthly.** The Payout is paid every month.<br>- `4` - **Annually.** The Payout is paid every year.<br>- `5` - **Single.** The Payout is a one-off payment.<br></details><br> | getSchedule(): ?int | setSchedule(?int schedule): void |
| `scheduleFactor` | `?int` | Optional | A multiplier that you can use to adjust the schedule set in the 'schedule' field, if it is set to a duration-based trigger, such as daily, weekly, monthly, or annually.<br>This field is specified as an integer and its value determines how the interval is multiplied. | getScheduleFactor(): ?int | setScheduleFactor(?int scheduleFactor): void |
| `start` | `?int` | Optional | The date on which payment of the Payout should start.<br>The date is specified as an eight digit string in YYYYMMDD format, for example, '20160120' for January 20, 2016.<br>The value of this field must represent a date in the future, or the present date. | getStart(): ?int | setStart(?int start): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The currency of the amount in this Payout. This field is only required when Um is set to ACTUAL. If this field is not set we will process disbursements for all currencies. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `um` | [`?int(PayoutUmEnum)`](../../doc/models/payout-um-enum.md) | Optional | The unit of measure for this Payout is the percentage of funds.<br>If the Entity has a negative balance of $10 and the amount is set to 10000 (100%),<br>then $10 will be drawn from their account to fully replenish the balance to $0.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Percentage unit measurement.** (Percentage of Funds).<br>- `2` - **Actual unit measurement.** (Exact Currency Amount).<br>- `3` - **Negative Percentage unit measurement.** (Replenish account by percent negative back to $0).<br></details><br> | getUm(): ?int | setUm(?int um): void |
| `amount` | `?int` | Optional | The total amount of this Payout.<br>The units used in this field are determined by the value of the 'um' field on the Payout. If the 'um' field is set to '1' or '3', then this field specifies the Payout percentage to levy in basis points. If the 'um' field is set to '2', then this field specifies the Payout in cents. | getAmount(): ?int | setAmount(?int amount): void |
| `minimum` | `?int` | Optional | The threshold that will ensure no disbursement is generated if it doesn't reach the minimum value. | getMinimum(): ?int | setMinimum(?int minimum): void |
| `maximum` | `?int` | Optional | The maximum threshold for a disbursement. Any amount in a disbursement exceeding this value will not be released, and will roll over to the next disbursement. | getMaximum(): ?int | setMaximum(?int maximum): void |
| `float` | `?int` | Optional | An optional field indicating the minimum balance you want to maintain, despite any Payouts occurring. If the Payout would reduce the balance to below this value, then it is not processed.<br>This field is specified as an integer in cents.<br>For example, a float value of 1000 would ensure that a balance of 10 USD is maintained at all times. | getFloat(): ?int | setFloat(?int float): void |
| `secondaryDescriptor` | `?string` | Optional | The secondary billing descriptor to appear on the bank statements for the payout. | getSecondaryDescriptor(): ?string | setSecondaryDescriptor(?string secondaryDescriptor): void |
| `skipOffDays` | [`?int(PayoutFlowsSkipOffDaysEnum)`](../../doc/models/payout-flows-skip-off-days-enum.md) | Optional | Whether the Payout resource will be marked to skip the creation of disbursements on holidays and weekends.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Do not skip Holidays and Weekends.** Disbursement will be generated in a Requested status and process the next business day.<br>- `1` - **Skip Holidays and Weekends.** IMPORTANT: We do not advise setting this for weekly, monthly, or yearly Payout schedules as the disbursement will skip and not be generated until the next scheduled date.<br></details><br> | getSkipOffDays(): ?int | setSkipOffDays(?int skipOffDays): void |
| `sameDay` | [`?int(PayoutFlowsSameDayEnum)`](../../doc/models/payout-flows-same-day-enum.md) | Optional | Whether the payout workflow allows for same day payouts.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Disabled**<br>- `1` - **Enabled**<br></details><br> | getSameDay(): ?int | setSameDay(?int sameDay): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `disbursements` | [`?(DisbursementsResponse[])`](../../doc/models/disbursements-response.md) | Optional | - | getDisbursements(): ?array | setDisbursements(?array disbursements): void |

## Example (as JSON)

```json
{
  "currency": "USD",
  "inactive": 0,
  "frozen": 0,
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

