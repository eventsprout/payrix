# Omni Tokens

OmniTokens stores information related to the activation of the resource for an entity. OmniToken's Valued Added Service helps protect transactions and reduce transaction risk.

```php
$omniTokensController = $client->getOmniTokensController();
```

## Class Name

`OmniTokensController`

## Methods

* [Get Omni Tokens Id](../../doc/controllers/omni-tokens.md#get-omni-tokens-id)
* [Put Omni Tokens Id](../../doc/controllers/omni-tokens.md#put-omni-tokens-id)
* [Get Omni Tokens](../../doc/controllers/omni-tokens.md#get-omni-tokens)
* [Post Omni Tokens](../../doc/controllers/omni-tokens.md#post-omni-tokens)


# Get Omni Tokens Id

Query a omniToken.

```php
function getOmniTokensId(string $id, ?string $token = null, ?string $embed = null): OmniTokensResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this OmniToken. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`OmniTokensResponseResult`](../../doc/models/omni-tokens-response-result.md)

## Example Usage

```php
$id = 't1_otk_6809db98230a5b02b08f00z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $omniTokensController->getOmniTokensId(
    $id,
    $token
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_otk_6809db98230a5b02b08f00z",
        "created": "2025-04-24 02:35:04.1649",
        "modified": "2025-04-24 02:35:04.1649",
        "creator": "t1_log_663ce214b2f25f2325a9935",
        "modifier": "t1_log_663ce214b2f25f2325a9935",
        "enablementDate": "2025-04-24 02:35:04",
        "org": "t1_org_5b0e08025ec790d3f9b8c00",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414978z0",
        "entity": "t1_ent_6809db6dd78923dadbfd904",
        "platform": "VCORE",
        "inactive": 0,
        "frozen": 0,
        "deleted": "2025-04-24 02:35:04",
        "deleter": ""
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


# Put Omni Tokens Id

Update a Token.

```php
function putOmniTokensId(
    string $id,
    OmniTokensPutRequest $body,
    ?string $token = null
): OmniTokensResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this OmniToken. |
| `body` | [`OmniTokensPutRequest`](../../doc/models/omni-tokens-put-request.md) | Body, Required | Update OmniToken Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |

## Response Type

[`OmniTokensResponseResult`](../../doc/models/omni-tokens-response-result.md)

## Example Usage

```php
$id = 't1_otk_6809db98230a5b02b08f00z';

$body = OmniTokensPutRequestBuilder::init()
    ->enablementDate('2025-04-24 02:35:04')
    ->org('t1_org_5b0e08025ec790d3f9b8c00')
    ->division('t1_div_67c56806728fbbf0bae0b00')
    ->partition('t1_ptn_666834d4d504f21414978z0')
    ->entity('t1_ent_6809db6dd78923dadbfd904')
    ->platform(PlatformModelEnum::VCORE)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->deleted('2025-04-24 02:35:04')
    ->deleter('')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $omniTokensController->putOmniTokensId(
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
        "id": "t1_otk_6809db98230a5b02b08f00z",
        "created": "2025-04-24 02:35:04.1649",
        "modified": "2025-04-24 02:35:04.1649",
        "creator": "t1_log_663ce214b2f25f2325a9935",
        "modifier": "t1_log_663ce214b2f25f2325a9935",
        "enablementDate": "2025-04-24 02:35:04",
        "org": "t1_org_5b0e08025ec790d3f9b8c00",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414978z0",
        "entity": "t1_ent_6809db6dd78923dadbfd904",
        "platform": "VCORE",
        "inactive": 0,
        "frozen": 0,
        "deleted": "2025-04-24 02:35:04",
        "deleter": ""
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


# Get Omni Tokens

Query a omniTokens.

```php
function getOmniTokens(
    ?string $token = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): OmniTokensResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `search` | `?string` | Header, Optional | Set this header to filter or sort the list of resources that the method returns.<br>See [Searches](page:welcome#searches) for detailed information and examples on how to use search header. |
| `totals` | `?string` | Header, Optional | To configure a request to return a total for all instances of a field in a result set,  use the totals header in the format `totals={operator}[]={key}`.  This will calculate the desired total and return it in the `details > totals` object of the response.  For instance, if you want to sum the `total` field of all transactions,  you would use the `sum` operator. The response will include the result set,  along with the calculated total in the `details` section. See [Collection Operators](page:welcome#collection-operators) for detailed information and examples on how to use totals header. |
| `pageNumber` | `?int` | Query, Optional | Set this path parameter to request a specific page of records.<br>For example, set `?page[number]=2` to retrieve the second page of records for this request. |
| `pageLimit` | `?int` | Query, Optional | Set this path parameter to request up to a specific amount of records. By default 30 records are retrieved per page. The maximum limit that can be set is 100.<br>For example, set `?page[limit]=50` to retrieve up to 50 records for this request. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`OmniTokensResponseResult`](../../doc/models/omni-tokens-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $omniTokensController->getOmniTokens(
    $token,
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
        "id": "t1_otk_6809db98230a5b02b08f00z",
        "created": "2025-04-24 02:35:04.1649",
        "modified": "2025-04-24 02:35:04.1649",
        "creator": "t1_log_663ce214b2f25f2325a9935",
        "modifier": "t1_log_663ce214b2f25f2325a9935",
        "enablementDate": "2025-04-24 02:35:04",
        "org": "t1_org_5b0e08025ec790d3f9b8c00",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414978z0",
        "entity": "t1_ent_6809db6dd78923dadbfd904",
        "platform": "VCORE",
        "inactive": 0,
        "frozen": 0,
        "deleted": "2025-04-24 02:35:04",
        "deleter": ""
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


# Post Omni Tokens

Create a omniTokens.

```php
function postOmniTokens(OmniTokensPostRequest $body): OmniTokensResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`OmniTokensPostRequest`](../../doc/models/omni-tokens-post-request.md) | Body, Required | Create omniTokens |

## Response Type

[`OmniTokensResponseResult`](../../doc/models/omni-tokens-response-result.md)

## Example Usage

```php
$body = OmniTokensPostRequestBuilder::init()
    ->enablementDate('2025-04-24 02:35:04')
    ->org('t1_org_5b0e08025ec790d3f9b8c00')
    ->division('t1_div_67c56806728fbbf0bae0b00')
    ->partition('t1_ptn_666834d4d504f21414978z0')
    ->entity('t1_ent_6809db6dd78923dadbfd904')
    ->platform(PlatformModelEnum::VCORE)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->deleted('2025-04-24 02:35:04')
    ->deleter('')
    ->build();

$result = $omniTokensController->postOmniTokens($body);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_otk_6809db98230a5b02b08f00z",
        "created": "2025-04-24 02:35:04.1649",
        "modified": "2025-04-24 02:35:04.1649",
        "creator": "t1_log_663ce214b2f25f2325a9935",
        "modifier": "t1_log_663ce214b2f25f2325a9935",
        "enablementDate": "2025-04-24 02:35:04",
        "org": "t1_org_5b0e08025ec790d3f9b8c00",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414978z0",
        "entity": "t1_ent_6809db6dd78923dadbfd904",
        "platform": "VCORE",
        "inactive": 0,
        "frozen": 0,
        "deleted": "2025-04-24 02:35:04",
        "deleter": ""
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

