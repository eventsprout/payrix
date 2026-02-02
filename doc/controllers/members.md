# Members

A member represents a control or beneficiary member of the entity. At least one primary member record is required for merchant boarding.

```php
$membersController = $client->getMembersController();
```

## Class Name

`MembersController`

## Methods

* [Get Members Id](../../doc/controllers/members.md#get-members-id)
* [Put Members Id](../../doc/controllers/members.md#put-members-id)
* [Delete Members Id](../../doc/controllers/members.md#delete-members-id)
* [Get Members](../../doc/controllers/members.md#get-members)
* [Post Members](../../doc/controllers/members.md#post-members)


# Get Members Id

Query a Member. A Member is a person who is associated with a Merchant; One Member associated with each Merchant can be the 'primary' Member, meaning the Member with the most share of ownership in the Merchant.

```php
function getMembersId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): MembersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this member. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`MembersResponseResult`](../../doc/models/members-response-result.md)

## Example Usage

```php
$id = 't1_mbr_67d0336c01048ea41c4382z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $membersController->getMembersId(
    $id,
    $token,
    $requestToken
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_mbr_67d0336c01048ea41c4382z",
        "created": "2025-03-11 08:58:20.0258",
        "modified": "2025-03-11 08:58:20.0258",
        "creator": "g1577139c2304b7",
        "modifier": "g1577139c2304b7",
        "merchant": "t1_mer_67d033698c234e74c399ddd",
        "title": "CEO",
        "first": "Chad",
        "middle": "",
        "last": "Foster",
        "ssn": "1924",
        "dob": 20160120,
        "dl": "6679",
        "dlstate": "MD",
        "ownership": 10000,
        "email": "Jerrod_Glover@hotmail.com",
        "fax": "",
        "phone": "5106406000",
        "country": "MAR",
        "zip": "60064",
        "state": "MD",
        "city": "East Bettye",
        "address2": "",
        "address1": "83 Dan Ways",
        "primary": 1,
        "inactive": 0,
        "frozen": 0,
        "timezone": "est",
        "gender": "male",
        "creditScore": 334,
        "creditScoreDate": "2025-03-11 08:58:20",
        "significantResponsibility": 0,
        "politicallyExposed": 0,
        "citizenship": "MAR",
        "mailingAddress1": "",
        "mailingAddress2": "",
        "mailingCity": "",
        "mailingState": "MD",
        "mailingPostalCode": "",
        "mailingCountry": "MAR",
        "treasuryPrimeRoles": "",
        "facilitator": "",
        "vendor": "",
        "shareableUrl": "",
        "status": "",
        "createdAt": 1123,
        "completedAt": 1123,
        "plaidIdvId": "",
        "templateId": ""
      }
    ],
    "details": {
      "requestId": 1,
      "totals": [],
      "page": {
        "current": 1,
        "last": 1,
        "hasMore": false
      }
    },
    "errors": []
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Error | [`ErrorFourHundredException`](../../doc/models/error-four-hundred-exception.md) |


# Put Members Id

Update a Member, A Member is a person who is associated with a Merchant, One Member associated with each Merchant can be the 'primary' Member, meaning the Member with the most share of ownership in the Merchant.

```php
function putMembersId(
    string $id,
    MembersPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): MembersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this member. |
| `body` | [`MembersPutRequest`](../../doc/models/members-put-request.md) | Body, Required | Update Member Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`MembersResponseResult`](../../doc/models/members-response-result.md)

## Example Usage

```php
$id = 't1_mbr_67d0336c01048ea41c4382z';

$body = MembersPutRequestBuilder::init()
    ->merchant('t1_mer_67d033698c234e74c399ddd')
    ->title('CEO')
    ->first('Chad')
    ->middle('middle name')
    ->last('Foster')
    ->ssn('1924')
    ->citizenship(CountryEnum::MAR)
    ->dob(20160120)
    ->gender(MembersGenderEnum::MALE)
    ->dl('6679')
    ->dlstate('MD')
    ->email('Jerrod_Glover@hotmail.com')
    ->ownership(10000)
    ->primary(MembersPrimaryEnum::PRIMARYCONTACT)
    ->creditScore(334)
    ->creditScoreDate('2025-03-11 08:58:20')
    ->significantResponsibility(MembersSignificantResponsibilityEnum::NOSIGNIFICANTRESPONSIBILITY)
    ->politicallyExposed(MembersPoliticallyExposedEnum::NOTPOLITICALLYEXPOSED)
    ->mailingAddress1('mailing first line of address')
    ->mailingAddress2('mailing second line of address')
    ->mailingCity('mailing name of the city')
    ->mailingState('MD')
    ->mailingCountry(CountryEnum::MAR)
    ->mailingPostalCode('mailing postal code')
    ->timezone(MembersTimezoneEnum::EST)
    ->address1('first line of address')
    ->address2('second line of address')
    ->city('name of city')
    ->state('MD')
    ->zip('ZIP code')
    ->country(CountryEnum::MAR)
    ->phone('5106406000')
    ->fax('5106406000')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $membersController->putMembersId(
    $id,
    $body,
    $token,
    $requestToken
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_mbr_67d0336c01048ea41c4382z",
        "created": "2025-03-11 08:58:20.0258",
        "modified": "2025-03-11 08:58:20.0258",
        "creator": "g1577139c2304b7",
        "modifier": "g1577139c2304b7",
        "merchant": "t1_mer_67d033698c234e74c399ddd",
        "title": "CEO",
        "first": "Chad",
        "middle": "",
        "last": "Foster",
        "ssn": "1924",
        "dob": 20160120,
        "dl": "6679",
        "dlstate": "MD",
        "ownership": 10000,
        "email": "Jerrod_Glover@hotmail.com",
        "fax": "",
        "phone": "5106406000",
        "country": "MAR",
        "zip": "60064",
        "state": "MD",
        "city": "East Bettye",
        "address2": "",
        "address1": "83 Dan Ways",
        "primary": 1,
        "inactive": 0,
        "frozen": 0,
        "timezone": "est",
        "gender": "male",
        "creditScore": 334,
        "creditScoreDate": "2025-03-11 08:58:20",
        "significantResponsibility": 0,
        "politicallyExposed": 0,
        "citizenship": "MAR",
        "mailingAddress1": "",
        "mailingAddress2": "",
        "mailingCity": "",
        "mailingState": "MD",
        "mailingPostalCode": "",
        "mailingCountry": "MAR",
        "treasuryPrimeRoles": "",
        "facilitator": "",
        "vendor": "",
        "shareableUrl": "",
        "status": "",
        "createdAt": 1123,
        "completedAt": 1123,
        "plaidIdvId": "",
        "templateId": ""
      }
    ],
    "details": {
      "requestId": 1,
      "totals": [],
      "page": {
        "current": 1,
        "last": 1,
        "hasMore": false
      }
    },
    "errors": []
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Error | [`ErrorFourHundredException`](../../doc/models/error-four-hundred-exception.md) |


# Delete Members Id

Delete a Member. A Member is a person who is associated with a Merchant. One Member associated with each Merchant can be the 'primary' Member, meaning the Member with the most share of ownership in the Merchant.

```php
function deleteMembersId(string $id, ?string $token = null, ?string $requestToken = null): MembersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this member. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`MembersResponseResult`](../../doc/models/members-response-result.md)

## Example Usage

```php
$id = 't1_mbr_67d0336c01048ea41c4382z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $membersController->deleteMembersId(
    $id,
    $token,
    $requestToken
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_mbr_67d0336c01048ea41c4382z",
        "created": "2025-03-11 08:58:20.0258",
        "modified": "2025-03-11 08:58:20.0258",
        "creator": "g1577139c2304b7",
        "modifier": "g1577139c2304b7",
        "merchant": "t1_mer_67d033698c234e74c399ddd",
        "title": "CEO",
        "first": "Chad",
        "middle": "",
        "last": "Foster",
        "ssn": "1924",
        "dob": 20160120,
        "dl": "6679",
        "dlstate": "MD",
        "ownership": 10000,
        "email": "Jerrod_Glover@hotmail.com",
        "fax": "",
        "phone": "5106406000",
        "country": "MAR",
        "zip": "60064",
        "state": "MD",
        "city": "East Bettye",
        "address2": "",
        "address1": "83 Dan Ways",
        "primary": 1,
        "inactive": 0,
        "frozen": 0,
        "timezone": "est",
        "gender": "male",
        "creditScore": 334,
        "creditScoreDate": "2025-03-11 08:58:20",
        "significantResponsibility": 0,
        "politicallyExposed": 0,
        "citizenship": "MAR",
        "mailingAddress1": "",
        "mailingAddress2": "",
        "mailingCity": "",
        "mailingState": "MD",
        "mailingPostalCode": "",
        "mailingCountry": "MAR",
        "treasuryPrimeRoles": "",
        "facilitator": "",
        "vendor": "",
        "shareableUrl": "",
        "status": "",
        "createdAt": 1123,
        "completedAt": 1123,
        "plaidIdvId": "",
        "templateId": ""
      }
    ],
    "details": {
      "requestId": 1,
      "totals": [],
      "page": {
        "current": 1,
        "last": 1,
        "hasMore": false
      }
    },
    "errors": []
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Error | [`ErrorFourHundredException`](../../doc/models/error-four-hundred-exception.md) |


