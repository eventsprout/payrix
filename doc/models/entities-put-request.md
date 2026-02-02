
# Entities Put Request

## Structure

`EntitiesPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientIp` | `?string` | Optional | The client IP address from which the Entity was created. Valid values are any IPv4 or IPv6 address. | getClientIp(): ?string | setClientIp(?string clientIp): void |
| `login` | `?string` | Optional | The Login that owns this resource. | getLogin(): ?string | setLogin(?string login): void |
| `type` | [`?int(EntityTypeEnum)`](../../doc/models/entity-type-enum.md) | Optional | The type of Entity.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Sole Proprietorship**<br>- `1` - **Corporation**<br>- `2` - **Limited Liability Company**<br>- `3` - **Partnership**<br>- `4` - **Association**<br>- `5` - **Non-Profit Organization**<br>- `6` - **Government Organization**<br>- `7` - **C Corporation**<br>- `8` - **S Corporation**<br></details><br> | getType(): ?int | setType(?int type): void |
| `name` | `?string` | Optional | The name of this Entity.<br>This field is stored as a string string and must be between 1 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `displayName` | `?string` | Optional | The display name of this Entity.<br>This field is stored as a string and must be between 1 and 1,000 characters long. | getDisplayName(): ?string | setDisplayName(?string displayName): void |
| `address1` | `?string` | Optional | The first line of the address associated with this Entity.<br>This field is stored as a string and must be between 1 and 500 characters long. | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | The second line of the address associated with this Entity.<br>This field is stored as a string and must be between 1 and 500 characters long. | getAddress2(): ?string | setAddress2(?string address2): void |
| `city` | `?string` | Optional | The name of the city in the address associated with this Entity.<br>This field is stored as a string and must be between 1 and 500 characters long. | getCity(): ?string | setCity(?string city): void |
| `state` | `?string` | Optional | The U.S. state or Canadian province relevant to the address provided here. If the location is within the U.S. and Canada, specify the 2-character postal abbreviation for the state. If the location is outside of the U.S. and Canada, provide the full state name. This field is stored as a text string and must be between 2 and 100 characters long.<br><br><details><br><summary>U.S. States</summary><br> <br> - `AK` - **Alaska (US)**<br> <br> - `AR` - **Arkansas (US)**<br> <br> - `AL` - **Alabama (US)**<br> <br> - `AZ` - **Arizona (US)**<br> <br> - `CA` - **California (US)**<br> <br> - `CO` - **Colorado (US)**<br> <br> - `CT` - **Connecticut (US)**<br> <br> - `DE` - **Delaware (US)**<br> <br> - `FL` - **Florida (US)**<br> <br> - `GA` - **Georgia (US)**<br> <br> - `HI` - **Hawaii (US)**<br> <br> - `IA` - **Iowa (US)**<br> <br> - `ID` - **Idaho (US)**<br> <br> - `IL` - **Illinois (US)**<br> <br> - `IN` - **Indiana (US)**<br> <br> - `KY` - **Kentucky (US)**<br> <br> - `KS` - **Kansas (US)**<br> <br> - `LA` - **Louisiana (US)**<br> <br> - `MA` - **Massachusetts (US)**<br> <br> - `MD` - **Maryland (US)**<br> <br> - `ME` - **Maine (US)**<br> <br> - `MI` - **Michigan (US)**<br> <br> - `MN` - **Minnesota (US)**<br> <br> - `MO` - **Missouri (US)**<br> <br> - `MS` - **Mississippi (US)**<br> <br> - `MT` - **Montana (US)**<br> <br> - `NC` - **North Carolina (US)**<br> <br> - `ND` - **North Dakota (US)**<br> <br> - `NE` - **Nebraska (US)**<br> <br> - `NH` - **New Hampshire (US)**<br> <br> - `NJ` - **New Jersey (US)**<br> <br> - `NM` - **New Mexico (US)**<br> <br> - `NV` - **Nevada (US)**<br> <br> - `NY` - **New York (US)**<br> <br> - `OH` - **Ohio (US)**<br> <br> - `OK`- **Oklahoma (US)**<br> <br> - `OR` - **Oregon (US)**<br> <br> - `PA` - **Pennsylvania (US)**<br> <br> - `RI` - **Rhode Island (US)**<br> <br> - `SC`- **South Carolina (US)**<br> <br> - `SD` - **South Dakota (US)**<br> <br> - `TN` - **Tennessee (US)**<br> <br> - `TX` - **Texas (US)**<br> <br> - `UT` - **Utah (US)**<br> <br> - `VA` - **Virginia (US)**<br> <br> - `VT` - **Vermont (US)**<br> <br> - `WA` - **Washington (US)**<br> <br> - `WI` - **Wisconsin (US)**<br> <br> - `WV` - **West Virginia (US)**<br> <br> - `WY` - **Wyoming (US)**<br> </details><br> <details><br><summary>Canada Provinces and Territories</summary><br> <br> - `AB` - **Alberta (CAN)**<br> <br> - `BC` - **British Columbia (CAN)**<br> <br> - `MB` - **Manitoba (CAN)**<br> <br> - `ON` - **Ontario (CAN)**<br> <br> - `NS` - **Nova Scotia (CAN)**<br> <br> - `NB` - **New Brunswick (CAN)**<br> <br> - `NL` - **Newfoundland and Labrador (CAN)**<br> <br> - `NT` - **Northwest Territories (CAN)**<br> <br> - `NU` - **Nunavut (CAN)**<br> <br> - `PE` - **Prince Edward Island (CAN)**<br> <br> - `QC` - **Quebec (CAN)**<br> <br> - `SK` - **Saskatchewan (CAN)**<br> <br> - `YT` - **Yukon (CAN)**<br> </details><br> | getState(): ?string | setState(?string state): void |
| `zip` | `?string` | Optional | The ZIP code in the address associated with this Entity.<br>This field is stored as a text string and must be between 1 and 20 characters long. | getZip(): ?string | setZip(?string zip): void |
| `country` | [`?string(EntityCountryEnum)`](../../doc/models/entity-country-enum.md) | Optional | The country in the address associated with the Entity, currently accepting values including `USA` and `CAN`. | getCountry(): ?string | setCountry(?string country): void |
| `timezone` | [`?string(EntitiesTimezoneEnum)`](../../doc/models/entities-timezone-enum.md) | Optional | The time zone for the address associated with the terminal's location.<br><br><details><br><summary>Valid Values</summary> <br>- `est` - **Eastern Standard Time**<br>- `pst` - **Pacific Standard Time**<br><br>- `cst` - **Central Standard Time**<br><br>- `mst` - **Mountain Daylight Time**<br><br>- `akst` - **Alaska Standard Time**<br><br>- `hst` - **Hawaii Standard Time**<br><br>- `sst` - **Samoa Standard Time**<br><br>- `chst` - **Chamorro Standard Time**<br><br>- `ast`  - **Atlantic Standard Time**<br><br>- `pwt` - **Palau Time**<br><br>- `mht` - **Marshall Islands Time**<br><br>- `chut` - **Chuuk Time**<br><br>- `nst` - **Newfoundland Standard Time**<br>  <br>  </details><br> | getTimezone(): ?string | setTimezone(?string timezone): void |
| `phone` | `?string` | Optional | The phone number associated with this Entity.<br>This field is stored as a text string and must be between 5 and 15 characters long. | getPhone(): ?string | setPhone(?string phone): void |
| `customerPhone` | `?string` | Optional | The customer service phone number associated with this Entity. For Merchants, this number will be displayed on the customer's credit card statement.<br>This field is stored as a text string and must be between 5 and 15 characters long. | getCustomerPhone(): ?string | setCustomerPhone(?string customerPhone): void |
| `fax` | `?string` | Optional | The fax number associated with this Entity.<br>This field is stored as a text string and must be between 5 and 15 characters long. | getFax(): ?string | setFax(?string fax): void |
| `email` | `?string` | Optional | The email address associated with this Entity.<br>This field is stored as a text string and must be between 1 and 100 characters long. | getEmail(): ?string | setEmail(?string email): void |
| `website` | `?string` | Optional | The web site URL associated with this Entity.<br>This field is stored as a text string and must be between 0 and 500 characters long. | getWebsite(): ?string | setWebsite(?string website): void |
| `appleDomain` | `?string` | Optional | The web sites URL associated with this Entity.<br>This field is stored as a text string; must be between 0 and 1,000 characters long and separated by comma. | getAppleDomain(): ?string | setAppleDomain(?string appleDomain): void |
| `einType` | [`?string(EntitiesEinTypeEnum)`](../../doc/models/entities-ein-type-enum.md) | Optional | Indicates if the TIN being used is an EIN, SSN, or other/unknown number.<br><br><details><br><summary>Valid Values</summary><br>- `ssn` - **Social Security Number.**<br>- `tin` - **Employer Identification Number.**<br>- `other` - **Other/Unknown TIN.**<br></details><br> | getEinType(): ?string | setEinType(?string einType): void |
| `irsFilingName` | `?string` | Optional | The IRS Legal Filing Name. This must match what has been provided to the IRS when filing taxes. | getIrsFilingName(): ?string | setIrsFilingName(?string irsFilingName): void |
| `ein` | `?string` | Optional | The IRS Employer Identification Number (EIN) for the Entity.<br>This field is stored as an integer and must be 9 characters long. | getEin(): ?string | setEin(?string ein): void |
| `locations` | `?int` | Optional | The number of locations at which this Entity does business.<br>This field is stored as an integer and must be between 1 and 1,000,000 characters long. | getLocations(): ?int | setLocations(?int locations): void |
| `public` | [`?int(EntitiesPublicEnum)`](../../doc/models/entities-public-enum.md) | Optional | Indicates whether this is a publicly held entity.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Private entity**<br>- `1` - **Public entity**<br></details><br>**Default**: `EntitiesPublicEnum::PRIVATEENTITY`<br> | getPublic(): ?int | setPublic(?int public): void |
| `tcVersion` | `?string` | Optional | An indicator showing the version of the terms and conditions that this Entity has accepted. The API indicates the version as a string.<br>This field is stored as a text string and must be between 0 and 20 characters long. | getTcVersion(): ?string | setTcVersion(?string tcVersion): void |
| `tcAcceptDate` | `?string` | Optional | Date and time on which this Entity accepted the Terms and Conditions, if different than `tcDate`.<br>The date is specified as a 12-digit string in YYYYMMDDHHII format, for example, `201601201528` for January 20, 2016, at 15:28 (3:28 PM). | getTcAcceptDate(): ?string | setTcAcceptDate(?string tcAcceptDate): void |
| `tcAcceptIp` | `?string` | Optional | IP address from which this Entity accepted the Terms and Conditions, if different than `tcIp`. | getTcAcceptIp(): ?string | setTcAcceptIp(?string tcAcceptIp): void |
| `custom` | `?string` | Optional | Custom, free-form field for client-supplied text; must be between 0 and 1,000 characters long. | getCustom(): ?string | setCustom(?string custom): void |
| `payoutSecondaryDescriptor` | `?string` | Optional | The secondary billing descriptor to appear on the bank statements for funds transfer for the entity. | getPayoutSecondaryDescriptor(): ?string | setPayoutSecondaryDescriptor(?string payoutSecondaryDescriptor): void |
| `industry` | `?string` | Optional | This field is stored as a text string and must be between 0 and 1,000 characters long. | getIndustry(): ?string | setIndustry(?string industry): void |
| `globalBusinessType` | [`?string(GlobalBusinessTypeEnum)`](../../doc/models/global-business-type-enum.md) | Optional | The business registration type for the entity<br><br><details><br><summary>Valid Values for country USA</summary><br>- `ssn` - **Social Security Number.**<br>- `tin` - **Employer Identification Number.**<br>- `other` - **Other/Unknown TIN.**<br></details><br><details><br><summary>Valid Values for country Canada</summary><br>- `CD` - **Federal**<br>- `AB` - **Alberta**<br>- `BC` - **British Columbia**<br>- `MB` - **Manitoba**<br>- `NB` - **New Brunswick**<br>- `NL` - **Newfoundland and Labrador**<br>- `NT` - **Northwest Territories**<br>- `NS` - **Nova Scotia**<br>- `NU` - **Nunavut**<br>- `ON` - **Ontario**<br>- `PE` - **Prince Edward Island**<br>- `QC` - **Quebec**<br>- `SK` - **Saskatchewan**<br>- `YT` - **Yukon**<br></details><br> | getGlobalBusinessType(): ?string | setGlobalBusinessType(?string globalBusinessType): void |
| `globalBusinessId` | `?string` | Optional | The business registration number for the entity.<br>This field is stored as an alphanumeric and must be between 9 to 10 characters long. | getGlobalBusinessId(): ?string | setGlobalBusinessId(?string globalBusinessId): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |

