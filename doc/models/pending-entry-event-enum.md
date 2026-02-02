
# Pending Entry Event Enum

## Enumeration

`PendingEntryEventEnum`

## Fields

| Name | Description |
|  --- | --- |
| `DAYS` | The PendingEntry for an Entry that triggers every day. |
| `WEEKS` | The PendingEntry for an Entry that triggers every week. |
| `MONTHS` | The PendingEntry for an Entry that triggers every month. |
| `YEARS` | The PendingEntry for an Entry that triggers every year. |
| `SINGLE` | The PendingEntry for an Entry related to a one-off event. |
| `AUTH` | The PendingEntry for an Entry related to the time of authorization of a transaction. |
| `CAPTURE` | The PendingEntry for an Entry related to the capture time of a Transaction. |
| `REFUND` | The PendingEntry for an Entry related to when a refund transaction is processed. |
| `BOARD` | The PendingEntry for an Entry related to when the Merchant is boarded. |
| `PAYOUT` | The PendingEntry for an Entry related to when a payout is processed. |
| `CHARGEBACK` | The PendingEntry for an Entry related to when a card chargeback occurs. |
| `OVERDRAFT` | The PendingEntry for an Entry related to when an overdraft usage charge from a bank is levied. |
| `INTERCHANGE` | The PendingEntry for an Entry related to when interchange Fees are assessed for the Transactions of this Merchant. |
| `PROCESSOR` | The PendingEntry for an Entry related to when the Transactions of this Merchant are processed by a payment processor. |
| `ACHFAIL` | The PendingEntry for an Entry related to when an automated clearing house failure occurs. |
| `ACCOUNT` | The PendingEntry for an Entry related to when a bank account is verified. |
| `SIFT` | The PendingEntry for an Entry related to Transaction fraud score. |
| `ADJUSTMENT` | The PendingEntry for an Entry related to adjusted funds. |
| `RETRIEVAL` | The PendingEntry for an Entry related to Retrieval Request Chargeback. |
| `ARBITRATION` | The PendingEntry for an Entry related to Arbitration Chargeback. |
| `ECSALE` | The PendingEntry for an Entry related to an eCheck Sale. |
| `ECREFUND` | The PendingEntry for an Entry related to an eCheck Refund. |
| `ECRETURN` | The PendingEntry for an Entry related to an eCheck Return. |
| `SETTLEMENT` | The PendingEntry for an Entry related to transaction settlement. |
| `MISUSE` | The PendingEntry for an Entry related to Misuse of authorization. |
| `PROFITSHARE` | The PendingEntry for an Entry related to a profit sharing entry. |
| `UNAUTH` | The PendingEntry for an Entry related to an unauthorized entry. |
| `ACHNOC` | The PendingEntry for an Entry related to an ACH Notification of Change. |
| `ECNOC` | The PendingEntry for an Entry related to an eCheck Notifications of Change. |
| `ECFAIL` | The PendingEntry for an Entry related to an eCheck Fail. |
| `ECNSF` | The PendingEntry for an Entry related to an eCheck Non-Sufficient Funds. |
| `CURRENCYCONVERSION` | The PendingEntry for an Entry related to a currency conversion. |
| `TERMINALTXN` | The PendingEntry for an Entry related to a terminal transaction. |
| `REVERSEPAYOUT` | The PendingEntry for an Entry related to a payout that's been reversed. |
| `PARTIALREVERSEPAYOUT` | The PendingEntry for an Entry related to a payout that's been partially reversed. |
| `PAYMENTCHECK` | The PendingEntry for an Entry related to a single payment check (deprecated). |
| `PAYMENTUPDATE` | The PendingEntry for an Entry related to a single payment update. |
| `PAYMENTGROUPCHECK` | The PendingEntry for an Entry related to a group payment check (deprecated). |
| `PAYMENTGROUPUPDATE` | The PendingEntry for an Entry related to a group payment update. |
| `ENTRYREFUND` | The PendingEntry for an Entry related to entry refunds. |
| `STATEMENT` | The PendingEntry for an Entry related to the payment of a statement. |
| `MERCHANTCREATION` | The PendingEntry for an Entry related to a merchant fee upon creation. |
| `REALTIMEBUSINESSSEARCH` | The PendingEntry for an Entry related to a real-time business search. |
| `REALTIMEMEMBERSEARCH` | The PendingEntry for an Entry related to a real-time member search. |
| `MASTERCARDMATCH` | The PendingEntry for an Entry related to Mastercard match. |
| `BUSINESSINSTANTID` | The PendingEntry for an Entry related to a business instant ID. |
| `CONSUMERINSTANTID` | The PendingEntry for an Entry related to a consumer instant ID. |
| `THREATMETRIX` | The PendingEntry for an Entry related to Threat Metrix. |
| `LEGITSCRIPTREGISTER` | The PendingEntry for an Entry related to Legit Script Register. |
| `EQUIFAXCONSUMERREPORT` | The PendingEntry for an Entry related to Equifax consumer report. |
| `GUIDESTAR` | The PendingEntry for an Entry related to Guide Star. |
| `PAYLOADATTRIBUTE` | The PendingEntry for an Entry related to internal decision V2. |
| `TINCHECK` | The PendingEntry for an Entry related to a Tin Check. |
| `EQUIFAXCOMMERCIALREPORT` | The PendingEntry for an Entry related to Equifax commercial report. |
| `LEGITSCRIPTCHECKMERCHANT` | The PendingEntry for an Entry related to Legit Script Check Merchant. |
| `PLAID` | The PendingEntry for an Entry related to Plaid. |
| `STATEMENTREVERSAL` | The PendingEntry for an Entry related to the reversal of a statement. |
| `GIACTECHECK` | The PendingEntry for an Entry related to GIACT call made to verify creator Echeck bank account. |
| `GIACTBANKACCOUNT` | The PendingEntry for an Entry related to Giact calls to verify merchant settlement account. |
| `BOARDDECISION` | The PendingEntry for an Entry related to process decision fee after board. |
| `TXNRISKDECISION` | The PendingEntry for an Entry related to a transaction going through a risk decision. |
| `FANF` | The PendingEntry for an Entry related to external fees. |
| `MCLOCATION` | The PendingEntry for an Entry related to external fees. |
| `VISAINTEGRITY` | The PendingEntry for an Entry related to external fees. |
| `SAFERPAYMENTSBASIC` | The PendingEntry for an Entry related to external fees. |
| `SAFERPAYMENTSMANAGED` | The PendingEntry for an Entry related to external fees. |
| `SAFERPAYMENTSPCINONVALIDATION` | The PendingEntry for an Entry related to external fees. |
| `OMNITOKENSVOLUME` | The PendingEntry for an Entry related to external fees. |
| `PAYOUTRETURN` | The PendingEntry for an Entry related to a payout return. |
| `PAYOUTPARTIALRETURN` | The PendingEntry for an Entry related to a partial payout return. |
| `REVSHARE` | The PendingEntry for an Entry related to revenue sharing. |
| `CARDSETTLEMENT` | The PendingEntry for an Entry related to card settlement. |
| `ECHECKSETTLEMENT` | The PendingEntry for an Entry related to e-check settlement. |
| `REVSHARECARD` | The PendingEntry for an Entry related to revenue sharing for cards. |
| `REVSHAREECHECK` | The PendingEntry for an Entry related to revenue sharing for e-checks. |
| `REVSHAREDBM` | The PendingEntry for an Entry related to revenue sharing for DBM. |
| `PREARBITRATION` | The PendingEntry for an Entry related to chargeback pre-arbitration. |
| `PLAIDIDENTITYMACH` | The PendingEntry for an Entry related to Plaid Identity Mach. |
| `TXNPLAIDIDENTITYMACH` | The PendingEntry for an Entry related to transactions with Plaid Identity Mach. |
| `PLAIDGETIDENTITY` | The PendingEntry for an Entry related to Plaid Get Identity. |
| `TXNPLAIDGETIDENTITY` | The PendingEntry for an Entry related to transactions with Plaid Get Identity. |
| `PLAIDGETAUTH` | The PendingEntry for an Entry related to Plaid Get Auth. |
| `TXNPLAIDGETAUTH` | The PendingEntry for an Entry related to transactions with Plaid Get Auth. |
| `REVERSAL` | The PendingEntry for an Entry related to chargeback reversal. |
| `REPRESENTMENT` | The PendingEntry for an Entry related to chargeback representment. |
| `OMNITOKENSMONTHLY` | The PendingEntry for an Entry related to Omnitokens Monthly Fee. |
| `ICRETAINPASSTHRUREFUND` | The PendingEntry for an Entry related to interchange retain pass-through refund. |
| `VALUTECESSENTIALGIFT` | The PendingEntry for an Entry related to external fees. |
| `VALUTECESSENTIALMONTHLYTXN` | The PendingEntry for an Entry related to external fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGE` | The PendingEntry for an Entry related to external fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGETXN` | The PendingEntry for an Entry related to external fees. |
| `VALUTECLOYALTYPLUSPACKAGE` | The PendingEntry for an Entry related to external fees. |
| `VALUTECLOYALTYPLUSPACKAGETXN` | The PendingEntry for an Entry related to external fees. |
| `VALUTECTRANSACTIONFEE` | The PendingEntry for an Entry related to external fees. |
| `VALUTECSETUPFEE` | The PendingEntry for an Entry related to external fees. |
| `VALUTECGIFTACHPOOLING` | The PendingEntry for an Entry related to external fees. |
| `VALUTECJUMPSTARTKIT` | The PendingEntry for an Entry related to external fees. |
| `VALUTECLAUNCHBOXKIT` | The PendingEntry for an Entry related to external fees. |
| `VALUTEC500CUSTOMCARDS` | The PendingEntry for an Entry related to external fees. |
| `VALUTECMAINTENANCEFEE` | The PendingEntry for an Entry related to external fees. |
| `VALUTECDIGITALGIFTPLUSPACKAGEME` | The PendingEntry for an Entry related to external fees. |
| `EFEMWCRESIDUALATELIO` | The PendingEntry for an Entry related to EFE external fees. |
| `EFEMWCRESIDUALPARAFIN` | The PendingEntry for an Entry related to EFE external fees. |
| `EFEMWCBILLING` | The PendingEntry for an Entry related to EFE external fees. |
| `FRAUDSIGHTCNPDECISION` | The PendingEntry for an Entry related to external fees. |
| `FRAUDSIGHTCPDECISION` | The PendingEntry for an Entry related to external fees. |
| `REVBOOSTEMBEDDEDTMSMONTHLY` | The PendingEntry for an Entry related to external fees. |
| `REVBOOSTEMBEDDEDTMSPPT` | The PendingEntry for an Entry related to external fees. |
| `TXNTHREATMETRIX` | The PendingEntry for an Entry related to external fees. |
| `THREATMETRIXEMAILAGE` | The PendingEntry for an Entry related to external fees. |
| `THREATMETRIXFRAUDPOINT` | The PendingEntry for an Entry related to external fees. |
| `GIACTINQUIRY` | The PendingEntry for an Entry related to external fees. |
| `GIACTTXNGAUTHENTICATE` | The PendingEntry for an Entry related to external fees. |
| `TRULIOOIDV` | The PendingEntry for an Entry related to external fees. |
| `TRULIOOAMLLDV` | The PendingEntry for an Entry related to external fees. |
| `TRULIOOBUSINESSVERIFICATION` | The PendingEntry for an Entry related to external fees. |
| `THREATMETRIXPHONEFINDER` | The PendingEntry for an Entry related to external fees. |
| `TIERNONQUALIFIEDCOUNT` | The PendingEntry for an Entry related to risk-based tier fees. |
| `TIERQUALIFIEDCOUNT` | The PendingEntry for an Entry related to risk-based tier fees. |
| `TIERMIDQUALIFIEDCOUNT` | The PendingEntry for an Entry related to risk-based tier fees. |
| `TIERHIGHRISKCOUNT` | The PendingEntry for an Entry related to risk-based tier fees. |
| `TIERNONQUALIFIEDVOLUME` | The PendingEntry for an Entry related to risk-based tier fees. |
| `TIERQUALIFIEDVOLUME` | The PendingEntry for an Entry related to risk-based tier fees. |
| `TIERMIDQUALIFIEDVOLUME` | The PendingEntry for an Entry related to risk-based tier fees. |
| `TIERHIGHRISKVOLUME` | The PendingEntry for an Entry related to risk-based tier fees. |

