# Calendar Print Sample

React and TypeScript components for turning care schedules into printable weekly calendars, medication lists, activity lists, and recipient summaries.

Extracted from a product I worked on during 2022–2023, this repository highlights print layout and scheduling logic. **It is a source sample, not a standalone application.**

## What to explore

- **Weekly schedule layout:** calculate the visible time range and grid dimensions from the events in each week.
- **Overlapping events:** determine event positioning before rendering schedule blocks.
- **Print presentation:** landscape page styles, shared headers and footers, and page breaks.
- **Reusable output:** separate views for medications, activities, and care recipient details.

## Start here

| File | Responsibility |
| --- | --- |
| [CalendarPrint.tsx](PrintableContent/CalendarPrint/CalendarPrint.tsx) | Weekly pages and schedule grid composition |
| [helpers.ts](PrintableContent/CalendarPrint/helpers.ts) | Schedule preparation, recurrence, and positioning |
| [CalendarPrintElements.tsx](PrintableContent/CalendarPrint/CalendarPrintElements.tsx) | Hour labels, event blocks, and grid lines |
| [CalendarPrintPanel.tsx](PrintableContent/CalendarPrint/CalendarPrintPanel.tsx) | Print controls and data integration |
| [PrintableContentContainer.tsx](PrintableContent/PrintableContentContainer.tsx) | Ref forwarding and landscape print style |

## Run and integration status

There is no `package.json`, lockfile, application entry point, or development server in this repository. Running `npm install` or `npm run dev` here will not launch a demo.

The components depend on React, Fluent UI, recurrence utilities, and application-specific modules imported through `src/...`. Those modules include generated GraphQL hooks, recipient data hooks, medication helpers, shared components, and styling definitions that are not bundled in this excerpt.

To integrate this source into a host application:

1. Copy `PrintableContent/` into the host's `src/features/` directory, matching the existing imports.
2. Configure the host's `src/*` alias and provide the missing application modules.
3. Supply recipient details and weekly event data to `CalendarPrint` using the interfaces defined in its source.
4. Mount the print view through the host's print flow and check landscape print preview with both sparse and overlapping schedules.

These are integration requirements, not a verified standalone quick start. No environment variables or backend setup can make this excerpt runnable on its own.

## Technology

TypeScript, React, Fluent UI, CSS grid, browser print styles, and recurrence rules (`rrule`).

## Next milestone

A self-contained demo needs synthetic schedule fixtures, replacements for host-specific dependencies, a small application shell, and browser print verification. Until then, use this repository as a focused code walkthrough.
