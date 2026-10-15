---
date: 2026-10-13
type: analysis
tags: [AI, business, blockchain]
status: review
source:
  - cb/works/ai-chat/2026-10-10-aiagents-hackathon/outputs/arc-app-kit-vs-build-ai-merged.md
evidence_as_of: 2026-10-13
run: cb/works/ai-chat/2026-10-10-aiagents-hackathon/outputs/arc-app-kit-vs-build-ai-merge-20261013
analysis_runs:
  - date: 2026-10-13
    tool: Claude Code
    model: claude-opus-5-5
    reasoning: unknown
    steps: guide, independent-review, revision, figure
  - date: 2026-10-15
    tool: codex
    model: unknown
    reasoning: unknown
    scope: "Reader-driven visualization revision; paired figures and local interpretations; factual cutoffs unchanged."
visualization_run: cb/derived/visualization-application-20261015/run.json
---

# Arc App Kits와 Build with AI 읽기 안내

이 안내문은 "Arc 문서의 App Kits와 Build with AI(Arc Studio, Arc Studio CLI, Skills, MCP server)는 무엇이 다른가"라는 질문에 세 AI 답변이 내놓은 내용을, 2026-10-07에 보관한 Arc 공식 문서와 대조해 읽기 쉽게 정리한 문서이다. 원문 문장, 단위별 상태와 근거는 통합본에 모두 보존했다. 여기서 "확인했다"고 쓴 것은 통합본에서 `확인됨`이나 `일부 틀림`으로 표시한 내용이고, 그 밖의 답변 내용은 확인하지 않은 주장으로 구별해 쓴다.

질문은 하나이다. 괄호 안의 네 이름을 질문 넷으로 나누지 않은 이유는 질문 목록에 있다.

## 1. App Kits와 Build with AI는 무엇이 다른가?

**쓰는 주체가 다르다.** App Kits는 앱 코드 안에 설치해서 호출하는 SDK이고, 메인넷 체인도 지원한다. Build with AI는 개발자와 그의 AI 코딩 도구가 앱을 만들 때 쓰는 도구 묶음이며, 완성된 앱 안에는 들어가지 않는다. 결제 스킬 하나가 이 구분의 예외인데, 아래 "마지막 점" 단락에서 다룬다. 세 답변의 결론이 같고, 결론을 받치는 문서 내용은 모두 확인했다(확인 기록, `cb/works/ai-chat/2026-10-10-aiagents-hackathon/outputs/arc-app-kit-vs-build-ai-merge-20261013/03-check.md`).

**도구의 사용자와 연결 근거를 구분하기**

한국어:

```text
+----------------+-----------------------+-------------------------------------------------------+
| 도구           | 쓰는 주체             | 본문의 역할                                           |
+----------------+-----------------------+-------------------------------------------------------+
| Arc Studio     | 개발자와 AI 코딩 도구 | 프롬프트로 앱 생성, 테스트넷 배포                     |
| Arc Studio CLI | 개발자와 AI 코딩 도구 | Studio 기능을 터미널과 코딩 도구에서 호출             |
| Skills         | AI 코딩 도구          | Arc와 Circle 사용법 지식; 일부 결제 절차도 설명       |
| MCP server     | AI 코딩 도구          | Arc 문서 검색; 읽기 도구 두 개                        |
| App Kits       | 앱 코드               | kit.send, kit.bridge, kit.swap, kit.unifiedBalance 등 |
+----------------+-----------------------+-------------------------------------------------------+

[Build with AI를 쓰는 개발자와 코딩 도구] -- 코드 작성 --> [앱 코드]
[앱 코드] -- 선택해 SDK 호출 --> [App Kits] -- 기능별 연결 --> [Circle 프로토콜과 지원 체인]
[Skills의 세 사용법] -- 작성 안내 --> [App Kits 호출 코드]

Studio가 만든 앱의 App Kits 사용 여부: 미확인
개발 시점이라는 구분의 예외: 결제 Skills는 에이전트 실행 중 지급 절차도 다룬다.
```

English:

