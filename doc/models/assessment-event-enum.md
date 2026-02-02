
# Assessment Event Enum

## Enumeration

`AssessmentEventEnum`

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
| `REFUND` | This assessment triggers when Refund transaction is processed. |
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
| `RETRIEVAL` | This assessment triggers on Retrieval Request Chargeback. |
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
| `ECNSF` | This assessment triggers an the time of an eCheck non-disbursed funds. |
| `CURRENCYCONVERSION` | This assessment triggers at the time of a currency conversion. |
| `TERMINALTXN` | This assessment triggers at the time of a terminal transaction. |
| `REVERSEPAYOUT` | This assessment triggers when a payout has been partially reversed. |
| `PARTIALREVERSEPAYOUT` | This assessment triggers when a payout is partially reversed. |
| `PAYMENTCHECK` | Single payment check (deprecated). |
| `PAYMENTUPDATE` | This assessment triggers on a payment update for Account Updater. |
| `PAYMENTGROUPCHECK` | Group payment check (deprecated). |
| `PAYMENTGROUPUPDATE` | This assessment triggers on a payment group update for Account Updater. |
| `ENTRYREFUND` | This assessment triggers on an entry refund. |
| `STATEMENT` | the payment of a statement. |
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
| `OMNITOKENSMONTHLY` | Omnitokens Monthly Fee. |
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
| `NYCEPULSEANNUALFEE` | Nyce Pulse Annual Fee |
| `PULSEANNUALFEE` | Pulse Annual Fee |
| `CU24PULSEANNUALFEE` | Cu24 Pulse Annual Fee |
| `STARPULSEANNUALFEE` | Star Pulse Annual Fee |
| `ACCELPULSEANNUALFEE` | Accel Pulse Annual Fee |
| `INGENICOLINK2500` | Ingenico Link 2500, Canada (inactive) |
| `INGENICOLANE3600STD` | Ingenico Lane 3600 Std, Canada |
| `INGENICOLANE3600DLX` | Ingenico Lane 3600 Dlx, Canada (inactive) |
| `INGENICOLANE7000STD` | Ingenico Lane 7000 Std, Canada |
| `INGENICOLANE7000DLX` | Ingenico Lane 7000 Dlx, Canada (inactive) |
| `INGENICOMOVE5000` | Ingenico Move 5000, Canada (inactive) |

