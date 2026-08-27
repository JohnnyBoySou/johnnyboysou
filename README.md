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

## Open source

[**wkix**](https://github.com/JohnnyBoySou/wkix) — codebase indexer written in
Zig. Generates `.wkix` maps so an LLM can navigate a repository without having
to read all of it.

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

**Infra** — Docker · Traefik · OpenTelemetry · S3 · GPU serving
