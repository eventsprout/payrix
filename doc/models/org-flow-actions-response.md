
# Org Flow Actions Response

## Structure

`OrgFlowActionsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `orgFlow` | string\|[OrgFlowsResponse](../../doc/models/org-flows-response.md)\|null | Optional | The identifier of the OrgFlow resource that this orgFlowActions resource is associated with. | getOrgFlow(): | setOrgFlow( orgFlow): void |
| `org` | string\|[OrgsResponse](../../doc/models/orgs-response.md)\|null | Optional | The identifier of the Org resource that this orgFlowActions resource is associated with. | getOrg(): | setOrg( org): void |
| `action` | [`?string(OrgFlowActionEnum)`](../../doc/models/org-flow-action-enum.md) | Optional | The action to take in relation to the Entity being processed.<br><br><details><br><summary>Valid Values</summary><br>- `add` - **Add the referenced Entity to the referenced Org.**<br>- `remove` - **Remove the referenced Entity from the referenced Org.**<br></details><br> | getAction(): ?string | setAction(?string action): void |

## Example (as JSON)

```json
{
  "id": "id8",
  "created": "created8",
  "modified": "modified6",
  "creator": "String7",
  "modifier": "modifier2"
}
```

