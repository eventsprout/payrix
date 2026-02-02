
# Alert Trigger Event Enum

## Enumeration

`AlertTriggerEventEnum`

## Fields

| Name | Description |
|  --- | --- |
| `CREATE` | Triggers when the associated resource is created. |
| `UPDATE` | Triggers when the associated resource is updated. |
| `DELETE` | Triggers when the associated resource is deleted. |
| `OWNERSHIP` | Triggers when the ownership of the associated resource changes. |
| `BATCH` | Triggers when Transactions are captured in a batch. |
| `ACCOUNT` | Triggers when the Account associated with a Merchant is updated. |
| `ACCOUNTCREATED` | Triggers when the Account is created. |
| `ACCOUNTUPDATED` | Triggers when the Account is updated. |
| `PAYOUT` | Triggers when a Payout occurs. |
| `FEE` | Triggers when an Entity is charged a Fee. |
| `CHANGEREQUESTDECLINED` | Triggers when change request declined. |
| `CHANGEREQUESTCREATED` | Triggers when change request created. |
| `CHANGEREQUESTAPPROVED` | Triggers when change request approved. |
| `CHANGEREQUESTMANUALREVIEW` | Triggers when change request reviewed manually. |
| `CHARGEBACK` | Triggers alert when Chargeback Reports are created. |
| `CHARGEBACKOPENED` | Triggers alert when Chargeback opened. |
| `CHARGEBACKCLOSED` | Triggers alert when Chargeback closed. |
| `CHARGEBACKCREATED` | Triggers alert when a Chargeback is created. |
| `CHARGEBACKLOST` | Triggers alert when a Chargeback dispute was lost. |
| `CHARGEBACKWON` | Triggers alert when a Chargeback dispute was won. |
| `CHARGEBACKDOCUMENTUPLOADED` | Triggers alert when Chargeback document uploaded. |
| `DEBITDISBURSEMENTRECOVERY` | Triggers when the entity recovers from a negative balance and now has a positive balance again and the debtorEntity record is deleted. |
| `DISBURSEMENTREQUESTED` | Triggers alert when a Disbursement is requested. |
| `DISBURSEMENTPROCESSING` | Triggers alert when a Disbursement is processing. |
| `DISBURSEMENTPROCESSED` | Triggers alert when a Disbursement has been processed. |
| `DISBURSEMENTFAILED` | Triggers alert when a Disbursement has failed. |
| `DISBURSEMENTDENIED` | Triggers alert when a Disbursement has been denied. |
| `DISBURSEMENTREPORT` | Triggers alert when Disbursements are processed. |
| `DISBURSEMENTRETURNED` | Triggers alert when Disbursement has returned. |
| `DISBURSEMENTENTRIESPROCESSED` | Triggers alert when Disbursement Entries have been processed. |
| `INVOICECREATED` | Triggers alert when an invoice has been created. |
| `INVOICECANCELLED` | Triggers alert when an invoice has been cancelled. |
| `INVOICEEMAILED` | Triggers alert when an invoice has been emailed. |
| `INVOICEEXPIRED` | Triggers alert when an invoice has expired. |
| `INVOICEPAID` | Triggers alert when an invoice has been paid. |
| `INVOICEREFUNDED` | Triggers alert when an invoice has been refunded. |
| `INVOICEVIEWED` | Triggers alert when an invoice has been viewed. |
| `INVOICERESULTFAILURE` | Triggers alert when an invoice result has failed. |
| `MERCHANTCREATED` | Triggers alert when a Merchant has been created. |
| `MERCHANTBOARDING` | Triggers alert when a Merchant is boarding. |
| `MERCHANTBOARDED` | Triggers alert when a Merchant has been boarded. |
| `MERCHANTCLOSED` | Triggers alert when a Merchant is closed. |
| `MERCHANTCONDITIONALLYAPPROVED` | Triggers alert when a Merchant is conditionally approved. |
| `MERCHANTFULLYBOARDED` | Triggers alert when a Merchant is fully boarded after being conditionally approved. |
| `MERCHANTPENDING` | Triggers alert when a Merchant is pending. |
| `MERCHANTRESERVED` | Triggers alert when a Merchant is reserved after being conditionally approved. |
| `MERCHANTINCOMPLETE` | Triggers alert when a Merchant is incomplete. |
| `MERCHANTFAILED` | Triggers alert when Merchant boarding has failed. |
| `MERCHANTHELD` | Triggers alert when a Merchant boarding requires manual review. |
| `MESSAGECREATED` | Triggers alert when a Message was created. |
| `PAYMENTUPDATEREPORT` | Triggers when a report for a paymentUpdate is generated. |
| `RESOURCECREATED` | Triggers alert when a Resource was created. |
| `RESOURCEUPDATED` | Triggers alert when a Resource was updated. |
| `SUBSCRIPTIONCREATED` | Triggers alert when a Subscription was created. |
| `SUBSCRIPTIONAPPROVED` | Triggers alert when a Subscription was approved. |
| `SUBSCRIPTIONFAILED` | Triggers alert when a Subscription has failed. |
| `TERMINALTXNCREATED` | Triggers alert when Terminal Transaction has been created. |
| `TERMINALTXNAPPROVED` | Triggers alert when Terminal Transaction has been approved. |
| `TERMINALTXNFAILED` | Triggers alert when Terminal Transaction has failed. |
| `TXNCREATED` | Triggers alert when a Transaction is created. |
| `TXNAPPROVED` | Triggers alert when a Transaction has been approved. |
| `TXNFAILED` | Triggers alert when a Transaction has failed. |
| `TXNCAPTURED` | Triggers alert when a Transaction has been captured. |
| `TXNSETTLED` | Triggers alert when a Transaction has been settled. |
| `TXNRETURNED` | Triggers alert when a Transaction has been returned. |
| `TXNECHECKFUNDED` | Triggers alert when a Transaction has been eCheck funded. |
| `TXNDELAYEDFUNDING` | Triggers alert when a Transaction delayed funding. |
| `UPCOMINGDEBITDISBURSEMENT` | Triggers alert for upcoming debit disbursement. |

