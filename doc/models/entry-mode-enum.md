
# Entry Mode Enum

## Enumeration

`EntryModeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `KEYED` | Manually keyed entry. |
| `TRACK1` | Card swiped. Track 1 received. |
| `TRACK2` | Card swiped. Track 2 received. |
| `BOTH` | Card swiped. Track 1 & 2 received. |
| `EMV` | Card dipped. EMV chip received. |
| `CONTACTLESS` | Contactless card read. Track or EMV data received. |
| `FALLBACKSWIPED` | Track Data from Card Swipe after EMV chip failure. |
| `FALLBACKKEYED` | Track Data from Manually keyed entry after EMV chip failure. |
| `APPLEPAY` | ApplePay read and cryptogram data received. |
| `GOOGLEPAY` | Google Pay. |
| `MERCHANT` | Merchant created transaction. |
| `INVOICE` | Invoice payment. |
| `PAYRIXMERCHANT` | Merchant created transaction in payrix portal. |
| `PAYRIXINVOICE` | Invoice payment from payrix portal. |

