
# Configurations Response

## Structure

`ConfigurationsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that owns this configuration resource. | getLogin(): | setLogin( login): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity associated with this configuration resource. | getEntity(): | setEntity( entity): void |
| `org` | string\|[OrgsResponse](../../doc/models/orgs-response.md)\|null | Optional | The identifier of the Org associated with this configuration resource. | getOrg(): | setOrg( org): void |
| `division` | string\|[DivisionsResponse](../../doc/models/divisions-response.md)\|null | Optional | The identifier of the Division associated with this configuration resource. | getDivision(): | setDivision( division): void |
| `partition` | string\|[PartitionsResponse](../../doc/models/partitions-response.md)\|null | Optional | The identifier of the Partition associated with this configuration resource. | getPartition(): | setPartition( partition): void |
| `integration` | [`?string(ConfigurationIntegrationEnum)`](../../doc/models/configuration-integration-enum.md) | Optional | The integration associated with this configuration resource.<br><br><details><br><summary>Valid Values</summary><br>- `ACH` - **ACH integration.**<br>- `APPLE` - **APPLE integration.**<br>- `ELAVON` - **ELAVON integration.**<br>- `FEDACH` - **FEDACH integration.**<br>- `FIRSTDATA` - **FIRSTDATA integration.**<br>- `LEGITSCRIPT` - **LEGITSCRIPT integration.**<br>- `NEUTRINO` - **NEUTRINO integration.**<br>- `OFAC` - **OFAC integration.**<br>- `OMNITOKEN` - **OMNITOKEN integration.**<br>- `PAYRIX` - **PAYRIX integration.**<br>- `PLAID` - **PLAID integration.**<br>- `PUSHY` - **PUSHY integration.**<br>- `SAFERPAYMENT` - **SAFERPAYMENT integration.**<br>- `SIFT` - **SIFT integration.**<br>- `SOCURE` - **SOCURE integration.**<br>- `SOUNDPAYMENTS` - **SOUNDPAYMENTS integration.**<br>- `TDBANK` - **TDBANK integration.**<br>- `TDBANKCA` - **TDBANKCA integration.**<br>- `VANTIV` - **VANTIV integration.**<br>- `VCORE` - **VCORE integration.**<br>- `WEBSHIELD` - **WEBSHIELD integration.**<br>- `WELLSACH` - **WELLSACH integration.**<br>- `WELLSFARGO` - **WELLSFARGO integration.**<br>- `WFSINGLE` - **WFSINGLE integration.**<br>- `WORLDPAY` - **WORLDPAY integration.**<br></details><br> | getIntegration(): ?string | setIntegration(?string integration): void |
| `name` | [`?string(ConfigurationsNameEnum)`](../../doc/models/configurations-name-enum.md) | Optional | The name of this configuration resource.<br><br><details><br><summary>Valid Values</summary><br>- `account` - **Account. The specified configuration will be used for bank accounts integrations.**<br>- `batchTxn` - **BatchTxn. The specified configuration will be used for processing transaction batches.**<br>- `binReport` - **BinReport. The specified configuration will be used for bin reports integrations.**<br>- `board` - **Board. The specified configuration will be used for boarding merchants.**<br>- `chargeback` - **Chargeback. The specified configuration will be used for everything related to chargebacks.**<br>- `decision` - **Decision. The specified configuration will be used for everything related to decisions.**<br>- `decisionBoard` - **This holds configuration for running boarding decision policy on entity through Risk MS.**<br>- `decisionTxn` - **DecisionTxn is used for running transaction decision policy through the Risk MS.**<br>- `echeckTxn` - **EcheckTxn. The specified configuration will be used to get reports of echeck transactions as well as getting additional information about those transactions.**<br>- `encryption` - **Holds the configuration for running Google and Apple Pay encryption/decryption through the Payrix Encryption Service.**<br>- `omnitoken` - **Holds the configuration parameters for omnitoken services.**<br>- `onlineTxn` - **OnlineTxn. The specified configuration will be used to process transactions online without a batch.**<br>- `onlineTxnSocket` - **OnlineTxnSocket.**<br>- `paymentUpdates` - **PaymentUpdates.**<br>- `payout` - **Payout. The specified configuration will be used for everything related to payouts.**<br>- `payoutCredit` - **Holds the configuration for processing payout credit through the integration service.**<br>- `payoutDebit` - **Holds the configuration for processing payouts debit through the integration service.**<br>- `plaid` - **Holds the configuration parameters for Plaid services (connecting accounts, getting identity, etc.).**<br>- `reports` - **Reports. The specified configuration will be used to import processed transactions.**<br>- `register` - **Register.**<br>- `saferPayment` - **Holds the configuration parameters for safer payment VAS.**<br>- `unregister` - **Unregister.**<br>- `varsheetRetrieval` - **Holds the configuration parameters for varsheet retrieval.**<br>- `watchlist` - **Watchlist. The specified configuration will be used to receive a watch list by the OFAC.**<br></details><br> | getName(): ?string | setName(?string name): void |
| `type` | [`?string(ConfigurationTypeEnum)`](../../doc/models/configuration-type-enum.md) | Optional | The type of configuration resource.<br><br><details><br><summary>Valid Values</summary><br>- `create` - **Create type of configuration.**<br>- `read` - **Read type of configuration.**<br>- `update` - **Update type of configuration.**<br>- `delete` - **Delete type of configuration.**<br></details><br> | getType(): ?string | setType(?string type): void |
| `options` | `?string` | Optional | The options used for this configuration integration. | getOptions(): ?string | setOptions(?string options): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `configurationStages` | [`?(ConfigurationStagesResponse[])`](../../doc/models/configuration-stages-response.md) | Optional | - | getConfigurationStages(): ?array | setConfigurationStages(?array configurationStages): void |

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

