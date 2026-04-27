# Free Busy

Query free/busy information for calendars and groups.

```php
$freeBusyApi = $client->getFreeBusyApi();
```

## Class Name

`FreeBusyApi`


# Query Free Busy

Returns free/busy information for a set of calendars and groups.

```php
function queryFreeBusy(FreeBusyRequest $body): ApiResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`FreeBusyRequest`](../../doc/models/free-busy-request.md) | Body, Required | Request body for query free-busy information. |

## Requires scope

### oauth2

`https://www.googleapis.com/auth/calendar`, `https://www.googleapis.com/auth/calendar.readonly`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`FreeBusyResponse`](../../doc/models/free-busy-response.md).

## Example Usage

```php
$body = FreeBusyRequestBuilder::init(
    DateTimeHelper::fromRfc3339DateTimeRequired('2024-01-15T09:00:00Z'),
    DateTimeHelper::fromRfc3339DateTimeRequired('2024-01-15T09:00:00Z'),
    [
        FreeBusyRequestItemBuilder::init(
            'primary'
        )->build()
    ]
)
    ->timeZone('America/New_York')
    ->groupExpansionMax(50)
    ->calendarExpansionMax(25)
    ->build();

$freeBusyApi = $client->getFreeBusyApi();
$apiResponse = $freeBusyApi->queryFreeBusy($body);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'FreeBusyResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    if ($error instanceof ErrorResponseError1Exception) {
        echo 'ErrorResponseError1Exception:', $error;
    }
}
```

## Example Response *(as JSON)*

```json
{
  "kind": "calendar#freeBusy",
  "timeMin": "2024-01-15T09:00:00Z",
  "timeMax": "2024-01-15T09:00:00Z"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request — invalid parameters or request body. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 401 | Authentication required or credentials are invalid. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |

