
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](../README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| timeout | `int` | Timeout for API calls in seconds.<br>*Default*: `30` |
| enableRetries | `bool` | Whether to enable retries and backoff feature.<br>*Default*: `false` |
| numberOfRetries | `int` | The number of retries to make.<br>*Default*: `0` |
| retryInterval | `float` | The retry time interval between the endpoint calls.<br>*Default*: `1` |
| backOffFactor | `float` | Exponential backoff factor to increase interval between retries.<br>*Default*: `2` |
| maximumRetryWaitTime | `int` | The maximum wait time in seconds for overall retrying requests.<br>*Default*: `0` |
| retryOnTimeout | `bool` | Whether to retry on request timeout.<br>*Default*: `true` |
| httpStatusCodesToRetry | `array` | Http status codes to retry against.<br>*Default*: `408, 413, 429, 500, 502, 503, 504, 521, 522, 524` |
| httpMethodsToRetry | `array` | Http methods to retry against.<br>*Default*: `'GET', 'PUT'` |
| loggingConfiguration | [`LoggingConfigurationBuilder`](../doc/logging-configuration-builder.md) | Represents the logging configurations for API calls |
| proxyConfiguration | [`ProxyConfigurationBuilder`](../doc/proxy-configuration-builder.md) | Represents the proxy configurations for API calls |
| authorizationCodeAuth | [`AuthorizationCodeAuth`](auth/oauth-2-authorization-code-grant.md) | The Credentials Setter for OAuth 2 Authorization Code Grant |

The API client can be initialized as follows:

```php
use CalendarApiLib\Logging\LoggingConfigurationBuilder;
use CalendarApiLib\Logging\RequestLoggingConfigurationBuilder;
use CalendarApiLib\Logging\ResponseLoggingConfigurationBuilder;
use Psr\Log\LogLevel;
use CalendarApiLib\Environment;
use CalendarApiLib\Authentication\AuthorizationCodeAuthCredentialsBuilder;
use CalendarApiLib\Models\OauthScope;
use CalendarApiLib\CalendarApiClientBuilder;

$client = CalendarApiClientBuilder::init()
    ->authorizationCodeAuthCredentials(
        AuthorizationCodeAuthCredentialsBuilder::init(
            'OAuthClientId',
            'OAuthClientSecret',
            'OAuthRedirectUri'
        )
            ->oauthScopes(
                [
                    OauthScope::HTTPS_WWW_GOOGLEAPIS_COM_AUTH_CALENDAR_READONLY,
                    OauthScope::HTTPS_WWW_GOOGLEAPIS_COM_AUTH_CALENDAR_EVENTS
                ]
            )
    )
    ->environment(Environment::PRODUCTION)
    ->loggingConfiguration(
        LoggingConfigurationBuilder::init()
            ->level(LogLevel::INFO)
            ->requestConfiguration(RequestLoggingConfigurationBuilder::init()->body(true))
            ->responseConfiguration(ResponseLoggingConfigurationBuilder::init()->headers(true))
    )
    ->build();
```

## Calendar API Client

The gateway for the SDK. This class acts as a factory for the Apis and also holds the configuration of the SDK.

## Apis

| Name | Description |
|  --- | --- |
| getCalendarListApi() | Gets CalendarListApi |
| getEventsApi() | Gets EventsApi |
| getFreeBusyApi() | Gets FreeBusyApi |
| getChannelsApi() | Gets ChannelsApi |
| getOauthAuthorizationApi() | Gets OauthAuthorizationApi |

