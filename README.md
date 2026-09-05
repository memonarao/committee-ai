# CommitteeAI

CommitteeAI is a PKR-based committee savings management workspace for administrators. It keeps member contributions, payment status, committee rotations, recipients, reports, and AI-powered financial guidance in one place.

## Run locally

This repository uses the Replit pnpm workspace layout:

```bash
pnpm install
pnpm --filter @workspace/db run push
pnpm --filter @workspace/api-server run dev
```

The web artifact is started by its managed workflow. The shared API is served under `/api`.

## Demo access

Open the CommitteeAI preview and select **Enter seeded demo workspace**. The seeded workspace includes eight members, several months of paid and pending contributions, an active 2026 cycle, and recipient assignments.

## Alibaba Cloud Qwen

AI requests are made only by the backend. To connect Alibaba Cloud Model Studio, add the following environment variables to the workspace:

- `ALIBABA_API_KEY` — the Model Studio API key
- `ALIBABA_BASE_URL` — the OpenAI-compatible endpoint base URL
- `AI_MODEL` — the Qwen model name

CommitteeAI sends structured committee data with each request and asks the model to answer only from that data. If the variables are not configured, the app uses a transparent, data-grounded local analysis so the demo remains usable without exposing credentials in the browser.

## Main surfaces

- Dashboard overview with collection rhythm, pending alerts, and recent activity
- Member and payment CRUD with search and status filters
- Committee cycle and recipient rotation management
- AI Insights with health score, risks, forecast, actions, and assistant chat
- Report views with CSV export