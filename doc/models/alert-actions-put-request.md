
# Alert Actions Put Request

## Structure

`AlertActionsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `alert` | `?string` | Optional | The identifier of the Alert resource that defines this alertAction. | getAlert(): ?string | setAlert(?string alert): void |
| `headerName` | `?string` | Optional | The request header name for authentication to the endpoint. | getHeaderName(): ?string | setHeaderName(?string headerName): void |
| `headerValue` | `?string` | Optional | The request header value for authentication to the endpoint. | getHeaderValue(): ?string | setHeaderValue(?string headerValue): void |
| `options` | `?string` | Optional | When the 'type' field of this resource is set to 'web', this field determines the format that the Alert data should be sent in. | getOptions(): ?string | setOptions(?string options): void |
| `value` | `?string` | Optional | A value used to deliver the alert. Thie field should be set to an email address if the type is email, an endpoint if the type is web, etc. | getValue(): ?string | setValue(?string value): void |
| `retries` | `?int` | Optional | The number of times an alert should be resent in case of a failure. This fields can only be set for web type alertActions. | getRetries(): ?int | setRetries(?int retries): void |
| `maxAttemptsTempDisabled` | [`?int(AlertActionsMaxAttemptsTempDisabledEnum)`](../../doc/models/alert-actions-max-attempts-temp-disabled-enum.md) | Optional | Whether it was temporarily disabled for reaching the maximum number of failed attempts.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Temporarily Disabled**<br>- `1` - **Temporarily Disabled**<br></details><br> | getMaxAttemptsTempDisabled(): ?int | setMaxAttemptsTempDisabled(?int maxAttemptsTempDisabled): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "alert": "t1_alt_65fddb118236188e055d54c",
  "options": "JSON",
  "value": "https://test.payrix.com/apix/test/t1",
  "maxAttemptsTempDisabled": 0,
  "headerName": "Authorization",
  "headerValue": "SecrtToken1234!",
  "retries": 3,
  "inactive": 0,
  "frozen": 0
}
```

