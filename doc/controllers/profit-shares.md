# Profit Shares

```php
$profitSharesController = $client->getProfitSharesController();
```

## Class Name

`ProfitSharesController`

## Methods

* [Get Profit Shares Id](../../doc/controllers/profit-shares.md#get-profit-shares-id)
* [Put Profit Shares Id](../../doc/controllers/profit-shares.md#put-profit-shares-id)
* [Delete Profit Shares Id](../../doc/controllers/profit-shares.md#delete-profit-shares-id)
* [Get Profit Shares](../../doc/controllers/profit-shares.md#get-profit-shares)
* [Post Profit Shares](../../doc/controllers/profit-shares.md#post-profit-shares)


# Get Profit Shares Id

Query a ProfitShare resource, which will cause an entity to have its earnings/expenses shared with another entity.

```php
function getProfitSharesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): ProfitSharesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, The Profit Share ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`ProfitSharesResponseResult`](../../doc/models/profit-shares-response-result.md)

## Example Usage

```php
$id = 't1_psh_67aa7fd81e45a8b5eb569yz';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $profitSharesController->getProfitSharesId(
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
        "id": "t1_psh_67aa7fd81e45a8b5eb569yz",
        "created": "2025-02-10 17:38:16.1450",
        "modified": "2025-02-10 17:38:16.1450",
        "creator": "t1_log_67aa2de0a914190a267b600",
        "modifier": "t1_log_67aa2de0a914190a267b600",
        "login": "t1_log_67aa2de0a914190a267b672",
        "entity": "t1_ent_67aa5d38dbb22dc72775f72",
        "forentity": "t1_ent_673fa38d3e069c7ac4bdbd8",
        "org": "t1_org_67aa73a2d8098f2853f97ee",
        "division": "t1_div_67b51635da21f7399ce2af0",
        "partition": "t1_ptn_666834d4d504f11234578f0",
        "type": "income",
        "name": "LEad Capture",
        "description": "Webhook test2",
        "amount": 5000,
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


# Put Profit Shares Id

Update a ProfitShare resource, which causes an entity's earnings/expenses to be shared with another entity.

```php
function putProfitSharesId(
    string $id,
    ProfitSharesPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ProfitSharesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, The Profit Share ID. |
| `body` | [`ProfitSharesPutRequest`](../../doc/models/profit-shares-put-request.md) | Body, Required | Update Profit Share Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ProfitSharesResponseResult`](../../doc/models/profit-shares-response-result.md)

## Example Usage

```php
$id = 't1_psh_67aa7fd81e45a8b5eb569yz';

$body = ProfitSharesPutRequestBuilder::init()
    ->login('t1_log_67aa2de0a914190a267b672')
    ->entity('t1_ent_67aa5d38dbb22dc72775f72')
    ->forentity('t1_ent_673fa38d3e069c7ac4bdbd8')
    ->org('t1_org_67aa73a2d8098f2853f97ee')
    ->division('t1_div_67b51635da21f7399ce2af0')
    ->partition('t1_ptn_666834d4d504f11234578f0')
    ->type(ProfitShareTypeEnum::INCOME)
    ->name('LEad Capture')
    ->description('Webhook test2')
    ->amount(5000)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $profitSharesController->putProfitSharesId(
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
        "id": "t1_psh_67aa7fd81e45a8b5eb569yz",
        "created": "2025-02-10 17:38:16.1450",
        "modified": "2025-02-10 17:38:16.1450",
        "creator": "t1_log_67aa2de0a914190a267b600",
        "modifier": "t1_log_67aa2de0a914190a267b600",
        "login": "t1_log_67aa2de0a914190a267b672",
        "entity": "t1_ent_67aa5d38dbb22dc72775f72",
        "forentity": "t1_ent_673fa38d3e069c7ac4bdbd8",
        "org": "t1_org_67aa73a2d8098f2853f97ee",
        "division": "t1_div_67b51635da21f7399ce2af0",
        "partition": "t1_ptn_666834d4d504f11234578f0",
        "type": "income",
        "name": "LEad Capture",
        "description": "Webhook test2",
        "amount": 5000,
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


# Delete Profit Shares Id

Delete a ProfitShare resource, which causes an entity's earnings/expenses to be shared with another entity.

```php
function deleteProfitSharesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): ProfitSharesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, The Profit Share ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ProfitSharesResponseResult`](../../doc/models/profit-shares-response-result.md)

## Example Usage

```php
$id = 't1_psh_67aa7fd81e45a8b5eb569yz';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $profitSharesController->deleteProfitSharesId(
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
        "id": "t1_psh_67aa7fd81e45a8b5eb569yz",
        "created": "2025-02-10 17:38:16.1450",
        "modified": "2025-02-10 17:38:16.1450",
        "creator": "t1_log_67aa2de0a914190a267b600",
        "modifier": "t1_log_67aa2de0a914190a267b600",
        "login": "t1_log_67aa2de0a914190a267b672",
        "entity": "t1_ent_67aa5d38dbb22dc72775f72",
        "forentity": "t1_ent_673fa38d3e069c7ac4bdbd8",
        "org": "t1_org_67aa73a2d8098f2853f97ee",
        "division": "t1_div_67b51635da21f7399ce2af0",
        "partition": "t1_ptn_666834d4d504f11234578f0",
        "type": "income",
        "name": "LEad Capture",
        "description": "Webhook test2",
        "amount": 5000,
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


# Get Profit Shares

Query a ProfitShare resource.
A ProfitShare resource will cause an entity to have it's earnings/expenses shared with another entity.

```php
function getProfitShares(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): ProfitSharesResponseResult
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

[`ProfitSharesResponseResult`](../../doc/models/profit-shares-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $profitSharesController->getProfitShares(
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
        "id": "t1_psh_67aa7fd81e45a8b5eb569yz",
        "created": "2025-02-10 17:38:16.1450",
        "modified": "2025-02-10 17:38:16.1450",
        "creator": "t1_log_67aa2de0a914190a267b600",
        "modifier": "t1_log_67aa2de0a914190a267b600",
        "login": "t1_log_67aa2de0a914190a267b672",
        "entity": "t1_ent_67aa5d38dbb22dc72775f72",
        "forentity": "t1_ent_673fa38d3e069c7ac4bdbd8",
        "org": "t1_org_67aa73a2d8098f2853f97ee",
        "division": "t1_div_67b51635da21f7399ce2af0",
        "partition": "t1_ptn_666834d4d504f11234578f0",
        "type": "income",
        "name": "LEad Capture",
        "description": "Webhook test2",
        "amount": 5000,
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


# Post Profit Shares

Create a ProfitShare resource.
A ProfitShare resource will cause an entity to have it's earnings/expenses shared with another entity.

```php
function postProfitShares(
    ProfitSharesPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ProfitSharesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ProfitSharesPostRequest`](../../doc/models/profit-shares-post-request.md) | Body, Required | Create Profit Share Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ProfitSharesResponseResult`](../../doc/models/profit-shares-response-result.md)

## Example Usage

```php
$body = ProfitSharesPostRequestBuilder::init(
    't1_log_67aa2de0a914190a267b672',
    't1_ent_67aa5d38dbb22dc72775f72',
    ProfitShareTypeEnum::INCOME,
    5000
)
    ->forentity(
        't1_ent_673fa38d3e069c7ac4bdbd8'
    )
    ->org(
        't1_org_67aa73a2d8098f2853f97ee'
    )
    ->division('t1_div_67b51635da21f7399ce2af0')
    ->partition('t1_ptn_666834d4d504f11234578f0')
    ->name('LEad Capture')
    ->description('Webhook test2')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $profitSharesController->postProfitShares(
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
        "id": "t1_psh_67aa7fd81e45a8b5eb569yz",
        "created": "2025-02-10 17:38:16.1450",
        "modified": "2025-02-10 17:38:16.1450",
        "creator": "t1_log_67aa2de0a914190a267b600",
        "modifier": "t1_log_67aa2de0a914190a267b600",
        "login": "t1_log_67aa2de0a914190a267b672",
        "entity": "t1_ent_67aa5d38dbb22dc72775f72",
        "forentity": "t1_ent_673fa38d3e069c7ac4bdbd8",
        "org": "t1_org_67aa73a2d8098f2853f97ee",
        "division": "t1_div_67b51635da21f7399ce2af0",
        "partition": "t1_ptn_666834d4d504f11234578f0",
        "type": "income",
        "name": "LEad Capture",
        "description": "Webhook test2",
        "amount": 5000,
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

