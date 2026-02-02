
# Invoices Post Request

## Structure

`InvoicesPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `string` | Required | The identifier of the Login of this invoice resource. | getLogin(): string | setLogin(string login): void |
| `merchant` | `?string` | Required | The identifier of the Merchant of this invoice resource. | getMerchant(): ?string | setMerchant(?string merchant): void |
| `customer` | string\|null\|[CustomersPostRequest](../../doc/models/customers-post-request.md)\|null | Optional | The identifier of the Customer of this invoice resource. | getCustomer(): | setCustomer( customer): void |
| `subscription` | `?string` | Required | The identifier of the Subscription of this invoice resource. | getSubscription(): ?string | setSubscription(?string subscription): void |
| `number` | `string` | Required | The invoice number. | getNumber(): string | setNumber(string number): void |
| `allowedPaymentMethods` | `?string` | Optional | The methods of payment allowed for this invoice. This field accepts multiple options concatenated into a<br>single string with a pipe (\|) separator between each option.<br><br><details><br><summary>Allowed Values</summary><br>- `Amex` - **American Express**<br>- `Visa` - **Visa card**<br>- `Mc` - **MasterCard**<br>- `Diners` - **Diners Club card**<br>- `Discover` - **Discover card**<br>- `PayPal` - **PayPal payment method**<br>- `Debit` - **Debit card**<br>- `Checking` - **Checking account**<br>- `Savings` - **Savings account**<br>- `CorpChecking` - **Corporate checking account**<br>- `CorpSavings` - **Corporate savings account**<br>- `Gift` - **Gift card**<br>- `EBT` - **Electronic Benefits Transfer**<br>- `WIC` - **Women, Infants, and Children program**<br>- `Accel` - **Accel network**<br>- `ATH` - **ATH network**<br>- `AFFN` - **Armed Forces Financial Network**<br>- `Culiance` - **Culiance network**<br>- `Interlink` - **Interlink network**<br>- `Jeanie` - **Jeanie network**<br>- `Maestro` - **Maestro card**<br>- `NYCE` - **NYCE network**<br>- `Pulse` - **Pulse network**<br>- `Shazam` - **Shazam network**<br>- `Star` - **Star network**<br>- `Interac` - **Interac network**<br>- `Omnitoken` - **Omnitoken**<br></details><br> | getAllowedPaymentMethods(): ?string | setAllowedPaymentMethods(?string allowedPaymentMethods): void |
| `title` | `?string` | Optional | The title of the invoice. | getTitle(): ?string | setTitle(?string title): void |
| `message` | `?string` | Optional | The message that will be sent with the invoice. | getMessage(): ?string | setMessage(?string message): void |
| `total` | `?int` | Optional | The total amount for this invoice.<br><br>**Default**: `0` | getTotal(): ?int | setTotal(?int total): void |
| `tax` | `?int` | Optional | The tax amount for this invoice. | getTax(): ?int | setTax(?int tax): void |
| `discount` | `?int` | Optional | The discount amount applied to this invoice. | getDiscount(): ?int | setDiscount(?int discount): void |
| `dueDate` | `?int` | Optional | The date the invoice is due. | getDueDate(): ?int | setDueDate(?int dueDate): void |
| `expirationDate` | `?int` | Optional | The date the invoice is due. | getExpirationDate(): ?int | setExpirationDate(?int expirationDate): void |
| `sendOn` | `?int` | Optional | The date to send this invoice. | getSendOn(): ?int | setSendOn(?int sendOn): void |
| `status` | [`string(InvoiceStatusEnum)`](../../doc/models/invoice-status-enum.md) | Required | The current status of the transaction.<br><br><details><br><summary>Valid Values</summary><br> - `pending` - **Pending**<br> - `cancelled` - **Cancelled**<br> - `expired` - **Expired**<br> - `viewed` - **Viewed**<br> - `paid` - **Paid**<br> - `confirmed` - **Confirmed**<br> - `refunded` - **Refunded**       <br> - `rejected` - **Rejected**<br> </details><br> | getStatus(): string | setStatus(string status): void |
| `emailStatus` | [`?string(InvoicesEmailStatusEnum)`](../../doc/models/invoices-email-status-enum.md) | Optional | The current status of the invoice.<br><br><details><br><summary>Valid Values</summary><br>- `send` - **Updated email status to indicate the invoice is ready to be sent to the customer.**<br>- `sent` - **Updated email status once the invoice is sent to the customer.**<br>- `pending` - **Updated email status pending**<br>  </details><br> | getEmailStatus(): ?string | setEmailStatus(?string emailStatus): void |
| `emails` | `?string` | Optional | The email addresses to send the invoice to. | getEmails(): ?string | setEmails(?string emails): void |
| `type` | [`?string(InvoiceTypeEnum)`](../../doc/models/invoice-type-enum.md) | Optional | The type of invoice.<br><br><details><br><summary>Valid Values</summary><br>- `single` - **A single-use invoice.**<br>- `multiUse` - **A static, reusable invoice. (Payment Page.)**<br>- `recurring` - **A subscription-based invoice.**<br></details><br>**Default**: `InvoiceTypeEnum::ONEOFF`<br> | getType(): ?string | setType(?string type): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `invoiceLineItems` | [`?(InvoiceLineItemsPostRequest[])`](../../doc/models/invoice-line-items-post-request.md) | Optional | - | getInvoiceLineItems(): ?array | setInvoiceLineItems(?array invoiceLineItems): void |

## Example (as JSON)

```json
{
  "login": "t1_log_0092b50e1112b18e41d521e",
  "merchant": "t1_mer_008e7f511d5c5a2d2fade82",
  "customer": "t1_cus_00b39e97b2110ba9075dfda",
  "subscription": "t1_sbn_00fc6fxx7a871bbce685897",
  "title": "Test Invoice Alert",
  "number": "9999888888",
  "message": "Testing invoice alerts",
  "emails": "erik@test.com",
  "total": 100,
  "tax": 1000,
  "discount": 1000,
  "type": "single",
  "status": "paid",
  "dueDate": 20250217,
  "expirationDate": 20250217,
  "sendOn": 20250217,
  "emailStatus": "pending",
  "inactive": 0,
  "frozen": 0,
  "allowedPaymentMethods": "visa"
}
```

