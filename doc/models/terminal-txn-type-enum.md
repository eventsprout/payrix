
# Terminal Txn Type Enum

## Enumeration

`TerminalTxnTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `SALE` | Sale Transaction, This is the most common type of Transaction, it processes a sale and charges the customer. |
| `AUTH` | Auth Transaction, Authorizes and holds the requested total on the credit card. |
| `UNAUTH` | Reverse Authorization, Reverses a prior Auth or Sale Transaction and releases the credit hold. |
| `REFUND` | Refund Transaction, Refunds a prior Capture or Sale Transaction (total may be specified for a partial refund). |
| `BATCH` | Batch out terminal. |

