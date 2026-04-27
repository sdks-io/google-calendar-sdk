
# Focus Time Properties

Focus time event data. Used if eventType is focusTime.

*This model accepts additional fields of type array.*

## Structure

`FocusTimeProperties`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `autoDeclineMode` | [`?string(AutoDeclineMode)`](../../doc/models/auto-decline-mode.md) | Optional | Whether to auto-decline conflicting meeting invitations. | getAutoDeclineMode(): ?string | setAutoDeclineMode(?string autoDeclineMode): void |
| `declineMessage` | `?string` | Optional | Response message to set when auto-declining invitations. | getDeclineMessage(): ?string | setDeclineMessage(?string declineMessage): void |
| `chatStatus` | [`?string(ChatStatus)`](../../doc/models/chat-status.md) | Optional | Chat status during focus time. | getChatStatus(): ?string | setChatStatus(?string chatStatus): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "declineMessage": "Resource not found.",
  "autoDeclineMode": "declineOnlyNewConflictingInvitations",
  "chatStatus": "available",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

