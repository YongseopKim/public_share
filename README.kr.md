# 김용섭

(updated: 2026-07-30) · [English](README.md)

**수직 통합형 AI 엔지니어.** 저는 AI가 그 위에서 돌아가는 층들을 만듭니다.

삼성전자에서 12년 반 (2014-02 ~ 2026-07) 동안 해 온 것들.
- (서로 다른 조직에서, 서로 다른 층의, 별개의 과제들)
- **NPU 칩 컴파일러**
- **온디바이스 신경망 추론 런타임**
- **이기종 GPU 분산학습 플랫폼**
- **전사 사내 LLM 챗 서비스**
- **에이전트를 포함하는 서비스**: 웹으로 제공되는 **범용 에이전트 플랫폼**, 그리고 모든 주장이 출처까지 추적되도록 만든 **기밀 문서 기반 리포트 생성 서비스**.

AI 이전: **Tizen OS** - 네이티브 API 개발 및 관리와 WRT(웹 런타임), **.NET Core 런타임**과 그 JIT 개발.

삼성전자 내 소속:
- **소프트웨어센터(SWC)** 2014-02 ~ 2017-10
- **삼성리서치(SR)** 2017-11 ~ 2025-11
- **AX/PI센터 AX개발팀** 2025-12 ~ 2026-07

2026년 7월 31일 퇴사하였습니다.

