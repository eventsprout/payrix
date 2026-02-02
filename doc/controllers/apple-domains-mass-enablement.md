# Apple Domains Mass Enablement

```php
$appleDomainsMassEnablementController = $client->getAppleDomainsMassEnablementController();
```

## Class Name

`AppleDomainsMassEnablementController`

## Methods

* [Post Apple Pay for Csv](../../doc/controllers/apple-domains-mass-enablement.md#post-apple-pay-for-csv)
* [Post Apple Pay for Merchant List](../../doc/controllers/apple-domains-mass-enablement.md#post-apple-pay-for-merchant-list)
* [Post Apple Pay for Merchant List Disable](../../doc/controllers/apple-domains-mass-enablement.md#post-apple-pay-for-merchant-list-disable)
* [Post Update Apple Pay Domain](../../doc/controllers/apple-domains-mass-enablement.md#post-update-apple-pay-domain)


# Post Apple Pay for Csv

"Registers Apple Pay domains for multiple merchants using a CSV file. The uploaded CSV must include at least two columns: `"domain"` and `"merchant_id"`. All other columns are ignored. The file is parsed using the header row, and any data rows with missing or extra columns are also rejected.

For each merchant-domain pair, the system creates an `appleDomains` record. Domains not already registered are marked as `registering`, and asynchronous processing begins. If verification succeeds, the status updates to `registered`. If verification fails, the status changes to `failed_registration`, with an `errorNote` explaining the reason.

This endpoint is idempotent for previously registered domains, allowing repeated submissions without adverse effects. You can resubmit the same CSV to retry failed registrations after resolving any issues.

Upload the CSV file as a form-data field named files. All domains must be fully qualified domain names (FQDNs) and must host the Apple Pay verification file at:
https://{merchantDomain}/.well-known/apple-developer-merchantid-domain-association

```php
function postApplePayForCsv(
    string $id,
    FileWrapper $files,
    ?string $token = null,
    ?string $requestToken = null
): AppleDomainsMassEnablementCsvResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The Payrix Pro Entity ID for the Partner initiating domain verification for one or more Merchants. |
| `files` | `FileWrapper` | Form, Required | The `multipart/form-data` field used to upload the CSV file containing merchant-domain pairs for Apple Pay domain verification.<br>The CSV file must include a header row with at least two columns: `"domain"` and `"merchant_id"`. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AppleDomainsMassEnablementCsvResponseResult`](../../doc/models/apple-domains-mass-enablement-csv-response-result.md)

## Example Usage

```php
$id = 'p1_ent_123abc4d567890efg1h2i34';

$files = FileWrapper::createFromPath('dummy_file');

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $appleDomainsMassEnablementController->postApplePayForCsv(
    $id,
    $files,
    $token,
    $requestToken
);
```

## Example Response *(as JSON)*

```json
{
  "response": [
    {
      "dataPreview": [
        {
          "merchantId": "p1_mer_123abc4d567890efg1h2i34",
          "domain": "domain1.com"
        },
        {
          "merchantId": "p1_mer_234bcd5e678901fgh2i3j45",
          "domain": "domain2.com"
        },
        {
          "merchantId": "p1_mer_345cde6f789012ghi3j4k56",
          "domain": "domain1.com"
        },
        {
          "merchantId": "p1_mer_456def7g890123hij4k5l67",
          "domain": "domain3.com"
        }
      ],
      "msg": "Merchant Registration for Apple Pay Initiated",
      "status": "success"
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Error | [`ErrorFourHundredException`](../../doc/models/error-four-hundred-exception.md) |


# Post Apple Pay for Merchant List

Registers Apple Pay domains for a list of merchants using a JSON request body. For each merchant-domain pair, the system creates an `appleDomains` record. Domains not already registered update their status to `registering`, and asynchronous verification begins. If verification succeeds, the status updates to `registered`. If verification fails, the status changes to `failed_registration`, with an `errorNote` explaining the reason.

This endpoint is idempotent, allowing repeated submissions of the same request body without adverse effects. Only failed registrations are retried.

All domains must be fully qualified domain names (FQDNs) and must host the Apple Pay verification file at:
https://{merchantDomain}/.well-known/apple-developer-merchantid-domain-association

```php
function postApplePayForMerchantList(
    string $id,
    ApplePayForMerchantListPostRequest $body,
    ?string $requestToken = null,
    ?string $token = null
): AppleDomainsMassEnablementForMerchantList
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The Payrix Pro Entity ID for the Partner initiating domain verification for one or more Merchants. |
| `body` | [`ApplePayForMerchantListPostRequest`](../../doc/models/apple-pay-for-merchant-list-post-request.md) | Body, Required | - |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |

## Response Type

[`AppleDomainsMassEnablementForMerchantList`](../../doc/models/apple-domains-mass-enablement-for-merchant-list.md)

## Example Usage

```php
$id = 'p1_ent_123abc4d567890efg1h2i34';

$body = ApplePayForMerchantListPostRequestBuilder::init()->build();

$requestToken = '20250423-yourmerchant-refunds-001';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $appleDomainsMassEnablementController->postApplePayForMerchantList(
    $id,
    $body,
    $requestToken,
    $token
);
```

## Example Response *(as JSON)*

```json
{
  "response": [
    {
      "msg": "Merchant Registration for Apple Pay Initiated",
      "status": "success"
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Error | [`ErrorFourHundredException`](../../doc/models/error-four-hundred-exception.md) |


# Post Apple Pay for Merchant List Disable

Unregisters Apple Pay domains for a list of merchants using a JSON request body. For each merchant-domain pair, the system updates the corresponding appleDomains record to reflect the `unregistered` status. Domains not yet unregistered are marked as `unregistering`, and asynchronous processing begins. If unregistration succeeds, the status updates to `unregistered`. If unregistration fails, the status reverts back to `registered`, with an `errorNote` explaining the reason.

This endpoint is idempotent, allowing repeated submissions of the same request body without adverse effects. Only failed de-registrations are retried.

All domains must be fully qualified domain names (FQDNs) and must have previously been registered for Apple Pay and verified.

```php
function postApplePayForMerchantListDisable(
    string $id,
    ApplePayForMerchantListPostRequest $body,
    ?string $requestToken = null,
    ?string $token = null
): AppleDomainsMassEnablementForMerchantList
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The Payrix Pro Entity ID for the Partner initiating unregistration for one or more Merchants. |
| `body` | [`ApplePayForMerchantListPostRequest`](../../doc/models/apple-pay-for-merchant-list-post-request.md) | Body, Required | - |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |

## Response Type

[`AppleDomainsMassEnablementForMerchantList`](../../doc/models/apple-domains-mass-enablement-for-merchant-list.md)

## Example Usage

```php
$id = 'p1_ent_123abc4d567890efg1h2i34';

$body = ApplePayForMerchantListPostRequestBuilder::init()->build();

$requestToken = '20250423-yourmerchant-refunds-001';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $appleDomainsMassEnablementController->postApplePayForMerchantListDisable(
    $id,
    $body,
    $requestToken,
    $token
);
```

## Example Response *(as JSON)*

```json
{
  "response": [
    {
      "msg": "Merchant Unregistration for Apple Pay Initiated",
      "status": "success"
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Error | [`ErrorFourHundredException`](../../doc/models/error-four-hundred-exception.md) |


# Post Update Apple Pay Domain

Verifies a remote Apple Pay configuration file.

The configuration file must be stored on the merchant's or vendor's domain, but accessible to the Payrix systems.

This endpoint can be used to ensure the configuration file is in the correct location with the correct rights for remote access.

It is meant to validate one configuration file with the provided Fully Qualified Domain Name (fqdn).

This endpoint does not do any action towards registration. It only verifies access to the remote file.

```php
function postUpdateApplePayDomain(
    string $id,
    UpdateApplePayDomainPostRequest $body,
    ?string $requestToken = null,
    ?string $token = null
): UpdateApplePayDomainResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The Payrix Pro Merchant ID for the Partner initiating verification for the listed domain. |
| `body` | [`UpdateApplePayDomainPostRequest`](../../doc/models/update-apple-pay-domain-post-request.md) | Body, Required | - |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |

## Response Type

[`UpdateApplePayDomainResponseResult`](../../doc/models/update-apple-pay-domain-response-result.md)

## Example Usage

```php
$id = 'p1_mer_123abc4d567890efg1h2i34';

$body = UpdateApplePayDomainPostRequestBuilder::init()
    ->domain('domain.com')
    ->build();

$requestToken = '20250423-yourmerchant-refunds-001';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $appleDomainsMassEnablementController->postUpdateApplePayDomain(
    $id,
    $body,
    $requestToken,
    $token
);
```

## Example Response *(as JSON)*

```json
{
  "responses": []
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Error | [`ErrorFourHundredException`](../../doc/models/error-four-hundred-exception.md) |

