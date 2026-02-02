
# Fee Rules Put Request

## Structure

`FeeRulesPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fee` | `?string` | Optional | The identifier of the Fee that this Fee Rule applies. | getFee(): ?string | setFee(?string fee): void |
| `name` | `?string` | Optional | The name of this Fee Rule.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | The description of this Fee Rule. | getDescription(): ?string | setDescription(?string description): void |
| `type` | [`?string(FeeRuleTypeEnum)`](../../doc/models/fee-rule-type-enum.md) | Optional | The type of Fee Rule.<br><br><details><br><summary>Valid Values</summary><br>- `AVSRESULT`<br>- `BIN`<br>- `BUSINESS`<br>- `CVVRESULT`<br>- `CORPORATE`<br>- `DYNAMICALLYROUTED`<br>- `EMV`<br>- `ENTITY`<br>- `EQUAL`<br>- `FRAUDSIGHTENABLED`<br>- `FUNDINGCURRENCYEQUAL`<br>- `FUNDINGCURRENCYNOTEQUAL`<br>- `FUNDINGCURRENCYMISMATCH`<br>- `FUNDINGENABLED`<br>- `GREATER`<br>- `IMPORTED`<br>- `INTERCHANGE`<br>- `INTERNATIONAL`<br>- `ISSUERCOUNTRY`<br>- `LESS`<br>- `MCC`<br>- `MERCHANTCOUNTRY`<br>- `METHOD`<br>- `METHODTYPE`<br>- `MISUSE`<br>- `NOTEQUAL`<br>- `ORIGIN`<br>- `OMNITOKENSENABLED`<br>- `PLATFORM`<br>- `RELATED`<br>- `RELATEDCEIL`<br>- `RELATEDDELAY`<br>- `RELATEDFLOOR`<br>- `SAMEDAY`<br>- `SETTLEDCURRENCYMISMATCH`<br>- `SIGNED`<br>- `SUBSCRIPTION`<br>- `SWIPED`<br>- `TAXFORM1099K`<br>- `TYPE`<br>- `3DSRESULT`<br>- `STATUS`<br>- `IC_RETAIN_PASSTHRU_REFUND`<br>- `SOFTPOS`<br></details><br> | getType(): ?string | setType(?string type): void |
| `application` | [`?string(FeeApplicationEnum)`](../../doc/models/fee-application-enum.md) | Optional | Where the feeRule should apply.<br><br><details><br><summary>Valid Values</summary><br>- `both` - **Both.** The rule should apply to the fee and to the calculation of collections.<br>- `fee` - **Fee.** The rule should apply only to the fee itself.<br>- `collection` - **Collection.** The fee should be only used when calculating a collection.<br></details><br>**Default**: `FeeApplicationEnum::BOTH`<br> | getApplication(): ?string | setApplication(?string application): void |
| `value` | `?string` | Optional | The value to compare against when evaluating this Fee Rule. | getValue(): ?string | setValue(?string value): void |
| `grouping` | `?string` | Optional | A name for a group of rules to be applied in conjunction when evaluating this Fee Rule.<br>When grouping is used, the Fee will be allowed to be processed if at least one of the rules are matched. | getGrouping(): ?string | setGrouping(?string grouping): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "fee": "t1_fee_67ce8623b048d0d5284a886",
  "type": "CVVRESULT",
  "application": "both",
  "value": "1",
  "name": "Fee Rule1",
  "description": "Fee Rule",
  "grouping": "Fee Rule Group1",
  "inactive": 0,
  "frozen": 0
}
```

