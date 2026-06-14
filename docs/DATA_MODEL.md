# Data model direction

## Personal entities

- Day log
- Meal section
- Consumed item
- Nutrition targets
- User settings
- Favourite or saved meal

These entities are private and must never be included in community product contributions.

## Product entities

- Barcode or GTIN
- Product and brand name
- Package quantity
- Nutrition basis and values
- Ingredients and allergens
- Serving and practical portion units
- Field-level provenance
- Verification date
- Local revision state

## Provenance

Each important value should record its origin, for example:

- Printed label scan
- Barcode database lookup
- User-confirmed calculation
- Manual correction
- AI-assisted estimate

Confirmed label values should take priority over stale or estimated values while preserving conflict information for review.

## Portion model

Portions may include grams, millilitres, slices, pieces, servings, package fractions, or user-defined units. Derived portions must retain the calculation source and whether the user confirmed it.
