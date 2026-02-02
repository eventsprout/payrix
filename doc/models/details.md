
# Details

An object describing the response, including the request ID and pagination indicators.

## Structure

`Details`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `requestId` | `?int` | Optional | A unique identifier set by the API client, that is echoed by the response.<br>The request ID can be useful in troubleshooting and monitoring. | getRequestId(): ?int | setRequestId(?int requestId): void |
| `totals` | `?array` | Optional | Returns an empty array if we don't pass totals header. | getTotals(): ?array | setTotals(?array totals): void |
| `page` | [`?DetailsProperties`](../../doc/models/details-properties.md) | Optional | Where the response lists multiple resources, the API splits the response into several 'pages'.<br>This object indicates the current and last available pages in the list. | getPage(): ?DetailsProperties | setPage(?DetailsProperties page): void |

## Example (as JSON)

```json
{
  "requestId": 240,
  "totals": {
    "key1": "val1",
    "key2": "val2"
  },
  "page": {
    "current": 164,
    "last": 78,
    "hasMore": false
  }
}
```

