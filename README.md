# Yongseop Kim

(updated: 2026-07-30) · [한국어](README.kr.md)

**Vertically integrated AI engineer.** I build the layers AI runs on.

Twelve and a half years at Samsung Electronics (2014-02 to 2026-07).
- (separate assignments, at different levels, in different organisations)
- an **NPU chip compiler**
- an **on-device neural-network inference runtime**
- a **heterogeneous GPU distributed-training platform**
- a **company-wide internal LLM chat service**
- **services built around agents**: a **general-purpose agent platform** served over the web, and a **report-generation service** over confidential business documents, built so that every claim traces to the source it came from.

Before AI: **Tizen OS** - native API development and coordination, and WRT (the web runtime); the **.NET Core runtime** and its JIT.

Within Samsung Electronics:
- **Software Center (SWC)** 2014-02 to 2017-10
- **Samsung Research (SR)** 2017-11 to 2025-11
- **AX/PI Center, AX Development Team** 2025-12 to 2026-07

Left Samsung Electronics on 2026-07-31.

[LinkedIn](https://www.linkedin.com/in/dragonseop/)

## Career

### Services built around agents

- 2026-03 to 2026-07

Vertical AI projects
- pick a business domain,
- work out what an agent can actually be trusted to do inside it,
- then build the service on that judgement

Sole or primary architect of both. 99% of the code was produced through Claude Code and Codex; my work was the architecture and the boundary design.

**1. A general-purpose agent platform, served over the web.**

- **The execution loop**: multi-round tool-calling with token streaming, per-agent
  budgets, and a completion gate that refuses to accept "done" without verified
  evidence.
- **Delegation as an auditable contract:** a parent agent hands a child a task
  contract carrying success criteria, required claims, evidence requirements and
  capability grants, then re-verifies the child's result against them.
- **A four-tier execution sandbox:** RLIMIT, bubblewrap namespace isolation,
  Docker with networking off. Session-scoped path allow-listing,
  human-in-the-loop approval.

**2. A report-generation service over confidential business documents.**

- Not a document converter — a service built around which claim came from which
  evidence, and what the LLM proposed versus what a deterministic gate decided.
- **A governed control plane**: twelve bounded contexts, a fifteen-state machine
  with whitelisted transitions and an audit snapshot at every hop, and terminal
  statuses that make Silent Success impossible. Built so that a statically
  guarded authority token rejects an LLM's claim to hold release authority
  outright.
- **Deep document understanding**: the deliverable is not prose but an auditable,
  structured evidence bundle.

**What I was aiming at in both**:
- the LLM proposes; deterministic gates and humans decide
- nothing passes by asserting that it passed

Python 3.13, Litestar, LiteLLM, Pydantic, Redis, OpenTelemetry, Claude Code, Codex.

---

### LLM chat service backend

- 2024-05 to 2025-11

The orchestration layer of a company-wide internal LLM platform. Took what was a plain chat window and built it toward something agent-shaped.

- **Aimed at an agentic platform rather than a chat window.** Backend API work - file/S3 APIs, tool-call APIs, graph execution and so on - producing a platform that is not 100% agentic but is capable of being agentic.
- **From design document to production.** Built from the API, schema and scenario documents, and it landed successfully inside the company. Project: SR AIPlayground.

Python async, Litestar, LangChain/LangGraph, MCP SDK, LlamaIndex, PostgreSQL, S3.

(The period just before agentic coding - all of this code written directly.)

---

### Distributed training platform: HARP (Heterogeneous AcceleRator Platform)

- 2022-09 to 2023-11

An internal challenge project.

- **Built and experimented with a distributed training platform, from the control
  plane down to the infrastructure under it.** A batch-size recommendation engine
  ranking candidates from historical training metrics, a thirty-second ETL tick
  from Elasticsearch into MariaDB, a Kubernetes batch-job manifest parser. In
  Python, Horovod extended for per-host weights.
- **For the record: "No."** Heterogeneous load balancing did not pay off.
  Gradients still have to be synchronised, and on mixed hardware that cost eats
  away the gain over simply using fewer homogeneous GPUs.

Go 1.19, Python, Horovod, ctypes FFI, NCCL/CUDA, Elasticsearch, Kubernetes,
InfiniBand, SWIG.

---

### VS Code extension for a compiler toolchain

- 2022-03 to 2022-07

Module owner for the extension model and the tests.

- **Designed the extension model that any compiler backend plugs into.**
- **Wrote the test infrastructure from scratch.**

[Samsung/ONE-vscode](https://github.com/Samsung/ONE-vscode) ·
[PRs](https://github.com/Samsung/ONE-vscode/pulls?q=is%3Apr+author%3AYongseopKim)

---

### NPU chip compiler for on-device AI

- 2020-12 to 2021-11

Compiler for an in-house TV NPU.

- **Built it end to end, from frontend IR down to vISA.** The signature work is
  InstanceNorm: pattern matching from the Circle frontend into high-level IR,
  legalise and split passes, and an SRAM-aware tile search with weight-footprint
  estimation and an output-feature-map tailoring policy. Alongside it, new
  virtual ISA opcodes for a silicon revision, and elementwise subgraphs offloaded
  onto the on-die DSP.

C++17, quantisation (Q8/Q16), multi-stage lowering, SRAM tiling, DSP offload.

---

### On-device runtime for NN models

- 2018-04 to 2020-12

Inference runtime for on-device targets.

- **Tensor memory management for the runtime.** Separated memory planning from
  backing storage, built per-backend managers, and finally unified them behind a
  single tensor-manager interface.
- Lowering pipeline and an fp16 conversion pass; brought in Google XNNPACK's
  float kernels.

[Samsung/ONE](https://github.com/Samsung/ONE) ·
[PRs](https://github.com/Samsung/ONE/pulls?q=is%3Apr+author%3AYongseopKim) ·
C++11/14/17, ARM Compute Library, OpenCL, TFLite/Circle, XNNPACK, JNI.

---

### .NET Core runtime and JIT

- 2016-07 to 2018-02

.NET Core runtime and JIT
- Cast codegen for the four integer/float directions, integer and floating-point
  divide, and struct argument passing under the ARM32 ABI (sub-word block copy,
  promoted-struct guards, GC pointer counting).
- Made pre-compiled native images loadable directly on in-house devices, reaching
  close to native startup speed.

[coreclr](https://github.com/dotnet/coreclr) ·
[corefx](https://github.com/dotnet/corefx) ·
[runtime](https://github.com/dotnet/runtime) ·
[PRs](https://github.com/dotnet/coreclr/pulls?q=is%3Apr+author%3AYongseopKim) ·
C++ (JIT and VM), C#, x86 assembly.

---

### 2014-03 to 2016-06

- 2016-03 to 2016-06: Tizen C# API and Xamarin
- 2015-03 to 2016-02: Tizen web runtime (WRT)
- 2014-03 to 2015-02: managing the API surface
