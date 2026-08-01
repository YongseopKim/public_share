Vertically integrated AI engineer. I build the layers AI runs on.

Twelve and a half years at Samsung Electronics (Feb 2014 - Jul 2026), across separate assignments at different levels of the stack:

- NPU chip compiler for on-device AI: quantised operators carried from frontend IR down to vISA.
- On-device neural-network inference runtime, later open-sourced as Samsung/ONE: tensor memory management, lowering pipeline, fp16 conversion, XNNPACK backend.
- Heterogeneous GPU distributed-training platform: Go control plane, Horovod extensions, Kubernetes. Built it and measured it, and the honest answer was that heterogeneous load balancing does not pay off.
- Company-wide internal LLM chat service (SR AIPlayground): the orchestration layer that moved it from a chat window toward an agentic platform.
- Services built around agents, as vertical AI projects.

Before AI: Tizen OS - native API development and coordination, then the web runtime (WRT). After that the .NET Core runtime and its JIT - ARM32 code generation and ahead-of-time native images.

The 2026 work was two separate systems: a general-purpose agent platform served over the web, and a report-generation service over confidential business documents, built so that every claim traces to the source it came from. 99% of that code was produced through Claude Code and Codex; my work was the architecture and the boundary design. The LLM proposes; deterministic gates and humans decide, and nothing passes by asserting that it passed.

Software Center 2014-2017, Samsung Research 2017-2025, AX/PI Center 2025-2026.

Full profile: github.com/YongseopKim/public_share
