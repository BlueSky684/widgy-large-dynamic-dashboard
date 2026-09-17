# Widgy Large Dynamic Dashboard

A premium **Large Widgy dashboard** with four interactive in-widget screens:

- **Home**
- **Calendar**
- **Weather**
- **Fitness**

The project is designed as a single Large Widgy widget whose bottom navigation switches the visible information screen without opening a separate widget.

## Project status

**Design phase complete. Implementation starting.**

The visual masters for all four screens are approved and should be treated as locked references during implementation. Changes to layout, proportions, visual language, or navigation should be made only after explicit approval.

## Approved screen structure

### Home

Main dashboard screen with:

- Dynamic World Map hero
- Time and date context
- Calendar / next-event information
- Day progress
- Compact dashboard information
- Persistent bottom navigation

The World Map hero will be rendered dynamically through a dedicated API endpoint. The existing `widgy-maps-world-glass` project must remain untouched; this project will use its own renderer/endpoint so the approved World Map Glass widget cannot be broken by future development.

### Calendar

Dedicated calendar screen with:

- Month calendar
- Current day highlight
- Today / upcoming events
- Reminders where supported
- Persistent bottom navigation with **Calendar** highlighted as active

### Weather

Dedicated detailed weather screen with:

- Current conditions
- Temperature and condition icon
- Feels Like
- High / Low
- Humidity
- Wind
- UV
- Hourly forecast
- Daily forecast
- Persistent bottom navigation with **Weather** highlighted as active

Weather artwork should follow the approved project icon language rather than introducing a new icon family.

### Fitness

Dedicated activity screen with:

- Steps
- Activity / progress rings
- Active calories
- Distance
- Exercise
- Stand / activity metrics where supported by Widgy
- Daily progress metrics
- Weekly activity where the available Widgy data source supports it
- Persistent bottom navigation with **Fitness** highlighted as active

## Navigation model

The widget uses a persistent four-tab navigation bar:

`HOME · CALENDAR · WEATHER · FITNESS`

The navigation stays in the same position on every screen. A tap changes the visible Widgy content group and active-tab highlight while keeping the widget itself on screen.

The implementation should follow the proven Widgy layer-toggle / button mechanism from the reference widget rather than creating four separate widgets.

## Architecture

### Widgy

Widgy is responsible for:

- Main widget layout
- Four screen groups
- Tab switching
- Active-tab visual state
- Calendar data where available
- Weather data
- Fitness / pedometer / health-related data where available
- Native text, typography, cards, separators, and interactions

### GitHub

This repository is the source of truth for:

- Renderer source code
- Project assets
- Technical documentation
- Versioned files used by the dashboard

### Vercel

Vercel will be used only where a server-side renderer is actually needed, initially for the **Home World Map hero**.

Planned endpoint:

```text
/api/world-map-large
```

This endpoint must be independent of the existing World Map Glass renderer.

## Visual direction

The approved visual language is:

- Dark neutral graphite / Midnight Glass base
- Clean premium glass panels
- Thin restrained borders and separators
- White and cool-gray typography
- Neon lime used as the primary active accent
- Blue retained for precipitation / selected weather information where appropriate
- Natural weather-icon colors retained where approved
- No unnecessary cyber-blue background treatment
- No decorative city photography
- No unrelated Tesla vehicle content

## Implementation principles

1. **Do not redesign approved screens during implementation.**
2. Build from a known-working Widgy structure rather than inventing an unverified schema.
3. Keep the four navigation tabs fixed and consistent across every screen.
4. Prefer native Widgy data and layers where practical.
5. Use GitHub/Vercel only for elements that genuinely require external rendering.
6. Do not modify the existing approved World Map Glass endpoint or assets in place.
7. Test navigation first with a minimal four-screen shell before adding full screen content.
8. Add each approved screen incrementally and verify it on-device before continuing.

## Planned build order

1. Four-screen Widgy shell
2. Persistent bottom navigation and active states
3. Home structure
4. Dedicated World Map Large renderer
5. Calendar screen
6. Weather screen
7. Fitness screen
8. Data validation and fallback states
9. Final visual alignment and cleanup
10. Release-ready Widgy JSON

## Repository

`BlueSky684/widgy-large-dynamic-dashboard`

---

Built specifically for the approved Large Widgy dashboard project. This README should be updated as implementation decisions are verified and locked.
