
# Watchlists Post Request

## Structure

`WatchlistsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `string` | Required | The identifier of the Login associated with this Watchlist. | getLogin(): string | setLogin(string login): void |
| `integration` | [`?string(WatchlistIntegrationEnum)`](../../doc/models/watchlist-integration-enum.md) | Optional | The integration related to this Watchlist.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **APPLE integration.**<br>- `ELAVON` - **ELAVON integration.**<br>- `FEDACH` - **FEDACH integration.**<br>- `FIRSTDATA` - **FIRSTDATA integration.**<br>- `NEUTRINO` - **NEUTRINO integration.**<br>- `OFAC` - **OFAC integration.**<br>- `PAYRIX` - **PAYRIX integration.**<br>- `PLAID` - **PLAID integration.**<br>- `SIFT` - **SIFT integration.**<br>- `SOCURE` - **SOCURE integration.**<br>- `SOUNDPAYMENTS` - **SOUNDPAYMENTS integration.**<br>- `TDBANK` - **TDBANK integration.**<br>- `TDBANKCA` - **TDBANKCA integration.**<br>- `VANTIV` - **VANTIV integration.**<br>- `VCORE` - **VCORE integration.**<br>- `WEBSHIELD` - **WEBSHIELD integration.**<br>- `WELLSACH` - **WELLSACH integration.**<br>- `WELLSFARGO` - **WELLSFARGO integration.**<br>- `WFSINGLE` - **WFSINGLE integration.**<br>- `WORLDPAY` - **WORLDPAY integration.**<br></details><br> | getIntegration(): ?string | setIntegration(?string integration): void |
| `name` | `?string` | Optional | The name of this Watchlist.<br>This field is stored as a text string and must be between 0 and 500 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Watchlist.<br>This field is stored as a text string and must be between 0 and 500 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `default` | [`int(WatchlistsDefaultEnum)`](../../doc/models/watchlists-default-enum.md) | Required | Whether this Watchlist applies to everyone.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Non-Default**<br>- `1` - **Default**<br></details><br> | getDefault(): int | setDefault(int default): void |
| `custom` | `?string` | Optional | A custom identifier for this Watchlist.<br>This field is stored as a text string and must be between 0 and 500 characters long. | getCustom(): ?string | setCustom(?string custom): void |
| `inactive` | [`int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Required | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): int | setInactive(int inactive): void |
| `frozen` | [`int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Required | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): int | setFrozen(int frozen): void |

## Example (as JSON)

```json
{
  "login": "login4",
  "default": 0,
  "inactive": 0,
  "frozen": 0,
  "integration": "FEDACH",
  "name": "name4",
  "description": "description4",
  "custom": "custom2"
}
```

