
# Funding Parameters Response

## Structure

`FundingParametersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that owns this fundingParameter resource. | getLogin(): | setLogin( login): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity associated with this fundingParameter. | getEntity(): | setEntity( entity): void |
| `org` | string\|[OrgsResponse](../../doc/models/orgs-response.md)\|null | Optional | The identifier of the Org associated with this fundingParameter. | getOrg(): | setOrg( org): void |
| `division` | string\|[DivisionsResponse](../../doc/models/divisions-response.md)\|null | Optional | The identifier of the Division associated with this fundingParameter. | getDivision(): | setDivision( division): void |
| `partition` | string\|[PartitionsResponse](../../doc/models/partitions-response.md)\|null | Optional | The identifier of the Partition associated with this fundingParameter. | getPartition(): | setPartition( partition): void |
| `platform` | [`?string(FundingParameterPlatformEnum)`](../../doc/models/funding-parameter-platform-enum.md) | Optional | The identifier of the Platform associated with this fundingParameter.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **The Apple Payment Processor.**<br>- `ELAVON` - **The Elavon processor.**<br>- `FIRSTDATA` - **The First Data processor.**<br>- `GOOGLE` - **The Google Payment Processor.**<br>- `VANTIV` - **The WorldPay (aka Vantiv or Litle) eComm (aka VAP) processor.**<br>- `VCORE` - **The WorldPay (aka Vantiv) Core processor.**<br>- `WELLSACH` - **The Wells Fargo ACH processor.**<br>- `WELLSFARGO` - **The Wells Fargo Merchant Services processor.**<br>- `WFSINGLE` - **The WFSINGLE processor.**<br>- `WORLDPAY` - **The WORLDPAY processor.**<br>- `TDBANKCA` - **External funding with TD Bank Canada via the Operating Account.**<br>- `all` - **All Platform Processor.**<br></details><br>**Default**: `FundingParameterPlatformEnum::ALL`<br> | getPlatform(): ?string | setPlatform(?string platform): void |
| `type` | [`?string(FundingParameterTypeEnum)`](../../doc/models/funding-parameter-type-enum.md) | Optional | The type of fundingParameter that we will be configuring.<br><br><details><br><summary>Valid Values</summary><br>- `agentCnp` - **The id to use for boarding merchants that are card not present**<br>- `agentCp` - **The id to use for boarding merchants that are card present**<br>- `creditCompanyId` - **Company credit identifier**<br>- `debitCompanyId` - **Company debit identifier**<br>- `delay` - **Delay**<br>- `offDaysAdditionalDelay` - **Additional delay for off days.**<br>- `settlementAccountTransferDelay` - **The amount of time in days to wait before issuing a transfer, will be counted from the date of the first item within the total settlement amount.**<br>- `settlementAccountTransferEnabled` - **Indication if during settlements credits should be transferred from the merchant's operating account.**<br>- `settlementAccountTransferFloat` - **Additional amount to keep at the merchant's operating account.**<br>- `settlementAccountTransferMaximum` - **The maximum amount needed to transfer funds from merchant's operating account.**<br>- `settlementAccountTransferMinimum` - **The minimum amount needed to transfer funds from the merchant's operating account.**<br>- `settlementAccountTransferPercent` - **The percent amount to transfer from the total settlement amount.**<br>- `customBatchCloseTime` - **The specified time to close a batch**<br>- `lateFunding` - **2 am late funding cutoff time**<br>- `5AmFunding` - **5 am funding cutoff time**<br></details><br> | getType(): ?string | setType(?string type): void |
| `value` | `?string` | Optional | The value of this type of fundingParameter. | getValue(): ?string | setValue(?string value): void |
| `paymentMethods` | [`?string(FundingParameterPaymentMethodsEnum)`](../../doc/models/funding-parameter-payment-methods-enum.md) | Optional | The payment methods that the fundingParameter should apply to.<br><br><details><br><summary>Valid Values</summary><br>- `amex` - **American Express**<br>- `visa` - **Visa**<br>- `masterCard` - **MasterCard**<br>- `diners` - **Diners Club**<br>- `discover` - **Discover**<br>- `paypal` - **PayPal**<br>- `debit` - **Debit**<br>- `checking` - **Personal checking**<br>- `savings` - **Personal savings**<br>- `corpChecking` - **Corporate checking**<br>- `corpSavings` - **Corporate savings**<br>- `gift` - **Gift card**<br>- `ebt` - **EBT (Electronic Benefits Transfer)**<br>- `wic` - **WIC (Women, Infants and Children)**<br></details><br> | getPaymentMethods(): ?string | setPaymentMethods(?string paymentMethods): void |
| `locked` | [`?int(FundingParameterLockedEnum)`](../../doc/models/funding-parameter-locked-enum.md) | Optional | Whether this fundingParameter is locked or not.<br>If it is locked, then the value of this type of fundingParameter will prevail.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **OFF**<br>- `1` - **ON**<br></details><br>**Default**: `FundingParameterLockedEnum::OFF`<br> | getLocked(): ?int | setLocked(?int locked): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "platform": "all",
  "locked": 0,
  "inactive": 0,
  "frozen": 0,
  "id": "id4",
  "created": "created4",
  "modified": "modified2",
  "creator": "String3",
  "modifier": "modifier8"
}
```

