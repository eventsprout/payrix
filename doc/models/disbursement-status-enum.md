
# Disbursement Status Enum

## Enumeration

`DisbursementStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `REQUESTED` | The request for this Disbursement has been received. |
| `PROCESSING` | This Disbursement is being processed to be paid out. |
| `PROCESSED` | This Disbursement has been paid by ACH to the bank account referenced in the Disbursement data. |
| `FAILED` | A problem occurred and the payment processor has failed to process this Disbursement. |
| `DENIED` | This Disbursement has been refused. |
| `RETURNED` | This Disbursement has been returned. |

