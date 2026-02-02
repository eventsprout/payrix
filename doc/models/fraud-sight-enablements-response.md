
# Fraud Sight Enablements Response

## Structure

`FraudSightEnablementsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `entity` | `?string` | Optional | The identifier of the Entity that is enabled for fraudSight. | getEntity(): ?string | setEntity(?string entity): void |
| `org` | `?string` | Optional | The identifier of the Org (group) that fraudSightEnablements is associated to. | getOrg(): ?string | setOrg(?string org): void |
| `groupName` | [`?string(GroupNameEnum)`](../../doc/models/group-name-enum.md) | Optional | The name of the group for this FraudSight enablement.<br><br><details><br><summary>Valid Values</summary><br>- `PIECPA` - Post Network -Decision Non EMV CP & Inform remaining CP.<br>- `PICNP` - Post Network - Decision CNP only & Inform CP.<br>- `PACPA` - Post Network - Decision All CP Authorizations.<br>- `INCNP` - Pre Network -Decision Non-Recurring CNP & Inform CP.<br>- `PIKCPA` - Post Network -Decision Key Entered CP & Inform remaining CP.<br>- `IECNP` - Pre Network -Decision CNP and Non EMV CP & Inform remaining CP.<br>- `ACPA` - Pre Network - Decision All CP Authorizations.<br>- `PACNP` - Post Network - Decision All Authorizations (CNP & CP).<br>- `PIECNP` - Post Network -Decision CNP and Non EMV CP & Inform remaining CP.<br>- `IKCPA` - Pre Network -Decision Key Entered CP & Inform remaining CP.<br>- `ACNP` - Pre Network - Decision All Authorizations (CNP & CP).<br>- `PINCNP` - Post Network -Decision Non-Recurring CNP & Inform CP.<br>- `IECPA` - Pre Network -Decision Non EMV CP & Inform remaining CP.<br>- `ICNP` - Pre Network - Decision CNP only & Inform CP.<br></details><br> | getGroupName(): ?string | setGroupName(?string groupName): void |
| `description` | `?string` | Optional | The description of the Group Name. | getDescription(): ?string | setDescription(?string description): void |
| `enablementDate` | `?string` | Optional | The Date and time when an entity was enabled for fraudSight.\nThe date is specified as an eight digit string in YYYY-MM-DD hh:mm:ss format, for example, '2023-06-01 01:00:00' for June 01, 2023. 1:00 am.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getEnablementDate(): ?string | setEnablementDate(?string enablementDate): void |
| `deleted` | `?string` | Optional | The date and time at which this resource was deleted.\nThe date is specified as an eight digit string in YYYY-MM-DD hh:mm:ss format, for example, '2023-06-01 01:00:00' for June 01, 2023. 1:00 am.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getDeleted(): ?string | setDeleted(?string deleted): void |
| `deleter` | `?string` | Optional | The id of user who deleted the fraudSightEnablements. | getDeleter(): ?string | setDeleter(?string deleter): void |
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
  "modifier": "modifier8"
}
```

