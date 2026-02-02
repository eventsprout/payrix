
# Verification Ref Action Enum

## Enumeration

`VerificationRefActionEnum`

## Fields

| Name | Description |
|  --- | --- |
| `NONE` | No action. |
| `BLOCK` | Block txn, will never be processed. The Entity is sent to the manual review queue. |
| `HOLD` | Hold txn, will not be captured. |
| `RESERVE` | Reserve txn, funds should be reserved. |
| `LIMIT` | Block current activity, no change for merchant. |
| `PASS` | Passed decision(s). Will not be set anywhere, will only be used for integration purposes. |
| `POSTREVIEWONLY` | PostReviewOnly. |
| `MANUALREVIEW` | manualReview. |
| `APPROVED` | approved. |
| `DECLINED` | declined. |

