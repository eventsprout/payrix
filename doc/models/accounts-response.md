
# Accounts Response

## Structure

`AccountsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity associated with this Account. | getEntity(): | setEntity( entity): void |
| `account` | string\|[AccountPayment](../../doc/models/account-payment.md)\|null | Optional | The identifier of the Payment associated with this Account. | getAccount(): | setAccount( account): void |
| `token` | `?string` | Optional | A unique token that can be used to refer to this Account in other parts of the API. | getToken(): ?string | setToken(?string token): void |
| `name` | `?string` | Optional | A client-supplied name for this bank account.<br>This field is stored as a string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A client-supplied description for this bank account.<br>This field is stored as a string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `primary` | [`?int(AccountPrimaryEnum)`](../../doc/models/account-primary-enum.md) | Optional | Indicates whether the Account is the primary Account for the associated Entity.<br>Only one Account associated with each Entity can be the primary Account.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not primary**<br>- `1` - **Primary**<br></details><br>**Default**: `AccountPrimaryEnum::NOTPRIMARY`<br> | getPrimary(): ?int | setPrimary(?int primary): void |
| `type` | [`?string(AccountTypeEnum)`](../../doc/models/account-type-enum.md) | Optional | The type of financial account: debit, credit, or both.<br><br><details><br><summary>Valid Values</summary><br>- `all` - **Debit/checking and credit**<br>- `credit` - **Credit only**<br>- `debit` - **Debit/checking only**<br></details><br>**Default**: `AccountTypeEnum::ALL`<br> | getType(): ?string | setType(?string type): void |
| `status` | [`?int(AccountStatusEnum)`](../../doc/models/account-status-enum.md) | Optional | The status of the Account.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Ready.**<br>- `1` - **Ready.**<br>- `2` - **Challenged.**<br>- `3` - **Verified.**<br>- `4` - **Manual.**<br></details><br>**Default**: `AccountStatusEnum::NOTREADY`<br> | getStatus(): ?int | setStatus(?int status): void |
| `reserved` | [`?int(AccountsReservedEnum)`](../../doc/models/accounts-reserved-enum.md) | Optional | Indicates whether the Account is reserved and the action that will be taken as a result.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **No reserve.**<br>- `1` - **Block transaction, will never be processed. The Entity is sent to the manual review queue..**<br>- `3` - **Hold transaction, will not be captured.**<br>- `4` - **Reserve transaction, funds should be reserved.**<br>- `5` - **Block current activity, no change for merchant.**<br>- `6` - **Passed decision(s). Will not be set anywhere, will only be used for integration purposes.**<br>- `7` - **We did not have policies to process.**<br>- `8` - **We onboard the merchant and wait for manual check later.**<br>- `9` - **Schedule the automatic release of the reserve.**<br>- `10` - **Hold transaction, will not be captured. Automatic release when the associated sale is done.**<br></details><br> | getReserved(): ?int | setReserved(?int reserved): void |
| `checkStage` | [`?string(AccountCheckStageEnum)`](../../doc/models/account-check-stage-enum.md) | Optional | The last stage completed for risk.<br><br><details><br><summary>Valid Values</summary><br>- `createAccount` - **Create Account**<br></details><br> | getCheckStage(): ?string | setCheckStage(?string checkStage): void |
| `expiration` | `?string` | Optional | The expiration date of the related debit account.<br>The date is specified as a four-digit string in MMYY format, for example, `0118` for January 2018. | getExpiration(): ?string | setExpiration(?string expiration): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The currency of this Account. The default is `USD`. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `publicToken` | `?string` | Optional | The token received from the Plaid account connection process. | getPublicToken(): ?string | setPublicToken(?string publicToken): void |
| `mask` | `?string` | Optional | The account number mask, showing the last four digits of the account number. | getMask(): ?string | setMask(?string mask): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `plaidAccountId` | `?string` | Optional | The account identifier that is returned by the Plaid flow. | getPlaidAccountId(): ?string | setPlaidAccountId(?string plaidAccountId): void |
| `updateMethod` | [`?string(AccountsUpdateMethodEnum)`](../../doc/models/accounts-update-method-enum.md) | Optional | The method used to update the account.<br><br><details><br><summary>Valid Values</summary><br>- `NOC` - **Notification of change**<br>- `PLAID` - **Plaid.**<br>- `MANUAL` - **Manual**<br></details><br> | getUpdateMethod(): ?string | setUpdateMethod(?string updateMethod): void |
| `changeRequests` | [`?(ChangeRequest[])`](../../doc/models/change-request.md) | Optional | - | getChangeRequests(): ?array | setChangeRequests(?array changeRequests): void |
| `paymentUpdates` | [`?(PaymentUpdatesResponse[])`](../../doc/models/payment-updates-response.md) | Optional | - | getPaymentUpdates(): ?array | setPaymentUpdates(?array paymentUpdates): void |
| `payouts` | [`?(PayoutsResponse[])`](../../doc/models/payouts-response.md) | Optional | - | getPayouts(): ?array | setPayouts(?array payouts): void |

## Example (as JSON)

```json
{
  "primary": 0,
  "type": "all",
  "status": 0,
  "currency": "USD",
  "inactive": 0,
  "frozen": 0,
  "id": "id4",
  "created": "created4",
  "modified": "modified2",
  "creator": "String3",
  "modifier": "modifier8"
}
```

