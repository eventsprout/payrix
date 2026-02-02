
# Decisions Target Enum

## Enumeration

`DecisionsTargetEnum`

## Fields

| Name | Description |
|  --- | --- |
| `ACTIVATION` | Terminal activation. |
| `AUTH` | Apply this decision during transaction authorization. |
| `POSTAUTH` | Immediately after authorization. |
| `CAPTURE` | Apply this decision during transaction capture. |
| `REFUND` | Apply this decision when processing a refund. |
| `CREATEENTITY` | Process decisions during entity creation. |
| `UNDERWRITING` | Underwriting. Check the members before they are boarded. |
| `PREBOARD` | Preboard. Check the Merchant before they are boarded. |
| `POSTBOARD` | Check the Merchant after they are boarded. |
| `TXN` | Check the Merchant when they process a Transaction. |
| `TXNVOLUME` | Check the Merchant when their transaction volume hits a certain amount. |
| `PAYOUT` | Check the Merchant when a Payout occurs. |
| `PAYOUTVOLUME` | Check the Merchant when the volume of Payouts to the Merchant hits a certain amount. |

