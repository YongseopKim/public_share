# CURG 14기 팀 모집 피치

## content

### 잠시 제 소개

- 약 10년 정도 [SW 개발자](https://github.com/YongseopKim/public_share)로 일한 후 최근 퇴사
- 최근 5년은 AI 관련 일: DL, LLM 그리고 Agent
- 현재는? 백수(미혼 무직)
- 목표는? 금융업으로의 도메인 전환

```
manufacturing, on-device SW --> DL (Deep Learning) --> LLM --> Agent --> finance (goal)
|<---                            about 10 years                     ---> |  now  |
```

### AI에 대한 확신

- 최근 5년의 AI 관련 일을 진행하면서 AI 기술에 대한 확신이 매우 커짐
  - AI는 앞으로 우리가 엑셀을 사용하듯, DB 인프라를 사용하듯 어디에든 포함되는 기술이 될 것
- but, AI도 어디에나 같은 꼴로 쓰이지는 않음
  - DB가 산업마다 사용하는 방식이 갈라졌듯 AI도 도메인마다 갈라질 것
- refs:
  - ["Use of agentic AI varies by industry"](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai)(McKinsey, 2026-08)
  - ["today I actually have a hard time thinking of an industry that I don't think AI will transform in the next several years"](https://www.gsb.stanford.edu/insights/andrew-ng-why-ai-new-electricity)(Andrew Ng, "AI is the new electricity", Stanford GSB, 2017)

### Agent 시대의 도래

- 현재 시점에서 이런 AI는 이미 우리에게 사용되기 시작
- 챗GPT와 같은 서비스 말고도, 기계적인 workflow와 더불어 판단이 용이한 케이스에 이미 Agent는 도입되기 시작
- 단, Agent의 시대는 한 번에 오지 않음. 두 단계로 봄
- refs:
  - ["77% of API transcripts show automation patterns (especially full task delegation)"](https://www.anthropic.com/research/anthropic-economic-index-september-2025-report)(Anthropic Economic Index, 2025-09)
  - [Agent를 규모 있게 쓰는 조직은 약 열에 둘. 매출 10억 달러 이상은 27%에서 40%로](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai)(McKinsey, 2026-08)
  - [확산은 아직 초기. 기술 기업의 SW 엔지니어링(24%), IT(22%), 서비스 운영(21%)에서 규모 있게 씀](https://hai.stanford.edu/ai-index/2026-ai-index-report)(Stanford AI Index 2026, 4.3장 197쪽)
  - ["Today, the industry is hovering on the edge of levels 1 and 2"](https://assets.stripeassets.com/fzn2n1nzq965/3LlGw839Q6kUwxZlLZDtH6/ffc733b5f678b754e56c519e4c62deb8/Stripe-annual-letter-2025-desktop.pdf#page=11)(Stripe, 2025 연례 서한 11쪽)

### 사람이 하던 일을 Agent가 하게 될 때 생기는 일은?

- (이미 지불하고 있어서 우리는 인지하지 못 하지만) 사람이 하고 있는 결제들
  - 월세, 인터넷 사용료, Office 365 같은 문서 작업 도구
  - (광고를 통해 인지하지 못 했지만) 뉴스, 포털, 검색 등
- 인간이 한번에 하나의 작업(T; a task)을 하고, 그 작업 안에 몇 개(n)의 결제(P)가 있다면?
  - a task = n x P (n은 사람이 할 때 그 작업에 든 결제 수)
  - a human: m tasks at once (m == 1), h hours a day (h == 8), r tasks an hour
  - payments a day = n x m x h x r
- 사람이 그 동안 하던 결제들을 Agent가 하게 된다면?
  - 8시간 일하는 노동자에서 24시간 쉬지 않는 Worker: h = 8 -> 24
  - 한 번에 하나만 하던 노동자에서 수백 개를 동시에 돌리는 Worker: m = 1 -> 한계 없음
  - 사람의 수십 배 속도로 처리하는 Worker: r -> r x 수십
  - 작업이 더 마이크로하게 쪼개져 결제도 쪼개지는 Worker: n -> n x k (정액제에서 종량제로)
  - 넷이 모두 곱으로 늘어남
- 폭발적으로 증가하는 결제는 쉽게 예측할 수 있음

### 두 단계로 올 Agent 시대

- 1단계: 사람의 대리인으로서의 Agent (지금이 여기)
  - 사람이 Agent에게 결제를 위임
  - 카드망도 여기에 맞춰 움직이는 중: [Visa Intelligent Commerce](https://developer.visa.com/capabilities/visa-intelligent-commerce), [Mastercard Agent Pay](https://developer.mastercard.com/agent-pay/documentation/)
  - refs:
    - [Google AP2 명세](https://github.com/google-agentic-commerce/AP2/blob/main/docs/ap2/specification.md)의 [Human Present](https://github.com/google-agentic-commerce/AP2/blob/main/docs/ap2/specification.md#direct-human-present)와 [Human Not Present](https://github.com/google-agentic-commerce/AP2/blob/main/docs/ap2/specification.md#autonomous-human-not-present)
    - [Stripe의 자동화 5등급](https://assets.stripeassets.com/fzn2n1nzq965/3LlGw839Q6kUwxZlLZDtH6/ffc733b5f678b754e56c519e4c62deb8/Stripe-annual-letter-2025-desktop.pdf#page=9)
    - [Four Pillars](https://research.4pillars.io/ko/research/agentic-commerce-expansion-not-replacement)의 T1 보조, T2 위임, T3 에이전트 네이티브
- 2단계: 스스로 주체가 되는 Agent
  - 개인/법인을 넘어선 세 번째 경제 주체
  - refs:
    - ["결제 주체가 될 수 있는 법적 신분은 인간과 법인밖에 없다"](https://www.youtube.com/watch?v=rwsW1AZ4Djw&t=242s)(박정호, 업비트 인사이트 토크)
    - ["Autonomous AI agents are becoming independent economic entities"](https://public.bnbstatic.com/static/files/research/full-year-2025-and-themes-for-2026.pdf#page=76)(Binance Research)
    - ["Agents are becoming economic entities, not tools"](https://research.4pillars.io/ko/research/agentic-x402-a-to-z)(Four Pillars)
    - ["a new economic layer where agents transact and coordinate at scales and speeds beyond direct human oversight"](https://arxiv.org/abs/2509.10147)(Google DeepMind)
  - 제가 미리 준비하고 싶은 영역이 여기!
    - 참고: 반드시 이번 학기에 해야 할 영역은 아님

---

주체별

|               | 개인         | 법인           | Agent (1단계, 대리인)   | Agent (2단계, 주체) |
| ------------- | ------------ | -------------- | ----------------------- | ------------------- |
| 주체 자격은 어디서 오나 | 자연         | 제도 (회사법)  | 개인이나 법인이 위임    | ? (아직 없음)       |
| 신원의 근거   | 출생, 신분증 | 등기           | 빌림 (사람 카드의 토큰) | 키                  |
| 책임          | 본인         | 법인 재산      | 위임한 사람             | 비어 있음           |
| 결제 수단     | 현금, 카드   | 법인카드, 계좌 | 사람 카드의 일부        | 스테이블코인        |

---

기술 관점

|              | 0단계: 사람이 직접          | 1단계: Agent는 대리인                    | 2단계: Agent는 주체      |
| ------------ | --------------------------- | ---------------------------------------- | ------------------------ |
| 언제         | 지금까지                    | 지금                                     | 위임이 촘촘해진 뒤       |
| 결제 주체    | 사람                        | 사람 (Agent는 사람 뒤에 묶임)            | Agent 자신               |
| 신원         | 신분증, 발급 심사           | 사람의 신원을 빌림                       | 키                       |
| 책임         | 사람                        | 사람 (카드 소지자)                       | 아직 붙을 자리 없음      |
| 카드망       | 딱 맞음 (이걸 위해 만든 것) | 적응 중 (Visa, Mastercard)               | 전제가 안 맞아 못 들어옴 |
| 레일         | 카드, 계좌                  | 아무거나                                 | 온체인, 스테이블코인     |
| 비어 있는 것 | 없음                        | 위임 층 (한도, 승인, 영수증, 감사, 분쟁) | 신원, 정책, 책임 층      |

### 2단계는 왜 오는가: 위임이 촘촘해지면 1단계가 깨짐

- 1단계는 사람 한 명 뒤에 Agent를 묶는 구조 (카드 하나, 토큰 여럿, 책임은 한 사람)
- 위임(delegation)이 촘촘해지면 이게 깨짐
  - 사람이 거기 있을 수 없음: Agent 수백 개가 하루 수천 건
  - 한 사람이 그 책임을 다 질 수 없음
  - Agent가 Agent에게 사는 거래는 어느 사람 뒤에 묶을지가 없음 (`agent buys from agent`)
- 그때 필요한 건 Agent 자신의 신원, 한도, 책임. 사람 뒤에 묶이지 않는 결제
- 즉, 2단계

```
Stage 1: one card, many tokens

    Human --- Card (1)
                |-- token a --> [Agent a] --+
                |-- token b --> [Agent b] --+--> card network --> seller
                +-- token c --> [Agent c] --+
    liability: one human, for a, b and c

Stage 2: one key per agent

    [Agent A, key A] --sign--> rail --> seller
    [Agent B, key B] --sign--> rail --> seller
    [Agent C, key C] --sign--> rail --> [Agent D, key D]    (agent buys from agent)
    liability: ? (nowhere to attach)
```

### 왜 블록체인인가

- 카드망
  - 카드 발행을 원하고 지불의 주체인 사람이 먼저 있고 -> 신원
  - 카드사에 의해 발급 심사를 거쳐 카드가 발행되고 -> 한도
  - 이 카드를 가진 카드 소지자가 결제를 실행하며 -> 책임
  - 이 레일이 돈다 -> 모두 사람 중심
  - 계좌도 같음: 개설 주체가 사람 또는 법인
  - 위의 2단계 Agent에 대한 준비가 전혀 되지 않음
- 온체인 + 스테이블코인
  - 키가 곧 주소(누가 서명했나)이고, 서명이 곧 승인이고, 한도는 키마다 붙음
  - 발급자가 없으니 Agent가 카드 없이 바로 씀
  - 다만 키가 누구 것인지(KYA)는 아직 없음
- 블록체인은 이런 발급자가 없이 결제가 실행되는 유일한 레일

### 현실에서 합의해야 되는 지점: 즉, 아직 미정인 부분들

- 최종 책임은 누구인가?
  - 현재 답은 "사람"
  - [Visa](https://usa.visa.com/dam/VCOM/download/about-visa/visa-rules-public.pdf): Agent의 행동을 카드 소지자가 직접 한 것으로 봄
  - (참고 - 최종 책임: 카드망과 판매자 앞에서 누가 물어내는가? 현재는 카드 소지자)
- 사고가 누구 탓인가?
  - 사용자의 지시 오류, Agent의 오작동, 판매자의 과실을 가를 기준이 없음 ([금융결제원, 2025-12](https://research.kftc.or.kr/research/issue/7118))
  - 과기정통부는 이용자 부주의면 이용자, AI 결함이면 개발사로 갈랐고, 시키지 않은 자율 판단의 사고는 공백 ([뉴시스, 2026-05](https://www.newsis.com/view/NISX20260430_0003613148))
  - (참고 - 사고 탓: 그 사람이 물어낸 뒤에 Agent 개발사나 판매자에게 되물릴 수 있는가? 현재는 그 기준이 없다)
- Agent의 신원은 누가 확인하나?
  - [KYA(Know Your Agent)](https://research.kftc.or.kr/research/issue/7118): 누구에게 귀속되나, 누가 만들었나, 의도대로 도나
- Agent에게 법적 인격이나 책임 재산을 줄 것인가?
  - [전자인 논의 (2021)](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART002796467)
  - [EU의 강제보험과 보상기금 제안 (2017, 입법 안 됨)](https://www.europarl.europa.eu/doceo/document/TA-8-2017-0051_EN.html)
- 아직 답이 없는 것(제가 찾은 범위에서): Agent 간 거래의 과세([스테이블코인 결제 차익 과세 논의는 시작됨, 서울경제 2026-09](https://m.news.nate.com/view/20260913n12485)), 청약철회권의 적용, 카드 대여 금지의 적용

### 이번 학기동안 하고 싶은 것: Agent x Payment x Blockchain의 시작

- Agent가 결제(Payment)하는 시대가 올 것으로 예측하고, 선점하는 것이 목적
- 이 Agent의 결제가 이뤄질 온체인 세상(Blockchain)에서는 무엇이 필요한지를 파악하고,
- 리서치로 빈칸을 찾고, 비즈니스가 보이면 그 칸을 만들자

### 원래 제 목표

현재 에이전트 결제 계층

```
    #  layer (name)                 status        filled by what (checked 2026-08-13)
------------------------------------------------------------------------------------------
    1  discover (발견)              converging    UCP, pay.sh catalog with verified endpoints
    2  evaluate (평가)              accumulating  almost nothing yet; grows only from usage records
    3  authority (권한)             converging    AP2 mandate, Solana Spend Permissions
    4  policy (정책)                BUILD GAP     every rule exists somewhere (Mastercard, AP2, Ramp),
                                                  but none is issued to an agent, only to a person
    5  execute (실행)               commodity     UCP, x402
    6  payment (결제)               commodity     x402, card networks, AP2
    7  verify+recover (검증과 복구) BUILD GAP     refunds per rail (x402r, Mastercard), no common guarantee
    8  dispute (분쟁)               INSTITUTION   card networks put all liability on the human;
                                                  no agent reason code, by design
    9  audit (감사)                 BUILD GAP     PEAC, Kevros, Catena, Kite; fewer than policy tools
   10  accounting, regulation       INSTITUTION   tax, AML, KYC unresolved once wallet = identity
       (회계와 규제)
------------------------------------------------------------------------------------------
    converging   = standards are settling it, wait                 (표준 수렴형)
    commodity    = solved, many vendors, pick one                  (커모디티)
    accumulating = fills itself with use, cannot be built ahead    (축적형)
    BUILD GAP    = nobody built it yet, so I can                   (구축 공백형)
    INSTITUTION  = needs a rule or a law, not code                 (제도형)
```

---

- status `BUILD GAP` 중 policy, verify+recover 부분이 원래 제 목표
- 그 둘을 구체적으로 보면
- 자연어 규칙의 구조화
  - 제 처음 목표는 법인 카드 사용과 같은 결제에 사용되는 정책에 대한 자연어 규칙의 구조화
  - 이를 쇼핑몰 유즈케이스나 (주제를 벗어나지만) 보안 정책 부분으로 확장 가능
- 환불과 중간 환불은 어디까지 일반화되는가?
  - 결제 계층 표의 7번(검증과 복구)과 8번(분쟁). 1단계 위임 층에서 아직 없는 분쟁, 2단계에서는 책임 층
- 이 가운데 하나가 이번 학기 해커톤 주제 후보

### 끝

End of writing
