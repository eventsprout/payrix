
# Orgs VAS Efe Products Put Request

## Structure

`OrgsVASEfeProductsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `org` | `?string` | Optional | The identifier of the Org (group) that orgsVASEfeProducts is associated to. | getOrg(): ?string | setOrg(?string org): void |
| `product` | [`?string(OrgsVASEfeProductsProductEnum)`](../../doc/models/orgs-vas-efe-products-product-enum.md) | Optional | This field contains the product type of the orgsVASEfeProducts. | getProduct(): ?string | setProduct(?string product): void |
| `contractType` | `?string` | Optional | The Contract type details related to the Embedded Finance product. | getContractType(): ?string | setContractType(?string contractType): void |
| `platform` | [`?string(OrgsVASEfeProductsPlatformEnum)`](../../doc/models/orgs-vas-efe-products-platform-enum.md) | Optional | The Platform to which orgsVASEfeProducts should be applied. | getPlatform(): ?string | setPlatform(?string platform): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "org": "t1_org_6862c1211b366bbfe87657c",
  "product": "merchantWorkingCapital",
  "contractType": "{\"residualFeeType\": \"rev_share\"}",
  "platform": "PARAFIN",
  "inactive": 0,
  "frozen": 0
}
```

