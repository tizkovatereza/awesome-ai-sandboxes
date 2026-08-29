# Awesome AI Sandboxes

A curated list of cloud sandbox providers for AI agents.

All information sourced exclusively from official docs and landing pages. PRs welcome, but please link to official sources only.

> **Why this list?** There's a lot of noise and inaccurate info about sandbox providers online. This repo exists to fix that. Every claim here links back to the provider's own docs or landing page.

![Awesome AI Sandboxes Market Map](assets/market-map.png)

---

## Sandbox Benchmarks

- [ComputeSDK Sandbox Leaderboard](https://www.computesdk.com/benchmarks/sandboxes/) - Live TTI (Time to Interactive) benchmarks across sandbox providers. Measures median, P95, P99 startup times and success rates. [Methodology & raw data on GitHub.](https://github.com/computesdk/benchmarks)
- [Agent Arena - Sandboxes](https://2027.dev/arena/sandboxes) - AI agent evaluation of sandbox providers. An autonomous coding agent (Claude Opus 4.6) discovers docs, installs packages, writes code, and verifies results. Ranked by time, cost, errors, and interruptions.
- [Tensorlake SQLite Benchmark](https://github.com/tensorlakeai/sandbox-sqlite-bench) - SQLite insert benchmarks (100k rows) across Tensorlake, Vercel, E2B, Daytona, and Modal comparing filesystem I/O performance.
- [microsandbox sandbox-bench](https://github.com/superradcompany/sandbox-bench) - Cold-start boot-time and guest-visible filesystem benchmarks across microsandbox, libkrun, Docker, Firecracker, and Cloud Hypervisor.

---

## Open Source

### [E2B](https://e2b.dev)
[Website](https://e2b.dev) | [Docs](https://e2b.dev/docs) | [GitHub](https://github.com/e2b-dev/E2B)

Secure cloud sandboxes for AI agents with real-world tools. Powered by Firecracker microVMs.

- **Isolation:** Firecracker microVMs
- **Key features:** Code interpreter SDK, custom sandbox templates, desktop sandboxes (computer use), up to 24h sessions, filesystem & network access, sub-200ms cold starts
- **Stateful:** Yes, persistent full environments, not just code execution
- **GPU:** No
- **BYOC / Self-host:** Yes (BYOC, on-prem, self-hosted)
- **SDKs:** Python, JavaScript/TypeScript
- **License:** Apache 2.0
- **Long-running:** Up to 1 hour (Hobby), up to 24 hours (Pro)
- **Pricing:** Free tier available, pay-as-you-go
- **Providing sandboxes for:** Hugging Face, Manus, Groq, Lindy, Genspark, Athena, Gumloop

---

### [Beam](https://beam.cloud)
[Website](https://beam.cloud) | [Docs](https://docs.beam.cloud) | [GitHub](https://github.com/beam-cloud/beta9)

Open-source GPU sandboxes with checkpoint restore, durable task queues, and serverless inference endpoints.

- **Isolation:** gVisor or runc (configurable)
- **Key features:** GPU checkpoint restore, Docker-in-Docker support, storage volumes, and per-second billing
- **Stateful:** Full memory and disk snapshots, plus distributed volumes for file storage
- **GPU:** Yes
- **BYOC / Self-host:** Yes (BYOC, on-prem, self-hosted)
- **SDKs:** Python, JavaScript/TypeScript
- **Long-running:** Unlimited (configurable auto-shutdown)
- **License:** AGPL 3.0
- **Pricing:** $30 monthly free tier, pay-as-you-go

---

### [Daytona](https://daytona.io)
[Website](https://daytona.io) | [Docs](https://daytona.io/docs) | [GitHub](https://github.com/daytonaio/daytona)

Secure and elastic infrastructure for running AI-generated code. Sub-90ms sandbox creation.

- **Isolation:** Secure isolated runtimes
- **Key features:** Sub-90ms creation, massive parallelization, file/git/LSP/execute APIs, environment snapshots, computer use (Linux, macOS, Windows), Docker-in-Docker, volumes for shared data
- **Stateful:** Yes, sandboxes run indefinitely, built for long-running and persistent agents
- **GPU:** Yes (Nvidia H100, RTX PRO 6000)
- **BYOC / Self-host:** Yes (customer-managed compute, on-prem)
- **SDKs:** Python, TypeScript
- **Long-running:** Unlimited (auto-stop after 15min idle by default, configurable to run indefinitely)
- **License:** Apache 2.0
- **Pricing:** Pay-as-you-go per second, $200 free compute included
- **Providing sandboxes for:** LangChain, Turing, AfterQuery, Mintlify, SambaNova, Elementor, Writer, Mastra, Prosus, Tessl, Snorkel AI, CoreWeave, Parabola

---

### [microsandbox](https://microsandbox.dev)
[Website](https://microsandbox.dev) | [Docs](https://docs.microsandbox.dev) | [GitHub](https://github.com/superradcompany/microsandbox)

Secure, programmable microVMs for AI agents. Local-first, with a 1:1 interoperable managed cloud in private beta.

- **Isolation:** libkrun microVMs, every sandbox gets its own kernel (KVM on Linux, Hypervisor.framework on macOS; Windows via WSL2)
- **Key features:** Programmable from the ground up (networks, secrets, fs, init, kernel), real secrets never enter the VM, sub-100ms boots, 1:1 interoperable local and cloud sandboxes, any OCI image, Docker-in-VM
- **Stateful:** Yes, named sandboxes with start/stop lifecycle and disk snapshots
- **GPU:** No
- **Embeddable:** Yes, SDK with the runtime built in
- **BYOC / Self-host:** Yes (self-host the runtime)
- **SDKs:** Rust, Python, TypeScript, Go, CLI (`msb`)
- **License:** Apache 2.0 (local runtime)
- **Pricing:** Free locally, cloud pricing out post private beta

---

### [OpenComputer](https://opencomputer.dev)
[Website](https://opencomputer.dev) | [Docs](https://docs.opencomputer.dev) | [GitHub](https://github.com/diggerhq/opencomputer)

Persistent cloud VMs for AI agents by Digger. Full Linux machines that hibernate when idle and wake in seconds.

- **Isolation:** Full VMs with own filesystem, network, and process space
- **Key features:** Always-on persistent VMs, elastic compute (resize CPU/memory at runtime), hibernate & wake, instant checkpoints (snapshot/fork/rollback), 20GB disk per VM
- **Stateful:** Yes, state survives across sessions, VMs stay alive until explicitly stopped
- **GPU:** No
- **BYOC / Self-host:** Not specified
- **SDKs:** API-based (works with Claude Agent SDK and others)
- **Pricing:** Pay-per-minute, pre-booked ($0.024/h) or instant ($0.12/h) for 2GB/1vCPU

---

### [OpenSandbox](https://open-sandbox.ai) (by Alibaba)
[Website](https://open-sandbox.ai) | [GitHub](https://github.com/alibaba/OpenSandbox)

Production-grade sandbox runtime for AI agents.

- **Isolation:** Docker/Kubernetes runtimes
- **Key features:** Unified sandbox APIs, supports coding agents, GUI agents, agent evaluation, AI code execution, and RL training
- **GPU:** Not specified
- **BYOC / Self-host:** Yes (self-hosted by design)
- **License:** Apache 2.0
- **Pricing:** Free (open source)

---

### [SmolVM](https://celesto.ai) (by Celesto AI)
[Website](https://celesto.ai) | [Docs](https://docs.celesto.ai/smolvm) | [GitHub](https://github.com/CelestoAI/SmolVM)

Open source AI sandbox with flexible microVM backends - ships with QEMU and Firecracker.

- **Isolation:** Full VMs with their own filesystem, network, and process space
- **Key features:** Run Ubuntu, Windows, or any OS, mount local file systems, snapshots to restore the state, and network control for egress
- **Stateful:** Yes, stop and resume at any point in time
- **GPU:** Yes (powered by QEMU)
- **BYOC / Self-host:** Yes, built to self-host
- **SDKs:** Python SDK and CLI (`pip install smolvm`)
- **Pricing:** Free (open source)

---

### [Superserve](https://www.superserve.ai)
[Website](https://www.superserve.ai) | [Docs](https://docs.superserve.ai) | [GitHub](https://github.com/superserve-ai/superserve)

Persistent and secure sandboxes for AI agents, powered by Firecracker microVMs.

- **Isolation:** Firecracker microVMs
- **Long-running:** Unlimited session duration
- **Key features:** <200ms startup, unlimited session duration, credentials broker (API keys never exposed to agents), versioned filesystem with snapshot/rollback, per-sandbox egress rules
- **Stateful:** Yes, full memory and disk state preserved on pause; sessions persist indefinitely
- **GPU:** No
- **BYOC / Self-host:** Yes (Enterprise)
- **SDKs:** TypeScript (`@superserve/sdk`), Python (`superserve`)
- **License:** Apache 2.0
- **Pricing:** Free tier, usage-based (vCPU/hour, GiB/hour)

---

### [Steel.dev](https://steel.dev)
[Website](https://steel.dev) | [Docs](https://docs.steel.dev) | [GitHub](https://github.com/steel-dev/steel-browser)

Open-source browser API for AI agents and apps. Sandboxed Chrome sessions with anti-detection, session viewer, and computer-use integrations.

- **Isolation:** Docker containers (Chrome via Puppeteer/CDP)
- **Key features:** Up to 24h sessions, auto CAPTCHA solving, proxy chain management, stealth + fingerprint plugins, session viewer (live and recorded), cookie/localStorage persistence, computer-use integrations (Claude, Gemini, OpenAI), agent framework integrations (LangGraph, CrewAI, Pydantic AI, Vercel AI SDK)
- **Stateful:** Yes, session state (cookies, local storage) persists and can be reused across sessions
- **GPU:** Not specified
- **BYOC / Self-host:** Yes (self-host via Docker; Steel Cloud also available)
- **SDKs:** Python (`steel-sdk`), Node.js/TypeScript (`steel-sdk`), CLI
- **License:** Apache 2.0
- **Pricing:** Free tier ($10/month in credits), paid tiers $29–$499/month with included browser hours and bandwidth

---

### [h5i](https://github.com/h5i-dev/h5i)
[GitHub](https://github.com/h5i-dev/h5i)

Open-source CLI that runs multiple coding agents on one task, each in its own sealed git-worktree sandbox to prevent file, branch, and port clashes.

- **Isolation:** Per-agent sealed git worktrees (one isolated worktree per agent)
- **Key features:** Runs multiple coding agents (Claude Code, Codex) on the same task, per-agent sealed sandboxes with no file/branch/port clashes, cross-agent peer review, neutral verifier that replays and tests each candidate then merges the one that passes, run metadata versioned in the repo under `refs/h5i/*`
- **Stateful:** Yes (runs versioned in your Git under `refs/h5i/*`)
- **GPU:** Not specified
- **BYOC / Self-host:** Yes (runs locally, no SaaS)
- **SDKs:** CLI (Rust)
- **License:** Apache 2.0
- **Pricing:** Free (open source)

---

### [distro-rig-vps](https://github.com/shafir-info/distro-rig-vps)
[Docs](https://github.com/shafir-info/distro-rig-vps/wiki) | [GitHub](https://github.com/shafir-info/distro-rig-vps)

Self-hosted disposable Linux VMs for coding agents that need real guest root without giving the driving account host hypervisor privileges.

- **Isolation:** Full KVM/libvirt VMs with their own kernel and real PID 1 systemd
- **Key features:** Root inside the guest, no host sudo/`/dev/kvm`/libvirt access for the agent account, deny-by-default guest egress, local package cache, copy-on-write pinned bases, snapshots and clean recreate
- **Cold start:** Not specified
- **Max session:** Not specified
- **Snapshots / Forking:** Yes (snapshot only)
- **Stateful:** Yes
- **GPU:** Not specified
- **BYOC / Self-host:** Yes
- **SDKs:** CLI (`rigctl`)
- **License:** GPL-3.0-or-later
- **Pricing:** Free (open source)

---

## Closed Source

### [Baponi](https://baponi.ai)
[Website](https://baponi.ai) | [Docs](https://baponi.ai/docs) | [GitHub](https://github.com/baponi/baponi-sdk)

Sandboxes for AI agents billed only when code runs. Sessions persist for weeks at zero idle cost; your S3/GCS/Azure bucket mounts as a local filesystem.

- **Isolation:** nsjail with Linux namespace isolation (mount, PID, network, IPC, UTS), seccomp-bpf syscall allowlist, and zero Linux capabilities
- **Key features:** Zero idle cost (billed per execution, nothing runs or bills between agent calls), sessions resume days or weeks later with installed packages, env vars, and files intact (no pause/resume orchestration to build), your own S3/GCS/Azure bucket mounted as a local filesystem so pandas and CLI tools read cloud data unmodified (no upload/download step, data never leaves your bucket), bucket credentials kernel-isolated outside the sandbox, MCP server (Claude Desktop, Cursor, Windsurf, any MCP client) + REST API + Python SDK, LangChain / OpenAI / Anthropic / Gemini / CrewAI integrations, custom OCI images, per-sandbox kernel-level network policies
- **Stateful:** Yes. State persists between calls with a single session parameter; sessions resume days or weeks later. Agents never manage container lifecycle.
- **Long-running:** Sessions persist across calls for days or weeks at zero idle cost; single executions up to 60s (Free), 1 hour (Pro), unlimited (Enterprise)
- **GPU:** Not specified
- **BYOC / Self-host:** Yes (Enterprise). One Helm chart deploys the entire platform in your own Kubernetes cluster and VPC (GKE, EKS, AKS, OpenShift, bare-metal); air-gapped environments supported; bring your own OIDC provider and database; operational in hours.
- **SDKs:** Python (`pip install baponi`); also accessible via MCP and REST API
- **Pricing:** Per execution, not per second, with no idle charges. Free ($0, 1,000 credits/month, no credit card); Pro ($97/month, 10,000 credits included, then $1.00 per additional 1K); Enterprise (custom, self-hosted)

---

### [Blaxel](https://blaxel.ai)
[Website](https://blaxel.ai) | [Docs](https://docs.blaxel.ai) | [GitHub](https://github.com/blaxel-ai)

The perpetual sandbox platform. Sandboxes auto-suspend when idle and resume from standby in ~25ms with full memory state.

- **Isolation:** Individual microVMs with root filesystem in memory
- **Key features:** 25ms resume from standby, auto-suspend to $0 compute, 50k+ concurrent sandboxes, Agent Drive (distributed filesystem), volumes for long-term data, agent + MCP server co-hosting on same backbone
- **Stateful:** Yes, full memory + filesystem snapshot on suspend, persists forever
- **GPU:** No
- **BYOC / Self-host:** No
- **SDKs:** TypeScript, Python
- **Long-running:** Auto-suspend after idle, resume in ~25ms; TTL configurable
- **Pricing:** Pay for active compute only, $0 on standby. SOC 2, HIPAA, ISO 27001
- **Providing sandboxes for:** Shortwave, Strapi, Webflow

---

### [Box](https://box.ascii.dev) (by ascii.dev)
[Website](https://box.ascii.dev) | [Docs](https://docs.ascii.dev)

Simple and affordable full VM sandbox for agents.

- **Isolation:** Dedicated Linux (Ubuntu) VMs, one IPv4 per VM
- **Long-running:** No session timeout; timed extension up to 30 days
- **Key features:** Agent-friendly CLI, SSH/SCP access, fork, stop to pause billing, no session timeout, public HTTPS hosting (full TCP/UDP), 60fps desktop streaming + computer-use skills & CLI for agents, Docker in-VM, built-in agent harness (Claude Code, Codex)
- **Stateful:** Yes, VMs persist; snapshot/fork and stop/resume
- **GPU:** No
- **BYOC / Self-host:** No (managed service, EU regions)
- **SDKs:** CLI (`box`) with `--json` JSONL output for scripting
- **Pricing:** $20/month minimum; $20 buys 2,000,000 VM-seconds (~555h) of a dedicated 4 vCPU / 8 GB VM, billed by the second

---

### [Cloudflare Sandboxes](https://developers.cloudflare.com/sandbox/)
[Docs](https://developers.cloudflare.com/sandbox/) | [GitHub](https://github.com/cloudflare/sandbox-sdk) | [Blog](https://blog.cloudflare.com/sandbox-ga/)

Persistent, isolated environments powered by Cloudflare Containers. Full computer for AI agents with shell, filesystem, and background processes.

- **Isolation:** Containers (Cloudflare Containers)
- **Key features:** Snapshots with R2 storage, secure credential injection via egress proxy, PTY terminal support, persistent code interpreters, live preview URLs, filesystem watching, active CPU pricing (pay only for used cycles)
- **Stateful:** Yes, auto-sleep on idle and wake on request, snapshots for full disk state
- **GPU:** No
- **BYOC / Self-host:** No (runs on Cloudflare's network)
- **SDKs:** JavaScript/TypeScript (`@cloudflare/sandbox`)
- **Pricing:** Active CPU pricing, up to 15k concurrent instances on standard plan

---

### [CodeSandbox](https://codesandbox.io)
[Website](https://codesandbox.io) | [Docs](https://codesandbox.io/docs) | [GitHub](https://github.com/codesandbox)

Cloud sandbox platform (now part of Together AI) for isolated microVM environments for AI agents.

- **Isolation:** MicroVM-based sandboxes
- **Key features:** Snapshot/restore in <2s, VM cloning in <2s, millions of concurrent VMs, customizable hibernation, forking for A/B testing agents, SOC 2 Type II
- **Stateful:** Yes, snapshot and restore
- **GPU:** No
- **BYOC / Self-host:** No
- **SDKs:** TypeScript/JavaScript (`@codesandbox/sdk`)
- **Pricing:** Free tier (40h VM credits/month), Scale from $170/month
- **Providing sandboxes for:** Algolia, Microsoft, Intel, NVIDIA, Atlassian, Uber, Stripe, Zendesk, Adobe, Shopify

---

### [Freestyle](https://freestyle.sh)
[Website](https://freestyle.sh) | [Docs](https://freestyle.sh/docs) | [GitHub](https://github.com/freestyle-sh/freestyle-sh)

Full Linux VMs for AI agents with built-in Git, live forking, and pause/resume. Sub-600ms provisioning.

- **Isolation:** Full Linux VMs with KVM, nested virtualization support
- **Key features:** <600ms VM provisioning, live forking (clone running VM in milliseconds), pause & resume, built-in multi-tenant Git with branching/diffs/webhooks, custom domains, VPCs, SSH access, high IO, largest VMs/most memory + disk available in public tiers
- **Stateful:** Yes, persistent VMs with suspend/resume, snapshots
- **Long-running:** Unlimited (configurable idle timeout, can be set to null for indefinite)
- **GPU:** Not specified
- **BYOC / Self-host:** Not specified
- **SDKs:** TypeScript (`freestyle`)
- **Pricing:** Free tier (10 concurrent VMs), Hobby $50/month, Pro $500/month
- **Providing sandboxes for:** Onlook, Wordware, HeroUI, Rork, Vibeflow

---

### [Islo](https://islo.dev)
[Website](https://islo.dev) | [Docs](https://docs.islo.dev/overview) | [GitHub](https://github.com/islo-labs/python-sdk)

Long-running AI sandboxes for coding agents. Persistent microVM environments with security controls for connected agent workflows.

- **Isolation:** Dedicated microVMs (hardware-level isolation)
- **Key features:** Gateway profiles (network policy, credential injection, LLM-as-judge filters), cloud roles (AWS IAM assume-role via STS), first-class coding agent support, native integrations (GitHub, Slack, Linear, Jira), end-customer BYOC for multi-tenant agent products, snapshots
- **Stateful:** Yes, persistent environments with pause/resume and snapshot/restore
- **GPU:** Yes
- **BYOC / Self-host:** Yes (your cloud or your customer's cloud)
- **SDKs:** Python, TypeScript, Go, Rust
- **Pricing:** Usage-based ($0.07/CPU-hour, $0.04/GB-hour, $0.0007/GB-hour storage)

---

### [Leap0](https://leap0.dev)
[Website](https://leap0.dev) | [Docs](https://leap0.dev/docs) | [GitHub](https://github.com/leap0-dev)

Cloud sandboxes for AI agents. Spin up Firecracker microVMs in ~100ms.

- **Isolation:** Firecracker microVMs with Jailer
- **Key features:** ~100ms cold start, any container image as template, checkpoint/restore snapshots, pause/resume, desktop (computer use), Git integration, LSP support, network firewall with credential brokering, object storage mounts
- **Stateful:** Yes, pause/resume, checkpoint snapshots with restore
- **GPU:** No
- **BYOC / Self-host:** Yes (BYOC and on-premises)
- **SDKs:** Python, TypeScript
- **Pricing:** Free during public preview, $0.0504/vCPU-hour, $0.0162/GB-hour

---

### [Modal](https://modal.com)
[Website](https://modal.com) | [Docs](https://modal.com/docs) | [GitHub](https://github.com/modal-labs)

Serverless cloud platform for AI with sandboxes, GPU compute, and sub-second cold starts.

- **Isolation:** Sandboxes with ephemeral isolated environments
- **Key features:** Pay-per-second billing, sub-second container boots, autoscale 0 to 1000+ GPUs, SOC2 & HIPAA compliant
- **Stateful:** Sandboxes are ephemeral; volumes available for persistence
- **Long-running:** Default 5 minutes, configurable up to 24 hours
- **GPU:** Yes (H100, A100, L40S, A10, L4, T4, B200, H200)
- **BYOC / Self-host:** No
- **SDKs:** Python (primary), TypeScript/Go via libmodal
- **Pricing:** Pay-as-you-go, $30/month free credits on Starter plan
- **Providing sandboxes for:** Runway, Suno, Lovable, Quora, Substack, Ramp, DoorDash, Cognition

---

### [Northflank](https://northflank.com)
[Website](https://northflank.com) | [Docs](https://northflank.com/docs)

Full-stack AI infrastructure platform with microVM-backed sandboxes. Runs on Northflank's managed cloud or deploys into your own cloud account.

- **Isolation:** Kata Containers (Cloud Hypervisor), Firecracker, or gVisor (user-space kernel isolation)
- **Key features:** Sub-1s boot, any OCI container image, persistent volumes, public port exposure, built-in managed databases, preview environments, CI/CD pipelines
- **Stateful:** Optional — ephemeral by default, persistent with attached volumes
- **CPU/GPU:** Yes — CPU and GPU sandboxes (L4, A100, H100, on Northflank compute or BYOC)
- **BYOC / Self-host:** Yes (AWS, GCP, Azure, Oracle, Civo, CoreWeave, bare-metal, on-prem)
- **SDKs:** JavaScript/TypeScript, Python, REST API, CLI
- **Compliance:** SOC 2 Type II
- **Pricing:** $0.01667/vCPU-hr, $0.00833/GB-hr, billed per second. BYOC available self-serve at $0.01389/vCPU-hr + $0.00139/GB-hr management fee

---

### [Morph](https://morph.so)
[Website](https://morph.so) | [GitHub](https://github.com/morph-labs)

Cloud infrastructure for AI agents with instant environment branching and burst scalability.

- **Isolation:** Full VM instances (not containers)
- **Key features:** Instant environment branching and snapshot/restore, burst scalability (millisecond deploys), used for SWE-Bench, RL rollouts, and computer-use agents
- **Stateful:** Yes, snapshot and restore
- **GPU:** Not specified
- **BYOC / Self-host:** Not specified
- **SDKs:** Python, TypeScript
- **Pricing:** Not publicly listed

---

### [Novita AI Agent Sandbox](https://novita.ai/sandbox)
[Website](https://novita.ai/sandbox) | [Docs](https://novita.ai/docs/guides/sandbox-your-first-agent-sandbox) | [Pricing](https://novita.ai/docs/guides/sandbox-pricing)

Fast, secure cloud sandboxes for AI agents to run code, browse the web, use desktop environments, call external APIs, and keep long-running tasks alive across sessions.

- **Isolation:** Isolated cloud sandbox environments with system-level separation
- **Key features:** Sub-200ms average startup, high-concurrency sandbox creation, code execution, browser automation, full desktop computer use, live session viewing, external API access, persistent sessions, custom sandbox templates, and E2B SDK compatibility
- **Stateful:** Yes, sandboxes can pause and resume with filesystem and memory state preserved
- **GPU:** No
- **BYOC / Self-host:** Not supported
- **SDKs:** Python, JavaScript/TypeScript, CLI, and E2B-compatible SDKs
- **Pricing:** Usage-based, billed per second by vCPU and memory; templates are currently free

---

### [Qbox](https://qbox.sh)
[Website](https://qbox.sh) | [Docs](https://qbox.sh/docs)

Self-hostable Firecracker microVM sandbox orchestrator for AI agents and untrusted code. Runs on your own Linux hosts.

- **Isolation:** Firecracker microVMs (full VM with own kernel, hardware-level isolation)
- **Key features:** Self-hosted by design, persistent volumes, port forwarding with HTTPS previews, browser sessions over CDP, templates from any OCI image, operator dashboard, single-host installer
- **Stateful:** Sandboxes are ephemeral, mount object storage volumes for persistence
- **GPU:** No
- **BYOC / Self-host:** Yes, self-hosted by default (bare metal, on-prem hypervisors, your own cloud VMs)
- **SDKs:** Python (`qbox-sh`), REST + WebSocket API, CLI
- **License:** Closed source
- **Pricing:** Free to self-host

---

### [Runloop](https://runloop.ai)
[Website](https://runloop.ai) | [Docs](https://docs.runloop.ai) | [GitHub](https://github.com/runloopai)

Devbox infrastructure for building, benchmarking, and shipping AI coding agents at enterprise scale.

- **Isolation:** Micro-VM sandboxes on custom bare-metal hypervisor
- **Key features:** 2x faster vCPUs, sub-2s startup for 10GB images, 10k+ parallel sandboxes, snapshot/branch state (Git for Agent State), suspend & resume, built-in SWE-Bench
- **Stateful:** Yes, snapshot and branch sandbox state
- **GPU:** Not specified
- **BYOC / Self-host:** Yes (deploy-to-VPC option)
- **SDKs:** Python, TypeScript
- **Pricing:** Free tier with $50 credits, usage-based compute

---

### [Sprites](https://sprites.dev) (by Fly.io)
[Website](https://sprites.dev) | [Docs](https://docs.sprites.dev) | [API](https://sprites.dev/api)

Persistent, hardware-isolated execution environments. A Sprite is a full Linux computer with stateful filesystem, unlimited checkpoints, and granular billing.

- **Isolation:** Firecracker VMs with isolated networking
- **Key features:** Persistent ext4 filesystem across runs, live checkpoints (~300ms, copy-on-write), dynamic resources (up to 8 CPUs / 16GB RAM), HTTP access with unique URLs per Sprite, L3 network egress policies, auto-activate on request
- **Stateful:** Yes, filesystem persists between runs, full environment checkpointed
- **GPU:** No
- **BYOC / Self-host:** No
- **SDKs:** JavaScript, Go, CLI, REST API
- **Pricing:** Pay for actual usage: $0.07/CPU-hour, $0.04375/GB-hour memory, $30 trial credits

---

### [Tensorlake](https://tensorlake.ai)
[Website](https://tensorlake.ai) | [Docs](https://docs.tensorlake.ai) | [GitHub](https://github.com/tensorlakeai/tensorlake)

Lightspeed AI-native sandboxes. Stateful compute for durable agentic loops and isolated tool/code execution, powered by Firecracker and CloudHypervisor.

- **Isolation:** Firecracker / CloudHypervisor microVMs
- **Key features:** <300ms startup, dynamic CPU/memory/disk sizing per API call, snapshot/clone/replicate running sandboxes, live migration, durable orchestration with fan-out/retries/queues, RL environment support (10k+ concurrent)
- **Stateful:** Yes, named sandboxes with suspend/resume in exact state
- **Long-running:** Idle timeout 2h (Free), 24h (On-Demand)
- **GPU:** Not specified
- **BYOC / Self-host:** Yes (deploy in your own AWS/GCP/Azure account)
- **SDKs:** Python, TypeScript
- **Pricing:** Free tier, usage-based (vCPU/hour, GiB-hour). SOC 2 Type II, HIPAA
- **Providing sandboxes for:** SIXT, Reliant AI, Novis AI

---

### [Vercel Sandbox](https://vercel.com/sandbox)
[Website](https://vercel.com/sandbox) | [Docs](https://vercel.com/docs/sandbox) | [GitHub](https://github.com/vercel/sandbox)

Secure Firecracker microVMs for running untrusted or AI-generated code on Vercel. Millisecond startup with Active CPU pricing.

- **Isolation:** Firecracker microVMs (each sandbox gets its own filesystem and network)
- **Key features:** Millisecond cold starts, persistent sandboxes (auto-save state on stop), snapshots, network firewall with credentials brokering, up to 8 vCPUs / 2GB RAM per vCPU, live preview URLs (up to 4 ports), Node.js and Python runtimes
- **Stateful:** Yes, persistent sandboxes with auto-save and snapshot/restore
- **Long-running:** Default 5 minutes; up to 45 minutes (Hobby), up to 5 hours (Pro/Enterprise)
- **GPU:** No
- **BYOC / Self-host:** No (runs on Vercel)
- **SDKs:** JavaScript/TypeScript (`@vercel/sandbox`), Python (`vercel.sandbox`), CLI
- **Pricing:** Active CPU pricing (pay only when code runs), up to 5h max session on Pro/Enterprise
- **Providing sandboxes for:** Xata, Cua AI

---

### [InstaVM](https://instavm.io)
[Website](https://instavm.io) | [Docs](https://instavm.io/docs) | [Pricing](https://instavm.io/pricing) | [GitHub](https://github.com/instavm/coderunner)

Cloud microVM platform for AI agents. Boots isolated Firecracker sandboxes for code execution, browser automation, app previews, and persistent VM workflows.

- **Isolation:** Firecracker microVMs with dedicated Linux kernel, filesystem, memory, CPU, and configurable egress
- **Key features:** Sub-200ms cold boots, <10ms warm session reuse, <500ms snapshot restore, persistent sessions, volumes, VM clone/fan-out, browser automation and computer use, public/private shares and custom domains
- **Stateful:** Yes, sessions persist between execute calls; ephemeral by default, with volumes and snapshots for durable state
- **GPU:** No
- **BYOC / Self-host:** Yes
- **SDKs:** Python (`instavm`), TypeScript, CLI (`instavm`), REST API
- **Pricing:** Free plan with $50 credits and $0 base plus usage; Pro starts at $100/month base plus usage

---

### [Declaw](https://declaw.ai)
[Website](https://declaw.ai) | [Docs](https://docs.declaw.ai)

Firecracker microVM sandboxes with a 6-stage security pipeline — PII redaction, prompt injection defense, network policies, and audit logging.

- **Isolation:** Firecracker microVMs with dedicated network namespace per sandbox
- **Key features:** 6-stage security pipeline (network policies, domain filtering, TLS interception, guardrails, transformations, audit logging), sub-200ms cold start, 8 pre-built templates, custom templates from Dockerfiles, MCP server sandboxing via CLI, PTY terminal access, port proxy
- **Stateful:** Yes, snapshots (memory + filesystem + process state), volumes, pause/resume
- **GPU:** No
- **BYOC / Self-host:** Yes (self-hosted on AWS or GCP with Terraform + Helm)
- **SDKs:** Python, TypeScript, Go, CLI (`declaw`)
- **Long-running:** Up to 1 hour (Free), 72 hours (Pro), 7 days (Enterprise)
- **Pricing:** $300 in free credits, usage-based

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for the entry template and source policy.

**Key rules:**
1. Only include products that **provide sandboxes as a service** to others, not tools built for internal use only
2. All information must come from official sources (docs, landing pages, official GitHub repos)
3. No blog posts, tweets, or third-party articles as primary sources
4. Keep entries factual, no marketing fluff
5. Tell us a bit about yourself in the PR description. We favor contributions from people who actually build with sandboxes or are otherwise involved in the space, to keep the quality of this list high

## License

[CC BY-NC-SA 4.0](LICENSE.md)
