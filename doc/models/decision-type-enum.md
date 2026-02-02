
# Decision Type Enum

## Enumeration

`DecisionTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `MERCHANTFAILURELIMIT` | Exceeded the maximum number of allowed failed authorizations. |
| `MERCHANTFAILURERATIO` | Exceeded the maximum ratio of allowed failed authorizations. |
| `SALETOTALLIMIT` | Exceeded the maximum allowed sale total value. |
| `REFUNDTOTALLIMIT` | Exceeded the maximum allowed refund total value. |
| `AVERAGESALECOUNTLIMIT` | Exceeded the allowed maximum payment size (individual transaction amount). |
| `MERCHANTREFUNDSALERATIO` | Exceeded the maximum allowed ratio of refunds to sales. |
| `MERCHANTPAYMENTSUCCESSLIMIT` | This is used to check if the merchant has charged the same payment more than X times on a given period of time. |
| `IPFAILURELIMIT` | Exceeded the maximum allowed number of failed authorizations for a particular IP address. |
| `IPFAILURERATIO` | Exceeded the maximum allowed ratio of failed authorizations for a particular IP address. |
| `INACTIVEMERCHANT` | The Merchant is not active. |
| `MERCHANTPAYMENTFAILURELIMIT` | Exceeded the maximum allowed number of failed transactions. |
| `MERCHANTCAPTUREWITHOUTAUTHLIMIT` | Exceeded the maximum allowed number of transactions without authorizations. |
| `REFUNDWITHOUTSALE` | Refund transaction does not have an associated sale transaction. |
| `REFUNDWITHOUTSALELIMIT` | Exceeded the maximum number of refund transactions that do not have associated sale transactions. |
| `CAPTUREABOVEAUTHLIMIT` | Exceeded the maximum authorized value for transactions with failed authorizations. |
| `FRAUDSCORE` | Transaction fraud score. |
| `CVV` | CVV. |
| `AVS` | AVS. |
| `AAVS` | AAVS. |
| `DUPLICATETXN` | Duplicate transaction. |
| `MERCHANTMATCH` | Transaction matches merchant details. |
| `CURRENCYCONVERSION` | Transaction triggers currency conversion. |
| `SETTLEDCURRENCYMISMATCH` | Transaction settled currency mismatch. |
| `INITIALTXN` | Initial transaction of this type. |
| `SIMILARTOTALLIMIT` | Exceeded the limit of transactions with equal totals. |
| `SIMILARTOTALRATIO` | Exceeded the ratio of transactions with equal totals. |
| `SALETOTALMINIMUM` | Minimum transaction amount. |
| `LIMIT` | Exceeded the maximum allowed number of authorizations. |
| `RATIO` | This is used to check if similar transactions have reached the ratio of auth transactions in a given period of time. |
| `TXNWATCHLIST` | Check the transaction data against a custom watchlist. |
| `BALANCEREFUNDLIMIT` | This is used to check if a merchant has enough balance to process a REFUND transaction and it is within the scope of the threshold. |

