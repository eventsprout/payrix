
# Login Helpers Response

## Structure

`LoginHelpersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The Login that owns this resource. | getLogin(): | setLogin( login): void |
| `mfaSmsCode` | `?string` | Optional | The most recent SMS Code which has been texted to the user. | getMfaSmsCode(): ?string | setMfaSmsCode(?string mfaSmsCode): void |
| `mfaSmsCodeUnixTime` | `?int` | Optional | The expiry date of the most recent SMS Code. | getMfaSmsCodeUnixTime(): ?int | setMfaSmsCodeUnixTime(?int mfaSmsCodeUnixTime): void |
| `mfaSmsCodeAttempts` | `?int` | Optional | The number of times the most recent code has been attempted. | getMfaSmsCodeAttempts(): ?int | setMfaSmsCodeAttempts(?int mfaSmsCodeAttempts): void |
| `mfaSmsCodesCount` | `?int` | Optional | The number of codes which has been created in the current window.<br>If this goes above the max, you must wait until a new window to create more. | getMfaSmsCodesCount(): ?int | setMfaSmsCodesCount(?int mfaSmsCodesCount): void |
| `mfaSmsWindow` | `?int` | Optional | The end time of the current MFA SMS window which is a sliding window limiting how many codes can be generated during a given window. | getMfaSmsWindow(): ?int | setMfaSmsWindow(?int mfaSmsWindow): void |
| `loginAsEnabled` | [`?int(LoginHelpersLoginAsEnabledEnum)`](../../doc/models/login-helpers-login-as-enabled-enum.md) | Optional | Whether the associated login can use loginAs or not.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **OFF**<br>- `1` - **ON**<br></details><br> | getLoginAsEnabled(): ?int | setLoginAsEnabled(?int loginAsEnabled): void |

## Example (as JSON)

```json
{
  "id": "id2",
  "created": "created2",
  "modified": "modified0",
  "creator": "String1",
  "modifier": "modifier6"
}
```

