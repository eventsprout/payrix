
# Fund Origins Response

## Structure

`FundOriginsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `fund` | string\|[FundsResponse](../../doc/models/funds-response.md)\|null | Optional | The fund for which the amount is available from this source. | getFund(): | setFund( fund): void |
| `disbursement` | string\|[DisbursementsResponse](../../doc/models/disbursements-response.md)\|null | Optional | ID of the disbursement related to this fund. | getDisbursement(): | setDisbursement( disbursement): void |
| `amount` | `?float` | Optional | The amount of funds available from this source, in cents(up to three decimal points). | getAmount(): ?float | setAmount(?float amount): void |
| `funding` | string([FundOriginPlatformEnum](../../doc/models/fund-origin-platform-enum.md))\|[EntityRefsResponse](../../doc/models/entity-refs-response.md)\|null | Optional | The processor's funding ID (related to a merchant, this field is required if the adjustment is not between entities. | getFunding(): | setFunding( funding): void |
| `fbo` | `?string` | Optional | FBO which this fund is drawn from. | getFbo(): ?string | setFbo(?string fbo): void |
| `platform` | [`?string(PlatformModelEnum)`](../../doc/models/platform-model-enum.md) | Optional | The platform used to process this resource.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **The Apple Payment Processor.**<br>- `ELAVON` - **The Elavon processor.**<br>- `FIRSTDATA` - **The FirstData processor.**<br>- `GOOGLE` - **The Google Payment Processor.**<br>- `VANTIV` - **The WorldPay (aka Vantiv or Litle) eComm (aka VAP) processor.**<br>- `VCORE` - **The WorldPay (aka Vantiv) Core processor.**<br>- `TDBANKCA` - **External funding with TD Bank Canada via the Operating Account.**<br>- `WELLSACH` - **The Wells Fargo ACH processor.**<br>- `WELLSFARGO` - **The Wells Fargo Merchant Services processor.**<br>- `WFSINGLE` - **The WFSINGLE processor.**<br>- `WORLDPAY` - **The WORLDPAY processor.**<br></details><br> | getPlatform(): ?string | setPlatform(?string platform): void |
| `adjustment` | string\|[AdjustmentsResponse](../../doc/models/adjustments-response.md)\|null | Optional | The identifier of the Adjustment that this fund origin relates to. | getAdjustment(): | setAdjustment( adjustment): void |
| `txn` | string\|[TxnsResponse](../../doc/models/txns-response.md)\|null | Optional | The identifier of the Transaction that this fund origin relates to. | getTxn(): | setTxn( txn): void |

## Example (as JSON)

```json
{
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier6"
}
```

