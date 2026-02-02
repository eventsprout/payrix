
# Hold Action Enum

## Enumeration

`HoldActionEnum`

## Fields

| Name | Description |
|  --- | --- |
| `NONE` | No action. |
| `BLOCK` | Block the Transaction from proceeding, This returns an error. |
| `HOLD` | Hold the Transaction, It will not be captured until it is manually released. |
| `RESERVE` | Reserve the Transaction, The funds for the transaction will not be released until the Transaction is manually reviewed. |
| `LIMIT` | Block current activity. |
| `PASS` | Passed decision(s). |
| `POSTREVIEWONLY` | We onboard the merchant and wait for manual check later. |

