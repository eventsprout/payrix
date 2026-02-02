
# Logins Response

## Structure

`LoginsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login. | getLogin(): | setLogin( login): void |
| `lastLogin` | `?string` | Optional | The timestamp when this Login last logged in to the API. The format should be YYYY-MM-DD HH:MM:SS.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getLastLogin(): ?string | setLastLogin(?string lastLogin): void |
| `username` | `?string` | Optional | The username associated with this Login.<br>This field is stored as a text string, all lowercase, and must be between 0 and 50 characters long. | getUsername(): ?string | setUsername(?string username): void |
| `password` | `?string` | Optional | The password associated with this Login.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getPassword(): ?string | setPassword(?string password): void |
| `ssoId` | `?string` | Optional | The SSO (Single Sign On) ID setup for the login.<br>This field is stored as a text string and must be between 1 and 100 characters long. | getSsoId(): ?string | setSsoId(?string ssoId): void |
| `first` | `?string` | Optional | The first name associated with this Login. | getFirst(): ?string | setFirst(?string first): void |
| `middle` | `?string` | Optional | The middle name associated with this Login. | getMiddle(): ?string | setMiddle(?string middle): void |
| `last` | `?string` | Optional | The last name associated with this Login. | getLast(): ?string | setLast(?string last): void |
| `email` | `?string` | Optional | The email address associated with this Login. | getEmail(): ?string | setEmail(?string email): void |
| `fax` | `?string` | Optional | The fax number associated with this Login.<br>This field is stored as a text string and must be between 10 and 15 characters long. | getFax(): ?string | setFax(?string fax): void |
| `phone` | `?string` | Optional | The phone number associated with this Login.<br>This field is stored as a text string and must be between 10 and 15 characters long. | getPhone(): ?string | setPhone(?string phone): void |
| `country` | [`?string(CountryEnum)`](../../doc/models/country-enum.md) | Optional | The country associated with this Customer.<br>Valid values for this field is the 3-letter ISO code for the country. | getCountry(): ?string | setCountry(?string country): void |
| `zip` | `?string` | Optional | The ZIP code in the address associated with this Login.<br>This field is stored as a text string and must be between 1 and 20 characters long. | getZip(): ?string | setZip(?string zip): void |
| `state` | `?string` | Optional | The U.S. state or Canadian province relevant to the address provided here. If the location is within the U.S. and Canada, specify the 2-character postal abbreviation for the state. If the location is outside of the U.S. and Canada, provide the full state name. This field is stored as a text string and must be between 2 and 100 characters long.<br><br><details><br><summary>U.S. States</summary><br> <br> - `AK` - **Alaska (US)**<br> <br> - `AR` - **Arkansas (US)**<br> <br> - `AL` - **Alabama (US)**<br> <br> - `AZ` - **Arizona (US)**<br> <br> - `CA` - **California (US)**<br> <br> - `CO` - **Colorado (US)**<br> <br> - `CT` - **Connecticut (US)**<br> <br> - `DE` - **Delaware (US)**<br> <br> - `FL` - **Florida (US)**<br> <br> - `GA` - **Georgia (US)**<br> <br> - `HI` - **Hawaii (US)**<br> <br> - `IA` - **Iowa (US)**<br> <br> - `ID` - **Idaho (US)**<br> <br> - `IL` - **Illinois (US)**<br> <br> - `IN` - **Indiana (US)**<br> <br> - `KY` - **Kentucky (US)**<br> <br> - `KS` - **Kansas (US)**<br> <br> - `LA` - **Louisiana (US)**<br> <br> - `MA` - **Massachusetts (US)**<br> <br> - `MD` - **Maryland (US)**<br> <br> - `ME` - **Maine (US)**<br> <br> - `MI` - **Michigan (US)**<br> <br> - `MN` - **Minnesota (US)**<br> <br> - `MO` - **Missouri (US)**<br> <br> - `MS` - **Mississippi (US)**<br> <br> - `MT` - **Montana (US)**<br> <br> - `NC` - **North Carolina (US)**<br> <br> - `ND` - **North Dakota (US)**<br> <br> - `NE` - **Nebraska (US)**<br> <br> - `NH` - **New Hampshire (US)**<br> <br> - `NJ` - **New Jersey (US)**<br> <br> - `NM` - **New Mexico (US)**<br> <br> - `NV` - **Nevada (US)**<br> <br> - `NY` - **New York (US)**<br> <br> - `OH` - **Ohio (US)**<br> <br> - `OK`- **Oklahoma (US)**<br> <br> - `OR` - **Oregon (US)**<br> <br> - `PA` - **Pennsylvania (US)**<br> <br> - `RI` - **Rhode Island (US)**<br> <br> - `SC`- **South Carolina (US)**<br> <br> - `SD` - **South Dakota (US)**<br> <br> - `TN` - **Tennessee (US)**<br> <br> - `TX` - **Texas (US)**<br> <br> - `UT` - **Utah (US)**<br> <br> - `VA` - **Virginia (US)**<br> <br> - `VT` - **Vermont (US)**<br> <br> - `WA` - **Washington (US)**<br> <br> - `WI` - **Wisconsin (US)**<br> <br> - `WV` - **West Virginia (US)**<br> <br> - `WY` - **Wyoming (US)**<br> </details><br> <details><br><summary>Canada Provinces and Territories</summary><br> <br> - `AB` - **Alberta (CAN)**<br> <br> - `BC` - **British Columbia (CAN)**<br> <br> - `MB` - **Manitoba (CAN)**<br> <br> - `ON` - **Ontario (CAN)**<br> <br> - `NS` - **Nova Scotia (CAN)**<br> <br> - `NB` - **New Brunswick (CAN)**<br> <br> - `NL` - **Newfoundland and Labrador (CAN)**<br> <br> - `NT` - **Northwest Territories (CAN)**<br> <br> - `NU` - **Nunavut (CAN)**<br> <br> - `PE` - **Prince Edward Island (CAN)**<br> <br> - `QC` - **Quebec (CAN)**<br> <br> - `SK` - **Saskatchewan (CAN)**<br> <br> - `YT` - **Yukon (CAN)**<br> </details><br> | getState(): ?string | setState(?string state): void |
| `city` | `?string` | Optional | The name of the city in the address associated with this Login.<br>This field is stored as a text string and must be between 1 and 500 characters long. | getCity(): ?string | setCity(?string city): void |
| `address2` | `?string` | Optional | The second line of the address associated with this Login.<br>This field is stored as a text string and must be between 1 and 500 characters long. | getAddress2(): ?string | setAddress2(?string address2): void |
| `address1` | `?string` | Optional | The first line of the address associated with this Login.<br>This field is stored as a text string and must be between 1 and 500 characters long. | getAddress1(): ?string | setAddress1(?string address1): void |
| `confirmed` | [`?int(LoginsConfirmedEnum)`](../../doc/models/logins-confirmed-enum.md) | Optional | Whether the email associated with this Login was confirmed. This field is stored as an integer and will be set to '1' when the email is confirmed.<br><br><details> <summary>Valid Values</summary><br>- `0`  - **Not confirmed.**<br>- `1`  - **Confirmed.**<br>  <br>  </details><br> | getConfirmed(): ?int | setConfirmed(?int confirmed): void |
| `roles` | `?int` | Optional | The roles associated with this Login, specified as an integer. | getRoles(): ?int | setRoles(?int roles): void |
| `partition` | `?string` | Optional | The partition that this Login is associated with. | getPartition(): ?string | setPartition(?string partition): void |
| `division` | string\|[DivisionsResponse](../../doc/models/divisions-response.md)\|null | Optional | The division that this Login belongs to. | getDivision(): | setDivision( division): void |
| `parentDivision` | `?string` | Optional | The parent division that this Login belongs to. Children of this Login will inherit its parent division. | getParentDivision(): ?string | setParentDivision(?string parentDivision): void |
| `allowedResources` | `?string` | Optional | The allowedResources field specifies the actions and resources a user can access. The JSON structure includes action keys (create, update, read, delete, totals) and lists of resources (e.g., logins, apikeys, sessions). Omitted action keys indicate no access for those actions. | getAllowedResources(): ?string | setAllowedResources(?string allowedResources): void |
| `restrictedResources` | `?string` | Optional | The restrictedResources field defines the actions and resources a user is restricted from accessing. The JSON structure includes action keys (create, update, read, delete, totals) and lists of resources (e.g., logins, apikeys, sessions). Omitted action keys indicate no restrictions for those actions. | getRestrictedResources(): ?string | setRestrictedResources(?string restrictedResources): void |
| `portalAccess` | [`?int(LoginsPortalAccessEnum)`](../../doc/models/logins-portal-access-enum.md) | Optional | Whether or not this user should have access to portal functionality.<br><br><details><br><summary>Valid Values</summary> <br>- `0` - **No access to the portal**<br>- `1` - **Has access to the portal**<br>  <br>  </details><br> | getPortalAccess(): ?int | setPortalAccess(?int portalAccess): void |
| `mfaEnabled` | [`?int(LoginsMfaEnabledEnum)`](../../doc/models/logins-mfa-enabled-enum.md) | Optional | Whether or not this user should have multi factor authentication (MFA) feature.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Disabled**<br>- `1` - **Enabled**<br></details><br> | getMfaEnabled(): ?int | setMfaEnabled(?int mfaEnabled): void |
| `mfaSecret` | `?string` | Optional | The MFA secret key used to link the MFA device with this Login.<br>This field is stored as a text string and must be between 1 and 128 characters long. | getMfaSecret(): ?string | setMfaSecret(?string mfaSecret): void |
| `mfaEnrolledDate` | `?string` | Optional | The datetimestamp  when this Login was enabled for MFA. | getMfaEnrolledDate(): ?string | setMfaEnrolledDate(?string mfaEnrolledDate): void |
| `mfaType` | `?string` | Optional | The Type of the MFA enrolled.<br>This field is stored as a text string and must be between 1 and 50 characters long. | getMfaType(): ?string | setMfaType(?string mfaType): void |
| `effectiveRoles` | `?int` | Optional | EffectiveRoles is included in the response when a user record is returned via API indicating the full effective roles of the user (as an integer), broken down by role, for roles that include other roles automatically. | getEffectiveRoles(): ?int | setEffectiveRoles(?int effectiveRoles): void |
| `mfaSmsCodesCount` | `?int` | Optional | The end time of the current MFA SMS window which is a sliding window limitinig how many codes can be generated during a given window | getMfaSmsCodesCount(): ?int | setMfaSmsCodesCount(?int mfaSmsCodesCount): void |
| `mfaSmsWindow` | `?int` | Optional | The most recent SMS Code which has been texted to the user | getMfaSmsWindow(): ?int | setMfaSmsWindow(?int mfaSmsWindow): void |
| `loginAsEnabled` | `?int` | Optional | Whether the associated login can use loginAs or not | getLoginAsEnabled(): ?int | setLoginAsEnabled(?int loginAsEnabled): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `aggregations` | [`?(AggregationsResponse[])`](../../doc/models/aggregations-response.md) | Optional | - | getAggregations(): ?array | setAggregations(?array aggregations): void |
| `analyzedChangeRequests` | [`?(ChangeRequest[])`](../../doc/models/change-request.md) | Optional | - | getAnalyzedChangeRequests(): ?array | setAnalyzedChangeRequests(?array analyzedChangeRequests): void |
| `changeRequests` | [`?(ChangeRequest[])`](../../doc/models/change-request.md) | Optional | - | getChangeRequests(): ?array | setChangeRequests(?array changeRequests): void |
| `confirmCodes` | [`?(ConfirmCodesResponse[])`](../../doc/models/confirm-codes-response.md) | Optional | - | getConfirmCodes(): ?array | setConfirmCodes(?array confirmCodes): void |
| `customers` | [`?(CustomersResponse[])`](../../doc/models/customers-response.md) | Optional | - | getCustomers(): ?array | setCustomers(?array customers): void |
| `billings` | [`?(BillingsResponse[])`](../../doc/models/billings-response.md) | Optional | - | getBillings(): ?array | setBillings(?array billings): void |
| `divisions` | [`?(DivisionsResponse[])`](../../doc/models/divisions-response.md) | Optional | - | getDivisions(): ?array | setDivisions(?array divisions): void |
| `entities` | [`?(EntitiesResponse[])`](../../doc/models/entities-response.md) | Optional | - | getEntities(): ?array | setEntities(?array entities): void |
| `entityReturns` | [`?(EntityReturnsResponse[])`](../../doc/models/entity-returns-response.md) | Optional | - | getEntityReturns(): ?array | setEntityReturns(?array entityReturns): void |
| `invoices` | [`?(InvoicesResponse[])`](../../doc/models/invoices-response.md) | Optional | - | getInvoices(): ?array | setInvoices(?array invoices): void |
| `invoiceParameters` | [`?(InvoiceParametersResponse[])`](../../doc/models/invoice-parameters-response.md) | Optional | - | getInvoiceParameters(): ?array | setInvoiceParameters(?array invoiceParameters): void |
| `logins` | [`?(LoginsResponse[])`](../../doc/models/logins-response.md) | Optional | - | getLogins(): ?array | setLogins(?array logins): void |
| `loginsHelpers` | [`?(LoginHelpersResponse[])`](../../doc/models/login-helpers-response.md) | Optional | - | getLoginsHelpers(): ?array | setLoginsHelpers(?array loginsHelpers): void |
| `notes` | [`?(NotesResponse[])`](../../doc/models/notes-response.md) | Optional | - | getNotes(): ?array | setNotes(?array notes): void |
| `messageThreads` | [`?(MessageThreadsResponse[])`](../../doc/models/message-threads-response.md) | Optional | - | getMessageThreads(): ?array | setMessageThreads(?array messageThreads): void |
| `orgFlows` | [`?(OrgFlowsResponse[])`](../../doc/models/org-flows-response.md) | Optional | - | getOrgFlows(): ?array | setOrgFlows(?array orgFlows): void |
| `orgFlowsforlogin` | [`?(OrgFlowsResponse[])`](../../doc/models/org-flows-response.md) | Optional | - | getOrgFlowsforlogin(): ?array | setOrgFlowsforlogin(?array orgFlowsforlogin): void |
| `profitShares` | [`?(ProfitSharesResponse[])`](../../doc/models/profit-shares-response.md) | Optional | - | getProfitShares(): ?array | setProfitShares(?array profitShares): void |
| `secrets` | [`?(SecretsResponse[])`](../../doc/models/secrets-response.md) | Optional | - | getSecrets(): ?array | setSecrets(?array secrets): void |
| `teamLogins` | [`?(TeamLoginResponse[])`](../../doc/models/team-login-response.md) | Optional | - | getTeamLogins(): ?array | setTeamLogins(?array teamLogins): void |
| `teams` | [`?(TeamsResponse[])`](../../doc/models/teams-response.md) | Optional | - | getTeams(): ?array | setTeams(?array teams): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id6",
  "created": "created6",
  "modified": "modified6",
  "creator": "String5",
  "modifier": "modifier0"
}
```

