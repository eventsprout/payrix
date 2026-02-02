
# Entry Event Enum

## Enumeration

`EntryEventEnum`

## Fields

| Name | Description |
|  --- | --- |
| `DAYS` | The Entry is triggered by a daily event. |
| `WEEKS` | The Entry is triggered by a weekly event. |
| `MONTHS` | The Entry is triggered by a monthly event. |
| `YEARS` | The Entry is triggered by an annual event. |
| `SINGLE` | The Entry is triggered by a one-off event. |
| `AUTH` | The Entry is triggered when a transaction has been authorized. |
| `CAPTURE` | The Entry is triggered when a transaction has been captured. |
| `REFUND` | The Entry is triggered when a refund transaction is processed. |
| `BOARD` | The Entry is triggered when a Merchant is boarded. |
| `PAYOUT` | The Entry is triggered when a payout is processed. |
| `CHARGEBACK` | The Entry is triggered when a card chargeback occurs. |
| `OVERDRAFT` | The Entry is triggered when an overdraft usage charge from a bank is levied. |
| `INTERCHANGE` | The Entry is triggered when interchange Fees are assessed for the Transactions of this Merchant. |
| `PROCESSOR` | The Entry is triggered when the Transactions of this Merchant are processed by a payment processor. |
| `ACHFAIL` | The Entry is triggered when an automated clearing house failure occurs. |
| `ACCOUNT` | The Entry is triggered when a bank account is verified. |
| `SIFT` | The Entry is triggered by a transaction's fraud Score. |
| `ADJUSTMENT` | The Entry is triggered when there's an adjustment. |
| `RETRIEVAL` | The Entry is triggered by a retrieval request chargeback. |
| `ARBITRATION` | The Entry is triggered by an arbitration chargeback. |
| `ECSALE` | The Entry is triggered by an eCheck sale transaction. |
| `ECREFUND` | The Entry is triggered by an eCheck refund. |
| `ECRETURN` | The Entry is triggered by an eCheck return. |
| `SETTLEMENT` | The Entry triggers when a transaction has been settled. |
| `MISUSE` | The Entry is triggered when there's been a Misuse of authorization. |
| `PROFITSHARE` | The Entry is triggered by a profit sharing entry event. |
| `UNAUTH` | The Entry is triggered when a transaction is unauthorized. |
| `ACHNOC` | The Entry is triggered by a disbursement NOC (Notification of change). |
| `ECNOC` | The Entry is triggered by an echeck transaction NOC (Notification of change). |
| `ECFAIL` | The Entry is triggered by an echeck transaction failed. |
| `ECNSF` | The Entry is triggered by an eCheck transaction NSF (Non-sufficient funds) return. |
| `CURRENCYCONVERSION` | This Entry is triggered by a currency conversion. |
| `TERMINALTXN` | This Entry is triggered by a terminal transaction. |
| `REVERSEPAYOUT` | This Entry is triggered by a payout that has been reversed. |
| `PARTIALREVERSEPAYOUT` | This Entry is triggered by a payout that has been partially reversed. |
| `PAYMENTCHECK` | This Entry is triggered by a payment check for Account Updater. |
| `PAYMENTUPDATE` | This Entry is triggered by a payment update for Account Updater. |
| `PAYMENTGROUPCHECK` | This Entry is triggered by a payment group check for Account Updater. |
| `PAYMENTGROUPUPDATE` | This Entry is triggered by a payment group update for Account Updater. |
| `ENTRYREFUND` | This Entry is triggered by an entry refund. |
| `STATEMENT` | The payment of a statement. |
| `MERCHANTCREATION` | Merchant fee upon creation. |
| `REALTIMEBUSINESSSEARCH` | Real-time business search. |
| `REALTIMEMEMBERSEARCH` | Real-time member search. |
| `MASTERCARDMATCH` | Mastercard match. |
| `BUSINESSINSTANTID` | Business instant ID. |
| `CONSUMERINSTANTID` | Consumer instant ID. |
| `THREATMETRIX` | Threat Metrix. |
| `LEGITSCRIPTREGISTER` | Legit Script Register. |
| `EQUIFAXCONSUMERREPORT` | Equifax consumer report. |
| `GUIDESTAR` | Guide Star. |
| `PAYLOADATTRIBUTE` | internal decision V2. |
| `TINCHECK` | Tin Check. |
| `EQUIFAXCOMMERCIALREPORT` | Equifax commercial report. |
| `LEGITSCRIPTCHECKMERCHANT` | Legit Script Check Merchant. |
| `PLAID` | Plaid. |
| `STATEMENTREVERSAL` | the reversal of a statement. |
| `GIACTECHECK` | GIACT call made to verify creator Echeck bank account. |
| `GIACTBANKACCOUNT` | Giact calls to verify merchant settlement account. |
| `BOARDDECISION` | process decision fee after board. |
| `TXNRISKDECISION` | Transaction going through Risk decision. |
| `FANF` | External fees. |
| `MCLOCATION` | External fees. |
| `VISAINTEGRITY` | External fees. |
| `SAFERPAYMENTSBASIC` | External fees. |
| `SAFERPAYMENTSMANAGED` | External fees. |
| `SAFERPAYMENTSPCINONVALIDATION` | External fees. |
| `OMNITOKENSVOLUME` | External fees. |
| `PAYOUTRETURN` | Payout return. |
| `PAYOUTPARTIALRETURN` | Partial payout return. |
| `REVSHARE` | Revenue sharing. |
| `CARDSETTLEMENT` | Card settlement. |
| `ECHECKSETTLEMENT` | E-Check settlement. |
| `REVSHARECARD` | Revenue sharing for cards. |
| `REVSHAREECHECK` | Revenue sharing for e-checks. |
| `REVSHAREDBM` | Revenue sharing for DBM. |
| `PREARBITRATION` | Chargeback pre-arbitration. |
| `PLAIDIDENTITYMACH` | Plaid Identity Mach. |
| `TXNPLAIDIDENTITYMACH` | transactions with Plaid Identity Mach. |
| `PLAIDGETIDENTITY` | Plaid Get Identity. |
| `TXNPLAIDGETIDENTITY` | Transactions with Plaid Get Identity. |
| `PLAIDGETAUTH` | Plaid Get Auth. |
| `TXNPLAIDGETAUTH` | Transactions with Plaid Get Auth. |
| `REVERSAL` | Chargeback reversal. |
| `REPRESENTMENT` | Chargeback representment. |
| `OMNITOKENSMONTHLY` | Omnitokens monthly fee. |
| `ICRETAINPASSTHRUREFUND` | Interchange retain pass-through refund. |
| `VALUTECESSENTIALGIFT` | External fees. |
| `VALUTECESSENTIALMONTHLYTXN` | External fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGE` | External fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGETXN` | External fees. |
| `VALUTECLOYALTYPLUSPACKAGE` | External fees. |
| `VALUTECLOYALTYPLUSPACKAGETXN` | External fees. |
| `VALUTECTRANSACTIONFEE` | External fees. |
| `VALUTECSETUPFEE` | External fees. |
| `VALUTECGIFTACHPOOLING` | External fees. |
| `VALUTECJUMPSTARTKIT` | External fees. |
| `VALUTECLAUNCHBOXKIT` | External fees. |
| `VALUTEC500CUSTOMCARDS` | External fees. |
| `VALUTECMAINTENANCEFEE` | External fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGEME` | External fees. |
| `EFEMWCRESIDUALATELIO` | EFE External fees. |
| `EFEMWCRESIDUALPARAFIN` | EFE External fees. |
| `EFEMWCBILLING` | EFE External fees. |
| `FRAUDSIGHTCNPDECISION` | External fees. |
| `FRAUDSIGHTCPDECISION` | External fees. |
| `REVBOOSTEMBEDDEDTMSMONTHLY` | External fees. |
| `REVBOOSTEMBEDDEDTMSPPT` | External fees. |
| `TXNTHREATMETRIX` | External fees. |
| `THREATMETRIXEMAILAGE` | External fees. |
| `THREATMETRIXFRAUDPOINT` | External fees. |
| `GIACTINQUIRY` | External fees. |
| `GIACTTXNGAUTHENTICATE` | External fees. |
| `TRULIOOIDV` | External fees. |
| `TRULIOOAMLLDV` | External fees. |
| `TRULIOOBUSINESSVERIFICATION` | External fees. |
| `THREATMETRIXPHONEFINDER` | External fees. |
| `TIERNONQUALIFIEDCOUNT` | Risk-based tier fees. |
| `TIERQUALIFIEDCOUNT` | Risk-based tier fees. |
| `TIERMIDQUALIFIEDCOUNT` | Risk-based tier fees. |
| `TIERHIGHRISKCOUNT` | Risk-based tier fees. |
| `TIERNONQUALIFIEDVOLUME` | Risk-based tier fees. |
| `TIERQUALIFIEDVOLUME` | Risk-based tier fees. |
| `TIERMIDQUALIFIEDVOLUME` | Risk-based tier fees. |
| `TIERHIGHRISKVOLUME` | Risk-based tier fees. |

