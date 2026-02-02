
# Cycle Enum

## Enumeration

`CycleEnum`

## Fields

| Name | Description |
|  --- | --- |
| `RETRIEVAL` | Initial request from the issuer for more information on this Transaction. |
| `FIRST` | First Chargeback from issuer for this Transaction. |
| `ARBITRATION` | Arbitration is being sought for this Chargeback. |
| `REVERSAL` | Chargeback was reversed. |
| `REPRESENTMENT` | Merchant is being represented to the issuer with the Chargeback response posted. |
| `PREARBITRATION` | Chargeback is no longer representable, Merchant must choose to accept or arbitrate with the card brand. |
| `ARBITRATIONLOST` | Arbitration lost. |
| `ARBITRATIONSPLIT` | Arbitration split. |
| `ARBITRATIONWON` | Arbitration won. |
| `ISSUERACCEPTPREARBITRATION` | Issuer accepted the pre-arbitration response. |
| `ISSUERDECLINEDPREARBITRATION` | Issuer declined pre-arbitration. |
| `RESPONSETOISSUERPREARBITRATION` | Response to issuer pre-arbitration. |
| `MERCHANTACCEPTEDPREARBITRATION` | Merchant accepted the pre-arbitration response. |
| `MERCHANTDECLINEDPREARBITRATION` | Merchant declined the pre-arbitration response. |
| `PRECOMPLIANCE` | Pre-compliance. |
| `COMPLIANCE` | Compliance. |

