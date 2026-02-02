
# Accounts Reserved Enum

## Enumeration

`AccountsReservedEnum`

## Fields

| Name | Description |
|  --- | --- |
| `NONE` | No action. |
| `BLOCK` | Block transaction, will never be processed. The Entity is sent to the manual review queue. |
| `HOLD` | Hold transaction, will not be captured. |
| `RESERVE` | Reserve transaction, funds should be reserved. |
| `LIMIT` | Block current activity, no change for merchant. |
| `PASS` | Passed decision(s). Will not be set anywhere, will only be used for integration purposes. |
| `SKIP` | We did not have policies to process. |
| `POSTREVIEWONLY` | We onboard the merchant and wait for manual check later. |
| `SCHEDULERESERVERELEASE` | Schedule the automatic release of the reserve. |
| `AUTOMATICREFUNDHOLD` | Hold transaction, will not be captured. Automatic release when the associated sale is done. |

