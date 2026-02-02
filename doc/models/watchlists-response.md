
# Watchlists Response

## Structure

`WatchlistsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | `?string` | Optional | The identifier of the Login associated with this Watchlist. | getLogin(): ?string | setLogin(?string login): void |
| `integration` | [`?string(WatchlistIntegrationEnum)`](../../doc/models/watchlist-integration-enum.md) | Optional | The integration related to this Watchlist.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **APPLE integration.**<br>- `ELAVON` - **ELAVON integration.**<br>- `FEDACH` - **FEDACH integration.**<br>- `FIRSTDATA` - **FIRSTDATA integration.**<br>- `NEUTRINO` - **NEUTRINO integration.**<br>- `OFAC` - **OFAC integration.**<br>- `PAYRIX` - **PAYRIX integration.**<br>- `PLAID` - **PLAID integration.**<br>- `SIFT` - **SIFT integration.**<br>- `SOCURE` - **SOCURE integration.**<br>- `SOUNDPAYMENTS` - **SOUNDPAYMENTS integration.**<br>- `TDBANK` - **TDBANK integration.**<br>- `TDBANKCA` - **TDBANKCA integration.**<br>- `VANTIV` - **VANTIV integration.**<br>- `VCORE` - **VCORE integration.**<br>- `WEBSHIELD` - **WEBSHIELD integration.**<br>- `WELLSACH` - **WELLSACH integration.**<br>- `WELLSFARGO` - **WELLSFARGO integration.**<br>- `WFSINGLE` - **WFSINGLE integration.**<br>- `WORLDPAY` - **WORLDPAY integration.**<br></details><br> | getIntegration(): ?string | setIntegration(?string integration): void |
| `name` | `?string` | Optional | The name of this Watchlist.<br>This field is stored as a text string and must be between 0 and 500 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Watchlist.<br>This field is stored as a text string and must be between 0 and 500 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `default` | [`?int(WatchlistsDefaultEnum)`](../../doc/models/watchlists-default-enum.md) | Optional | Whether this Watchlist applies to everyone.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Non-Default**<br>- `1` - **Default**<br></details><br> | getDefault(): ?int | setDefault(?int default): void |
| `custom` | `?string` | Optional | A custom identifier for this Watchlist.<br>This field is stored as a text string and must be between 0 and 500 characters long. | getCustom(): ?string | setCustom(?string custom): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id6",
  "created": "created6",
  "modified": "modified4",
  "creator": "String5",
  "modifier": "modifier0"
}
```

