
# Fee Schedule Enum

## Enumeration

`FeeScheduleEnum`

## Fields

| Name | Description |
|  --- | --- |
| `DAYS` | Days |
| `WEEKS` | Weeks |
| `MONTHS` | Months |
| `YEARS` | Years |
| `SINGLE` | Single |
| `AUTH` | Auth |
| `CAPTURE` | Capture |
| `REFUND` | Refund Only For Txn Refunds |
| `BOARD` | Board |
| `PAYOUT` | Payout |
| `CHARGEBACK` | Chargeback Include These Chargeback Cycles First Representment Pre Arbitration |
| `OVERDRAFT` | Overdraft |
| `INTERCHANGE` | Interchange |
| `PROCESSOR` | Processor |
| `ACHFAIL` | Ach Fail |
| `ACCOUNT` | Account |
| `SIFT` | Sift |
| `ADJUSTMENT` | Adjustment |
| `RETRIEVAL` | Retrieval Retrieval Request Chargeback |
| `ARBITRATION` | Arbitration Arbitration Chargeback |
| `ECSALE` | Ec Sale Ec Sale Transaction |
| `ECREFUND` | Ec Refund Ec Refund Transaction |
| `ECRETURN` | Ec Return Ec Return Returns |
| `SETTLEMENT` | Settlement Txn Settlement Legacy |
| `MISUSE` | Misuse Misuse Of Authorization |
| `PROFITSHARE` | Profit Share Profit Sharing Entry Event |
| `UNAUTH` | Unauth Unauth Transaction |
| `ACHNOC` | Ach Noc Disbursement Noc |
| `ECNOC` | Ec Noc Transaction Noc |
| `ECFAIL` | Ec Fail Echeck Transaction Failure Return |
| `ECNSF` | Ec Nsf Echeck Transaction Nsf Return |
| `CURRENCYCONVERSION` | Currency Conversion Currency Conversion Fee |
| `TERMINALTXN` | Terminal Txn Terminal Txns Fee |
| `REVERSEPAYOUT` | Reverse Payout Reverse Payout Fee |
| `PARTIALREVERSEPAYOUT` | Partial Reverse Payout Partial Reverse Payout Fee |
| `PAYMENTCHECK` | Payment Check Single Payment Check Deprecated |
| `PAYMENTUPDATE` | Payment Update Single Payment Update |
| `PAYMENTGROUPCHECK` | Payment Group Check Group Payment Check Deprecated |
| `PAYMENTGROUPUPDATE` | Payment Group Update Group Payment Update |
| `ENTRYREFUND` | Entry Refund Entry Refunds |
| `STATEMENT` | Statement Payment Of Statement |
| `MERCHANTCREATION` | Merchant Creation Merchant Fee Upon Creation |
| `REALTIMEBUSINESSSEARCH` | Realtime Business Search Real Time Business Search |
| `REALTIMEMEMBERSEARCH` | Realtime Member Search Real Time Member Search |
| `MASTERCARDMATCH` | Master Card Match Mastercard Match |
| `BUSINESSINSTANTID` | Business Instant Id Business Instant Id |
| `CONSUMERINSTANTID` | Consumer Instant Id Consumer Instant Id |
| `THREATMETRIX` | Threat Metrix Threat Metrix |
| `LEGITSCRIPTREGISTER` | Legit Script Register Legit Script Register |
| `EQUIFAXCONSUMERREPORT` | Equifax Consumer Report Equifax Consumer Report |
| `GUIDESTAR` | Guide Star Guidestar |
| `PAYLOADATTRIBUTE` | Payload Attribute Internal Decision V2 |
| `TINCHECK` | Tin Check Tin Check |
| `EQUIFAXCOMMERCIALREPORT` | Equifax Commercial Report Equifax Commercial Report |
| `LEGITSCRIPTCHECKMERCHANT` | Legit Script Check Merchant Legit Script Check Merchant |
| `PLAID` | Plaid Plaid |
| `STATEMENTREVERSAL` | Statement Reversal Reversal Of Statement |
| `GIACTECHECK` | Giact Echeck Giact Call Made To Verify Creator Echeck Bank Account |
| `GIACTBANKACCOUNT` | Giact Bank Account Giact Calls To Verify Merchant Settlement Account On Sign Up Or Post Boarding Account |
| `BOARDDECISION` | Board Decision Process Decision Fee After Board |
| `TXNRISKDECISION` | Txn Risk Decision Txn Going Through A Risk Decision |
| `FANF` | Fanf External Fees |
| `MCLOCATION` | Mc Location External Fees |
| `VISAINTEGRITY` | Visa Integrity External Fees |
| `SAFERPAYMENTSBASIC` | Safer Payments Basic External Fees |
| `SAFERPAYMENTSMANAGED` | Safer Payments Managed External Fees |
| `SAFERPAYMENTSNONVALIDATION` | Safer Payments Non Validation External Fees |
| `OMNITOKENSVOLUME` | Omni Tokens Volume External Fees |
| `PAYOUTRETURN` | Payout Return Payout Return |
| `PAYOUTPARTIALRETURN` | Payout Partial Return Payout Partial Return |
| `REVSHARE` | Rev Share Rev Share |
| `CARDSETTLEMENT` | Card Settlement Txns Card Settlement |
| `ECHECKSETTLEMENT` | Echeck Settlement Txns E Check Settlement |
| `REVSHARECARD` | Rev Share Card Rev Share Schedules |
| `REVSHAREECHECK` | Rev Share Echeck Rev Share Schedules |
| `REVSHAREDBM` | Rev Share Dbm Rev Share Schedules |
| `PLAIDIDENTITYMACH` | Plaid Identity Mach |
| `TXNPLAIDIDENTITYMACH` | Txn Plaid Identity Mach |
| `PLAIDGETIDENTITY` | Plaid Get Identity |
| `TXNPLAIDGETIDENTITY` | Txn Plaid Get Identity |
| `PLAIDGETAUTH` | Plaid Get Auth |
| `TXNPLAIDGETAUTH` | Txn Plaid Get Auth |
| `OMNITOKENSMONTHLY` | Omnitokens Monthly Fee. |
| `VALUTECESSENTIALGIFT` | Valutec Essential Gift External Fees |
| `VALUTECESSENTIALMONTHLYTXN` | Valutec Essential Monthly Txn External Fees |
| `VALUTECDIGITALGIFTPLUSPACKAGE` | Valutec Digital Gift Plus Package External Fees |
| `VALUTECDIGITALGIFTPLUSPACKAGETXN` | Valutec Digital Gift Plus Package Txn External Fees |
| `VALUTECLOYALTYPLUSPACKAGE` | Valutec Loyalty Plus Package External Fees |
| `VALUTECLOYALTYPLUSPACKAGETXN` | Valutec Loyalty Plus Package Txn External Fees |
| `VALUTECTRANSACTIONFEE` | Valutec Transaction Fee External Fees |
| `VALUTECSETUPFEE` | Valutec Setup Fee External Fees |
| `VALUTECGIFTACHPOOLING` | Valutec Gift Ach Pooling External Fees |
| `VALUTECJUMPSTARTKIT` | Valutec Jump Start Kit External Fees |
| `VALUTECLAUNCHBOXKIT` | Valutec Launch Box Kit External Fees |
| `VALUTEC500CUSTOMCARDS` | Valutec 500 Custom Cards External Fees |
| `VALUTECMAINTENANCEFEE` | Valutec Maintenance Fee External Fees |
| `VALUTECDIGITALGIFTPLUSPACKAGEME` | Valutec Digital Gift Plus Package Me External Fees |
| `EFEMWCRESIDUALATELIO` | Efe Mwc Residual Atelio |
| `EFEMWCRESIDUALPARAFIN` | Efe Mwc Residual Parafin |
| `EFEMWCBILLING` | Efe Mwc Billing |
| `FRAUDSIGHTCNPDECISION` | Fraudsight Cnp Decision |
| `FRAUDSIGHTCPDECISION` | Fraudsight Cp Decision |
| `VALUTECOVERAGETRANSACTIONFEE` | Valutec Overage Transaction Fee |
| `VALUTECSTANDARDMOBILEPASSMONTHLYAPPLE` | Valutec Standard Mobile Pass Monthly Apple |
| `VALUTECNFCMOBILEPASSMONTHLY` | Valutec Nfc Mobile Pass Monthly |
| `VALUTECSTANDARDMOBILEPASSMONTHLYGOOGLE` | Valutec Standard Mobile Pass Monthly Google |
| `VALUTECONLINEGIFTWEBSITEMONTHLY` | Valutec Online Gift Website Monthly |
| `VALUTECMARKETING360MONTHLY` | Valutec Marketing 360 Monthly |
| `VALUTECONLINEGIFTCARDVOLUMEFEE` | Valutec Online Gift Card Volume Fee |
| `VALUTECSOCIALSHARINGMONTHLY` | Valutec Social Sharing Monthly |
| `VALUTECDIGICARDMONTHLY` | Valutec Digicard Monthly |
| `VALUTECLOYALTYSTANDARDMONTHLY` | Valutec Loyalty Standard Monthly |
| `VALUTECAUTOREWARDSLPRMONTHLY` | Valutec Auto Rewards Lpr Monthly |
| `VALUTECONECARDSETUPFEE` | Valutec Onecard Setup Fee |
| `VALUTECONECARDMONTHLYFEE` | Valutec Onecard Monthly Fee |
| `VALUTECMONTHLYFEECHOICE` | Valutec Monthly Fee Choice |
| `VALUTECSYSTEMACCESS` | Valutec System Access |
| `VALUTECTRANSACTION` | Valutec Transaction |
| `VALUTECMONTHLYFEELAUNCHBOX` | Valutec Monthly Fee Launchbox |
| `VALUTECMONTHLYFEEJUMPSTART` | Valutec Monthly Fee Jumpstart |
| `VALUTECONECARDPHYSICALFULFILLMENTFEE` | Valutec Onecard Physical Fulfillment Fee |
| `VALUTECONECARDVIRTUALFULFILLMENTFEE` | Valutec Onecard Virtual Fulfillment Fee |
| `VALUTECCUSTOMIZEDREPORTING` | Valutec Customized Reporting |
| `VALUTECTRANSACTIONFILEFEED` | Valutec Transaction File Feed |
| `VALUTEC250CUSTOMCARDS` | Valutec 250 Custom Cards |
| `VALUTEC1000CUSTOMCARDS` | Valutec 1000 Custom Cards |
| `VALUTEC2500CUSTOMCARDS` | Valutec 2500 Custom Cards |
| `VALUTEC5000CUSTOMCARDS` | Valutec 5000 Custom Cards |
| `VALUTEC10000CUSTOMCARDS` | Valutec 10000 Custom Cards |
| `VALUTEC15000CUSTOMCARDS` | Valutec 15000 Custom Cards |
| `VALUTEC20000CUSTOMCARDS` | Valutec 20000 Custom Cards |
| `VALUTEC25000CUSTOMCARDS` | Valutec 25000 Custom Cards |
| `VALUTEC250EXPRESSCARDS` | Valutec 250 Express Cards |
| `VALUTEC500EXPRESSCARDS` | Valutec 500 Express Cards |
| `VALUTEC1000EXPRESSCARDS` | Valutec 1000 Express Cards |
| `VALUTEC2500EXPRESSCARDS` | Valutec 2500 Express Cards |
| `VALUTEC5000EXPRESSCARDS` | Valutec 5000 Express Cards |
| `VALUTEC10000EXPRESSCARDS` | Valutec 10000 Express Cards |
| `VALUTECSPECIALTYCARDS` | Valutec Specialty Cards |
| `VALUTECKEYTAGS` | Valutec Keytags |
| `VALUTECSLEEVESCARRIERSHANGERS` | Valutec Sleeves Carriers Hangers |
| `VALUTECSIGNATUREPANEL` | Valutec Signature Panel |
| `VALUTEC44PRINTING` | Valutec 4 4 Printing |
| `VALUTECSPECIALTYFINISH` | Valutec Specialty Finish |
| `VALUTECPANTONE` | Valutec Pantone |
| `VALUTECPINSCRATCH` | Valutec Pin Scratch |
| `VALUTECMERCHANDISE` | Valutec Merchandise |
| `VALUTECGIFTCARDDESIGNSETUPFEE` | Valutec Gift Card Design Setup Fee |
| `VALUTECSHIPPINGHANDLING` | Valutec Shipping Handling |
| `VALUTECRUSHFEES` | Valutec Rush Fees |
| `VALUTECSEQUENCING` | Valutec Sequencing |
| `VALUTECWHOLESALEFULFILLMENTFEE` | Valutec Wholesale Fulfillment Fee |
| `VALUTECMISCELLANEOUSFEES` | Valutec Miscellaneous Fees |
| `VALUTECHOSTINGFEE` | Valutec Hosting Fee |
| `VALUTECSTORECARDMONTHLYFEE` | Valutec Storecard Monthly Fee |
| `VALUTECGIFTACHFEEMONTHLY` | Valutec Gift Ach Fee Monthly |
| `VALUTECONECARDMONTHLYFEESTORECARD` | Valutec Onecard Monthly Fee Storecard |
| `REVBOOSTEMBEDDEDTMSMONTHLY` | Revboost Embedded Tms Monthly |
| `REVBOOSTEMBEDDEDTMSPPT` | Revboost Embedded Tms Ppt |
| `TXNTHREATMETRIX` | Txn Threat Metrix |
| `THREATMETRIXEMAILAGE` | Threat Metrix Emailage |
| `THREATMETRIXFRAUDPOINT` | Threat Metrix Fraud Point |
| `GIACTINQUIRY` | Giact Inquiry |
| `GIACTTXNGAUTHENTICATE` | Giact Txn Gauthenticate |
| `TRULIOOIDV` | Trulioo Idv |
| `TRULIOOAMLLDV` | Trulioo Amll Dv |
| `TRULIOOBUSINESSVERIFICATION` | Trulioo Business Verification |
| `THREATMETRIXPHONEFINDER` | Threat Metrix Phone Finder |
| `TIERNONQUALIFIEDCOUNT` | Tier Non Qualified Count |
| `TIERQUALIFIEDCOUNT` | Tier Qualified Count |
| `TIERMIDQUALIFIEDCOUNT` | Tier Mid Qualified Count |
| `TIERHIGHRISKCOUNT` | Tier High Risk Count |
| `TIERNONQUALIFIEDVOLUME` | Tier Non Qualified Volume |
| `TIERQUALIFIEDVOLUME` | Tier Qualified Volume |
| `TIERMIDQUALIFIEDVOLUME` | Tier Mid Qualified Volume |
| `TIERHIGHRISKVOLUME` | Tier High Risk Volume |
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
| `PAYRIXEQUIPMENTSETUPFEE` | Payrix Equipment |

