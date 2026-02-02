
# Fee Modifiers Response

## Structure

`FeeModifiersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `fee` | string\|[FeesResponse](../../doc/models/fees-response.md)\|null | Optional | The identifier of the Fee that this Fee Modifier applies. | getFee(): | setFee( fee): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity that this Fee Modifier applies for. | getEntity(): | setEntity( entity): void |
| `org` | string\|[OrgsResponse](../../doc/models/orgs-response.md)\|null | Optional | The identifier of the Org this Fee Modifiers should apply for on behalf of the Entity identified in the value of the 'entity' field.<br>This field is optional. If it is set, then the Fee Modifier is applied to this Org instead. | getOrg(): | setOrg( org): void |
| `division` | string\|[DivisionsResponse](../../doc/models/divisions-response.md)\|null | Optional | Division ID in which the fee modifiers is associated. | getDivision(): | setDivision( division): void |
| `partition` | string\|[PartitionsResponse](../../doc/models/partitions-response.md)\|null | Optional | ID of the partition related to this fee modifiers. | getPartition(): | setPartition( partition): void |
| `fromentity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity who should pay this Fee on behalf of the Entity identified in the value of the 'entity' or 'org' field.<br>This field is optional. If it is set, then the Fee is charged to this Entity instead. | getFromentity(): | setFromentity( fromentity): void |
| `markupUm` | [`?int(FeeModifiersMarkupUmEnum)`](../../doc/models/fee-modifiers-markup-um-enum.md) | Optional | The unit of measure for the markup amount for the Fee.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Fixed Amount.** Specified in the 'markupAmount' field as an integer in cents.<br>- `2` - **Percentage.** Specified in the 'markupAmount' field in basis points.<br></details><br> | getMarkupUm(): ?int | setMarkupUm(?int markupUm): void |
| `markupAmount` | `?int` | Optional | The total amount of the markup value for this Fee.<br>The units used in this field are determined by the value of the 'markupUm' field on the Fee. If the 'markupUm' field is set to 'percentage', then this field specifies the Fee percentage to levy in basis points. If the 'markupUm' field is set to 'actual', then this field specifies the markup amount in cents. | getMarkupAmount(): ?int | setMarkupAmount(?int markupAmount): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id8",
  "created": "created8",
  "modified": "modified6",
  "creator": "String7",
  "modifier": "modifier2"
}
```

