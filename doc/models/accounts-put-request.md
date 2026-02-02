
# Accounts Put Request

## Structure

`AccountsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `account` | [`?AccountsPutRequestSchemaProperties`](../../doc/models/accounts-put-request-schema-properties.md) | Optional | An object representing details of the Account, including the type of Account (method), Account number, and routing code. | getAccount(): ?AccountsPutRequestSchemaProperties | setAccount(?AccountsPutRequestSchemaProperties account): void |
| `name` | `?string` | Optional | A client-supplied name for this bank account.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A client-supplied description for this bank account.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `primary` | [`?int(AccountPrimaryEnum)`](../../doc/models/account-primary-enum.md) | Optional | Indicates whether the Account is the primary Account for the associated Entity.<br>Only one Account associated with each Entity can be the primary Account.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not primary**<br>- `1` - **Primary**<br></details><br>**Default**: `AccountPrimaryEnum::NOTPRIMARY`<br> | getPrimary(): ?int | setPrimary(?int primary): void |
| `type` | [`?string(AccountTypeEnum)`](../../doc/models/account-type-enum.md) | Optional | The type of financial account: debit, credit, or both.<br><br><details><br><summary>Valid Values</summary><br>- `all` - **Debit/checking and credit**<br>- `credit` - **Credit only**<br>- `debit` - **Debit/checking only**<br></details><br>**Default**: `AccountTypeEnum::ALL`<br> | getType(): ?string | setType(?string type): void |
| `status` | [`?int(AccountStatusEnum)`](../../doc/models/account-status-enum.md) | Optional | The status of the Account.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Ready.**<br>- `1` - **Ready.**<br>- `2` - **Challenged.**<br>- `3` - **Verified.**<br>- `4` - **Manual.**<br></details><br>**Default**: `AccountStatusEnum::NOTREADY`<br> | getStatus(): ?int | setStatus(?int status): void |
| `expiration` | `?string` | Optional | The expiration date of the related debit account in MMYY format, for example, `0118` for January 2018 or `0225` for February 2025. | getExpiration(): ?string | setExpiration(?string expiration): void |
| `mask` | `?string` | Optional | The account number mask, showing the last four digits of the account number. | getMask(): ?string | setMask(?string mask): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "id": "t1_act_5a1ef5e55656698eefaf8b6",
  "entity": "t1_ent_5a1pf5a1234531155a12345",
  "primary": 1,
  "name": "Bank Account Name",
  "description": "Bank account description",
  "account": {
    "method": 8,
    "routing": "1",
    "number": "2"
  },
  "currency": "USD",
  "type": "all",
  "status": 1,
  "expiration": "0118",
  "mask": "2345",
  "inactive": 0,
  "frozen": 0
}
```

