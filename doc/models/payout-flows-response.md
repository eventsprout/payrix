
# Payout Flows Response

## Structure

`PayoutFlowsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The Login that owns this resource. | getLogin(): | setLogin( login): void |
| `payoutLogin` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The Login that will own the Payout resource. When set to null, the Payout resource will be owned by the triggerring Entity. | getPayoutLogin(): | setPayoutLogin( payoutLogin): void |
| `org` | string\|[OrgsResponse](../../doc/models/orgs-response.md)\|null | Optional | The identifier of the Org that this payoutFlows resource applies to.<br>If you set this field, then the payoutFlow applies to all Entities in the Org. | getOrg(): | setOrg( org): void |
| `division` | string\|[DivisionsResponse](../../doc/models/divisions-response.md)\|null | Optional | The identifier of the Division in which entities will have automated payouts generated. | getDivision(): | setDivision( division): void |
| `partition` | string\|[PartitionsResponse](../../doc/models/partitions-response.md)\|null | Optional | The identifier of the Partition in which entities will have automated payouts generated. | getPartition(): | setPartition( partition): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity that this payoutFlow applies to. | getEntity(): | setEntity( entity): void |
| `billing` | string\|[BillingsResponse](../../doc/models/billings-response.md)\|null | Optional | The identifier of a Billing that this PayoutFlow is associated with.<br>The Billing identifier will be carried over to Payouts created based on this PayoutFlow. | getBilling(): | setBilling( billing): void |
| `trigger` | [`?string(PayoutFlowTriggerEnum)`](../../doc/models/payout-flow-trigger-enum.md) | Optional | The event on the Org or Entity that should trigger the creation of an associated Payout resource.<br><br><details><br><summary>Valid Values</summary><br>- `accountCreate` - **Primary payment account creation.** (primary must be 1)<br>- `board` - **Merchant boarding.**<br></details><br> | getTrigger(): ?string | setTrigger(?string trigger): void |
| `schedule` | [`?string(PayoutFlowScheduleEnum)`](../../doc/models/payout-flow-schedule-enum.md) | Optional | The schedule that determines when the Payout resource that is created should be triggered to be paid.<br><br><details><br><summary>Valid Values</summary><br>- `days` - **Daily.** The Payout is paid every day.<br>- `weeks` - **Weekly.** The Payout is paid every week.<br>- `months` - **Monthly.** The Payout is paid every month.<br>- `years` - **Annually.** The Payout is paid every year.<br>- `single` - **Single.** The Payout is a one-off payment.<br></details><br>**Default**: `PayoutFlowScheduleEnum::DAYS`<br> | getSchedule(): ?string | setSchedule(?string schedule): void |
| `scheduleFactor` | `?int` | Optional | A multiplier that you can use to adjust the schedule set in the 'schedule' field, if it is set to a duration-based trigger, such as daily, weekly, monthly, or annually. This affects the Payout resource that is created by this payoutFlow. This field is specified as an integer and its value determines how the interval is multiplied.<br><br><details><br><summary>Valid Values</summary> <br>- `1`  - **Subscription to trigger daily**.<br> </details><br> | getScheduleFactor(): ?int | setScheduleFactor(?int scheduleFactor): void |
| `start` | `?int` | Optional | The date on which payment of the Payout should start.<br>The date is specified as an eight digit string in YYYYMMDD format, for example, '20160120' for January 20, 2016. | getStart(): ?int | setStart(?int start): void |
| `um` | [`?string(PayoutFlowUmEnum)`](../../doc/models/payout-flow-um-enum.md) | Optional | The unit of measure for this Payout is the percentage of funds.<br>If the Entity has a negative balance of $10 and the amount is set to 10000 (100%),<br>then $10 will be drawn from their account to fully replenish the balance to $0.<br><br><details><br><summary>Valid Values</summary><br>- `percent` - **Percentage unit measurement.** (Percentage of Funds).<br>- `actual` - **Actual unit measurement.** (Exact Currency Amount).<br>- `percentneg` - **Negative Percentage unit measurement.** (Replenish account by percent negative back to $0).<br></details><br>**Default**: `PayoutFlowUmEnum::PERCENT`<br> | getUm(): ?string | setUm(?string um): void |
| `amount` | `?int` | Optional | The total amount of the Payout resource that is created.<br>The units used in this field are determined by the value of the 'um' field on the Payout. If the 'um' field is set to '1' or '3', then this field specifies the Payout percentage to levy in basis points. If the 'um' field is set to '2', then this field specifies the Payout in cents. | getAmount(): ?int | setAmount(?int amount): void |
| `minimum` | `?int` | Optional | The minium amout of payout that will process. | getMinimum(): ?int | setMinimum(?int minimum): void |
| `secondaryDescriptor` | `?string` | Optional | The secondary billing descriptor to appear on the bank statements in which entities will have automated payouts generated. | getSecondaryDescriptor(): ?string | setSecondaryDescriptor(?string secondaryDescriptor): void |
| `payoutInactive` | [`?int(PayoutInactiveEnum)`](../../doc/models/payout-inactive-enum.md) | Optional | Whether the Payout resource will be marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Inactive**<br>- `1` - **Active**<br></details><br> | getPayoutInactive(): ?int | setPayoutInactive(?int payoutInactive): void |
| `skipOffDays` | [`?int(PayoutFlowsSkipOffDaysEnum)`](../../doc/models/payout-flows-skip-off-days-enum.md) | Optional | Whether the Payout resource will be marked to skip the creation of disbursements on holidays and weekends.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Do not skip Holidays and Weekends.** Disbursement will be generated in a Requested status and process the next business day.<br>- `1` - **Skip Holidays and Weekends.** IMPORTANT: We do not advise setting this for weekly, monthly, or yearly Payout schedules as the disbursement will skip and not be generated until the next scheduled date.<br></details><br> | getSkipOffDays(): ?int | setSkipOffDays(?int skipOffDays): void |
| `sameDay` | [`?int(PayoutFlowsSameDayEnum)`](../../doc/models/payout-flows-same-day-enum.md) | Optional | Whether the payout workflow allows for same day payouts.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Disabled**<br>- `1` - **Enabled**<br></details><br> | getSameDay(): ?int | setSameDay(?int sameDay): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The identifier of a currency that this PayoutFlow is associated with. This field is optional and there is no currency restriction for the PayoutFlow if it's not set. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |

## Example (as JSON)

```json
{
  "schedule": "days",
  "um": "percent",
  "currency": "USD",
  "frozen": 0,
  "inactive": 0,
  "id": "id2",
  "created": "created2",
  "modified": "modified0",
  "creator": "String1",
  "modifier": "modifier6"
}
```

