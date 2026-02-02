
# Details Properties

Where the response lists multiple resources, the API splits the response into several 'pages'.
This object indicates the current and last available pages in the list.

## Structure

`DetailsProperties`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `current` | `?int` | Optional | The current page in the paginated resource list. | getCurrent(): ?int | setCurrent(?int current): void |
| `last` | `?int` | Optional | The last available page in the paginated resource list. | getLast(): ?int | setLast(?int last): void |
| `hasMore` | `?bool` | Optional | Indicates if another page of results is available. | getHasMore(): ?bool | setHasMore(?bool hasMore): void |

## Example (as JSON)

```json
{
  "current": 44,
  "last": 214,
  "hasMore": false
}
```

