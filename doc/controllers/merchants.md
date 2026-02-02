# Merchants

Merchant details for transaction processing entities. Together with the entities table, this table defines a merchant. A merchant is primarily an entity that accepts payments and transacts with customers in Payrix Pro.

```php
$merchantsController = $client->getMerchantsController();
```

## Class Name

`MerchantsController`

## Methods

* [Get Merchants](../../doc/controllers/merchants.md#get-merchants)
* [Post Merchants](../../doc/controllers/merchants.md#post-merchants)
* [Get Merchants Id](../../doc/controllers/merchants.md#get-merchants-id)
* [Put Merchants Id](../../doc/controllers/merchants.md#put-merchants-id)
* [Delete Merchants Id](../../doc/controllers/merchants.md#delete-merchants-id)


# Get Merchants

Query a Merchant, an organization that processes credit card payments, each associated with an Entity.

```php
function getMerchants(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): MerchantsResponseResult
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

[`MerchantsResponseResult`](../../doc/models/merchants-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $merchantsController->getMerchants(
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
        "id": "p1_mer_00c66ace58ad2d376bb0067",
        "created": "2025-03-03 21:51:58.4016",
        "modified": "2025-03-03 22:56:04.3579",
        "creator": "p1_log_0067be40688861230a79682",
        "modifier": "p1_log_00c66acd69830f6a0d4718b",
        "lastActivity": "2025-03-03 21:51:58",
        "entity": "p1_ent_00c66acd8154446fc5567a3",
        "dba": "Colorado Blitz",
        "new": 0,
        "established": 20250226,
        "annualCCSales": 750000,
        "avgTicket": 15000,
        "amex": "",
        "discover": "",
        "mcc": "7997",
        "status": 2,
        "boarded": 20250303,
        "inactive": 0,
        "frozen": 0,
        "environment": "ecommerce",
        "visaMvv": "",
        "chargebackNotificationEmail": "",
        "statusReason": "noResponse",
        "totalApprovedSales": 0,
        "autoBoarded": 1,
        "saqType": "SAQ-A",
        "saqDate": 20250303,
        "qsa": "",
        "letterStatus": 0,
        "letterDate": 20250303,
        "tcAttestation": 1,
        "visaDisclosure": 1,
        "disclosureIP": "67.174.101.19",
        "disclosureDate": 20250303,
        "accountClosureReasonCode": "",
        "accountClosureReasonDate": 20250303,
        "annualCCSaleVolume": 0,
        "annualACHSaleVolume": 0,
        "riskLevel": "restricted",
        "creditRatio": 0,
        "creditTimeliness": 0,
        "chargebackRatio": 0,
        "ndxDays": 0,
        "ndxPercentage": 0,
        "advancedBilling": 0,
        "locationType": 77,
        "percentKeyed": 0,
        "totalVolume": 0,
        "percentEcomm": 0,
        "seasonal": 0,
        "amexVolume": 0,
        "incrementalAuthSupported": 0,
        "tmxSessionId": "6395015c-b0cc-45ba-abdc-aaf17123a4db",
        "percentBusiness": 0,
        "applePayActive": 0,
        "applePayStatus": "",
        "googlePayActive": 1,
        "passTokenEnabled": 0,
        "naics": "11",
        "naicsDescription": "",
        "expressBatchCloseMethod": "TimeInitiated",
        "expressBatchCloseTime": ""
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


# Post Merchants

Create a new Merchant. Details for creating one will be available soon.

```php
function postMerchants(
    MerchantsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): MerchantsPostResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`MerchantsPostRequest`](../../doc/models/merchants-post-request.md) | Body, Required | - |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`MerchantsPostResponseResult`](../../doc/models/merchants-post-response-result.md)

## Example Usage

```php
$body = MerchantsPostRequestBuilder::init(
    'p1_ent_00c94cb712c4cb8ecbe4c88',
    MerchantEnvironmentEnum::CARDPRESENT
)
    ->totalApprovedSales(0)
    ->dba('DISPOSAL LLC')
    ->new(MerchantsNewEnum::NOTNEW)
    ->advancedBilling(MerchantsAdvanceBillingEnum::DISABLED)
    ->seasonal(MerchantsSeasonalEnum::YEARROUND)
    ->established(20210916)
    ->annualCCSales(2530)
    ->annualCCSaleVolume(2530)
    ->annualACHSaleVolume(2530)
    ->amexVolume(0)
    ->avgTicket(56000)
    ->amex('American Express merchant identifier')
    ->discover('Discover merchant identifier')
    ->mcc('1799')
    ->visaMvv('Merchant Verification Value')
    ->visaDisclosure(MerchantsVisaDisclosureIPEnum::NOTACCEPTED)
    ->disclosureIP('11.11.11.111')
    ->disclosureDate(20250307)
    ->status(MerchantStatusEnum::BOARDED)
    ->incrementalAuthSupported(MerchantsIncrementalAuthSupportedEnum::NOTSUPPORTED)
    ->autoBoarded(MerchantAutoBoardedEnum::AUTOBOARDED)
    ->statusReason(MerchantStatusReasonEnum::FRAUD)
    ->locationType(MerchantLocationTypeEnum::RETAILSTOREFRONT)
    ->percentEcomm(70)
    ->percentKeyed(30)
    ->percentBusiness(0)
    ->totalVolume(1000000)
    ->accountClosureReasonCode('reason code')
    ->accountClosureReasonDate(20250307)
    ->riskLevel(MerchantRiskLevelEnum::RESTRICTED)
    ->creditRatio(0)
    ->creditTimeliness(0)
    ->chargebackRatio(0)
    ->ndxDays(1)
    ->ndxPercentage(0)
    ->saqType(MerchantsSaqTypeEnum::SAQA)
    ->saqDate(20250307)
    ->qsa('0')
    ->letterStatus(MerchantsLetterStatusEnum::OFF)
    ->letterDate(20250307)
    ->chargebackNotificationEmail('Notification Email')
    ->tcAttestation(MerchantsTcAttestationEnum::NOTACCEPTED)
    ->applePayActive(MerchantsApplePayActiveEnum::INACTIVE)
    ->googlePayActive(MerchantsGooglePayActiveEnum::ACTIVE)
    ->naics(MerchantsNaicsEnum::AGRICULTURE)
    ->naicsDescription('other')
    ->tmxSessionId('007462d6-a1df-40f4-b998-35bfa5539562')
    ->passTokenEnabled(MerchantsPassTokenEnabledEnum::DISABLED)
    ->expressBatchCloseMethod(MerchantsExpressBatchCloseMethodEnum::TIMEINITIATED)
    ->expressBatchCloseTime('03:00:00')
    ->omniTokenEnabled(MerchantsOmniTokenEnabledEnum::DISABLED)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $merchantsController->postMerchants(
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
        "id": "p1_mer_00c66ace58ad2d376bb0067",
        "created": "2025-03-03 21:51:58.4016",
        "modified": "2025-03-03 22:56:04.3579",
        "creator": "p1_log_0067be40688861230a79682",
        "modifier": "p1_log_00c66acd69830f6a0d4718b",
        "lastActivity": "2025-03-03 21:51:58",
        "entity": "p1_ent_00c66acd8154446fc5567a3",
        "dba": "Colorado Blitz",
        "new": 0,
        "established": 20250226,
        "annualCCSales": 750000,
        "avgTicket": 15000,
        "amex": "",
        "discover": "",
        "mcc": "7997",
        "status": 2,
        "boarded": 20250303,
        "inactive": 0,
        "frozen": 0,
        "environment": "ecommerce",
        "visaMvv": "",
        "chargebackNotificationEmail": "",
        "statusReason": "noResponse",
        "totalApprovedSales": 0,
        "autoBoarded": 1,
        "saqType": "SAQ-A",
        "saqDate": 20250303,
        "qsa": "",
        "letterStatus": 0,
        "letterDate": 20250303,
        "tcAttestation": 1,
        "visaDisclosure": 1,
        "disclosureIP": "67.174.101.19",
        "disclosureDate": 20250303,
        "accountClosureReasonCode": "",
        "accountClosureReasonDate": 20250303,
        "annualCCSaleVolume": 0,
        "annualACHSaleVolume": 0,
        "riskLevel": "restricted",
        "creditRatio": 0,
        "creditTimeliness": 0,
        "chargebackRatio": 0,
        "ndxDays": 0,
        "ndxPercentage": 0,
        "advancedBilling": 0,
        "locationType": 77,
        "percentKeyed": 0,
        "totalVolume": 0,
        "percentEcomm": 0,
        "seasonal": 0,
        "amexVolume": 0,
        "incrementalAuthSupported": 0,
        "tmxSessionId": "6395015c-b0cc-45ba-abdc-aaf17123a4db",
        "percentBusiness": 0,
        "applePayActive": 0,
        "applePayStatus": "",
        "googlePayActive": 1,
        "passTokenEnabled": 0,
        "naics": "11",
        "naicsDescription": "",
        "expressBatchCloseMethod": "TimeInitiated",
        "expressBatchCloseTime": ""
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


# Get Merchants Id

Query a Merchant, which is an organization that processes credit card payments and each is associated with an Entity.

```php
function getMerchantsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): MerchantsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, also known as the Merchant ID (MID). |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`MerchantsResponseResult`](../../doc/models/merchants-response-result.md)

## Example Usage

```php
$id = 'p1_mer_00c6b12d04ac280ed694323';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $merchantsController->getMerchantsId(
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
        "id": "p1_mer_00c66ace58ad2d376bb0067",
        "created": "2025-03-03 21:51:58.4016",
        "modified": "2025-03-03 22:56:04.3579",
        "creator": "p1_log_0067be40688861230a79682",
        "modifier": "p1_log_00c66acd69830f6a0d4718b",
        "lastActivity": "2025-03-03 21:51:58",
        "entity": "p1_ent_00c66acd8154446fc5567a3",
        "dba": "Colorado Blitz",
        "new": 0,
        "established": 20250226,
        "annualCCSales": 750000,
        "avgTicket": 15000,
        "amex": "",
        "discover": "",
        "mcc": "7997",
        "status": 2,
        "boarded": 20250303,
        "inactive": 0,
        "frozen": 0,
        "environment": "ecommerce",
        "visaMvv": "",
        "chargebackNotificationEmail": "",
        "statusReason": "noResponse",
        "totalApprovedSales": 0,
        "autoBoarded": 1,
        "saqType": "SAQ-A",
        "saqDate": 20250303,
        "qsa": "",
        "letterStatus": 0,
        "letterDate": 20250303,
        "tcAttestation": 1,
        "visaDisclosure": 1,
        "disclosureIP": "67.174.101.19",
        "disclosureDate": 20250303,
        "accountClosureReasonCode": "",
        "accountClosureReasonDate": 20250303,
        "annualCCSaleVolume": 0,
        "annualACHSaleVolume": 0,
        "riskLevel": "restricted",
        "creditRatio": 0,
        "creditTimeliness": 0,
        "chargebackRatio": 0,
        "ndxDays": 0,
        "ndxPercentage": 0,
        "advancedBilling": 0,
        "locationType": 77,
        "percentKeyed": 0,
        "totalVolume": 0,
        "percentEcomm": 0,
        "seasonal": 0,
        "amexVolume": 0,
        "incrementalAuthSupported": 0,
        "tmxSessionId": "6395015c-b0cc-45ba-abdc-aaf17123a4db",
        "percentBusiness": 0,
        "applePayActive": 0,
        "applePayStatus": "",
        "googlePayActive": 1,
        "passTokenEnabled": 0,
        "naics": "11",
        "naicsDescription": "",
        "expressBatchCloseMethod": "TimeInitiated",
        "expressBatchCloseTime": ""
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


# Put Merchants Id

Update a Merchant, A Merchant is an organization that processes credit card payments. Each Merchant is associated with an Entity.

```php
function putMerchantsId(
    string $id,
    MerchantsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): MerchantsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, also known as the Merchant ID (MID). |
| `body` | [`MerchantsPutRequest`](../../doc/models/merchants-put-request.md) | Body, Required | Update Merchant Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`MerchantsResponseResult`](../../doc/models/merchants-response-result.md)

