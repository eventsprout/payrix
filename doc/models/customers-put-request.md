
# Customers Put Request

## Structure

`CustomersPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `?string` | Optional | The ID of the Login that owns this resource. | getLogin(): ?string | setLogin(?string login): void |
| `merchant` | `?string` | Optional | The ID of the Merchant associated with this Customer. | getMerchant(): ?string | setMerchant(?string merchant): void |
| `entity` | `?string` | Optional | The ID of the Entity that owns this resource. | getEntity(): ?string | setEntity(?string entity): void |
| `first` | `?string` | Optional | The first name associated with this Customer. | getFirst(): ?string | setFirst(?string first): void |
| `middle` | `?string` | Optional | The middle name associated with this Customer. | getMiddle(): ?string | setMiddle(?string middle): void |
| `last` | `?string` | Optional | The last name associated with this Customer. | getLast(): ?string | setLast(?string last): void |
| `company` | `?string` | Optional | The name of the company associated with this Customer. | getCompany(): ?string | setCompany(?string company): void |
| `email` | `?string` | Optional | The email address of this Customer. | getEmail(): ?string | setEmail(?string email): void |
| `shippingFirst` | `?string` | Optional | The first name associated with this Customer's shipping information. | getShippingFirst(): ?string | setShippingFirst(?string shippingFirst): void |
| `shippingMiddle` | `?string` | Optional | The middle name associated with this Customer's shipping information. | getShippingMiddle(): ?string | setShippingMiddle(?string shippingMiddle): void |
| `shippingLast` | `?string` | Optional | The last name associated with this Customer's shipping information. | getShippingLast(): ?string | setShippingLast(?string shippingLast): void |
| `shippingCompany` | `?string` | Optional | The name of the company associated with this Customer's shipping information. | getShippingCompany(): ?string | setShippingCompany(?string shippingCompany): void |
| `shippingAddress1` | `?string` | Optional | The first line of the address associated with this Customer's shipping information.<br>This field is stored as a text string and must be between 1 and 500 characters long. | getShippingAddress1(): ?string | setShippingAddress1(?string shippingAddress1): void |
| `shippingAddress2` | `?string` | Optional | The second line of the address associated with this Customer's shipping information.<br>This field is stored as a text string and must be between 1 and 500 characters long. | getShippingAddress2(): ?string | setShippingAddress2(?string shippingAddress2): void |
| `shippingCity` | `?string` | Optional | The name of the city associated with this Customer's shipping information.<br>This field is stored as a text string and must be between 1 and 500 characters long. | getShippingCity(): ?string | setShippingCity(?string shippingCity): void |
| `shippingState` | `?string` | Optional | The U.S. state or Canadian province relevant to the address provided here. If the location is within the U.S. and Canada, specify the 2-character postal abbreviation for the state. If the location is outside of the U.S. and Canada, provide the full state name. This field is stored as a text string and must be between 2 and 100 characters long.<br><br><details><br><summary>U.S. States</summary><br> <br> - `AK` - **Alaska (US)**<br> <br> - `AR` - **Arkansas (US)**<br> <br> - `AL` - **Alabama (US)**<br> <br> - `AZ` - **Arizona (US)**<br> <br> - `CA` - **California (US)**<br> <br> - `CO` - **Colorado (US)**<br> <br> - `CT` - **Connecticut (US)**<br> <br> - `DE` - **Delaware (US)**<br> <br> - `FL` - **Florida (US)**<br> <br> - `GA` - **Georgia (US)**<br> <br> - `HI` - **Hawaii (US)**<br> <br> - `IA` - **Iowa (US)**<br> <br> - `ID` - **Idaho (US)**<br> <br> - `IL` - **Illinois (US)**<br> <br> - `IN` - **Indiana (US)**<br> <br> - `KY` - **Kentucky (US)**<br> <br> - `KS` - **Kansas (US)**<br> <br> - `LA` - **Louisiana (US)**<br> <br> - `MA` - **Massachusetts (US)**<br> <br> - `MD` - **Maryland (US)**<br> <br> - `ME` - **Maine (US)**<br> <br> - `MI` - **Michigan (US)**<br> <br> - `MN` - **Minnesota (US)**<br> <br> - `MO` - **Missouri (US)**<br> <br> - `MS` - **Mississippi (US)**<br> <br> - `MT` - **Montana (US)**<br> <br> - `NC` - **North Carolina (US)**<br> <br> - `ND` - **North Dakota (US)**<br> <br> - `NE` - **Nebraska (US)**<br> <br> - `NH` - **New Hampshire (US)**<br> <br> - `NJ` - **New Jersey (US)**<br> <br> - `NM` - **New Mexico (US)**<br> <br> - `NV` - **Nevada (US)**<br> <br> - `NY` - **New York (US)**<br> <br> - `OH` - **Ohio (US)**<br> <br> - `OK`- **Oklahoma (US)**<br> <br> - `OR` - **Oregon (US)**<br> <br> - `PA` - **Pennsylvania (US)**<br> <br> - `RI` - **Rhode Island (US)**<br> <br> - `SC`- **South Carolina (US)**<br> <br> - `SD` - **South Dakota (US)**<br> <br> - `TN` - **Tennessee (US)**<br> <br> - `TX` - **Texas (US)**<br> <br> - `UT` - **Utah (US)**<br> <br> - `VA` - **Virginia (US)**<br> <br> - `VT` - **Vermont (US)**<br> <br> - `WA` - **Washington (US)**<br> <br> - `WI` - **Wisconsin (US)**<br> <br> - `WV` - **West Virginia (US)**<br> <br> - `WY` - **Wyoming (US)**<br> </details><br> <details><br><summary>Canada Provinces and Territories</summary><br> <br> - `AB` - **Alberta (CAN)**<br> <br> - `BC` - **British Columbia (CAN)**<br> <br> - `MB` - **Manitoba (CAN)**<br> <br> - `ON` - **Ontario (CAN)**<br> <br> - `NS` - **Nova Scotia (CAN)**<br> <br> - `NB` - **New Brunswick (CAN)**<br> <br> - `NL` - **Newfoundland and Labrador (CAN)**<br> <br> - `NT` - **Northwest Territories (CAN)**<br> <br> - `NU` - **Nunavut (CAN)**<br> <br> - `PE` - **Prince Edward Island (CAN)**<br> <br> - `QC` - **Quebec (CAN)**<br> <br> - `SK` - **Saskatchewan (CAN)**<br> <br> - `YT` - **Yukon (CAN)**<br> </details><br> | getShippingState(): ?string | setShippingState(?string shippingState): void |
| `shippingZip` | `?string` | Optional | The ZIP code associated with this Customer's shipping information.<br>This field is stored as a text string and must be between 1 and 20 characters long. | getShippingZip(): ?string | setShippingZip(?string shippingZip): void |
| `shippingCountry` | [`?string(CountryEnum)`](../../doc/models/country-enum.md) | Optional | The country associated with this Customer's shipping information.<br>Valid values for this field is the 3-letter ISO code for the country. | getShippingCountry(): ?string | setShippingCountry(?string shippingCountry): void |
| `shippingPhone` | `?string` | Optional | The phone number associated with this Customer's shipping information.<br>This field is stored as a text string and must be between 10 and 15 characters long. | getShippingPhone(): ?string | setShippingPhone(?string shippingPhone): void |
| `shippingFax` | `?string` | Optional | The fax number associated with this Customer's shipping information.<br>This field is stored as a text string and must be between 10 and 15 characters long. | getShippingFax(): ?string | setShippingFax(?string shippingFax): void |
| `custom` | `?string` | Optional | Custom, free-form field for client-supplied text. Must be between 0 and 1,000 characters long. | getCustom(): ?string | setCustom(?string custom): void |
| `address1` | `?string` | Optional | The first line of the address associated with this Customer.<br>This field is stored as a text string and must be between 1 and 500 characters long. | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | The second line of the address associated with this Customer.<br>This field is stored as a text string and must be between 1 and 500 characters long. | getAddress2(): ?string | setAddress2(?string address2): void |
| `city` | `?string` | Optional | The name of the city in the address associated with this Customer.<br>This field is stored as a text string and must be between 1 and 500 characters long. | getCity(): ?string | setCity(?string city): void |
| `state` | `?string` | Optional | The U.S. state or Canadian province relevant to the address provided here. If the location is within the U.S. and Canada, specify the 2-character postal abbreviation for the state. If the location is outside of the U.S. and Canada, provide the full state name. This field is stored as a text string and must be between 2 and 100 characters long.<br><br><details><br><summary>U.S. States</summary><br> <br> - `AK` - **Alaska (US)**<br> <br> - `AR` - **Arkansas (US)**<br> <br> - `AL` - **Alabama (US)**<br> <br> - `AZ` - **Arizona (US)**<br> <br> - `CA` - **California (US)**<br> <br> - `CO` - **Colorado (US)**<br> <br> - `CT` - **Connecticut (US)**<br> <br> - `DE` - **Delaware (US)**<br> <br> - `FL` - **Florida (US)**<br> <br> - `GA` - **Georgia (US)**<br> <br> - `HI` - **Hawaii (US)**<br> <br> - `IA` - **Iowa (US)**<br> <br> - `ID` - **Idaho (US)**<br> <br> - `IL` - **Illinois (US)**<br> <br> - `IN` - **Indiana (US)**<br> <br> - `KY` - **Kentucky (US)**<br> <br> - `KS` - **Kansas (US)**<br> <br> - `LA` - **Louisiana (US)**<br> <br> - `MA` - **Massachusetts (US)**<br> <br> - `MD` - **Maryland (US)**<br> <br> - `ME` - **Maine (US)**<br> <br> - `MI` - **Michigan (US)**<br> <br> - `MN` - **Minnesota (US)**<br> <br> - `MO` - **Missouri (US)**<br> <br> - `MS` - **Mississippi (US)**<br> <br> - `MT` - **Montana (US)**<br> <br> - `NC` - **North Carolina (US)**<br> <br> - `ND` - **North Dakota (US)**<br> <br> - `NE` - **Nebraska (US)**<br> <br> - `NH` - **New Hampshire (US)**<br> <br> - `NJ` - **New Jersey (US)**<br> <br> - `NM` - **New Mexico (US)**<br> <br> - `NV` - **Nevada (US)**<br> <br> - `NY` - **New York (US)**<br> <br> - `OH` - **Ohio (US)**<br> <br> - `OK`- **Oklahoma (US)**<br> <br> - `OR` - **Oregon (US)**<br> <br> - `PA` - **Pennsylvania (US)**<br> <br> - `RI` - **Rhode Island (US)**<br> <br> - `SC`- **South Carolina (US)**<br> <br> - `SD` - **South Dakota (US)**<br> <br> - `TN` - **Tennessee (US)**<br> <br> - `TX` - **Texas (US)**<br> <br> - `UT` - **Utah (US)**<br> <br> - `VA` - **Virginia (US)**<br> <br> - `VT` - **Vermont (US)**<br> <br> - `WA` - **Washington (US)**<br> <br> - `WI` - **Wisconsin (US)**<br> <br> - `WV` - **West Virginia (US)**<br> <br> - `WY` - **Wyoming (US)**<br> </details><br> <details><br><summary>Canada Provinces and Territories</summary><br> <br> - `AB` - **Alberta (CAN)**<br> <br> - `BC` - **British Columbia (CAN)**<br> <br> - `MB` - **Manitoba (CAN)**<br> <br> - `ON` - **Ontario (CAN)**<br> <br> - `NS` - **Nova Scotia (CAN)**<br> <br> - `NB` - **New Brunswick (CAN)**<br> <br> - `NL` - **Newfoundland and Labrador (CAN)**<br> <br> - `NT` - **Northwest Territories (CAN)**<br> <br> - `NU` - **Nunavut (CAN)**<br> <br> - `PE` - **Prince Edward Island (CAN)**<br> <br> - `QC` - **Quebec (CAN)**<br> <br> - `SK` - **Saskatchewan (CAN)**<br> <br> - `YT` - **Yukon (CAN)**<br> </details><br> | getState(): ?string | setState(?string state): void |
| `zip` | `?string` | Optional | The ZIP code in the address associated with this Customer.<br>This field is stored as a text string and must be between 1 and 20 characters long. | getZip(): ?string | setZip(?string zip): void |
| `country` | [`?string(CountryEnum)`](../../doc/models/country-enum.md) | Optional | The country associated with this Customer.<br>Valid values for this field is the 3-letter ISO code for the country. | getCountry(): ?string | setCountry(?string country): void |
| `phone` | `?string` | Optional | The phone number associated with this Transaction.<br>This field is stored as a text string and must be between 10 and 15 characters long. | getPhone(): ?string | setPhone(?string phone): void |
| `fax` | `?string` | Optional | The fax number associated with this Customer.<br>This field is stored as a text string and must be between 10 and 15 characters long. | getFax(): ?string | setFax(?string fax): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |

## Example (as JSON)

```json
{
  "login": "t1_log_0089616d2294ec86ba6076c",
  "merchant": "t1_mer_00415e924c58c616f8a119b",
  "first": "John",
  "middle": "M",
  "last": "Doe",
  "company": "Doe Enterprises",
  "email": "somename@emaol.com",
  "fax": "+11234567845",
  "phone": "+11324567845",
  "country": "USA",
  "zip": "75001",
  "state": "TX",
  "city": "Shelbyville",
  "address2": "Apt 4B",
  "address1": "456 Secondary Ave",
  "inactive": 0,
  "frozen": 0,
  "shippingFirst": "John",
  "shippingMiddle": "M",
  "shippingLast": "Doe",
  "shippingCompany": "Doe Shipping Co.",
  "shippingAddress1": "123 Main st.",
  "shippingAddress2": "Apt 4B",
  "shippingCity": "Shelbyville",
  "shippingState": "TX",
  "shippingZip": "75001",
  "shippingCountry": "USA",
  "shippingPhone": "+11234567845",
  "shippingFax": "+11234567845",
  "custom": "Customer's custom data",
  "entity": "t1_ent_64415e922e9000ef8bf3c1d"
}
```

