
# Fraud Sight Enablements Put Request

## Structure

`FraudSightEnablementsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entity` | `string` | Required | The identifier of the Entity that fraudSightEnablements is associated to. | getEntity(): string | setEntity(string entity): void |
| `groupName` | [`string(GroupNameEnum)`](../../doc/models/group-name-enum.md) | Required | The name of the group for this FraudSight enablement.<br><br><details><br><summary>Valid Values</summary><br>- `PIECPA` - Post Network -Decision Non EMV CP & Inform remaining CP.<br>- `PICNP` - Post Network - Decision CNP only & Inform CP.<br>- `PACPA` - Post Network - Decision All CP Authorizations.<br>- `INCNP` - Pre Network -Decision Non-Recurring CNP & Inform CP.<br>- `PIKCPA` - Post Network -Decision Key Entered CP & Inform remaining CP.<br>- `IECNP` - Pre Network -Decision CNP and Non EMV CP & Inform remaining CP.<br>- `ACPA` - Pre Network - Decision All CP Authorizations.<br>- `PACNP` - Post Network - Decision All Authorizations (CNP & CP).<br>- `PIECNP` - Post Network -Decision CNP and Non EMV CP & Inform remaining CP.<br>- `IKCPA` - Pre Network -Decision Key Entered CP & Inform remaining CP.<br>- `ACNP` - Pre Network - Decision All Authorizations (CNP & CP).<br>- `PINCNP` - Post Network -Decision Non-Recurring CNP & Inform CP.<br>- `IECPA` - Pre Network -Decision Non EMV CP & Inform remaining CP.<br>- `ICNP` - Pre Network - Decision CNP only & Inform CP.<br></details><br> | getGroupName(): string | setGroupName(string groupName): void |
| `description` | `string` | Required | The description of the Group Name. | getDescription(): string | setDescription(string description): void |

## Example (as JSON)

```json
{
  "entity": "t1_ent_5a1pf5a1234531155a12345",
  "groupName": "PIECPA",
  "description": "The description of the Group Name.",
  "org": "t1_org_5a1pf5a1234531155a12345",
  "inactive": 0,
  "frozen": 0
}
```

