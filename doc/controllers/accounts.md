# Accounts

Accounts deals with  payment account details for merchant boarding and entity funding. Ultimately, all the business performed within Payrix Pro (be it merchant transactions, vendor income, or facilitator fees) must end up in the entity's payment account.

```php
$accountsController = $client->getAccountsController();
```

## Class Name

`AccountsController`

## Methods

* [Get Accounts Id](../../doc/controllers/accounts.md#get-accounts-id)
* [Put Accounts Id](../../doc/controllers/accounts.md#put-accounts-id)
* [Delete Accounts Id](../../doc/controllers/accounts.md#delete-accounts-id)
* [Get Accounts](../../doc/controllers/accounts.md#get-accounts)
* [Post Accounts](../../doc/controllers/accounts.md#post-accounts)


# Get Accounts Id

Query an Account. An Account represents a bank account associated with an Entity.

```php
function getAccountsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): AccountsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`AccountsResponseResult`](../../doc/models/accounts-response-result.md)

## Example Usage

```php
$id = 't1_act_12a003cde5d6b2ec3d9canb';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $accountsController->getAccountsId(
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
        "id": "t1_act_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "entity": "t1_ent_67a18bcde1a1b2ec3d9c9az",
        "account": "t1_pmt_67a18bcde1a1b2ec3d9c9az",
        "token": "1dc2304a56783be9f31001459981abab",
        "name": "Bank Account Non-Primary",
        "description": "Test merchant 9af2d883c7b2c",
        "primary": 0,
        "type": "all",
        "status": 0,
        "reserved": 0,
        "checkStage": "createAccount",
        "expiration": "",
        "inactive": 0,
        "currency": "USD",
        "frozen": 0,
        "publicToken": "public-test-a12eeba1-1234-4567-af1g-d80cc1bfd713",
        "mask": "2345",
        "plaidAccountId": "aK6w4rjrdrIEAcPKp3KyABkaz5NordiRRkbzBP",
        "updateMethod": "NOC"
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


# Put Accounts Id

Update an existing Account representing a bank account associated with an Entity.

```php
function putAccountsId(
    string $id,
    AccountsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): AccountsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of the Account associated with the Entity's bank account. |
| `body` | [`AccountsPutRequest`](../../doc/models/accounts-put-request.md) | Body, Required | A request body for updating existing bank account information for one or more entities. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AccountsResponseResult`](../../doc/models/accounts-response-result.md)

## Example Usage

```php
$id = 't1_act_12a003cde5d6b2ec3d9canb';

$body = AccountsPutRequestBuilder::init()
    ->account(
        AccountsPutRequestSchemaPropertiesBuilder::init()
            ->method(AccountMethodEnum::CHECKING)
            ->number('2')
            ->routing('1')
            ->build()
    )
    ->name('Bank Account Name')
    ->description('Bank account description')
    ->primary(AccountPrimaryEnum::PRIMARY)
    ->type(AccountTypeEnum::ALL)
    ->status(AccountStatusEnum::READY)
    ->expiration('0118')
    ->mask('2345')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $accountsController->putAccountsId(
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
        "id": "t1_act_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "entity": "t1_ent_67a18bcde1a1b2ec3d9c9az",
        "account": "t1_pmt_67a18bcde1a1b2ec3d9c9az",
        "token": "1dc2304a56783be9f31001459981abab",
        "name": "Bank Account Non-Primary",
        "description": "Test merchant 9af2d883c7b2c",
        "primary": 0,
        "type": "all",
        "status": 0,
        "reserved": 0,
        "checkStage": "createAccount",
        "expiration": "",
        "inactive": 0,
        "currency": "USD",
        "frozen": 0,
        "publicToken": "public-test-a12eeba1-1234-4567-af1g-d80cc1bfd713",
        "mask": "2345",
        "plaidAccountId": "aK6w4rjrdrIEAcPKp3KyABkaz5NordiRRkbzBP",
        "updateMethod": "NOC"
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


# Delete Accounts Id

Delete an Account. An Account represents a bank account associated with an Entity.

```php
function deleteAccountsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): AccountsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AccountsResponseResult`](../../doc/models/accounts-response-result.md)

## Example Usage

```php
$id = 't1_act_12a003cde5d6b2ec3d9canb';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $accountsController->deleteAccountsId(
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
        "id": "t1_act_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "entity": "t1_ent_67a18bcde1a1b2ec3d9c9az",
        "account": "t1_pmt_67a18bcde1a1b2ec3d9c9az",
        "token": "1dc2304a56783be9f31001459981abab",
        "name": "Bank Account Non-Primary",
        "description": "Test merchant 9af2d883c7b2c",
        "primary": 0,
        "type": "all",
        "status": 0,
        "reserved": 0,
        "checkStage": "createAccount",
        "expiration": "",
        "inactive": 0,
        "currency": "USD",
        "frozen": 0,
        "publicToken": "public-test-a12eeba1-1234-4567-af1g-d80cc1bfd713",
        "mask": "2345",
        "plaidAccountId": "aK6w4rjrdrIEAcPKp3KyABkaz5NordiRRkbzBP",
        "updateMethod": "NOC"
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


# Get Accounts

Query Accounts that each represent a bank account associated with an Entity.

```php
function getAccounts(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): AccountsResponseResult
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

[`AccountsResponseResult`](../../doc/models/accounts-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $accountsController->getAccounts(
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
        "id": "t1_act_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "entity": "t1_ent_67a18bcde1a1b2ec3d9c9az",
        "account": "t1_pmt_67a18bcde1a1b2ec3d9c9az",
        "token": "1dc2304a56783be9f31001459981abab",
        "name": "Bank Account Non-Primary",
        "description": "Test merchant 9af2d883c7b2c",
        "primary": 0,
        "type": "all",
        "status": 0,
        "reserved": 0,
        "checkStage": "createAccount",
        "expiration": "",
        "inactive": 0,
        "currency": "USD",
        "frozen": 0,
        "publicToken": "public-test-a12eeba1-1234-4567-af1g-d80cc1bfd713",
        "mask": "2345",
        "plaidAccountId": "aK6w4rjrdrIEAcPKp3KyABkaz5NordiRRkbzBP",
        "updateMethod": "NOC"
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


# Post Accounts

Create an account, representing a bank account, to associate bank information with an Entity.

```php
function postAccounts(
    AccountsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): AccountsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`AccountsPostRequest`](../../doc/models/accounts-post-request.md) | Body, Required | Add Bank Account Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AccountsResponseResult`](../../doc/models/accounts-response-result.md)

## Example Usage

```php
$body = AccountsPostRequestBuilder::init(
    't1_ent_5a1pf5a1234531155a12345',
    AccountsAccountBuilder::init()
        ->method(AccountMethodEnum::CHECKING)
        ->number('2')
        ->routing('1')
        ->build()
)
    ->name('Bank Account Name')
    ->description('Bank account description')
    ->primary(AccountPrimaryEnum::PRIMARY)
    ->type(AccountTypeEnum::ALL)
    ->status(AccountStatusEnum::READY)
    ->expiration('0118')
    ->currency(CurrencyEnum::USD)
    ->publicToken('public-test-a12eeba1-1234-4567-af1g-d80cc1bfd713')
    ->mask('2345')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $accountsController->postAccounts(
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
        "id": "t1_act_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "entity": "t1_ent_67a18bcde1a1b2ec3d9c9az",
        "account": {
          "id": "t1_pmt_67a18bcde1a1b2ec3d9c9az",
          "method": 10,
          "number": "9876",
          "routing": "1234"
        },
        "token": "1dc2304a56783be9f31001459981abab",
        "name": "Bank Account Non-Primary",
        "description": "Test merchant 9af2d883c7b2c",
        "primary": 0,
        "type": "all",
        "status": 0,
        "reserved": 0,
        "checkStage": "createAccount",
        "expiration": "",
        "inactive": 0,
        "currency": "USD",
        "frozen": 0,
        "publicToken": "public-test-a12eeba1-1234-4567-af1g-d80cc1bfd713",
        "mask": "2345",
        "plaidAccountId": "aK6w4rjrdrIEAcPKp3KyABkaz5NordiRRkbzBP",
        "updateMethod": "NOC"
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

