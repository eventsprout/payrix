
# Disbursement Entry Event Enum

## Enumeration

`DisbursementEntryEventEnum`

## Fields

| Name | Description |
|  --- | --- |
| `DAYS` | This assessment triggers every day. |
| `WEEKS` | This assessment triggers every week. |
| `MONTHS` | This assessment triggers every month. |
| `YEARS` | This assessment triggers every year. |
| `SINGLE` | This assessment is a one-off event. |
| `AUTH` | This assessment triggers at the time of authorization of a transaction. |
| `CAPTURE` | This assessment triggers at the capture time of a Transaction. |
| `REFUND` | This assessment triggers when a refund transaction is processed. |
| `BOARD` | This assessment triggers when the Merchant is boarded. |
| `PAYOUT` | This assessment triggers when a payout is processed. |
| `CHARGEBACK` | This assessment triggers when a card chargeback occurs. |
| `OVERDRAFT` | This assessment triggers when an overdraft usage charge from a bank is levied. |
| `INTERCHANGE` | This assessment triggers when interchange Fees are assessed for the Transactions of this Merchant. |
| `PROCESSOR` | This assessment triggers when the Transactions of this Merchant are processed by a payment processor. |
| `ACHFAIL` | This assessment triggers when an automated clearing house failure occurs. |
| `ACCOUNT` | This assessment triggers when a bank account is verified. |
| `SIFT` | This assessment triggers on the Transaction fraud score. |
| `ADJUSTMENT` | This assessment triggers when the transaction is adjusted. |
| `RETRIEVAL` | This assessment triggers on a Retrieval Request Chargeback. |
| `ARBITRATION` | This assessment triggers on an Arbitration Chargeback. |
| `ECSALE` | This assessment triggers on an eCheck Sale transaction. |
| `ECREFUND` | This assessment triggers on an eCheck Refund transaction. |
| `ECRETURN` | This assessment triggers on an eCheck Return transaction. |
| `SETTLEMENT` | This assessment triggers on a transaction settlement. |
| `MISUSE` | This assessment triggers on a Misuse of authorization. |
| `PROFITSHARE` | This assessment triggers on a Profit Sharing entry event. |
| `UNAUTH` | This assessment triggers at the time of an unauthorized entry. |
| `ACHNOC` | This assessment triggers at the time of an ACH Notification Change. |
| `ECNOC` | This assessment triggers at the time of an eCheck Notification Change. |
| `ECFAIL` | This assessment triggers at the time of an eCheck Fail. |
| `ECNSF` | This assessment triggers at the time of an eCheck non-disbursed funds. |
| `CURRENCYCONVERSION` | This assessment triggers at the time of a currency conversion. |
| `TERMINALTXN` | This assessment triggers at the time of a terminal transaction. |
| `REVERSEPAYOUT` | This assessment triggers when a payout has been partially reversed. |
| `PARTIALREVERSEPAYOUT` | This assessment triggers when a payout is partially reversed. |
| `RESERVEENTRY` | DisbursementEntry for an Entry related to reserved funds. |
| `RESERVEENTRYRELEASE` | DisbursementEntry for an Entry related to released reserves. |
| `PENDINGENTRY` | DisbursementEntry for an Entry related to pending funds. |
| `PENDINGPAID` | DisbursementEntry for an Entry related to paid pending funds. |
| `REMAINDER` | DisbursementEntry for an Entry on the remaining, non-disbursed funds. |
| `REMAINDERUSED` | DisbursementEntry for an Entry related to previously non-disbursed funds. |
| `PENDINGREFUNDCANCELLED` | DisbursementEntry for an Entry related to a pending refund that was cancelled. |
| `PAYMENTCHECK` | Payment Check. |
| `PAYMENTUPDATE` | This assessment triggers on a payment update for Account Updater. |
| `PAYMENTGROUPCHECK` | Payment Group Check. |
| `PAYMENTGROUPUPDATE` | This assessment triggers on a payment group update for Account Updater. |
| `ENTRYREFUND` | This assessment triggers on an entry refund. |
| `STATEMENT` | Payment of statement. |
| `MERCHANTCREATION` | Merchant fee upon creation. |
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
| `FANF` | External Fees. |
| `MCLOCATION` | External Fees. |
| `VISAINTEGRITY` | External Fees. |
| `SAFERPAYMENTSBASIC` | External Fees. |
| `SAFERPAYMENTSMANAGED` | External Fees. |
| `SAFERPAYMENTSPCINONVALIDATION` | External Fees. |
| `OMNITOKENSVOLUME` | External Fees. |
| `PAYOUTRETURN` | Payout Return. |
| `PAYOUTPARTIALRETURN` | Payout Partial Return. |
| `REVSHARE` | Rev share. |
| `CARDSETTLEMENT` | Txns card settlement. |
| `ECHECKSETTLEMENT` | Txns e-check settlement. |
| `REVSHARECARD` | Rev Share Schedules. |
| `REVSHAREECHECK` | Rev Share Schedules. |
| `REVSHAREDBM` | Rev Share Schedules. |
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
| `VALUTECESSENTIALGIFT` | DisbursementEntry for an Entry related to external fees. |
| `VALUTECESSENTIALMONTHLYTXN` | DisbursementEntry for an Entry related to external fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGE` | DisbursementEntry for an Entry related to external fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGETXN` | DisbursementEntry for an Entry related to external fees. |
| `VALUTECLOYALTYPLUSPACKAGE` | DisbursementEntry for an Entry related to external fees. |
| `VALUTECLOYALTYPLUSPACKAGETXN` | DisbursementEntry for an Entry related to external fees. |
| `VALUTECTRANSACTIONFEE` | DisbursementEntry for an Entry related to external fees. |
| `VALUTECSETUPFEE` | DisbursementEntry for an Entry related to external fees. |
| `VALUTECGIFTACHPOOLING` | DisbursementEntry for an Entry related to external fees. |
| `VALUTECJUMPSTARTKIT` | DisbursementEntry for an Entry related to external fees. |
| `VALUTECLAUNCHBOXKIT` | DisbursementEntry for an Entry related to external fees. |
| `VALUTEC500CUSTOMCARDS` | DisbursementEntry for an Entry related to external fees. |
| `VALUTECMAINTENANCEFEE` | DisbursementEntry for an Entry related to external fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGEME` | DisbursementEntry for an Entry related to external fees. |
| `EFEMWCRESIDUALATELIO` | DisbursementEntry for an Entry related to EFE external fees. |
| `EFEMWCRESIDUALPARAFIN` | DisbursementEntry for an Entry related to EFE external fees. |
| `EFEMWCBILLING` | DisbursementEntry for an Entry related to EFE external fees. |
| `FRAUDSIGHTCNPDECISION` | DisbursementEntry for an Entry related to external fees. |
| `FRAUDSIGHTCPDECISION` | DisbursementEntry for an Entry related to external fees. |
| `REVBOOSTEMBEDDEDTMSMONTHLY` | DisbursementEntry for an Entry related to external fees. |
| `REVBOOSTEMBEDDEDTMSPPT` | DisbursementEntry for an Entry related to external fees. |
| `TXNTHREATMETRIX` | DisbursementEntry for an Entry related to external fees. |
| `THREATMETRIXEMAILAGE` | DisbursementEntry for an Entry related to external fees. |
| `THREATMETRIXFRAUDPOINT` | DisbursementEntry for an Entry related to external fees. |
| `GIACTINQUIRY` | DisbursementEntry for an Entry related to external fees. |
| `GIACTTXNGAUTHENTICATE` | DisbursementEntry for an Entry related to external fees. |
| `TRULIOOIDV` | DisbursementEntry for an Entry related to external fees. |
| `TRULIOOAMLLDV` | DisbursementEntry for an Entry related to external fees. |
| `TRULIOOBUSINESSVERIFICATION` | DisbursementEntry for an Entry related to external fees. |
| `THREATMETRIXPHONEFINDER` | DisbursementEntry for an Entry related to external fees. |
| `TIERNONQUALIFIEDCOUNT` | DisbursementEntry for an Entry related to risk-based tier fees. |
| `TIERQUALIFIEDCOUNT` | DisbursementEntry for an Entry related to risk-based tier fees. |
| `TIERMIDQUALIFIEDCOUNT` | DisbursementEntry for an Entry related to risk-based tier fees. |
| `TIERHIGHRISKCOUNT` | DisbursementEntry for an Entry related to risk-based tier fees. |
| `TIERNONQUALIFIEDVOLUME` | DisbursementEntry for an Entry related to risk-based tier fees. |
| `TIERQUALIFIEDVOLUME` | DisbursementEntry for an Entry related to risk-based tier fees. |
| `TIERMIDQUALIFIEDVOLUME` | DisbursementEntry for an Entry related to risk-based tier fees. |
| `TIERHIGHRISKVOLUME` | DisbursementEntry for an Entry related to risk-based tier fees. |

