# Contacts

A contact reflects a known, valid individual registered as a contact for the entity. It is purely informational and not a required record.

```php
$contactsController = $client->getContactsController();
```

## Class Name

`ContactsController`

## Methods

* [Get Contacts Id](../../doc/controllers/contacts.md#get-contacts-id)
* [Put Contacts Id](../../doc/controllers/contacts.md#put-contacts-id)
* [Delete Contacts Id](../../doc/controllers/contacts.md#delete-contacts-id)
* [Get Contacts](../../doc/controllers/contacts.md#get-contacts)
* [Post Contacts](../../doc/controllers/contacts.md#post-contacts)


# Get Contacts Id

Query a Contact, which represents an individual who is associated with an Entity.

```php
function getContactsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): ContactsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this contact. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`ContactsResponseResult`](../../doc/models/contacts-response-result.md)

## Example Usage

```php
$id = 't1_con_665f696f0d66c3281d00000';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $contactsController->getContactsId(
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
        "id": "t1_con_665f696f0d66c3281d00000",
        "created": "2024-06-04 15:22:23.0592",
        "modified": "2024-06-04 15:22:23.0592",
        "creator": "t1_log_5d263a0050fcc8fb784a957",
        "modifier": "t1_log_5d263a0050fcc8fb784a957",
        "entity": "t1_ent_665e13ff8b2e613134b9273",
        "first": "John",
        "middle": "",
        "last": "Doe",
        "description": "",
        "email": "JohnD@payr.com",
        "fax": "",
        "phone": "",
        "country": "USA",
        "zip": "",
        "state": "AK",
        "city": "",
        "address2": "",
        "address1": "",
        "inactive": 0,
        "frozen": 0
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


# Put Contacts Id

Update a Contact, A Contact resource represents an individual who is associated with an Entity.

```php
function putContactsId(
    string $id,
    ContactsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ContactsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this contact. |
| `body` | [`ContactsPutRequest`](../../doc/models/contacts-put-request.md) | Body, Required | Update Contact Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ContactsResponseResult`](../../doc/models/contacts-response-result.md)

## Example Usage

```php
$id = 't1_con_665f696f0d66c3281d00000';

$body = ContactsPutRequestBuilder::init()
    ->entity('t1_ent_665e13ff8b2e613134b9273')
    ->first('first name')
    ->middle('middle name')
    ->last('last name')
    ->description('description of Contact')
    ->email('fewafehwuohfewafewafewa@payrjfhuiweafewa.com')
    ->address1('first line of the address')
    ->address2('second line of the address')
    ->city('Anchorage')
    ->state('AK')
    ->zip('99501')
    ->country(CountryEnum::USA)
    ->phone('1234567890')
    ->fax('1234567890')
    ->frozen(FrozenEnum::NOTFROZEN)
    ->inactive(InactiveEnum::ACTIVE)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $contactsController->putContactsId(
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
        "id": "t1_con_665f696f0d66c3281d00000",
        "created": "2024-06-04 15:22:23.0592",
        "modified": "2024-06-04 15:22:23.0592",
        "creator": "t1_log_5d263a0050fcc8fb784a957",
        "modifier": "t1_log_5d263a0050fcc8fb784a957",
        "entity": "t1_ent_665e13ff8b2e613134b9273",
        "first": "John",
        "middle": "",
        "last": "Doe",
        "description": "",
        "email": "JohnD@payr.com",
        "fax": "",
        "phone": "",
        "country": "USA",
        "zip": "",
        "state": "AK",
        "city": "",
        "address2": "",
        "address1": "",
        "inactive": 0,
        "frozen": 0
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


# Delete Contacts Id

Delete a Contact. A Contact resource represents an individual who is associated with an Entity.

```php
function deleteContactsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): ContactsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this contact. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ContactsResponseResult`](../../doc/models/contacts-response-result.md)

## Example Usage

```php
$id = 't1_con_665f696f0d66c3281d00000';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $contactsController->deleteContactsId(
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
        "id": "t1_con_665f696f0d66c3281d00000",
        "created": "2024-06-04 15:22:23.0592",
        "modified": "2024-06-04 15:22:23.0592",
        "creator": "t1_log_5d263a0050fcc8fb784a957",
        "modifier": "t1_log_5d263a0050fcc8fb784a957",
        "entity": "t1_ent_665e13ff8b2e613134b9273",
        "first": "John",
        "middle": "",
        "last": "Doe",
        "description": "",
        "email": "JohnD@payr.com",
        "fax": "",
        "phone": "",
        "country": "USA",
        "zip": "",
        "state": "AK",
        "city": "",
        "address2": "",
        "address1": "",
        "inactive": 0,
        "frozen": 0
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


# Get Contacts

Query a Contact, which represents an individual who is associated with an Entity.

```php
function getContacts(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): ContactsResponseResult
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

[`ContactsResponseResult`](../../doc/models/contacts-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $contactsController->getContacts(
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
        "id": "t1_con_665f696f0d66c3281d00000",
        "created": "2024-06-04 15:22:23.0592",
        "modified": "2024-06-04 15:22:23.0592",
        "creator": "t1_log_5d263a0050fcc8fb784a957",
        "modifier": "t1_log_5d263a0050fcc8fb784a957",
        "entity": "t1_ent_665e13ff8b2e613134b9273",
        "first": "John",
        "middle": "",
        "last": "Doe",
        "description": "",
        "email": "JohnD@payr.com",
        "fax": "",
        "phone": "",
        "country": "USA",
        "zip": "",
        "state": "AK",
        "city": "",
        "address2": "",
        "address1": "",
        "inactive": 0,
        "frozen": 0
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


# Post Contacts

Create a Contact.
A Contact resource represents an individual who is associated with an Entity.

```php
function postContacts(
    ContactsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ContactsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ContactsPostRequest`](../../doc/models/contacts-post-request.md) | Body, Required | Create Contact Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ContactsResponseResult`](../../doc/models/contacts-response-result.md)

## Example Usage

```php
$body = ContactsPostRequestBuilder::init(
    't1_ent_665e13ff8b2e613134b9273',
    'first name',
    'last name',
    'fewafehwuohfewafewafewa@payrjfhuiweafewa.com'
)
    ->middle('middle name')
    ->description('description of Contact')
    ->address1('first line of the address')
    ->address2('second line of the address')
    ->city('Anchorage')
    ->state('AK')
    ->zip('99501')
    ->country(CountryEnum::USA)
    ->phone('1234567890')
    ->fax('1234567890')
    ->frozen(FrozenEnum::NOTFROZEN)
    ->inactive(InactiveEnum::ACTIVE)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $contactsController->postContacts(
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
        "id": "t1_con_665f696f0d66c3281d00000",
        "created": "2024-06-04 15:22:23.0592",
        "modified": "2024-06-04 15:22:23.0592",
        "creator": "t1_log_5d263a0050fcc8fb784a957",
        "modifier": "t1_log_5d263a0050fcc8fb784a957",
        "entity": "t1_ent_665e13ff8b2e613134b9273",
        "first": "John",
        "middle": "",
        "last": "Doe",
        "description": "",
        "email": "JohnD@payr.com",
        "fax": "",
        "phone": "",
        "country": "USA",
        "zip": "",
        "state": "AK",
        "city": "",
        "address2": "",
        "address1": "",
        "inactive": 0,
        "frozen": 0
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

