
# Out of Office Properties

Out-of-office event data. Used if eventType is outOfOffice.

*This model accepts additional fields of type array.*

## Structure

`OutOfOfficeProperties`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `autoDeclineMode` | [`?string(AutoDeclineMode)`](../../doc/models/auto-decline-mode.md) | Optional | Whether to auto-decline conflicting meeting invitations. | getAutoDeclineMode(): ?string | setAutoDeclineMode(?string autoDeclineMode): void |
| `declineMessage` | `?string` | Optional | Response message to set when auto-declining invitations. | getDeclineMessage(): ?string | setDeclineMessage(?string declineMessage): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "declineMessage": "Resource not found.",
  "autoDeclineMode": "declineOnlyNewConflictingInvitations",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

