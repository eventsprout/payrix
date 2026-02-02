
# Divisions Response

## Structure

`DivisionsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The login ID of the user that owns this division record. | getLogin(): | setLogin( login): void |
| `name` | `?string` | Optional | The name of the division, which may be used for some white-label purposes | getName(): ?string | setName(?string name): void |
| `email` | `?string` | Optional | The white-labeled outgoing email for all automated emails generated throughout this division | getEmail(): ?string | setEmail(?string email): void |
| `saferPaymentNonComplianceFeeManaged` | [`?int(SaferPaymentNonComplianceFeeManagedModelEnum)`](../../doc/models/safer-payment-non-compliance-fee-managed-model-enum.md) | Optional | Whether SaferPayment Non-compliance fee management is enabled<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Disabled.**<br>- `1` - **Enabled.**<br></details><br> | getSaferPaymentNonComplianceFeeManaged(): ?int | setSaferPaymentNonComplianceFeeManaged(?int saferPaymentNonComplianceFeeManaged): void |
| `changeManagementEnabled` | [`?int(ChangeManagementEnabledEnum)`](../../doc/models/change-management-enabled-enum.md) | Optional | Whether change management is enabled.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Disabled**<br>- `1` - **Enabled**<br></details><br> | getChangeManagementEnabled(): ?int | setChangeManagementEnabled(?int changeManagementEnabled): void |
| `minPasswordLength` | `?int` | Optional | Minimum password length | getMinPasswordLength(): ?int | setMinPasswordLength(?int minPasswordLength): void |
| `minPasswordComplexity` | [`?int(MinPasswordComplexityEnum)`](../../doc/models/min-password-complexity-enum.md) | Optional | The minimum level of complexity that all passwords used in this Partition must have.<br>There are four complexity 'factors' that can be evaluated. These are the presence<br>of the following character types in the password: lowercase characters, uppercase<br>characters, integers, and special characters. For instance, the password '123a'<br>would get a complexity rating of '2', since it contains integers and lowercase characters.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Needs to include one type.**<br>- `2` - **Needs to include two types.**<br>- `3` - **Needs to include three types.**<br>- `4` - **Needs to include four types.**<br></details><br> | getMinPasswordComplexity(): ?int | setMinPasswordComplexity(?int minPasswordComplexity): void |
| `canUsePlaidWrapperMicroservice` | [`?int(DivisionsCanUsePlaidWrapperMicroserviceEnum)`](../../doc/models/divisions-can-use-plaid-wrapper-microservice-enum.md) | Optional | Describes if the user can use the Plaid Wrapper Microservice or not<br><br><details><br><summary>Valid Values</summary><br>- `0` - **No.**<br>- `1` - **Yes.**<br></details><br> | getCanUsePlaidWrapperMicroservice(): ?int | setCanUsePlaidWrapperMicroservice(?int canUsePlaidWrapperMicroservice): void |
| `simplifiedDepositEnabled` | [`?int(SimplifiedDepositEnabledEnum)`](../../doc/models/simplified-deposit-enabled-enum.md) | Optional | Allows automatic enablement of simplified deposits for new boardings and allows enablement of existing boardings. Restricted to admin.<br>Valid Values :  - `1` - **Enabled** | getSimplifiedDepositEnabled(): ?int | setSimplifiedDepositEnabled(?int simplifiedDepositEnabled): void |
| `aggregations` | [`?(AggregationsResponse[])`](../../doc/models/aggregations-response.md) | Optional | - | getAggregations(): ?array | setAggregations(?array aggregations): void |
| `billingModifiers` | [`?(BillingModifiersResponse[])`](../../doc/models/billing-modifiers-response.md) | Optional | - | getBillingModifiers(): ?array | setBillingModifiers(?array billingModifiers): void |
| `billings` | [`?(BillingsResponse[])`](../../doc/models/billings-response.md) | Optional | - | getBillings(): ?array | setBillings(?array billings): void |
| `configurations` | [`?(ConfigurationsResponse[])`](../../doc/models/configurations-response.md) | Optional | - | getConfigurations(): ?array | setConfigurations(?array configurations): void |
| `currencyRates` | [`?(CurrencyRatesResponse[])`](../../doc/models/currency-rates-response.md) | Optional | - | getCurrencyRates(): ?array | setCurrencyRates(?array currencyRates): void |
| `decisions` | [`?(DecisionsResponse[])`](../../doc/models/decisions-response.md) | Optional | - | getDecisions(): ?array | setDecisions(?array decisions): void |
| `embeddedFinance` | [`?(EmbeddedFinanceResponse[])`](../../doc/models/embedded-finance-response.md) | Optional | - | getEmbeddedFinance(): ?array | setEmbeddedFinance(?array embeddedFinance): void |
| `entityRoutes` | [`?(EntityRoutesResponse[])`](../../doc/models/entity-routes-response.md) | Optional | - | getEntityRoutes(): ?array | setEntityRoutes(?array entityRoutes): void |
| `feeModifiers` | [`?(FeeModifiersResponse[])`](../../doc/models/fee-modifiers-response.md) | Optional | - | getFeeModifiers(): ?array | setFeeModifiers(?array feeModifiers): void |
| `fundingParameters` | [`?(FundingParametersResponse[])`](../../doc/models/funding-parameters-response.md) | Optional | - | getFundingParameters(): ?array | setFundingParameters(?array fundingParameters): void |
| `hosts` | [`?(HostsResponse[])`](../../doc/models/hosts-response.md) | Optional | - | getHosts(): ?array | setHosts(?array hosts): void |
| `invoiceParameters` | [`?(InvoiceParametersResponse[])`](../../doc/models/invoice-parameters-response.md) | Optional | - | getInvoiceParameters(): ?array | setInvoiceParameters(?array invoiceParameters): void |
| `logins` | [`?(LoginsResponse[])`](../../doc/models/logins-response.md) | Optional | - | getLogins(): ?array | setLogins(?array logins): void |
| `mccs` | [`?(MccsResponse[])`](../../doc/models/mccs-response.md) | Optional | - | getMccs(): ?array | setMccs(?array mccs): void |
| `orgFlows` | [`?(OrgFlowsResponse[])`](../../doc/models/org-flows-response.md) | Optional | - | getOrgFlows(): ?array | setOrgFlows(?array orgFlows): void |
| `omniTokens` | [`?(OmniTokensResponse[])`](../../doc/models/omni-tokens-response.md) | Optional | - | getOmniTokens(): ?array | setOmniTokens(?array omniTokens): void |
| `parameters` | [`?(ParametersResponse[])`](../../doc/models/parameters-response.md) | Optional | - | getParameters(): ?array | setParameters(?array parameters): void |
| `payoutFlows` | [`?(PayoutFlowsResponse[])`](../../doc/models/payout-flows-response.md) | Optional | - | getPayoutFlows(): ?array | setPayoutFlows(?array payoutFlows): void |
| `pinlessDebitConversions` | [`?(PinlessDebitConversionsResponse[])`](../../doc/models/pinless-debit-conversions-response.md) | Optional | - | getPinlessDebitConversions(): ?array | setPinlessDebitConversions(?array pinlessDebitConversions): void |
| `profitShares` | [`?(ProfitSharesResponse[])`](../../doc/models/profit-shares-response.md) | Optional | - | getProfitShares(): ?array | setProfitShares(?array profitShares): void |
| `reserves` | [`?(ReservesResponse[])`](../../doc/models/reserves-response.md) | Optional | - | getReserves(): ?array | setReserves(?array reserves): void |
| `revenueBoosts` | [`?(RevenueBoostsResponse[])`](../../doc/models/revenue-boosts-response.md) | Optional | - | getRevenueBoosts(): ?array | setRevenueBoosts(?array revenueBoosts): void |
| `saferPayments` | [`?(SaferPaymentsResponse[])`](../../doc/models/safer-payments-response.md) | Optional | - | getSaferPayments(): ?array | setSaferPayments(?array saferPayments): void |
| `secrets` | [`?(SecretsResponse[])`](../../doc/models/secrets-response.md) | Optional | - | getSecrets(): ?array | setSecrets(?array secrets): void |
| `vendors` | [`?(VendorsResponse[])`](../../doc/models/vendors-response.md) | Optional | - | getVendors(): ?array | setVendors(?array vendors): void |

## Example (as JSON)

```json
{
  "id": "id8",
  "created": "created8",
  "modified": "modified6",
  "creator": "String7",
  "modifier": "modifier2"
}
```