```text
+----------------+-------------------------------+----------------------------------------------------------+
| Tool           | User                          | Role stated in the guide                                 |
+----------------+-------------------------------+----------------------------------------------------------+
| Arc Studio     | Developer and AI coding tools | Generate an app from prompts; deploy to testnet          |
| Arc Studio CLI | Developer and AI coding tools | Call Studio through a terminal or coding tool            |
| Skills         | AI coding tools               | Arc/Circle usage knowledge; some payment procedures      |
| MCP server     | AI coding tools               | Search Arc docs; two read tools                          |
| App Kits       | App code                      | kit.send, kit.bridge, kit.swap, kit.unifiedBalance, etc. |
+----------------+-------------------------------+----------------------------------------------------------+

[Developer/coding tool using Build with AI] -- writes --> [App code]
[App code] -- optionally calls SDK --> [App Kits] -- by function --> [Circle protocols / supported chains]
[Three Skills usage guides] -- guide implementation --> [App Kits call code]

Whether Studio-generated apps use App Kits: unconfirmed
Exception to build-time-only use: payment Skills also describe agent runtime payments.
```

표는 누가 무엇을 사용하는지 비교하고, 아래 연결은 코드 작성과 SDK 호출 및 사용법 안내를 나눈다. 세 Skills는 본문의 bridge-stablecoin, swap-tokens와 unify-balance다. CCTP와 Gateway 같은 프로토콜 연결은 기능별로 다르며, 모든 앱이 App Kits를 써야 한다는 뜻이 아니다. Studio와 CLI의 테스트넷 배포 범위, App Kits의 메인넷 지원과 결제 Skills 예외를 함께 읽어야 한다.

English interpretation: The table compares users and roles; the links distinguish writing code, calling an SDK and receiving implementation guidance. The three Skills are bridge-stablecoin, swap-tokens and unify-balance. Connections to protocols such as CCTP or Gateway depend on the function and do not require every app to use App Kits. Retain Studio/CLI testnet limits, App Kits mainnet support and the payment-Skills exception.

위 그림은 분석자가 문서 내용으로 다시 그린 것이다. ChatGPT 답변에도 계층도가 하나 있으며, 답변 스스로 "개념적 계층도"라고 표시했다. 아래 그림은 그 원본 SVG를 ASCII로 옮긴 것이다. 그림 속 글자는 추출 목록에 있는 원본의 글자를 바꾸지 않고 옮겼다. 네 도구를 2x2로 놓은 배치, 위쪽 화살표는 점선(`:`)이고 아래쪽 화살표는 실선(`|`)인 구분도 원본을 따랐으며, 색만 뺐다.

```text
+----------------------------------------------------+
| 개발 단계 · Build with AI                          |
|  +---------------------+  +---------------------+  |
|  |     Arc Studio      |  |     Studio CLI      |  |
|  |     AI 앱 생성      |  |    AI 작업 위임     |  |
|  +---------------------+  +---------------------+  |
|  +---------------------+  +---------------------+  |
|  |       Skills        |  |     MCP Server      |  |
|  |   전문 지식 제공    |  |   공식 문서 검색    |  |
|  +---------------------+  +---------------------+  |
+----------------------------------------------------+
                           :
                           :  개발·생성
                           v
+----------------------------------------------------+
| 애플리케이션 실행 단계 · App Kits                  |
|  +----------------------------------------------+  |
|  |     Send · Bridge · Swap · Balance · ...     |  |
|  +----------------------------------------------+  |
|                          |                         |
|                          v                         |
|  +----------------------------------------------+  |
|  |    Circle 프로토콜 · Arc 및 기타 블록체인    |  |
|  +----------------------------------------------+  |
+----------------------------------------------------+
```

원본 그림 바로 아래에 답변이 붙인 설명은 다음과 같다.

> 개념적 계층도. Build with AI가 App Kits를 반드시 사용하는 것은 아니며, App Kits 역시 AI 없이 직접 사용할 수 있습니다.

두 그림은 보여 주는 것이 달라서 함께 두었다. 분석자의 그림은 누가 어느 도구를 쓰는지(개발자와 AI 코딩 도구, 그리고 앱 코드)를 보여 주고, ChatGPT의 그림은 네 도구를 나란히 놓고 각 도구의 역할을 짧게 붙였다. 다만 ChatGPT의 그림에서는 점선 화살표가 Build with AI 상자에서 App Kits 상자로 곧바로 이어지므로, 화살표만 보면 Build with AI가 App Kits를 쓰는 것처럼 읽힐 수 있다. 답변의 설명이 "반드시 사용하는 것은 아니"라고 단서를 달았고, 문서로도 Studio가 만든 앱이 App Kits를 쓰는지는 확인되지 않는다(아래 엇갈림 표). 분석자의 그림에서는 코드 작성, 선택적인 SDK 호출과 Skills의 사용법 안내를 서로 다른 관계로 표시했다. 그림 속 역할 설명(예: "AI 작업 위임")은 답변의 말이며, 통합본에서 이 그림의 상태는 `해석`이다.

