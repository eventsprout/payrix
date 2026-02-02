
# Vas Efe Offers Response

## Structure

`VasEfeOffersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `offerId` | `?string` | Optional | Id of the offer | getOfferId(): ?string | setOfferId(?string offerId): void |
| `expiry` | `?string` | Optional | Expire date of offer<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getExpiry(): ?string | setExpiry(?string expiry): void |
| `entity` | `?string` | Optional | EntityId for merchant | getEntity(): ?string | setEntity(?string entity): void |
| `mid` | `?string` | Optional | MID | getMid(): ?string | setMid(?string mid): void |
| `primaryContactEmail` | `?string` | Optional | Primary point of contacts email | getPrimaryContactEmail(): ?string | setPrimaryContactEmail(?string primaryContactEmail): void |
| `merchantLenderId` | `?string` | Optional | This refers to the partner product association | getMerchantLenderId(): ?string | setMerchantLenderId(?string merchantLenderId): void |
| `vendorName` | `?string` | Optional | Vendor associated with the product | getVendorName(): ?string | setVendorName(?string vendorName): void |
| `offerDate` | `?string` | Optional | Date of provided offer<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getOfferDate(): ?string | setOfferDate(?string offerDate): void |
| `totalApprovedAmount` | `?string` | Optional | Amount approved for | getTotalApprovedAmount(): ?string | setTotalApprovedAmount(?string totalApprovedAmount): void |
| `feeAmount` | `?string` | Optional | Fee amount charged | getFeeAmount(): ?string | setFeeAmount(?string feeAmount): void |
| `originationFee` | `?string` | Optional | Refers to fee charged by a lender to process a new loan application. | getOriginationFee(): ?string | setOriginationFee(?string originationFee): void |
| `offerUrl` | `?string` | Optional | Url of corresponding offer | getOfferUrl(): ?string | setOfferUrl(?string offerUrl): void |
| `productName` | `?string` | Optional | Name associated with the product | getProductName(): ?string | setProductName(?string productName): void |
| `productLongDescription` | `?string` | Optional | Long description of the product. | getProductLongDescription(): ?string | setProductLongDescription(?string productLongDescription): void |
| `acquirePlatform` | `?string` | Optional | To identify whether a partner belongs to Core or VAP platforms. | getAcquirePlatform(): ?string | setAcquirePlatform(?string acquirePlatform): void |
| `prequalificationSentDate` | `?string` | Optional | The date when preliminary information is submitted for vendor assessment to determine merchant eligibility to receive the cash advance.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getPrequalificationSentDate(): ?string | setPrequalificationSentDate(?string prequalificationSentDate): void |
| `prequalificationReceivedDate` | `?string` | Optional | Date when the vendor provides the preQualification status of a given sub-merchant.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getPrequalificationReceivedDate(): ?string | setPrequalificationReceivedDate(?string prequalificationReceivedDate): void |
| `isMerchantPrequalified` | [`?int(VasEfeOffersIsMerchantPrequalifiedEnum)`](../../doc/models/vas-efe-offers-is-merchant-prequalified-enum.md) | Optional | A flag that indicates if a merchant meets predetermined vendor criteria to receive cash advance funding. | getIsMerchantPrequalified(): ?int | setIsMerchantPrequalified(?int isMerchantPrequalified): void |
| `appliedDate` | `?string` | Optional | Date when merchant submitted an application to receive cash advance from a vendor. Date should be past or present in the format YYYY-MM-DD.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getAppliedDate(): ?string | setAppliedDate(?string appliedDate): void |
| `offerStatus` | [`?string(VasEfeOffersOfferStatusEnum)`](../../doc/models/vas-efe-offers-offer-status-enum.md) | Optional | Indicates the status of a cash advance application submitted by the sub-merchant | getOfferStatus(): ?string | setOfferStatus(?string offerStatus): void |
| `productCode` | `?string` | Optional | Type of product which partner has enrolled into. | getProductCode(): ?string | setProductCode(?string productCode): void |
| `startDate` | `?string` | Optional | Date when sub merchant started re-paying cash advance.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getStartDate(): ?string | setStartDate(?string startDate): void |
| `endDate` | `?string` | Optional | Date when sub merchant is expected to complete the repayment of cash advance.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getEndDate(): ?string | setEndDate(?string endDate): void |
| `splitFundingCap` | `?string` | Optional | Maximum amount to be repaid by sub merchant. | getSplitFundingCap(): ?string | setSplitFundingCap(?string splitFundingCap): void |
| `splitFundingRate` | `?string` | Optional | Repayment percentage as defined by lender. | getSplitFundingRate(): ?string | setSplitFundingRate(?string splitFundingRate): void |
| `dailyFundingMaxLimit` | `?string` | Optional | Maximum daily repayment limit as defined by lender. | getDailyFundingMaxLimit(): ?string | setDailyFundingMaxLimit(?string dailyFundingMaxLimit): void |
| `splitFundingAmount` | `?string` | Optional | Split Funding Amount refers to the cash advance provided to the merchant. | getSplitFundingAmount(): ?string | setSplitFundingAmount(?string splitFundingAmount): void |
| `optInDate` | `?string` | Optional | The date when the merchant has opted in.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getOptInDate(): ?string | setOptInDate(?string optInDate): void |
| `splitSettlementEnabled` | [`?int(VasEfeOffersSplitSettlementEnabledEnum)`](../../doc/models/vas-efe-offers-split-settlement-enabled-enum.md) | Optional | Indicates if split funding settlement allowed for merchant. | getSplitSettlementEnabled(): ?int | setSplitSettlementEnabled(?int splitSettlementEnabled): void |

## Example (as JSON)

```json
{
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

