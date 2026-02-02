
# Txn Type Enum

## Enumeration

`TxnTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `SALE` | Credit Card Only Sale Transaction, This is the most common type of Transaction, it processes a sale and charges the customer. |
| `AUTH` | Credit Card Only Auth Transaction, Authorizes and holds the requested total on the credit card. |
| `CAPTURE` | Credit Card Only Capture Transaction, Finalizes a prior Auth Transaction and charges the customer. |
| `REVERSEAUTHORIZATION` | Credit Card Only Reverse Authorization, Reverses a prior Auth or Sale Transaction and releases the credit hold. |
| `REFUND` | Credit Card Only Refund Transaction, Refunds a prior Capture or Sale Transaction (total may be specified for a partial refund). |
| `ECHECKSALE` | Echeck Only Echeck Sale Transaction, Sale Transaction for ECheck payment. |
| `ECHECKREFUND` | Echeck Only ECheck Refund Transaction, Refund Transaction for prior ECheck Sale Transaction. |
| `ECHECKREDEPOSIT` | Echeck Only Echeck Redeposit Transaction, Attempt to redeposit a prior failed eCheck Sale Transaction. |
| `ECHECKVERIFICATION` | Echeck Only Echeck Account Verification Transaction, Attempt to verify eCheck payment details. |
| `INCREMENTALAUTHORIZATION` | Incremental Authorization. |

