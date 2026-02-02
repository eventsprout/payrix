
# Hosts Post Request

## Structure

`HostsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `partition` | `string` | Required | The identifier of the Partition resource that this Host belongs to. | getPartition(): string | setPartition(string partition): void |
| `division` | `?string` | Optional | The identifier of the Division resource that this Host belongs to. | getDivision(): ?string | setDivision(?string division): void |
| `api` | `string` | Required | The fully-qualified host name of the API for this Host.<br>For example, 'api.example.com'.<br>This field must be unique. | getApi(): string | setApi(string api): void |
| `portal` | `?string` | Optional | The fully-qualified host name of the portal for this Host.<br>For example, 'portal.example.com'. | getPortal(): ?string | setPortal(?string portal): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "api": "test-api.powerschool.com",
  "portal": "test-portal.powerschool.com",
  "partition": "t1_ptn_6509cc497e1545b08f46585",
  "division": "t1_div_63975c4e50b5282378fe306",
  "inactive": 0,
  "frozen": 0
}
```

