
# Reserve Entry Event Enum

## Enumeration

`ReserveEntryEventEnum`

## Fields

| Name | Description |
|  --- | --- |
| `DAYS` | This ReserveEntry triggers every day. |
| `WEEKS` | This ReserveEntry triggers every week. |
| `MONTHS` | This ReserveEntry triggers every month. |
| `YEARS` | This ReserveEntry triggers every year. |
| `SINGLE` | This ReserveEntry is a one-off event. |
| `AUTH` | This ReserveEntry triggers at the time of authorization of a transaction. |
| `CAPTURE` | This ReserveEntry triggers at the capture time of a Transaction. |
| `REFUND` | This ReserveEntry triggers when a refund transaction is processed. |
| `BOARD` | This ReserveEntry triggers when the Merchant is boarded. |
| `PAYOUT` | This ReserveEntry triggers when a payout is processed. |
| `CHARGEBACK` | This ReserveEntry triggers when a card chargeback occurs. |
| `OVERDRAFT` | This ReserveEntry triggers when an overdraft usage charge from a bank is levied. |
| `INTERCHANGE` | This ReserveEntry triggers when interchange Fees are assessed for the Transactions of this Merchant. |
| `PROCESSOR` | This ReserveEntry triggers when the Transactions of this Merchant are processed by a payment processor. |
| `ACHFAIL` | This ReserveEntry triggers when an automated clearing house failure occurs. |
| `ACCOUNT` | This ReserveEntry triggers when a bank account is verified. |
| `SIFT` | This ReserveEntry triggers on the Transaction fraud score. |
| `ADJUSTMENT` | This ReserveEntry triggers when the transaction is adjusted. |
| `RETRIEVAL` | This ReserveEntry triggers on a Retrieval Request Chargeback. |
| `ARBITRATION` | This ReserveEntry triggers on an Arbitration Chargeback. |
| `ECSALE` | This ReserveEntry triggers on an eCheck Sale transaction. |
| `ECREFUND` | This ReserveEntry triggers on an eCheck Refund transaction. |
| `ECRETURN` | This ReserveEntry triggers on an eCheck Return transaction. |
| `SETTLEMENT` | This ReserveEntry triggers on a transaction settlement. |
| `MISUSE` | This ReserveEntry triggers on a Misuse of authorization. |
| `PROFITSHARE` | This ReserveEntry triggers on a Profit Sharing entry event. |
| `UNAUTH` | This ReserveEntry triggers at the time of an unauthorized entry. |
| `ACHNOC` | This ReserveEntry triggers at the time of an ACH Notification Change. |
| `ECNOC` | This ReserveEntry triggers at the time of an eCheck Notification Change. |
| `ECFAIL` | This ReserveEntry triggers at the time of an eCheck Fail. |
| `ECNSF` | This ReserveEntry triggers at the time of an eCheck non-disbursed funds. |
| `CURRENCYCONVERSION` | This ReserveEntry triggers at the time of a currency conversion. |
| `TERMINALTXN` | This ReserveEntry triggers at the time of a terminal transaction. |
| `REVERSEPAYOUT` | This ReserveEntry triggers when a payout has been partially reversed. |
| `PARTIALREVERSEPAYOUT` | This ReserveEntry triggers when a payout is partially reversed. |
| `RESERVEENTRYRELEASE` | The ReserveEntry for an Entry related to released reserves. |
| `PAYMENTCHECK` | Payment Check. |
| `PAYMENTUPDATE` | This ReserveEntry triggers on a payment update for Account Updater. |
| `PAYMENTGROUPCHECK` | Payment Group Check. |
| `PAYMENTGROUPUPDATE` | This ReserveEntry triggers on a payment group update for Account Updater. |
| `ENTRYREFUND` | This ReserveEntry triggers on an entry refund. |
| `ENTITYRESERVECHANGE` | Entity Reserve Total change. |
| `RELEASEHOLD` | Release Hold. |
| `RELEASEENTRIESDEFAULT` | Default values for older records. |
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
| `VALUTECESSENTIALGIFT` | The ReserveEntry for an Entry related to external fees. |
| `VALUTECESSENTIALMONTHLYTXN` | The ReserveEntry for an Entry related to external fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGE` | The ReserveEntry for an Entry related to external fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGETXN` | The ReserveEntry for an Entry related to external fees. |
| `VALUTECLOYALTYPLUSPACKAGE` | The ReserveEntry for an Entry related to external fees. |
| `VALUTECLOYALTYPLUSPACKAGETXN` | The ReserveEntry for an Entry related to external fees. |
| `VALUTECTRANSACTIONFEE` | The ReserveEntry for an Entry related to external fees. |
| `VALUTECSETUPFEE` | The ReserveEntry for an Entry related to external fees. |
| `VALUTECGIFTACHPOOLING` | The ReserveEntry for an Entry related to external fees. |
| `VALUTECJUMPSTARTKIT` | The ReserveEntry for an Entry related to external fees. |
| `VALUTECLAUNCHBOXKIT` | The ReserveEntry for an Entry related to external fees. |
| `VALUTEC500CUSTOMCARDS` | The ReserveEntry for an Entry related to external fees. |
| `VALUTECMAINTENANCEFEE` | The ReserveEntry for an Entry related to external fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGEME` | The ReserveEntry for an Entry related to external fees. |
| `EFEMWCRESIDUALATELIO` | The ReserveEntry for an Entry related to EFE external fees. |
| `EFEMWCRESIDUALPARAFIN` | The ReserveEntry for an Entry related to EFE external fees. |
| `EFEMWCBILLING` | The ReserveEntry for an Entry related to EFE external fees. |
| `FRAUDSIGHTCNPDECISION` | The ReserveEntry for an Entry related to external fees. |
| `FRAUDSIGHTCPDECISION` | The ReserveEntry for an Entry related to external fees. |
| `REVBOOSTEMBEDDEDTMSMONTHLY` | The ReserveEntry for an Entry related to external fees. |
| `REVBOOSTEMBEDDEDTMSPPT` | The ReserveEntry for an Entry related to external fees. |
| `TXNTHREATMETRIX` | The ReserveEntry for an Entry related to external fees. |
| `THREATMETRIXEMAILAGE` | The ReserveEntry for an Entry related to external fees. |
| `THREATMETRIXFRAUDPOINT` | The ReserveEntry for an Entry related to external fees. |
| `GIACTINQUIRY` | The ReserveEntry for an Entry related to external fees. |
| `GIACTTXNGAUTHENTICATE` | The ReserveEntry for an Entry related to external fees. |
| `TRULIOOIDV` | The ReserveEntry for an Entry related to external fees. |
| `TRULIOOAMLLDV` | The ReserveEntry for an Entry related to external fees. |
| `TRULIOOBUSINESSVERIFICATION` | The ReserveEntry for an Entry related to external fees. |
| `THREATMETRIXPHONEFINDER` | The ReserveEntry for an Entry related to external fees. |
| `TIERNONQUALIFIEDCOUNT` | The ReserveEntry for an Entry related to risk-based tier fees. |
| `TIERQUALIFIEDCOUNT` | The ReserveEntry for an Entry related to risk-based tier fees. |
| `TIERMIDQUALIFIEDCOUNT` | The ReserveEntry for an Entry related to risk-based tier fees. |
| `TIERHIGHRISKCOUNT` | The ReserveEntry for an Entry related to risk-based tier fees. |
| `TIERNONQUALIFIEDVOLUME` | The ReserveEntry for an Entry related to risk-based tier fees. |
| `TIERQUALIFIEDVOLUME` | The ReserveEntry for an Entry related to risk-based tier fees. |
| `TIERMIDQUALIFIEDVOLUME` | The ReserveEntry for an Entry related to risk-based tier fees. |
| `TIERHIGHRISKVOLUME` | The ReserveEntry for an Entry related to risk-based tier fees. |

