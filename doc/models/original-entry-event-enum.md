
# Original Entry Event Enum

## Enumeration

`OriginalEntryEventEnum`

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
| `STATEMENT` | the payment of a statement. |
| `MERCHANTCREATION` | a merchant fee upon creation. |
| `REALTIMEBUSINESSSEARCH` | a real-time business search. |
| `REALTIMEMEMBERSEARCH` | a real-time member search. |
| `MASTERCARDMATCH` | Mastercard match. |
| `BUSINESSINSTANTID` | a business instant ID. |
| `CONSUMERINSTANTID` | a consumer instant ID. |
| `THREATMETRIX` | Threat Metrix. |
| `LEGITSCRIPTREGISTER` | Legit Script Register. |
| `EQUIFAXCONSUMERREPORT` | Equifax consumer report. |
| `GUIDESTAR` | Guide Star. |
| `PAYLOADATTRIBUTE` | internal decision V2. |
| `TINCHECK` | a Tin Check. |
| `EQUIFAXCOMMERCIALREPORT` | Equifax commercial report. |
| `LEGITSCRIPTCHECKMERCHANT` | Legit Script Check Merchant. |
| `PLAID` | Plaid. |
| `STATEMENTREVERSAL` | the reversal of a statement. |
| `GIACTECHECK` | GIACT call made to verify creator Echeck bank account. |
| `GIACTBANKACCOUNT` | Giact calls to verify merchant settlement account. |
| `BOARDDECISION` | process decision fee after board. |
| `TXNRISKDECISION` | a transaction going through a risk decision. |
| `FANF` | external fees. |
| `MCLOCATION` | external fees. |
| `VISAINTEGRITY` | external fees. |
| `SAFERPAYMENTSBASIC` | external fees. |
| `SAFERPAYMENTSMANAGED` | external fees. |
| `SAFERPAYMENTSPCINONVALIDATION` | external fees. |
| `OMNITOKENSVOLUME` | external fees. |
| `PAYOUTRETURN` | a payout return. |
| `PAYOUTPARTIALRETURN` | a partial payout return. |
| `REVSHARE` | revenue sharing. |
| `CARDSETTLEMENT` | card settlement. |
| `ECHECKSETTLEMENT` | e-check settlement. |
| `REVSHARECARD` | revenue sharing for cards. |
| `REVSHAREECHECK` | revenue sharing for e-checks. |
| `REVSHAREDBM` | revenue sharing for DBM. |
| `PREARBITRATION` | chargeback pre-arbitration. |
| `PLAIDIDENTITYMACH` | Plaid Identity Mach. |
| `TXNPLAIDIDENTITYMACH` | transactions with Plaid Identity Mach. |
| `PLAIDGETIDENTITY` | Plaid Get Identity. |
| `TXNPLAIDGETIDENTITY` | transactions with Plaid Get Identity. |
| `PLAIDGETAUTH` | Plaid Get Auth. |
| `TXNPLAIDGETAUTH` | transactions with Plaid Get Auth. |
| `REVERSAL` | chargeback reversal. |
| `REPRESENTMENT` | chargeback representment. |
| `OMNITOKENSMONTHLY` | Omnitokens monthly fee. |
| `ICRETAINPASSTHRUREFUND` | interchange retain pass-through refund. |
| `VALUTECESSENTIALGIFT` | external fees. |
| `VALUTECESSENTIALMONTHLYTXN` | external fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGE` | external fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGETXN` | external fees. |
| `VALUTECLOYALTYPLUSPACKAGE` | external fees. |
| `VALUTECLOYALTYPLUSPACKAGETXN` | external fees. |
| `VALUTECTRANSACTIONFEE` | external fees. |
| `VALUTECSETUPFEE` | external fees. |
| `VALUTECGIFTACHPOOLING` | external fees. |
| `VALUTECJUMPSTARTKIT` | external fees. |
| `VALUTECLAUNCHBOXKIT` | external fees. |
| `VALUTEC500CUSTOMCARDS` | external fees. |
| `VALUTECMAINTENANCEFEE` | external fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGEME` | external fees. |
| `EFEMWCRESIDUALATELIO` | EFE external fees. |
| `EFEMWCRESIDUALPARAFIN` | EFE external fees. |
| `EFEMWCBILLING` | EFE external fees. |
| `FRAUDSIGHTCNPDECISION` | external fees. |
| `FRAUDSIGHTCPDECISION` | external fees. |
| `REVBOOSTEMBEDDEDTMSMONTHLY` | external fees. |
| `REVBOOSTEMBEDDEDTMSPPT` | external fees. |
| `TXNTHREATMETRIX` | external fees. |
| `THREATMETRIXEMAILAGE` | external fees. |
| `THREATMETRIXFRAUDPOINT` | external fees. |
| `GIACTINQUIRY` | external fees. |
| `GIACTTXNGAUTHENTICATE` | external fees. |
| `TRULIOOIDV` | external fees. |
| `TRULIOOAMLLDV` | external fees. |
| `TRULIOOBUSINESSVERIFICATION` | external fees. |
| `THREATMETRIXPHONEFINDER` | external fees. |
| `TIERNONQUALIFIEDCOUNT` | risk-based tier fees. |
| `TIERQUALIFIEDCOUNT` | risk-based tier fees. |
| `TIERMIDQUALIFIEDCOUNT` | risk-based tier fees. |
| `TIERHIGHRISKCOUNT` | risk-based tier fees. |
| `TIERNONQUALIFIEDVOLUME` | risk-based tier fees. |
| `TIERQUALIFIEDVOLUME` | risk-based tier fees. |
| `TIERMIDQUALIFIEDVOLUME` | risk-based tier fees. |
| `TIERHIGHRISKVOLUME` | risk-based tier fees. |

