
# Org Flow Rules Post Request

## Structure

`OrgFlowRulesPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `orgFlow` | string\|[OrgFlowsPostRequest](../../doc/models/org-flows-post-request.md)\|null | Optional | The identifier of the orgFlow resource that this orgFlowActions resource is associated with. | getOrgFlow(): | setOrgFlow( orgFlow): void |
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
  "orgFlow": "t1_ofr_6810c6e4dad2480c7733b00",
  "name": "Test1",
  "description": "Test1 Description",
  "type": "MCC",
  "value": "0742",
  "grouping": "portalgroup_2",
  "inactive": 0,
  "frozen": 0
}
```

