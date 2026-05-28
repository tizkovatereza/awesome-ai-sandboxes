# Awesome AI Sandboxes

A curated list of cloud sandbox providers for AI agents.

All information sourced exclusively from official docs and landing pages. PRs welcome, but please link to official sources only.

> **Why this list?** There's a lot of noise and inaccurate info about sandbox providers online. This repo exists to fix that. Every claim here links back to the provider's own docs or landing page.

![Awesome AI Sandboxes Market Map](assets/map-white.png)

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
- **Pricing:** Free tier available, pay-as-you-go

---

### [Beam](https://beam.cloud)

[Website](https://beam.cloud) | [Docs](https://docs.beam.cloud) | [GitHub](https://github.com/beam-cloud/beta9)

Open-source GPU sandboxes with checkpoint restore, durable task queues, and serverless inference endpoints. 

- **Isolation:** gVisor or runc (configurable)
- **Key features:** 
GPU checkpoint restore, Docker-in-Docker support, storage volumes, and per-second billing. 
- **Stateful:** Full memory and disk snapshots, plus distributed volumes for file storage
- **GPU:** Yes
- **BYOC / Self-host:** Yes (BYOC, on-prem, self-hosted)
- **SDKs:** Python, JavaScript/TypeScript
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
- **License:** Apache 2.0
- **Pricing:** Pay-as-you-go per second, $200 free compute included

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

### [Superserve](https://www.superserve.ai)
[Website](https://www.superserve.ai) | [Docs](https://docs.superserve.ai) | [GitHub](https://github.com/superserve-ai/superserve)

Persistent and secure sandboxes for AI agents, powered by Firecracker microVMs.

- **Isolation:** Firecracker microVMs
- **Key features:** <200ms startup, unlimited session duration, credentials broker (API keys never exposed to agents), versioned filesystem with snapshot/rollback, per-sandbox egress rules
- **Stateful:** Yes, full memory and disk state preserved on pause; sessions persist indefinitely
- **GPU:** No
- **BYOC / Self-host:** Yes (Enterprise)
- **SDKs:** TypeScript (`@superserve/sdk`), Python (`superserve`)
- **License:** Apache 2.0
- **Pricing:** Free tier, usage-based (vCPU/hour, GiB/hour)

---

## Closed Source

### [Blaxel](https://blaxel.ai)
[Website](https://blaxel.ai) | [Docs](https://docs.blaxel.ai) | [GitHub](https://github.com/blaxel-ai)

The perpetual sandbox platform. Sandboxes auto-suspend when idle and resume from standby in ~25ms with full memory state.

- **Isolation:** Individual microVMs with root filesystem in memory
- **Key features:** 25ms resume from standby, auto-suspend to $0 compute, 50k+ concurrent sandboxes, Agent Drive (distributed filesystem), volumes for long-term data, agent + MCP server co-hosting on same backbone
- **Stateful:** Yes, full memory + filesystem snapshot on suspend, persists forever
- **GPU:** No
- **BYOC / Self-host:** No
- **SDKs:** TypeScript, Python
- **Pricing:** Pay for active compute only, $0 on standby. SOC 2, HIPAA, ISO 27001

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

### [Freestyle](https://freestyle.sh)
[Website](https://freestyle.sh) | [Docs](https://freestyle.sh/docs) | [GitHub](https://github.com/freestyle-sh/freestyle-sh)

Full Linux VMs for AI agents with built-in Git, live forking, and pause/resume. Sub-600ms provisioning.

- **Isolation:** Full Linux VMs with KVM, nested virtualization support
- **Key features:** <600ms VM provisioning, live forking (clone running VM in milliseconds), pause & resume, built-in multi-tenant Git with branching/diffs/webhooks, custom domains, VPCs, SSH access, high IO, largest VMs/most memory + disk available in public tiers.
- **Stateful:** Yes, persistent VMs with suspend/resume, snapshots
- **GPU:** Not specified
- **BYOC / Self-host:** Not specified
- **SDKs:** TypeScript (`freestyle`)
- **Pricing:** Free tier (10 concurrent VMs), Hobby $50/month, Pro $500/month

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

### [Modal](https://modal.com)
[Website](https://modal.com) | [Docs](https://modal.com/docs) | [GitHub](https://github.com/modal-labs)

Serverless cloud platform for AI with sandboxes, GPU compute, and sub-second cold starts.

- **Isolation:** Sandboxes with ephemeral isolated environments
- **Key features:** Pay-per-second billing, sub-second container boots, autoscale 0 to 1000+ GPUs, SOC2 & HIPAA compliant
- **Stateful:** Sandboxes are ephemeral; volumes available for persistence
- **GPU:** Yes (H100, A100, L40S, A10, L4, T4, B200, H200)
- **BYOC / Self-host:** No
- **SDKs:** Python (primary), TypeScript/Go via libmodal
- **Pricing:** Pay-as-you-go, $30/month free credits on Starter plan

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

### [Vercel Sandbox](https://vercel.com/sandbox)
[Website](https://vercel.com/sandbox) | [Docs](https://vercel.com/docs/sandbox) | [GitHub](https://github.com/vercel/sandbox)

Secure Firecracker microVMs for running untrusted or AI-generated code on Vercel. Millisecond startup with Active CPU pricing.

- **Isolation:** Firecracker microVMs (each sandbox gets its own filesystem and network)
- **Key features:** Millisecond cold starts, persistent sandboxes (auto-save state on stop), snapshots, network firewall with credentials brokering, up to 8 vCPUs / 2GB RAM per vCPU, live preview URLs (up to 4 ports), Node.js and Python runtimes
- **Stateful:** Yes, persistent sandboxes with auto-save and snapshot/restore
- **GPU:** No
- **BYOC / Self-host:** No (runs on Vercel)
- **SDKs:** JavaScript/TypeScript (`@vercel/sandbox`), Python (`vercel.sandbox`), CLI
- **Pricing:** Active CPU pricing (pay only when code runs), up to 5h max session on Pro/Enterprise

---

### [Tensorlake](https://tensorlake.ai)
[Website](https://tensorlake.ai) | [Docs](https://docs.tensorlake.ai) | [GitHub](https://github.com/tensorlakeai/tensorlake)

Lightspeed AI-native sandboxes. Stateful compute for durable agentic loops and isolated tool/code execution, powered by Firecracker and CloudHypervisor.

- **Isolation:** Firecracker / CloudHypervisor microVMs
- **Key features:** <300ms startup, dynamic CPU/memory/disk sizing per API call, snapshot/clone/replicate running sandboxes, live migration, durable orchestration with fan-out/retries/queues, RL environment support (10k+ concurrent)
- **Stateful:** Yes, named sandboxes with suspend/resume in exact state
- **GPU:** Not specified
- **BYOC / Self-host:** Yes (deploy in your own AWS/GCP/Azure account)
- **SDKs:** Python, TypeScript
- **Pricing:** Free tier, usage-based (vCPU/hour, GiB-hour). SOC 2 Type II, HIPAA

---

### [Zerops](https://zerops.io)
[Website](https://zerops.io) | [Docs](https://docs.zerops.io) | [GitHub](https://github.com/zeropsio) | [ZCP](https://zerops.io/zcp)

Developer-first cloud platform with ZCP for coding agents. Agents work inside real Zerops projects with managed services, private networking, deploys, logs, and verification exposed through MCP.

- **Isolation:** Linux system containers on project-private networks
- **Key features:** ZCP MCP, BYO agent/subscription, local + VPN development, Cloud IDE, native IDE over SSH, managed services by hostname, CI/CD pipeline, dev/stage projects separated from production
- **Stateful:** Yes, persistent projects and managed services with environment parity across dev, stage, and production
- **GPU:** Not specified
- **BYOC / Self-host:** Not specified
- **SDKs:** ZCP MCP, zCLI, MCP-capable clients including Claude Code, Codex, Gemini CLI, and opencode
- **Pricing:** Free Lightweight project core, $10/month Serious project core, minute-based compute/resource pricing

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
### [qbox](https://qbox.sh)
[Website](https://qbox.sh) | [Docs](https://qbox.sh/docs)

Self-hostable Firecracker microVM sandbox orchestrator for AI agents and untrusted code. Runs on your own Linux hosts.

- **Isolation:** Firecracker microVMs (full VM with own kernel, hardware-level isolation)
- **Key features:** Self-hosted by design, persistent volumes, port forwarding with HTTPS previews, browser sessions over CDP, templates from any OCI image, operator dashboard, single-host installer (`curl -fsSL https://qbox.sh/install.sh | sh`)
- **Stateful:** Sandboxes are ephemeral, mount object storage volumes for persistence
- **GPU:** No
- **BYOC / Self-host:** Yes, self-hosted by default (bare metal, on-prem hypervisors, your own cloud VMs)
- **SDKs:** Python (`qbox-sh`), REST + WebSocket API, CLI
- **License:** Closed source
- **Pricing:** Free to self-host.
---

## Contributing

Want to add a provider or fix an error? Open a PR with a link to the provider's official documentation or landing page as the source.

**Rules:**
1. All information must come from official sources (docs, landing pages, official GitHub repos)
2. No blog posts, tweets, or third-party articles as primary sources
3. Keep entries factual, no marketing fluff

## License

[CC BY-NC-SA 4.0](LICENSE.md)
