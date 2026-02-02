# Embedded Finance

```php
$embeddedFinanceController = $client->getEmbeddedFinanceController();
```

## Class Name

`EmbeddedFinanceController`

## Methods

* [Get Embedded Finance Id](../../doc/controllers/embedded-finance.md#get-embedded-finance-id)
* [Put Embedded Finance Id](../../doc/controllers/embedded-finance.md#put-embedded-finance-id)
* [Get Embedded Finance](../../doc/controllers/embedded-finance.md#get-embedded-finance)
* [Post Embedded Finance](../../doc/controllers/embedded-finance.md#post-embedded-finance)


# Get Embedded Finance Id

Query a embeddedFinance.

```php
function getEmbeddedFinanceId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): EmbeddedFinanceResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`EmbeddedFinanceResponseResult`](../../doc/models/embedded-finance-response-result.md)

## Example Usage

```php
$id = 't1_efe_685d2955cc86da261b3bd00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $embeddedFinanceController->getEmbeddedFinanceId(
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
        "id": "t1_efe_685d2955cc86da261b3bd00",
        "created": "2025-06-26 07:04:53.8477",
        "modified": "2025-06-26 07:04:53.8477",
        "creator": "t1_log_685d27bb478b996498e00d3",
        "modifier": "t1_log_685d27bb478b996498e00d3",
        "enablementDate": "2025-06-26 00:00:00",
        "product": "merchantWorkingCapital",
        "platform": "PARAFIN",
        "entity": "t1_ent_685d27bc1611a5c48c0000f",
        "org": "t1_org_685d27bd878c0a8cf00ad0c",
        "division": "t1_div_67b51635da21f7399ce2af1",
        "partition": "t1_ptn_666834d4d504f11234578f0",
        "inactive": 0,
        "frozen": 0,
        "productContract": "",
        "accumulatedLoanTotal": ""
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


# Put Embedded Finance Id

Update a embeddedFinance.

```php
function putEmbeddedFinanceId(
    string $id,
    EmbeddedFinancePutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): EmbeddedFinanceResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `body` | [`EmbeddedFinancePutRequest`](../../doc/models/embedded-finance-put-request.md) | Body, Required | Update embeddedFinance Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`EmbeddedFinanceResponseResult`](../../doc/models/embedded-finance-response-result.md)

## Example Usage

```php
$id = 't1_efe_685d2955cc86da261b3bd00';

$body = EmbeddedFinancePutRequestBuilder::init()
    ->enablementDate('2023-06-01 01:00:00')
    ->product(EmbeddedFinanceProductEnum::MERCHANTWORKINGCAPITAL)
    ->platform(EmbededFinancePlatformEnum::PARAFIN)
    ->entity('t1_ent_685d27bc1611a5c48c0000f')
    ->org('t1_org_685d27bd878c0a8cf00ad0c')
    ->division('t1_div_67b51635da21f7399ce2af1')
    ->partition('t1_ptn_666834d4d504f11234578f0')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $embeddedFinanceController->putEmbeddedFinanceId(
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
        "id": "t1_efe_685d2955cc86da261b3bd00",
        "created": "2025-06-26 07:04:53.8477",
        "modified": "2025-06-26 07:04:53.8477",
        "creator": "t1_log_685d27bb478b996498e00d3",
        "modifier": "t1_log_685d27bb478b996498e00d3",
        "enablementDate": "2025-06-26 00:00:00",
        "product": "merchantWorkingCapital",
        "platform": "PARAFIN",
        "entity": "t1_ent_685d27bc1611a5c48c0000f",
        "org": "t1_org_685d27bd878c0a8cf00ad0c",
        "division": "t1_div_67b51635da21f7399ce2af1",
        "partition": "t1_ptn_666834d4d504f11234578f0",
        "inactive": 0,
        "frozen": 0,
        "productContract": "",
        "accumulatedLoanTotal": ""
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


# Get Embedded Finance

Query embeddedFinance.

```php
function getEmbeddedFinance(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): EmbeddedFinanceResponseResult
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

[`EmbeddedFinanceResponseResult`](../../doc/models/embedded-finance-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $embeddedFinanceController->getEmbeddedFinance(
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
        "id": "t1_efe_685d2955cc86da261b3bd00",
        "created": "2025-06-26 07:04:53.8477",
        "modified": "2025-06-26 07:04:53.8477",
        "creator": "t1_log_685d27bb478b996498e00d3",
        "modifier": "t1_log_685d27bb478b996498e00d3",
        "enablementDate": "2025-06-26 00:00:00",
        "product": "merchantWorkingCapital",
        "platform": "PARAFIN",
        "entity": "t1_ent_685d27bc1611a5c48c0000f",
        "org": "t1_org_685d27bd878c0a8cf00ad0c",
        "division": "t1_div_67b51635da21f7399ce2af1",
        "partition": "t1_ptn_666834d4d504f11234578f0",
        "inactive": 0,
        "frozen": 0,
        "productContract": "",
        "accumulatedLoanTotal": ""
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


# Post Embedded Finance

Create a embeddedFinance.

```php
function postEmbeddedFinance(
    EmbeddedFinancePostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): EmbeddedFinanceResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`EmbeddedFinancePostRequest`](../../doc/models/embedded-finance-post-request.md) | Body, Required | Create embeddedFinance |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`EmbeddedFinanceResponseResult`](../../doc/models/embedded-finance-response-result.md)

## Example Usage

```php
$body = EmbeddedFinancePostRequestBuilder::init()
    ->enablementDate('2023-06-01 01:00:00')
    ->product(EmbeddedFinanceProductEnum::MERCHANTWORKINGCAPITAL)
    ->platform(EmbededFinancePlatformEnum::PARAFIN)
    ->entity('t1_ent_685d27bc1611a5c48c0000f')
    ->org('t1_org_685d27bd878c0a8cf00ad0c')
    ->division('t1_div_67b51635da21f7399ce2af1')
    ->partition('t1_ptn_666834d4d504f11234578f0')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $embeddedFinanceController->postEmbeddedFinance(
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
        "id": "t1_efe_685d2955cc86da261b3bd00",
        "created": "2025-06-26 07:04:53.8477",
        "modified": "2025-06-26 07:04:53.8477",
        "creator": "t1_log_685d27bb478b996498e00d3",
        "modifier": "t1_log_685d27bb478b996498e00d3",
        "enablementDate": "2025-06-26 00:00:00",
        "product": "merchantWorkingCapital",
        "platform": "PARAFIN",
        "entity": "t1_ent_685d27bc1611a5c48c0000f",
        "org": "t1_org_685d27bd878c0a8cf00ad0c",
        "division": "t1_div_67b51635da21f7399ce2af1",
        "partition": "t1_ptn_666834d4d504f11234578f0",
        "inactive": 0,
        "frozen": 0,
        "productContract": "",
        "accumulatedLoanTotal": ""
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

