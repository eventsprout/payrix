
# Getting Started with Payrix

## Building

The generated code has dependencies over external libraries like UniRest and JsonMapper. JsonMapper requires docblock annotations like `@var`, `@maps`, and `@factory` to map JSON responses with our class definitions. Hence the docblocks in generated code cannot be disabled by deactivating the PHP configurations like `opcache.save_comments`. These dependencies are defined in the `composer.json` file that comes with the SDK. To resolve these dependencies, we use the Composer package manager which requires PHP greater than or equal to 7.2 installed in your system. Visit [https://getcomposer.org/download/](https://getcomposer.org/download/) to download the installer file for Composer and run it in your system. Open command prompt and type `composer --version`. This should display the current version of the Composer installed if the installation was successful.

* Using command line, navigate to the directory containing the generated files (including `composer.json`) for the SDK.
* Run the command `composer install`. This should install all the required dependencies and create the `vendor` directory in your project directory.

![Building SDK - Step 1](https://apidocs.io/illustration/php?workspaceFolder=Payrix&step=installDependencies)

### Configuring CURL Certificate Path in php.ini

:information_source: **Note** This is for Windows users only.

CURL used to include a list of accepted CAs, but no longer bundles ANY CA certs. So by default it will reject all SSL certificates as unverifiable. You will have to get your CA's cert and point curl at it. The steps are as follows:

1. Download the certificate bundle (.pem file) from [https://curl.haxx.se/docs/caextract.html](https://curl.haxx.se/docs/caextract.html) on to your system.
2. Add curl.cainfo = "PATH_TO/cacert.pem" to your php.ini file located in your php installation. “PATH_TO” must be an absolute path containing the .pem file.

```
[curl]; A default value for the CURLOPT_CAINFO option. This is required to be an
; absolute path.
curl.cainfo = PATH_TO/cacert.pem
```

## Installation

The following section explains how to use the Payrix library in a new project.

### 1. Open Project in an IDE

Open an IDE for PHP like PhpStorm. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.

![Open project in PHPStorm - Step 1](https://apidocs.io/illustration/php?workspaceFolder=Payrix&step=openIDE)

Click on `Open` in PhpStorm to browse to your generated SDK directory and then click `OK`.

![Open project in PHPStorm - Step 2](https://apidocs.io/illustration/php?workspaceFolder=Payrix&step=openProject0)

### 2. Add a new Test Project

Create a new directory by right clicking on the solution name as shown below:

![Add a new project in PHPStorm - Step 1](https://apidocs.io/illustration/php?workspaceFolder=Payrix&step=createDirectory)

Name the directory as "test".

![Add a new project in PHPStorm - Step 2](https://apidocs.io/illustration/php?workspaceFolder=Payrix&step=nameDirectory)

Add a PHP file to this project.

![Add a new project in PHPStorm - Step 3](https://apidocs.io/illustration/php?workspaceFolder=Payrix&step=createFile)

Name it "testSDK".

![Add a new project in PHPStorm - Step 4](https://apidocs.io/illustration/php?workspaceFolder=Payrix&step=nameFile)

Depending on your project setup, you might need to include composer's autoloader in your PHP code to enable auto loading of classes.

```php
require_once "vendor/autoload.php";
```

It is important that the path inside require_once correctly points to the file `autoload.php` inside the vendor directory created during dependency installations.

![Add a new project in PHPStorm - Step 5](https://apidocs.io/illustration/php?workspaceFolder=Payrix&step=projectFiles)

After this you can add code to initialize the client library and acquire the instance of a Controller class. Sample code to initialize the client library and use the Controller methods is given in the subsequent sections.

### 3. Run the Test Project

To run your project you must set the Interpreter for your project. Interpreter is the PHP engine installed on your computer.

Open `Settings` from `File` menu.

![Run Test Project - Step 1](https://apidocs.io/illustration/php?workspaceFolder=Payrix&step=openSettings)

Select `PHP` from within `Languages & Frameworks`.

![Run Test Project - Step 2](https://apidocs.io/illustration/php?workspaceFolder=Payrix&step=setInterpreter0)

Browse for Interpreters near the `Interpreter` option and choose your interpreter.

![Run Test Project - Step 3](https://apidocs.io/illustration/php?workspaceFolder=Payrix&step=setInterpreter1)

Once the interpreter is selected, click `OK`.

![Run Test Project - Step 4](https://apidocs.io/illustration/php?workspaceFolder=Payrix&step=setInterpreter2)

To run your project, right click on your PHP file inside your Test project and click on `Run`.

![Run Test Project - Step 5](https://apidocs.io/illustration/php?workspaceFolder=Payrix&step=runProject)

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| serverUrl | `string` | *Default*: `'https://custom.payrix.com'` |
| environment | `Environment` | The API environment. <br> **Default: `Environment.SANDBOX`** |
| timeout | `int` | Timeout for API calls in seconds.<br>*Default*: `0` |
| enableRetries | `bool` | Whether to enable retries and backoff feature.<br>*Default*: `false` |
| numberOfRetries | `int` | The number of retries to make.<br>*Default*: `0` |
| retryInterval | `float` | The retry time interval between the endpoint calls.<br>*Default*: `1` |
| backOffFactor | `float` | Exponential backoff factor to increase interval between retries.<br>*Default*: `2` |
| maximumRetryWaitTime | `int` | The maximum wait time in seconds for overall retrying requests.<br>*Default*: `0` |
| retryOnTimeout | `bool` | Whether to retry on request timeout.<br>*Default*: `true` |
| httpStatusCodesToRetry | `array` | Http status codes to retry against.<br>*Default*: `408, 413, 429, 500, 502, 503, 504, 521, 522, 524, 408, 413, 429, 500, 502, 503, 504, 521, 522, 524` |
| httpMethodsToRetry | `array` | Http methods to retry against.<br>*Default*: `'GET', 'PUT', 'GET', 'PUT'` |
| proxyConfiguration | [`ProxyConfigurationBuilder`](doc/proxy-configuration-builder.md) | Represents the proxy configurations for API calls |
| apiKeyCredentials | [`ApiKeyCredentials`](doc/auth/custom-header-signature.md) | The Credentials Setter for Custom Header Signature |
| sessionKeyCredentials | [`SessionKeyCredentials`](doc/auth/custom-header-signature-1.md) | The Credentials Setter for Custom Header Signature |
| txnSessionKeyCredentials | [`TxnSessionKeyCredentials`](doc/auth/custom-header-signature-2.md) | The Credentials Setter for Custom Header Signature |
| usernameCredentials | [`UsernameCredentials`](doc/auth/custom-header-signature-3.md) | The Credentials Setter for Custom Header Signature |
| passwordCredentials | [`PasswordCredentials`](doc/auth/custom-header-signature-4.md) | The Credentials Setter for Custom Header Signature |

The API client can be initialized as follows:

```php
use PayrixLib\Environment;
use PayrixLib\Authentication\ApiKeyCredentialsBuilder;
use PayrixLib\Authentication\SessionKeyCredentialsBuilder;
use PayrixLib\Authentication\TxnSessionKeyCredentialsBuilder;
use PayrixLib\Authentication\UsernameCredentialsBuilder;
use PayrixLib\Authentication\PasswordCredentialsBuilder;
use PayrixLib\PayrixClientBuilder;

$client = PayrixClientBuilder::init()
    ->apiKeyCredentials(
        ApiKeyCredentialsBuilder::init(
            'APIKEY'
        )
    )
    ->sessionKeyCredentials(
        SessionKeyCredentialsBuilder::init(
            'SESSIONKEY'
        )
    )
    ->txnSessionKeyCredentials(
        TxnSessionKeyCredentialsBuilder::init(
            'TXNSESSIONKEY'
        )
    )
    ->usernameCredentials(
        UsernameCredentialsBuilder::init(
            'USERNAME'
        )
    )
    ->passwordCredentials(
        PasswordCredentialsBuilder::init(
            'PASSWORD'
        )
    )
    ->environment(Environment::SANDBOX)
    ->serverUrl('https://custom.payrix.com')
    ->build();
```

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| sandbox | **Default** |
| canada sandbox | - |
| custom | - |

## Authorization

This API uses the following authentication schemes.

* [`apiKey (Custom Header Signature)`](doc/auth/custom-header-signature.md)
* [`sessionKey (Custom Header Signature)`](doc/auth/custom-header-signature-1.md)
* [`txnSessionKey (Custom Header Signature)`](doc/auth/custom-header-signature-2.md)
* [`username (Custom Header Signature)`](doc/auth/custom-header-signature-3.md)
* [`password (Custom Header Signature)`](doc/auth/custom-header-signature-4.md)

## List of APIs

* [API Keys](doc/controllers/api-keys.md)
* [Apple Domains](doc/controllers/apple-domains.md)
* [Apple Domains Mass Enablement](doc/controllers/apple-domains-mass-enablement.md)
* [Accounts Verifications](doc/controllers/accounts-verifications.md)
* [Aggregation Result Groups](doc/controllers/aggregation-result-groups.md)
* [Aggregation Results](doc/controllers/aggregation-results.md)
* [Alert Actions](doc/controllers/alert-actions.md)
* [Alert Triggers](doc/controllers/alert-triggers.md)
* [Authentication Tokens](doc/controllers/authentication-tokens.md)
* [Batches Settlements](doc/controllers/batches-settlements.md)
* [Billing Modifiers](doc/controllers/billing-modifiers.md)
* [Billing Events](doc/controllers/billing-events.md)
* [Change Requests](doc/controllers/change-requests.md)
* [Chargeback Documents](doc/controllers/chargeback-documents.md)
* [Chargeback Message Results](doc/controllers/chargeback-message-results.md)
* [Chargeback Messages](doc/controllers/chargeback-messages.md)
* [Chargeback Statuses](doc/controllers/chargeback-statuses.md)
* [Confirmation Codes](doc/controllers/confirmation-codes.md)
* [Decision Actions](doc/controllers/decision-actions.md)
* [Decision Rules](doc/controllers/decision-rules.md)
* [Disbursement Entries](doc/controllers/disbursement-entries.md)
* [Disbursement Reference](doc/controllers/disbursement-reference.md)
* [Disbursement Results](doc/controllers/disbursement-results.md)
* [Embedded Finance](doc/controllers/embedded-finance.md)
* [Entity Debts](doc/controllers/entity-debts.md)
* [Entity Reserves](doc/controllers/entity-reserves.md)
* [Entity Returns](doc/controllers/entity-returns.md)
* [Entity Terms](doc/controllers/entity-terms.md)
* [Entry Origin](doc/controllers/entry-origin.md)
* [Fee Modifiers](doc/controllers/fee-modifiers.md)
* [Fee Rules](doc/controllers/fee-rules.md)
* [Fraud Sight Enablements](doc/controllers/fraud-sight-enablements.md)
* [Fraud Sight Results](doc/controllers/fraud-sight-results.md)
* [Host Themes](doc/controllers/host-themes.md)
* [Fund Origins](doc/controllers/fund-origins.md)
* [IP Address Lists](doc/controllers/ip-address-lists.md)
* [Invoice Items](doc/controllers/invoice-items.md)
* [Invoice Parameters](doc/controllers/invoice-parameters.md)
* [Invoice Line Items](doc/controllers/invoice-line-items.md)
* [Invoice Results](doc/controllers/invoice-results.md)
* [Logins Helpers](doc/controllers/logins-helpers.md)
* [Merchant Results](doc/controllers/merchant-results.md)
* [Merchant Platform Statuses](doc/controllers/merchant-platform-statuses.md)
* [Message Threads](doc/controllers/message-threads.md)
* [Note Documents](doc/controllers/note-documents.md)
* [Orgs VAS Efe Products](doc/controllers/orgs-vas-efe-products.md)
* [Orgs VA Sfraud Sight Enablements](doc/controllers/orgs-va-sfraud-sight-enablements.md)
* [Orgs VAS Omni Tokens](doc/controllers/orgs-vas-omni-tokens.md)
* [Orgs VAS Pinless Debit Conversions](doc/controllers/orgs-vas-pinless-debit-conversions.md)
* [Orgs VAS Revenue Boosts](doc/controllers/orgs-vas-revenue-boosts.md)
* [Orgs VAS Safer Payments](doc/controllers/orgs-vas-safer-payments.md)
* [Orgs VAS Safer Payments Non-Compliance](doc/controllers/orgs-vas-safer-payments-non-compliance.md)
* [Org Entities](doc/controllers/org-entities.md)
* [Org Flow Actions](doc/controllers/org-flow-actions.md)
* [Org Flows](doc/controllers/org-flows.md)
* [Org Flow Rules](doc/controllers/org-flow-rules.md)
* [Payment Update Groups](doc/controllers/payment-update-groups.md)
* [Payment Updates](doc/controllers/payment-updates.md)
* [Payout Flows](doc/controllers/payout-flows.md)
* [Pending Entry](doc/controllers/pending-entry.md)
* [Pinless Debit Conversions](doc/controllers/pinless-debit-conversions.md)
* [Profit Share Results](doc/controllers/profit-share-results.md)
* [Profit Share Rules](doc/controllers/profit-share-rules.md)
* [Profit Shares](doc/controllers/profit-shares.md)
* [Reserve Entry](doc/controllers/reserve-entry.md)
* [Revenue Boosts](doc/controllers/revenue-boosts.md)
* [Rev Share Schedules](doc/controllers/rev-share-schedules.md)
* [Rev Share Statements](doc/controllers/rev-share-statements.md)
* [Safer Payments](doc/controllers/safer-payments.md)
* [Statement Entry](doc/controllers/statement-entry.md)
* [Subscription Tokens](doc/controllers/subscription-tokens.md)
* [Tax Form Requests](doc/controllers/tax-form-requests.md)
* [Team Logins](doc/controllers/team-logins.md)
* [Terminal Transaction Reference](doc/controllers/terminal-transaction-reference.md)
* [Terminal Transactions Datas](doc/controllers/terminal-transactions-datas.md)
* [Terminal Transactions](doc/controllers/terminal-transactions.md)
* [Terminal Transaction Results](doc/controllers/terminal-transaction-results.md)
* [Terminal Transactions Metadatas](doc/controllers/terminal-transactions-metadatas.md)
* [Token Results](doc/controllers/token-results.md)
* [Transaction Datas](doc/controllers/transaction-datas.md)
* [Transaction Metadatas](doc/controllers/transaction-metadatas.md)
* [Transaction Holds](doc/controllers/transaction-holds.md)
* [Transaction Items](doc/controllers/transaction-items.md)
* [Transactions Results](doc/controllers/transactions-results.md)
* [Fee Refunds](doc/controllers/fee-refunds.md)
* [Transactions Txns](doc/controllers/transactions-txns.md)
* [Txn Sessions](doc/controllers/txn-sessions.md)
* [VAS Efe Offers](doc/controllers/vas-efe-offers.md)
* [VAS Efe Offer Updates](doc/controllers/vas-efe-offer-updates.md)
* [Accounts](doc/controllers/accounts.md)
* [Adjustments](doc/controllers/adjustments.md)
* [Aggregations](doc/controllers/aggregations.md)
* [Alerts](doc/controllers/alerts.md)
* [Assessments](doc/controllers/assessments.md)
* [Billing](doc/controllers/billing.md)
* [Bins](doc/controllers/bins.md)
* [Chargebacks](doc/controllers/chargebacks.md)
* [Contacts](doc/controllers/contacts.md)
* [Credentials](doc/controllers/credentials.md)
* [Customers](doc/controllers/customers.md)
* [Decisions](doc/controllers/decisions.md)
* [Disbursements](doc/controllers/disbursements.md)
* [Divisions](doc/controllers/divisions.md)
* [Entities](doc/controllers/entities.md)
* [Entity Refs](doc/controllers/entity-refs.md)
* [Entity Data](doc/controllers/entity-data.md)
* [Entities Custom Fields](doc/controllers/entities-custom-fields.md)
* [Entries](doc/controllers/entries.md)
* [Fees](doc/controllers/fees.md)
* [Funds](doc/controllers/funds.md)
* [Invoices](doc/controllers/invoices.md)
* [Logins](doc/controllers/logins.md)
* [Mappings](doc/controllers/mappings.md)
* [Members](doc/controllers/members.md)
* [Merchants](doc/controllers/merchants.md)
* [Messages](doc/controllers/messages.md)
* [Notes](doc/controllers/notes.md)
* [Omni Tokens](doc/controllers/omni-tokens.md)
* [Orgs](doc/controllers/orgs.md)
* [Payouts](doc/controllers/payouts.md)
* [Plans](doc/controllers/plans.md)
* [Reserves](doc/controllers/reserves.md)
* [Secrets](doc/controllers/secrets.md)
* [Sessions](doc/controllers/sessions.md)
* [Statements](doc/controllers/statements.md)
* [Subscriptions](doc/controllers/subscriptions.md)
* [Teams](doc/controllers/teams.md)
* [Terminals](doc/controllers/terminals.md)
* [Tokens](doc/controllers/tokens.md)
* [Vendors](doc/controllers/vendors.md)

## SDK Infrastructure

### Configuration

* [ProxyConfigurationBuilder](doc/proxy-configuration-builder.md)

### HTTP

* [HttpRequest](doc/http-request.md)
* [HttpResponse](doc/http-response.md)

### Utilities

* [FileWrapper](doc/file-wrapper.md)
* [ApiException](doc/api-exception.md)

