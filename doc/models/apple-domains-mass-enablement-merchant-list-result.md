
# Apple Domains Mass Enablement Merchant List Result

## Structure

`AppleDomainsMassEnablementMerchantListResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `msg` | `?string` | Optional | Current verification status of the Apple Pay domain registration. | getMsg(): ?string | setMsg(?string msg): void |
| `status` | `?string` | Optional | Status of the Apple domain change<br><br><details><br><summary>Valid Values</summary><br>- `success` - **Domain successfully verified**<br>- `failed` - **Domain verification failed**<br></details><br> | getStatus(): ?string | setStatus(?string status): void |

## Example (as JSON)

```json
{
  "msg": "msg0",
  "status": "status6"
}
```

