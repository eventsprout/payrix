
# Apple Pay for Merchant List Post Request

## Structure

`ApplePayForMerchantListPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantIdDomainPairs` | [`?(AppleDomainsMassEnablementDataPreviewItem[])`](../../doc/models/apple-domains-mass-enablement-data-preview-item.md) | Optional | - | getMerchantIdDomainPairs(): ?array | setMerchantIdDomainPairs(?array merchantIdDomainPairs): void |

## Example (as JSON)

```json
{
  "merchantIdDomainPairs": [
    {
      "merchantId": "merchantId2",
      "domain": "domain2"
    },
    {
      "merchantId": "merchantId2",
      "domain": "domain2"
    },
    {
      "merchantId": "merchantId2",
      "domain": "domain2"
    }
  ]
}
```