## Example (as JSON)

```json
{
  "clientIp": "152.58.83.44",
  "login": "t1_log_6733015a79f48410904564b",
  "type": 6,
  "name": "Splash LLC",
  "address1": "1234 Rivver Lane",
  "address2": "San house Fremont",
  "city": "Frisco",
  "state": "TX",
  "zip": "75034",
  "country": "USA",
  "timezone": "cst",
  "phone": "995685662566",
  "fax": "995685662566",
  "email": "rawatankit0911@gmail.com",
  "website": "http://payrix.com",
  "ein": "678912345",
  "tcVersion": "1.0",
  "tcDate": "2024-11-12 02:18:50",
  "tcIp": "134.238.16.164",
  "tcAcceptDate": "202204281403",
  "tcAcceptIp": "162.250.123.158",
  "custom": "voluptatibus et accusamus",
  "inactive": 0,
  "frozen": 0,
  "public": 1,
  "customerPhone": "995685662566",
  "locations": 1,
  "industry": "Residential Painting",
  "displayName": "John",
  "payoutSecondaryDescriptor": "Apex Leadership",
  "einType": "ssn",
  "irsFilingName": "Integration Test 2025-02-21T09:12:15.332",
  "currency": "USD",
  "globalBusinessId": "678912345",
  "globalBusinessType": "ssn"
}
```

