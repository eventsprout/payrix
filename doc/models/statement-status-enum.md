
# Statement Status Enum

## Enumeration

`StatementStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `PENDING` | Statement amount is owed and is pending payment. |
| `PROCESSING` | A payment is processing for this statement, pending completion. |
| `PARTIALLYPAID` | The statement was partially paid, some amount is still outstanding. |
| `PAID` | The statement was paid in full. |
| `PARTIALLYCANCELLED` | The statement was partially cancelled, some amount is still outstanding. |
| `CANCELLED` | The statement was completely cancelled and is no longer due for payment. |

