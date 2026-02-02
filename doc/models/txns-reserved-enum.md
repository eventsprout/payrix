
# Txns Reserved Enum

## Enumeration

`TxnsReservedEnum`

## Fields

| Name | Description |
|  --- | --- |
| `NONE` | No action. |
| `BLOCK` | Block transaction, will never be processed. The Entity is sent to the manual review queue. |
| `HOLD` | Hold transaction, will not be captured. |
| `RESERVE` | Reserve transaction, funds should be reserved. |
| `LIMIT` | Block current activity, no change for merchant. |
| `POSTREVIEWONLY` | We onboard the merchant and wait for manual check later. |

