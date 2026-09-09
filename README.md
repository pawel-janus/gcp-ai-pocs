# GCP / AI — Reference Implementations

TypeScript fullstack developer transitioning to cloud-native. These repositories are deliberate practice: each one targets a specific GCP or AI integration pattern I intend to use in production work.

They are proof-of-concept implementations — intentionally scoped, some things simplified — not production systems. The goal is to understand the pattern and have a working reference, not to ship a product.

Two Google Cloud certifications provide the theoretical foundation; these projects are the applied side.

**Certifications**
- Google Cloud Associate Cloud Engineer
- Google Cloud Associate Data Practitioner

---

## Projects

### [smart-changelog](https://github.com/pawel-janus/smart-changelog)

Web app that connects to a GitHub repository, analyzes commits and pull requests using Gemini AI, and generates a human-readable changelog. Deployed on Cloud Run. Also exposes an MCP server so AI assistants (Claude) can call the same logic as a tool.

**Patterns:** Gemini streaming over SSE · Secret Manager · MCP Server (stdio + SSE transport) · monorepo with shared services · multi-stage Docker build · Cloud Build CI/CD

`TypeScript` `Fastify` `React` `Gemini` `Cloud Run` `Secret Manager` `Turborepo` `MCP`

---

### [functions-firestore-auth](https://github.com/pawel-janus/functions-firestore-auth)

Serverless full-stack app: Google sign-in via Firebase Auth, notes stored in Firestore, backend logic in Cloud Functions (2nd gen). JWT verified server-side on every request — no sessions. Frontend deployed to Firebase Hosting.

**Patterns:** JWT verification in Cloud Function · user-scoped Firestore queries · composite indexes · named database · esbuild bundling for npm workspaces · Firebase Emulator Suite for local dev

`TypeScript` `Cloud Functions (2nd gen)` `Firestore` `Firebase Auth` `Firebase Hosting` `React`

---

### [vertex-ai](https://github.com/pawel-janus/vertex-ai)

Minimal Hono backend on Cloud Run that generates changelog entries from git commit messages using Vertex AI Gemini 3.8 Flash. Same SDK (`@google/genai`) as Smart Changelog, but with `vertexai: true` backend — demonstrates auth model differences (API key vs ADC), enterprise features (Cloud Logging, Model Garden), and cost structure (thoughts tokens).

**Patterns:** `@google/genai` with Vertex AI backend · Application Default Credentials (separate file for local dev) · service account authentication · Gemini 3.8 Flash with chain-of-thought reasoning · thoughts tokens observability · npm workspace (shared types) · private Cloud Run service · region `us`/`eu` for Gemini 3.x

`TypeScript` `Hono` `Vertex AI` `Gemini 3.8 Flash` `Cloud Run` `Cloud Logging` `ADC` `npm workspaces`

---

### github-actions-wif *(planned)*

CI/CD pipeline for Smart Changelog using GitHub Actions authenticated to GCP via Workload Identity Federation — no long-lived service account keys stored anywhere. On push to `main`: build image → push to Artifact Registry → deploy to Cloud Run.

**Patterns:** OIDC token exchange · keyless GCP authentication · minimal-privilege deploy service account · Artifact Registry

`GitHub Actions` `Workload Identity Federation` `Cloud Run` `Artifact Registry`

---

### pubsub-cloud-run *(planned)*

Two Cloud Run services communicating asynchronously through Pub/Sub. Producer publishes events; consumer receives them via push subscription and processes them. Practical extension: `release` event triggers changelog generation in Smart Changelog.

**Patterns:** push vs pull subscriptions · message acknowledgment · dead-letter topics · decoupled service architecture · publisher/subscriber IAM

`TypeScript` `Pub/Sub` `Cloud Run` `Firestore`

---

### terraform-iac *(planned)*

Full GCP infrastructure for an existing project (Smart Changelog) provisioned entirely through Terraform — Cloud Run, Secret Manager secrets, Artifact Registry, IAM bindings. State stored in GCS. No manual `gcloud` commands, no console clicks.

**Patterns:** IaC mindset · remote state in GCS · IAM as code · Terraform + firebase-tools split (Firebase resources not supported by Terraform)

`Terraform` `GCS` `Cloud Run` `Secret Manager` `Artifact Registry`

---

### bigquery-cloud-sql *(planned)*

Fastify backend on Cloud Run that queries a public BigQuery dataset (Bitcoin blockchain), aggregates results, and persists daily summaries to Cloud SQL (PostgreSQL). REST API serves pre-aggregated data without re-running expensive BQ queries.

**Patterns:** BQ Node.js client · parameterized queries · Cloud SQL Connector (no public IP) · ETL in TypeScript: extract (BQ) → transform (backend) → load (Cloud SQL) · Cloud Scheduler for daily sync

`TypeScript` `Fastify` `BigQuery` `Cloud SQL (PostgreSQL)` `Cloud Run` `Cloud Scheduler`

---

> These implementations prioritize pattern clarity over production completeness. Error handling, observability, and scalability are simplified or omitted where they would obscure the core pattern being explored.
