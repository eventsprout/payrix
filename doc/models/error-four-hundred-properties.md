
# Error Four Hundred Properties

## Structure

`ErrorFourHundredProperties`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?int` | Optional | The error code associated with a particular error. | getCode(): ?int | setCode(?int code): void |
| `severity` | `?int` | Optional | The severity level of a particular error.<br>Possible values are '0' (informational), '1' (warning), '2' (error) and '4' (failure). | getSeverity(): ?int | setSeverity(?int severity): void |
| `msg` | `?string` | Optional | The message associated with a particular error. | getMsg(): ?string | setMsg(?string msg): void |
| `field` | `?string` | Optional | Field name associated with error. | getField(): ?string | setField(?string field): void |
| `errorCode` | `?string` | Optional | An identifying string code for this error. | getErrorCode(): ?string | setErrorCode(?string errorCode): void |

## Example (as JSON)

```json
{
  "code": 52,
  "severity": 158,
  "msg": "msg8",
  "field": "field6",
  "errorCode": "errorCode8"
}
```

