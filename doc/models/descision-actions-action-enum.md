
# Descision Actions Action Enum

## Enumeration

`DescisionActionsActionEnum`

## Fields

| Name | Description |
|  --- | --- |
| `BLOCK` | Block txn, will never be processed. The Entity is sent to the manual review queue. |
| `HOLD` | Hold txn, will not be captured. |
| `RESERVE` | Reserve txn, funds should be reserved. |
| `LIMIT` | Block current activity, no change for merchant. |
| `POSTREVIEWONLY` | We onboard the merchant and wait for manual check later. |

