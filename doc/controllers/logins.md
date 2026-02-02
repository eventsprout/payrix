# Logins

Logins resources deal with individual user details like name and email as well as management details like which partition and division the user belongs to.

```php
$loginsController = $client->getLoginsController();
```

## Class Name

`LoginsController`

## Methods

* [Get Logins Id](../../doc/controllers/logins.md#get-logins-id)
* [Put Logins Id](../../doc/controllers/logins.md#put-logins-id)
* [Delete Logins Id](../../doc/controllers/logins.md#delete-logins-id)
* [Get Logins](../../doc/controllers/logins.md#get-logins)
* [Post Logins](../../doc/controllers/logins.md#post-logins)


# Get Logins Id

Query a Login. A Login is a user of the API and has a unique username and password.

```php
function getLoginsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): LoginsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Login ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`LoginsResponseResult`](../../doc/models/logins-response-result.md)

## Example Usage

```php
$id = 't1_log_67c56806038bb4eb85a0000';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $loginsController->getLoginsId(
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
        "id": "t1_log_67c56806038bb4eb85a0000",
        "created": "2025-03-03 03:27:50.0511",
        "modified": "2025-03-03 03:38:26.1424",
        "creator": "g1577139c2304b0",
        "modifier": "t1_log_67c56806038bb4eb85a0000",
        "login": "g15967a6e0d7cf6",
        "lastLogin": "2025-03-03 03:38:26",
        "username": "user9287347954",
        "password": "myPassword",
        "first": "John",
        "middle": "",
        "last": "Doe",
        "email": "user2118145526@example.com",
        "fax": "",
        "phone": "0028106820",
        "country": "USA",
        "zip": "77379",
        "state": "TX",
        "city": "Spring",
        "address2": "",
        "address1": "9337 SPRING CYPRESS RD STE A413",
        "confirmed": 0,
        "roles": 64,
        "partition": "g157713aff9b946",
        "division": "t1_div_67c56806728fbbf0bae0b10",
        "inactive": 0,
        "frozen": 0,
        "allowedResources": "",
        "restrictedResources": "",
        "parentDivision": "",
        "portalAccess": 1,
        "ssoId": "",
        "mfaEnabled": 1,
        "mfaSecret": "",
        "mfaEnrolledDate": "2025-06-16 08:02:53",
        "mfaType": "",
        "mfaSmsCodesCount": 0,
        "mfaSmsWindow": 0,
        "loginAsEnabled": 1,
        "effectiveRoles": 1550314
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


# Put Logins Id

Update a Login, which is a user of the API having a unique username and password.

```php
function putLoginsId(
    string $id,
    LoginsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): LoginsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Login ID. |
| `body` | [`LoginsPutRequest`](../../doc/models/logins-put-request.md) | Body, Required | Update Login Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`LoginsResponseResult`](../../doc/models/logins-response-result.md)

## Example Usage

```php
$id = 't1_log_67c56806038bb4eb85a0000';

$body = LoginsPutRequestBuilder::init()
    ->login('g15967a6e0d7cf6')
    ->partition('g157713aff9b946')
    ->division('t1_div_67c56806728fbbf0bae0b10')
    ->parentDivision('t1_div_67c56806728fbbf0bae0b10')
    ->roles(64)
    ->confirmed(LoginsConfirmedEnum::NOTCONFIRMED)
    ->username('user9287347954')
    ->password('****')
    ->first('John')
    ->last('Doe')
    ->email('user2118145526@example.com')
    ->allowedResources('{"create":["accounts","payouts"],"read":["disbursements","disbursementResults"],"update":["accounts","payouts"],"delete":["accounts","payouts"],"totals":["disbursements","disbursementResults"]}')
    ->restrictedResources('{"create":["ltxns"],"read":["txnResults"],"update":["txns"],"delete":["txns"],"totals":["txns"]}')
    ->portalAccess(LoginsPortalAccessEnum::HASACCESS)
    ->mfaEnabled(LoginsMfaEnabledEnum::DISABLED)
    ->mfaSecret('****')
    ->mfaEnrolledDate('2025-06-16 08:02:53')
    ->mfaType('totp')
    ->address1('9337 SPRING CYPRESS RD STE A413')
    ->address2('Suite 403')
    ->city('Spring')
    ->state('TX')
    ->zip('77379')
    ->country(CountryEnum::USA)
    ->phone('1028106820')
    ->fax('1085069293')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $loginsController->putLoginsId(
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
        "id": "t1_log_67c56806038bb4eb85a0000",
        "created": "2025-03-03 03:27:50.0511",
        "modified": "2025-03-03 03:38:26.1424",
        "creator": "g1577139c2304b0",
        "modifier": "t1_log_67c56806038bb4eb85a0000",
        "login": "g15967a6e0d7cf6",
        "lastLogin": "2025-03-03 03:38:26",
        "username": "user9287347954",
        "password": "myPassword",
        "first": "John",
        "middle": "",
        "last": "Doe",
        "email": "user2118145526@example.com",
        "fax": "",
        "phone": "0028106820",
        "country": "USA",
        "zip": "77379",
        "state": "TX",
        "city": "Spring",
        "address2": "",
        "address1": "9337 SPRING CYPRESS RD STE A413",
        "confirmed": 0,
        "roles": 64,
        "partition": "g157713aff9b946",
        "division": "t1_div_67c56806728fbbf0bae0b10",
        "inactive": 0,
        "frozen": 0,
        "allowedResources": "",
        "restrictedResources": "",
        "parentDivision": "",
        "portalAccess": 1,
        "ssoId": "",
        "mfaEnabled": 1,
        "mfaSecret": "",
        "mfaEnrolledDate": "2025-06-16 08:02:53",
        "mfaType": "",
        "mfaSmsCodesCount": 0,
        "mfaSmsWindow": 0,
        "loginAsEnabled": 1,
        "effectiveRoles": 1550314
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


# Delete Logins Id

Delete a Login. A Login is a user of the API and has a unique username and password.

```php
function deleteLoginsId(string $id, ?string $token = null, ?string $requestToken = null): LoginsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Login ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`LoginsResponseResult`](../../doc/models/logins-response-result.md)

## Example Usage

```php
$id = 't1_log_67c56806038bb4eb85a0000';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $loginsController->deleteLoginsId(
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
        "id": "t1_log_67c56806038bb4eb85a0000",
        "created": "2025-03-03 03:27:50.0511",
        "modified": "2025-03-03 03:38:26.1424",
        "creator": "g1577139c2304b0",
        "modifier": "t1_log_67c56806038bb4eb85a0000",
        "login": "g15967a6e0d7cf6",
        "lastLogin": "2025-03-03 03:38:26",
        "username": "user9287347954",
        "password": "myPassword",
        "first": "John",
        "middle": "",
        "last": "Doe",
        "email": "user2118145526@example.com",
        "fax": "",
        "phone": "0028106820",
        "country": "USA",
        "zip": "77379",
        "state": "TX",
        "city": "Spring",
        "address2": "",
        "address1": "9337 SPRING CYPRESS RD STE A413",
        "confirmed": 0,
        "roles": 64,
        "partition": "g157713aff9b946",
        "division": "t1_div_67c56806728fbbf0bae0b10",
        "inactive": 0,
        "frozen": 0,
        "allowedResources": "",
        "restrictedResources": "",
        "parentDivision": "",
        "portalAccess": 1,
        "ssoId": "",
        "mfaEnabled": 1,
        "mfaSecret": "",
        "mfaEnrolledDate": "2025-06-16 08:02:53",
        "mfaType": "",
        "mfaSmsCodesCount": 0,
        "mfaSmsWindow": 0,
        "loginAsEnabled": 1,
        "effectiveRoles": 1550314
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


# Get Logins

Query Logins. Retrieves the list of all users details like name and email as well as management details like which partition and division the user belongs to. A Login represents the unique ID of the user making an API request. Each user has a unique username and password

```php
function getLogins(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): LoginsResponseResult
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

[`LoginsResponseResult`](../../doc/models/logins-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $loginsController->getLogins(
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
        "id": "t1_log_67c56806038bb4eb85a0000",
        "created": "2025-03-03 03:27:50.0511",
        "modified": "2025-03-03 03:38:26.1424",
        "creator": "g1577139c2304b0",
        "modifier": "t1_log_67c56806038bb4eb85a0000",
        "login": "g15967a6e0d7cf6",
        "lastLogin": "2025-03-03 03:38:26",
        "username": "user9287347954",
        "password": "myPassword",
        "first": "John",
        "middle": "",
        "last": "Doe",
        "email": "user2118145526@example.com",
        "fax": "",
        "phone": "0028106820",
        "country": "USA",
        "zip": "77379",
        "state": "TX",
        "city": "Spring",
        "address2": "",
        "address1": "9337 SPRING CYPRESS RD STE A413",
        "confirmed": 0,
        "roles": 64,
        "partition": "g157713aff9b946",
        "division": "t1_div_67c56806728fbbf0bae0b10",
        "inactive": 0,
        "frozen": 0,
        "allowedResources": "",
        "restrictedResources": "",
        "parentDivision": "",
        "portalAccess": 1,
        "ssoId": "",
        "mfaEnabled": 1,
        "mfaSecret": "",
        "mfaEnrolledDate": "2025-06-16 08:02:53",
        "mfaType": "",
        "mfaSmsCodesCount": 0,
        "mfaSmsWindow": 0,
        "loginAsEnabled": 1,
        "effectiveRoles": 1550314
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


# Post Logins

Create a Login. A Login represents the unique ID of the user making an API request. Each user has a unique username and password.

```php
function postLogins(
    LoginsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): LoginsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`LoginsPostRequest`](../../doc/models/logins-post-request.md) | Body, Required | Create Login Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`LoginsResponseResult`](../../doc/models/logins-response-result.md)

## Example Usage

```php
$body = LoginsPostRequestBuilder::init(
    'g157713aff9b946',
    'user9287347954',
    '****',
    'John',
    'Doe',
    'user2118145526@example.com',
    LoginsMfaEnabledEnum::DISABLED
)
    ->login('g15967a6e0d7cf6')
    ->division(
        't1_div_67c56806728fbbf0bae0b10'
    )
    ->parentDivision('Login belongs to')
    ->roles(64)
    ->allowedResources('{"create":["accounts","payouts"],"read":["disbursements","disbursementResults"],"update":["accounts","payouts"],"delete":["accounts","payouts"],"totals":["disbursements","disbursementResults"]}')
    ->restrictedResources('{"create":["ltxns"],"read":["txnResults"],"update":["txns"],"delete":["txns"],"totals":["txns"]}')
    ->portalAccess(LoginsPortalAccessEnum::HASACCESS)
    ->mfaSecret('****')
    ->mfaEnrolledDate('2025-06-16 08:02:53')
    ->mfaType('totp')
    ->address1('9337 SPRING CYPRESS RD STE A413')
    ->address2('Suite 403')
    ->city('Spring')
    ->state('TX')
    ->zip('77379')
    ->country(CountryEnum::USA)
    ->phone('1028106820')
    ->fax('1085069293')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $loginsController->postLogins(
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
        "id": "t1_log_67c56806038bb4eb85a0000",
        "created": "2025-03-03 03:27:50.0511",
        "modified": "2025-03-03 03:38:26.1424",
        "creator": "g1577139c2304b0",
        "modifier": "t1_log_67c56806038bb4eb85a0000",
        "login": "g15967a6e0d7cf6",
        "lastLogin": "2025-03-03 03:38:26",
        "username": "user9287347954",
        "password": "myPassword",
        "first": "John",
        "middle": "",
        "last": "Doe",
        "email": "user2118145526@example.com",
        "fax": "",
        "phone": "0028106820",
        "country": "USA",
        "zip": "77379",
        "state": "TX",
        "city": "Spring",
        "address2": "",
        "address1": "9337 SPRING CYPRESS RD STE A413",
        "confirmed": 0,
        "roles": 64,
        "partition": "g157713aff9b946",
        "division": "t1_div_67c56806728fbbf0bae0b10",
        "inactive": 0,
        "frozen": 0,
        "allowedResources": "",
        "restrictedResources": "",
        "parentDivision": "",
        "portalAccess": 1,
        "ssoId": "",
        "mfaEnabled": 1,
        "mfaSecret": "",
        "mfaEnrolledDate": "2025-06-16 08:02:53",
        "mfaType": "",
        "mfaSmsCodesCount": 0,
        "mfaSmsWindow": 0,
        "loginAsEnabled": 1,
        "effectiveRoles": 1550314
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

