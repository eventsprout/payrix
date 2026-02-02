# Terminal Transaction Reference

```php
$terminalTransactionReferenceController = $client->getTerminalTransactionReferenceController();
```

## Class Name

`TerminalTransactionReferenceController`


# Post Terminal Txn Refs

Create a terminalTxnRefs resource, which represents a reference code issued by the Processor in relation to a particular Transaction.

```php
function postTerminalTxnRefs(
    TerminalTxnRefPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): TerminalTxnRefResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`TerminalTxnRefPostRequest`](../../doc/models/terminal-txn-ref-post-request.md) | Body, Required | Create Terminal Transaction Reference Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TerminalTxnRefResponseResult`](../../doc/models/terminal-txn-ref-response-result.md)

## Example Usage

```php
$body = TerminalTxnRefPostRequestBuilder::init(
    't1_ttx_6806cde42b47ee61cdf6ab9',
    'MCC000012',
    TerminalTxnRefStageEnum::AUTHORIZATION,
    PlatformModelEnum::VCORE
)->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $terminalTransactionReferenceController->postTerminalTxnRefs(
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
        "id": "t1_ttr_6806cde43831bc88d5f4e00",
        "created": "2025-04-21 18:59:48.2388",
        "modified": "2025-04-21 18:59:48.2388",
        "creator": "t1_log_62fd0aa37c3d8ec3a9dcea8",
        "modifier": "t1_log_62fd0aa37c3d8ec3a9dcea8",
        "terminalTxn": "t1_ttx_6806cde42b47ee61cdf6ab9",
        "ref": "MCC000012",
        "stage": "auth",
        "platform": "VCORE"
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

