# Channels

Manage push notification channels.

```php
$channelsApi = $client->getChannelsApi();
```

## Class Name

`ChannelsApi`


# Stop Channel

Stops receiving push notifications for the specified channel. This is required to clean up channels created by the watchEvents operation.

```php
function stopChannel(StopChannelRequest $body): ApiResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`StopChannelRequest`](../../doc/models/stop-channel-request.md) | Body, Required | Request body for stop a notification channel. |

## Requires scope

### oauth2

`https://www.googleapis.com/auth/calendar`, `https://www.googleapis.com/auth/calendar.events`, `https://www.googleapis.com/auth/calendar.readonly`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```php
$body = StopChannelRequestBuilder::init(
    'abc123',
    'abc123'
)->build();

$channelsApi = $client->getChannelsApi();
$apiResponse = $channelsApi->stopChannel($body);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'void:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    if ($error instanceof ErrorResponseError1Exception) {
        echo 'ErrorResponseError1Exception:', $error;
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request — invalid parameters or request body. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 401 | Authentication required or credentials are invalid. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 403 | Insufficient permissions for the requested resource. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 404 | The requested resource was not found. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |

