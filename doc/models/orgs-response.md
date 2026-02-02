
# Orgs Response

## Structure

`OrgsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The Login that owns this Org. | getLogin(): | setLogin( login): void |
| `name` | `?string` | Optional | The name of this Org.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Org.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `defaultFeeFromEntity` | `?string` | Optional | This is used to specify a default fee for a group. | getDefaultFeeFromEntity(): ?string | setDefaultFeeFromEntity(?string defaultFeeFromEntity): void |
| `aggregations` | [`?(AggregationsResponse[])`](../../doc/models/aggregations-response.md) | Optional | - | getAggregations(): ?array | setAggregations(?array aggregations): void |
| `billingModifiers` | [`?(BillingModifiersResponse[])`](../../doc/models/billing-modifiers-response.md) | Optional | - | getBillingModifiers(): ?array | setBillingModifiers(?array billingModifiers): void |
| `billings` | [`?(BillingsResponse[])`](../../doc/models/billings-response.md) | Optional | - | getBillings(): ?array | setBillings(?array billings): void |
| `decisions` | [`?(DecisionsResponse[])`](../../doc/models/decisions-response.md) | Optional | - | getDecisions(): ?array | setDecisions(?array decisions): void |
| `embeddedFinance` | [`?(EmbeddedFinanceResponse[])`](../../doc/models/embedded-finance-response.md) | Optional | - | getEmbeddedFinance(): ?array | setEmbeddedFinance(?array embeddedFinance): void |
| `feeModifiers` | [`?(FeeModifiersResponse[])`](../../doc/models/fee-modifiers-response.md) | Optional | - | getFeeModifiers(): ?array | setFeeModifiers(?array feeModifiers): void |
| `fees` | [`?(FeesResponse[])`](../../doc/models/fees-response.md) | Optional | - | getFees(): ?array | setFees(?array fees): void |
| `invoiceParameters` | [`?(InvoiceParametersResponse[])`](../../doc/models/invoice-parameters-response.md) | Optional | - | getInvoiceParameters(): ?array | setInvoiceParameters(?array invoiceParameters): void |
| `orgEntities` | [`?(OrgEntitiesResponse[])`](../../doc/models/org-entities-response.md) | Optional | - | getOrgEntities(): ?array | setOrgEntities(?array orgEntities): void |
| `omniTokens` | [`?(OmniTokensResponse[])`](../../doc/models/omni-tokens-response.md) | Optional | - | getOmniTokens(): ?array | setOmniTokens(?array omniTokens): void |
| `payoutFlows` | [`?(PayoutFlowsResponse[])`](../../doc/models/payout-flows-response.md) | Optional | - | getPayoutFlows(): ?array | setPayoutFlows(?array payoutFlows): void |
| `profitShares` | [`?(ProfitSharesResponse[])`](../../doc/models/profit-shares-response.md) | Optional | - | getProfitShares(): ?array | setProfitShares(?array profitShares): void |
| `reserves` | [`?(ReservesResponse[])`](../../doc/models/reserves-response.md) | Optional | - | getReserves(): ?array | setReserves(?array reserves): void |
| `revenueBoosts` | [`?(RevenueBoostsResponse[])`](../../doc/models/revenue-boosts-response.md) | Optional | - | getRevenueBoosts(): ?array | setRevenueBoosts(?array revenueBoosts): void |
| `secrets` | [`?(SecretsResponse[])`](../../doc/models/secrets-response.md) | Optional | - | getSecrets(): ?array | setSecrets(?array secrets): void |
| `saferPayments` | [`?(SaferPaymentsResponse[])`](../../doc/models/safer-payments-response.md) | Optional | - | getSaferPayments(): ?array | setSaferPayments(?array saferPayments): void |

## Example (as JSON)

```json
{
  "id": "id4",
  "created": "created4",
  "modified": "modified2",
  "creator": "String3",
  "modifier": "modifier8"
}
```