|           | App Kits                           | Build with AI                                             |
| --------- | ---------------------------------- | --------------------------------------------------------- |
| 정체      | SDK 묶음 (npm 패키지)              | AI 개발 도구 네 가지                                      |
| 쓰는 주체 | 앱 코드                            | 개발자, AI 코딩 도구                                      |
| 쓰는 시점 | 앱이 실행될 때                     | 앱을 만들 때                                              |
| 메인넷    | 메인넷 체인도 지원한다             | Studio와 CLI는 테스트넷에만 배포한다. MCP는 문서만 읽는다 |
| 체인      | Arc 전용이 아니다 ("not just Arc") | Studio는 Arc와 USDC가 기본값이다                          |
| 문서 위치 | `/app-kit`                         | `/ai/` 아래 네 페이지                                     |

**App Kits의 구성에서 헷갈리기 쉬운 점이 있다.** 핵심 패키지 하나로 쓰는 기능은 일곱 가지(Send, Bridge, Swap, Unified Balance, Onramp, Earn, Borrow)이다. 따로 설치할 수 있는 Kit은 Send를 뺀 여섯 가지이며, Send Kit은 없다.

**두 묶음은 Skills에서 만난다.** Skills 문서의 스킬 세 개(bridge-stablecoin, swap-tokens, unify-balance)가 App Kit 사용법을 다룬다. 그래서 Skills를 설치한 코딩 도구는 App Kits를 호출하는 코드를 쓰도록 안내받는다. 이것은 모든 페이지 머리에 붙은 에이전트용 안내문을 빼고 본문만 볼 때의 이야기이다. 그 안내문도 Skill 설치와 App Kits 사용을 함께 권하지만, 문서 전체에 붙는 일반 지침이어서 연결로서는 더 약하다. 반면 Arc Studio가 만든 앱이 App Kits를 쓰는지는 Studio와 CLI 문서에 언급이 없어서 확인되지 않는다.

**답변들이 엇갈린 곳은 세 군데이며, 문서로 가린 결과는 다음과 같다.**

| 엇갈린 점                            | 답변들                                                                                | 문서로 확인한 것                                                                                                                                          |
| ------------------------------------ | ------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Build with AI 문서의 위치            | Claude는 `/ai/` 경로라고 하고, Grok은 "/build 하위"라고 한다                          | URL은 `/ai/` 아래이다. 다만 문서 색인에서는 Build on Arc 바로 다음 줄들에 놓인다. 사이트 메뉴가 이 페이지들을 Build 아래에 묶는지는 보관본으로 알 수 없다 |
| Studio가 만든 앱이 App Kits를 쓰는가 | Claude는 명시가 없다고 하고, Grok은 활용할 수 있다고 한다                             | Studio와 CLI 문서에 App Kit 언급이 없다. Grok의 말은 근거가 없다                                                                                          |
| Skills는 무엇을 실행하는가           | Claude는 코드를 실행하지 않는다고 하고, ChatGPT는 CLI 실행 절차도 담을 수 있다고 한다 | 둘 다 맞다. 스킬 자체는 지식이지만, 일부 스킬은 에이전트 지갑으로 결제하는 절차를 다룬다                                                                  |

마지막 점 때문에 "Build with AI는 개발 시점, App Kits는 실행 시점"이라는 구분은 Studio, CLI, MCP에는 맞지만 Skills에는 완전히 맞지 않는다. 결제 스킬을 받은 코딩 에이전트는 실행 중에 스스로 돈을 쓸 수 있다. 그때 쓰는 것은 App Kits가 아니라 Circle CLI와 에이전트 지갑으로 보이지만, 이것은 Skills 문서 표의 설명에서 끌어낸 분석자의 추론이다(확신도 중간).

"Build with AI"라는 이름 자체는 보관본 어디에도 나오지 않는다. 사이트 탐색 메뉴에 붙은 이름일 가능성이 높지만, 이것은 분석자의 추정이다.

**묻지 않았는데 나온 내용도 있다.** ChatGPT와 Claude 답변은 사용자의 프로젝트를 전제로 어떤 조합을 쓸지 권고했다(예: 코딩 도구에 Skills와 MCP를 붙이고, 실제 결제와 이동은 App Kits로 구현). 이 권고는 답변의 판단이며 확인 대상이 아니다. 통합본 3절(묻지 않았는데 나온 내용)에 원문 그대로 있다.

세부 문장과 근거: 통합본 Q01
