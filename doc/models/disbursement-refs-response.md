
# Disbursement Refs Response

## Structure

`DisbursementRefsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `disbursement` | string\|[DisbursementsResponse](../../doc/models/disbursements-response.md)\|null | Optional | The identifier of the Disbursement that this disbursementRef resource refers to. | getDisbursement(): | setDisbursement( disbursement): void |
| `disbursementRef` | string\|[DisbursementRefsResponse](../../doc/models/disbursement-refs-response.md)\|null | Optional | The identifier of the DisbursementRef that this disbursementRef resource refers to. | getDisbursementRef(): | setDisbursementRef( disbursementRef): void |
| `platform` | [`?string(DisbursementRefPlatformEnum)`](../../doc/models/disbursement-ref-platform-enum.md) | Optional | The platform used to process this Transaction.<br><br><details><br><summary>Valid Values</summary><br>- `ELAVON`  - The Elavon processor.<br>- `VANTIV`  - The WorldPay (aka Vantiv or Litle) eComm (aka VAP) processor.<br><br>- `VCORE` - The WorldPay (aka Vantiv) Core processor.<br><br>- `TDBANK` - External funding with TD Bank via the Operating Account.<br><br>- `TDBANKCA` - External funding with TD Bank Canada via the Operating Account.<br><br>- `WELLSACH` - The Wells Fargo ACH processor.<br><br>- `WELLSFARGO` - The Wells Fargo Merchant Services processor.<br><br>- `WFSINGLE` - The WFSINGLE processor.<br><br>- `WORLDPAY` - The WORLDPAY processor.<br><br></details><br> | getPlatform(): ?string | setPlatform(?string platform): void |
| `companyId` | `?string` | Optional | An identification document for a company. | getCompanyId(): ?string | setCompanyId(?string companyId): void |
| `ref` | `?string` | Optional | The Disbursement reference code itself. This field is stored as a text string and must be between 1 and 50 characters long. | getRef(): ?string | setRef(?string ref): void |
| `fileRef` | `?string` | Optional | A file reference code that is stored as a text string and must be between 1 and 50 characters long. | getFileRef(): ?string | setFileRef(?string fileRef): void |
| `stage` | [`?string(DisbursementRefStageEnum)`](../../doc/models/disbursement-ref-stage-enum.md) | Optional | The stage of the Disbursement reference.<br><br><details><br><summary>Valid Values</summary><br>- `create`  - Funding is sent to the processor (based on prior split setup).<br>- `approve`  - Funding approved by the processor.<br><br>- `split` - Disbursement amount is split for processing.<br><br>- `failed` - Funding failed.<br><br></details><br> | getStage(): ?string | setStage(?string stage): void |
| `amount` | `?int` | Optional | The amount of the disbursement related to this disbursementRef. | getAmount(): ?int | setAmount(?int amount): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `disbursementRefs` | [`?(DisbursementRefsResponse[])`](../../doc/models/disbursement-refs-response.md) | Optional | - | getDisbursementRefs(): ?array | setDisbursementRefs(?array disbursementRefs): void |
| `disbursementResults` | [`?(DisbursementResultsResponse[])`](../../doc/models/disbursement-results-response.md) | Optional | - | getDisbursementResults(): ?array | setDisbursementResults(?array disbursementResults): void |

## Example (as JSON)

```json
{
  "frozen": 0,
  "inactive": 0,
  "id": "id4",
  "created": "created4",
  "modified": "modified2",
  "creator": "String3",
  "modifier": "modifier2"
}
```

