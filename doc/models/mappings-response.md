
# Mappings Response

## Structure

`MappingsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | `?string` | Optional | The Login that owns this resource. | getLogin(): ?string | setLogin(?string login): void |
| `name` | `?string` | Optional | Name of Mappings. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Mapping. | getDescription(): ?string | setDescription(?string description): void |
| `input` | `?string` | Optional | A JSON document that describes the input fields that should be mapped.<br>This field is stored as a text string and must be between 1 and 5000 characters long. | getInput(): ?string | setInput(?string input): void |
| `output` | `?string` | Optional | A JSON document that describes the fields that should appear in the output, after the input fields have been mapped.<br>This field is stored as a text string and must be between 1 and 5000 characters long. | getOutput(): ?string | setOutput(?string output): void |
| `namespace` | `?string` | Optional | A valid URL that represents the XML namespace of the input and output documents.<br>This field is stored as a text string and must be between 1 and 100 characters long. | getNamespace(): ?string | setNamespace(?string namespace): void |

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

