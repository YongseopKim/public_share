# 3. 에이전트로 기존 문제를 어떻게 풀려 하는가, 그 방향이 맞는가?

## 목차

가 절과 나 절은 질문의 앞 절반("어떻게 풀려 하는가")에, 다 절은 뒤 절반("그 방향이 맞는가")에 답하고, 라 절은 판정에서 비어 있는 곳과 그것이 채워질 모습을 적습니다. 가, 나, 다, 라 절은 각각 머리에 작은 질문과 한 줄 답을 둡니다. 그림은 들어 있는 절 아래에 적었습니다.

- [한 줄 답](#한-줄-답)
  - 그림 1. 3번 답의 구조
- [가. 고객 쪽 해법: 고객마다 어떤 에이전트 장치를 냈고, 그 장치는 나왔는가](#가-고객-쪽-해법-고객마다-어떤-에이전트-장치를-냈고-그-장치는-나왔는가)
  - [1. 고객별 장치와 상태: 장치가 나온 곳과 나오지 않은 곳](#1-고객별-장치와-상태-장치가-나온-곳과-나오지-않은-곳)
    - 그림 2. 고객과 에이전트 장치의 상태
  - [2. 버는 고리: 수요라는 빈칸에 대한 회사의 답과 그 일정](#2-버는-고리-수요라는-빈칸에-대한-회사의-답과-그-일정)
    - 그림 3. 버는 고리와 기관 수요의 조건
  - [3. 고객 쪽 정리: 장치가 푸는 문제와 장치가 닿지 않은 고객](#3-고객-쪽-정리-장치가-푸는-문제와-장치가-닿지-않은-고객)
- [나. 회사 쪽 경로: 에이전트 매출의 길, 공시에 보이는 크기, 회사 안에서 쓰는 에이전트](#나-회사-쪽-경로-에이전트-매출의-길-공시에-보이는-크기-회사-안에서-쓰는-에이전트)
  - [1. CEO의 답: 에이전트 매출의 시점을 묻는 질문에 무엇이라고 답했는가](#1-ceo의-답-에이전트-매출의-시점을-묻는-질문에-무엇이라고-답했는가)
    - 그림 4. CEO 답의 세 갈래가 닿는 공시의 줄
  - [2. 갈래 1, 프로토콜 매출 ("some"): 공시의 어느 줄에 들어가고, 그 줄은 얼마인가](#2-갈래-1-프로토콜-매출-some-공시의-어느-줄에-들어가고-그-줄은-얼마인가)
  - [3. 갈래 2, USDC 채택 ("fundamentally"): 보유 잔액과 회전 가운데 무엇이 준비금 수익을 늘리는가](#3-갈래-2-usdc-채택-fundamentally-보유-잔액과-회전-가운데-무엇이-준비금-수익을-늘리는가)
  - [4. 갈래 3, Arc 채택: Arc의 수수료가 가는 곳과 지금 들어오는 돈](#4-갈래-3-arc-채택-arc의-수수료가-가는-곳과-지금-들어오는-돈)
  - [5. 10-Q가 적은 두 목표: 준비금 수익 증대와 매출 다변화](#5-10-q가-적은-두-목표-준비금-수익-증대와-매출-다변화)
  - [6. 방식 3, 회사 안에서 쓰는 에이전트: 개발 속도와 비용](#6-방식-3-회사-안에서-쓰는-에이전트-개발-속도와-비용)
- [다. 판정: 에이전트라는 수단이 1번의 두 문제에 닿는가](#다-판정-에이전트라는-수단이-1번의-두-문제에-닿는가)
  - [1. 고객 쪽: 맞는 방향이지만 일정이 남았습니다](#1-고객-쪽-맞는-방향이지만-일정이-남았습니다)
  - [2. 회사 쪽, 제 기준(금리 의존): 의존을 줄이는 수단이라고 할 수 없습니다](#2-회사-쪽-제-기준금리-의존-의존을-줄이는-수단이라고-할-수-없습니다)
  - [3. 회사 쪽, 회사 기준(USDC와 Arc의 채택): 일관되지만 규모는 아직 작습니다](#3-회사-쪽-회사-기준usdc와-arc의-채택-일관되지만-규모는-아직-작습니다)
  - [4. 회사 안의 생산성: 다변화와 같은 방향이지만 효과를 잴 숫자가 없습니다](#4-회사-안의-생산성-다변화와-같은-방향이지만-효과를-잴-숫자가-없습니다)
- [라. 빈칸: 무엇이 비었고, 어떻게 채울 수 있으며, 앞으로 어떻게 채워질 것 같은가](#라-빈칸-무엇이-비었고-어떻게-채울-수-있으며-앞으로-어떻게-채워질-것-같은가)
- [마. 다음 질문으로 넘기는 것](#마-다음-질문으로-넘기는-것)
- [한계](#한계)
- [뒤에서 고친 것](#뒤에서-고친-것)
- [인용 위치](#인용-위치)

## 한 줄 답

**에이전트는 고객이 쓰는 도구로는 맞는 방향이지만 Circle 매출과 가까운 고객에게는 아직 닿지 않았고, 회사의 매출 경로로는 회사가 세운 기준(USDC와 Arc의 채택)과 일관되지만 금리 의존(제 해석)을 줄이지 않으며, 회사 안의 생산성 도구로는 매출 다변화와 같은 방향이지만 효과를 보여 주는 숫자가 없습니다.**

- 고객 쪽(가 절): 지금 나와 있는 에이전트 제품이 푸는 문제는 두 가지입니다.
  - 에이전트를 만드는 개발자: 개인 키를 코드에 넣거나 사람용 계정과 수동 승인에 기대야 했던 문제
  - API와 데이터를 파는 쪽: 구독제 말고는 작은 금액을 받을 방법이 없던 문제
  - 1번에서 본 Circle의 주된 고객(은행, PSP, 기업, 기관)의 문제에는 에이전트 장치가 아직 붙지 않았습니다.
  - 2-3에서 가장 큰 빈칸이던 수요는 "에이전트가 돈을 버는 고리"로 채우겠다며 하반기에 짓는 중입니다.
- 회사 쪽(나 절): 에이전트가 언제 매출이 되느냐는 질문에 대한 CEO의 답은 세 갈래이고, "some"과 "fundamentally"로 무게가 갈립니다.
  - 갈래 1, 프로토콜 매출("some"): 2분기 공시에서 사용량 수수료가 들어갈 줄은 매출의 0.76%입니다.
  - 갈래 2와 3, USDC 채택과 Arc 채택("fundamentally"): USDC 채택은 준비금 수익에 닿고, Arc 채택이 Circle 매출이 되는 경로는 4번에서 다룹니다.
  - 기타 매출이 늘어난 이유에 에이전트는 없습니다.
  - 회사 안에서 쓰는 에이전트(나 절 6)는 매출이 아니라 비용과 개발 속도로 회사에 닿습니다. 2분기에 AI 도구 비용이 310만 달러 늘었고, 개발 속도는 CEO의 말("several hundred percent")로만 있습니다.
- 판정(다 절): 어떤 기준을 쓰는지에 따라 갈립니다.
  - 고객 쪽: 맞는 방향이지만 일정이 남아 있습니다.
  - 회사가 세운 기준(USDC와 Arc의 채택): 방향은 일관되고, 규모는 아직 작습니다(다 절 3).
  - 제 기준(금리 의존): 에이전트는 이 의존을 줄이는 수단이 아니라 준비금 수익을 늘리는 수단입니다(제 판단, 확신도 중간). 이 기준은 회사가 적은 목표가 아니라, 제가 1번에서 매출의 95.2%가 금리에 묶인 준비금 수익인 것을 보고 읽은 해석입니다.
  - 회사 안의 생산성: 회사가 적은 매출 다변화 목표와 같은 방향이지만, 효과의 크기를 판정할 숫자가 없습니다(다 절 4).
- 빈칸(라 절): 매출과 가까운 고객에게 닿는 장치, 버는 고리의 첫 바퀴, 에이전트가 쥔 잔액, 기관이 요구하는 운영 층, 회사 안 생산성의 효과, 에이전트 거래의 수수료가 비어 있습니다. 가장 먼저 채워질 것은 회사가 하반기 일정으로 적은 고리의 첫 바퀴라고 봅니다(제 판단, 확신도 낮음).

나눈 기준:

- "고객 쪽"과 "회사 쪽": 1번의 구분(1-1 고객의 문제, 1-2 회사의 문제)을 그대로 썼고, 1번에서 사용자가 고른 picker 답("고객의 문제와 회사의 문제를 나눠서 (추천)")을 따랐습니다.
- 나 절의 세 갈래: 제 구분입니다. 다만 원문이 "some revenue around the protocols themselves, but fundamentally ..."로 스스로 갈라 놓았기 때문에 그 경계를 따랐습니다.
- 에이전트를 쓰는 세 방식: 사용자의 구분입니다(2026-10-15 피드백, "회사 쪽에서 기존의 서비스에 에이전트를 붙이는 방식이 있고, 지금처럼 에이전트를 개발할 수 있는 툴을 제공할 수도 있으며, 에이전트와 함께 지금 개발하는 것들의 생산성을 높일 수 있음"). 위의 "고객 쪽"과 "회사 쪽"은 누구의 문제인가로 나눈 것이고, 세 방식은 에이전트를 누가 어떻게 쓰는가로 나눈 것입니다. 두 구분이 만나는 곳은 아래 표와 같습니다.

| 방식 (사용자의 구분) | 에이전트를 쓰는 쪽 | Circle에 있는 것 | 상태 | 이 답에서 다룬 곳 |
|---|---|---|---|---|
| 1. 기존 서비스에 에이전트를 붙임 | 고객의 에이전트 | CPN의 "agentic payments" 용도와 백서 예시, 에이전트가 잔액을 두고 쓰는 Gateway(Nanopayments), Circle의 API와 프로토콜을 AI 에이전트가 바로 쓰게 하는 skills 라이브러리와 MCP 서버(4분기 콜 326-327, 1057-1059행) | CPN은 계획("In the future"), Nanopayments는 Agent Stack의 일부로 나옴, skills와 MCP 서버는 4분기 콜에서 나와 있다고 말함 | 가 절 1의 고객 표 1행, 나 절 3 |
| 2. 에이전트를 만드는 도구를 제공 | 고객(개발자)이 만든 에이전트 | Agent Wallets, Marketplace, CLI, Arc Studio, Arc Portal, 하반기의 버는 기능 | 결제하는 기능은 상반기에 나옴, 버는 기능은 하반기에 짓는 중 | 가 절 1의 고객 표 4-7행, 가 절 2 |
| 3. 회사 안의 생산성 | Circle의 직원과 회사 | 에이전트가 돌리는 소프트웨어 개발, 직원에게 주는 AI 도구와 에이전트 제작 도구, 10-Q가 적은 회사 안의 AI 쓰임(사기 탐지부터 고객 지원까지) | 상반기 "adoption at scale", 하반기 "orchestration at scale"(2분기 콜 380, 386-387행) | 나 절 6, 다 절 4 |

- 1과 2의 경계는 겹칩니다. Nanopayments는 기존 Gateway 위에 만든 기능이면서 Agent Stack의 한 부분입니다(Agent Stack 블로그 207, 222행). 표에서는 기존 제품의 이름이 붙은 것을 1에 두었고, 이 배치는 제 판단입니다.
- 방식 1은 "Circle의 기존 서비스를 에이전트가 쓸 수 있게 붙이는 것"으로 읽었습니다. Circle이 자기 업무에 AI를 넣는 것(10-Q의 사기 탐지, 거래 모니터링 등)은 회사 안의 일이므로 방식 3에 두었습니다. 사용자의 방식 3은 개발 생산성이었으므로, 운영 업무까지 넣은 것은 제가 넓힌 것입니다.
- 처음 답은 누구의 문제인가로만 나눴기 때문에 방식 3이 통째로 빠져 있었습니다.

**그림 1. 3번 답의 구조: 세 방식, 두 쪽의 장치와 경로, 기준에 따라 갈리는 판정과 빈칸**

한국어판:

```text
3번 질문: 에이전트라는 수단이 1번의 두 문제에 닿는가

에이전트를 쓰는 세 방식 (사용자의 구분, 한 줄 답 아래 표)
  방식 1 기존 서비스에 붙임, 방식 2 만드는 도구 제공, 방식 3 회사 안의 생산성

고객 쪽 (가 절): 방식 1과 2
  |
  +-- 장치가 나온 곳: 에이전트를 만드는 개발자 (고객 표 5행), 파는 쪽 (6행)
  |     H1 2026 결제하는 기능은 나옴, H2 2026 버는 기능은 짓는 중
  |
  +-- 매출과 가까운 고객 (1-3행: 은행, PSP, 기업, 기관)
        1행 CPN 백서의 예시 하나 ("In the future"), 2행과 3행은 장치 없음

회사 쪽 (나 절)
  |
  +-- CEO 답의 세 갈래 (2분기 실적 콜 991-993행)
  |     +-- 갈래 1 프로토콜 매출 ("some") --------> Transaction revenue, 매출의 0.76%
  |     +-- 갈래 2 USDC 채택 ("fundamentally") ---> 준비금 수익
  |     +-- 갈래 3 Arc 채택 .....................> Circle 매출: 숫자 없음 (4번에서)
  |
  +-- 방식 3, 회사 안의 에이전트 (나 절 6)
        비용 ------> 2분기 AI 도구 비용 310만 달러 증가 (10-Q)
        개발 속도 ..> 제품 확대와 새 수익 기회: CEO의 말, 숫자 없음

판정 (다 절): 어떤 기준을 쓰는지에 따라 갈림
  고객 쪽: 맞는 방향, 일정이 남음
  회사 기준 (USDC와 Arc 채택): 일관됨, 규모는 아직 작음
  제 기준 (금리 의존, 제 해석): 줄이는 수단이 아님, 갈래 2는 의존을 그대로 둠
  회사 안의 생산성: 다변화와 같은 방향, 효과를 잴 숫자 없음

빈칸 (라 절): 매출과 가까운 고객의 장치, 고리의 첫 바퀴, 에이전트가 쥔 잔액,
              기관의 운영 층, 생산성의 효과, 에이전트 거래의 수수료
```

English version:

```text
Question 3: does the agent route reach the two problems from question 1?

Three ways of using agents (the user's split, table under the one-line answer)
  way 1 attach to existing services, way 2 provide building tools,
  way 3 productivity inside the company

Customer side (section ga): ways 1 and 2
  |
  +-- Where tools shipped: developers building agents (customer table row 5),
  |   sellers (row 6)
  |     H1 2026 paying shipped, H2 2026 earning being built
  |
  +-- Customers close to revenue (rows 1-3: banks, PSPs, businesses, institutions)
        row 1 one CPN whitepaper example ("In the future"), rows 2 and 3 no tools

Company side (section na)
  |
  +-- Three branches of the CEO's answer (Q2 call 991-993)
  |     +-- Branch 1 protocol revenue ("some") ---------> Transaction revenue, 0.76%
  |     +-- Branch 2 USDC adoption ("fundamentally") ---> reserve income
  |     +-- Branch 3 Arc adoption ......................> Circle revenue: no figure
  |                                                       (question 4)
  |
  +-- Way 3, agents inside the company (section na 6)
        cost ------------> Q2 AI tool costs up USD 3.1M (10-Q)
        development pace ..> wider products, new revenue: CEO's words, no figure

Verdict (section da): depends on the yardstick
  Customer side: right direction, schedule still open
  Company yardstick (USDC and Arc adoption): consistent, still small in scale
  My yardstick (rate dependence, my reading): not a way to reduce it;
    branch 2 leaves the dependence as it is
  Productivity inside the company: same direction as diversification,
    no figure to measure the effect

Gaps (section ra): tools for customers close to revenue, the loop's first turn,
  balances held by agents, the institutional operating layer,
  the effect of productivity, fees on agent transactions
```

그림은 위에서 아래로 읽습니다. 맨 위의 세 방식은 사용자의 구분이고, 한 줄 답 아래 표에서 각 방식이 이 답의 어느 절에 있는지 보입니다. 고객 쪽은 방식 1과 2를, 회사 쪽의 마지막 가지는 방식 3을 다룹니다.

고객 쪽은 가 절의 고객 표를 두 무리로 묶은 것입니다. 장치가 나온 곳은 에이전트를 만드는 개발자와 파는 쪽이고, 결제하는 기능은 상반기에 나왔지만 버는 기능은 하반기에 짓는 중입니다. Circle 매출과 가까운 고객(은행, PSP, 기업, 기관)에게는 CPN 백서의 예시 하나만 있고, 그것도 "In the future"로 시작합니다. 고객 표 4행(앱 개발자)과 7행(에이전트에게 일을 맡기는 사람)은 이 개관에서 뺐고 그림 2에 있습니다.

회사 쪽은 두 가지입니다. 첫째는 CEO 답의 세 갈래입니다. 세 갈래로 나눈 것은 제 구분이고, 원문이 "some"과 "fundamentally"로 갈라 놓은 경계를 따랐습니다. 실선 화살표(`-->`)는 그 갈래가 공시의 어느 줄에 닿는지를 가리키고, 점선 화살표(`...>`)는 콜에서 주장되었지만 숫자로 보이지 않은 연결입니다. 갈래 1은 매출의 0.76%인 Transaction revenue 줄에 닿고, 갈래 2는 준비금 수익에 닿으며, 갈래 3이 Circle 매출이 되는 경로는 4번에서 다룹니다. 둘째는 회사 안에서 쓰는 에이전트(방식 3)입니다. 비용은 10-Q에 숫자가 있고(실선), 개발 속도가 제품 확대와 새 수익 기회로 이어진다는 것은 CEO의 말입니다(점선).

판정은 기준마다 한 줄입니다. 같은 사실을 놓고도 회사가 세운 기준(USDC와 Arc의 채택)으로 보면 일관되고, 제가 1번에서 읽은 기준(금리 의존)으로 보면 줄이는 수단이 아닙니다. 금리 의존이라는 기준은 회사가 적은 목표가 아니라 제 해석입니다. 회사 안의 생산성은 다변화와 같은 방향이지만 효과를 잴 숫자가 없습니다. 맨 아래 빈칸 여섯은 라 절에서 하나씩 다룹니다.

## 가. 고객 쪽 해법: 고객마다 어떤 에이전트 장치를 냈고, 그 장치는 나왔는가

작은 질문: 고객의 기존 문제를 에이전트 제품은 어떤 장치로 풀겠다고 하고, 그 장치는 나왔는가? (세 방식 가운데 1과 2)

한 줄 답: **나온 장치는 에이전트를 만드는 개발자와 API를 파는 쪽의 문제를 풀고, Circle 매출과 가까운 고객(은행, PSP, 기업, 기관)에게는 CPN 백서의 예시 하나뿐이며, 수요를 만들 버는 고리는 하반기에 짓는 중입니다.**

### 1. 고객별 장치와 상태: 장치가 나온 곳과 나오지 않은 곳

1번의 고객 다섯 부류에 2번에서 드러난 고객 둘(파는 쪽, 일을 맡기는 사람)을 더했습니다. "1-1의 문제" 칸은 1번 답에서 가져왔고, "장치"와 "상태" 칸은 이번에 원문을 열어 채웠습니다.

| 고객 | 1-1의 문제 | 에이전트 장치 | 상태 | 근거 |
|---|---|---|---|---|
| 1. 은행, PSP, 기업 (CPN) | 해외 송금 | 물류 회사의 에이전트가 싱가포르 운송사를 고르면, CPN에 연결된 송금 쪽 기관이 달러를 USDC로 바꿔 보내고 받는 쪽 기관이 SGD로 지급합니다 [Circle 글]. 10-K는 CPN이 지원하려는 용도에 "agentic payments"를 넣습니다 [공시]. | 계획입니다. 백서 문장이 "In the future"로 시작합니다. | CPN 백서 442-447행, 10-K 500-501행 |
| 2. 블록체인을 직접 다루기 어려운 기업 (Managed Payments) | 스테이블코인 운영 부담 | 없습니다. | - | 1번 답의 검색(`rg -n -i 'agent'`, 출시 글 두 편에서 0건) |
| 3. 기관 환전 (StableFX) | 상대방마다 따로 계약하고 신용 한도를 정해야 하는 부담(1번이 10-K 512-515행에서 읽은 것) | 없습니다. | - | 1번 답의 검색(제품 페이지의 일치 1건은 메뉴 링크) |
| 4. 앱 개발자 | 결제와 이동 기능을 직접 구현하는 부담 | 에이전트가 돈을 쓰는 주체가 아니라 개발 도구입니다. Arc Studio는 "an onchain coding agent"입니다 [Circle 글]. | 나왔습니다. 다만 "Arc Studio deploys to Arc testnet only."입니다 [Team Arc 글]. | Circle 메인넷 보도자료 77행, Arc 개발 문서 arc-studio-cli 24행 |
| 5. 에이전트를 만드는 개발자 (Agent Stack) | "developers can be pushed toward hard-coded private keys, human-centric accounts, or manual approvals" [Circle 글] | 에이전트가 USDC를 쥐고 옮기는 전용 지갑(Agent Wallets)과 CLI. 지갑은 사람용 계정이 아니라 기계가 시작하는 거래를 위해 만들어졌고("wallets designed for machine-initiated operation"), 사람이 정한 정책(기간별 지출 한도, 지갑과 컨트랙트 주소의 허용 목록과 차단 목록)을 실행 전에 지갑에서 검사합니다 [Circle 글]. | 2026-05에 나왔습니다. | Agent Stack 블로그 211, 213, 215행 |
| 6. (2번에서 드러난 고객) API와 데이터를 파는 쪽 | 1-1에 없습니다. 원문은 "human-scale subscriptions and manual integrations"를 바꿀 대상으로 적습니다 [Circle 글]. | Agent Marketplace, x402 결제, Nanopayments(가스비 없는 작은 금액 이체) | 결제를 받는 장치는 나왔습니다. "Agents can earn"은 하반기에 짓는 중입니다. | Agent Stack 블로그 214, 222행, 2분기 발표 자료 528행 |
| 7. (1번 표에서 더한 고객) 에이전트에게 일을 맡기는 사람 (Arc Portal) | 1-1에 없습니다. | "Arc Portal lets people fund agent wallets, set spend limits, and delegate onchain tasks with visibility and control." [Circle 글] | Circle 메인넷 보도자료가 쓸 수 있는 창구로 소개합니다. | Circle 메인넷 보도자료 45행 |

5행의 장치는 블로그가 든 문제 셋에 두 부분으로 답합니다. 개인 키를 코드에 넣는 것과 사람용 계정에 기대는 것에는 기계가 시작하는 거래를 위한 전용 지갑으로, 수동 승인에는 실행 전에 지갑이 검사하는 정책으로 답합니다(Agent Stack 블로그 211, 213행). 이 짝은 블로그가 한 문단에서 문제와 장치를 차례로 적은 것을 제가 맞춘 것입니다. 2분기 발표 자료도 Agent Wallet을 "USDC balance + spending policy"로 줄여 적어 두 부분을 함께 듭니다(발표 자료 531-532행).

6행의 문제는 Circle만의 말이 아닙니다. vault의 Agent Stack 유닛에 함께 보관한 Keyrock 글은 x402 결제 1억 7,600만 건의 중앙값이 0.01-0.10달러이고, 76%가 카드 수수료 하한(0.30달러)보다 작다고 씁니다("with 76% of activity falling below the \$0.30 card-fee floor", Keyrock 글 74행) [다른 회사 글]. 카드로는 받을 수 없던 금액을 받게 해 주는 것이 파는 쪽에 주는 도움입니다.

**그림 2. 고객과 에이전트 장치의 상태: 장치가 나온 곳은 매출과 가까운 고객 밖에 있음**

한국어판:

```text
+-----------+----------------------------------+-----------------------------------+
| 장치 상태 | 매출과 가까운 고객               | 그 밖의 고객                      |
|           | (고객 표 1-3행)                  | (고객 표 4-7행)                   |
+-----------+----------------------------------+-----------------------------------+
| 나옴      | (없음)                           | 4 앱 개발자: Arc Studio           |
|           |                                  |   (개발 도구, 테스트넷만)         |
|           |                                  | 5 에이전트를 만드는 개발자:       |
|           |                                  |   Agent Wallets (2026-05)         |
|           |                                  | 6 파는 쪽: 결제를 받는 장치       |
|           |                                  |   (버는 기능은 H2 2026에 짓는 중) |
|           |                                  | 7 에이전트에게 일을 맡기는 사람:  |
|           |                                  |   Arc Portal (메인넷 보도자료)    |
+-----------+----------------------------------+-----------------------------------+
| 계획      | 1 은행, PSP, 기업: CPN           | (없음)                            |
|           |   (백서의 예시, "In the future") |                                   |
+-----------+----------------------------------+-----------------------------------+
| 없음      | 2 Managed Payments               | (없음)                            |
|           | 3 StableFX                       |                                   |
+-----------+----------------------------------+-----------------------------------+
```

English version:

```text
+--------------+--------------------------------+------------------------------------+
| Device state | Customers close to revenue     | Other customers                    |
|              | (customer table rows 1-3)      | (customer table rows 4-7)          |
+--------------+--------------------------------+------------------------------------+
| Shipped      | (none)                         | 4 App developers: Arc Studio       |
|              |                                |   (dev tool, testnet only)         |
|              |                                | 5 Developers building agents:      |
|              |                                |   Agent Wallets (2026-05)          |
|              |                                | 6 Sellers: payment-receiving tools |
|              |                                |   (earning: building in H2 2026)   |
|              |                                | 7 People delegating to agents:     |
|              |                                |   Arc Portal (mainnet release)     |
+--------------+--------------------------------+------------------------------------+
| Planned      | 1 Banks, PSPs, businesses: CPN | (none)                             |
|              |   (whitepaper example,         |                                    |
|              |   "In the future")             |                                    |
+--------------+--------------------------------+------------------------------------+
| None         | 2 Managed Payments             | (none)                             |
|              | 3 StableFX                     |                                    |
+--------------+--------------------------------+------------------------------------+
```

이 그림은 위의 고객 표 일곱 행을 두 기준으로 다시 놓은 것입니다. 행은 장치의 상태(나옴, 계획, 없음)이고, 열은 1번에서 Circle 매출과 가까운 고객으로 본 1행부터 3행까지와 그 밖의 고객입니다. 숫자는 고객 표의 행 번호입니다.

장치가 나온 칸은 모두 오른쪽 열에 있습니다. 왼쪽 열에는 1행의 계획(CPN 백서의 예시, "In the future"로 시작) 하나와 장치가 없는 2행과 3행만 있습니다. 가 절 3의 두 판단("지금 나와 있는 장치가 푸는 문제는 에이전트를 만드는 사람과 파는 사람의 문제", "매출과 가까운 고객의 문제에는 에이전트 장치가 붙지 않았다")이 이 분포에서 나옵니다.

오른쪽 열의 네 행은 성격이 서로 다릅니다. 4행의 Arc Studio는 에이전트가 돈을 쓰는 장치가 아니라 개발 도구이고, 테스트넷에만 배포합니다. 6행은 결제를 받는 장치가 나왔지만 버는 기능은 하반기에 짓는 중입니다. 7행은 Circle 메인넷 보도자료가 쓸 수 있는 창구로 소개한 것이어서, 실제 사용 규모는 확인하지 않았습니다. 오른쪽 열의 제목을 "매출과 먼 고객"이라 하지 않고 "그 밖의 고객"이라 한 것은, 답이 5행과 6행만 매출과 멀다고 적었고 4행과 7행은 나누지 않았기 때문입니다.

### 2. 버는 고리: 수요라는 빈칸에 대한 회사의 답과 그 일정

2-3에서 회사가 스스로 비었다고 한 칸 가운데 가장 큰 것은 수요였습니다(Beyond 글 39행 "But institutional volume hasn't shown up yet."). 이 칸에 대한 회사의 답은 2분기 발표 자료 18쪽(Agent Stack 쪽)에 있습니다. 쪽 제목은 "Circle Agent Stack: from agent payment rail to agent labor market"입니다(발표 자료 515행) [Circle 글].

이 쪽은 텍스트 추출본(`pages/`)에서 그림의 배치가 사라졌습니다. 그래서 원본 PDF의 18쪽을 그림으로 열어 단계와 화살표를 읽었습니다(`pdftoppm -f 18 -l 18 -r 110 -png raw/circle-q2-2026-earnings-presentation.pdf`). 아래 행 번호는 텍스트 추출본의 행입니다.

- 쪽은 두 칸으로 나뉩니다. 왼쪽 "Agents can pay"는 "H1 2026 - SHIPPED"이고, 오른쪽 "Agents can earn"은 "H2 2026 - BUILDING"입니다(528행).
- 왼쪽 칸은 네 단계가 한 방향으로 이어지고, 칸 아래에 "Value flows one way"라고 적혀 있습니다(545행). 단계는 Agent Wallet("USDC balance + spending policy"), Marketplace, Pay per call("X402 - no accounts, no keys"), Settle onchain("USDC, real-time")입니다(531-542행). Marketplace의 설명 칸에는 Agent Wallet과 같은 문구가 적혀 있습니다.
- 오른쪽 칸은 순환이고, 칸 아래에 "Value cycles"라고 적혀 있습니다(545행). 그림에서는 Publish에서 들어와 Discover("open ranking"), Pay(설명은 x402와 USDC), Settle("onchain, final"), Reputation("from behavior")을 거쳐 다시 Discover로 돌아갑니다(531-542행과 원본 18쪽의 그림).
- 오른쪽 칸은 세 단계를 글로도 정의합니다. Publish는 "a paid agent, live in minutes", Reputation은 "Trust earned from real settlement", Discovery는 "Ranked on merit, like PageRank"입니다(531-541행). Pay와 Settle에는 글로 쓴 정의가 없고, 그림 안의 짧은 설명만 있습니다.
- 쪽의 부제 "Settlement feeds reputation, reputation feeds discovery, discovery drives the next payment."(516행)는 이 순환을 한 문장으로 적은 것입니다.
- 하반기 목표는 "First full turn of the loop, between strangers"입니다(522-523행).
- Arc 개발 문서도 같은 그림을 Arc 쪽 표준으로 적습니다. ERC-8004(신원과 평판)와 ERC-8183(일감 정산)을 들어 "so agents can register, find work, and get paid autonomously"라고 씁니다(Arc 개발 문서 agentic-economy 15-18행) [Team Arc 글].

이 답에서 "버는 고리"라고 부르는 것은 오른쪽 칸의 순환입니다. 이름은 제가 붙였고, 원문의 "Agents can earn"과 "the loop"를 합친 것입니다.

[제 판단, 확신도 중간] 이 고리는 기관 수요가 아니라 에이전트끼리의 수요를 만들려는 장치입니다. 2-3의 Beyond 글이 기관 수요의 조건으로 든 것은 "authorize, govern, audit, and underwrite"(45행)였습니다. 이 쪽의 장치와 하나씩 맞춰 보면 다음과 같습니다.

- 왼쪽 칸의 지출 정책은 authorize와 govern의 일부를 에이전트 주인 쪽에서 맡습니다. Beyond 글도 정책 통제의 예로 "per-transaction and daily limits, approved-counterparty lists"를 듭니다(53행).
- 오른쪽 칸의 평판은 underwrite의 재료가 될 수 있습니다.
- audit을 맡는 장치는 이 쪽에 없고, Agent Stack 자료에도 없습니다(검색: `rg -n -i '\baudit' cb/works/web/2026-10-13-circle-agent-stack-sources/pages`, 0건). Arc 메인넷 보도자료가 "auditable records"를 내건 Agent Sector는 "THE ROAD AHEAD" 아래, 곧 로드맵에 있습니다(메인넷 보도자료 82, 86행).

그래서 고리가 돌아도 1행부터 3행까지의 고객이 에이전트를 쓰게 될지는 따로 봐야 합니다.

**그림 3. 버는 고리: 결제하는 칸과 버는 칸, 기관 수요의 조건과 맞닿는 곳**

한국어판:

```text
2분기 발표 자료 18쪽: "from agent payment rail to agent labor market"

[1] 결제하는 기능: H1 2026 SHIPPED, "Value flows one way"

  Agent Wallet ---> Marketplace ---> Pay per call ---> Settle onchain
  (USDC 잔액과                       (x402, 계정과      (USDC, 실시간)
   지출 정책)                         키 없음)

[2] 버는 기능: H2 2026 BUILDING, "Value cycles"

                          +------> Pay ----------+
                          |      (x402, USDC)    |
                          |                      v
  Publish --------> Discover                   Settle
  (유료 에이전트를  (공개 순위)                (온체인, 최종)
   몇 분 안에 게시)       ^                      |
                          |                      |
                          +---- Reputation <-----+
                               (행동에서 나옴)

  하반기 목표: "First full turn of the loop, between strangers"

[3] 기관 수요의 조건 (Beyond 글 45행): authorize, govern, audit, underwrite

  [1]의 지출 정책 ......> authorize와 govern의 일부 (에이전트 주인 쪽의 한도)
  [2]의 Reputation .....> underwrite의 재료가 될 수 있음
  audit ................> 이 쪽에 맡는 장치 없음 (Agent Sector는 로드맵)

  (점선 화살표는 제 대응, 확신도 중간)
```

English version:

```text
Q2 earnings presentation page 18: "from agent payment rail to agent labor market"

[1] Paying: H1 2026 SHIPPED, "Value flows one way"

  Agent Wallet ---> Marketplace ---> Pay per call ---> Settle onchain
  (USDC balance +                    (x402, no          (USDC, real-time)
   spending policy)                   accounts, no keys)

[2] Earning: H2 2026 BUILDING, "Value cycles"

                          +------> Pay ----------+
                          |      (x402, USDC)    |
                          |                      v
  Publish --------> Discover                   Settle
  (a paid agent,    (open ranking)             (onchain, final)
   live in minutes)       ^                      |
                          |                      |
                          +---- Reputation <-----+
                               (from behavior)

  H2 goal: "First full turn of the loop, between strangers"

[3] Conditions for institutional demand (Beyond post line 45):
    authorize, govern, audit, underwrite

  spending policy in [1] ...> part of authorize and govern (owner-side limits)
  Reputation in [2] ........> could feed underwriting
  audit ....................> no device for it on this page (Agent Sector: roadmap)

  (dotted arrows are my mapping, medium confidence)
```

그림은 위에서 아래로 세 덩어리입니다. [1]과 [2]는 발표 자료 18쪽의 두 칸을 옮긴 것이고, [3]은 2-3에서 본 Beyond 글의 기관 수요 조건을 그 아래에 둔 것입니다.

[1]의 화살표는 쪽에 그려진 대로 한 방향입니다. 지갑을 만들고, 마켓플레이스에서 서비스를 찾고, 호출마다 x402로 값을 치르고, 온체인에서 정산합니다. 이 칸은 상반기에 나왔고, 쪽은 이 칸을 "Value flows one way"라고 부릅니다.

[2]의 화살표도 쪽에 그려진 대로입니다. Publish는 고리 밖에서 Discover로 들어오는 입구이고, 고리 자체는 Discover, Pay, Settle, Reputation의 네 단계입니다. 정산 기록이 평판이 되고("Trust earned from real settlement"), 평판이 순위를 정하며("Ranked on merit, like PageRank"), 순위가 다음 결제를 낳습니다. 화살표는 돈의 이동이 아니라 단계의 순서입니다. 다만 Pay에서 Settle로 가는 화살표에는 실제로 USDC가 움직입니다. 쪽은 이 칸을 하반기에 짓는 중이라고 적고, 하반기 목표를 모르는 상대끼리 고리를 처음 한 바퀴 돌리는 것으로 둡니다. 발표 자료 시점에는 고리가 아직 한 바퀴도 돌지 않았다는 뜻입니다.

[3]의 점선 화살표는 제가 맞춘 대응이고, 확신도는 중간입니다. 지출 정책은 authorize와 govern의 일부를 에이전트 주인 쪽에서 맡고, 평판은 underwrite의 재료가 될 수 있습니다. audit을 맡는 장치는 이 쪽에 없으며, Arc의 Agent Sector가 로드맵에 있습니다. 그래서 고리가 돌아도 매출과 가까운 고객(고객 표 1-3행)이 에이전트를 쓰게 될지는 따로 봐야 합니다.

### 3. 고객 쪽 정리: 장치가 푸는 문제와 장치가 닿지 않은 고객

- [제 판단, 확신도 높음] 지금 나와 있는 장치가 푸는 문제는 에이전트를 만드는 사람(5행)과 파는 사람(6행)의 문제입니다.
- [제 판단, 확신도 높음] 1-1에서 Circle 매출과 가까운 고객(1행부터 3행까지)의 문제에는 에이전트 장치가 붙지 않았습니다. 1행은 예시와 계획이고, 2행과 3행은 1번에서 검색한 자료에 에이전트 이야기가 없습니다.

## 나. 회사 쪽 경로: 에이전트 매출의 길, 공시에 보이는 크기, 회사 안에서 쓰는 에이전트

작은 질문: 회사의 기존 문제(제 해석으로는 금리 의존)에 대해 회사는 에이전트로 무엇을 하겠다고 하고, 그것은 공시에서 얼마인가? 회사 안에서 쓰는 에이전트는 어디에 닿는가? (세 방식 가운데 3을 포함)

한 줄 답: **CEO가 말한 에이전트 매출의 길은 세 갈래이고 금액도 시점도 없으며, 사용량 수수료가 들어갈 줄은 매출의 0.76%이고 주된 갈래인 USDC 채택은 준비금 수익으로 가며, 회사 안에서 쓰는 에이전트는 매출이 아니라 비용과 개발 속도로 회사에 닿습니다.**

### 1. CEO의 답: 에이전트 매출의 시점을 묻는 질문에 무엇이라고 답했는가

2분기 실적 콜에서 Clear Street의 Owen Lau가 정면으로 물었습니다. "When should we expect to see more revenue contribution from agentic commerce? I know it's still small."(941행) 이어서 "It's still growing, but we just want to understand when it can become more material to Circle longer term."(942행)이라고 덧붙였습니다.

Allaire의 답(945-993행)은 하반기 제품(신원, 발견, 평판, 버는 기능)을 설명한 뒤 매출을 이렇게 말합니다.

> In terms of direct impact on revenue, I mean, very clearly, we believe over time, the amount of stablecoin / money that is held and used in agentic applications will grow and the velocity of transactions will grow. (984-985행)

> So we see the agentic stack as driving some revenue around the protocols themselves, but fundamentally / driving stablecoin adoption, which drives revenue and driving Arc infrastructure adoption, which drives / revenue as well. (991-993행)

945-993행을 모두 열어 보면, 이 답에는 매출의 금액도 시점도 없습니다. 답에 나오는 숫자는 마켓플레이스의 서비스 900개(953행) 하나입니다. Owen이 물은 "material"에 대해서는 "In terms of the second half and sort of the materiality, there are a number of really key things."(962행)라고 받은 뒤, 신원, 발견, 평판, 버는 기능을 차례로 설명합니다(966-976행). 아래 세 갈래는 991-993행의 구분을 따른 것입니다.

**그림 4. CEO 답의 세 갈래: 각 갈래가 공시의 어느 줄에 닿는가**

한국어판:

```text
CEO의 답 (2분기 실적 콜 991-993행)
"some revenue around the protocols themselves, but fundamentally ..."
 |
 +-- 갈래 1 프로토콜 매출 ("some")
 |     닿는 줄 --> Transaction revenue (10-Q 1349-1351행)
 |                 2026년 2분기 533만 달러, 매출의 0.76%, 1년 전보다 -8.5%
 |                 에이전트 수수료는 이 줄 안에서 따로 표시되지 않음
 |
 +-- 갈래 2 USDC 채택 ("fundamentally")
 |     닿는 줄 --> 준비금 수익: 평균 유통량과 수익률로 설명됨 (10-Q 2300-2302행)
 |       보유 잔액 (held)     결과: 준비금 수익을 늘림
 |       회전 (velocity)      결과: 수수료가 붙을 때만 갈래 1의 줄로 감,
 |                                  준비금 수익은 그대로
 |     에이전트가 보유한 잔액의 숫자: 찾지 못함 (본 숫자는 모두 흐름)
 |
 +-- 갈래 3 Arc 채택
       거래 수수료 =====> 검증자들 (Circle은 그 가운데 하나)
       지금 들어오는 돈: ARC 토큰 사전판매, 의무를 이행한 뒤 기타 매출로 인식
       Arc 채택 ........> Circle 매출: 콜에서 주장됨, 숫자 없음 (4번에서)

  -->   그 갈래가 들어가는 공시의 줄
  ==>   돈이 가는 곳
  ...>  콜에서 주장되었지만 숫자로 보이지 않은 연결
```

English version:

```text
The CEO's answer (Q2 earnings call lines 991-993)
"some revenue around the protocols themselves, but fundamentally ..."
 |
 +-- Branch 1 protocol revenue ("some")
 |     reaches --> Transaction revenue (10-Q lines 1349-1351)
 |                 Q2 2026 USD 5.33M, 0.76% of revenue, -8.5% year over year
 |                 agent fees are not shown separately within this line
 |
 +-- Branch 2 USDC adoption ("fundamentally")
 |     reaches --> reserve income: explained by average circulation
 |                 and yield (10-Q lines 2300-2302)
 |       balance held         result: raises reserve income
 |       velocity             result: goes to branch 1's line only if a fee applies;
 |                                    reserve income unchanged
 |     balance held by agents: no figure found (all figures seen are flows)
 |
 +-- Branch 3 Arc adoption
       transaction fees ===> validators (Circle is one of them)
       money coming in now: ARC token presale, other revenue once obligations are met
       Arc adoption .......> Circle revenue: claimed on the call, no figure (question 4)

  -->   the line of the disclosure the branch goes into
  ==>   where money goes
  ...>  a link claimed on the call but not shown in figures
```

세 갈래로 나눈 것은 제 구분이지만, CEO의 답이 "some"과 "fundamentally"로 스스로 갈라 놓았으므로 그 경계를 따랐습니다. 화살표는 기호마다 뜻이 하나이고, 그림 아래에 적었습니다. `-->`는 그 갈래가 공시의 어느 줄에 들어가는지를, `==>`는 돈이 가는 곳을, `...>`는 콜에서 주장되었지만 숫자로 보이지 않은 연결을 가리킵니다. 갈래 2 안에서 보유와 회전이 각각 낳는 결과는 화살표 대신 "결과:"로 적었습니다.

갈래 1은 사용량 수수료가 들어가는 Transaction revenue 줄에 닿습니다. 이 줄은 2026년 2분기에 매출의 0.76%이고 1년 전보다 8.5% 줄었으며, 공시가 제품별로 나누지 않으므로 에이전트 몫은 알 수 없습니다. 갈래 2는 준비금 수익에 닿습니다. 10-Q는 준비금 수익의 변화를 평균 유통량과 수익률로만 설명하므로, 준비금 수익을 늘리는 것은 에이전트가 쥐고 있는 잔액입니다. 에이전트가 USDC를 빨리 돌려도 수수료가 붙지 않으면 준비금 수익은 늘지 않고, 수수료가 붙으면 그 돈은 갈래 1의 줄로 갑니다. 보유 잔액과 회전을 나눈 것은 제 구분입니다. 그런데 지금까지 본 규모 숫자는 모두 흐름(처리 금액)이고, 에이전트가 보유한 잔액을 밝힌 숫자는 찾지 못했습니다. 갈래 3에서 Arc의 거래 수수료는 검증자들에게 가고 Circle은 그 가운데 하나입니다. 지금 Arc에서 실제로 들어오는 돈은 ARC 토큰 사전판매이며, Arc 채택이 Circle 매출이 되는 경로는 4번에서 다룹니다.

### 2. 갈래 1, 프로토콜 매출 ("some"): 공시의 어느 줄에 들어가고, 그 줄은 얼마인가

- 10-Q의 매출 표에서 사용량 수수료가 들어갈 줄은 Transaction revenue입니다. 정의는 "usage-based, volume-based, or event-driven transactions"이고, 그 안에 "use of Circle infrastructure in facilitating digital asset transactions (including CCTP)"가 있습니다(10-Q 1349-1351행) [공시].
- 2026년 2분기 Transaction revenue는 533만 달러이고, 1년 전 582.5만 달러보다 8.5% 줄었습니다(10-Q 1326행). 전체 매출 7억 131만 5천 달러의 0.76%입니다(`python3 -c "print(round(5330/701315*100,2), round((5330/5825-1)*100,1))"`, 결과 0.76과 -8.5).
- [제 판단, 확신도 중간] 에이전트가 Gateway나 Nanopayments로 수수료를 낸다면 이 줄에 들어갈 것으로 보입니다. 그러나 공시는 이 줄을 제품별로 나누지 않습니다. 그래서 에이전트 수수료가 얼마인지는 공시로 알 수 없습니다.
- 10-Q는 기타 매출이 늘어난 이유로 "additional integration services performed, as well as an increase in fund management fees and redemption fees"를 듭니다(2303-2305행). 에이전트는 이유에 없습니다. 10-Q 전체에서 agent가 나오는 줄은 107-112행과 114행(용어 정의), 1900행(제품 목록), 2924행(AI 위험 요인의 "agentic payment capabilities")뿐입니다(검색: `rg -n -i agent <10-Q>`, 9줄).
- CFO는 같은 콜에서 기타 매출의 큰 줄(subscription and services)이 "based on the partnerships that we build with other blockchains"라고 설명했습니다(901-903행).
- 기타 매출 가이던스가 1억 5천만-1억 7천만 달러에서 3억 1천만-3억 3천만 달러로 오른 것은 각주 (3) "Includes recognized ARC Token presale revenue."에 따른 것입니다(실적 보도자료 209, 219행). 사전판매 대금은 기타 매출로 인식합니다(10-Q 784-785행).

### 3. 갈래 2, USDC 채택 ("fundamentally"): 보유 잔액과 회전 가운데 무엇이 준비금 수익을 늘리는가

- Allaire는 에이전트가 쓰는 USDC의 "held"(보유)와 "velocity"(회전)가 함께 늘 것이라고 했습니다(984-985행). 두 말을 나눈 것은 제 구분입니다. 나눈 이유는 준비금 수익이 어떻게 생기는지를 10-Q가 스스로 적기 때문입니다. 10-Q는 준비금 수익의 변화를 USDC 평균 유통량("a 25.2% increase in average daily USDC in circulation")과 수익률("a 66 basis point decline in the average yields")으로만 설명합니다(2300-2302행).
- [제 판단, 확신도 높음] 그러므로 준비금 수익을 늘리는 것은 보유 잔액입니다. 회전이 빨라져도 수수료가 붙지 않으면 준비금 수익은 늘지 않습니다.
- 잔액을 쌓는 장치는 있습니다. 2025년 4분기 콜에서 Allaire는 Gateway가 "allow autonomous agents to hold a balance and spend not just on Arc, but on other networks"라고 했습니다(4분기 콜 520-521행). Agent Stack 문서의 목차에는 "How-to: Deposit for nanopayments" 항목이 있습니다(Agent Stack 릴리스 노트 146행). 그 페이지 본문은 [미독]입니다.
- 그러나 에이전트가 보유한 USDC 잔액을 밝힌 숫자는 찾지 못했습니다(검색: `rg -n -i -e 'held by agent' -e 'agent.{0,40}balance' -e 'balance.{0,40}agent'`를 분기 보고 유닛과 Agent Stack 유닛 pages에 실행. 일치는 4분기 콜 521행 한 줄이고, 금액이 없는 기능 설명입니다).
- 지금까지 본 규모 숫자는 회사 것이든 다른 회사 것이든 모두 흐름의 크기입니다. Keyrock은 지금까지("to date") 1억 7,600만 건, 중앙값 0.01-0.10달러라고 쓰고(Keyrock 글 74행), 2-3에서 본 숫자(30일 처리액 \$24.24M, Agent Stack 블로그 209행. 하루 실거래액 약 \$28,000, Beyond 글 41행)도 처리 금액입니다.

### 4. 갈래 3, Arc 채택: Arc의 수수료가 가는 곳과 지금 들어오는 돈

Arc의 거래 수수료는 검증자에게 갑니다. 분석가 콜에서 Allaire는 "That flows to validators."라고 말한 뒤, Circle이 검증자 무리의 "key participant"이고 다른 검증자도 그 수입에 참여한다고 덧붙였습니다(분석가 콜 308-310행) [Circle 발언, 2026-08-05 분석가 콜]. 그러므로 Circle은 수수료를 혼자 받는 쪽이 아니라 여러 검증자 가운데 하나로서 나눠 받는 쪽입니다. 지금 Arc에서 실제로 들어오는 돈은 ARC 토큰 사전판매입니다. Arc 채택이 어떻게 Circle의 매출이 되는지는 4번(Arc를 어떻게 볼 수 있는가)에서 다룹니다. 3번에서는 이 갈래가 콜에서 주장되었고, 숫자로 보여지지 않았다는 점만 적습니다.

### 5. 10-Q가 적은 두 목표: 준비금 수익 증대와 매출 다변화

10-Q의 "Other products" 문단은 두 목표를 한 문단에 함께 적습니다 [공시].

- "We also expect growth in our network to drive increases in our stablecoins in circulation and thereby drive our reserve income."(1895-1896행)
- "We anticipate growing these offerings in the coming years, diversifying our revenue profile."(1896-1897행)
- 같은 문단은 다른 제품의 매출 몫을 "between 4.8% and 5.4%"로 적고(1892행), 바로 아래 목록에서 Agent Stack을 Arc를 받치는 제품으로 듭니다(1899-1900행).

1번을 처음 보낼 때 1-2에 "제품 확장을 금리 의존을 줄이려는 시도로 읽는다"는 뜻으로 쓴 것은 제 해석이었습니다(그 문장은 지금 1번 답 본문에 없고, 1번 답의 "뒤에서 고친 것" 1번에 원래 문장으로 남아 있습니다). 이 문단을 보면 회사도 "diversifying our revenue profile"을 목표로 적었으므로, 그 해석에 회사 쪽 근거가 하나 생겼습니다. 다만 같은 문단이 준비금 수익을 늘리는 것도 목표로 적었고, CEO의 콜 답은 둘 가운데 준비금 쪽을 "fundamentally"로 골랐습니다.

### 6. 방식 3, 회사 안에서 쓰는 에이전트: 개발 속도와 비용

이 소절은 한 줄 답 아래 표의 방식 3(회사 안의 생산성)을 다룹니다. 나 절 1부터 5까지가 다룬 매출의 길과는 다른 경로입니다.

- Allaire는 2분기 콜의 발표 부분에서 "Our work on agentic infrastructure is also unfolding inside of Circle. We are building toward operating an agentic corporation."이라고 말했습니다(377-378행) [Circle 발언].
- 상반기 숫자로는 "86% of our employees are weekly active users of AI tools", AI 앱 1,100개 이상(대부분 2분기에, 대부분 비개발자가 만듦), 회사 안의 AI 도구 모음에 올린 "agent skills" 수백 개를 들었습니다(380-383행).
- 개발에 대해서는 "continuous agent run software development with product development velocity up several hundred percent over the first half of the year"라고 했습니다(385-386행).
- 하반기 계획은 "from adoption at scale to orchestration at scale"입니다(386-387행). 사람과 에이전트가 함께 일하는 팀, 기억과 조율을 맡는 "company brain", 모든 직원에게 주는 에이전트 제작 도구를 들었습니다(387-393행).
- 같은 이야기는 2025년 4분기 콜에도 있습니다. AI가 "foundational infrastructure across all of our functions"가 되고 있고, 직원이 AI 에이전트를 스스로 만들고 쓰게 하는 관리 체계를 만들며, 제품 속도가 "AI coding agents"와 함께 빨라진다고 말했습니다(4분기 콜 328-336행).
- 10-Q는 회사가 AI를 쓰는 곳으로 "fraud detection, transaction monitoring, compliance, reserve analytics, smart contract development, customer support, and developer tools"를 적습니다(2922-2924행) [공시]. 10-Q는 "AI"라고만 적고, 그 가운데 무엇이 에이전트인지는 나누지 않습니다.
- 비용: 10-Q는 IT 인프라 비용에 "costs related to the use of AI-enabled tools and capabilities"를 넣고(2223-2224행), 이 비용이 2분기에 310만 달러, 상반기에 410만 달러 늘었다고 적습니다(2337, 2426행) [공시]. 2분기 증가분은 매출의 0.44%입니다(`python3 -c "print(round(3.1/701.315*100,2))"`, 결과 0.44).
- 효과: 10-Q에는 개발 속도나 생산성을 밝힌 숫자가 없습니다(검색: `rg -n -i -e productiv -e velocity <10-Q>`, 0건). "several hundred percent"는 콜에서 나온 말이고, 무엇을 잰 숫자인지는 적혀 있지 않습니다.
- 매출과의 연결: 질의응답에서 Allaire는 개발 생산성이 "cover more surface area"를 가능하게 하고, 제품이 넓어지면서 "new monetization opportunities"가 나온다고 말했습니다(675-680행).

## 다. 판정: 에이전트라는 수단이 1번의 두 문제에 닿는가

작은 질문: 그 방향이 맞는가? 곧 에이전트라는 수단이 1번에서 본 두 문제에 닿는가?

한 줄 답: **어떤 기준을 쓰는지에 따라 갈립니다: 고객 쪽은 맞는 방향이지만 일정이 남았고, 회사가 세운 기준으로는 일관되지만 규모가 작으며, 제 기준인 금리 의존으로는 줄이는 수단이 아니고, 회사 안의 생산성은 다변화와 같은 방향이지만 효과를 잴 숫자가 없습니다.**

3번에서 판정하는 범위는 제가 좁혔습니다. 여기서는 "에이전트라는 수단이 1번에서 본 두 문제에 닿는가"만 봅니다. Circle과 Arc의 방향 전체(Arc, CPN, 토큰을 포함한 것)는 6번에서 판정합니다. 이렇게 나눈 이유는 3번 질문이 "agent로"라는 수단을 정해 놓고 묻기 때문입니다.

### 1. 고객 쪽: 맞는 방향이지만 일정이 남았습니다

- [제 판단, 확신도 중간] 장치가 겨냥한 문제(5행, 6행)는 회사 글(Agent Stack 블로그 211, 214행)과 다른 회사 글(Keyrock 글 74행)이 똑같이 문제로 적습니다. 장치도 나와 있습니다. 그래서 개발자와 파는 쪽에 대해서는 문제와 해법이 맞물립니다.
- 다만 이 고객들은 1-1에서 Circle 매출과 먼 고객입니다. 매출과 가까운 고객(은행, PSP, 기업, 기관)에 대해 회사가 낸 에이전트 장치는 CPN 백서의 예시 하나이고, 그것도 "In the future"입니다.
- 수요를 만들 고리는 하반기에 짓는 중입니다. 2-3에서 본 대로, 회사 스스로 기관 수요는 "operating layer"가 생기기 전에는 늘기 어렵다고 씁니다(Beyond 글 45행 "Until the “operating layer” is built out, volume will struggle to grow."). [원문 그대로]

### 2. 회사 쪽, 제 기준(금리 의존): 의존을 줄이는 수단이라고 할 수 없습니다

- [제 판단, 확신도 중간] CEO가 꼽은 주된 경로(USDC 채택)는 준비금 수익을 늘리는 길입니다. 이 길이 성공하면 매출은 커지지만, 매출이 금리에 묶인 비율은 줄지 않습니다.
- 금리 의존을 줄일 수 있는 갈래는 프로토콜 매출 하나인데, CEO 스스로 "some"이라고 했고, 공시에서는 매출의 0.76%인 줄 안에 따로 표시되지 않습니다.
- 그래서 "에이전트로 금리 의존을 푼다"는 방향은 지금 근거로는 성립하지 않습니다.

### 3. 회사 쪽, 회사 기준(USDC와 Arc의 채택): 일관되지만 규모는 아직 작습니다

공정하게 적으면, 회사가 에이전트를 금리 의존의 해법으로 소개한 문장은 찾지 못했습니다. CEO의 답은 처음부터 "에이전트는 USDC와 Arc의 쓰임을 늘린다"였고, 이 기준으로 보면 고객 쪽 장치(USDC 잔액과 지출 정책을 갖는 에이전트 지갑, 작은 금액 결제, 잔액을 두는 Gateway)는 그 목표와 일관됩니다. 그러므로 3번의 판정은 어떤 기준을 쓰는지에 따라 갈립니다.

- 회사가 세운 기준(USDC와 Arc의 채택): 방향은 일관되고, 규모는 아직 작습니다(2-3의 숫자).
- 1-2에서 제가 읽은 문제(금리 의존, 제 해석): 에이전트는 해법으로 제시되지 않았고, 주된 경로는 오히려 그 의존을 그대로 둡니다.

### 4. 회사 안의 생산성: 다변화와 같은 방향이지만 효과를 잴 숫자가 없습니다

- [제 판단, 확신도 중간] 회사 안에서 에이전트를 쓰는 것은 매출 구성을 직접 바꾸지 않습니다. 회사가 말한 연결은 개발 속도가 제품의 범위를 넓히고, 넓어진 제품에서 새 수익 기회가 나온다는 것입니다(2분기 콜 675-680행). 이 연결은 10-Q가 적은 매출 다변화 목표(1896-1897행)와 같은 방향입니다.
- 비용 쪽은 공시에 숫자가 있습니다. 2분기 AI 도구 비용 증가분 310만 달러는 매출의 0.44%입니다(나 절 6).
- 효과 쪽은 회사의 말뿐입니다. 10-Q에는 개발 속도나 생산성의 숫자가 없고, 콜의 "several hundred percent"는 무엇을 잰 숫자인지 적혀 있지 않습니다.
- 그래서 이 방식은 방향은 다변화와 일관되지만, 지금 근거로는 효과의 크기를 판정할 수 없습니다.

## 라. 빈칸: 무엇이 비었고, 어떻게 채울 수 있으며, 앞으로 어떻게 채워질 것 같은가

작은 질문: 다 절의 판정에서 비어 있는 곳은 어디이고, 그 빈칸은 어떻게 채울 수 있으며, 앞으로 어떤 모습으로 채워질 것 같은가?

한 줄 답: **가장 먼저 채워질 빈칸은 회사가 하반기 일정으로 적은 버는 고리의 첫 바퀴이고, 가장 늦게 채워질 빈칸은 매출과 가까운 고객에게 닿는 장치와 그 고객이 요구하는 운영 층(감사와 손실 책임)이라고 봅니다(제 판단, 확신도 낮음).**

빈칸은 이 답의 가 절부터 다 절까지에서 "없다", "찾지 못했다", "[미독]", "짓는 중"으로 적은 곳을 모은 것입니다. "앞으로의 모습" 칸은 모두 제 판단입니다.

| 빈칸 | 지금 있는 것 | 채우는 길 | 앞으로의 모습 (제 판단) |
|---|---|---|---|
| 1. 매출과 가까운 고객(고객 표 1-3행)에게 닿는 장치 | CPN 백서의 예시("In the future")와 10-K의 "agentic payments" 용도 | 기관이 자기 업무에 에이전트를 쓰려면 아래 4의 운영 층이 먼저 있어야 합니다. | CPN에서 먼저 나타날 것으로 봅니다. 회사가 기관 고객 제품에서 에이전트 예시를 든 곳이 CPN 하나이기 때문입니다. 확신도 낮음. |
| 2. 버는 고리의 첫 바퀴 | 결제하는 기능(상반기에 나옴)과 마켓플레이스의 유료 서비스 900개 이상(2026-07-31 기준, 발표 자료 521-523, 551행) | 회사의 하반기 계획(게시, 평판, 발견)과 Arc의 표준(ERC-8004, ERC-8183) | 2026년 하반기 실적 발표에서 첫 바퀴를 돌렸다는 발표가 나올 가능성이 큽니다. 회사가 일정으로 적은 목표이기 때문입니다. 확신도 중간. 다만 "between strangers"가 실제 수요인지 회사가 연 시연인지는 따로 봐야 합니다. |
| 3. 에이전트가 쥔 USDC 잔액의 숫자 | 처리 금액(흐름)의 숫자만 있습니다(나 절 3). | 회사가 Agent Wallets와 Gateway에 머문 잔액을 공개하면 채워집니다. 온체인에서 에이전트 지갑 주소를 가려낼 수 있다면 직접 셀 수도 있습니다(가려낼 수 있는지는 확인하지 않았습니다). | 회사는 지금 흐름(x402 처리액과 USDC 비중)으로 말합니다. 잔액은 준비금 수익과 바로 이어지므로 커지면 공개할 이유가 생기지만, 작은 동안에는 흐름 숫자를 계속 쓸 것으로 봅니다. 확신도 낮음. |
| 4. 기관이 요구하는 운영 층 | 지출 정책(Agent Wallets), 위임(Arc Portal), 신원과 평판(하반기 계획), "auditable records"를 내건 Agent Sector(로드맵) | Beyond 글은 운영 층을 세 부분(신원과 위임과 구제, 정책과 감사, 거래 통제)으로 적습니다(49-55행). 지금 장치가 없는 곳은 감사와 구제(recourse)입니다. | 회사가 다 만들기보다, 기관이 먼저 "agent-policy framework"를 문서로 만들고(Beyond 글 66행의 권고) Arc의 Agent Sector가 기록을 맡는 모양이 될 것으로 봅니다. 확신도 낮음. |
| 5. 회사 안 생산성의 효과 | 비용 숫자(2분기 AI 도구 비용 310만 달러 증가)와 CEO의 말("several hundred percent") | 회사가 무엇을 잰 숫자인지 밝히거나, 출시 제품 수와 영업비용을 분기마다 함께 보는 것 | 효과는 기타 매출의 다변화로 드러나야 합니다. 그런데 지금 기타 매출이 늘어난 이유로 10-Q가 드는 것은 통합 서비스와 펀드 관리 수수료와 환매 수수료이고, 가이던스 상향은 ARC 사전판매 때문입니다(나 절 2). 생산성의 효과를 매출에서 따로 가려내기는 앞으로도 어려울 것으로 봅니다. 확신도 중간. |
| 6. Circle이 에이전트 거래마다 수수료를 받는가 | Agent wallet fees와 Facilitator Service 페이지의 목차 줄만 있습니다(한계 절, 본문 [미독]). | 두 페이지를 반입해 읽으면 바로 채워집니다. | 사실 확인으로 채울 수 있는 빈칸입니다. 이 답에서는 하지 않았습니다. |

빈칸이 채워지면 판정이 바뀌는 곳은 다음과 같습니다.

- 1과 4가 채워지면 다 절 1의 "매출과 가까운 고객에게는 장치가 닿지 않았다"가 바뀝니다.
- 3이 크게 채워지면 다 절 3의 "규모는 아직 작다"가 바뀝니다. 반대로 다 절 2(금리 의존)의 판정은 더 강해집니다. 잔액은 준비금 수익으로 가기 때문입니다.
- 6에서 거래마다 수수료가 있다고 확인되면 갈래 1의 무게가 달라집니다. 다만 그 수수료가 들어갈 줄이 매출의 0.76%인 동안에는 다 절 2의 판정이 바뀌지 않습니다.
- 2가 채워져도 다 절 1의 판정은 그대로입니다. 고리는 에이전트끼리의 수요를 만드는 장치이고, 기관 고객의 장치가 아니기 때문입니다(가 절 2).

## 마. 다음 질문으로 넘기는 것

- 4번: 갈래 3(Arc 채택이 어떻게 매출이 되는가)
- 5번: 흐름과 잔액의 구분. 에이전트 결제의 실제 영향력을 잴 때 처리 금액만으로는 Circle의 매출에 닿는 크기를 알 수 없습니다.
- 7번: 고객 쪽 빈칸 둘. 하나는 매출과 가까운 고객(고객 표의 1행부터 3행까지)에게 닿는 에이전트 장치가 아직 나오지 않았다는 점이고, 다른 하나는 버는 고리가 하반기에 짓는 중이라는 점입니다.

## 한계

- Agent wallet fees와 Facilitator Service 페이지는 vault에 목차 줄만 있습니다(Agent Wallets 지원 체인 문서 33행, Agent Stack 릴리스 노트 161행). 페이지 본문은 [미독]입니다. 그래서 Circle이 에이전트 거래마다 수수료를 받는지는 확인하지 못했습니다. 3번의 판정은 공시에 드러난 크기(0.76%의 줄)에 기대었습니다.
- 에이전트 지갑이나 Gateway에 머무는 USDC에 유통 비용이 얼마나 붙는지는 보지 않았습니다. 1-2에서 본 유통 비용(매출의 59%)이 이 잔액에도 같은 비율로 붙는지에 따라 갈래 2의 크기가 달라집니다.
- 2026년 3분기 실적은 아직 나오지 않았습니다. 3번의 숫자는 2026년 2분기 공시까지입니다.
- Allaire가 콜에서 "In the coming days"에 낸다고 한 백서와 로드맵(357-358행)이 2-3에서 본 2026-08-12 Open Agentic Economy 글과 같은 것인지는 확인하지 않았습니다.

## 뒤에서 고친 것

6번을 쓰면서 1번의 "회사의 문제"(금리 의존)를 회사가 적은 목표가 아니라 제 해석으로 낮췄습니다. 10-Q는 새 제품의 목표를 준비금 수익을 키우는 것과 매출 구성을 다변화하는 것으로 적고(10-Q 1895-1897행), 금리 의존을 줄이는 것은 목표로 적지 않았기 때문입니다(q6-answer.md 나 절, q6-report.md 1번). 1번 답은 이 점을 본문에 반영했고(1번 답의 "뒤에서 고친 것" 1번), 2026-10-14에 이 답에도 같은 점을 반영했습니다. 판정 자체는 바꾸지 않았습니다. 이 답은 처음 보낼 때부터 다 절 3에서 회사 기준과 1-2의 기준을 나눠 판정했으므로(다 절 3은 계획에 없던 절로, 답을 쓰면서 새로 두었습니다. q3-report.md 2번), 고친 것은 금리 의존이 제 해석이라는 표시입니다. 고치기 전의 판은 `git show 6a86e4288:cb/derived/arc-hackathon-questions-20261014/q3-answer.md`로 열 수 있습니다.

- 반영한 곳: 한 줄 답, 나 절 5의 마지막 문단(1-2의 해석을 다룬 문단, 고친 당시의 86행), 다 절 2의 제목, 다 절 3의 둘째 항목.
- 원래 문장:
  - 한 줄 답: "회사 쪽 문제(매출의 95.2%가 금리에 묶인 준비금 수익)에 대해 CEO는 ..."로 시작했고, "... 회사 쪽으로는 금리 의존을 줄이는 수단이 아니라 준비금 수익을 늘리는 수단이라고 판단합니다(확신도 중간)."로 끝났습니다.
  - 나 절 끝: "1-2에서 "제품 확장을 금리 의존을 줄이려는 시도로 읽는다"고 쓴 것은 제 해석이었습니다."
  - 다 절 2의 제목: "회사 쪽: 금리 의존을 줄이는 수단으로는 맞다고 할 수 없습니다"
  - 다 절 3의 둘째 항목: "1-2에서 본 문제(금리 의존): ..."

같은 날 사용자 요청("우선 문서 안에 중요 내용들을 선정하고, 그것들을 시각화 자료로 설명하는 내용을 추가할 것")에 따라 그림 넷을 더했습니다. 그림 1은 한 줄 답 아래, 그림 2는 가 절 1 끝, 그림 3은 가 절 2 끝, 그림 4는 나 절 1 끝에 있습니다. 본문 문장과 판정은 바꾸지 않았습니다. 고른 내용과 고르지 않은 후보, 그림마다 근거 행을 맞춘 표는 q3-figures/README.md에 있습니다.

2026-10-15에 사용자 요청("q3-answer.md(이하 answer.md) 에 목차를 만들어서 내가 캐치하기 쉽게 만들 것. / 목차들을 보면서 제대로 된 목차인지 보고, 그렇지 않다면 수정할 것.")에 따라 맨 위에 목차를 더하고 제목 13개를 고쳤습니다. 기준은 문서 계약의 "Heading hierarchy as a concept map"입니다: 제목은 "개념: 그 단위가 설명하는 것"의 꼴로 쓰고, 형제 제목은 한 기준으로 나눕니다. 절의 글자와 번호(가 절 1, 나 절 4, 다 절 3 등)는 다른 답이 가리키므로 그대로 두었고, 본문 문장과 판정은 바꾸지 않았습니다. 한 줄 답, 한계, 인용 위치는 1번과 4번부터 7번까지의 답이, 뒤에서 고친 것은 1번, 4번, 5번의 답이 같은 이름을 쓰므로 그대로 두었습니다. 고친 이유와 판단은 q3-report.md의 "뒤에서 달라진 것" 절에 있습니다.

- 원래 제목:
  - 가 절: "가. 고객 쪽: 문제, 장치, 상태"
  - 가 절 1: "1. 고객별 표"
  - 가 절 2: "2. 수요에 대한 회사의 답: 버는 고리"
  - 가 절 3: "3. 고객 쪽 정리"
  - 나 절: "나. 회사 쪽: CEO가 말한 세 갈래와 공시"
  - 나 절 1: "1. 회사가 직접 답한 곳"
  - 나 절 2: "2. 갈래 1, 프로토콜 매출 ("some")"
  - 나 절 3: "3. 갈래 2, USDC 채택 ("fundamentally")"
  - 나 절 4: "4. 갈래 3, Arc 채택"
  - 나 절 5: "5. 회사 문서가 한 문단에 둔 두 목표"
  - 다 절: "다. 그 방향이 맞는가 (3번의 범위)"
  - 다 절 2: "2. 회사 쪽, 제 기준(금리 의존)으로 보면: 금리 의존을 줄이는 수단으로는 맞다고 할 수 없습니다"
  - 다 절 3: "3. 회사 기준으로 보면 일관됩니다"
- 고치기 전의 판은 `git show d22adfc36:cb/derived/arc-hackathon-questions-20261014/q3-answer.md`로 열 수 있습니다.

같은 날 사용자가 "한 줄 답"이 한 줄이 아니라고 지적했습니다("이게 어떻게 한줄이라고 표현하지? 의미적으로 한줄이라는게 뭔지 생각해야 하는 것 아냐?"). 그래서 한 줄 답 절의 첫 문단(여덟 문장)을 한 문장의 답과 그 아래 항목들로 바꿨습니다. 문단의 내용은 모두 항목으로 옮겼고, 다른 곳에서 세 구절을 가져와 더했습니다: 다 절 3의 "규모는 아직 작습니다", 그림 4의 "갈래 2는 준비금 수익에 닿음", 나 절 4의 "Arc 채택이 어떻게 Circle의 매출이 되는지는 4번에서 다룸". 옮기면서 원래 문단의 문제 둘을 함께 고쳤습니다.

- "이 점에 대해 CEO는 ..."은 CEO가 제 해석(금리 의존)에 답한 것처럼 읽혔습니다. CEO는 에이전트 매출의 시점을 묻는 질문에 답했으므로, 회사 쪽 항목에 그 질문을 적고 제 해석은 판정 항목으로 옮겼습니다.
- "CEO는 프로토콜 매출을 "some"으로, USDC와 Arc의 채택을 "fundamentally"로 나눠"는 두 갈래처럼 읽혀, 나 절의 세 갈래와 맞지 않았습니다. 갈래 번호를 붙였습니다.
- 그 아래 "나눈 것은 ..." 문단도 두 항목으로 나눴습니다.
- 고치기 전의 판은 `git show ad5dc22e3:cb/derived/arc-hackathon-questions-20261014/q3-answer.md`로 열 수 있습니다.

2026-10-15에 사용자가 3번 답에 질문 다섯을 보냈습니다. 질문마다 원문과 고친 곳은 다음과 같습니다. 고치기 전의 판은 `git show 7f8a37d7b:cb/derived/arc-hackathon-questions-20261014/q3-answer.md`로 열 수 있고, 경위와 판단은 q3-report.md의 "뒤에서 달라진 것" 5번에 있습니다.

1. "사람이 정한 정책(기간별 지출 한도, 주소 허용 목록과 차단 목록)을 지갑에서 검사"는 자연스럽게 조사하면서 나온 결과인거니 아니면 vault/ 에서 내가 과거에 조사한 것 때문에 영향 받아서 적은거니?"
   - 문구의 낱말은 모두 Agent Stack 블로그 213행에 있습니다. 그러나 이 답을 쓴 세션은 블로그를 열기 전에 사용자의 과거 문서(2026-09-21에 정한 방향 "권한과 정책을 검사"가 적힌 문서)를 읽었으므로, 영향이 없었다고 말할 수는 없습니다.
   - 다시 읽어 보니 장치 칸은 블로그의 장치 가운데 정책 절반만 적고, 전용 지갑 절반("wallets designed for machine-initiated operation")을 빠뜨렸습니다. 가 절 1의 고객 표 5행을 고치고, 표 아래에 문제와 장치의 짝을 적은 문단을 더했습니다.
   - 같은 좁힘은 1번 답 마 절의 고객 표 5행("해법은 사람이 정한 정책 ...")에서 먼저 생겼고, 이 답이 그것을 이어받았습니다. 1번 답은 다른 세션이 맡고 있으므로 고치지 않았습니다.
2. "가/나/다 절마다 각각 작은 질문에 대해 너가 또한 한 줄 대답을 해야지"
   - 가, 나, 다 절과 새 라 절의 머리에 작은 질문과 한 줄 답을 더했습니다.
3. "아래 부분의 단계별 정의는 무엇? 너가 확대 해석한 것은 아니고?" (그림 3의 영어판)
   - 처음 그림은 발표 자료 18쪽의 부제 한 문장(516행)만 보고 그렸고, 쪽에 그려진 그림을 열지 않았습니다. 텍스트 추출본에서는 그림의 배치가 사라졌기 때문입니다.
   - 그 결과 고리의 입구인 Publish를 빠뜨렸고, Pay와 Settle을 "다음 결제" 하나로 합쳤으며, 쪽이 글로 적은 단계 정의(Publish, Reputation, Discovery)를 옮기지 않았습니다. 순환의 순서(정산, 평판, 발견, 결제)는 쪽의 그림과 같았습니다.
   - 원본 PDF 18쪽을 그림으로 열어 가 절 2와 그림 3을 다시 썼습니다. 가 절 2의 판단 "고리의 세 단계(정산, 평판, 발견)는 이 가운데 어느 것도 직접 채우지 않습니다"는 지출 정책과 평판이 일부에 대응하는 것으로 고쳤습니다. 결론(고리가 돌아도 1-3행 고객은 따로 봐야 함)은 그대로입니다.
4. "그런데 에이전트를 고객이 에이전트를 이용할 수도 있지만, 회사에서도 에이전트를 이용할 수 있음. 회사 쪽에서 기존의 서비스에 에이전트를 붙이는 방식이 있고, 지금처럼 에이전트를 개발할 수 있는 툴을 제공할 수도 있으며, 에이전트와 함께 지금 개발하는 것들의 생산성을 높일 수 있음. / 너는 이런 구분이 전혀 없고 빠뜨림."
   - 한 줄 답 아래 "나눈 기준"에 세 방식의 표를 더하고, 빠져 있던 방식 3을 나 절 6(근거)과 다 절 4(판정)로 더했습니다. 그림 1과 한 줄 답에도 반영했습니다.
   - 나 절의 제목을 "나. 회사 쪽 경로: 회사가 말하는 에이전트 매출의 길과 공시에 보이는 크기"에서 지금 제목으로 넓혔습니다.
5. "추가적으로 마지막 절에는 무언가 비어있는 부분은 무엇이며, 그걸 어떻게 하면 커버할 수 있는지 혹은 미래에 어떤 모습으로 이게 채워질 것 같은지에 대한 의견 제시 또한 필요함"
   - 판정 뒤에 라 절(빈칸)을 새로 두었습니다. 전에 라 절이던 "다음 질문으로 넘기는 것"은 마 절이 되었습니다.

함께 고친 것: 다 절 3의 "정책 지갑"은 1번 질문과 같은 좁힘이어서 "USDC 잔액과 지출 정책을 갖는 에이전트 지갑"으로 바꿨습니다.

2026-10-15에 사용자가 "이후 새 시각화 스킬 이용해서 q*-answer.md 들의 시각화 자료들 리뷰."를 요청했고, 리뷰 보고를 받은 뒤 "모두 진행"이라고 했습니다. 리뷰 전체와 고친 내용은 figures/review-20261015.md에 있습니다.

- 그림 4(CEO 답의 세 갈래): 실선 화살표 하나가 공시의 줄, 결과, 돈이 가는 곳의 세 뜻을 지녀서, 돈이 가는 곳은 `==>`로, 결과는 "결과:"로 바꾸고 기호의 뜻을 그림 아래에 적었습니다. "지금 들어오는 돈 -> ARC 토큰 사전판매"는 화살표 없이 "지금 들어오는 돈: ARC 토큰 사전판매"로 적었습니다. 원래 설명은 "실선 화살표는 자리에 따라 뜻이 다릅니다."로 시작했습니다. 그림 파일 `q3-figures/fig-4-branches.md`를 먼저 고치고 같은 부분을 옮겼습니다.

## 인용 위치

행 번호는 1부터 셉니다(`sed -n` 기준). 인용 안의 " / "는 원문의 줄바꿈입니다.

| 인용한 곳 | 경로와 행 |
|---|---|
| 2분기 실적 콜 (Owen의 질문, Allaire의 답, CFO, 로드맵 예고) | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-earnings-call-transcript.md:357-358, 377-378, 380-383, 385-393, 675-680, 901-903, 941, 942, 945-993, 953, 962, 966-976, 984-985, 991-993` |
| 2025년 4분기 실적 콜 (Gateway 잔액, skills와 MCP 서버, 회사 안의 AI) | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q4-2025-earnings-call-transcript.md:326-336, 520-521, 1057-1059` |
| 2분기 10-Q (용어 정의, 다른 제품 문단, 매출 표, 매출 정의, 증가 이유, 사전판매, AI 도구 비용, 회사의 AI 쓰임) | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-10q.md:107-114, 784-785, 1326, 1349-1351, 1892, 1895-1897, 1899-1900, 2223-2224, 2300-2302, 2303-2305, 2337, 2426, 2922-2924` |
| 2분기 분석가 콜 (Arc 수수료가 가는 곳) | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-analyst-call-transcript.md:308-310` |
| 2분기 실적 보도자료 (가이던스와 각주) | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-earnings-release.md:209, 219` |
| 2분기 발표 자료 (Agent Stack 쪽, 18쪽) | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-earnings-presentation.md:515, 516, 521-523, 528, 531-545, 551`; 그림의 배치는 `cb/works/web/2026-09-26-circle-quarterly-reports-sources/raw/circle-q2-2026-earnings-presentation.pdf` 18쪽 |
| CPN 백서 | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-cpn-whitepaper.md:442-447` |
| 10-K (CPN 용도) | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-fy2025-10k.md:500-501` |
| Agent Stack 블로그 | `cb/works/web/2026-10-13-circle-agent-stack-sources/pages/circle-blog-introducing-agent-stack.txt:207, 209, 211, 213, 214, 215, 222` |
| Agent Stack 릴리스 노트 | `cb/works/web/2026-10-13-circle-agent-stack-sources/pages/agent-stack-release-notes.txt:146, 161` |
| Agent Wallets 지원 체인 문서 (목차) | `cb/works/web/2026-10-13-circle-agent-stack-sources/pages/agent-wallets-supported-blockchains.txt:33` |
| Keyrock 글 | `cb/works/web/2026-10-13-circle-agent-stack-sources/pages/keyrock-who-pays-the-agent.txt:74` |
| Circle 메인넷 보도자료 | `cb/works/web/2026-09-20-circle-arc-primary-sources/raw/circle-mainnet-launch.md:45, 77, 82, 86` |
| Arc 개발 문서 agentic-economy | `cb/works/web/2026-10-07-arc-official-library/pages/en/docs/build/agentic-economy.md:15-18` |
| Arc 개발 문서 arc-studio-cli | `cb/works/web/2026-10-07-arc-official-library/pages/en/docs/ai/arc-studio-cli.md:24` |
| Beyond 글 | `cb/works/circle-blog/undated-current-beyond-agentic-payments-the-operating-layer-for-the-agentic-economy/pages/beyond-agentic-payments-the-operating-layer-for-the-agentic-economy.en.md:39, 41, 45, 49-55, 66` |
