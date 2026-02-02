
# Error Four Hundred Exception

## Structure

`ErrorFourHundredException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(ErrorFourHundredProperties[])`](../../doc/models/error-four-hundred-properties.md) | Optional | An array of zero or more errors that occurred when the API processed the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example (as JSON)

```json
{
  "errors": [
    {
      "code": 144,
      "severity": 6,
      "msg": "msg6",
      "field": "field4",
      "errorCode": "errorCode6"
    }
  ]
}
```

