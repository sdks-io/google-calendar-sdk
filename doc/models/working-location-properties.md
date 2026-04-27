
# Working Location Properties

Working location event data. Used if eventType is workingLocation.

*This model accepts additional fields of type array.*

## Structure

`WorkingLocationProperties`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | [`?string(WorkingLocationType)`](../../doc/models/working-location-type.md) | Optional | Type of working location. | getType(): ?string | setType(?string type): void |
| `homeOffice` | `?array` | Optional | Indicates working from home. Present if type is homeOffice. Value is always an empty object. | getHomeOffice(): ?array | setHomeOffice(?array homeOffice): void |
| `officeLocation` | [`?OfficeLocation`](../../doc/models/office-location.md) | Optional | Office location details for a working location event. | getOfficeLocation(): ?OfficeLocation | setOfficeLocation(?OfficeLocation officeLocation): void |
| `customLocation` | [`?CustomLocation`](../../doc/models/custom-location.md) | Optional | Custom location details for a working location event. | getCustomLocation(): ?CustomLocation | setCustomLocation(?CustomLocation customLocation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "type": "officeLocation",
  "homeOffice": {
    "key1": "val1",
    "key2": "val2"
  },
  "officeLocation": {
    "buildingId": "buildingId2",
    "floorId": "floorId6",
    "floorSectionId": "floorSectionId6",
    "deskId": "deskId8",
    "label": "label0",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "customLocation": {
    "label": "label0",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

