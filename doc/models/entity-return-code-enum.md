
# Entity Return Code Enum

## Enumeration

`EntityReturnCodeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `R01` | Insufficient funds in account. |
| `R02` | Account is closed. |
| `R03` | No account on file. |
| `R04` | Invalid account number. |
| `R05` | Unauthorized debit to consumer account. |
| `R06` | Returned at request of ODFI. |
| `R07` | Authorization revoked by customer. |
| `R08` | Payment stopped. |
| `R09` | Insufficient collected funds in account being charged. |
| `R10` | Customer advises not Authorized, notice not provided, improper source document, or amount of entry not accurately obtained from source document. |
| `R11` | Check truncation return. |
| `R12` | Account sold to another financial institution. |
| `R13` | Invalid ACH routing number. |
| `R14` | Representative payee is deceased or cannot continue in that capacity. |
| `R15` | Beneficiary or account holder other than representative payee deceased. |
| `R16` | Account funds have been frozen. |
| `R17` | Item returned because of invalid data; refer to addenda for information. |
| `R18` | Improper effective date. |
| `R19` | Amount error. |
| `R20` | Account does not allow ACH transactions or limit for transactions has been exceeded. |
| `R21` | Invalid company identification. |
| `R22` | Invalid individual ID. |
| `R23` | Credit entry refused by receiver. |
| `R24` | Duplicate entry. |
| `R25` | Addenda record error. |
| `R26` | Mandatory field error. |
| `R27` | Trace number error. |
| `R28` | Routing/transit number check digit error. |
| `R29` | Corporate customer advised not authorized. |
| `R30` | RDFI not participant in check truncation program. |
| `R31` | Permissible return entry. |
| `R32` | RDFI non-settlement. |
| `R33` | Return of item. |
| `R34` | Limited participation ODFI. |
| `R35` | Return of improper debit entry. |
| `R36` | Return of improper credit entry. |
| `R37` | Source document presented for payment. |
| `R38` | Stop payment on source document. |
| `R39` | Improper source document. |
| `R40` | Return of item by government agency. |
| `R41` | Invalid Transaction Code. |
| `R42` | Routing/transit number check digit error. |
| `R43` | Invalid account number. |
| `R44` | Invalid individual ID. |
| `R45` | Invalid individual name or company name. |
| `R46` | Invalid representative payee indicator code. |
| `R47` | Duplicate enrollment. |
| `R50` | State law affecting RCK acceptance. |
| `R51` | Item is ineligible, notice not provided, signature not genuine, or original item altered for adjustment entry. |
| `R52` | Stop payment on item. |
| `R53` | Item and ACH entry presented for payment. |
| `R61` | Misrouted return - RDFI for original entry has placed incorrect routing/transit number in RDFI identification field. |
| `R62` | Incorrect trace number. |
| `R63` | Incorrect dollar amount. |
| `R64` | Incorrect individual identification. |
| `R65` | Incorrect transaction code. |
| `R66` | Incorrect company identification. |
| `R67` | Duplicate return. |
| `R68` | Untimely return - return was not sent within the established timeframe. |
| `R69` | Field errors. |
| `R70` | Permissible return entry not accepted. |
| `R71` | Misrouted dishonored return - incorrect routing/transit number in RDFI identification field. |
| `R72` | Untimely return - dishonored return was not sent within the established timeframe. |
| `R73` | Timely original return - RDFI certifies the original return entry was sent within established timeframe for original returns. |
| `R74` | Corrected return - RDFI is correcting a previous return entry that was dishonored because it contained incomplete or incorrect information. |
| `R75` | Original return not a duplicate. |
| `R76` | No errors found. |
| `R80` | Cross-border payment coding error. |
| `R81` | Non-participant in cross-border program. |
| `R82` | Invalid foreign RDFI identification. |
| `R83` | Foreign RDFI unable to settle. |
| `R84` | Cross-border entry not processed by originating gateway operator. |
| `R94` | Administrative return item was processed and resubmitted as a photocopy. |
| `R95` | Administrative return item was processed and resubmitted as a MICR-Split. |
| `R97` | Administrative return item was processed and resubmitted with corrected dollar amount. |
| `R98` | Indicates a return PAC (pre-authorized check); RDFI provides a text reason and indicated a new account number on the PAC itself. |
| `R99` | Indicates a return PAC (pre-authorized check); RDFI provides a text reason on the PAC itself for which there is no equivalent return reason code. |
| `C01` | Incorrect DFI Account Number. |
| `C02` | Incorrect Transit/Routing Number. |
| `C03` | Incorrect Transit/Routing Number and Incorrect DFI Account Number. |
| `C04` | Incorrect Individual Name. |
| `C05` | Incorrect Transaction Code. |
| `C06` | Incorrect DFI Account Number and Incorrect Transaction Code. |
| `C07` | Incorrect Transit/Routing Number, Incorrect DFI Account Number, and Incorrect Transaction Code. |
| `C08` | Reserved. |
| `C09` | Incorrect Individual Identification Number. |
| `C10` | Incorrect Company Name. |
| `C11` | Incorrect Company Identification. |
| `C12` | Incorrect Company Name and Company Identification. |
| `C13` | Addenda Format Error. |
| `C61` | Misrouted Notification of Change. |
| `C62` | Incorrect Trace Number. |
| `C63` | Incorrect Company Identification Number. |
| `C64` | Incorrect Individual Identification Number. |
| `C65` | Incorrectly Formatted Corrected Data. |
| `C66` | Incorrect Discretionary Data. |
| `C67` | Routing Number Not From Original Entry Detail Record. |
| `C68` | DFI Account Number Not From Original Entry Detail Record. |
| `C69` | Incorrect Transaction Code. |
| `R90007` | Institution ID Invalid. |
| `R90008` | Account Number Invalid. |
| `R90016` | Institution ID for Return Invalid. |
| `R90017` | Account Number for Return Invalid. |
| `R900D2` | Destination Institute is Not Defined on FIF. |
| `R900E1` | Destination Account Number Invalid. |
| `R900L2` | Institution for Return Not Defined on FIF. |
| `R900L3` | Institution for Return Cross Reference Invalid. |
| `R900M1` | Account for Return Invalid. |
| `R901` | NFS (Debit Only). |
| `R902` | Cannot Trace. |
| `R903` | Payment Stopped/Recalled. |
| `R904` | Post/Stale Dated. |
| `R905` | Account Closed. |
| `R907` | No Debit Allowed. |
| `R908` | Funds Not Cleared. |
| `R909` | Currency/Account Mismatch. |
| `R910` | Payor/Payee Deceased. |
| `R911` | Account Frozen. |
| `R912` | Invalid/Incorrect Account Number. |
| `R914` | Incorrect Payor/Payee Name. |
| `R915` | PAD No Agreement Existed - Business/Personal. |
| `R916` | PAD Not According to Agreement - Personal. |
| `R917` | PAD Agreement Revoked - Personal. |
| `R918` | PAD No Confirmation/Pre-Notification - Personal. |
| `R919` | PAD Not According to Agreement - Business. |
| `R920` | PAD Agreement Revoked - Business. |
| `R921` | PAD No Confirmation/Pre-Notification - Business. |
| `R922` | Customer Initiated Return - CREDIT only. |
| `R990` | Institution in Default. |

