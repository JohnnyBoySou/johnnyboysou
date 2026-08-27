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

**Developer tooling**
The things a platform needs around it: analytics with feature flags and
session replay, webhook delivery, job queues, workflow automation, an MCP
server so the control plane answers to natural language, a CLI, and desktop
clients built in Go over Wails — an editor on Monaco, a Git client, and a
local-first HTTP client whose collections are git-versionable YAML instead of
a database. Plus a codebase indexer on oxc-parser that gives LLM agents a
deterministic map of a repository, and a design system published on the
shadcn registry.

## Stack

**Languages** — TypeScript · Python · Go · Rust · Zig · Java · Kotlin · C++

**Backend** — Bun · Elysia · Fastify · Express · Gin · FastAPI · Spring Boot

**Data** — PostgreSQL · Drizzle · Prisma · Redis · BullMQ

**Frontend** — React 19 · TanStack Start · Next.js · Vue · React Native + Expo ·
shadcn/ui · Tailwind · Vite

**ML** — PyTorch · Transformers · PEFT / LoRA · TRL · bitsandbytes ·
Accelerate · Datasets · Hugging Face Hub

**Speech and vision** — faster-whisper · CTranslate2 · pyannote.audio ·
sentence-transformers · ONNX Runtime · WebRTC VAD · diffusion · VLMs

**Agents** — LangGraph · MCP · OpenAI-compatible endpoints

**Real-time** — LiveKit · Asterisk / ARI · WebSockets · Socket.io

**Desktop and tooling** — Wails · Monaco · oxc · goja · MCP · Fumadocs

**Infra** — Docker · Traefik · OpenTelemetry · S3 · GPU serving ·
GitHub Actions · GitHub Packages

## Contact

[joao.sousa@adila.co](mailto:joao.sousa@adila.co) · +55 47 98845-1732
