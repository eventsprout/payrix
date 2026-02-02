
# Org Flow Rules Response

## Structure

`OrgFlowRulesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `orgFlow` | string\|[OrgFlowsResponse](../../doc/models/org-flows-response.md)\|null | Optional | The identifier of the orgFlow resource that this orgFlowActions resource is associated with. | getOrgFlow(): | setOrgFlow( orgFlow): void |
| `name` | `?string` | Optional | The name of the orgFlowRules resource. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | The description of the orgFlowRules resource. | getDescription(): ?string | setDescription(?string description): void |
| `type` | [`?string(OrgFlowRulesTypeEnum)`](../../doc/models/org-flow-rules-type-enum.md) | Optional | The type of logic to apply with this OrgFlow Rule.<br><br><details><br><summary>Valid Values</summary><br>- `MCC` - **Type MCC.** The Orgflow applies based on the MCC properties of the merchants.<br>- `Custom` - **Type Custom.** The Orgflow applies based on the custom properties of the entities.<br></details><br> | getType(): ?string | setType(?string type): void |
| `value` | `?string` | Optional | The value to compare against when evaluating this OrgFlowRule. | getValue(): ?string | setValue(?string value): void |
| `grouping` | `?string` | Optional | A name for a group of rules to be applied in conjunction when evaluating this OrgFlow Rule. \nWhen grouping is used the OrgFlow will be allowed to be processed if at least one of the rules are matched. | getGrouping(): ?string | setGrouping(?string grouping): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

