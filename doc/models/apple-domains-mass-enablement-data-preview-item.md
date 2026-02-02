
# Apple Domains Mass Enablement Data Preview Item

## Structure

`AppleDomainsMassEnablementDataPreviewItem`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantId` | `?string` | Optional | The Payrix Pro Merchant ID associated with the domain or domains being verified for Apple Pay. | getMerchantId(): ?string | setMerchantId(?string merchantId): void |
| `domain` | `?string` | Optional | The Fully Qualified Domain Name (FQDN) associated with the registered Merchant. | getDomain(): ?string | setDomain(?string domain): void |

## Example (as JSON)

```json
{
  "merchantId": "merchantId6",
  "domain": "domain6"
}
```