## Example Usage

```php
$id = 'p1_mer_00c6b12d04ac280ed694323';

$body = MerchantsPutRequestBuilder::init()
    ->totalApprovedSales(0)
    ->entity('p1_ent_00c94cb712c4cb8ecbe4c88')
    ->dba('DISPOSAL LLC')
    ->new(MerchantsNewEnum::NOTNEW)
    ->advancedBilling(MerchantsAdvanceBillingEnum::DISABLED)
    ->seasonal(MerchantsSeasonalEnum::YEARROUND)
    ->established(20210916)
    ->annualCCSales(2530)
    ->annualCCSaleVolume(2530)
    ->annualACHSaleVolume(2530)
    ->amexVolume(0)
    ->avgTicket(56000)
    ->amex('American Express merchant identifier')
    ->discover('Discover merchant identifier')
    ->mcc('1799')
    ->visaMvv('Merchant Verification Value')
    ->visaDisclosure(MerchantsVisaDisclosureIPEnum::NOTACCEPTED)
    ->disclosureIP('11.11.11.111')
    ->disclosureDate(20250307)
    ->environment(MerchantEnvironmentEnum::CARDPRESENT)
    ->status(MerchantStatusEnum::BOARDED)
    ->incrementalAuthSupported(MerchantsIncrementalAuthSupportedEnum::NOTSUPPORTED)
    ->autoBoarded(MerchantAutoBoardedEnum::AUTOBOARDED)
    ->statusReason(MerchantStatusReasonEnum::FRAUD)
    ->locationType(MerchantLocationTypeEnum::RETAILSTOREFRONT)
    ->percentEcomm(70)
    ->percentKeyed(30)
    ->percentBusiness(0)
    ->totalVolume(1000000)
    ->accountClosureReasonCode('reason code')
    ->accountClosureReasonDate(20250307)
    ->riskLevel(MerchantRiskLevelEnum::RESTRICTED)
    ->creditRatio(0)
    ->creditTimeliness(0)
    ->chargebackRatio(0)
    ->ndxDays(1)
    ->ndxPercentage(0)
    ->saqType(MerchantsSaqTypeEnum::SAQA)
    ->saqDate(20250307)
    ->qsa('0')
    ->letterStatus(MerchantsLetterStatusEnum::OFF)
    ->letterDate(20250307)
    ->chargebackNotificationEmail('Notification Email')
    ->tcAttestation(MerchantsTcAttestationEnum::NOTACCEPTED)
    ->applePayActive(MerchantsApplePayActiveEnum::INACTIVE)
    ->googlePayActive(MerchantsGooglePayActiveEnum::ACTIVE)
    ->naics(MerchantsNaicsEnum::AGRICULTURE)
    ->naicsDescription('other')
    ->tmxSessionId('007462d6-a1df-40f4-b998-35bfa5539562')
    ->passTokenEnabled(MerchantsPassTokenEnabledEnum::DISABLED)
    ->expressBatchCloseMethod(MerchantsExpressBatchCloseMethodEnum::TIMEINITIATED)
    ->expressBatchCloseTime('03:00:00')
    ->tinStatus(0)
    ->omniTokenEnabled(MerchantsOmniTokenEnabledEnum::DISABLED)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $merchantsController->putMerchantsId(
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
        "id": "p1_mer_00c66ace58ad2d376bb0067",
        "created": "2025-03-03 21:51:58.4016",
        "modified": "2025-03-03 22:56:04.3579",
        "creator": "p1_log_0067be40688861230a79682",
        "modifier": "p1_log_00c66acd69830f6a0d4718b",
        "lastActivity": "2025-03-03 21:51:58",
        "entity": "p1_ent_00c66acd8154446fc5567a3",
        "dba": "Colorado Blitz",
        "new": 0,
        "established": 20250226,
        "annualCCSales": 750000,
        "avgTicket": 15000,
        "amex": "",
        "discover": "",
        "mcc": "7997",
        "status": 2,
        "boarded": 20250303,
        "inactive": 0,
        "frozen": 0,
        "environment": "ecommerce",
        "visaMvv": "",
        "chargebackNotificationEmail": "",
        "statusReason": "noResponse",
        "totalApprovedSales": 0,
        "autoBoarded": 1,
        "saqType": "SAQ-A",
        "saqDate": 20250303,
        "qsa": "",
        "letterStatus": 0,
        "letterDate": 20250303,
        "tcAttestation": 1,
        "visaDisclosure": 1,
        "disclosureIP": "67.174.101.19",
        "disclosureDate": 20250303,
        "accountClosureReasonCode": "",
        "accountClosureReasonDate": 20250303,
        "annualCCSaleVolume": 0,
        "annualACHSaleVolume": 0,
        "riskLevel": "restricted",
        "creditRatio": 0,
        "creditTimeliness": 0,
        "chargebackRatio": 0,
        "ndxDays": 0,
        "ndxPercentage": 0,
        "advancedBilling": 0,
        "locationType": 77,
        "percentKeyed": 0,
        "totalVolume": 0,
        "percentEcomm": 0,
        "seasonal": 0,
        "amexVolume": 0,
        "incrementalAuthSupported": 0,
        "tmxSessionId": "6395015c-b0cc-45ba-abdc-aaf17123a4db",
        "percentBusiness": 0,
        "applePayActive": 0,
        "applePayStatus": "",
        "googlePayActive": 1,
        "passTokenEnabled": 0,
        "naics": "11",
        "naicsDescription": "",
        "expressBatchCloseMethod": "TimeInitiated",
        "expressBatchCloseTime": ""
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


# Delete Merchants Id

Delete a Merchant. A Merchant is an organization that processes credit card payments. Each Merchant is associated with an Entity.

```php
function deleteMerchantsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): MerchantsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, also known as the Merchant ID (MID). |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`MerchantsResponseResult`](../../doc/models/merchants-response-result.md)

