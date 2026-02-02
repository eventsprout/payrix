# Terminals

Resources for dealing with transaction that occur on physical terminals, such as a table or register.

```php
$terminalsController = $client->getTerminalsController();
```

## Class Name

`TerminalsController`

## Methods

* [Get Terminals Id](../../doc/controllers/terminals.md#get-terminals-id)
* [Put Terminals Id](../../doc/controllers/terminals.md#put-terminals-id)
* [Delete Terminals Id](../../doc/controllers/terminals.md#delete-terminals-id)
* [Get Terminals](../../doc/controllers/terminals.md#get-terminals)
* [Post Terminals](../../doc/controllers/terminals.md#post-terminals)


# Get Terminals Id

Query a Terminal resource.

```php
function getTerminalsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): TerminalsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Terminal ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`TerminalsResponseResult`](../../doc/models/terminals-response-result.md)

## Example Usage

```php
$id = 't1_tml_67c12924f339facb1c80000';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $terminalsController->getTerminalsId(
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
        "id": "t1_tml_67c12924f339facb1c80000",
        "created": "2025-02-27 22:10:29.0043",
        "modified": "2025-02-27 22:10:29.0043",
        "creator": "t1_log_5cd987a73478a6179b95000",
        "modifier": "t1_log_5cd987a73478a6179b95000",
        "merchant": "t1_mer_67c127497499df129bfc68b",
        "type": "paxSp30Casio",
        "capability": 1,
        "environment": 1,
        "autoClose": 2,
        "autoCloseTime": 2355,
        "name": "",
        "description": "",
        "address1": "",
        "address2": "",
        "city": "",
        "state": "AB",
        "zip": "",
        "country": "CAN",
        "timezone": "est",
        "status": 1,
        "phone": "",
        "serial": "",
        "cloudEnabled": 0,
        "token": ""
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


# Put Terminals Id

Update a Terminal resource.

```php
function putTerminalsId(
    string $id,
    TerminalsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): TerminalsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Terminal ID. |
| `body` | [`TerminalsPutRequest`](../../doc/models/terminals-put-request.md) | Body, Required | Update Terminal Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TerminalsResponseResult`](../../doc/models/terminals-response-result.md)

## Example Usage

```php
$id = 't1_tml_67c12924f339facb1c80000';

$body = TerminalsPutRequestBuilder::init()
    ->type(TerminalTypeEnum::PAXSP30CASIO)
    ->capability(TerminalsCapabilityEnum::KEYED)
    ->environment(TerminalEnvironmentEnum::RETAIL)
    ->autoClose(TerminalsAutoCloseEnum::NONE)
    ->autoCloseTime(2355)
    ->cloudEnabled(TerminalsCloudEnabledEnum::CLOUDSERVICESDISABLED)
    ->serial('serial number')
    ->token('token')
    ->name('name of this terminal')
    ->description('description of the Terminal')
    ->address1('first line of the address')
    ->address2('second line of the address')
    ->city('city name')
    ->state('AB')
    ->zip('zip code')
    ->country(CountryEnum::CAN)
    ->phone('phone number')
    ->timezone(TerminalsTimezoneEnum::EST)
    ->status(TerminalStatusEnum::ACTIVE)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $terminalsController->putTerminalsId(
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
        "id": "t1_tml_67c12924f339facb1c80000",
        "created": "2025-02-27 22:10:29.0043",
        "modified": "2025-02-27 22:10:29.0043",
        "creator": "t1_log_5cd987a73478a6179b95000",
        "modifier": "t1_log_5cd987a73478a6179b95000",
        "merchant": "t1_mer_67c127497499df129bfc68b",
        "type": "paxSp30Casio",
        "capability": 1,
        "environment": 1,
        "autoClose": 2,
        "autoCloseTime": 2355,
        "name": "",
        "description": "",
        "address1": "",
        "address2": "",
        "city": "",
        "state": "AB",
        "zip": "",
        "country": "CAN",
        "timezone": "est",
        "status": 1,
        "phone": "",
        "serial": "",
        "cloudEnabled": 0,
        "token": ""
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


# Delete Terminals Id

Delete a terminal resource that represents a device/software that will be used to process transactions.

```php
function deleteTerminalsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): TerminalsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Terminal ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TerminalsResponseResult`](../../doc/models/terminals-response-result.md)

## Example Usage

```php
$id = 't1_tml_67c12924f339facb1c80000';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $terminalsController->deleteTerminalsId(
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
        "id": "t1_tml_67c12924f339facb1c80000",
        "created": "2025-02-27 22:10:29.0043",
        "modified": "2025-02-27 22:10:29.0043",
        "creator": "t1_log_5cd987a73478a6179b95000",
        "modifier": "t1_log_5cd987a73478a6179b95000",
        "merchant": "t1_mer_67c127497499df129bfc68b",
        "type": "paxSp30Casio",
        "capability": 1,
        "environment": 1,
        "autoClose": 2,
        "autoCloseTime": 2355,
        "name": "",
        "description": "",
        "address1": "",
        "address2": "",
        "city": "",
        "state": "AB",
        "zip": "",
        "country": "CAN",
        "timezone": "est",
        "status": 1,
        "phone": "",
        "serial": "",
        "cloudEnabled": 0,
        "token": ""
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


# Get Terminals

Query a terminal resource.
A terminal resource represents a device/software that will be used to process transactions.

```php
function getTerminals(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): TerminalsResponseResult
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

[`TerminalsResponseResult`](../../doc/models/terminals-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $terminalsController->getTerminals(
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
        "id": "t1_tml_67c12924f339facb1c80000",
        "created": "2025-02-27 22:10:29.0043",
        "modified": "2025-02-27 22:10:29.0043",
        "creator": "t1_log_5cd987a73478a6179b95000",
        "modifier": "t1_log_5cd987a73478a6179b95000",
        "merchant": "t1_mer_67c127497499df129bfc68b",
        "type": "paxSp30Casio",
        "capability": 1,
        "environment": 1,
        "autoClose": 2,
        "autoCloseTime": 2355,
        "name": "",
        "description": "",
        "address1": "",
        "address2": "",
        "city": "",
        "state": "AB",
        "zip": "",
        "country": "CAN",
        "timezone": "est",
        "status": 1,
        "phone": "",
        "serial": "",
        "cloudEnabled": 0,
        "token": ""
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


# Post Terminals

Create a terminal resource.
A terminal resource represents a device/software that will be used to process transactions.

```php
function postTerminals(
    TerminalsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): TerminalsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`TerminalsPostRequest`](../../doc/models/terminals-post-request.md) | Body, Required | Create Terminal Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TerminalsResponseResult`](../../doc/models/terminals-response-result.md)

## Example Usage

```php
$body = TerminalsPostRequestBuilder::init(
    't1_mer_67c127497499df129bfc68b',
    TerminalTypeEnum::PAXSP30CASIO,
    TerminalsAutoCloseEnum::NONE,
    TerminalStatusEnum::ACTIVE
)
    ->capability(TerminalsCapabilityEnum::KEYED)
    ->environment(TerminalEnvironmentEnum::RETAIL)
    ->autoCloseTime(2355)
    ->cloudEnabled(TerminalsCloudEnabledEnum::CLOUDSERVICESDISABLED)
    ->serial('serial number')
    ->token('token')
    ->name('name of this terminal')
    ->description('description of the Terminal')
    ->address1('first line of the address')
    ->address2('second line of the address')
    ->city('city name')
    ->state('AB')
    ->zip('zip code')
    ->country(CountryEnum::CAN)
    ->phone('phone number')
    ->timezone(TerminalsTimezoneEnum::EST)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $terminalsController->postTerminals(
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
        "id": "t1_tml_67c12924f339facb1c80000",
        "created": "2025-02-27 22:10:29.0043",
        "modified": "2025-02-27 22:10:29.0043",
        "creator": "t1_log_5cd987a73478a6179b95000",
        "modifier": "t1_log_5cd987a73478a6179b95000",
        "merchant": "t1_mer_67c127497499df129bfc68b",
        "type": "paxSp30Casio",
        "capability": 1,
        "environment": 1,
        "autoClose": 2,
        "autoCloseTime": 2355,
        "name": "",
        "description": "",
        "address1": "",
        "address2": "",
        "city": "",
        "state": "AB",
        "zip": "",
        "country": "CAN",
        "timezone": "est",
        "status": 1,
        "phone": "",
        "serial": "",
        "cloudEnabled": 0,
        "token": ""
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

