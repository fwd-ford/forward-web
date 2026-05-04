# forward-web

![org](https://img.shields.io/badge/org-fwd--ford-blue?style=flat-square)
![stack](https://img.shields.io/badge/stack-SvelteKit_·_TypeScript_·_Tailwind-333?style=flat-square)

Web dashboard for **ForwardService** — dealer management, Ford regional/national views, performance console.

## Stack

- **SvelteKit** with TypeScript
- **Tailwind CSS** for styling
- **Supabase SDK** for data, auth and realtime
- **Chart.js** or similar for visualizations

## Structure

```
src/
├── lib/
│   ├── components/
│   │   ├── ui/          # Primitives (Button, Card, Table, Chart, Badge)
│   │   └── domain/      # Business components (VehicleCard, LeadRow, ChurnBadge)
│   ├── stores/          # Svelte stores (global state)
│   ├── services/        # Supabase client, API calls
│   ├── utils/           # Helpers, formatters, validators
│   ├── i18n/            # Localization (en, pt-BR)
│   └── types/           # Shared TypeScript types
├── routes/
│   ├── (auth)/          # Authenticated routes
│   │   ├── dashboard/   # Service Share Map, general metrics
│   │   ├── customers/   # Customer Vista 360
│   │   ├── leads/       # Pulse Leads
│   │   ├── dealers/     # IHC, Benchmark
│   │   ├── performance/ # ROI, funnel, conversion
│   │   └── settings/    # Dealer/user settings
│   ├── (public)/
│   │   └── login/
│   └── api/             # SvelteKit server routes (BFF)
└── tests/
```

## Related Repos

| Repo | Purpose |
|---|---|
| [forward-api-java](https://github.com/fwd-ford/forward-api-java) | Official backend — Java 17 + Spring Boot 3, REST + SOAP |
| [forward-infra](https://github.com/fwd-ford/forward-infra) | Supabase schema and migrations |
| [forward-docs](https://github.com/fwd-ford/forward-docs) | Documentation |
