# Tokens

Tokens provide the means through which to safely and securely store payment methods (e.g. credit cards or bank accounts) for later use.

```php
$tokensController = $client->getTokensController();
```

## Class Name

`TokensController`

## Methods

* [Get Tokens Id](../../doc/controllers/tokens.md#get-tokens-id)
* [Put Tokens Id](../../doc/controllers/tokens.md#put-tokens-id)
* [Delete Tokens Id](../../doc/controllers/tokens.md#delete-tokens-id)
* [Get Tokens](../../doc/controllers/tokens.md#get-tokens)
* [Post Tokens](../../doc/controllers/tokens.md#post-tokens)


# Get Tokens Id

Query a Token, which is a resource that acts as a storage place for credit card and customer information, allowing you to run Transactions.

```php
function getTokensId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): TokensResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this token. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`TokensResponseResult`](../../doc/models/tokens-response-result.md)

## Example Usage

```php
$id = 'p1_tok_00c82eb304b0067620c82be';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $tokensController->getTokensId(
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
        "id": "p1_tok_00c82eb304b0067620c82be",
        "created": "2025-03-05 06:00:03.0273",
        "modified": "2025-03-05 06:00:03.0273",
        "creator": "t1_log_00c82eb304b0067620c8",
        "modifier": "t1_log_00c82eb304b0067620c8",
        "customer": "t1_cus_00c82eb304b0067620c7",
        "payment": "p1_pmt_67c802b1b662567771cf8e0",
        "status": "pending",
        "token": "11c6a6d85f0a20c31e4c49e461066850",
        "omnitoken": "123",
        "track": "",
        "cvv": "",
        "expiration": "0123",
        "name": "test",
        "description": "test Token",
        "custom": "Custom Token Processor 1",
        "authTokenCustomer": "",
        "inactive": 0,
        "frozen": 0,
        "origin": "2",
        "entryMode": 2
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


# Put Tokens Id

Update a Token, which is a resource that acts as a storage place for credit card and customer information, allowing you to run Transactions.

```php
function putTokensId(string $id, TokenPutRequest $body, ?string $token = null): TokensResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this Token. |
| `body` | [`TokenPutRequest`](../../doc/models/token-put-request.md) | Body, Required | Update Token Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |

## Response Type

[`TokensResponseResult`](../../doc/models/tokens-response-result.md)

## Example Usage

```php
$id = 'p1_tok_00c82eb304b0067620c82be';

$body = TokenPutRequestBuilder::init()
    ->customer('t1_cus_00c82eb304b0067620c7')
    ->payment(
        TokenPaymentParamBuilder::init()
            ->method(TokenPaymentMethodEnum::AMEX)
            ->number('378734493671000')
            ->routing('code')
            ->build()
    )
    ->status(TokenStatusEnum::PENDING)
    ->token('11c6a6d85f0a20c31e4c49e461066850')
    ->expiration('0123')
    ->name('test1')
    ->description('test Token')
    ->custom('Custom Token Processor 1')
    ->authTokenCustomer('authToken')
    ->origin(2)
    ->entryMode(2)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $tokensController->putTokensId(
    $id,
    $body,
    $token
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "p1_tok_00c82eb304b0067620c82be",
        "created": "2025-03-05 06:00:03.0273",
        "modified": "2025-03-05 06:00:03.0273",
        "creator": "t1_log_00c82eb304b0067620c8",
        "modifier": "t1_log_00c82eb304b0067620c8",
        "customer": "t1_cus_00c82eb304b0067620c7",
        "payment": "p1_pmt_67c802b1b662567771cf8e0",
        "status": "pending",
        "token": "11c6a6d85f0a20c31e4c49e461066850",
        "omnitoken": "123",
        "track": "",
        "cvv": "",
        "expiration": "0123",
        "name": "test",
        "description": "test Token",
        "custom": "Custom Token Processor 1",
        "authTokenCustomer": "",
        "inactive": 0,
        "frozen": 0,
        "origin": "2",
        "entryMode": 2
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


# Delete Tokens Id

Delete a Token, which is a resource that acts as a storage place for credit card and customer information, allowing you to run Transactions.

```php
function deleteTokensId(string $id, ?string $token = null, ?string $requestToken = null): TokensResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this token. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TokensResponseResult`](../../doc/models/tokens-response-result.md)

## Example Usage

```php
$id = 'p1_tok_00c82eb304b0067620c82be';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $tokensController->deleteTokensId(
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
        "id": "p1_tok_00c82eb304b0067620c82be",
        "created": "2025-03-05 06:00:03.0273",
        "modified": "2025-03-05 06:00:03.0273",
        "creator": "t1_log_00c82eb304b0067620c8",
        "modifier": "t1_log_00c82eb304b0067620c8",
        "customer": "t1_cus_00c82eb304b0067620c7",
        "payment": "p1_pmt_67c802b1b662567771cf8e0",
        "status": "pending",
        "token": "11c6a6d85f0a20c31e4c49e461066850",
        "omnitoken": "123",
        "track": "",
        "cvv": "",
        "expiration": "0123",
        "name": "test",
        "description": "test Token",
        "custom": "Custom Token Processor 1",
        "authTokenCustomer": "",
        "inactive": 0,
        "frozen": 0,
        "origin": "2",
        "entryMode": 2
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


# Get Tokens

Query a Token. A Token is a resource that acts as a storage place for credit card and customer information. You can use a Token to run Transactions.

```php
function getTokens(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): TokensResponseResult
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

[`TokensResponseResult`](../../doc/models/tokens-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $tokensController->getTokens(
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
        "id": "p1_tok_00c82eb304b0067620c82be",
        "created": "2025-03-05 06:00:03.0273",
        "modified": "2025-03-05 06:00:03.0273",
        "creator": "t1_log_00c82eb304b0067620c8",
        "modifier": "t1_log_00c82eb304b0067620c8",
        "customer": "t1_cus_00c82eb304b0067620c7",
        "payment": "p1_pmt_67c802b1b662567771cf8e0",
        "status": "pending",
        "token": "11c6a6d85f0a20c31e4c49e461066850",
        "omnitoken": "123",
        "track": "",
        "cvv": "",
        "expiration": "0123",
        "name": "test",
        "description": "test Token",
        "custom": "Custom Token Processor 1",
        "authTokenCustomer": "",
        "inactive": 0,
        "frozen": 0,
        "origin": "2",
        "entryMode": 2
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


# Post Tokens

Create a Token. A Token is a resource that acts as a storage place for credit card and customer information. You can use a Token to run Transactions.

```php
function postTokens(
    TokenPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): TokensResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`TokenPostRequest`](../../doc/models/token-post-request.md) | Body, Required | Create Token Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TokensResponseResult`](../../doc/models/tokens-response-result.md)

## Example Usage

```php
$body = TokenPostRequestBuilder::init(
    't1_cus_00c82eb304b0067620c7',
    PaymentPostRequestBuilder::init()
        ->method(PaymentMethodEnum::AMEX)
        ->number('378734493671000')
        ->routing('code')
        ->build(),
    TokenStatusEnum::PENDING,
    InactiveEnum::ACTIVE,
    FrozenEnum::NOTFROZEN
)
    ->expiration('0123')
    ->name('test')
    ->description('test Token')
    ->custom('Custom Token Processor 2')
    ->authTokenCustomer('authToken')
    ->origin(2)
    ->entryMode(2)
    ->omnitoken('123')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $tokensController->postTokens(
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
        "id": "p1_tok_00c82eb304b0067620c82be",
        "created": "2025-03-05 06:00:03.0273",
        "modified": "2025-03-05 06:00:03.0273",
        "creator": "t1_log_00c82eb304b0067620c8",
        "modifier": "t1_log_00c82eb304b0067620c8",
        "customer": "t1_cus_00c82eb304b0067620c7",
        "payment": "p1_pmt_67c802b1b662567771cf8e0",
        "status": "pending",
        "token": "11c6a6d85f0a20c31e4c49e461066850",
        "omnitoken": "123",
        "track": "",
        "cvv": "",
        "expiration": "0123",
        "name": "test",
        "description": "test Token",
        "custom": "Custom Token Processor 1",
        "authTokenCustomer": "",
        "inactive": 0,
        "frozen": 0,
        "origin": "2",
        "entryMode": 2
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

