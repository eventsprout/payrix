
# Vas Efe Offer Updates Response

## Structure

`VasEfeOfferUpdatesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `notificationId` | `?string` | Optional | Update event notification ID. | getNotificationId(): ?string | setNotificationId(?string notificationId): void |
| `mid` | `?string` | Optional | MID of the merchant. | getMid(): ?string | setMid(?string mid): void |
| `merchantName` | `?string` | Optional | Name of the merchant | getMerchantName(): ?string | setMerchantName(?string merchantName): void |
| `merchantLenderId` | `?string` | Optional | This refers to the partner product association | getMerchantLenderId(): ?string | setMerchantLenderId(?string merchantLenderId): void |
| `vendorId` | `?string` | Optional | ID of Vendor associated with the product | getVendorId(): ?string | setVendorId(?string vendorId): void |
| `vendorName` | `?string` | Optional | Vendor associated with the product | getVendorName(): ?string | setVendorName(?string vendorName): void |
| `vendorAccountId` | `?string` | Optional | Account ID of the product vendor | getVendorAccountId(): ?string | setVendorAccountId(?string vendorAccountId): void |
| `offerId` | `?string` | Optional | Amount approved for | getOfferId(): ?string | setOfferId(?string offerId): void |
| `offerUrl` | `?string` | Optional | Url of corresponding offer | getOfferUrl(): ?string | setOfferUrl(?string offerUrl): void |
| `primaryContactEmail` | `?string` | Optional | Primary point of contacts email | getPrimaryContactEmail(): ?string | setPrimaryContactEmail(?string primaryContactEmail): void |
| `productCode` | `?string` | Optional | Type of product which partner has enrolled into. | getProductCode(): ?string | setProductCode(?string productCode): void |
| `productShortDescription` | `?string` | Optional | Short description of the product. | getProductShortDescription(): ?string | setProductShortDescription(?string productShortDescription): void |
| `productLongDescription` | `?string` | Optional | Long description of the product. | getProductLongDescription(): ?string | setProductLongDescription(?string productLongDescription): void |
| `acquirePlatform` | `?string` | Optional | To identify whether a partner belongs to Core or VAP platforms. | getAcquirePlatform(): ?string | setAcquirePlatform(?string acquirePlatform): void |
| `prequalificationSentDate` | `?string` | Optional | The date when preliminary information is submitted for vendor assessment to determine merchant eligibility to receive the cash advance.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{2}$` | getPrequalificationSentDate(): ?string | setPrequalificationSentDate(?string prequalificationSentDate): void |
| `prequalificationReceivedDate` | `?string` | Optional | Date when the vendor provides the preQualification status of a given sub-merchant.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{2}$` | getPrequalificationReceivedDate(): ?string | setPrequalificationReceivedDate(?string prequalificationReceivedDate): void |
| `merchantPrequalified` | [`?int(VasEfeOffersMerchantPrequalifiedEnum)`](../../doc/models/vas-efe-offers-merchant-prequalified-enum.md) | Optional | A flag that indicates if a merchant meets predetermined vendor criteria to receive cash advance funding. | getMerchantPrequalified(): ?int | setMerchantPrequalified(?int merchantPrequalified): void |
| `appliedDate` | `?string` | Optional | Date when merchant submitted an application to receive cash advance from a vendor. Date should be past or present in the format YYYY-MM-DD.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{2}$` | getAppliedDate(): ?string | setAppliedDate(?string appliedDate): void |
| `originationFee` | `?string` | Optional | Refers to fee charged by a lender to process a new loan application. | getOriginationFee(): ?string | setOriginationFee(?string originationFee): void |
| `applicationStatus` | [`?string(VasEfeOfferUpdatesApplicationStatusEnum)`](../../doc/models/vas-efe-offer-updates-application-status-enum.md) | Optional | Indicates the status of a cash advance application submitted by the sub-merchant | getApplicationStatus(): ?string | setApplicationStatus(?string applicationStatus): void |
| `paymentStartDate` | `?string` | Optional | Date when the merchant is expected to start loan payment<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{2}$` | getPaymentStartDate(): ?string | setPaymentStartDate(?string paymentStartDate): void |
| `paymentEndDate` | `?string` | Optional | Date when the merchant is expected to complete the loan payment<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{2}$` | getPaymentEndDate(): ?string | setPaymentEndDate(?string paymentEndDate): void |
| `splitFundingCap` | `?string` | Optional | Maximum amount to be repaid by sub merchant. | getSplitFundingCap(): ?string | setSplitFundingCap(?string splitFundingCap): void |
| `splitFundingRate` | `?string` | Optional | Repayment percentage as defined by lender. | getSplitFundingRate(): ?string | setSplitFundingRate(?string splitFundingRate): void |
| `dailyFundingMaxLimit` | `?string` | Optional | Maximum daily repayment limit as defined by lender. | getDailyFundingMaxLimit(): ?string | setDailyFundingMaxLimit(?string dailyFundingMaxLimit): void |
| `outstandingAmount` | `?string` | Optional | Amount remaining to be paid by the merchant on the loan | getOutstandingAmount(): ?string | setOutstandingAmount(?string outstandingAmount): void |
| `infoSource` | [`?string(VasEfeOfferUpdatesInfoSourceEnum)`](../../doc/models/vas-efe-offer-updates-info-source-enum.md) | Optional | Indicates the source of the update | getInfoSource(): ?string | setInfoSource(?string infoSource): void |
| `status` | [`?string(VasEfeOfferUpdatesStatusEnum)`](../../doc/models/vas-efe-offer-updates-status-enum.md) | Optional | Indicates the status of a cash advance application submitted by the sub-merchant | getStatus(): ?string | setStatus(?string status): void |
| `rawPayload` | `?string` | Optional | Dump of the data received for update. This field is a serialized JSON. | getRawPayload(): ?string | setRawPayload(?string rawPayload): void |
| `vasEfeOffer` | `?string` | Optional | Id of the offer | getVasEfeOffer(): ?string | setVasEfeOffer(?string vasEfeOffer): void |

## Example (as JSON)

```json
{
  "id": "id6",
  "created": "created6",
  "modified": "modified4",
  "creator": "String5",
  "modifier": "modifier0"
}
```

