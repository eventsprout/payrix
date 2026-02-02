
# Merchant Status Enum

## Enumeration

`MerchantStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `NOTREADY` | Occurs when a new Merchant is created. Unable to process payments. |
| `READY` | New Merchant submitted for underwriting approval after submitting a signup form. |
| `BOARDED` | Merchant has been approved and boarded to the platform. Payment processing now available. |
| `MANUAL` | Set internally by platform underwriting. New Merchant is pending manual verification. |
| `CLOSED` | Set internally by platform underwriting. New Merchant was declined and cannot access the platform. |
| `INCOMPLETE` | Set by user boarding the merchant. Can be manually set to "save" an incomplete Merchant boarding request for a later time. |
| `PENDING` | New Merchant was submitted for boarding, platform access pending review. |

