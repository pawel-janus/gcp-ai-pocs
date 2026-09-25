# Portfolio

TypeScript fullstack developer building production-ready applications on Google Cloud Platform. Focused on serverless architecture, AI integrations, and modern frontend patterns.

**Certifications**
- Google Cloud Associate Cloud Engineer
- Google Cloud Associate Data Practitioner

---

## GCP Projects

Building serverless infrastructure, AI applications, and data pipelines on GCP.

### [smart-changelog](https://github.com/pawel-janus/smart-changelog)

AI-powered changelog generator. Analyzes GitHub commits and PRs using Gemini, generates human-readable changelogs. Deployed on Cloud Run with MCP server integration.

`TypeScript` `Fastify` `React` `Gemini` `Cloud Run` `MCP`

### [functions-firestore-auth](https://github.com/pawel-janus/functions-firestore-auth)

Serverless full-stack: Firebase Auth (Google sign-in), Firestore database, Cloud Functions backend. JWT verification, user-scoped queries, Firebase Hosting.

`TypeScript` `Cloud Functions` `Firestore` `Firebase Auth`

### [vertex-ai](https://github.com/pawel-janus/vertex-ai)

Vertex AI Gemini 3.8 Flash backend. Demonstrates enterprise AI: ADC authentication, private Cloud Run, thoughts tokens observability.

`TypeScript` `Hono` `Vertex AI` `Gemini 3.8`

### [gcp-github-actions](https://github.com/pawel-janus/gcp-github-actions)

CI/CD pipeline with GitHub Actions and Workload Identity Federation. Keyless authentication via OIDC token exchange — zero static credentials. Smart deployment with path filtering: deploy only changed workspaces. Phase 1-3: backend (Cloud Run), frontend (Firebase Hosting), conditional deployment with reusable workflows.

`GitHub Actions` `Workload Identity Federation` `Cloud Run` `Firebase Hosting` `React` `TypeScript` `path filtering`

---

## Next.js Projects

Modern Next.js 16 App Router patterns: SSR, ISR, Server Actions, route organization. Progressive POC sequence exploring production patterns.

### [nextjs-ssr-basics](https://github.com/pawel-janus/nextjs-ssr-basics)

Weather dashboard demonstrating Server-Side Rendering (SSR) with Next.js 16 App Router. Async Server Components, Suspense boundaries, error.tsx, Tailwind v4.

`TypeScript` `Next.js 16` `React 19` `Tailwind v4` `Cloud Run`

### [nextjs-interactive-weather](https://github.com/pawel-janus/nextjs-interactive-weather)

Client Components and interactivity: city selector, recent searches, API Routes. Demonstrates 'use client', useState/useEffect, useRouter, useSearchParams.

`TypeScript` `Next.js 16` `Client Components` `API Routes` `Zod` `Cloud Run`

### [nextjs-dynamic-routes](https://github.com/pawel-janus/nextjs-dynamic-routes)

Dynamic routes (`/weather/[city]`), loading.tsx, not-found.tsx, generateMetadata for SEO. Shared server-side weatherService. Better SEO, shareable links.

`TypeScript` `Next.js 16` `Dynamic Routes` `Loading States` `Cloud Run`

### [nextjs-server-actions](https://github.com/pawel-janus/nextjs-server-actions)

Weather app with Server Actions and progressive enhancement. Form works without JavaScript. Replaces API Routes with 'use server' functions.

`TypeScript` `Next.js 16` `Server Actions` `useActionState` `Cloud Run`

### [nextjs-isr-ssg](https://github.com/pawel-janus/nextjs-isr-ssg)

Incremental Static Regeneration (ISR) and Static Site Generation (SSG). Popular cities pre-rendered at build time, revalidated every hour. Time-based cache invalidation.

`TypeScript` `Next.js 16` `ISR` `SSG` `Cloud Run`

### [nextjs-route-groups](https://github.com/pawel-janus/nextjs-route-groups)

Route Groups demonstration: different layouts per section, code organization without URL changes. Homepage uses hero layout, weather pages use sticky search bar.

`TypeScript` `Next.js 16` `Route Groups` `Nested Layouts` `Cloud Run`

### [nextjs-auth-middleware](https://github.com/pawel-janus/nextjs-auth-middleware)

NextAuth.js v5 integration with Google OAuth. Middleware-based route protection, httpOnly cookie sessions, Server Actions. Full page redirect OAuth flow, protected dashboard.

`TypeScript` `Next.js 16` `NextAuth` `OAuth 2.0` `Middleware` `Cloud Run`

**In progress:** Firestore database integration, multi-provider OAuth.

---

## AI/LLM Applications

Production AI/LLM patterns with GCP implementation. Progressive POC sequence: embeddings → RAG → agents → conversations.

### [llm-search](https://github.com/pawel-janus/llm-search)

Semantic search over SEC quarterly filings. Vector embeddings with Vertex AI, Firestore vector search, 275 real financial documents from BigQuery. Deployed to Cloud Run with 411ms warm latency, similarity 0.82-0.85.

`TypeScript` `Fastify` `Vertex AI` `Firestore` `BigQuery` `Cloud Run` `Deployed`

### [llm-rag](https://github.com/pawel-janus/llm-rag)

Financial Q&A with RAG pipeline. Ask questions in natural language, get answers with citations from SEC filings. Gemini 2.5 Flash generation, context formatting (human-readable tags/values), prompt engineering. Deployed to Cloud Run with ~2s warm latency.

`TypeScript` `Fastify` `React` `Gemini 2.5 Flash` `Vertex AI` `Firestore` `BigQuery` `Cloud Run` `Deployed`

**Planned (Phase 1):** Multi-source agents (SEC + IEX) · Multi-turn conversations

---

> These implementations prioritize pattern clarity over production completeness. The goal is to understand the pattern and have a working reference, not to ship a product.