# Get Members

Query a Member, A Member being a person who is associated with a Merchant, and one Member associated with each Merchant can be the 'primary' Member, meaning the Member with the most share of ownership in the Merchant.

```php
function getMembers(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): MembersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `search` | `?string` | Header, Optional | Set this header to filter or sort the list of resources that the method returns.<br>See [Searches](page:welcome#searches) for detailed information and examples on how to use search header. |
| `totals` | `?string` | Header, Optional | To configure a request to return a total for all instances of a field in a result set,  use the totals header in the format `totals={operator}[]={key}`.  This will calculate the desired total and return it in the `details > totals` object of the response.  For instance, if you want to sum the `total` field of all transactions,  you would use the `sum` operator. The response will include the result set,  along with the calculated total in the `details` section. See [Collection Operators](page:welcome#collection-operators) for detailed information and examples on how to use totals header. |
| `pageNumber` | `?int` | Query, Optional | Set this path parameter to request a specific page of records.<br>For example, set `?page[number]=2` to retrieve the second page of records for this request. |
| `pageLimit` | `?int` | Query, Optional | Set this path parameter to request up to a specific amount of records. By default 30 records are retrieved per page. The maximum limit that can be set is 100.<br>For example, set `?page[limit]=50` to retrieve up to 50 records for this request. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`MembersResponseResult`](../../doc/models/members-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $membersController->getMembers(
    $token,
    $requestToken,
    $search,
    $totals,
    $pageNumber,
    $pageLimit
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_mbr_67d0336c01048ea41c4382z",
        "created": "2025-03-11 08:58:20.0258",
        "modified": "2025-03-11 08:58:20.0258",
        "creator": "g1577139c2304b7",
        "modifier": "g1577139c2304b7",
        "merchant": "t1_mer_67d033698c234e74c399ddd",
        "title": "CEO",
        "first": "Chad",
        "middle": "",
        "last": "Foster",
        "ssn": "1924",
        "dob": 20160120,
        "dl": "6679",
        "dlstate": "MD",
        "ownership": 10000,
        "email": "Jerrod_Glover@hotmail.com",
        "fax": "",
        "phone": "5106406000",
        "country": "MAR",
        "zip": "60064",
        "state": "MD",
        "city": "East Bettye",
        "address2": "",
        "address1": "83 Dan Ways",
        "primary": 1,
        "inactive": 0,
        "frozen": 0,
        "timezone": "est",
        "gender": "male",
        "creditScore": 334,
        "creditScoreDate": "2025-03-11 08:58:20",
        "significantResponsibility": 0,
        "politicallyExposed": 0,
        "citizenship": "MAR",
        "mailingAddress1": "",
        "mailingAddress2": "",
        "mailingCity": "",
        "mailingState": "MD",
        "mailingPostalCode": "",
        "mailingCountry": "MAR",
        "treasuryPrimeRoles": "",
        "facilitator": "",
        "vendor": "",
        "shareableUrl": "",
        "status": "",
        "createdAt": 1123,
        "completedAt": 1123,
        "plaidIdvId": "",
        "templateId": ""
      }
    ],
    "details": {
      "requestId": 1,
      "totals": [],
      "page": {
        "current": 1,
        "last": 1,
        "hasMore": false
      }
    },
    "errors": []
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Error | [`ErrorFourHundredException`](../../doc/models/error-four-hundred-exception.md) |


# Post Members

Create a Member. A Member is a person who is associated with a Merchant, and one Member associated with each Merchant can be the 'primary' Member, meaning the Member with the most share of ownership in the Merchant.

```php
function postMembers(
    MembersPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): MembersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`MembersPostRequest`](../../doc/models/members-post-request.md) | Body, Required | Create Member Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`MembersResponseResult`](../../doc/models/members-response-result.md)

