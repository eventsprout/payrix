
# Credentials Response

## Structure

`CredentialsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity that this Credential resource belongs to. | getEntity(): | setEntity( entity): void |
| `name` | `?string` | Optional | The name of this Credential resource.<br>This field is stored as a text string and must be between 1 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Credential resource.<br>This field is stored as a text string and must be between 1 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `username` | `?string` | Optional | The username to use when authenticating to the integration associated with this Credential resource.<br>This field is stored as a text string and must be between 1 and 50 characters long. | getUsername(): ?string | setUsername(?string username): void |
| `password` | `?string` | Optional | The password to use when authenticating to the integration associated with this Credential resource.<br>This field is stored as a text string and must be between 1 and 50 characters long. | getPassword(): ?string | setPassword(?string password): void |
| `connectUsername` | `?string` | Optional | The username to use when connecting to the integration associated with this Credential resource.<br>This field is stored as a text string and must be between 1 and 50 characters long.<br>This field is only necessary when it is required by the integration. | getConnectUsername(): ?string | setConnectUsername(?string connectUsername): void |
| `connectPassword` | `?string` | Optional | The password to use when connecting to the integration associated with this Credential resource.<br>This field is stored as a text string and must be between 1 and 50 characters long.<br>This field is only necessary when it is required by the integration. | getConnectPassword(): ?string | setConnectPassword(?string connectPassword): void |
| `integration` | [`?string(CredentialIntegrationEnum)`](../../doc/models/credential-integration-enum.md) | Optional | The payment platform integration using credential logins.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **Apple API**<br>- `ELAVON` - **Elavon API**<br><br>- `FEDACH` - **FedACH Account Integration**<br><br>- `FIRSTDATA` - **FirstData / Clover Integration**<br><br>- `NEUTRINO` - **Neutrino eCommerce Integration**<br><br>- `OFAC` - **Office of Foreign Assets Control Sanctions**<br><br>- `PAYRIX` - **Payrix API**<br><br>- `PLAID` - **Plaid Account Integration**<br><br>- `SIFT` - **Sift Fraud Management**<br><br>- `SOCURE` - **Socure ID Verification**<br><br>- `SOUNDPAYMENTS` - **Sound Payments POS**<br><br>- `TDBANK` - **TD Bank Platform**<br><br>- `VANTIV` - **WorldPay / Vantiv eComm Platform**<br><br>- `VCORE` - **WorldPay / Vantiv Core Platform**<br><br>- `WEBSHIELD` - **Web Shield Merchant Monitoring**<br><br>- `WELLSACH` - **Wells Fargo Merchant Services ACH Processor.**<br><br>- `WELLSFARGO` - **Wells Fargo Merchant Services Payment Processor**<br><br>- `WFSINGLE` - **Wells Fargo Single Payment Processors**<br><br></details><br> | getIntegration(): ?string | setIntegration(?string integration): void |
| `type` | [`?string(CredentialTypeEnum)`](../../doc/models/credential-type-enum.md) | Optional | The type of Transaction.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Credit Card Only:** Sale Transaction. Processes a sale and charges the customer.<br>- `2` - **Credit Card Only:** Auth Transaction. Authorizes and holds the requested total on the credit card.<br>- `3` - **Credit Card Only:** Capture Transaction. Finalizes a prior Auth Transaction and charges the customer.<br>- `4` - **Credit Card Only:** Reverse Authorization. Reverses a prior Auth or Sale Transaction and releases the credit hold.<br>- `5` - **Credit Card Only:** Refund Transaction. Refunds a prior Capture or Sale Transaction (total may be specified for a partial refund).<br>- `7` - **Echeck Only:** Echeck Sale Transaction. Sale Transaction for ECheck payment.<br>- `8` - **ECheck Only:** ECheck Refund Transaction. Refund Transaction for prior ECheck Sale Transaction.<br>- `11` - **Echeck Only:** Echeck Redeposit Transaction. Attempt to redeposit a prior failed eCheck Sale Transaction.<br>- `12` - **Echeck Only:** Echeck Account Verification Transaction. Attempt to verify eCheck payment details.<br></details><br> | getType(): ?string | setType(?string type): void |
| `secret` | string\|[SecretsResponse](../../doc/models/secrets-response.md)\|null | Optional | The secret resource identifier to use when connecting using this Credential.<br>This field is only necessary when a private key is required by the integration. | getSecret(): | setSecret( secret): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id4",
  "created": "created4",
  "modified": "modified2",
  "creator": "String3",
  "modifier": "modifier8"
}
```

