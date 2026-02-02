
# Iplists Response

## Structure

`IplistsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | `?string` | Optional | The Login that owns this resource. | getLogin(): ?string | setLogin(?string login): void |
| `version` | [`?int(IplistsVersionEnum)`](../../doc/models/iplists-version-enum.md) | Optional | Whether this IP List contains IPv4 addresses (for example, 198.51.100.113) or IPv6 addresses (for example, 2001:0db8:85a3:0000:0000:8a2e:0370:7334).<br><br>You can only use one type in each IP List resource.<br><br><details><br><summary>Valid Values</summary><br>- `4` - **IPv4 addresses.** (Example: 198.51.100.113)<br>- `6` - **IPv6 addresses.** (Example: 2001:0db8:85a3:0000:0000:8a2e:0370:7334)<br></details><br> | getVersion(): ?int | setVersion(?int version): void |
| `type` | [`?int(IplistTypeEnum)`](../../doc/models/iplist-type-enum.md) | Optional | The type of this IP List.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Blacklisted IP address range.**<br>- `1` - **Whitelisted IP address range.**<br></details><br>**Default**: `IplistTypeEnum::BLACKLIST`<br> | getType(): ?int | setType(?int type): void |
| `start` | `?string` | Optional | The lowest IP address that should be included in this IP List.<br>The valid data type for this field depends on whether the IP list is set to be an IPv4 or IPv6 list in the 'type' field.<br>For an IPv4 list, only IPv4 addresses such as 198.51.100.113 are permitted. For an IPv6 list, only IPv6 addresses such as 2001:0db8:85a3:0000:0000:8a2e:0370:7334 are permitted. | getStart(): ?string | setStart(?string start): void |
| `finish` | `?string` | Optional | The highest IP address that should be included in this IP List.<br>The valid values for this field depend on whether the IP list is set to be an IPv4 or IPv6 list in the 'type' field.<br>For an IPv4 list, only IPv4 addresses, such as '198.51.100.113', are permitted. For an IPv6 list, only IPv6 addresses, such as '2001:0db8:85a3:0000:0000:8a2e:0370:7334' are permitted. | getFinish(): ?string | setFinish(?string finish): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "type": 0,
  "inactive": 0,
  "frozen": 0,
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

