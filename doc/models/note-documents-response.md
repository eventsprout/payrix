
# Note Documents Response

## Structure

`NoteDocumentsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `note` | string\|[NotesResponse](../../doc/models/notes-response.md)\|null | Optional | The identifier of the Note that owns this note documents resource. | getNote(): | setNote( note): void |
| `custom` | `?string` | Optional | The identifier of the Custom that relates to this notes resource. | getCustom(): ?string | setCustom(?string custom): void |
| `type` | [`?string(NoteDocumentTypeEnum)`](../../doc/models/note-document-type-enum.md) | Optional | The desired type to take on the referenced Note.<br><br><details><br><summary>Valid Values</summary><br>- `jpg` - **JPG Image File Type**<br>- `jpeg` - **JPEG Image File Type**<br>- `gif` - **GIF Image File Type**<br>- `png` - **PNG Image File Type**<br>- `pdf` - **PDF Document File Type**<br>- `tif` - **TIF Tag Image File Type**<br>- `tiff` - **TIFF Tag Image File Type**<br>- `txt` - **TXT Document File Type**<br>- `xml` - **XML Document File Type**<br>- `asc` - **American Standard Code II File Type**<br>- `rtf` - **Rich Text Document File Type**<br>- `csv` - **Comma Separated Values Table File Type**<br>- `xls` - **Microsoft Excel File Type**<br>- `doc` - **Microsoft Word File Type**<br>- `odt` - **OpenDocument Text File Type**<br>- `ods` - **OpenDocument Spreadsheet File Type**<br>- `json` - **JSON Document File Type**<br>- `soap` - **SOAP Document File Type**<br></details><br> | getType(): ?string | setType(?string type): void |
| `documentType` | [`?string(NoteDocumentsDocumentTypeEnum)`](../../doc/models/note-documents-document-type-enum.md) | Optional | The purpose of the document upload.<br><br><details><br><summary>Valid Values</summary><br>- `general` - **General use for unspecified type.**<br>- `personalId` - **An identification document for a person.**<br>- `companyId` - **An identification document for a company.**<br>- `voidCheck` - **A voided check for bank account verification.**<br>- `bankStatement` - **A bank statement.**<br>- `bankLetter` - **A bank letter for verification.**<br>- `contract` - **A contract for goods or services.**<br>- `taxDocument` - **A tax document for verification.**<br></details><br>**Default**: `NoteDocumentsDocumentTypeEnum::GENERAL`<br> | getDocumentType(): ?string | setDocumentType(?string documentType): void |
| `name` | `?string` | Optional | The name of the document on the referenced NoteDocument. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A brief description of the document. | getDescription(): ?string | setDescription(?string description): void |
| `status` | [`?string(NoteDocumentStatusEnum)`](../../doc/models/note-document-status-enum.md) | Optional | The current status of the document upload.<br><br><details><br><summary>Valid Values</summary><br>- `created` - **The database record has been created.**<br>- `processed` - **The document upload for this record was processed successfully.**<br>- `failed` - **The document upload for this record could not be processed.**<br></details><br>**Default**: `NoteDocumentStatusEnum::CREATED`<br> | getStatus(): ?string | setStatus(?string status): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "documentType": "general",
  "status": "created",
  "inactive": 0,
  "frozen": 0,
  "id": "id6",
  "created": "created6",
  "modified": "modified4",
  "creator": "String5",
  "modifier": "modifier0"
}
```

