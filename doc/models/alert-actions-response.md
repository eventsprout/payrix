
# Alert Actions Response

## Structure

`AlertActionsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `type` | [`?string(AlertActionTypeEnum)`](../../doc/models/alert-action-type-enum.md) | Optional | The medium to use to deliver this Alert.<br><br><details><br><summary>Valid Values</summary><br>- `email` - **Deliver the Alert to an email address.**<br>- `web` - **Deliver the Alert through a web site notification.**<br>- `app` - **Deliver the Alert through a mobile application notification.**<br>- `sms` - **Deliver the Alert through an SMS message to a mobile device.**<br></details><br> | getType(): ?string | setType(?string type): void |
| `options` | `?string` | Optional | When the 'type' field of this resource is set to 'web', this field determines the format that the Alert data should be sent in. | getOptions(): ?string | setOptions(?string options): void |
| `value` | `?string` | Optional | A value used to deliver the alert. The field should be set to an email address if the type is email, an endpoint if the type is web, etc. | getValue(): ?string | setValue(?string value): void |
| `headerName` | `?string` | Optional | The request header name for authentication to the endpoint. | getHeaderName(): ?string | setHeaderName(?string headerName): void |
| `headerValue` | `?string` | Optional | The request header value for authentication to the endpoint. | getHeaderValue(): ?string | setHeaderValue(?string headerValue): void |
| `retries` | `?int` | Optional | The number of times an alert should be resent in case of a failure. This fields can only be set for web type alertActions. | getRetries(): ?int | setRetries(?int retries): void |
| `maxAttemptsTempDisabled` | [`?int(AlertActionsMaxAttemptsTempDisabledEnum)`](../../doc/models/alert-actions-max-attempts-temp-disabled-enum.md) | Optional | Whether it was temporarily disabled for reaching the maximum number of failed attempts.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Temporarily Disabled**<br>- `1` - **Temporarily Disabled**<br></details><br> | getMaxAttemptsTempDisabled(): ?int | setMaxAttemptsTempDisabled(?int maxAttemptsTempDisabled): void |
| `alert` | string\|[AlertsResponse](../../doc/models/alerts-response.md)\|null | Optional | The identifier of the Alert resource that defines this alertAction. | getAlert(): | setAlert( alert): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

