
# Batches Response

## Structure

`BatchesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `merchant` | string\|[MerchantsResponse](../../doc/models/merchants-response.md)\|null | Optional | The identifier of the Merchant that is associated with this Batch. | getMerchant(): | setMerchant( merchant): void |
| `date` | `?DateTime` | Optional | The date the batch was first opened. | getDate(): ?\DateTime | setDate(?\DateTime date): void |
| `processingDate` | `?DateTime` | Optional | The date the batch was sent to the processor for processing. | getProcessingDate(): ?\DateTime | setProcessingDate(?\DateTime processingDate): void |
| `processingId` | `?string` | Optional | Internal ID set for processing. | getProcessingId(): ?string | setProcessingId(?string processingId): void |
| `platform` | [`?string(PlatformModelEnum)`](../../doc/models/platform-model-enum.md) | Optional | The platform used to process this resource.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **The Apple Payment Processor.**<br>- `ELAVON` - **The Elavon processor.**<br>- `FIRSTDATA` - **The FirstData processor.**<br>- `GOOGLE` - **The Google Payment Processor.**<br>- `VANTIV` - **The WorldPay (aka Vantiv or Litle) eComm (aka VAP) processor.**<br>- `VCORE` - **The WorldPay (aka Vantiv) Core processor.**<br>- `TDBANKCA` - **External funding with TD Bank Canada via the Operating Account.**<br>- `WELLSACH` - **The Wells Fargo ACH processor.**<br>- `WELLSFARGO` - **The Wells Fargo Merchant Services processor.**<br>- `WFSINGLE` - **The WFSINGLE processor.**<br>- `WORLDPAY` - **The WORLDPAY processor.**<br></details><br> | getPlatform(): ?string | setPlatform(?string platform): void |
| `status` | [`?string(BatchStatusEnum)`](../../doc/models/batch-status-enum.md) | Optional | The current status of this Batch.<br><br><details><br><summary>Valid Values</summary><br>- `open`  - **This Batch can accept more Transactions.**<br>- `closed` - **This Batch is closed to new Transactions and is ready to be sent to the processor.**<br></details><br>**Default**: `BatchStatusEnum::OPEN`<br> | getStatus(): ?string | setStatus(?string status): void |
| `ref` | `?string` | Optional | The reference code of the batch.<br>This field is automatically generated and stored as a text string and must be between 0 and 50 characters long. | getRef(): ?string | setRef(?string ref): void |
| `clientRef` | `?string` | Optional | The merchant's reference code of the batch.<br>This field is stored as a text string and must be between 0 and 50 characters long. | getClientRef(): ?string | setClientRef(?string clientRef): void |
| `closeTime` | `?string` | Optional | The default batches close time. The format should be YYYY-MM-DD HH:MM:SS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getCloseTime(): ?string | setCloseTime(?string closeTime): void |
| `batchRefs` | `?(array[])` | Optional | - | getBatchRefs(): ?array | setBatchRefs(?array batchRefs): void |
| `txns` | [`?(TxnsResponse[])`](../../doc/models/txns-response.md) | Optional | - | getTxns(): ?array | setTxns(?array txns): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "status": "open",
  "inactive": 0,
  "frozen": 0,
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

