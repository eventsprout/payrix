
# Mappings Put Request

## Structure

`MappingsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `?string` | Optional | The Login that owns this resource. | getLogin(): ?string | setLogin(?string login): void |
| `name` | `?string` | Optional | Name of Mappings. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Mapping. | getDescription(): ?string | setDescription(?string description): void |
| `input` | `?string` | Optional | A JSON document that describes the input fields that should be mapped.<br>This field is stored as a text string and must be between 1 and 5000 characters long. | getInput(): ?string | setInput(?string input): void |
| `output` | `?string` | Optional | A JSON document that describes the fields that should appear in the output, after the input fields have been mapped.<br>This field is stored as a text string and must be between 1 and 5000 characters long. | getOutput(): ?string | setOutput(?string output): void |
| `namespace` | `?string` | Optional | A valid URL that represents the XML namespace of the input and output documents.<br>This field is stored as a text string and must be between 1 and 100 characters long. | getNamespace(): ?string | setNamespace(?string namespace): void |

## Example (as JSON)

```json
{
  "login": "t1_log_63d25f51ea7ddb271d78304",
  "name": "Test1",
  "description": "Test1",
  "input": "{\\\"mappingsCreate\\\":{\\\"requests\\\":[{\\\"name\\\":{\\\"__path__\\\":\\\"mappings2Create;mappings2Request;name\\\"}}]}}",
  "output": "{\\\"mappings2CreateResponse\\\":{\\\"mappings2Responses\\\":[{\\\"name\\\":{\\\"__path__\\\":\\\"mappingsCreateResponse;requests;[];name\\\"}}]}}",
  "namespace": "XML namespace of input and output"
}
```

