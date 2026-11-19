# 7. 나는 Arc AI agent 해커톤에 지원해도 되는가?

Arc 해커톤 지원 판단을 위한 질문 일곱 가운데 마지막 질문의 답입니다. 1번부터 6번까지의 답을 재료로 썼습니다. 답을 쓰기 전에 적은 소질문과 예상 답은 q7-plan.md에 있고, 예상과 달라진 점, 답을 쓴 뒤 고친 것, 검증은 q7-report.md에 있습니다.

**목차**

가부터 바까지 각 절의 역할은 다음과 같습니다. 이 구분은 제 것이며, 그림 1이 같은 구조를 보여 줍니다.

- 가와 나: 판정의 재료
- 다와 라: 판정의 두 층
- 마: 결과물을 Arc 밖으로 옮길 수 있는지에 대한 보충 판단
- 바: 앞의 판정을 모은 결론

그림은 그것이 들어 있는 절 아래에 적었습니다.

- [한 줄 답](#한-줄-답)
- [요약: 두 층의 판정과 판단의 전제](#요약-두-층의-판정과-판단의-전제)
  - 그림 1. 7번 답의 구조
- [가. Circle/Arc와 각 행사: 참가자에게 바라는 것](#가-circlearc와-각-행사-참가자에게-바라는-것)
  - [1. 회사 쪽: 바라는 것과 스스로 비었다고 적은 칸](#1-회사-쪽-바라는-것과-스스로-비었다고-적은-칸)
  - [2. Tameion: 주최자 페이지가 적은 주제, 심사, 제출 조건](#2-tameion-주최자-페이지가-적은-주제-심사-제출-조건)
  - [3. 그 밖의 행사: Microgrants, Encode London, ETHGlobal Mumbai](#3-그-밖의-행사-microgrants-encode-london-ethglobal-mumbai)
- [나. 행사가 주는 것과 요구하는 것: 주최자 페이지의 항목별 정리](#나-행사가-주는-것과-요구하는-것-주최자-페이지의-항목별-정리)
  - 그림 2. Tameion에 들어가지 않아도 얻는 것과 실제 사업체를 가지고 들어가야 얻는 것
- [다. Tameion 지원 여부: 조건 넷과 사업체라는 갈림길](#다-tameion-지원-여부-조건-넷과-사업체라는-갈림길)
  - 그림 3. Tameion 기간과 점수가 되는 구간
- [라. 그 밖의 Arc 에이전트 행사: 지금 보이는 행사의 판정과 앞으로의 기준](#라-그-밖의-arc-에이전트-행사-지금-보이는-행사의-판정과-앞으로의-기준)
  - [1. 지금 보이는 행사: 행사별 판정과 일정 순서](#1-지금-보이는-행사-행사별-판정과-일정-순서)
    - 그림 4. 지금 보이는 행사의 순서
  - [2. 앞으로 나올 행사: 고르는 기준 여섯 가지](#2-앞으로-나올-행사-고르는-기준-여섯-가지)
- [마. 이식성: 결과물을 Arc 밖으로 옮길 때 잃는 것](#마-이식성-결과물을-arc-밖으로-옮길-때-잃는-것)
- [바. 종합 판정: 행사별 결론과 사용자가 정할 것](#바-종합-판정-행사별-결론과-사용자가-정할-것)
- [한계](#한계)
- [인용 위치](#인용-위치)

## 한 줄 답

**남은 나흘 안에 실제 돈 문제를 가진 사업체를 붙일 수 있으면 Tameion에 지원하고, 그 밖의 Arc 에이전트 행사는 행사마다 기준 여섯 가지로 따져서 고릅니다.**

## 요약: 두 층의 판정과 판단의 전제

- **층 1, Tameion** (다 절)
  - 마감은 2026-10-18 12:59 KST이고, 이 답을 쓴 10-14 06:11 KST 기준으로 102.8시간이 남았습니다(`python3 cb/derived/arc-hackathon-questions-20261014/tools/deadlines.py`).
  - 남은 나흘 안에 실제 돈 문제를 가진 사업체를 붙일 수 있으면 "예"입니다.
    - 사업체는 본인 회사여도 되고, 아는 프리랜서나 본인이 관리하는 오픈소스 프로젝트여도 됩니다.
  - 붙일 수 없으면 제출은 "아니오"입니다.
    - 주최자가 합성 데이터는 인정하지 않는다고 적었기 때문입니다(409행).
- **층 2, 그 밖의 Arc 에이전트 행사** (라 절)
  - 지금 보이는 행사는 행사마다 형식과 조건이 다르고, 앞으로 나올 행사는 미리 정하지 않습니다. 행사가 나오면 라 절의 기준 여섯 가지로 고릅니다.
  - 행사가 주는 것과 요구하는 것은 나 절에 주최자 페이지의 항목으로 정리했습니다.
    - 확실히 주는 것: 주최자가 공개한 학습 자료와 외부 마감
    - 행사가 끝나도 남는 것: 공개 저장소와 영상. Tameion은 둘 다 제출 조건으로 요구합니다.
    - 일부만 주는 것: Circle/Arc 쪽 사람과의 연결. 온라인 행사에서는 Discord와, 행사 뒤에도 계속 만드는 팀의 후속 지원을 거칩니다.
    - 주는 것이 아니라 요구하는 것: 실제 사업체와, 그 사업체가 행사 기간에 실제로 쓴 기록(Tameion의 견인)
- **판단의 전제**
  - 사용자가 행사에서 무엇을 얻고 싶은지는 이 답에서 정하지 않았습니다. 그래서 나 절은 행사가 주는 것과 요구하는 것을 주최자 페이지의 항목으로만 적고, 그 가운데 무엇이 중요한지는 사용자의 목적에 맡깁니다.
  - 두 층의 구분, 각 판정, 라 절의 기준 여섯 가지는 제 것입니다.
  - 두 층으로 나눈 이유: Tameion은 마감이 나흘 뒤여서 지금 예나 아니오로 정할 수 있습니다. 반면 앞으로 어떤 행사가 나올지는 제가 알 수 없으므로, 그 행사들에는 판정 대신 기준만 적습니다.
  - 원문은 모두 2026-10-08에 보관한 주최자 페이지와 공고입니다. 그 뒤에 페이지가 바뀌었는지는 확인하지 않았습니다.
  - 사용자의 현재 상태(Tameion 등록 여부, 붙일 수 있는 사업체, 이미 배포한 결과물)도 이 세션에서 확인하지 않았으므로, 있다고도 없다고도 쓰지 않고 조건으로만 적습니다.

그림 1. 7번 답의 구조 (한국어)

```text
가 절  회사와 행사가 바라는 것: Arc 위에서 실제로 흐르는 USDC
나 절  행사가 주는 것과 요구하는 것
   |
   v
질문: 나는 Arc AI 에이전트 해커톤에 지원해도 되는가?
   |
   +-- 층 1: Tameion (다 절)
   |     마감 10-18 12:59 KST, 102.8시간 남음 -> 지금 정할 수 있음
   |     |
   |     +-- 실제 돈 문제를 가진 사업체를 붙일 수 있는가?
   |           |
   |           +-- 예 -----> 지원. 목표는 상금보다 학습과 공개 저장소
   |           +-- 아니오 -> 제출하지 않음. 공개 자료로 학습만
   |
   +-- 층 2: 그 밖의 Arc 에이전트 행사 (라 절)
         앞으로 나올 행사는 알 수 없음 -> 판정 대신 기준 여섯 가지
```

Figure 1. Structure of answer 7 (English)

```text
Sec. ga  What Circle/Arc and the events want: USDC actually flowing on Arc
Sec. na  What the events give and what they require
   |
   v
Question: Should I apply to an Arc AI agent hackathon?
   |
   +-- Layer 1: Tameion (Sec. da)
   |     Deadline 10-18 12:59 KST, 102.8 hours left -> decidable now
   |     |
   |     +-- Can I attach a business with a real money problem?
   |           |
   |           +-- Yes -> Apply. Aim at learning and a public repo, not prizes
   |           +-- No --> Do not submit. Learn from the public materials only
   |
   +-- Layer 2: Other Arc agent events (Sec. ra)
         Future events are unknown -> six criteria instead of a verdict
```

이 그림은 7번 답 전체의 구조를 보여 줍니다. 위에서 아래로 읽습니다.

- 위의 두 줄: 판정의 재료인 가 절과 나 절입니다.
- 층 1: Tameion은 마감이 정해져 있어서, 실제 돈 문제를 가진 사업체를 붙일 수 있는지 하나로 예와 아니오가 갈립니다.
- 층 2: 앞으로 나올 행사를 알 수 없으므로 판정 대신 기준을 둡니다.
- 선과 화살표: 판단이 이어지는 순서이고 돈의 이동이 아닙니다.
- 판단 표시: 두 층으로 나눈 것과 각 판정은 제 판단입니다(확신도 중간).
- 세부 그림: 나 절의 그림은 재료 가운데 나 절 줄을 자세히 보여 주고, 다 절의 그림은 층 1을, 라 절의 그림은 층 2 가운데 지금 보이는 행사를 자세히 보여 줍니다.
- 영문판의 ga, na, da, ra는 절 기호 가, 나, 다, 라를 로마자로 적은 것입니다.

## 가. Circle/Arc와 각 행사: 참가자에게 바라는 것

### 1. 회사 쪽: 바라는 것과 스스로 비었다고 적은 칸

- 6번 라 절의 판단: 에이전트 갈래에서 회사가 바라는 것은 매출이 아니라 USDC와 Arc의 채택입니다. 4번 라 절의 말로 하면, Arc 쪽에서 보면 에이전트는 "Arc를 쓸 이유를 만들어야 하는 영역이고, 이미 쓸 이유가 있는 영역이 아닙니다"(q4-answer.md 527행).
- 회사 스스로 비었다고 적은 칸은 운영 층입니다. Beyond 글은 기관 규모의 에이전트 결제를 "authorize, govern, audit, and underwrite"할 인프라가 "still being created"라고 씁니다(45행) [Circle 글]. Arc의 Agent Sector("verifiable agent identity and auditable records")는 아직 로드맵 항목입니다(메인넷 보도자료 84, 86행) [Circle 글].

### 2. Tameion: 주최자 페이지가 적은 주제, 심사, 제출 조건

- 주최와 기간: Canteen이 주최하는 온라인 행사이고(34, 47행), 기간은 9월 27일부터 10월 17일까지입니다(36행). 끝나는 날은 자료끼리 어긋나며, 그 내용은 한계 절에 적었습니다.
- 주제: "AI agents that manage a business's money."(28행). 행사 설명은 "Settled on Arc in USDC."로 끝납니다(29행). Canteen 시리즈의 세 번째 행사이고, 앞의 둘은 Agora와 Lepton입니다(47행).
- 우선순위 셋(394-397행), 원문이 정한 순서 그대로입니다.
  1. "It runs on Arc, with payments actually flowing in USDC, testnet or mainnet, on the Circle Agent Stack."(395행)
  2. 행사가 끝난 뒤에도 계속 만들 것(396행)
  3. "It's already in front of a business that uses it, solving a problem they actually have."(397행)
- 심사 비율: 에이전트 판단력 30%, 견인 30%, Circle 도구 20%, 혁신 20%입니다(356-367행). 판단력 항목은 "An agent that chooses when to pay, and can explain why, beats a cron job with a language model bolted on."이라고 적습니다(358행). 견인 항목은 "Test USDC counts. Real customers transacting in real USDC on mainnet count more."라고 적습니다(361행).
- 실제 사업체: FAQ의 Q3은 "Do I need a real business to build for?"이고(405행) 답은 "Yes, and it can be a small one. Yours counts."입니다(406행). 원문은 "Your own company counts, and so does the open-source project you maintain"이라고 이어 가고(408행), "What doesn't count is a synthetic dataset."이라고 적습니다(409행).
- 변화분 심사: "we judge the delta, not the whole project: what you shipped and who you reached during Tameion"(429행), 그리고 "work that already existed when you started doesn't"(430행).
- 에이전트의 자율성: FAQ의 Q4는 "How much autonomy should the agent actually have?"이고(411행), 주최자는 이것을 "the interesting design question of the whole event"라고 부르며 정해진 답이 없다고 적습니다(414행). 지금까지 나온 좋은 답의 예로는 "a contract that enforces the budget rather than a prompt that requests it, a threshold above which a human signs, a complete record it must produce afterwards"를 듭니다(415행).
- 제출물: 공개 GitHub 저장소(필수), 3분 미만 영상(필수), 배포 링크(권장)입니다. 견인 질문에도 답해야 합니다(95, 370-374행). "There is no live demo day."이고 심사는 비동기입니다(369행).
- 상금: 총 4만 달러입니다. 1등 1만 달러, 2등 7,500달러, 3등 5,000달러씩 세 팀이고, Standout 10팀에서 12팀은 팀당 약 650달러에서 750달러를 받습니다(107-116행).
- 등록: 페이지 상단에 "Invite-only"라고 적혀 있고(40행), 같은 페이지에 Luma 등록 링크와 우선 접근용 passphrase가 공개되어 있습니다(64-66행). 등록할 때 GitHub와 Discord 핸들을 정확히 적으라고 합니다(67행).

[제 판단, 확신도 중간] Tameion이 겨누는 고객은 작은 사업체의 재무 업무입니다(408행의 예: 청구서 세 장을 쫓는 프리랜서, 해외 계약자에게 돈을 보내는 2인 회사). 3번 답의 고객 표(q3-answer.md 가 절 1, 171-179행)로 보면 매출과 가까운 고객(1행부터 3행까지: 은행과 PSP와 기업, 블록체인을 직접 다루기 어려운 기업, 기관 환전)은 아니고, 5행(에이전트를 만드는 개발자)과 7행(에이전트에게 일을 맡기는 사람)이 만나는 칸입니다. 회사 쪽에서 보면 이 행사는 매출을 만드는 자리가 아니라, Arc 위에서 USDC를 실제로 움직이는 사례를 만드는 자리입니다. 6번의 "채택 논리"와 같은 방향입니다.

### 3. 그 밖의 행사: Microgrants, Encode London, ETHGlobal Mumbai

- **Arc Microgrants**: 해커톤이 아니라 보조금입니다.
  - 요구: "Submit a project that is already deployed and working on Arc mainnet."(64행)
  - 요구하지 않는 것: "You do not need traction, a company, a deck, or a roadmap. You need something real that runs."라고 적습니다(68행).
  - 대상에 "hackathon continuations"가 들어 있지만(67행), AI 에이전트 전용은 아닙니다.
  - testnet에서만 돌아가는 결과물은 제외됩니다(92행).
- **Encode London**: 공개된 과제 둘 가운데 하나가 "Agents That Ship"입니다(Encode 페이지 53행).
  - 원문은 "Build an AI agent that does a real job end to end"라고 적고, 사람에게 확인하는 단계를 요구합니다: "checking with a human before the risky steps"(54행).
  - 예시에 작은 사업체 업무(청구서 독촉, 결제 대사)와 "Agents that hand work to each other, or pay and get paid for it"이 있습니다(55, 58행).
  - 7번 계획에서는 Arc를 "상금을 거는 후원사 가운데 하나"라고 적었는데(q7-plan.md 23행), 원문을 다시 열어 보니 Arc는 "supported by" 명단에 Google DeepMind, MongoDB, Saint와 함께 있을 뿐입니다(63-67행). 상금과 심사위원은 "will be announced soon"입니다(43, 68행).
- **ETHGlobal Mumbai**: Arc는 1만 5,000달러의 상금을 겁니다(Mumbai 공고 114-115행).
  - 세부는 "Prize details coming soon"입니다(Arc 상금 페이지 31행).
  - 공고의 주제 목록 열두 개 가운데 하나가 "AI x Crypto"입니다(61-73행). 그러나 "agent"라는 낱말은 공고 전체에서 멘토 소개 한 곳(2411행)에만 나옵니다(검색: `rg -n -i '\bagent' cb/works/web/2026-10-08-arc-events-complete/pages/user-archives/mumbai.md`, 일치 1건).
  - 올해는 시작점이 셋으로 늘어서, 빈 저장소 말고도 본인이 관리하는 오픈소스나 기존 제품 위에 기능 하나를 더하는 갈래("Extend Open Source", "Ship a Feature")가 생겼습니다(90-104행).

## 나. 행사가 주는 것과 요구하는 것: 주최자 페이지의 항목별 정리

주는 것과 요구하는 것으로 나눈 것은 원문에 없는 제 구분입니다. Tameion 페이지가 제출 조건과 심사 기준(요구하는 것)을 상금과 후속 지원(주는 것)과 따로 적기 때문에 이렇게 나눴습니다.

| 항목 | 원문 | 주는 것인가, 요구하는 것인가 (제 판단) |
|---|---|---|
| 학습 자료와 외부 마감 | Tameion: "Agents and Ledgers" 글(89-90행), RFB(주최자가 제안한 과제) 다섯(재무(treasury), 매입과 매출 채권(AP/AR), 거래처 지급, 사업 운영 대행, 컴플라이언스, 172-292행), prior art(옛 재정 관리 제도에서 빌린 아이디어 모음, 306-316행), Circle CLI와 ARC CLI(80, 86행), 마감 10월 17일 23:59 ET(94행). 모든 행사에 마감이 있습니다. | 확실히 줍니다. 사업체가 없어도 얻을 수 있는 것은 이것 하나입니다. |
| 공개 결과물 | Tameion은 공개 저장소와 영상을 필수로 남기고, 심사위원이 "read the repo directly"합니다(374행). | 둘 다입니다. 제출 조건으로 요구하고, 행사가 끝나도 남습니다. |
| 상금과 Arc House 점수 | Tameion 상금은 총 4만 달러입니다(107-116행). Arc House는 해커톤 참가에 500점, 수상에 1,000점을 줍니다(기여 항목 47-58행). | 줍니다. 다만 상금은 순위에 달렸고, 늦게 들어가는 참가자에게는 기대가 낮습니다(다 절). |
| Circle/Arc 쪽 사람과의 연결 | Tameion: Canteen Discord와 Arc builder Discord(69-75행), 데모 데이는 열리지 않음(369행), 계속하는 팀에게 "introductions"(423행). Microgrants: "Introductions where they help"(77행), office hours(75행). Arc House: 1등급(500점과 opt-in, 등급 문서 41행)의 혜택은 토픽 그룹, 배지, Architect 행사, 해커톤 부스 팀입니다(46-58행). Circle 팀과의 분기 브리핑은 2등급(3,500점)부터입니다(67, 81행). | 일부만 줍니다. 온라인 행사에서 연결은 Discord를 거치고, Circle 팀과 직접 만나는 자리는 원문상 Arc House 2등급 이상이거나 행사 뒤에도 계속 만드는 팀의 후속 지원입니다. 현장 행사(Encode, Mumbai)는 사람을 직접 만나지만 Arc 쪽 역할이 아직 정해지지 않았습니다. |
| 실제 사업체와 견인 | Tameion은 실제 사업체를 요구하고(397, 406-409행) 견인에 30%를 줍니다(359-361행). 후속 지원에 "a path to real users"가 있지만, 계속 만드는 팀에게 주는 것입니다(420, 423행). Microgrants는 견인을 요구하지 않습니다(68행). | 요구합니다. Tameion에서 실제 사업체는 행사가 붙여 주는 것이 아니라 참가자가 가지고 들어가는 조건입니다. |

[제 판단, 확신도 중간] 갈리는 자리는 표의 마지막 줄입니다. Circle/Arc는 Arc 위에서 실제로 흐르는 USDC를 원하고, 그것을 견인으로 채점합니다. 행사는 그것을 참가자에게 주지 않고, 참가자가 가지고 들어오기를 요구합니다.

그림 2. Tameion에 들어가지 않아도 얻는 것과 실제 사업체를 가지고 들어가야 얻는 것 (한국어)

```text
Tameion 기준. 화살표는 순서와 방향이며 돈의 이동이 아닙니다.

[들어가지 않아도 얻는 것]

  공개 주최자 페이지 -----------------------> 학습 자료와 외부 마감: 확실히 얻음
  (등록하지 않아도 읽음)                      RFB, prior art, "Agents and Ledgers" 글

[실제 사업체를 가지고 들어가야 얻는 것]

  가지고 들어가는 것             행사          얻어 나오는 것

  실제 사업체와 견인 ------->  Tameion --+--> 공개 저장소와 영상: 남음
    실제 사업체(397, 406-409행)          |      제출 조건이기도 함(374행)
    견인 30%(359-361행)                  |
                                         +--> Circle/Arc 쪽 사람과의 연결: 일부만
                                         |      Discord, 계속하는 팀의 후속 지원
                                         |
                                         +--> 상금과 Arc House 점수: 순위와 참가에 따름
                                                상금 총 4만 달러(107-116행)
```

Figure 2. What Tameion gives without entering, and what needs a real business brought in (English)

```text
Tameion only. Arrows show order and direction, not money movement.

[Gained without entering]

  Public organizer page --------------------> Learning materials and an external
  (readable without registering)              deadline: gained for certain
                                              RFB, prior art, "Agents and Ledgers"

[Gained only by bringing a real business in]

  Brought in                     Event         Taken out

  A real business and ------>  Tameion --+--> Public repo and video: they remain
  traction                               |      also a submission requirement (374)
    a real business (397, 406-409)       |
    traction 30% (359-361)               |
                                         +--> Connections with Circle/Arc people: partly
                                         |      Discord, follow-up for teams that continue
                                         |
                                         +--> Prizes and Arc House points: by rank
                                                and participation; prizes USD 40,000
                                                in total (107-116)
```

이 그림은 나 절 표의 다섯 항목을, Tameion에 들어가지 않아도 얻는 것과 실제 사업체를 가지고 들어가야 얻는 것으로 나눠 다시 놓은 것입니다. 표는 항목마다 주는 것인지 요구하는 것인지를 적지만, 실제 사업체만 방향이 반대라는 점과 학습 자료만 사업체 없이 얻는다는 점은 표의 칸 안에 들어 있어서 잘 보이지 않습니다.

- 위 칸: 학습 자료와 외부 마감은 주최자 페이지가 공개되어 있어서, 등록하지 않아도 얻습니다. 나 절 표는 이 항목을 "사업체가 없어도 얻을 수 있는 것은 이것 하나"라고 적고, 다 절의 "아니오" 항목도 RFB, prior art, "Agents and Ledgers" 글을 등록 없이 읽을 수 있다고 적습니다.
- 아래 칸 왼쪽: 실제 사업체와 견인은 Tameion이 입장 조건으로 요구하므로 왼쪽에 있습니다.
- 아래 칸 오른쪽: 세 항목은 얻는 정도가 다릅니다.
  - 공개 저장소와 영상은 제출 조건이면서, 행사가 끝나도 남습니다.
  - 사람과의 연결은 Discord와 계속하는 팀의 후속 지원을 거쳐 일부만 얻습니다.
  - 상금과 점수는 순위와 참가 여부에 따라 달라집니다.
- 판단 표시: 두 칸으로 나눈 것과 얻는 정도의 표시는 제 판단입니다(확신도 중간).
- 범위: 그림의 범위는 Tameion입니다. Microgrants는 견인을 요구하지 않고 Encode와 Mumbai의 공개 문장에도 그런 요구가 없으므로(라 절 표), 다른 행사에서는 아래 칸의 왼쪽이 비어 있을 수 있습니다.
- 위치: 이 그림은 그림 1의 재료 가운데 나 절 줄을 자세히 보여 줍니다.

## 다. Tameion 지원 여부: 조건 넷과 사업체라는 갈림길

**[제 판단, 확신도 중간] 조건 (1)이 갈림길입니다.**

| 조건 | 원문 | 지금 알 수 있는 것 |
|---|---|---|
| (1) 실제 돈 문제를 가진 사업체를 붙일 수 있는가 | 406-409행 | 사용자 상태를 확인하지 않았습니다. 본인 사업, 아는 프리랜서나 작은 가게, 본인이 관리하는 오픈소스 모두 인정됩니다. |
| (2) 남은 시간 | 마감 "October 17, 11:59 PM ET"(94행) | 2026-10-18 12:59 KST, 102.8시간 남음(`python3 cb/derived/arc-hackathon-questions-20261014/tools/deadlines.py`, 10-14 06:11 KST 기준) |
| (3) 등록이 통과되는가 | "Invite-only"(40행), passphrase(66행), 거절되면 Discord에서 연락하라는 안내(75행) | 불확실합니다. 초대제라고 적으면서 passphrase를 같은 페이지에 공개했으므로 사실상 열려 있을 가능성이 있지만, 승인 여부는 등록해 봐야 압니다. |
| (4) 행사 기간의 변화분만 심사 | 429-430행 | 마지막 나흘에 들어가면 변화분도 나흘 치입니다. 이미 만든 것이 있어도 그것은 점수가 되지 않습니다. |

그림 3. Tameion 기간과 점수가 되는 구간 (한국어)

```text
다 절의 조건 (2) 남은 시간과 (4) 변화분 심사

9-27 행사 시작       10-14 06:11 KST 지금       10-18 12:59 KST 제출 마감
(36행)                                          (94행: 10-17 23:59 ET)
  |                    |                          |
  +====================+==========================+
  |<------ 처음부터 참가한 팀: 3주 (34행) ------->|
                       |<----- 102.8시간 -------->|
                       | 지금 들어가면 점수가     |
                       | 되는 변화분은 이 구간뿐  |
                       | (429-430행)              |
                       ^
                       지금 정할 것
                       (1) 붙일 사업체가 있는가: 갈림길
                       (3) 등록이 승인되는가: 등록해 봐야 앎
```

Figure 3. Tameion period and the window that counts (English)

```text
Conditions (2) time left and (4) delta judging, Sec. da

9-27 event start     10-14 06:11 KST now        10-18 12:59 KST deadline
(line 36)                                       (line 94: 10-17 23:59 ET)
  |                    |                          |
  +====================+==========================+
  |<-- teams there from the start: 3 weeks (34) ->|
                       |<----- 102.8 hours ------>|
                       | if I join now, the only  |
                       | delta that can score     |
                       | lies here (429-430)      |
                       ^
                       To decide now
                       (1) Is there a business to attach? The fork
                       (3) Is registration approved? Known only by registering
```

이 그림은 다 절의 조건 표 가운데 시간에 관한 두 조건, (2) 남은 시간과 (4) 변화분 심사를 한 축 위에 놓은 것입니다.

- 기간: 행사는 9월 27일에 시작했고, 마감은 10월 17일 23:59 ET, 한국 시각으로 10월 18일 12:59입니다(36, 94행).
- 남은 시간: 처음부터 참가한 팀에게는 3주가 있었지만(34행), 지금 들어가면 102.8시간이 남습니다.
- 변화분 심사: 심사는 행사 기간에 만든 변화분만 보고, 참가를 시작할 때 이미 있던 작업은 점수가 되지 않습니다(429-430행).
- 그래서 지금 들어가는 사람이 점수로 만들 수 있는 것은 이 102.8시간의 결과뿐이고, 상금 기대를 낮게 잡은 이유가 이것입니다.
- 아래의 (1)과 (3): 지금 정해야 하는 조건이며, 둘 다 이 답에서 확인하지 않은 사용자 상태입니다.
- 위치: 이 그림은 그림 1의 층 1을 시간 축으로 자세히 보여 줍니다. (1)이 예와 아니오를 가르는 갈림길이라는 점은 그림 1과 같습니다.

**사업체를 붙일 수 있으면 "예"입니다.** 이때 할 일은 이렇습니다(제 판단).

- 범위를 돈 문제 하나로 좁힙니다. 예를 들어 청구서 하나를 받아 지급하는 흐름 하나입니다.
- 견인 질문(95행: 몇 개의 사업체, 얼마의 금액, 어떤 문제)에 답할 숫자를 처음부터 기록합니다.
- 상금 기대는 낮게 잡습니다. 처음부터 참가한 팀에게는 3주가 있었고(34행), 견인은 행사 기간의 실제 사용으로 잽니다(361행). 이 행사에서 얻을 것은 상금보다 학습 자료와 마감, 그리고 남는 공개 저장소입니다.

**붙일 수 없으면 제출은 "아니오"입니다.**

- 이유: 합성 데이터는 인정되지 않으므로(409행), 사업체 없이 만든 결과물은 견인 30%를 얻을 수 없고 우선순위 3(397행)도 채우지 못합니다.
- 이때도 학습 자료는 얻을 수 있습니다. 주최자 페이지의 RFB, prior art, "Agents and Ledgers" 글은 등록하지 않아도 읽을 수 있습니다. 이 보관본이 그 공개 페이지의 텍스트입니다(보관 단위 README 31행: "pages/linked/는 공개 연결자료의 전체 가시 텍스트").
- Arc House의 참가 점수(500점)가 제출 없이 등록만으로 인정되는지는 원문이 정하지 않습니다. 원문은 "Participated in a hackathon after March 31, 2026"이라고만 적습니다(기여 항목 49행).

## 라. 그 밖의 Arc 에이전트 행사: 지금 보이는 행사의 판정과 앞으로의 기준

### 1. 지금 보이는 행사: 행사별 판정과 일정 순서

| 행사 | 형식과 시각 | 에이전트 관련 | 실제 사업체 요구 | Arc 쪽 역할 | 지금 판정 (제 것) |
|---|---|---|---|---|---|
| Arc Microgrants | 보조금. 마감 2026-10-15 12:59 KST(30.8시간 남음, 같은 `tools/deadlines.py`), 결정은 10월 21일까지(86행. 시각은 적혀 있지 않음) | 전용 아님(67행) | 아니오(68행) | 주최 | 이미 Arc 메인넷에 배포해 돌아가는 것이 있을 때만 맞습니다(64, 88, 92행). 해커톤 질문의 범위 밖이지만 마감이 가장 가까워 적었습니다. |
| Encode London | 런던 Shoreditch 현장(Encode 일정 37, 48-49행), 2026-10-23, 티켓은 추첨과 승인(Encode 페이지 31-36행) | 공개 과제 "Agents That Ship"(53-58행) | 공개된 문장에는 요구가 없습니다(검색: `rg -n -i 'real business\|customer\|traction\|users?\b' cb/works/web/2026-10-08-arc-events-complete/pages/linked/31013bc2e5a9535c.md`, 일치 1건은 이미지 주소) | "supported by" 명단(63-67행), 상금 미정 | 런던에 갈 수 있으면 외부 마감과, Circle/Arc 쪽을 포함한 사람을 직접 만나는 자리를 얻습니다. 상금과 심사위원은 아직 발표되지 않았습니다(43, 68행). |
| ETHGlobal Mumbai | 11월 5일부터 7일까지 현장(37, 342행), 신청 마감 2026-11-04 03:29 KST(723행), 개인별 신청과 stake(318, 358행), 여행비 지원 없음(459행) | 주제 목록에 "AI x Crypto"(63행). 에이전트 과제는 공고에 나오지 않음([가 절 3](#3-그-밖의-행사-microgrants-encode-london-ethglobal-mumbai)의 검색) | 아니오. 다만 기존 제품이나 오픈소스 위에서 시작하는 갈래가 있습니다(95-104행). | 상금 1만 5,000달러, 세부 미정(Arc 상금 페이지 26, 31행) | Arc 상금의 주제가 나온 뒤에 정합니다. 신청 마감까지 501시간이 남았습니다. |
| Arc Acceleration Season | 6주 온라인 프로그램, 중남미 핀테크와 AI 스타트업 대상 | 대상에 AI 포함 | 스타트업 대상 | 주최 | 지원 마감(9월 22일, 9행)이 지났습니다. |

그림 4. 지금 보이는 행사의 순서 (한국어)

```text
시각이 적힌 날짜만 KST로 옮겼고, 나머지는 원문의 날짜입니다.
남은 시간은 10-14 06:11 KST 기준입니다(tools/deadlines.py).
세로 간격은 순서만 뜻하고, 날짜 사이의 길이에 비례하지 않습니다.

 9-22          Arc Acceleration Season 지원 마감: 지남
   :
10-14 06:11    지금
   |
10-15 12:59    Arc Microgrants 마감 (30.8시간 남음)
   |             -> 이때 Tameion 상금은 아직 정해지지 않음
   |                그래서 "already funded" 제외 조건(92행)에 걸리지 않음
   |
10-18 12:59    Tameion 제출 마감 (102.8시간 남음)
   |
10-21          Microgrants 결정 기한 (원문 날짜, 시각 없음)
   |
10-23          Encode London (런던 현장, 상금과 심사위원 미정)
   |
11-04 03:29    ETHGlobal Mumbai 신청 마감 (501시간 남음)
   |
11-05 ~ 11-07  ETHGlobal Mumbai (현장, Arc 상금 1만 5,000달러, 세부 미정)
```

Figure 4. Order of the events now visible (English)

```text
Only dates that carry a time are converted to KST; the rest are source dates.
Time left is counted from 10-14 06:11 KST (tools/deadlines.py).
Vertical spacing shows order only; it is not proportional to the time between dates.

 9-22          Arc Acceleration Season application deadline: passed
   :
10-14 06:11    Now
   |
10-15 12:59    Arc Microgrants deadline (30.8 hours left)
   |             -> Tameion prizes are not decided yet at this point
   |                so the "already funded" exclusion (line 92) does not apply
   |
10-18 12:59    Tameion submission deadline (102.8 hours left)
   |
10-21          Microgrants decisions due (source date, no time given)
   |
10-23          Encode London (on site in London; prizes and judges not announced)
   |
11-04 03:29    ETHGlobal Mumbai application deadline (501 hours left)
   |
11-05 ~ 11-07  ETHGlobal Mumbai (on site; Arc prize USD 15,000, details pending)
```

이 그림은 라 절 표의 행사를 날짜 순서로 다시 놓은 것입니다. 표는 행사마다 형식과 조건을 비교하고, 이 그림은 순서를 보여 줍니다.

- 순서가 필요한 이유: 바로 아래 문단이 Microgrants와 Tameion이 이번 회차에 충돌하지 않는다고 판단하는 근거가 두 마감의 순서이기 때문입니다. 그 판단은 그림의 10-15 줄 아래에 짧게 적었습니다.
- 날짜: Microgrants의 결정 기한과 Encode, Mumbai의 날짜는 원문에 시각이 없어서 원문의 날짜를 그대로 적었습니다.
- 남은 시간: `tools/deadlines.py`가 10-14 06:11 KST를 기준으로 계산한 값입니다.
- 범위: 앞으로 나올 행사를 고르는 기준 여섯 가지는 이 그림이 아니라 아래 2번에 있습니다.
- 위치: 이 그림은 그림 1의 층 2 가운데 지금 보이는 행사를 자세히 보여 줍니다.

7번 계획에는 Microgrants에 대해 "Tameion 상금을 받은 작업은 제외되므로, 둘 다 노리면 순서가 충돌합니다"라고 적었습니다(q7-plan.md 58행). 원문을 다시 열어 보니 이번 회차에는 충돌하지 않습니다.

- Microgrants의 제외 조건은 "work already funded by a Circle or Arc program"입니다(92행).
- Microgrants 마감은 Tameion 마감보다 사흘 앞서므로, Microgrants에 낼 시점에 Tameion 상금은 아직 정해지지 않습니다.
- Tameion 쪽에는 다른 지원금을 받은 작업을 제외하는 문장이 없습니다(검색: `rg -n -i 'grant|funded|eligib' cb/works/web/2026-10-08-arc-events-complete/pages/linked/3014da44f43886ec.md`, 일치 3건 389, 422, 430행은 모두 후속 지원과 변화분 심사).

### 2. 앞으로 나올 행사: 고르는 기준 여섯 가지

Canteen 시리즈는 Agora, Lepton, Tameion 순으로 열렸고(47행), Lepton이 끝난 날부터 Tameion이 시작한 날까지는 90일입니다(`90일 = 2026-06-29 -> 2026-09-27`, `tools/deadlines.py`의 date 뺄셈; Lepton 공고 33행, Tameion 페이지 36행). 그러나 다음 회차를 약속하는 문장은 Tameion 페이지에 없습니다(검색: `rg -n -i 'next (event|round|series)|fourth|upcoming|series' cb/works/web/2026-10-08-arc-events-complete/pages/linked/3014da44f43886ec.md`, 일치 3건 47, 246, 256행은 시리즈 소개와 RFB 본문). 그래서 앞으로 나올 행사는 예측하지 않고, 행사가 나오면 다음 여섯 가지를 봅니다. 기준은 제 것이고, 나 절의 표와 이 절의 표에서 행사마다 갈렸던 자리를 그대로 질문으로 바꾼 것입니다.

1. **실제 사업체나 견인을 요구하는가.** 요구하면 고객 접점 축은 얻는 것이 아니라 조건입니다. 붙일 사업체가 없으면 제출하지 않는 쪽으로 기웁니다.
2. **현장 행사이고, 갈 수 있는가.** 사람과의 연결 축은 지금까지 본 행사에서 현장이냐 아니냐로 크게 갈렸습니다.
3. **Arc 쪽 에이전트 기준(상금 주제, 심사 비율)이 공개되었는가.** 공개되기 전에는 Arc가 무엇을 원하는지 알 수 없으므로, 공개된 뒤에 정합니다.
4. **결과물을 Arc 밖으로 옮길 수 있는가.** 마 절의 이식성 판단이 행사마다 달라지는지를 봅니다.
5. **Circle/Arc 사람과 직접 만나는 자리(데모 데이, 심사 방식, 후속 지원)가 있는가.**
6. **마감까지 남은 시간이 결과물 하나를 끝까지 만들기에 충분한가.** Tameion처럼 마지막 며칠에 들어가면 변화분 심사에서 불리합니다.

## 마. 이식성: 결과물을 Arc 밖으로 옮길 때 잃는 것

[제 판단, 확신도 중간] 잃는 것은 적습니다.

- 잃지 않는 이유: Arc는 EVM 호환이고(Arc 상금 페이지 30행), 지금 나와 있는 Circle 에이전트 장치는 Arc에 묶이지 않으며(4번 라 절), 결과물의 논리는 체인과 무관합니다.
- Arc에 묶이는 것은 제출 조건뿐입니다.
  - Tameion은 Arc 위에서 USDC가 흘러야 합니다(389, 395행, testnet도 인정).
  - Microgrants는 Arc 메인넷 배포가 필요합니다(64행).

## 바. 종합 판정: 행사별 결론과 사용자가 정할 것

[제 판단, 확신도 중간]

- **Tameion**: 사업체를 붙일 수 있으면 지원합니다. 붙일 수 없으면 제출하지 않고, 공개 자료로 학습만 합니다. 나흘이라는 시간을 생각하면 상금보다 학습과 공개 저장소를 목표로 잡습니다.
- **Arc AI 에이전트 해커톤 전반**: 행사마다 라 절의 기준 여섯 가지로 고릅니다. 지금까지 본 행사에서 공통으로 보이는 것은 이렇습니다(나 절).
  - 학습 자료와 외부 마감은 확실히 얻습니다.
  - 공개 저장소와 영상은 행사가 끝나도 남습니다.
  - 사람과의 연결은 행사 형식에 따라 일부만 얻습니다.
  - 실제 사업체는 얻는 것이 아니라 가지고 들어가야 합니다(Tameion).
- 그래서 이번 판단에서 사용자가 정할 것은 하나로 좁혀집니다. 남은 나흘 안에 붙일 실제 사업체가 있는지입니다.

## 한계

- 원문은 2026-10-08 보관본입니다. 그 뒤의 변경(Encode의 상금 발표, Mumbai의 Arc 상금 세부, Tameion FAQ의 수정)은 반영하지 않았습니다.
- 사용자의 Tameion 등록 여부, 붙일 수 있는 사업체, 이미 배포한 결과물은 확인하지 않았습니다. 그래서 다 절은 조건으로만 적었습니다.
- Encode London의 날짜는 자료끼리 어긋납니다.
  - 행사 소개는 "A full 3 days of non-stop hacking"이라고 적습니다(Encode 일정 13행).
  - 같은 파일의 일정 데이터는 시작과 끝이 모두 2026-10-23입니다(44-45행).
  - 세부는 "will be announced soon"입니다(15행).
- Tameion의 끝나는 날도 자료끼리 어긋납니다. 이 답은 주최자 페이지를 따랐습니다.
  - 주최자 페이지는 기간을 10월 17일까지로 적고(36행), 마감을 "Deadline: October 17, 11:59 PM ET."로 적습니다(94행).
  - 같은 날 보관한 Arc 커뮤니티의 행사 페이지는 "September 27 to October 10, 2026"이라고 적고(행사 페이지 152행), 같은 파일의 일정 데이터도 끝을 2026-10-10으로 적습니다(행사 페이지 20행).
  - 제출 마감을 직접 적은 쪽은 주최자 페이지뿐이어서 그쪽을 택했습니다.
  - 이 차이는 답을 쓴 뒤 최종 보고를 verifier로 대조하다가 찾았습니다(2026-10-14).
- Arc House의 "Hackathon Participant"는 어느 해커톤인지 한정하지 않고, 참가의 기준(등록인지 제출인지)도 적지 않습니다(기여 항목 47-51행).
- 처음 쓴 답(2026-10-14)은 사용자가 과거에 정리한 판단 두 가지를 판단의 틀로 썼습니다. 하나는 09-21 방향(권한과 정책을 검사하고 감사하는 런타임)을 다룬 절이고, 다른 하나는 제가 과거 문서(08-07 선발 기준과 커리어 기록)에서 이름을 지어 picker 선택지로 낸 네 축입니다. 둘 다 질문과 Circle/Arc 자료에서 나온 것이 아니어서 2026-10-15에 뺐습니다. 경위와 바꾼 곳은 q7-report.md의 "답을 쓴 뒤 고친 것" 6번과 checks/past-influence-audit.md에 있습니다.
- 투자와 자산 이야기는 하지 않았습니다.

## 인용 위치

행 번호는 1부터 셉니다(`sed -n` 기준). 인용 안의 " / "는 원문의 줄바꿈입니다. 별도 표시가 없는 행 번호는 그 항목이 다루는 행사의 주최자 페이지나 공고의 행입니다. Encode는 행사 페이지(Luma)와 일정 파일 두 곳을 인용했고, 본문에서 "Encode 페이지"와 "Encode 일정"으로 구분했습니다.

| 인용한 곳 | 경로와 행 |
|---|---|
| Tameion 주최자 페이지 | `cb/works/web/2026-10-08-arc-events-complete/pages/linked/3014da44f43886ec.md:28-29, 34, 36, 40, 47, 64-67, 69-75, 80, 86, 89-90, 94-95, 107-116, 172-292, 306-316, 355-374, 389, 394-397, 405-409, 411, 414-415, 420-424, 429-430` |
| Arc 커뮤니티의 Tameion 행사 페이지 | `cb/works/web/2026-10-08-arc-events-complete/pages/events/tameion-agents-hackathon-jb1w9clwx7.md:20, 152` |
| 보관 단위 README | `cb/works/web/2026-10-08-arc-events-complete/README.md:31` |
| Arc Microgrants 공고 | `cb/works/web/2026-10-08-arc-events-complete/pages/user-archives/arc-microgrants.md:60-68, 73-78, 86-94` |
| Encode 페이지 (Luma) | `cb/works/web/2026-10-08-arc-events-complete/pages/linked/31013bc2e5a9535c.md:30-36, 43, 53-58, 63-68` |
| Encode 일정 | `cb/works/web/2026-10-08-arc-events-complete/pages/reading-inputs/encode-london-hackathon-and-conference-znntsye2lf.md:13, 15, 37, 44-49` |
| ETHGlobal Mumbai 공고 | `cb/works/web/2026-10-08-arc-events-complete/pages/user-archives/mumbai.md:37, 61-73, 90-104, 114-115, 318, 342, 358, 459, 723, 2411` |
| Mumbai의 Arc 상금 페이지 | `cb/works/web/2026-10-08-arc-events-complete/pages/linked/3cc0d4f37b840e1c.md:26, 30-31` |
| Lepton 공고 | `cb/works/web/2026-10-08-arc-events-complete/pages/reading-inputs/hackathon-lepton-agents-em1dcv9xwe.md:33` |
| Arc Acceleration Season 공고 | `cb/works/web/2026-10-08-arc-events-complete/pages/reading-inputs/arc-acceleration-season-vanemu91dk.md:9` |
| Arc House 기여 항목 | `cb/works/web/2026-09-25-circle-arc-verdict-check-sources/raw/arc-house-architects-contribution-opportunities.md:47-58` |
| Arc House 등급과 혜택 | `cb/works/web/2026-09-25-circle-arc-verdict-check-sources/raw/arc-house-architects-tiers-and-benefits.md:41, 46-58, 67, 81` |
| Circle 메인넷 보도자료 | `cb/works/web/2026-09-20-circle-arc-primary-sources/raw/circle-mainnet-launch.md:84, 86` |
| Circle Beyond 글 | `cb/works/circle-blog/undated-current-beyond-agentic-payments-the-operating-layer-for-the-agentic-economy/pages/beyond-agentic-payments-the-operating-layer-for-the-agentic-economy.en.md:45` |
| 3번 답 | `cb/derived/arc-hackathon-questions-20261014/q3-answer.md:171-179` |
| 4번 답 | `cb/derived/arc-hackathon-questions-20261014/q4-answer.md:527` |
| 7번 계획 | `cb/derived/arc-hackathon-questions-20261014/q7-plan.md:23, 58` |
