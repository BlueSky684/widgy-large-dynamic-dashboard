# Shell v1

This is the first functional Widgy shell for the project.

## Purpose

Validate the four-screen in-widget tab mechanism before any approved master screen is implemented.

## Screens

- Home — layer group ID `245`
- Calendar — layer group ID `247`
- Weather — layer group ID `246`
- Fitness — layer group ID `195`

Only Home is visible by default.

## Tabs

The persistent tab group is named `Tabs`.

Each tab explicitly shows its own active visual state + screen group and hides all three other states/screens.

### Home

`button_174,176,245-181,183,247,188,190,246,160,170,195`

### Calendar

`button_181,183,247-174,176,245,188,190,246,160,170,195`

### Weather

`button_188,190,246-174,176,245,181,183,247,160,170,195`

### Fitness

`button_160,170,195-174,176,245,181,183,247,188,190,246`

## Test procedure

Import `widgy/WidgyLargeDynamicDashboard_Shell_v1.json` into Widgy and confirm this sequence:

1. Home is visible initially.
2. Tap Calendar — only Calendar should be visible and Calendar should become active.
3. Tap Weather — only Weather should be visible and Weather should become active.
4. Tap Fitness — only Fitness should be visible and Fitness should become active.
5. Tap Home — return to Home with no overlapping content.

The current screen content is intentionally limited to placeholder labels. Do not begin the final approved visual build until this navigation test passes on-device.
