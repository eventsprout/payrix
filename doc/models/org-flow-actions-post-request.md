
# Org Flow Actions Post Request

## Structure

`OrgFlowActionsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `orgFlow` | `string` | Required | The identifier of the orgFlow resource that this orgFlowActions resource is associated with. | getOrgFlow(): string | setOrgFlow(string orgFlow): void |
| `org` | string\|[OrgsPostRequest](../../doc/models/orgs-post-request.md) | Required | The identifier of the OrgFlow resource that this orgFlowActions resource is associated with. | getOrg(): | setOrg( org): void |
| `action` | [`string(OrgFlowActionEnum)`](../../doc/models/org-flow-action-enum.md) | Required | The action to take in relation to the Entity being processed.<br><br><details><br><summary>Valid Values</summary><br>- `add` - **Add the referenced Entity to the referenced Org.**<br>- `remove` - **Remove the referenced Entity from the referenced Org.**<br></details><br> | getAction(): string | setAction(string action): void |

## Example (as JSON)

```json
{
  "orgFlow": "t1_ofw_67ed51ece84aae1a7d0783z",
  "org": "t1_org_67c89c538efe67fbf018d00",
  "action": "add"
}
```