[LinkedIn](https://www.linkedin.com/in/yongseop-kim-35658154/)

## 경력

### 에이전트를 포함하는 서비스

- 2026-03 ~ 2026-07

vertical AI 과제
- 업무 도메인을 하나 잡고,
- 그 안에서 에이전트에게 무엇까지 맡길 수 있는지를 따진 다음,
- 그 판단 기반으로 서비스를 개발

두 과제를 단독 또는 주 설계자로 맡았고, 코드의 99%는 Claude Code와 Codex를 이용하였으며, 저는 아키텍처와 경계 디자인에 집중했습니다.

**1. 웹으로 제공되는 범용 에이전트 플랫폼.**

- **실행 루프**: 토큰 스트리밍을 동반한 멀티라운드 tool-calling, 에이전트별 예산, 그리고
  검증된 근거 없이는 "완료"를 받아들이지 않는 완료 게이트.
- **감사 가능한 계약으로서의 위임:** 부모 에이전트가 자식에게 성공 기준, 필수 주장,
  근거 요건, 권한 부여를 담은 task contract를 건네고, 자식의 결과를 그 기준으로 다시 검증.
- **4계층 실행 샌드박스:** RLIMIT, bubblewrap 네임스페이스 격리,
  네트워크를 끈 Docker. 세션 범위의 경로 allow-list, human-in-the-loop 승인.

**2. 기밀 업무 문서를 다루는 리포트 생성 서비스.**

- 단순 문서 변환기가 아닌 어떤 주장이 어떤 근거에서 나왔는가, 그리고 LLM이 제안한 것과 결정론적
게이트가 결정한 것은 무엇인가에 집중한 서비스
- **통제되는 컨트롤 플레인**: 12개 bounded context, 화이트리스트 전이와 매 hop의 감사
  스냅샷을 갖는 15-state 머신, 그리고 Silent Success를 불가능하게 만드는 종료 상태들.
  정적으로 가드되는 authority token이 릴리스 권한을 가졌다는 LLM의 주장 자체를
  기각하게 만드는 구조로 개발.
- **깊은 문서 이해**: 산출물이 산문이 아니라 감사 가능한 구조적 근거 묶음.

**두 시스템을 하고자 한 것**:
- LLM은 제안하고, 결정은 결정론적 게이트와 사람이 한다
- 통과했다고 주장해서 통과되는 것은 없다

Python 3.13, Litestar, LiteLLM, Pydantic, Redis, OpenTelemetry, Claude Code, Codex.

---

### LLM 챗 서비스 백엔드

- 2024-05 ~ 2025-11

전사 사내 LLM 플랫폼의 오케스트레이션 계층. 단순 챗 창이던 것을 에이전트에 가까운 형태로 개발했습니다.

- **챗 창이 아니라 에이전틱한 플랫폼을 목표로 개발.** BE(Backend) API 개발 - 파일/S3 API, ToolCall 관련 API, 그래프 실행 등 - 을 통해 100% 에이전틱하지는 않지만 에이전틱 가능한 플랫폼을 개발
- **설계 문서에서 상용까지.** API, 스키마, 시나리오를 기반으로 개발하였고, 사내에 성공적으로 안착. 프로젝트 명: SR AIPlayground

Python async, Litestar, LangChain/LangGraph, MCP SDK, LlamaIndex, PostgreSQL, S3.

(agentic coding 직전의 시기이며, 모든 코드 직접 개발)

---

### 분산학습 플랫폼: HARP (Heterogeneous AcceleRator Platform)

- 2022-09 ~ 2023-11

사내 챌린지 프로젝트.

- **컨트롤 플레인부터 그 아래 인프라까지, 분산학습 플랫폼 개발 및 실험**
  과거 학습 메트릭에서
  후보를 순위 매기는 배치사이즈 추천 엔진, Elasticsearch에서 MariaDB로 30초마다 도는
  ETL, Kubernetes batch job 매니페스트 파서. Python에서는 per-host 가중치를 위해 Horovod를
  확장함.
- **참고: "No."** 이기종
  로드밸런싱은 이득이 없었음. gradient는 결국 동기화되어야 하고, 이기종에서 그 비용이
  동기종 GPU를 덜 쓰는 것 대비의 이득을 깎아 먹음.

Go 1.19, Python, Horovod, ctypes FFI, NCCL/CUDA, Elasticsearch, Kubernetes,
InfiniBand, SWIG.

---

### 컴파일러 툴체인용 VS Code 확장

- 2022-03 ~ 2022-07

확장 모델과 테스트의 module owner.

- **어떤 컴파일러 백엔드든 꽂을 수 있는 확장 모델 설계.**
- **테스트 인프라를 from scratch부터 작성.**

[Samsung/ONE-vscode](https://github.com/Samsung/ONE-vscode) ·
[PRs](https://github.com/Samsung/ONE-vscode/pulls?q=is%3Apr+author%3AYongseopKim)

---

### 온디바이스 AI용 NPU 칩 컴파일러

- 2020-12 ~ 2021-11

사내 TV NPU를 위한 컴파일러.

- **FE IR부터 vISA까지 E2E로 개발.** 대표작은
  InstanceNorm입니다. Circle 프론트엔드에서 상위 IR로 패턴 매칭, legalize와 split 패스,
  그리고 weight footprint 추정과 OFM 타일 tailoring 정책을 갖춘 SRAM 인지
  타일 탐색. 여기에 특정 실리콘 리비전을 위한 신규 virtual ISA opcode 정의와, on-die
  DSP로 오프로드한 elementwise 서브그래프가 따라옴.

C++17, 양자화(Q8/Q16), 다단계 lowering, SRAM 타일링, DSP offload.

---

### 온디바이스 NN 추론 런타임

- 2018-04 ~ 2020-12

온디바이스 타깃을 위한 추론 런타임.

- **런타임 텐서 메모리 관리.** memory planning과 backing storage를 분리하고,
  백엔드별 매니저를 만들고, 마지막에 하나의 tensor-manager 인터페이스로 통합.
- lowering 파이프라인과
  fp16 변환 패스 개발, Google XNNPACK의 float
  커널 도입.

[Samsung/ONE](https://github.com/Samsung/ONE) ·
[PRs](https://github.com/Samsung/ONE/pulls?q=is%3Apr+author%3AYongseopKim) ·
C++11/14/17, ARM Compute Library, OpenCL, TFLite/Circle, XNNPACK, JNI.

---

### .NET Core 런타임과 JIT

- 2016-07 ~ 2018-02

.NET Core 런타임과 JIT
- 정수/부동소수
  네 방향의 cast codegen, 정수와 부동소수 나눗셈, 그리고 ARM32 ABI 하의 struct 인자
  전달(sub-word 블록 복사, promoted-struct 가드, GC 포인터 카운팅).
- 사내 기기에서
  프리컴파일된 네이티브 이미지를 직접 로드할 수 있게 만들어 네이티브에 가까운 시작
  속도에 도달.

[coreclr](https://github.com/dotnet/coreclr) ·
[corefx](https://github.com/dotnet/corefx) ·
[runtime](https://github.com/dotnet/runtime) ·
[PRs](https://github.com/dotnet/coreclr/pulls?q=is%3Apr+author%3AYongseopKim) ·
C++ (JIT과 VM), C#, x86 어셈블리.

---

### 2014-03 ~ 2016-06

- 2016-03 ~ 2016-06: Tizen C# API와 Xamarin
- 2015-03 ~ 2016-02: Tizen 웹 런타임 (WRT)
- 2014-03 ~ 2015-02: API 표면(Surface) 관리
