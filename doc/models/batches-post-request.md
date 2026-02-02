
# Batches Post Request

## Structure

`BatchesPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchant` | `string` | Required | The identifier of the Merchant that is associated with this Batch. | getMerchant(): string | setMerchant(string merchant): void |
| `platform` | [`string(PlatformModelEnum)`](../../doc/models/platform-model-enum.md) | Required | The platform used to process this resource.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **The Apple Payment Processor.**<br>- `ELAVON` - **The Elavon processor.**<br>- `FIRSTDATA` - **The FirstData processor.**<br>- `GOOGLE` - **The Google Payment Processor.**<br>- `VANTIV` - **The WorldPay (aka Vantiv or Litle) eComm (aka VAP) processor.**<br>- `VCORE` - **The WorldPay (aka Vantiv) Core processor.**<br>- `TDBANKCA` - **External funding with TD Bank Canada via the Operating Account.**<br>- `WELLSACH` - **The Wells Fargo ACH processor.**<br>- `WELLSFARGO` - **The Wells Fargo Merchant Services processor.**<br>- `WFSINGLE` - **The WFSINGLE processor.**<br>- `WORLDPAY` - **The WORLDPAY processor.**<br></details><br> | getPlatform(): string | setPlatform(string platform): void |
| `status` | [`?string(BatchStatusEnum)`](../../doc/models/batch-status-enum.md) | Optional | The current status of this Batch.<br><br><details><br><summary>Valid Values</summary><br>- `open`  - **This Batch can accept more Transactions.**<br>- `closed` - **This Batch is closed to new Transactions and is ready to be sent to the processor.**<br></details><br>**Default**: `BatchStatusEnum::OPEN`<br> | getStatus(): ?string | setStatus(?string status): void |
| `ref` | `?string` | Optional | The reference code of the batch.<br>This field is automatically generated and stored as a text string and must be between 0 and 50 characters long. | getRef(): ?string | setRef(?string ref): void |
| `clientRef` | `?string` | Optional | The merchant's reference code of the batch.<br>This field is stored as a text string and must be between 0 and 50 characters long. | getClientRef(): ?string | setClientRef(?string clientRef): void |
| `processingId` | `?string` | Optional | Internal ID set for processing. | getProcessingId(): ?string | setProcessingId(?string processingId): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "merchant": "t1_mer_63341144b40742676bea201",
  "platform": "VANTIV",
  "status": "open",
  "ref": "reference code of batch",
  "clientRef": "merchant's reference code",
  "processingId": "Internal ID",
  "inactive": 0,
  "frozen": 0
}
```

