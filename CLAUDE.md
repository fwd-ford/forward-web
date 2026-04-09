# forward-web — Repository Instructions

## Language Policy

- Code, variables, functions, components, routes: always in English.
- Comments: bilingual (English first, Portuguese in parentheses when helpful).
- User-facing text: always via i18n keys, never hardcoded strings.
- Supported locales: en, pt-BR.

## Stack

- SvelteKit with TypeScript (strict mode)
- Tailwind CSS
- Supabase JS SDK (@supabase/supabase-js)

## Project Structure

- `src/lib/components/ui/`: reusable UI primitives (Button, Card, Table, Badge, Chart)
- `src/lib/components/domain/`: business-specific components (VehicleCard, LeadRow, ChurnScore)
- `src/lib/stores/`: Svelte stores for global state
- `src/lib/services/`: Supabase client, external API calls
- `src/lib/utils/`: pure helper functions, formatters, validators
- `src/lib/i18n/`: localization files and i18n logic
- `src/lib/types/`: shared TypeScript interfaces and types
- `src/routes/(auth)/`: authenticated pages (dashboard, customers, leads, dealers, performance)
- `src/routes/(public)/`: public pages (login)
- `src/routes/api/`: SvelteKit server routes (BFF layer for Go API calls)

## Mandatory Patterns

### Components
- UI components are generic and reusable. Domain components are business-specific.
- Every component must accept data via props, never fetch data internally.
- Use TypeScript interfaces for all props.

### Data Flow
- Pages (`+page.svelte`) fetch data via `+page.server.ts` or Supabase client.
- Stores are for cross-component state only, not for data fetching.
- Supabase SDK is the primary data source. Go API is called only for WhatsApp/webhooks.

### i18n
- Every user-facing string must use an i18n key.
- Keys follow dot notation: `dashboard.vinShare.title`, `leads.priority.critical`.
- Default locale: pt-BR. Fallback: en.

### Styling
- Tailwind utility classes only. No custom CSS unless absolutely necessary.
- Follow the design tokens: Ford Blue (#003478) as primary.
