
# Secrets Response

## Structure

`SecretsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that owns this secret resource. | getLogin(): | setLogin( login): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity associated with this secret. | getEntity(): | setEntity( entity): void |
| `org` | string\|[OrgsResponse](../../doc/models/orgs-response.md)\|null | Optional | The identifier of the Org associated with this secret. | getOrg(): | setOrg( org): void |
| `division` | string\|[DivisionsResponse](../../doc/models/divisions-response.md)\|null | Optional | The identifier of the Division associated with this secret. | getDivision(): | setDivision( division): void |
| `partition` | string\|[PartitionsResponse](../../doc/models/partitions-response.md)\|null | Optional | The identifier of the Partition associated with this secret. | getPartition(): | setPartition( partition): void |
| `type` | [`?string(SecretTypeEnum)`](../../doc/models/secret-type-enum.md) | Optional | The type of secret.<br><br><details><br><summary>Valid Values</summary><br>- `baseKey` - **Base Derivation Key.**<br>- `sftp` - **SFTP Server Key.**<br>- `publicKey` - **Public Key.**<br>- `privateKey` - **Private Key.**<br>- `ecPrivateKey` - **Elliptic Curve Private Key.**<br>- `apikey` - **API Key.**<br>- `oldPrivateKey` - **Expired Private Key.**<br></details><br> | getType(): ?string | setType(?string type): void |
| `platform` | [`?string(SecretsPlatformEnum)`](../../doc/models/secrets-platform-enum.md) | Optional | The platform used to process this Transaction.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **Apple Payment Processor**<br>- `ELAVON` - **ELAVON Payment Processor**<br>- `FIRSTDATA` - **FirstData Payment Processor**<br>- `GOOGLE` - **Google Payment Processor**<br>- `VANTIV` - **WorldPay / Vantiv eComm Payment Processor (VAP)**<br>- `VCORE` - **WorldPay / Vantiv Core Payment Processor**<br>- `WELLSACH` - **Wells Fargo Merchant Services Payment Processor (ACH)**<br>- `WELLSFARGO` - **Wells Fargo Merchant Services Payment Processor**<br>- `WFSINGLE` - **Wells Fargo Single Payment Processor**<br>- `WORLDPAY` - **WORLDPAY**<br>- `TDBANKCA` - **TDBANKCA**<br></details><br> | getPlatform(): ?string | setPlatform(?string platform): void |
| `name` | `?string` | Optional | The name of this Secret.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Secret.<br>This field is stored as a text string and must be between 0 and 500 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `key` | `?string` | Optional | The actual key or the indicator of which key to use.<br>This field is stored as a text string and must be between 1 and 5000 characters long. | getKey(): ?string | setKey(?string key): void |
| `locked` | [`?int(SecretLockedEnum)`](../../doc/models/secret-locked-enum.md) | Optional | Whether this secret is locked or not.<br>If it is locked, then the value of this type of secret will prevail.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Locked**<br>- `1` - **Locked**<br></details><br>**Default**: `SecretLockedEnum::NOTLOCKED`<br> | getLocked(): ?int | setLocked(?int locked): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "locked": 0,
  "inactive": 0,
  "frozen": 0,
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

