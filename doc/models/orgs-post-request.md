
# Orgs Post Request

## Structure

`OrgsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `?string` | Optional | The Login that owns this Org. | getLogin(): ?string | setLogin(?string login): void |
| `name` | `?string` | Optional | The name of this Org.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Org.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `billings` | [`?(BillingsPostRequest[])`](../../doc/models/billings-post-request.md) | Optional | - | getBillings(): ?array | setBillings(?array billings): void |
| `feeModifiers` | [`?(FeeModifiersPostRequest[])`](../../doc/models/fee-modifiers-post-request.md) | Optional | - | getFeeModifiers(): ?array | setFeeModifiers(?array feeModifiers): void |
| `fees` | [`?(FeesPostRequest[])`](../../doc/models/fees-post-request.md) | Optional | - | getFees(): ?array | setFees(?array fees): void |
| `invoiceParameters` | [`?(InvoiceParametersPostRequest[])`](../../doc/models/invoice-parameters-post-request.md) | Optional | - | getInvoiceParameters(): ?array | setInvoiceParameters(?array invoiceParameters): void |
| `orgEntities` | [`?(OrgEntitiesPostRequest[])`](../../doc/models/org-entities-post-request.md) | Optional | - | getOrgEntities(): ?array | setOrgEntities(?array orgEntities): void |
| `payoutFlows` | [`?(PayoutFlowsPostRequest[])`](../../doc/models/payout-flows-post-request.md) | Optional | - | getPayoutFlows(): ?array | setPayoutFlows(?array payoutFlows): void |
| `profitShares` | [`?(ProfitSharesPostRequest[])`](../../doc/models/profit-shares-post-request.md) | Optional | - | getProfitShares(): ?array | setProfitShares(?array profitShares): void |
| `reserves` | [`?(ReservesPostRequest[])`](../../doc/models/reserves-post-request.md) | Optional | - | getReserves(): ?array | setReserves(?array reserves): void |
| `secrets` | [`?(SecretsPostRequest[])`](../../doc/models/secrets-post-request.md) | Optional | - | getSecrets(): ?array | setSecrets(?array secrets): void |

## Example (as JSON)

```json
{
  "login": "t1_log_656d51cd565edf13a27c494",
  "name": "Leora44",
  "description": "description of Org",
  "billings": [
    {
      "login": "login8",
      "entity": "entity6",
      "forentity": "forentity0",
      "org": "org4",
      "division": "division8",
      "partition": "partition0",
      "description": "description8",
      "schedule": "days",
      "start": 18,
      "collectionFactor": "days",
      "currency": "MWK"
    }
  ],
  "feeModifiers": [
    {
      "fee": "fee4",
      "entity": "entity0",
      "org": "org8",
      "fromentity": "fromentity4",
      "markupUm": 1,
      "markupAmount": 38
    },
    {
      "fee": "fee4",
      "entity": "entity0",
      "org": "org8",
      "fromentity": "fromentity4",
      "markupUm": 1,
      "markupAmount": 38
    },
    {
      "fee": "fee4",
      "entity": "entity0",
      "org": "org8",
      "fromentity": "fromentity4",
      "markupUm": 1,
      "markupAmount": 38
    }
  ]
}
```

