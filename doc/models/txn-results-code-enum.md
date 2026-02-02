
# Txn Results Code Enum

## Enumeration

`TxnResultsCodeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `APPROVED` | Transaction approved. |
| `PARTIALLYAPPROVED` | Partially approved. The processor has only approved a portion of the total transaction amount. |
| `DECLINED` | Declined. The processor has declined the Transaction. |
| `MATCH` | Verification successful, values provided matched. |
| `NOMATCH` | Verification unsuccessful, values provided did not match. |
| `ZIPNOMATCH` | The ZIP code in the Transaction data does not match the customer details held by the card issuer. |
| `ADDRESSNOMATCH` | The address in the Transaction data does not match the customer details held by the card issuer. |
| `NAMENOMATCH` | The name in the Transaction data does not match the customer details held by the card issuer. |
| `NAMEPHONENOMATCH` | The name and phone number in the Transaction data do not match the details held by the card issuer. |
| `NAMEEMAILNOMATCH` | The name and email address in the Transaction data do not match the customer details held by the card issuer. |
| `PHONENOMATCH` | The phone number in the Transaction data does not match the customer details held by the card issuer. |
| `PHONEEMAILNOMATCH` | The phone number and email address in the Transaction data do not match the customer details held by the card issuer. |
| `EMAILNOMATCH` | The email address in the Transaction data does not match the customer details held by the card issuer. |
| `NAMEUNAVAILABLE` | The customer name could not be found in the Transaction data. |
| `NAMEPHONEUNAVAILABLE` | The customer name and phone number were not found in the Transaction data. |
| `NAMEEMAILUNAVAILABLE` | The customer name and email address were not found in the Transaction data. |
| `PHONEUNAVAILABLE` | The customer phone number was not found in the Transaction data. |
| `PHONEEMAILUNAVAILABLE` | The customer phone number and email address were not found in the Transaction data. |
| `EMAILUNAVAILABLE` | The customer email address was not found in the Transaction data. |
| `UNAVAILABLE` | Information about the customer was not found in the Transaction data. |
| `NSF` | Non-sufficient funds. The customer did not have sufficient credit or balance to cover the Transaction. |
| `BADACCOUNT` | The account in the Transaction data is not valid. |
| `UNAUTHORIZED` | The account is unauthorized. |
| `GENERAL` | General error. |
| `ZIPNOTVERIFIED` | The ZIP code in the Transaction data was not verified. |
| `ZIPADDRESSNOTVERIFIED` | The ZIP code and the Address in the Transaction data were not verified. |
| `ADDRESSNOTVERIFIED` | The Address in the Transaction data was not verified. |
| `WARNING` | Txn did not fail but was not captured. |
| `ENUM_28` | 3DS authentication passed. |
| `ENUM_29` | 3DS authentication is invalid. |
| `ENUM_30` | 3DS authentication failed. |
| `ENUM_31` | 3DS authentication was not validated. |
| `ENUM_32` | 3DS authentication passed without liability shift. |
| `TIMEOUT` | Transaction processing timed out. |
| `CANCELLED` | Transaction cancelled. |

