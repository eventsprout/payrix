
# Chargeback Documents Response

## Structure

`ChargebackDocumentsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `chargeback` | string\|[ChargebacksResponse](../../doc/models/chargebacks-response.md)\|null | Optional | The identifier of the Chargeback resource that this chargebackDocument relates to. | getChargeback(): | setChargeback( chargeback): void |
| `ref` | `?string` | Optional | The reference for this chargebackDocument.<br>This field is stored as a text string and must be between 1 and 100 characters long.<br>The value is set when the file is properly integrated, otherwise will be null. | getRef(): ?string | setRef(?string ref): void |
| `type` | [`?string(ChargebackDocumentTypeEnum)`](../../doc/models/chargeback-document-type-enum.md) | Optional | The type of the file that holds this chargebackDocument.<br>The value is set when the file is properly integrated, otherwise will be null.<br><br><details><br><summary>Valid Values</summary><br>- `jpg` - **JPG file**<br>- `jpeg` - **JPEG file**<br>- `gif` - **GIF file**<br>- `png` - **PNG file**<br>- `pdf` - **PDF file**<br>- `tiff` - **TIFF file**<br>- `tif` - **TIF file**<br></details><br> | getType(): ?string | setType(?string type): void |
| `name` | `?string` | Optional | The name of this chargebackDocument.<br>This field is stored as a text string and must be between 1 and 100 characters long.<br>The value is set when the file is created and properly integrated. It holds the real file name used by the user. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | The description of this chargebackDocument.<br>This field is stored as a text string and must be between 1 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `status` | [`?string(ChargebackDocumentStatusEnum)`](../../doc/models/chargeback-document-status-enum.md) | Optional | The current status of the chargebackDocument.<br><br><details> <br><summary>Valid Values</summary><br>- `created` - **The ChargebackDocument has been created.**<br>- `processed` - **The ChargebackDocument integration has been successful.**<br><br>- `failed` - **The ChargebackDocument integration has failed.**<br><br></details><br>**Default**: `ChargebackDocumentStatusEnum::CREATED`<br> | getStatus(): ?string | setStatus(?string status): void |
| `documentSource` | [`?string(ChargebackDocumentsDocumentSourceEnum)`](../../doc/models/chargeback-documents-document-source-enum.md) | Optional | The source of the document.<br><br><details><br><summary>Valid Values</summary><br>- `merchant` - **Merchant.** <br>- `issuer` - **Issuer.** <br></details><br> | getDocumentSource(): ?string | setDocumentSource(?string documentSource): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "status": "created",
  "inactive": 0,
  "frozen": 0,
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier6"
}
```

