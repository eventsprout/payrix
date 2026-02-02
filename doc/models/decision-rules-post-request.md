
# Decision Rules Post Request

## Structure

`DecisionRulesPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `decision` | `string` | Required | The identifier of the Decision that this Decision Rule applies. | getDecision(): string | setDecision(string decision): void |
| `name` | `?string` | Optional | The name of this Decision Rule. This field is stored as a text string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | Description of the Decision Rules. | getDescription(): ?string | setDescription(?string description): void |
| `type` | [`string(DecisionRuleTypeEnum)`](../../doc/models/decision-rule-type-enum.md) | Required | The type of logic to apply with this Decision Rule.<br><br><details><br><summary>Valid Values</summary><br>- `less` - **Less.**<br>- `equal` - **Equal.**<br>- `notEqual` - **Not Equal.**<br>- `greater` - **Greater.**<br>- `swiped` - **Swiped.**<br>- `signed` - **Signed.**<br>- `type` - **Type.**<br>- `origin` - **Origin.**<br>- `method` - **Method.**<br>- `cvvResult` - **CVV Result.**<br>- `avsResult` - **AVS Result.**<br>- `3dsResult` - **3DS Result. The Decision applies based on the results of a 3DS check.**<br>- `related` - **Related.**<br>- `relatedDelay` - **Related Delay.**<br>- `relatedFloor` - **Related Floor.**<br>- `relatedCeil` - **Related Ceil.**<br>- `mcc` - **MCC.**<br>- `merchantCountry` - **Merchant Country.**<br>- `issuerCountry` - **Issuer Country.**<br>- `international` - **International.**<br>- `platform` - **Platform.**<br>- `methodType` - **Method Type.**<br>- `emv` - **EMV.**<br>- `misuse` - **Misuse.**<br>- `bin` - **BIN.**<br>- `primary` - **Primary.**<br>- `fundingCurrencyEqual` - **Funding Currency Equal.**<br>- `fundingCurrencyNotEqual` - **Funding Currency Not Equal.**<br>- `fundingCurrencyMismatch` - **Funding Currency Mismatch.**<br>- `settledCurrencyMismatch` - **Settled Currency Mismatch.**<br>- `imported` - **Imported.**<br>- `subscription` - **Subscription.**<br>- `publicAuth` - **Public Auth.**<br>- `clientIp` - **Client IP.**<br>- `debtRepayment` - **Debt Repayment.**<br>- `cofType` - **COF Type.**<br>- `entryMode` - **Entry Mode.**<br></details><br> | getType(): string | setType(string type): void |
| `value` | `int` | Required | The value to compare against when evaluating this Decision Rule. | getValue(): int | setValue(int value): void |
| `grouping` | `?string` | Optional | A name for a group of rules to be applied in conjunction when evaluating this Decision Rule; When grouping is used, the Decision will be allowed to be processed if at least one of the rules are matched. | getGrouping(): ?string | setGrouping(?string grouping): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "decision": "t1_dcs_67d97ed1a0fc6848c89d537",
  "name": "DecisionRule11",
  "description": "Rule Description",
  "type": "type",
  "value": 8,
  "grouping": "portalgroup_2",
  "inactive": 0,
  "frozen": 0
}
```

