
# Merchants Saq Type Enum

## Enumeration

`MerchantsSaqTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `SAQA` | Card-not-present merchants (e-commerce or mail/telephone-order) with PCI DSS-validated third-party payments service provider(s) and does not store cardholder data. |
| `SAQAEP` | E-commerce merchants with PCI DSS-validated third-party payments service provider(s) with a website that doesn't directly collect cardholder data, but may impact it in some way, and does not store cardholder data. |
| `SAQB` | Merchants with imprint machines or standalone, dial-out terminals that do not store cardholder data. |
| `SAQBIP` | Merchants with standalone, PTS-approved payment terminals that have an IP connection to the payment processor, but do not store cardholder data. |
| `SAQCVT` | Merchants that enter single transactions manually into an internet-based terminal hosted by PCI DSS-validated third-party payments service provider(s) and does not store cardholder data. |
| `SAQC` | Merchants with payment application systems connected to the internet that do not store cardholder data. |
| `SAQP2PEHW` | Merchants with hardware-only payment terminals managed by a PCI SSC-listed P2PE solution, and does not store cardholder data. |
| `SAQD` | Generic field for all Merchants that do not fall under the requirements for any above SAQ types. |

