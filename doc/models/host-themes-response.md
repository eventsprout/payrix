
# Host Themes Response

## Structure

`HostThemesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `host` | string\|[HostsResponse](../../doc/models/hosts-response.md)\|null | Optional | The identifier of the related host. | getHost(): | setHost( host): void |
| `primaryColor` | `?string` | Optional | The theme's custom primary color. It should be a valid hex color. | getPrimaryColor(): ?string | setPrimaryColor(?string primaryColor): void |
| `default` | [`?int(HostThemesDefaultEnum)`](../../doc/models/host-themes-default-enum.md) | Optional | Determines if the themes is the default one for the host.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **On**<br>- `1` - **Off**<br></details><br> | getDefault(): ?int | setDefault(?int default): void |

## Example (as JSON)

```json
{
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