## Example Usage

```php
$body = MembersPostRequestBuilder::init(
    't1_mer_67d033698c234e74c399ddd',
    'Chad',
    'Foster',
    20160120,
    'Jerrod_Glover@hotmail.com',
    10000,
    MembersTimezoneEnum::EST
)
    ->title('CEO')
    ->middle('middle name')
    ->ssn('1924')
    ->citizenship(CountryEnum::MAR)
    ->gender(MembersGenderEnum::MALE)
    ->dl('6679')
    ->dlstate('MD')
    ->primary(MembersPrimaryEnum::PRIMARYCONTACT)
    ->creditScore(334)
    ->creditScoreDate('2025-03-11 08:58:20')
    ->significantResponsibility(MembersSignificantResponsibilityEnum::NOSIGNIFICANTRESPONSIBILITY)
    ->politicallyExposed(MembersPoliticallyExposedEnum::NOTPOLITICALLYEXPOSED)
    ->mailingAddress1('mailing first line of address')
    ->mailingAddress2('mailing second line of address')
    ->mailingCity('mailing name of the city')
    ->mailingState('MD')
    ->mailingCountry(CountryEnum::MAR)
    ->mailingPostalCode('mailing postal code')
    ->address1('first line of address')
    ->address2('second line of address')
    ->city('name of city')
    ->state('MD')
    ->zip('ZIP code')
    ->country(CountryEnum::MAR)
    ->phone('5106406000')
    ->fax('5106406000')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $membersController->postMembers(
    $body,
    $token,
    $requestToken
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_mbr_67d0336c01048ea41c4382z",
        "created": "2025-03-11 08:58:20.0258",
        "modified": "2025-03-11 08:58:20.0258",
        "creator": "g1577139c2304b7",
        "modifier": "g1577139c2304b7",
        "merchant": "t1_mer_67d033698c234e74c399ddd",
        "title": "CEO",
        "first": "Chad",
        "middle": "",
        "last": "Foster",
        "ssn": "1924",
        "dob": 20160120,
        "dl": "6679",
        "dlstate": "MD",
        "ownership": 10000,
        "email": "Jerrod_Glover@hotmail.com",
        "fax": "",
        "phone": "5106406000",
        "country": "MAR",
        "zip": "60064",
        "state": "MD",
        "city": "East Bettye",
        "address2": "",
        "address1": "83 Dan Ways",
        "primary": 1,
        "inactive": 0,
        "frozen": 0,
        "timezone": "est",
        "gender": "male",
        "creditScore": 334,
        "creditScoreDate": "2025-03-11 08:58:20",
        "significantResponsibility": 0,
        "politicallyExposed": 0,
        "citizenship": "MAR",
        "mailingAddress1": "",
        "mailingAddress2": "",
        "mailingCity": "",
        "mailingState": "MD",
        "mailingPostalCode": "",
        "mailingCountry": "MAR",
        "treasuryPrimeRoles": "",
        "facilitator": "",
        "vendor": "",
        "shareableUrl": "",
        "status": "",
        "createdAt": 1123,
        "completedAt": 1123,
        "plaidIdvId": "",
        "templateId": ""
      }
    ],
    "details": {
      "requestId": 1,
      "totals": [],
      "page": {
        "current": 1,
        "last": 1,
        "hasMore": false
      }
    },
    "errors": []
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Error | [`ErrorFourHundredException`](../../doc/models/error-four-hundred-exception.md) |

