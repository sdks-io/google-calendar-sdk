
# Office Location

Office location details for a working location event.

*This model accepts additional fields of type array.*

## Structure

`OfficeLocation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `buildingId` | `?string` | Optional | Building identifier. | getBuildingId(): ?string | setBuildingId(?string buildingId): void |
| `floorId` | `?string` | Optional | Floor identifier. | getFloorId(): ?string | setFloorId(?string floorId): void |
| `floorSectionId` | `?string` | Optional | Floor section identifier. | getFloorSectionId(): ?string | setFloorSectionId(?string floorSectionId): void |
| `deskId` | `?string` | Optional | Desk identifier. | getDeskId(): ?string | setDeskId(?string deskId): void |
| `label` | `?string` | Optional | Office name displayed in Calendar Web and Mobile clients. | getLabel(): ?string | setLabel(?string label): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "buildingId": "abc123",
  "floorId": "abc123",
  "floorSectionId": "abc123",
  "deskId": "abc123",
  "label": "Main Campus - Building A",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

