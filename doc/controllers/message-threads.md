# Message Threads

```php
$messageThreadsController = $client->getMessageThreadsController();
```

## Class Name

`MessageThreadsController`

## Methods

* [Get Message Threads Id](../../doc/controllers/message-threads.md#get-message-threads-id)
* [Put Message Threads Id](../../doc/controllers/message-threads.md#put-message-threads-id)
* [Get Message Threads](../../doc/controllers/message-threads.md#get-message-threads)


# Get Message Threads Id

Query a Message Thread that represents the sender, receiver, and subject of the Messages resources.

```php
function getMessageThreadsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): MessageThreadsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this message thread. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`MessageThreadsResponseResult`](../../doc/models/message-threads-response-result.md)

## Example Usage

```php
$id = 't1_mtd_67ef5bad402b6b61e701e0z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $messageThreadsController->getMessageThreadsId(
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
        "id": "t1_mtd_67ef5bad402b6b61e701e0z",
        "created": "2025-04-04 00:10:21.2659",
        "modified": "2025-04-04 00:10:21.2659",
        "creator": "t1_log_63d25f51ea7ddb271d78304",
        "modifier": "t1_log_63d25f51ea7ddb271d78304",
        "login": "t1_log_621e8010c0e6c5b0262944c",
        "forlogin": "t1_log_61e9b7302360fbf12999d63",
        "hold": "t1_hld_67ef5bad3be038935902204",
        "entityReturn": "",
        "opposingMessageThread": "t1_mtd_67ef5bad40f7e68822ac0c7",
        "folder": "default",
        "sender": "testnewmerchant",
        "recipient": "testnewmerchant1",
        "subject": "Transaction was put on hold"
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


# Put Message Threads Id

Update a Message Thread that represents the sender, receiver, and subject of the Messages resources.

```php
function putMessageThreadsId(
    string $id,
    MessageThreadsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): MessageThreadsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this message thread. |
| `body` | [`MessageThreadsPutRequest`](../../doc/models/message-threads-put-request.md) | Body, Required | Update Message Thread Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`MessageThreadsResponseResult`](../../doc/models/message-threads-response-result.md)

## Example Usage

```php
$id = 't1_mtd_67ef5bad402b6b61e701e0z';

$body = MessageThreadsPutRequestBuilder::init()
    ->login('t1_mtd_67ef5bad402b6b61e701e0z')
    ->forlogin('t1_log_61e9b7302360fbf12999d63')
    ->hold('t1_hld_67ef5bad3be038935902204')
    ->entityReturn('entityReturn')
    ->opposingMessageThread('t1_mtd_67ef5bad40f7e68822ac0c7')
    ->folder('default')
    ->sender('testnewmerchant')
    ->recipient('testnewmerchant1')
    ->subject('Transaction was put on hold')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $messageThreadsController->putMessageThreadsId(
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
        "id": "t1_mtd_67ef5bad402b6b61e701e0z",
        "created": "2025-04-04 00:10:21.2659",
        "modified": "2025-04-04 00:10:21.2659",
        "creator": "t1_log_63d25f51ea7ddb271d78304",
        "modifier": "t1_log_63d25f51ea7ddb271d78304",
        "login": "t1_log_621e8010c0e6c5b0262944c",
        "forlogin": "t1_log_61e9b7302360fbf12999d63",
        "hold": "t1_hld_67ef5bad3be038935902204",
        "entityReturn": "",
        "opposingMessageThread": "t1_mtd_67ef5bad40f7e68822ac0c7",
        "folder": "default",
        "sender": "testnewmerchant",
        "recipient": "testnewmerchant1",
        "subject": "Transaction was put on hold"
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


# Get Message Threads

Query a Message Threads resource that represents the sender, receiver, and subject of the Messages resources

```php
function getMessageThreads(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): MessageThreadsResponseResult
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

[`MessageThreadsResponseResult`](../../doc/models/message-threads-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $messageThreadsController->getMessageThreads(
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
        "id": "t1_mtd_67ef5bad402b6b61e701e0z",
        "created": "2025-04-04 00:10:21.2659",
        "modified": "2025-04-04 00:10:21.2659",
        "creator": "t1_log_63d25f51ea7ddb271d78304",
        "modifier": "t1_log_63d25f51ea7ddb271d78304",
        "login": "t1_log_621e8010c0e6c5b0262944c",
        "forlogin": "t1_log_61e9b7302360fbf12999d63",
        "hold": "t1_hld_67ef5bad3be038935902204",
        "entityReturn": "",
        "opposingMessageThread": "t1_mtd_67ef5bad40f7e68822ac0c7",
        "folder": "default",
        "sender": "testnewmerchant",
        "recipient": "testnewmerchant1",
        "subject": "Transaction was put on hold"
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

