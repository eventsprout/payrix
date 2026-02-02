
# Descision Action Enum

## Enumeration

`DescisionActionEnum`

## Fields

| Name | Description |
|  --- | --- |
| `NONE` | No action. |
| `BLOCK` | Block txn, will never be processed. The Entity is sent to the manual review queue. |
| `HOLD` | Hold txn, will not be captured. |
| `RESERVE` | Reserve txn, funds should be reserved. |
| `LIMIT` | Block current activity, no change for merchant. |
| `PASS` | Passed decision(s). Will not be set anywhere, will only be used for integration purposes. |
| `SKIP` | We did not have policies to process. |
| `POSTREVIEWONLY` | We onboard the merchant and wait for manual check later. |
| `SCHEDULERESERVERELEASE` | Schedule the automatic release of the reserve. |
| `AUTOMATICREFUNDHOLD` | Hold txn, will not be captured. Automatic release when the associated sale is done. |

