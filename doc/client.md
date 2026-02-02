
# Client Class Documentation

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
| proxyConfiguration | [`ProxyConfigurationBuilder`](../doc/proxy-configuration-builder.md) | Represents the proxy configurations for API calls |
| apiKeyCredentials | [`ApiKeyCredentials`](auth/custom-header-signature.md) | The Credentials Setter for Custom Header Signature |
| sessionKeyCredentials | [`SessionKeyCredentials`](auth/custom-header-signature-1.md) | The Credentials Setter for Custom Header Signature |
| txnSessionKeyCredentials | [`TxnSessionKeyCredentials`](auth/custom-header-signature-2.md) | The Credentials Setter for Custom Header Signature |
| usernameCredentials | [`UsernameCredentials`](auth/custom-header-signature-3.md) | The Credentials Setter for Custom Header Signature |
| passwordCredentials | [`PasswordCredentials`](auth/custom-header-signature-4.md) | The Credentials Setter for Custom Header Signature |

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

## Payrix Client

The gateway for the SDK. This class acts as a factory for the Controllers and also holds the configuration of the SDK.

## Controllers

| Name | Description |
|  --- | --- |
| getAPIKeysController() | Gets APIKeysController |
| getAppleDomainsController() | Gets AppleDomainsController |
| getAppleDomainsMassEnablementController() | Gets AppleDomainsMassEnablementController |
| getAccountsController() | Gets AccountsController |
| getAccountsVerificationsController() | Gets AccountsVerificationsController |
| getAdjustmentsController() | Gets AdjustmentsController |
| getAggregationsController() | Gets AggregationsController |
| getAggregationResultGroupsController() | Gets AggregationResultGroupsController |
| getAggregationResultsController() | Gets AggregationResultsController |
| getAlertActionsController() | Gets AlertActionsController |
| getAlertTriggersController() | Gets AlertTriggersController |
| getAlertsController() | Gets AlertsController |
| getAssessmentsController() | Gets AssessmentsController |
| getAuthenticationTokensController() | Gets AuthenticationTokensController |
| getBatchesSettlementsController() | Gets BatchesSettlementsController |
| getBillingController() | Gets BillingController |
| getBillingModifiersController() | Gets BillingModifiersController |
| getBillingEventsController() | Gets BillingEventsController |
| getBinsController() | Gets BinsController |
| getChangeRequestsController() | Gets ChangeRequestsController |
| getChargebacksController() | Gets ChargebacksController |
| getChargebackDocumentsController() | Gets ChargebackDocumentsController |
| getChargebackMessageResultsController() | Gets ChargebackMessageResultsController |
| getChargebackMessagesController() | Gets ChargebackMessagesController |
| getChargebackStatusesController() | Gets ChargebackStatusesController |
| getConfirmationCodesController() | Gets ConfirmationCodesController |
| getContactsController() | Gets ContactsController |
| getCredentialsController() | Gets CredentialsController |
| getCustomersController() | Gets CustomersController |
| getDecisionActionsController() | Gets DecisionActionsController |
| getDecisionRulesController() | Gets DecisionRulesController |
| getDecisionsController() | Gets DecisionsController |
| getDisbursementsController() | Gets DisbursementsController |
| getDisbursementEntriesController() | Gets DisbursementEntriesController |
| getDisbursementReferenceController() | Gets DisbursementReferenceController |
| getDisbursementResultsController() | Gets DisbursementResultsController |
| getDivisionsController() | Gets DivisionsController |
| getEmbeddedFinanceController() | Gets EmbeddedFinanceController |
| getEntitiesController() | Gets EntitiesController |
| getEntityRefsController() | Gets EntityRefsController |
| getEntityDataController() | Gets EntityDataController |
| getEntitiesCustomFieldsController() | Gets EntitiesCustomFieldsController |
| getEntityDebtsController() | Gets EntityDebtsController |
| getEntityReservesController() | Gets EntityReservesController |
| getEntityReturnsController() | Gets EntityReturnsController |
| getEntriesController() | Gets EntriesController |
| getEntityTermsController() | Gets EntityTermsController |
| getEntryOriginController() | Gets EntryOriginController |
| getFeeModifiersController() | Gets FeeModifiersController |
| getFeeRulesController() | Gets FeeRulesController |
| getFeesController() | Gets FeesController |
| getFraudSightEnablementsController() | Gets FraudSightEnablementsController |
| getFraudSightResultsController() | Gets FraudSightResultsController |
| getFundsController() | Gets FundsController |
| getHostThemesController() | Gets HostThemesController |
| getFundOriginsController() | Gets FundOriginsController |
| getIPAddressListsController() | Gets IPAddressListsController |
| getInvoiceItemsController() | Gets InvoiceItemsController |
| getInvoiceParametersController() | Gets InvoiceParametersController |
| getInvoiceLineItemsController() | Gets InvoiceLineItemsController |
| getInvoiceResultsController() | Gets InvoiceResultsController |
| getInvoicesController() | Gets InvoicesController |
| getLoginsHelpersController() | Gets LoginsHelpersController |
| getLoginsController() | Gets LoginsController |
| getMappingsController() | Gets MappingsController |
| getMembersController() | Gets MembersController |
| getMerchantResultsController() | Gets MerchantResultsController |
| getMerchantsController() | Gets MerchantsController |
| getMerchantPlatformStatusesController() | Gets MerchantPlatformStatusesController |
| getMessageThreadsController() | Gets MessageThreadsController |
| getMessagesController() | Gets MessagesController |
| getNoteDocumentsController() | Gets NoteDocumentsController |
| getNotesController() | Gets NotesController |
| getOmniTokensController() | Gets OmniTokensController |
| getOrgsVASEfeProductsController() | Gets OrgsVASEfeProductsController |
| getOrgsVASFraudSightEnablementsController() | Gets OrgsVASFraudSightEnablementsController |
| getOrgsVASOmniTokensController() | Gets OrgsVASOmniTokensController |
| getOrgsVASPinlessDebitConversionsController() | Gets OrgsVASPinlessDebitConversionsController |
| getOrgsVASRevenueBoostsController() | Gets OrgsVASRevenueBoostsController |
| getOrgsVASSaferPaymentsController() | Gets OrgsVASSaferPaymentsController |
| getOrgsVASSaferPaymentsNonComplianceController() | Gets OrgsVASSaferPaymentsNonComplianceController |
| getOrgEntitiesController() | Gets OrgEntitiesController |
| getOrgFlowActionsController() | Gets OrgFlowActionsController |
| getOrgFlowsController() | Gets OrgFlowsController |
| getOrgFlowRulesController() | Gets OrgFlowRulesController |
| getOrgsController() | Gets OrgsController |
| getPaymentUpdateGroupsController() | Gets PaymentUpdateGroupsController |
| getPaymentUpdatesController() | Gets PaymentUpdatesController |
| getPayoutFlowsController() | Gets PayoutFlowsController |
| getPayoutsController() | Gets PayoutsController |
| getPendingEntryController() | Gets PendingEntryController |
| getPinlessDebitConversionsController() | Gets PinlessDebitConversionsController |
| getPlansController() | Gets PlansController |
| getProfitShareResultsController() | Gets ProfitShareResultsController |
| getProfitShareRulesController() | Gets ProfitShareRulesController |
| getProfitSharesController() | Gets ProfitSharesController |
| getReserveEntryController() | Gets ReserveEntryController |
| getReservesController() | Gets ReservesController |
| getRevenueBoostsController() | Gets RevenueBoostsController |
| getRevShareSchedulesController() | Gets RevShareSchedulesController |
| getRevShareStatementsController() | Gets RevShareStatementsController |
| getSaferPaymentsController() | Gets SaferPaymentsController |
| getSecretsController() | Gets SecretsController |
| getSessionsController() | Gets SessionsController |
| getStatementEntryController() | Gets StatementEntryController |
| getStatementsController() | Gets StatementsController |
| getSubscriptionTokensController() | Gets SubscriptionTokensController |
| getSubscriptionsController() | Gets SubscriptionsController |
| getTaxFormRequestsController() | Gets TaxFormRequestsController |
| getTeamLoginsController() | Gets TeamLoginsController |
| getTeamsController() | Gets TeamsController |
| getTerminalTransactionReferenceController() | Gets TerminalTransactionReferenceController |
| getTerminalTransactionsDatasController() | Gets TerminalTransactionsDatasController |
| getTerminalTransactionsController() | Gets TerminalTransactionsController |
| getTerminalTransactionResultsController() | Gets TerminalTransactionResultsController |
| getTerminalTransactionsMetadatasController() | Gets TerminalTransactionsMetadatasController |
| getTerminalsController() | Gets TerminalsController |
| getTokensController() | Gets TokensController |
| getTokenResultsController() | Gets TokenResultsController |
| getTransactionDatasController() | Gets TransactionDatasController |
| getTransactionMetadatasController() | Gets TransactionMetadatasController |
| getTransactionHoldsController() | Gets TransactionHoldsController |
| getTransactionItemsController() | Gets TransactionItemsController |
| getTransactionsResultsController() | Gets TransactionsResultsController |
| getFeeRefundsController() | Gets FeeRefundsController |
| getTransactionsTxnsController() | Gets TransactionsTxnsController |
| getTxnSessionsController() | Gets TxnSessionsController |
| getVASEfeOffersController() | Gets VASEfeOffersController |
| getVASEfeOfferUpdatesController() | Gets VASEfeOfferUpdatesController |
| getVendorsController() | Gets VendorsController |

