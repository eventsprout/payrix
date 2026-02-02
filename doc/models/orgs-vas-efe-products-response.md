
# Orgs VAS Efe Products Response

## Structure

`OrgsVASEfeProductsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `org` | `?string` | Optional | The identifier of the Org (group) that orgsVASEfeProducts is associated to. | getOrg(): ?string | setOrg(?string org): void |
| `product` | [`?string(OrgsVASEfeProductsProductEnum)`](../../doc/models/orgs-vas-efe-products-product-enum.md) | Optional | This field contains the product type of the orgsVASEfeProducts. | getProduct(): ?string | setProduct(?string product): void |
| `contractType` | `?string` | Optional | The Contract type details related to the Embedded Finance product. | getContractType(): ?string | setContractType(?string contractType): void |
| `platform` | [`?string(OrgsVASEfeProductsPlatformEnum)`](../../doc/models/orgs-vas-efe-products-platform-enum.md) | Optional | The Platform to which orgsVASEfeProducts should be applied. | getPlatform(): ?string | setPlatform(?string platform): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id6",
  "created": "created6",
  "modified": "modified6",
  "creator": "String5",
  "modifier": "modifier0"
}
```