## Example Usage

```php
$id = 'p1_mer_00c6b12d04ac280ed694323';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $merchantsController->deleteMerchantsId(
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
        "id": "p1_mer_00c66ace58ad2d376bb0067",
        "created": "2025-03-03 21:51:58.4016",
        "modified": "2025-03-03 22:56:04.3579",
        "creator": "p1_log_0067be40688861230a79682",
        "modifier": "p1_log_00c66acd69830f6a0d4718b",
        "lastActivity": "2025-03-03 21:51:58",
        "entity": "p1_ent_00c66acd8154446fc5567a3",
        "dba": "Colorado Blitz",
        "new": 0,
        "established": 20250226,
        "annualCCSales": 750000,
        "avgTicket": 15000,
        "amex": "",
        "discover": "",
        "mcc": "7997",
        "status": 2,
        "boarded": 20250303,
        "inactive": 0,
        "frozen": 0,
        "environment": "ecommerce",
        "visaMvv": "",
        "chargebackNotificationEmail": "",
        "statusReason": "noResponse",
        "totalApprovedSales": 0,
        "autoBoarded": 1,
        "saqType": "SAQ-A",
        "saqDate": 20250303,
        "qsa": "",
        "letterStatus": 0,
        "letterDate": 20250303,
        "tcAttestation": 1,
        "visaDisclosure": 1,
        "disclosureIP": "67.174.101.19",
        "disclosureDate": 20250303,
        "accountClosureReasonCode": "",
        "accountClosureReasonDate": 20250303,
        "annualCCSaleVolume": 0,
        "annualACHSaleVolume": 0,
        "riskLevel": "restricted",
        "creditRatio": 0,
        "creditTimeliness": 0,
        "chargebackRatio": 0,
        "ndxDays": 0,
        "ndxPercentage": 0,
        "advancedBilling": 0,
        "locationType": 77,
        "percentKeyed": 0,
        "totalVolume": 0,
        "percentEcomm": 0,
        "seasonal": 0,
        "amexVolume": 0,
        "incrementalAuthSupported": 0,
        "tmxSessionId": "6395015c-b0cc-45ba-abdc-aaf17123a4db",
        "percentBusiness": 0,
        "applePayActive": 0,
        "applePayStatus": "",
        "googlePayActive": 1,
        "passTokenEnabled": 0,
        "naics": "11",
        "naicsDescription": "",
        "expressBatchCloseMethod": "TimeInitiated",
        "expressBatchCloseTime": ""
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

