
# Accounts Post Request

A request body for creating new bank account information for one or more entities.

## Structure

`AccountsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entity` | `string` | Required | The identifier of the Entity associated with this Account. | getEntity(): string | setEntity(string entity): void |
| `account` | [`AccountsAccount`](../../doc/models/accounts-account.md) | Required | An object representing details of the Account, including the type of Account (method), Account number, and routing code. | getAccount(): AccountsAccount | setAccount(AccountsAccount account): void |
| `name` | `?string` | Optional | A client-supplied name for this bank account.<br>This field is stored as a string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A client-supplied description for this bank account.<br>This field is stored as a string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `primary` | [`?int(AccountPrimaryEnum)`](../../doc/models/account-primary-enum.md) | Optional | Indicates whether the Account is the primary Account for the associated Entity.<br>Only one Account associated with each Entity can be the primary Account.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not primary**<br>- `1` - **Primary**<br></details><br>**Default**: `AccountPrimaryEnum::NOTPRIMARY`<br> | getPrimary(): ?int | setPrimary(?int primary): void |
| `type` | [`?string(AccountTypeEnum)`](../../doc/models/account-type-enum.md) | Optional | The type of financial account: debit, credit, or both.<br><br><details><br><summary>Valid Values</summary><br>- `all` - **Debit/checking and credit**<br>- `credit` - **Credit only**<br>- `debit` - **Debit/checking only**<br></details><br>**Default**: `AccountTypeEnum::ALL`<br> | getType(): ?string | setType(?string type): void |
| `status` | [`?int(AccountStatusEnum)`](../../doc/models/account-status-enum.md) | Optional | The status of the Account.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Ready.**<br>- `1` - **Ready.**<br>- `2` - **Challenged.**<br>- `3` - **Verified.**<br>- `4` - **Manual.**<br></details><br>**Default**: `AccountStatusEnum::NOTREADY`<br> | getStatus(): ?int | setStatus(?int status): void |
| `expiration` | `?string` | Optional | The expiration date of the related debit account. The date is specified as a four-digit string in MMYY format, for example, `0118` for January 2018. | getExpiration(): ?string | setExpiration(?string expiration): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Required | The currency of this Account. The default is `USD`. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `publicToken` | `?string` | Optional | The token received from the Plaid account connection process. | getPublicToken(): ?string | setPublicToken(?string publicToken): void |
| `mask` | `?string` | Optional | The account number mask, showing the last four digits of the account number. | getMask(): ?string | setMask(?string mask): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `payouts` | [`?(PayoutPostRequest[])`](../../doc/models/payout-post-request.md) | Optional | - | getPayouts(): ?array | setPayouts(?array payouts): void |

## Example (as JSON)

```json
{
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
  "publicToken": "public-test-a12eeba1-1234-4567-af1g-d80cc1bfd713",
  "mask": "2345",
  "inactive": 0,
  "frozen": 0
}
```

