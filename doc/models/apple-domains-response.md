
# Apple Domains Response

## Structure

`AppleDomainsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `registeredMerchant` | string\|[MerchantsResponse](../../doc/models/merchants-response.md)\|null | Optional | The identifier of the Merchant registered with Apple Pay for this domain. | getRegisteredMerchant(): | setRegisteredMerchant( registeredMerchant): void |
| `ownerEntity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity that controls this domain. This is to identify the Vendor or Facilitator hosting the Apple Pay domain for the merchant. If this domain is controlled by the actual registered Merchant, the Entity field will be the Merchant's Entity. | getOwnerEntity(): | setOwnerEntity( ownerEntity): void |
| `status` | [`?string(AppleDomainStatusEnum)`](../../doc/models/apple-domain-status-enum.md) | Optional | The registration status of this domain for the given Registered Merchant.<br><br><details><br><summary>Valid Values</summary><br>- `registration_requested` **The domains that have been requested to be registered.**<br>- `registering` **In the process of being registered with Apple.**<br>- `registered` **Successfully Registered with Apple.**<br>- `failed_registration` **A Failure occurred Registering.**<br>- `unregistration_requested` **Unregistration requested.**<br>- `unregistering` **In the process of being un-registered from Apple.**<br>- `unregistered` **Successfully Unregistered with Apple.**<br></details><br> | getStatus(): ?string | setStatus(?string status): void |
| `domain` | `?string` | Optional | The domain(FQDN) associated with the Registered Merchant. | getDomain(): ?string | setDomain(?string domain): void |
| `errorNote` | `?string` | Optional | For a failed Registration or Un-Registration, will contain the reason for the failure. | getErrorNote(): ?string | setErrorNote(?string errorNote): void |

## Example (as JSON)

```json
{
  "id": "id8",
  "created": "created8",
  "modified": "modified6",
  "creator": "String7",
  "modifier": "modifier8"
}
```

