
# Chargebacks Documents Put Request

## Structure

`ChargebacksDocumentsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | [`?string(ChargebackDocumentTypeEnum)`](../../doc/models/chargeback-document-type-enum.md) | Optional | The type of the file that holds this chargebackDocument.<br>The value is set when the file is properly integrated, otherwise will be null.<br><br><details><br><summary>Valid Values</summary><br>- `jpg` - **JPG file**<br>- `jpeg` - **JPEG file**<br>- `gif` - **GIF file**<br>- `png` - **PNG file**<br>- `pdf` - **PDF file**<br>- `tiff` - **TIFF file**<br>- `tif` - **TIF file**<br></details><br> | getType(): ?string | setType(?string type): void |
| `ref` | `?string` | Optional | The reference of this chargeback document is stored as a text string and must be between 1 and 100 characters long, with the value being set when the file is properly integrated, otherwise it will be null. | getRef(): ?string | setRef(?string ref): void |
| `description` | `?string` | Optional | The description of this chargebackDocument.<br>This field is stored as a text string and must be between 1 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `name` | `?string` | Optional | The name of this chargeback document holds the real file name used by the user, stored as a text string and must be between 1 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `documentSource` | [`?string(ChargebackDocumentsDocumentSourceEnum)`](../../doc/models/chargeback-documents-document-source-enum.md) | Optional | The source of the document.<br><br><details><br><summary>Valid Values</summary><br>- `merchant` - **Merchant.** <br>- `issuer` - **Issuer.** <br></details><br> | getDocumentSource(): ?string | setDocumentSource(?string documentSource): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "chargeback": "t1_chb_679918b34232ae6145ec03e",
  "ref": "p1_chd_67b31fca23feed2b88d8a59.pdf",
  "type": "pdf",
  "name": "Test PDF  copy.pdf",
  "description": "Test PDF  copy.pdf",
  "inactive": 0,
  "frozen": 0,
  "documentSource": "merchant"
}
```

