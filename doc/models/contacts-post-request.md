
# Contacts Post Request

## Structure

`ContactsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entity` | `string` | Required | The identifier of the Entity that this Contact relates to. | getEntity(): string | setEntity(string entity): void |
| `first` | `string` | Required | The first name associated with this Contact. | getFirst(): string | setFirst(string first): void |
| `middle` | `?string` | Optional | The middle name associated with this Contact. | getMiddle(): ?string | setMiddle(?string middle): void |
| `last` | `string` | Required | The last name associated with this Contact. | getLast(): string | setLast(string last): void |
| `description` | `?string` | Optional | A description of this Contact. | getDescription(): ?string | setDescription(?string description): void |
| `email` | `string` | Required | The email address of this Contact. | getEmail(): string | setEmail(string email): void |
| `address1` | `?string` | Optional | The first line of the address associated with this Contact.<br>This field is stored as a text string and must be between 1 and 500 characters long. | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | The second line of the address associated with this Contact.<br>This field is stored as a text string and must be between 1 and 500 characters long. | getAddress2(): ?string | setAddress2(?string address2): void |
| `city` | `?string` | Optional | The name of the city in the address associated with this Contact.<br>This field is stored as a text string and must be between 1 and 500 characters long. | getCity(): ?string | setCity(?string city): void |
| `state` | `?string` | Optional | The U.S. state or Canadian province relevant to the address provided here. If the location is within the U.S. and Canada, specify the 2-character postal abbreviation for the state. If the location is outside of the U.S. and Canada, provide the full state name. This field is stored as a text string and must be between 2 and 100 characters long.<br><br><details><br><summary>U.S. States</summary><br> <br> - `AK` - **Alaska (US)**<br> <br> - `AR` - **Arkansas (US)**<br> <br> - `AL` - **Alabama (US)**<br> <br> - `AZ` - **Arizona (US)**<br> <br> - `CA` - **California (US)**<br> <br> - `CO` - **Colorado (US)**<br> <br> - `CT` - **Connecticut (US)**<br> <br> - `DE` - **Delaware (US)**<br> <br> - `FL` - **Florida (US)**<br> <br> - `GA` - **Georgia (US)**<br> <br> - `HI` - **Hawaii (US)**<br> <br> - `IA` - **Iowa (US)**<br> <br> - `ID` - **Idaho (US)**<br> <br> - `IL` - **Illinois (US)**<br> <br> - `IN` - **Indiana (US)**<br> <br> - `KY` - **Kentucky (US)**<br> <br> - `KS` - **Kansas (US)**<br> <br> - `LA` - **Louisiana (US)**<br> <br> - `MA` - **Massachusetts (US)**<br> <br> - `MD` - **Maryland (US)**<br> <br> - `ME` - **Maine (US)**<br> <br> - `MI` - **Michigan (US)**<br> <br> - `MN` - **Minnesota (US)**<br> <br> - `MO` - **Missouri (US)**<br> <br> - `MS` - **Mississippi (US)**<br> <br> - `MT` - **Montana (US)**<br> <br> - `NC` - **North Carolina (US)**<br> <br> - `ND` - **North Dakota (US)**<br> <br> - `NE` - **Nebraska (US)**<br> <br> - `NH` - **New Hampshire (US)**<br> <br> - `NJ` - **New Jersey (US)**<br> <br> - `NM` - **New Mexico (US)**<br> <br> - `NV` - **Nevada (US)**<br> <br> - `NY` - **New York (US)**<br> <br> - `OH` - **Ohio (US)**<br> <br> - `OK`- **Oklahoma (US)**<br> <br> - `OR` - **Oregon (US)**<br> <br> - `PA` - **Pennsylvania (US)**<br> <br> - `RI` - **Rhode Island (US)**<br> <br> - `SC`- **South Carolina (US)**<br> <br> - `SD` - **South Dakota (US)**<br> <br> - `TN` - **Tennessee (US)**<br> <br> - `TX` - **Texas (US)**<br> <br> - `UT` - **Utah (US)**<br> <br> - `VA` - **Virginia (US)**<br> <br> - `VT` - **Vermont (US)**<br> <br> - `WA` - **Washington (US)**<br> <br> - `WI` - **Wisconsin (US)**<br> <br> - `WV` - **West Virginia (US)**<br> <br> - `WY` - **Wyoming (US)**<br> </details><br> <details><br><summary>Canada Provinces and Territories</summary><br> <br> - `AB` - **Alberta (CAN)**<br> <br> - `BC` - **British Columbia (CAN)**<br> <br> - `MB` - **Manitoba (CAN)**<br> <br> - `ON` - **Ontario (CAN)**<br> <br> - `NS` - **Nova Scotia (CAN)**<br> <br> - `NB` - **New Brunswick (CAN)**<br> <br> - `NL` - **Newfoundland and Labrador (CAN)**<br> <br> - `NT` - **Northwest Territories (CAN)**<br> <br> - `NU` - **Nunavut (CAN)**<br> <br> - `PE` - **Prince Edward Island (CAN)**<br> <br> - `QC` - **Quebec (CAN)**<br> <br> - `SK` - **Saskatchewan (CAN)**<br> <br> - `YT` - **Yukon (CAN)**<br> </details><br> | getState(): ?string | setState(?string state): void |
| `zip` | `?string` | Optional | The ZIP code in the address associated with this Contact.<br>This field is stored as a text string and must be between 1 and 20 characters long. | getZip(): ?string | setZip(?string zip): void |
| `country` | [`?string(CountryEnum)`](../../doc/models/country-enum.md) | Optional | The country associated with this Contact.<br>Valid values for this field is the 3-letter ISO code for the country. | getCountry(): ?string | setCountry(?string country): void |
| `phone` | `?string` | Optional | The phone number associated with this Contact.<br>This field is stored as a text string and must be between 10 and 15 characters long. | getPhone(): ?string | setPhone(?string phone): void |
| `fax` | `?string` | Optional | The fax number associated with this Contact.<br>This field is stored as a text string and must be between 10 and 15 characters long. | getFax(): ?string | setFax(?string fax): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |

## Example (as JSON)

```json
{
  "entity": "t1_ent_665e13ff8b2e613134b9273",
  "first": "first name",
  "last": "last name",
  "email": "fewafehwuohfewafewafewa@payrjfhuiweafewa.com",
  "middle": "middle name",
  "description": "description of Contact",
  "address1": "first line of the address",
  "address2": "second line of the address",
  "city": "Anchorage",
  "state": "AK",
  "zip": "99501",
  "country": "USA",
  "phone": "1234567890",
  "fax": "1234567890",
  "inactive": 0,
  "frozen": 0
}
```

