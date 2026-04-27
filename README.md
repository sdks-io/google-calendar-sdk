
# Getting Started with Calendar API

## Introduction

Manipulates events and other calendar data. Provides access to Google Calendar for creating, listing, patching, and deleting events, querying free/busy information, and setting up push notifications for event changes.

## Install the Package

Run the following command to install the package and automatically add the dependency to your composer.json file:

```bash
composer require "sdks-io/google-calendar-apimatic-sdk:1.0.0"
```

Or add it to the composer.json file manually as given below:

```json
"require": {
    "sdks-io/google-calendar-apimatic-sdk": "1.0.0"
}
```

You can also view the package at:
https://packagist.org/packages/sdks-io/google-calendar-apimatic-sdk#1.0.0

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/sdks-io/google-calendar-sdk/tree/1.0.0/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](https://www.github.com/sdks-io/google-calendar-sdk/tree/1.0.0/README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| timeout | `int` | Timeout for API calls in seconds.<br>*Default*: `30` |
| enableRetries | `bool` | Whether to enable retries and backoff feature.<br>*Default*: `false` |
| numberOfRetries | `int` | The number of retries to make.<br>*Default*: `0` |
| retryInterval | `float` | The retry time interval between the endpoint calls.<br>*Default*: `1` |
| backOffFactor | `float` | Exponential backoff factor to increase interval between retries.<br>*Default*: `2` |
| maximumRetryWaitTime | `int` | The maximum wait time in seconds for overall retrying requests.<br>*Default*: `0` |
| retryOnTimeout | `bool` | Whether to retry on request timeout.<br>*Default*: `true` |
| httpStatusCodesToRetry | `array` | Http status codes to retry against.<br>*Default*: `408, 413, 429, 500, 502, 503, 504, 521, 522, 524` |
| httpMethodsToRetry | `array` | Http methods to retry against.<br>*Default*: `'GET', 'PUT'` |
| loggingConfiguration | [`LoggingConfigurationBuilder`](https://www.github.com/sdks-io/google-calendar-sdk/tree/1.0.0/doc/logging-configuration-builder.md) | Represents the logging configurations for API calls |
| proxyConfiguration | [`ProxyConfigurationBuilder`](https://www.github.com/sdks-io/google-calendar-sdk/tree/1.0.0/doc/proxy-configuration-builder.md) | Represents the proxy configurations for API calls |
| authorizationCodeAuth | [`AuthorizationCodeAuth`](https://www.github.com/sdks-io/google-calendar-sdk/tree/1.0.0/doc/auth/oauth-2-authorization-code-grant.md) | The Credentials Setter for OAuth 2 Authorization Code Grant |

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

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| PRODUCTION | **Default** Google Calendar API v3 |

## Authorization

This API uses the following authentication schemes.

* [`oauth2 (OAuth 2 Authorization Code Grant)`](https://www.github.com/sdks-io/google-calendar-sdk/tree/1.0.0/doc/auth/oauth-2-authorization-code-grant.md)

## List of APIs

* [Calendar List](https://www.github.com/sdks-io/google-calendar-sdk/tree/1.0.0/doc/controllers/calendar-list.md)
* [Events](https://www.github.com/sdks-io/google-calendar-sdk/tree/1.0.0/doc/controllers/events.md)
* [Free Busy](https://www.github.com/sdks-io/google-calendar-sdk/tree/1.0.0/doc/controllers/free-busy.md)
* [Channels](https://www.github.com/sdks-io/google-calendar-sdk/tree/1.0.0/doc/controllers/channels.md)

## SDK Infrastructure

### Configuration

* [ProxyConfigurationBuilder](https://www.github.com/sdks-io/google-calendar-sdk/tree/1.0.0/doc/proxy-configuration-builder.md)
* [LoggingConfigurationBuilder](https://www.github.com/sdks-io/google-calendar-sdk/tree/1.0.0/doc/logging-configuration-builder.md)
* [RequestLoggingConfigurationBuilder](https://www.github.com/sdks-io/google-calendar-sdk/tree/1.0.0/doc/request-logging-configuration-builder.md)
* [ResponseLoggingConfigurationBuilder](https://www.github.com/sdks-io/google-calendar-sdk/tree/1.0.0/doc/response-logging-configuration-builder.md)

### HTTP

* [HttpRequest](https://www.github.com/sdks-io/google-calendar-sdk/tree/1.0.0/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/sdks-io/google-calendar-sdk/tree/1.0.0/doc/api-response.md)

