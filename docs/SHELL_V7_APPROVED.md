# Approved Shell v7

Status: **APPROVED / LOCKED TECHNICAL BASE**

Validated on-device in Widgy on 2026-09-18.

## Confirmed behavior

- Four screen groups: HOME, CALENDAR, WEATHER, FITNESS
- HOME visible by default
- Bottom navigation switches correctly between all four screen groups
- Active tab state follows the selected screen
- Graphite/Midnight Glass palette renders correctly
- Layer ordering is correct
- Custom Widgy color IDs use valid 32-character IDs

## Locked implementation lessons

1. Widgy custom color IDs must use valid 32-character hexadecimal identifiers.
2. Shape field `h` is opacity; it must not be used as a corner-radius substitute.
3. For this structure, sibling ordering is front-to-back: foreground content/taps first, opaque background layers last.
4. Do not modify the working button-toggle IDs without a specific reason.

## Next phase

Build the approved Home master inside the HOME group while preserving this navigation shell unchanged.
