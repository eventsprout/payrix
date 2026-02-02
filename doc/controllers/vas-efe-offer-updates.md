# VAS Efe Offer Updates

```php
$vASEfeOfferUpdatesController = $client->getVASEfeOfferUpdatesController();
```

## Class Name

`VASEfeOfferUpdatesController`

## Methods

* [Get Vas Efe Offer Updates Id](../../doc/controllers/vas-efe-offer-updates.md#get-vas-efe-offer-updates-id)
* [Get Vas Efe Offer Updates](../../doc/controllers/vas-efe-offer-updates.md#get-vas-efe-offer-updates)


# Get Vas Efe Offer Updates Id

Query a vasEfeOfferUpdates.

```php
function getVasEfeOfferUpdatesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): VasEfeOfferUpdatesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`VasEfeOfferUpdatesResponseResult`](../../doc/models/vas-efe-offer-updates-response-result.md)

## Example Usage

```php
$id = 't1_eou_67fae4eb8a2b4faed000ed6';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $vASEfeOfferUpdatesController->getVasEfeOfferUpdatesId(
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
        "id": "t1_eou_67fae4eb8a2b4faed000ed6",
        "created": "2025-07-18 15:46:09.6400",
        "modified": "2025-07-18 15:46:09.6400",
        "creator": "t1_log_5c000e990c7a922100d4f00",
        "modifier": "t1_log_5c000e990c7a922100d4f00",
        "notificationId": "",
        "mid": "4445061757000",
        "merchantName": "Payrix Pro Merchant",
        "merchantLenderId": "",
        "vendorId": "",
        "vendorName": "Parafin",
        "vendorAccountId": "",
        "offerId": "c00ef79c-f024-4254-ae17-c67a2e691d00",
        "offerUrl": "https://test-capital.parafin.com?token=dc00ef79c-f000-0000-ae17-c67a2e001d00",
        "primaryContactEmail": "johnf@flobal.com",
        "productCode": "",
        "productShortDescription": "flex loan",
        "productLongDescription": "",
        "acquirePlatform": "",
        "prequalificationSentDate": null,
        "prequalificationReceivedDate": null,
        "merchantPrequalified": 0,
        "appliedDate": null,
        "originationFee": "",
        "applicationStatus": "RECEIVED",
        "paymentStartDate": null,
        "paymentEndDate": null,
        "splitFundingCap": "",
        "splitFundingRate": "",
        "dailyFundingMaxLimit": "",
        "outstandingAmount": "",
        "infoSource": "OFFER_FILE",
        "status": "ACTIVE",
        "rawPayload": "{\"type\": \"offer.received\", \"event\": \"offer.received\", \"offer\": {\"expiry\": \"2024-04-18\", \"offerId\": \"c00ef79c-f024-4254-ae17-c67a2e691d00\", \"lastName\": \"Amir AR2\", \"offerUrl\": \"https://test-capital.parafin.com?token=dc00ef79c-f000-0000-ae17-c67a2e001d00\", \"createdAt\": \"2024-12-03 22:35:17.908024+00:00\", \"feeAmount\": \"700\", \"firstName\": \"John\", \"productName\": \"flex loan\", \"merchantName\": \"Payrix Pro Merchant\", \"providerName\": \"Parafin\", \"applicationStatus\": \"RECEIVED\", \"primaryContactEmail\": \"johnf@flobal.com\", \"totalApprovedAmount\": \"70000\", \"additionalOfferDetails\": \"{'id': 'capital_product_offer_id_3b5b006', 'date': '2024-12-03', 'active': True, 'offer_url': 'https://test-capital.parafin.com?token=dc00ef79c-f000-0000-ae17-c67a2e001d00', 'business_id': 'business_c888d878-56a5-4b6c-aba9-f2ea910f2419', 'product_type': 'flex_loan', 'is_marketable': True, 'max_fee_amount': 1250.0, 'expiration_date': '2029-12-03', 'max_payment_rate': 0.14, 'max_fee_multiplier': 0.125, 'business_parafin_id': 'business_c888d878-56a5-4b6c-aba9-f2ea910f2419', 'business_external_id': '8995ef26-49dc-42d6-95bf-86aefb4b50db', 'total_approved_amount': 10000.0, 'max_fee_discount_amount': 0.0, 'term_loan_offer_details': None}\"}, \"fileName\": \"Offer_File_parafin_0523_2.csv\", \"platform\": \"VCORE\", \"eventName\": \"EmbeddedFinance\", \"offerType\": \"PARAFIN\", \"lineNumber\": \"3\", \"merchantId\": \"4445069598209\", \"eventSource\": \"file-collector-service-offer\", \"messageAttributes\": {\"type\": {\"dataType\": \"String\", \"stringValue\": \"EmbeddedFinance\", \"binaryListValues\": [], \"stringListValues\": []}, \"subject\": {\"dataType\": \"String\", \"stringValue\": \"EmbeddedFinance\", \"binaryListValues\": [], \"stringListValues\": []}, \"_datadog\": {\"dataType\": \"Binary\", \"binaryValue\": \"eyJ4LWRhdGFkb2ctdHJhY2UtaWQiOiIxNDI4MjY0OTcxMTU1MTY5NzUyIiwieC1kYXRhZG9nLXBhcmVudC1pZCI6IjIzMjQ4MzY1NDg4NTYyMDc5MzMiLCJ4LWRhdGFkb2ctc2FtcGxpbmctcHJpb3JpdHkiOiIxIiwieC1kYXRhZG9nLXRhZ3MiOiJfZGQucC50aWQ9NjgyZjcxMzgwMDAwMDAwMCxfZGQucC5kbT0tMCIsInRyYWNlcGFyZW50IjoiMDAtNjgyZjcxMzgwMDAwMDAwMDEzZDIzNzZjOGFkNjYxZDgtMjA0MzdhODYwZjZiNWEzZC0wMSIsInRyYWNlc3RhdGUiOiJkZD10LmRtOi0wO3QudGlkOjY4MmY3MTM4MDAwMDAwMDA7czoxO3A6MjA0MzdhODYwZjZiNWEzZCJ9\", \"binaryListValues\": [], \"stringListValues\": []}, \"eventSource\": {\"dataType\": \"String\", \"stringValue\": \"file-collector-service-offer\", \"binaryListValues\": [], \"stringListValues\": []}}}",
        "vasEfeOffer": "t1_veo_683075500a4f491543b000f"
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


# Get Vas Efe Offer Updates

Query a vasEfeOfferUpdates.

```php
function getVasEfeOfferUpdates(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): VasEfeOfferUpdatesResponseResult
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

[`VasEfeOfferUpdatesResponseResult`](../../doc/models/vas-efe-offer-updates-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $vASEfeOfferUpdatesController->getVasEfeOfferUpdates(
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
        "id": "t1_eou_67fae4eb8a2b4faed000ed6",
        "created": "2025-07-18 15:46:09.6400",
        "modified": "2025-07-18 15:46:09.6400",
        "creator": "t1_log_5c000e990c7a922100d4f00",
        "modifier": "t1_log_5c000e990c7a922100d4f00",
        "notificationId": "",
        "mid": "4445061757000",
        "merchantName": "Payrix Pro Merchant",
        "merchantLenderId": "",
        "vendorId": "",
        "vendorName": "Parafin",
        "vendorAccountId": "",
        "offerId": "c00ef79c-f024-4254-ae17-c67a2e691d00",
        "offerUrl": "https://test-capital.parafin.com?token=dc00ef79c-f000-0000-ae17-c67a2e001d00",
        "primaryContactEmail": "johnf@flobal.com",
        "productCode": "",
        "productShortDescription": "flex loan",
        "productLongDescription": "",
        "acquirePlatform": "",
        "prequalificationSentDate": null,
        "prequalificationReceivedDate": null,
        "merchantPrequalified": 0,
        "appliedDate": null,
        "originationFee": "",
        "applicationStatus": "RECEIVED",
        "paymentStartDate": null,
        "paymentEndDate": null,
        "splitFundingCap": "",
        "splitFundingRate": "",
        "dailyFundingMaxLimit": "",
        "outstandingAmount": "",
        "infoSource": "OFFER_FILE",
        "status": "ACTIVE",
        "rawPayload": "{\"type\": \"offer.received\", \"event\": \"offer.received\", \"offer\": {\"expiry\": \"2024-04-18\", \"offerId\": \"c00ef79c-f024-4254-ae17-c67a2e691d00\", \"lastName\": \"Amir AR2\", \"offerUrl\": \"https://test-capital.parafin.com?token=dc00ef79c-f000-0000-ae17-c67a2e001d00\", \"createdAt\": \"2024-12-03 22:35:17.908024+00:00\", \"feeAmount\": \"700\", \"firstName\": \"John\", \"productName\": \"flex loan\", \"merchantName\": \"Payrix Pro Merchant\", \"providerName\": \"Parafin\", \"applicationStatus\": \"RECEIVED\", \"primaryContactEmail\": \"johnf@flobal.com\", \"totalApprovedAmount\": \"70000\", \"additionalOfferDetails\": \"{'id': 'capital_product_offer_id_3b5b006', 'date': '2024-12-03', 'active': True, 'offer_url': 'https://test-capital.parafin.com?token=dc00ef79c-f000-0000-ae17-c67a2e001d00', 'business_id': 'business_c888d878-56a5-4b6c-aba9-f2ea910f2419', 'product_type': 'flex_loan', 'is_marketable': True, 'max_fee_amount': 1250.0, 'expiration_date': '2029-12-03', 'max_payment_rate': 0.14, 'max_fee_multiplier': 0.125, 'business_parafin_id': 'business_c888d878-56a5-4b6c-aba9-f2ea910f2419', 'business_external_id': '8995ef26-49dc-42d6-95bf-86aefb4b50db', 'total_approved_amount': 10000.0, 'max_fee_discount_amount': 0.0, 'term_loan_offer_details': None}\"}, \"fileName\": \"Offer_File_parafin_0523_2.csv\", \"platform\": \"VCORE\", \"eventName\": \"EmbeddedFinance\", \"offerType\": \"PARAFIN\", \"lineNumber\": \"3\", \"merchantId\": \"4445069598209\", \"eventSource\": \"file-collector-service-offer\", \"messageAttributes\": {\"type\": {\"dataType\": \"String\", \"stringValue\": \"EmbeddedFinance\", \"binaryListValues\": [], \"stringListValues\": []}, \"subject\": {\"dataType\": \"String\", \"stringValue\": \"EmbeddedFinance\", \"binaryListValues\": [], \"stringListValues\": []}, \"_datadog\": {\"dataType\": \"Binary\", \"binaryValue\": \"eyJ4LWRhdGFkb2ctdHJhY2UtaWQiOiIxNDI4MjY0OTcxMTU1MTY5NzUyIiwieC1kYXRhZG9nLXBhcmVudC1pZCI6IjIzMjQ4MzY1NDg4NTYyMDc5MzMiLCJ4LWRhdGFkb2ctc2FtcGxpbmctcHJpb3JpdHkiOiIxIiwieC1kYXRhZG9nLXRhZ3MiOiJfZGQucC50aWQ9NjgyZjcxMzgwMDAwMDAwMCxfZGQucC5kbT0tMCIsInRyYWNlcGFyZW50IjoiMDAtNjgyZjcxMzgwMDAwMDAwMDEzZDIzNzZjOGFkNjYxZDgtMjA0MzdhODYwZjZiNWEzZC0wMSIsInRyYWNlc3RhdGUiOiJkZD10LmRtOi0wO3QudGlkOjY4MmY3MTM4MDAwMDAwMDA7czoxO3A6MjA0MzdhODYwZjZiNWEzZCJ9\", \"binaryListValues\": [], \"stringListValues\": []}, \"eventSource\": {\"dataType\": \"String\", \"stringValue\": \"file-collector-service-offer\", \"binaryListValues\": [], \"stringListValues\": []}}}",
        "vasEfeOffer": "t1_veo_683075500a4f491543b000f"
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

