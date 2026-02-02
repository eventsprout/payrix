
# Configuration Stage Name Enum

## Enumeration

`ConfigurationStageNameEnum`

## Fields

| Name | Description |
|  --- | --- |
| `BLANK` | Blank. Used for a stage with no name. |
| `ACCEPTEDCARDS` | Set card types accepted by the merchant. |
| `ACK` |  |
| `ACTIVATESRS` | First Data merchant SRS activation. |
| `ALERT` |  |
| `AMEXUPDATE` | Update merchant card enablement for American Express. |
| `APPLEPAY` |  |
| `BALANCE` | Bank account balance request for decisions and verifications processes. |
| `BATCH` | Send batch command to terminal. |
| `CHARGEBACK` | Chargeback. The standard name used for chargeback related stages. |
| `CHARGEBACKLIST` | ChargebackList. The specific name to get chargeback reports. |
| `CONFIRMDISBURSEMENT` | Disbursement confirmation report retrieval. |
| `CONTACTUPDATE` | Update merchant contacts. |
| `CREATEMERCHANT` | Send merchant details for merchant boarding. |
| `CREDIT` |  |
| `DECRYPT` | Set card types accepted by the merchant. |
| `DEBIT` | Set card types accepted by the merchant. |
| `DEBITPINENABLE` | Set merchant Pin Debit enablement. |
| `DEBITPINLESSENABLE` | Set merchant Pinless Debit enablement. |
| `DISCOVERURL` | Retrieve merchant transaction processing url. |
| `DISCOVERUPDATE` | Update merchant card enablement for Discover. |
| `DOCUMENT` | Document. The standard name for chargeback related documentation such as uploading a document or updating a document. |
| `DOCUMENTLIST` | DocumentList. Used for receiving documents related to a chargeback. |
| `INTERCHANGE` |  |
| `ENCRYPT` |  |
| `ENTITY` | Entity. The standard name used when it comes to entity related stages such as retrieving an entity or updating. |
| `ENTITYADDRESSUPDATE` | Update merchant legal entity address. |
| `ENTITYRETRIEVAL` | EntityRetrieval. Used when entity stage name is already being used in that crud configuration. |
| `ENTITYUPDATE` | EntityUpdate. Used when entity stage name is already being used in that crud configuration. |
| `EXPRESSSUBACCOUNTUPDATE` | This holds the parameter for updating express subaccount. |
| `RETURN_` | Return. Used for return stage name. |
| `FEELIST` | FeeList. The specific name to get fees reports. |
| `GOOGLEPAY` |  |
| `MEMBERCREATE` | MemberCreate. Stage name used to indicate creating a merchant member. |
| `MEMBERDELETE` | MemberDelete. Stage name used to indicate deleting a merchant member. |
| `MEMBERS` | Members. Stage name used for creating several members for the merchant. |
| `MEMBERUPDATE` | Update merchant member. |
| `MERCHANT` | Merchant. The standard name used for merchant related stages such retrieving a merchant or updating a merchant. |
| `MERCHANTCARDPRESENT` | This holds the parameter for creating merchants with card present options, this is specific for WF and WFSingle platform. |
| `MERCHANTCARDNOTPRESENT` | This holds the parameter for creating merchants with card not present options, this is specific for WF and WFSingle platform. |
| `MERCHANTUPDATE` | Update merchant details. |
| `MERCHANTRETRIEVAL` | MerchantRetrieval. Used when merchant stage name is already being used in that crud configuration. |
| `NOC` | Noc. Stage name used for notification of change for disbursement related integrations. |
| `NOCRETURNS` |  |
| `OMNITOKENENABLE` | This holds the parameters for omni token enablement. |
| `PASSTOKENENABLE` | This holds the parameters for pass token enablement. |
| `PAYMENT` | Send payment details for Account Updater request. |
| `PAYMENTCONFIRMATION` | Retrieve Account Updater request echo confirmation. |
| `PAYMENTUPDATE` | Retrieve Account Updater updates. |
| `PAYOUT` | Payout. Stage name used for payouts. |
| `PRIMARYMEMBERUPDATE` | Update merchant primary member. |
| `REGISTERSRS` | First Data merchant SRS registration. |
| `RETURNCREDIT` |  |
| `RETURNDEBIT` |  |
| `RETURNS` |  |
| `SAFERPAYMENTENABLE` | This holds the parameters for safer payment enablement. |
| `TERMINALCREATE` | Send terminal details for terminal boarding. |
| `TERMINALLIST` | Retrieve list of terminals for a merchant. |
| `TERMINALSSUPPORTED` | Retrieve list of supported terminals for a merchant. |
| `TXN` | Txn. The standard name used for transaction related stages. |
| `TXNLIST` | TxnList. The specific name to get transaction reports. |
| `VARSHEET` | This hold the parameter for accessing the terminal VARSHEET retrieval |

