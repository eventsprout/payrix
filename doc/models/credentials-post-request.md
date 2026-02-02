
# Credentials Post Request

## Structure

`CredentialsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entity` | `string` | Required | The identifier of the Entity that this Credential resource belongs to. | getEntity(): string | setEntity(string entity): void |
| `name` | `?string` | Optional | The name of this Credential resource.<br>This field is stored as a text string and must be between 1 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Credential resource.<br>This field is stored as a text string and must be between 1 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `username` | `string` | Required | The username to use when authenticating to the integration associated with this Credential resource.<br>This field is stored as a text string and must be between 1 and 50 characters long. | getUsername(): string | setUsername(string username): void |
| `password` | `?string` | Optional | The password to use when authenticating to the integration associated with this Credential resource.<br>This field is stored as a text string and must be between 1 and 50 characters long. | getPassword(): ?string | setPassword(?string password): void |
| `connectUsername` | `?string` | Optional | The username to use when connecting to the integration associated with this Credential resource.<br>This field is stored as a text string and must be between 1 and 50 characters long.<br>This field is only necessary when it is required by the integration. | getConnectUsername(): ?string | setConnectUsername(?string connectUsername): void |
| `connectPassword` | `?string` | Optional | The password to use when connecting to the integration associated with this Credential resource.<br>This field is stored as a text string and must be between 1 and 50 characters long.<br>This field is only necessary when it is required by the integration. | getConnectPassword(): ?string | setConnectPassword(?string connectPassword): void |
| `integration` | [`string(CredentialIntegrationEnum)`](../../doc/models/credential-integration-enum.md) | Required | The payment platform integration using credential logins.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **Apple API**<br>- `ELAVON` - **Elavon API**<br><br>- `FEDACH` - **FedACH Account Integration**<br><br>- `FIRSTDATA` - **FirstData / Clover Integration**<br><br>- `NEUTRINO` - **Neutrino eCommerce Integration**<br><br>- `OFAC` - **Office of Foreign Assets Control Sanctions**<br><br>- `PAYRIX` - **Payrix API**<br><br>- `PLAID` - **Plaid Account Integration**<br><br>- `SIFT` - **Sift Fraud Management**<br><br>- `SOCURE` - **Socure ID Verification**<br><br>- `SOUNDPAYMENTS` - **Sound Payments POS**<br><br>- `TDBANK` - **TD Bank Platform**<br><br>- `VANTIV` - **WorldPay / Vantiv eComm Platform**<br><br>- `VCORE` - **WorldPay / Vantiv Core Platform**<br><br>- `WEBSHIELD` - **Web Shield Merchant Monitoring**<br><br>- `WELLSACH` - **Wells Fargo Merchant Services ACH Processor.**<br><br>- `WELLSFARGO` - **Wells Fargo Merchant Services Payment Processor**<br><br>- `WFSINGLE` - **Wells Fargo Single Payment Processors**<br><br></details><br> | getIntegration(): string | setIntegration(string integration): void |
| `type` | [`string(CredentialTypeEnum)`](../../doc/models/credential-type-enum.md) | Required | The type of Transaction.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Credit Card Only:** Sale Transaction. Processes a sale and charges the customer.<br>- `2` - **Credit Card Only:** Auth Transaction. Authorizes and holds the requested total on the credit card.<br>- `3` - **Credit Card Only:** Capture Transaction. Finalizes a prior Auth Transaction and charges the customer.<br>- `4` - **Credit Card Only:** Reverse Authorization. Reverses a prior Auth or Sale Transaction and releases the credit hold.<br>- `5` - **Credit Card Only:** Refund Transaction. Refunds a prior Capture or Sale Transaction (total may be specified for a partial refund).<br>- `7` - **Echeck Only:** Echeck Sale Transaction. Sale Transaction for ECheck payment.<br>- `8` - **ECheck Only:** ECheck Refund Transaction. Refund Transaction for prior ECheck Sale Transaction.<br>- `11` - **Echeck Only:** Echeck Redeposit Transaction. Attempt to redeposit a prior failed eCheck Sale Transaction.<br>- `12` - **Echeck Only:** Echeck Account Verification Transaction. Attempt to verify eCheck payment details.<br></details><br> | getType(): string | setType(string type): void |
| `secret` | `?string` | Optional | The secret resource identifier to use when connecting using this Credential.<br>This field is only necessary when a private key is required by the integration. | getSecret(): ?string | setSecret(?string secret): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "entity": "t1_ent_67e152cfd598c814ed8f2e0",
  "username": "JDoe123",
  "integration": "VANTIV",
  "type": "transaction",
  "name": "name of Credential resource",
  "description": "description of Credential resource",
  "password": "password",
  "connectUsername": "username connecting to integration",
  "connectPassword": "password",
  "secret": "secret resource identifier",
  "inactive": 0,
  "frozen": 0
}
```

