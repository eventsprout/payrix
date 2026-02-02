
# Fee Rules Response

## Structure

`FeeRulesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `fee` | string\|[FeesResponse](../../doc/models/fees-response.md)\|null | Optional | The identifier of the Fee that this Fee Rule applies. | getFee(): | setFee( fee): void |
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
  "application": "both",
  "inactive": 0,
  "frozen": 0,
  "id": "id8",
  "created": "created8",
  "modified": "modified6",
  "creator": "String7",
  "modifier": "modifier2"
}
```

