# Design notes

## Visual direction

- Cute raccoon chef mascot.
- Cozy pastel/crayon-inspired identity.
- Rounded cards, soft spacing, restrained shadows, and calm typography.
- Custom Cozy Pastel Light and Cozy Pastel Dark themes.
- Standard Light and Standard Dark themes aligned with Android conventions.
- Theme default: System.

## App bar

- Mascot/app symbol aligned left.
- App name centred against the full screen.
- Settings symbol aligned right.
- Settings page uses Back on the left and About on the right.

## About and support

- About follows the established K2040 Android dialog pattern.
- The optional Ko-fi action opens `https://ko-fi.com/k2040` in the external browser.
- Ko-fi support is voluntary and does not unlock features or create an entitlement.

## Bottom navigation

Primary destinations should focus on Home, History, central Camera action, and Products. Settings remains in the top app bar.

## Camera action

Pressing the central camera action reveals:

- Barcode/product scan.
- Meal-photo recognition, represented by a plate with fork and spoon.

Label OCR is a fallback inside the product flow rather than a third permanent main action.

## Meal templates

- Users can save a meal with its products and portions as a named template.
- Templates can target Breakfast, Lunch, Dinner, Snacks, or a custom meal list.
- A template can be added to today with one tap and may optionally be scheduled for selected weekdays.
- Editing today's copied meal must not alter the template.
- Editing a template must not rewrite historical diary entries.
