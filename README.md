# João Sousa

Tech Lead at **LAI**, where I build voice, messaging and inference
infrastructure — systems that have to keep calls, messages and transcriptions
flowing at the same time, without falling over.

Most of that work lives in private repositories. What follows is what I
actually build and the stack I build it with.

## What I work on

**Real-time voice**
Outbound dialing and conversational voice. Asterisk/ARI for call control and a
Python real-time pipeline for the conversation itself: WebRTC VAD for turn
detection, faster-whisper on CTranslate2 for streaming transcription, and an
OpenAI-compatible endpoint driving the dialogue. Backend in Bun + Elysia over
PostgreSQL, with BullMQ and Redis behind the queues.

**Messaging at scale**
High-volume WhatsApp messaging. Node backend on Prisma and PostgreSQL,
LangGraph agents with Postgres-backed checkpointing for stateful
conversations, S3 for media, rate limiting throughout. Shipped to users as a
PWA.

**Meeting capture and analysis**
LiveKit for real-time media, with transcription, speaker diarization and
expression analysis behind it, exposed over Socket.io and an MCP server.
Bun + Elysia + Drizzle on the API, C++ and Python in the inference layer.

**Model serving and training**
Self-hosted GPU workers, one job each: transcription, diarization with
pyannote.audio, VLM image understanding, diffusion, embeddings via
sentence-transformers, and fine-tuning — PyTorch and Transformers with PEFT
for LoRA adapters, TRL for supervised fine-tuning, bitsandbytes for
quantization and Accelerate for distributed runs. Go where the job is
orchestration and queueing, Python where the job is the model. Traefik and a
load balancer in front.

**Platform**
API gateway and key management, Stripe billing, status page, CRM
integrations, and OpenTelemetry tracing across services. Shared front-end and
back-end templates so a new service starts in the right shape instead of
drifting into its own.

## Adila

[**adila.co**](https://adila.co) is my own platform — an internal developer
platform I design and build end to end: identity, payments, mail, webhooks,
monitoring, queues, workflows, content, analytics and a CLI, plus the desktop
tooling around them. TypeScript and Go services, Go workers for the
throughput-bound paths.

[**Adila IDE**](https://github.com/adila-sh/coder-app) — code editor for
fullstack work. Go core with a Monaco front end over Wails, managed LSPs,
incremental indexing and no Electron overhead: 142ms cold start and sub-8ms
p99 keystroke latency.

[**stash**](https://github.com/adila-sh/stash-app) — minimal Git/GitHub
desktop client, Wails v3 + Go + React. → [stash.adila.co](https://stash.adila.co)

[**putch**](https://github.com/adila-sh/putch-app) — local-first HTTP client.
Collections are git-versionable YAML instead of a database, so a workspace is
just a repository. Pre/post request scripting sandboxed in goja.

[**walkmap**](https://github.com/adila-sh/walkmap) — codebase indexer for LLM
agents. Deterministic AST analysis on oxc-parser, no native binaries, runs on
Node or Bun.

[**@adila-sh/ui**](https://github.com/adila-sh/system-design) — design system
on the shadcn registry, published to GitHub Packages with Fumadocs +
TanStack Start docs. → [ds.adila.co](https://ds.adila.co)

[**pulse-sdk**](https://github.com/adila-sh/pulse-sdk) — isomorphic SDK for
analytics, feature flags, tracing and session replay. Zero runtime
dependencies.

[**dash-mcp**](https://github.com/adila-sh/dash-mcp) — MCP server that exposes
the control plane to AI clients, so deploys and logs are reachable in natural
language.

[**ops-worker**](https://github.com/adila-sh/ops-worker) — Go port of the
training worker. Gin handles the HTTP layer, SSE and job orchestration for a
static binary and instant cold start; the ML core stays in Python subprocesses
because it rides on PyTorch, Transformers, PEFT and TRL.

## Other work

[**wkix**](https://github.com/JohnnyBoySou/wkix) — the same indexing idea as
walkmap, written in Zig. Generates `.wkix` maps so an LLM can navigate a
repository without having to read all of it.

[**kit_s2mangas**](https://github.com/JohnnyBoySou/kit_s2mangas) — design
system and component library, published and consumed across the s2mangas
stack: [API](https://github.com/JohnnyBoySou/db_s2mangas) ·
[web](https://github.com/JohnnyBoySou/web_s2mangas) ·
[dashboard](https://github.com/JohnnyBoySou/dash_s2mangas)

**25stock** — inventory platform, end to end:
[API](https://github.com/JohnnyBoySou/fastify_25stock) ·
[AI service](https://github.com/JohnnyBoySou/ai_25stock) ·
[mobile app](https://github.com/JohnnyBoySou/app_25stock)

[**arch-config**](https://github.com/JohnnyBoySou/arch-config) — my Arch +
Hyprland setup, alongside
[ghostty-fish-config](https://github.com/JohnnyBoySou/ghostty-fish-config) and
[zed-theme](https://github.com/JohnnyBoySou/zed-theme).

## Stack

**Languages** — TypeScript · Python · Go · Rust · Zig · Java · Kotlin · C++

**Backend** — Bun · Elysia · Fastify · Express · FastAPI · Spring Boot

**Data** — PostgreSQL · Drizzle · Prisma · Redis · BullMQ

**Frontend** — React 19 · TanStack Start · Next.js · Vue · React Native + Expo

**ML** — PyTorch · Transformers · PEFT / LoRA · TRL · bitsandbytes ·
Accelerate · Datasets · Hugging Face Hub

**Speech and vision** — faster-whisper · CTranslate2 · pyannote.audio ·
sentence-transformers · ONNX Runtime · WebRTC VAD · diffusion · VLMs

**Agents** — LangGraph · MCP · OpenAI-compatible endpoints

**Real-time** — LiveKit · Asterisk / ARI · WebSockets · Socket.io

**Desktop and tooling** — Wails · Monaco · oxc · goja · MCP

**Infra** — Docker · Traefik · OpenTelemetry · S3 · GPU serving · GitHub Actions

## Contact

[joao.sousa@adila.co](mailto:joao.sousa@adila.co) · +55 47 98845-1732
