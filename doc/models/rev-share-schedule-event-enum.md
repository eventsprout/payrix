
# Rev Share Schedule Event Enum

## Enumeration

`RevShareScheduleEventEnum`

## Fields

| Name | Description |
|  --- | --- |
| `DAYS` | Daily scheduled event (like a fee). |
| `WEEKS` | Weekly scheduled event. |
| `MONTHS` | Monthly scheduled event. |
| `YEARS` | Yearly scheduled event. |
| `SINGLE` | One-off event. |
| `AUTH` | Auth and sale transaction (types 1 and 2) authorization. |
| `CAPTURE` | Capture and sale transaction (types 1 and 3) capture (settlement to processor). |
| `REFUND` | Refund transaction capture (settlement to processor). |
| `BOARD` | Merchant boarding (mid stage entityRef creation). |
| `PAYOUT` | Disbursement creation. |
| `CHARGEBACK` | Triggers when a card chargeback occurs. |
| `OVERDRAFT` | Disbursement return due to insufficient funds. |
| `INTERCHANGE` | Transaction interchange fees assessment. |
| `PROCESSOR` | Transaction processed by a payment processor. |
| `ACHFAIL` | Disbursement return due to any failure other than insufficient funds. |
| `ACCOUNT` | Bank account verification. |
| `SIFT` | Transaction fraud score. |
| `ADJUSTMENT` | Adjusted funds. |
| `RETRIEVAL` | Retrieval chargeback creation (retrieval cycle). |
| `ARBITRATION` | Arbitration chargeback creation (arbitration cycle). |
| `ECSALE` | Transaction e-check Sale. |
| `ECREFUND` | Transaction e-check Refund. |
| `ECRETURN` | eCheck transaction return. |
| `SETTLEMENT` | Transaction settlement (processor to issuer, reported in processor’s settlement report). |
| `MISUSE` | Transaction misuse (transaction violated Visa authorization misuse rules or MasterCard’s integrity rules). |
| `PROFITSHARE` | Profit sharing entry event. |
| `UNAUTH` | Unauthorized entry. |
| `ACHNOC` | Disbursement notice of change (NOC). |
| `ECNOC` | eCheck transaction notice of change (NOC). |
| `ECFAIL` | eCheck transaction return due to any failure other than insufficient funds. |
| `ECNSF` | eCheck transaction return due to insufficient funds. |
| `CURRENCYCONVERSION` | Currency conversion. |
| `TERMINALTXN` | Terminal transaction. |
| `REVERSEPAYOUT` | Payout that has been reversed. |
| `PARTIALREVERSEPAYOUT` | Payout that has been partially reversed. |
| `PAYMENTCHECK` | Account updater request sent (paymentUpdate status of processing). |
| `PAYMENTUPDATE` | Account updater response processed (paymentUpdate status of processed). |
| `PAYMENTGROUPCHECK` | Account updater unique request sent (one paymentUpdate status of processing per entity of entire paymentUpdateGroup). |
| `PAYMENTGROUPUPDATE` | Account updater unique response processed (one paymentUpdate status of processed per entity for entire paymentUpdateGroup). |
| `ENTRYREFUND` | Entry refunds. |
| `STATEMENT` | Billing statement (when paid by debit disbursement). |
| `MERCHANTCREATION` | Merchant creation. |
| `REALTIMEBUSINESSSEARCH` | Real time business search. |
| `REALTIMEMEMBERSEARCH` | Real time member search. |
| `MASTERCARDMATCH` | Mastercard match. |
| `BUSINESSINSTANTID` | Business instant id. |
| `CONSUMERINSTANTID` | Consumer instant id. |
| `THREATMETRIX` | Threat metrix. |
| `LEGITSCRIPTREGISTER` | Legit script register. |
| `EQUIFAXCONSUMERREPORT` | Equifax consumer report. |
| `GUIDESTAR` | Guidestar. |
| `PAYLOADATTRIBUTE` | Internal Decision V2. |
| `TINCHECK` | Tin check. |
| `EQUIFAXCOMMERCIALREPORT` | Equifax commercial report. |
| `LEGITSCRIPTCHECKMERCHANT` | Legit script check merchant. |
| `PLAID` | Plaid. |
| `STATEMENTREVERSAL` | Reversal of statement. |
| `GIACTECHECK` | GIACT call made to verify creator Echeck bank Account. |
| `GIACTBANKACCOUNT` | Giact calls to verify merchant settlement account on sign up or post boarding account. |
| `BOARDDECISION` | Process decision fee after board. |
| `TXNRISKDECISION` | Txn going through a risk decision. |
| `FANF` | FANF - External fees. |
| `MCLOCATION` | MCLOCATION - External fees. |
| `VISAINTEGRITY` | VISAINTEGRITY - External fees. |
| `SAFERPAYMENTSBASIC` | External Fees. |
| `SAFERPAYMENTSMANAGED` | External Fees. |
| `SAFERPAYMENTSPCINONVALIDATION` | External Fees. |
| `OMNITOKENSVOLUME` | External Fees. |
| `PAYOUTRETURN` | Payout Return. |
| `PAYOUTPARTIALRETURN` | Payout Partial Return. |
| `REVSHARE` | Rev share. |
| `CARDSETTLEMENT` | Transaction card settlement. |
| `ECHECKSETTLEMENT` | Transaction e-check settlement. |
| `REVSHARECARD` | Rev share card Schedules. |
| `REVSHAREECHECK` | Rev share e-chek Schedules. |
| `REVSHAREDBM` | Rev share DBM Schedules. |
| `PREARBITRATION` | Chargeback PreArbitration. |
| `PLAIDIDENTITYMACH` | Plaid. |
| `TXNPLAIDIDENTITYMACH` | Txns Plaid. |
| `PLAIDGETIDENTITY` | Plaid. |
| `TXNPLAIDGETIDENTITY` | Txns Plaid. |
| `PLAIDGETAUTH` | Plaid. |
| `TXNPLAIDGETAUTH` | Txns Plaid. |
| `REVERSAL` | Chargeback Reversal. |
| `REPRESENTMENT` | Chargeback Representment. |
| `OMNITOKENSMONTHLY` | Omnitokens Monthly Fee. |
| `ICRETAINPASSTHRUREFUND` | Interchange retain pass on refund. |
| `VALUTECESSENTIALGIFT` | External Fees. |
| `VALUTECESSENTIALMONTHLYTXN` | External Fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGE` | External Fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGETXN` | External Fees. |
| `VALUTECLOYALTYPLUSPACKAGE` | External Fees. |
| `VALUTECLOYALTYPLUSPACKAGETXN` | External Fees. |
| `VALUTECTRANSACTIONFEE` | External Fees. |
| `VALUTECSETUPFEE` | External Fees. |
| `VALUTECGIFTACHPOOLING` | External Fees. |
| `VALUTECJUMPSTARTKIT` | External Fees. |
| `VALUTECLAUNCHBOXKIT` | External Fees. |
| `VALUTEC500CUSTOMCARDS` | External Fees. |
| `VALUTECMAINTENANCEFEE` | External Fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGEME` | External Fees. |
| `EFEMWCRESIDUALATELIO` | EFE External Fees. |
| `EFEMWCRESIDUALPARAFIN` | EFE External Fees. |
| `EFEMWCBILLING` | EFE External Fees. |
| `FRAUDSIGHTCNPDECISION` | External Fees. |
| `FRAUDSIGHTCPDECISION` | External Fees. |
| `REVBOOSTEMBEDDEDTMSMONTHLY` | External Fees. |
| `REVBOOSTEMBEDDEDTMSPPT` | External Fees. |
| `TXNTHREATMETRIX` | External Fees. |
| `THREATMETRIXEMAILAGE` | External Fees. |
| `THREATMETRIXFRAUDPOINT` | External Fees. |
| `GIACTINQUIRY` | External Fees. |
| `GIACTTXNGAUTHENTICATE` | External Fees. |
| `TRULIOOIDV` | External Fees. |
| `TRULIOOAMLLDV` | External Fees. |
| `TRULIOOBUSINESSVERIFICATION` | External Fees. |
| `THREATMETRIXPHONEFINDER` | External Fees. |
| `TIERNONQUALIFIEDCOUNT` | Risk Based Tier Fees. |
| `TIERQUALIFIEDCOUNT` | Risk Based Tier Fees. |
| `TIERMIDQUALIFIEDCOUNT` | Risk Based Tier Fees. |
| `TIERHIGHRISKCOUNT` | Risk Based Tier Fees. |
| `TIERNONQUALIFIEDVOLUME` | Risk Based Tier Fees. |
| `TIERQUALIFIEDVOLUME` | Risk Based Tier Fees. |
| `TIERMIDQUALIFIEDVOLUME` | Risk Based Tier Fees. |

