# Agent vs Agent Payment

Agent와 Agent Payment를 구분하고, Agent가 결제할 때 지금의 결제 시스템이 왜 맞지 않는지 정리함

## 1. 현재의 결제 시스템: 사람 중심

- 지금의 카드 결제 시스템은 **사람**을 기준으로 만들어짐
- Agent가 결제하는 시대에는 이 기준이 맞지 않음
- 그래서 **사람이 Agent에게 결제를 맡기는 일**에 맞춘 시스템이 필요함
- 왜 사람 기준인지는 4.1절(결제 시스템의 단위)에서, 무엇이 바뀌어야 하는지는 6절(결론)에서 다룸

```text
[한국어]
[지금의 결제]

  사람 ---- 직접 결제 ----> 가맹점

  결제하는 쪽 = 책임지는 쪽      -> 지금의 결제 시스템과 맞음


[Agent 시대의 결제]

  사람 ---- 맡김 ----> Agent ---- 결제 ----> 가맹점

  결제하는 쪽(Agent) != 책임지는 쪽(사람)
                                 -> 지금의 결제 시스템과 맞지 않음

  지금의 시스템은 이런 차이를 전제하지 않음
```

```text
[English]
[Payment today]

  Person ---- pays directly ----> Merchant

  Who pays = who is liable        -> fits today's payment system


[Payment with Agents]

  Person ---- delegates ----> Agent ---- pays ----> Merchant

  Who pays (Agent) != who is liable (Person)
                                  -> does not fit today's payment system

  Today's system does not assume this difference
```

- 이 비교에서 달라진 것은 결제를 시작하는 쪽(사람 또는 Agent) 하나뿐임
- 지금의 결제는 결제하는 사람과 책임지는 사람이 같음
- Agent 시대에는 둘이 갈라짐. 지금의 결제 시스템은 이 갈라짐을 전제하지 않음

## 2. Agent: 자동화 프로그램 + 판단

- Agent는 자동화 프로그램의 한 종류임
- 여기서 자동화는, 사람이 처음에 한 번 정해 두면 그 뒤로는 실행할 때마다 사람이 그 자리에 없어도 프로그램이 대신 실행한다는 뜻임
- 자동화 프로그램 가운데 **판단**이 들어간 것만 Agent라고 부름

```text
[한국어]
+--------------------------------------------------------+
| 자동화 프로그램: 사람이 한 번 정해 두면, 실행은 대신함 |
|                                                        |
|   +------------------------+  +----------------------+ |
|   | 판단 없는 자동화       |  | 판단하는 자동화      | |
|   | 예: 정기배송, 자동이체 |  | = Agent              | |
|   | 사람이 정한 대로 실행  |  | 스스로 정해서 실행   | |
|   +------------------------+  +----------------------+ |
+--------------------------------------------------------+
```

```text
[English]
+--------------------------------------------------------+
| Automation program: set once by a person, then runs    |
|                                                        |
|   +------------------------+  +----------------------+ |
|   | No-judgment automation |  | Judging automation   | |
|   | e.g. subscriptions,    |  | = Agent              | |
|   | autopay; runs as set   |  | decides, then runs   | |
|   +------------------------+  +----------------------+ |
+--------------------------------------------------------+
```

- 자동화 프로그램은 모두, 사람이 처음에 정해 둔 뒤로는 사람 없이 실행됨
- 자동화 프로그램은 판단이 있는지로 둘로 나뉨. 판단하는 쪽만 Agent임
- 둘의 차이는 사람이 처음에 무엇까지 정하는가에 있음

```text
[한국어]
                  처음에 사람이 정하는 것   실행할 때 사람이 하는 일
----------------  ------------------------  ------------------------
판단 없는 자동화  무엇을, 누구에게, 얼마에  없음
Agent             목표와 조건만             없음
```

```text
[English]
                        What the person sets first    What the person does at run time
----------------------  ----------------------------  --------------------------------
No-judgment automation  What, to whom, how much       Nothing
Agent                   Only the goal and conditions  Nothing
```

- 실행할 때 사람이 빠지는 것은 둘 다 같음. 이것이 자동화임
- 판단 없는 자동화는 무엇을, 누구에게, 얼마에 낼지를 사람이 처음에 정함
- Agent는 사람이 목표와 조건만 정하고, 무엇을 할지는 Agent가 정함. 이것이 판단임
- Agent가 무엇인지는 2.1절(정의)에서, 판단 없는 자동화와 어떻게 다른지는 2.2절(Agent vs 판단 없는 자동화)에서 다룸

### 2.1 정의: 사람 대신 일하고 스스로 판단함

- Agent는 사람 대신 무언가를 자동으로 처리하는 프로그램임
- 그런데 자동화만으로는 Agent라고 부르지 않음. 핵심은 **판단**이 들어간다는 점임
  - 무엇을 할지, 언제 할지, 얼마에 할지를 Agent가 스스로 정함
  - 사람은 목표와 조건만 줌

```text
[한국어]
  사람 ---- 목표와 조건 ----> Agent ---- 실행 ----> 결과
                                | 판단
                                +-- 무엇을 할지 정함
                                +-- 언제 할지 정함
                                +-- 얼마에 할지 정함
```

```text
[English]
  Person ---- goal and conditions ----> Agent ---- acts ----> Result
                                          | judges
                                          +-- decides what to do
                                          +-- decides when to do it
                                          +-- decides how much to pay
```

- 사람이 주는 것은 목표와 조건뿐임
- 무엇을, 언제, 얼마에 할지는 Agent 안에서 정해짐
- 이 세 가지를 Agent가 정한다는 점이 4.2절(거래마다 미리 승인할 수 없음)의 출발점이 됨

### 2.2 Agent vs 판단 없는 자동화: 판단이 있는지로 갈림

- 쿠팡 정기배송이나 은행 자동이체도 사람 대신 결제를 처리함
- 그러나 이들은 판단하지 않음. 무엇을, 누구에게, 얼마를 낼지를 사람이 미리 정해 두었고, 프로그램은 그대로 실행할 뿐임
- 이 구분은 4절(필요성)에서 다시 중요해짐. 판단하지 않는 자동화는 지금의 결제 시스템으로도 충분히 처리되기 때문임

```text
[한국어]
                     판단 없는 자동화          Agent
                     (정기배송, 자동이체)      (리테일 Agent 등)
-------------------  ------------------------  ------------------------
무엇을, 얼마에 살지  사람이 미리 정함          Agent가 정함
누구에게 낼지        사람이 미리 정함          Agent가 정함
결제 승인            처음에 한 번 미리 함      거래마다 미리 할 수 없음
판단                 없음                      있음
```

```text
[English]
                      No-judgment automation    Agent
                      (subscription, autopay)   (retail Agent, etc.)
--------------------  ------------------------  ------------------------
What, how much to buy Set by the person         Decided by the Agent
Whom to pay           Set by the person         Decided by the Agent
Payment approval      Once, in advance          Not possible per
                                                transaction in advance
Judgment              None                      Yes
```

- 판단 없는 자동화와 Agent는 같은 일(사람 대신 결제)을 함
- 차이는 "누가 정하는가"임. 판단 없는 자동화는 사람이 미리 정하고, Agent는 스스로 정함. 이 차이가 곧 판단의 유무임
- 결제 승인의 차이(처음에 한 번 미리 하는가, 거래마다 미리 할 수 없는가)가 4절(필요성)의 핵심 문제로 이어짐

```text
[한국어]
[판단 없는 자동화의 워크플로우: 정기배송]

  사람: 상품, 금액, 주기를 정함
         |
         v
  프로그램: 정한 날이 됨 ---> 정한 상품을 ---> 정한 금액으로 결제
         |
         v
  다음 주기에도 같은 일을 반복함 (중간에 바뀌는 것 없음)


[Agent의 워크플로우: 리테일 Agent]

  사람: 목표와 조건을 줌 (예: 생필품을 싸게, 한 달 10만 원 안에서)
         |
         v
  Agent: 가격 확인 ---> 비교 ---> 무엇을, 언제, 얼마에 살지 판단 ---> 결제
           ^                                                          |
           |                                                          |
           +-------------- 결과를 보고 다음 판단에 반영 <-------------+
```

```text
[English]
[Workflow of no-judgment automation: subscription delivery]

  Person: sets the product, amount and interval
         |
         v
  Program: set day comes ---> set product ---> pays the set amount
         |
         v
  Repeats the same next cycle (nothing changes in between)


[Workflow of an Agent: retail Agent]

  Person: gives a goal and conditions
          (e.g. cheap daily goods, within 100,000 won a month)
         |
         v
  Agent: check prices ---> compare ---> decide what, when, how much ---> pay
           ^                                                              |
           |                                                              |
           +-------------- feeds the result into the next decision ----<--+
```

- 정기배송은 사람이 정한 것을 정해진 순서대로 되풀이함. 결제할 상품과 금액이 처음부터 정해져 있음
- 리테일 Agent는 매번 가격을 확인하고 비교해서 판단함. 결제할 상품과 금액은 판단이 끝나야 정해짐
- Agent는 결과를 보고 다음 판단을 바꿀 수 있음
- 예에 든 금액(한 달 10만 원)은 설명을 위한 값임

## 3. Agent Payment: Agent가 결제할 때 쓰는 기술

- Agent Payment는 Agent의 한 종류가 아님
- Agent가 결제와 관련된 일을 할 때 쓰는 기술들을 묶어 부르는 이름임
- 같은 Agent Payment 기술을 여러 종류의 Agent가 함께 씀
  - 예: 리테일 Agent, 데이터를 사는 Agent, 클라우드 자원을 빌리는 Agent
- 분류(Category): 지금 나와 있는 기술을 하는 일에 따라 나누면 아래와 같음. 이 나눔은 이 글이 정한 것임
  - **결제 요청과 지급**: Agent가 API나 데이터 같은 자원을 요청하면 그 자리에서 값을 치르게 함
    - [x402](https://www.x402.org/): HTTP의 402 Payment Required 응답으로 결제를 요청하고 받음. Coinbase가 만들었고 지금은 x402 재단이 맡음
    - [MPP(Machine Payments Protocol)](https://mpp.dev/): API 요청, 도구 호출, 콘텐츠에 값을 매기는 규격. Stripe와 Tempo가 함께 만듦
  - **권한 위임의 기록**: 사람이 Agent에게 무엇을 맡겼는지 기록하고 검증함
    - [AP2(Agent Payments Protocol)](https://ap2-protocol.org/): Agent가 사용자를 대신해 결제할 때 그 위임을 다루는 규격. Google이 공개함
  - **Agent 식별과 카드망 연결**: 가맹점이 Agent와 그 뒤의 사람을 알아보게 함
    - Visa Trusted Agent Protocol, Mastercard Agent Pay. 5.2절(가상카드로 풀리지 않는 것)의 가맹점의 확인에서 다룸
  - **구매 흐름**: Agent와 판매자 사이의 주문과 결제 과정을 정함
    - [ACP(Agentic Commerce Protocol)](https://www.agenticcommerce.dev/): Stripe와 OpenAI가 만든 규격
  - **소액 결제 정산과 Agent 지갑**
    - [Circle Nanopayments](https://www.circle.com/blog/a-deep-dive-into-circle-nanopayments-gas-free-usdc-transfers): 1센트보다 작은 USDC 결제를 모아서 정산함
    - [Circle Agent Stack](https://www.circle.com/blog/introducing-circle-agent-stack-financial-infrastructure-for-the-agentic-economy): Agent용 지갑과 결제 도구 묶음

```text
[한국어]
Agent           리테일 Agent    데이터 구매 Agent    클라우드 자원 Agent
                     |                 |                     |
                     +-----------------+---------------------+
                                       |
                                       v
Agent Payment             Agent가 결제할 때 쓰는 기술
                       (x402, MPP, AP2, ACP, TAP, Agent Pay 등)
                                       |
                                       v
결제 수단                  카드, 스테이블코인 등
```

```text
[English]
Agent           Retail Agent    Data-buying Agent    Cloud-renting Agent
                     |                 |                     |
                     +-----------------+---------------------+
                                       |
                                       v
Agent Payment           Technology Agents use to pay
                   (x402, MPP, AP2, ACP, TAP, Agent Pay, etc.)
                                       |
                                       v
Payment rails              Cards, stablecoins, etc.
```

- 일을 하는 Agent들은 하는 일이 서로 다름
- Agent Payment는 이 Agent들이 결제할 때 공통으로 쓰는 기술임. 괄호 안은 위에서 든 기술의 예임
- 실제로 돈이 오가는 것은 카드, 스테이블코인 같은 결제 수단임. Agent Payment는 이 위에서 동작함

### 3.1 흔한 오해: 쿠팡 쇼핑 Agent(예시)는 두 계층이 합쳐진 것임

- 사람들이 자주 드는 예: "쿠팡에서 어떤 물건이 싼지 살펴보고, 정기적으로 사 주는 에이전트가 있다면 그게 Agent Payment다."
- 이 예는 두 계층을 하나로 보고 있음

| 계층                 | 이 예에서 하는 일                                                          |
| -------------------- | -------------------------------------------------------------------------- |
| Agent (리테일 Agent) | 어떤 물건이 싼지 비교하고, 언제 무엇을 살지 판단한다                       |
| Agent Payment        | 그 Agent가 쿠팡 같은 기존 커머스 서비스에서 실제로 돈을 내는 일을 처리한다 |

- 즉 이 예의 주인공은 리테일 Agent이고, Agent Payment는 그 Agent가 결제하는 부분임

```text
[한국어]
  리테일 Agent (Agent)                    | Agent Payment
                                          |
  가격 비교 ---> 구매 판단 ---- 무엇을, ----> 결제 처리 ---- 돈 ----> 쿠팡
                               얼마에     |
                                          |
  <------- 판단하는 부분 ----------------> <----- 돈을 내는 부분 ----->
```

```text
[English]
  Retail Agent (Agent)                    | Agent Payment
                                          |
  compare prices ---> decide --- what, ------> pay ---- money ----> Coupang
                                how much  |
                                          |
  <---------- the judging part ----------> <------ the paying part ------->
```

- 리테일 Agent는 가격을 비교하고 무엇을 얼마에 살지 정함
- 그 결정("무엇을, 얼마에")이 결제 쪽으로 넘어감
- Agent Payment는 그 결정대로 쿠팡에 돈을 냄

## 4. 필요성: Agent만을 위한 결제가 왜 필요한가

- 구분하고 나면 질문이 나옴: **Agent도 그냥 지금의 결제 수단을 쓰면 되지 않나?**
- 먼저 인정할 것
  - 대부분은 지금도 됨
  - Agent 하나에 카드를 주고 한도를 걸 수 있고, 가상카드에도 한도와 기간을 걸 수 있음. 5.1절(가상카드가 이미 하는 것)에서 다룸
- 문제는 아래 다섯 조건에서 생김

| 조건                              | 막히는 것                                  |
| --------------------------------- | ------------------------------------------ |
| 결제 순간에 추가 인증(3DS)이 걸림 | OTP나 생체 인증은 카드 주인이 직접 해야 함 |
| 가맹점이 봇을 막음                | 권한을 받은 Agent인지 가맹점이 알 수 없음  |
| 아주 작은 금액을 자주 냄          | 카드는 건마다 고정 수수료가 붙음           |
| Agent가 많고 금방 생겼다 사라짐   | 카드 발급과 해지가 따라가지 못함           |
| 범위를 넘거나 잘못 판단한 결제    | 누가 책임지는지 정해져 있지 않음           |

- 이 조건들이 왜 생기는지는 세 단계로 이어짐

```text
[한국어]
  결제 시스템은 사람 단위임 (본인 확인, 인증, 사기 탐지, 분쟁 처리)
         |
         v
  Agent는 판단하므로, 사람이 거래마다 미리 승인할 수 없음
         |
         v
  대신 위임 범위(한도, 용처, 기간)를 미리 정해야 함
         |
         v
  위임 범위를 정할 때 속도와 세밀함의 문제가 생김
```

```text
[English]
  Payment systems are built around a person
  (identity check, authentication, fraud detection, disputes)
         |
         v
  An Agent judges, so the person cannot approve each transaction in advance
         |
         v
  Instead, a delegated scope (limit, use, period) must be set in advance
         |
         v
  Setting the delegated scope raises problems of speed and granularity
```

- 결제 시스템이 사람 단위라는 점은 4.1절(결제 시스템의 단위), 거래마다 승인할 수 없어 위임 범위가 필요하다는 점은 4.2절(거래마다 미리 승인할 수 없음), 속도와 세밀함의 문제는 4.3절(속도와 세밀함)에서 다룸
- 각 단계는 앞 단계의 결과로 나옴

### 4.1 결제 시스템의 단위: 사람

- 지금의 리테일 결제 시스템은 **사람 한 명**을 단위로 함. 그래서 Agent가 결제하려면, 사람이 쓰는 신용카드를 Agent에게도 쥐여 줘야 함
- 사람이 단위인 이유: 사람이 **책임을 지는 주체**이기 때문임. 시스템의 여러 부분이 이 전제 위에 있음
  - **본인 확인**: 카드를 만들 때 실명과 신원을 확인함(KYC). 사람이 해결 가능
    - 예: 미국 은행 규정은 계좌를 연 뒤 고객의 신원을 확인하는 절차를 두라고 함. "The CIP must contain procedures for verifying the identity of the customer ... within a reasonable time after the account is opened."([31 CFR 1020.220](https://www.law.cornell.edu/cfr/text/31/1020.220))
  - **결제 순간의 인증**: 3DS는 결제하는 쪽이 카드 주인인지 인증하는 절차임. 위험이 높은 거래에서는 카드 주인이 직접 추가 확인을 해야 함
    - EMVCo: "EMV 3DS enables the exchange of data, or messages, between the merchant and the issuer to authenticate the consumer and approve the transaction."
    - 같은 글: "consumers must authenticate themselves using a challenge, such as a one-time passcode, knowledge-based questions, biometrics, or other methods."([EMVCo, EMV 3-D Secure](https://www.emvco.com/emv-technologies/3-d-secure/))
  - **사기 탐지**: 사람이 아닌 것이 결제하면 의심함. 봇의 결제는 사기로 보기 쉬움
    - Visa는 가맹점이 겪는 문제로 이것을 듦: "Managing bot detection systems that can mistakenly block legitimate agentic transactions"([Visa, Trusted Agent Protocol 발표](https://usa.visa.com/about-visa/newsroom/press-releases.releaseId.21716.html))
  - **분쟁 처리**: 잘못된 결제는 카드 주인이 이의를 제기하고, 카드사가 조사함. 사람이 해결 가능
    - 예: 미국 대금 오류 규정은 카드 주인이나 그에게서 권한을 받은 사람이 하지 않은 결제를 대금 오류로 봄. "an extension of credit that is not made to the consumer or to a person who has actual, implied, or apparent authority to use the consumer's credit card"([12 CFR 1026.13](https://www.law.cornell.edu/cfr/text/12/1026.13))
- 근거
  - Four Pillars의 x402 보고서: "오늘날 우리가 사용하는 모든 결제망은 사람이 거래를 시작한다는 전제 위에 구축되어 있다."([Four Pillars, "x402에 대한 모든 것"](https://research.4pillars.io/ko/research/all-about-x402), PDF 9쪽)
  - 같은 보고서: "신용카드나 페이팔(PayPal)은 사람의 계정과 본인 인증을 전제로 작동했던" 반면, 비트코인은 소프트웨어가 사람 없이 결제할 수 있었음(PDF 16쪽)

```text
[한국어]
                         본인 확인 (KYC <- 사람이 해결 가능)
                               |
  결제 순간의 인증 ----- 사람 (카드 주인) ----- 사기 탐지
  (3DS)                        |                (사람이 아니면 의심)
                           분쟁 처리
                     (카드 주인이 이의 제기 <- 사람이 해결 가능)
```

```text
[English]
                                  Identity check (KYC <- the person can handle it)
                                            |
  Payment-time authentication ---- Person (cardholder) ---- Fraud detection
  (3DS)                                     |               (suspects non-humans)
                                    Dispute handling
                              (cardholder raises a dispute <- the person can handle it)
```

- 네 가지가 모두 사람(카드 주인)에 연결되어 있음
- 이 가운데 본인 확인과 분쟁 처리는 Agent가 결제해도 사람이 해결할 수 있음. 카드는 사람이 만들고, 이의도 사람이 제기하면 됨
- 사람 자리에 Agent를 넣으면 둘이 문제
  - Agent는 결제 순간의 인증을 스스로 통과하기 어렵고, 봇으로 의심받음

### 4.2 판단이 만드는 문제: 거래마다 미리 승인할 수 없음

- 2.2절(Agent vs 판단 없는 자동화)의 정기배송과 자동이체는 지금의 시스템으로도 됨. 상대와 금액을 사람이 **미리 승인**해 두었기 때문임
- Agent는 다름. 어디서, 무엇을, 얼마에 살지를 Agent가 판단하므로, 사람이 거래 하나하나를 미리 승인할 수 없음

```text
[한국어]
[정기배송, 자동이체]

  사람: 상대와 금액을 승인 ----> 프로그램: 그대로 결제 (매번 같음)
        (거래가 미리 정해져 있음)


[Agent]

  사람: 목표만 줌 ----> Agent: 상대와 금액을 고름 ----> 결제
                                    ^
                                    |
                          승인할 거래가 이때 처음 정해짐
```

```text
[English]
[Subscriptions, autopay]

  Person: approves payee and amount ----> Program: pays as set (same each time)
          (the transaction is fixed in advance)


[Agent]

  Person: gives a goal only ----> Agent: picks payee and amount ----> Pay
                                               ^
                                               |
                       the transaction to approve is first decided here
```

- 정기배송과 자동이체는 승인할 대상이 처음부터 정해져 있음
- Agent는 판단한 뒤에야 승인할 대상이 생김. 그래서 사람이 미리 승인할 수 없음

- 그렇다고 거래마다 사람에게 물어보면, Agent에게 일을 맡긴 의미가 사라짐
- 그래서 거래 하나하나를 승인하는 대신, **어디까지 맡길지**(위임 범위)를 미리 정해 주는 방식이 필요함
  - 얼마까지 쓸 수 있는가(한도)
  - 어디에, 무엇에 쓸 수 있는가(용처)
  - 언제까지 쓸 수 있는가(기간)

```text
[한국어]
[거래마다 승인]

  거래 1 ---> 사람이 확인 ---> 결제
  거래 2 ---> 사람이 확인 ---> 결제
  거래 3 ---> 사람이 확인 ---> 결제        사람이 매번 끼어듦


[위임 범위]

  사람이 범위를 한 번 정함 (한도, 용처, 기간)
         |
         v
  +-------------------- 위임 범위 --------------------+
  |  거래 1 ---> 결제                                 |
  |  거래 2 ---> 결제        Agent가 범위 안에서 결제 |
  |  거래 3 ---> 결제                                 |
  +---------------------------------------------------+
  거래 4 (범위 밖) ---> 막힘
```

```text
[English]
[Approval per transaction]

  Transaction 1 ---> person checks ---> pay
  Transaction 2 ---> person checks ---> pay
  Transaction 3 ---> person checks ---> pay      the person steps in every time


[Delegated scope]

  The person sets the scope once (limit, use, period)
         |
         v
  +--------------------- delegated scope ---------------------+
  |  Transaction 1 ---> pay                                   |
  |  Transaction 2 ---> pay      Agent pays within the scope  |
  |  Transaction 3 ---> pay                                   |
  +-----------------------------------------------------------+
  Transaction 4 (outside the scope) ---> blocked
```

- 거래마다 승인하면 사람이 매번 끼어듦
- 위임 범위를 쓰면 사람은 범위를 한 번만 정하고, 그 안의 거래는 Agent가 처리함
- 범위를 벗어난 거래는 결제되지 않음

### 4.3 위임 범위의 문제: 개수보다 속도와 세밀함이 중요

- Agent가 하나라면 카드 한 장을 주고 한도를 걸면 됨. 그런데 Agent가 1000개라면?
- 사실 개수 자체는 큰 문제가 아님. 회사는 이미 직원 1000명에게 법인카드를 나눠 줌
- 진짜 문제는 두 가지임
  - **속도**: Agent는 필요할 때 새로 만들고, 일이 끝나면 없앰. 금방 생겼다가 사라지는 Agent마다 카드 발급부터 시작해야 한다면 맞지 않음
  - **세밀함**: Agent마다 한도와 용처를 따로 정하고, 일이 바뀌면 바로 바꾸거나 거둘 수 있어야 함
- 이것이 Agent Payment가 푸는 가장 중요한 문제임

```text
[한국어]
[문제: 속도]

  Agent 생성 --> 결제 권한 줌 --> 일 수행 --> 결제 권한 거둠 --> Agent 삭제
                  (카드 발급?)                  (카드 해지?)

  |<----------------------- 짧으면 몇 초, 길면 며칠 --------------------->|
```

```text
[English]
[Problem: speed]

  Create Agent --> grant payment --> do work --> revoke payment --> delete Agent
                   (issue a card?)               (cancel the card?)

  |<-------------- seconds at the shortest, days at the longest -------------->|
```

- Agent 하나가 생겨서 사라질 때까지 결제 권한을 한 번 주고 한 번 거둬야 함
- 이 일생이 짧을수록, 사람을 위한 카드 발급과 해지 절차는 맞지 않음

```text
[한국어]
[문제: 세밀함] (예시)

              한도         용처              기간
  Agent A     5만 원       식료품            이번 주
  Agent B     1천 원       API 호출          1시간
  Agent C     0원          (권한 거둠)       -
```

```text
[English]
[Problem: granularity] (example)

              Limit          Use              Period
  Agent A     50,000 won     groceries        this week
  Agent B     1,000 won      API calls        1 hour
  Agent C     0 won          (revoked)        -
```

- 표의 값은 설명을 위한 예시임
- 같은 사람이 맡긴 Agent라도 한도, 용처, 기간이 서로 다름
- Agent C처럼 일이 끝나면 바로 권한을 거둘 수 있어야 함

## 5. 반론: Agent별 가상카드로 되지 않을까?

- 가상카드: 기업이 공급자 결제용으로 따로 발급하고 한도와 만료일을 거는 카드 번호([Four Pillars, "x402에 대한 모든 것"](https://research.4pillars.io/ko/research/all-about-x402), PDF 66쪽)
  - 실물 카드 없이 발급하는 카드 번호
  - 기존 카드 계좌나 신용 한도에 연결
  - 번호마다 한도, 만료일, 쓸 수 있는 가맹점을 따로 걸 수 있음
  - 출처(PDF 66쪽)가 받치는 것은 공급자 결제용이라는 점과 한도, 만료일까지임. 실물 카드 없이 발급하는 점, 카드 계좌나 신용 한도에 연결하는 점, 가맹점을 거는 점은 이 글에서 확인하지 않았음
- 4.3절(위임 범위의 문제)만 보면, 이미 있는 가상카드로 풀린다는 반론이 나옴
- 이 반론은 상당 부분 맞음. 그래도 풀리지 않는 문제가 남음

```text
[한국어]
  Agent 결제의 문제
    |
    +-- 가상카드로 풀리는 것
    |     Agent마다 한도, 용처, 기간을 따로 정하기
    |
    +-- 가상카드로 풀리지 않는 것
          건당 비용
          결제 순간의 인증
          가맹점의 확인
          책임
```

```text
[English]
  Problems of Agent payments
    |
    +-- Solved by virtual cards
    |     setting a limit, use and period per Agent
    |
    +-- Not solved by virtual cards
          per-transaction cost
          payment-time authentication
          merchant verification
          liability
```

- 가상카드로 풀리는 것은 5.1절(가상카드가 이미 하는 것), 풀리지 않는 것은 5.2절(가상카드로 풀리지 않는 것)에서 다룸

### 5.1 가상카드가 이미 하는 것: 한도와 기간을 건 카드

- 카드 회사는 이미 가상카드에 한도와 기간을 걸 수 있게 함
  - x402 보고서: "마스터카드(Mastercard)의 가상 카드 플랫폼은 지출 한도, 거래 한도와 유효 기간을 설정하는 통제를 제공한다."([Four Pillars, "x402에 대한 모든 것"](https://research.4pillars.io/ko/research/all-about-x402), PDF 66쪽)
  - 같은 자리에서 American Express의 기업용 가상카드도 지출 한도와 만료일을 설정한다고 씀
- 그래서 "Agent마다 한도와 용처를 따로 정한다"만으로는, 새 시스템이 필요한 이유가 되지 않음

```text
[한국어]
  회사 (사람) ---- 범위를 정함 ----> 가상카드 ---- 결제 ----> 공급자
                                       |
                                       +-- 지출 한도
                                       +-- 거래 한도
                                       +-- 유효 기간
```

```text
[English]
  Company (person) ---- sets the scope ----> Virtual card ---- pays ----> Supplier
                                                   |
                                                   +-- spending limit
                                                   +-- transaction limit
                                                   +-- validity period
```

- 범위를 가상카드에 담아 두면, 결제할 때마다 사람이 확인하지 않아도 됨
- 4.2절(거래마다 미리 승인할 수 없음)의 위임 범위와 같은 구조임

### 5.2 가상카드로 풀리지 않는 것: 건당 비용, 인증, 가맹점의 확인, 책임

- **건당 비용**
  - API 호출 한 번, 데이터 한 건처럼 몇 원도 안 되는 결제를 아주 자주 하는 경우임
  - 카드는 건마다 고정 수수료가 붙어서 이런 결제를 감당하지 못함
  - Circle: "Traditional payment rails are not designed to support high frequency sub-cent payments ... due to fixed fees, settlement latency, and operational overhead."([Circle, A Deep Dive into Circle Nanopayments](https://www.circle.com/blog/a-deep-dive-into-circle-nanopayments-gas-free-usdc-transfers))
  - x402 보고서도 [x402](https://www.x402.org/)로 "카드 결제망에서는 경제성이 없었던 거래가 가능해진다"고 쓰고, 예로 API 호출별 과금과 크롤링별 과금을 듦([Four Pillars, "x402에 대한 모든 것"](https://research.4pillars.io/ko/research/all-about-x402), PDF 9쪽)
- **결제 순간의 인증**
  - 4.1절(결제 시스템의 단위)에서 본 3DS의 추가 확인(OTP, 생체 인증 등)은 카드 주인이 직접 해야 함. Agent는 이 단계를 스스로 통과하기 어려움
  - 새 서비스를 쓸 때마다 사람이 계정을 만들고 카드를 등록해야 하는 것도 같은 문제임
  - Circle은 x402가 "allows any agent to pay any merchant without first needing to create an account or add a credit card"라고 씀(같은 글)
- **가맹점의 확인**
  - 건당 비용과 결제 순간의 인증은 돈을 **내는** 쪽의 문제임. 돈을 **받는** 쪽에도 문제가 있음
  - 가맹점은 결제하러 온 Agent가 정말 어떤 사람에게서 권한을 받았는지 알 수 없음. 그래서 봇으로 보고 막기 쉬움
  - 카드 회사들이 이 문제를 풀려고 함
    - x402 보고서: 비자는 Trusted Agent Protocol(TAP)과 Visa Intelligent Commerce를, 마스터카드는 Agent Pay를 통해 "에이전트 식별, 사용자 위임과 결제 승인을 기존 카드망에 연결하는 체계를 준비하고 있다"(PDF 56쪽)
    - 각 회사의 발표: [Visa, Trusted Agent Protocol 발표(2025-10-14)](https://usa.visa.com/about-visa/newsroom/press-releases.releaseId.21716.html), [Mastercard, Agent Pay 발표(2025-04)](https://www.mastercard.com/news/press/2025/april/mastercard-unveils-agent-pay-pioneering-agentic-payments-technology-to-power-commerce-in-the-age-of-ai/)
- **책임**
  - 지금의 분쟁 처리는 결제를 권한이 있었는지로 나눔. 4.1절(결제 시스템의 단위)의 미국 대금 오류 규정은 카드 주인이나 권한을 받은 사람이 하지 않은 결제만 대금 오류로 봄
  - 이 규정대로라면, 사람이 권한을 준 Agent가 범위 안에서 한 결제는 카드 주인이 승인한 결제 쪽에 들어갈 수 있음
  - 남는 문제는 Agent가 받은 범위를 넘었을 때, 그리고 범위 안에서 잘못 판단했을 때 누가 책임지는가임
  - Agent에게 준 권한이 이 규정의 "authority"에 해당하는지를 다룬 판례나 감독 당국의 해석은 이 글에서 확인하지 않았음
  - 이 문제는 7절(정리)의 앞으로 이야기될 것들에 남김

```text
[한국어]
  Agent (내는 쪽) ------------- 결제 -------------> 가맹점 (받는 쪽)

  내는 쪽의 문제                                    받는 쪽의 문제
  - 건당 비용: 소액 결제에 수수료가 큼              - 가맹점의 확인:
  - 결제 순간의 인증: 추가 확인을 통과하기 어려움    이 Agent가 정말
                                                      위임받았는가

                    양쪽 모두의 문제
                    - 책임: 잘못된 결제는 누가 지는가
```

```text
[English]
  Agent (payer) ------------- payment -------------> Merchant (payee)

  Payer-side problems                             Payee-side problems
  - Per-transaction cost: fees are                - Merchant verification:
    large for small payments                        was this Agent really
  - Payment-time authentication:                    delegated?
    hard to pass the extra check

                    Problem for both sides
                    - Liability: who bears a wrong payment?
```

- 네 문제는 결제의 어느 쪽에서 생기는지로 나뉨
- 건당 비용과 인증은 Agent 쪽, 가맹점의 확인은 가맹점 쪽, 책임은 양쪽 모두의 문제임

```text
[한국어]
  권한이 있는 결제                         권한이 없는 결제
  (대금 오류가 아님)                       (대금 오류, 이의 제기 대상)
    |                                        |
    +-- 카드 주인이 직접 한 결제             +-- 도용
    +-- 권한을 받은 Agent가
        범위 안에서 한 결제


  경계가 분명하지 않은 곳
    |
    +-- Agent가 받은 범위를 넘은 결제
    +-- 범위 안이지만 Agent가 잘못 판단한 결제
```

```text
[English]
  Authorized payments                      Unauthorized payments
  (not a billing error)                    (billing error, can be disputed)
    |                                        |
    +-- made by the cardholder               +-- stolen card use
    +-- made by an authorized Agent
        within its scope


  Where the line is unclear
    |
    +-- Agent payments beyond the granted scope
    +-- Agent payments within scope but on a wrong judgment
```

- 대금 오류 규정은 결제를 권한이 있었는지로 나눔
- 권한을 받은 Agent가 범위 안에서 한 결제는 권한이 있는 결제에 들어갈 수 있음
- 범위를 넘은 결제와 범위 안에서 잘못 판단한 결제는 어느 쪽에 들어갈지 정해져 있지 않음. Agent 결제의 책임 문제는 여기에 남음

## 6. 결론: 진짜 Agent Payment를 위해서는?

- 바뀌어야 하는 것은 두 가지임

```text
[한국어]
  바뀌어야 하는 것
    |
    +-- 결제의 단위
    |     사람 하나  ==>  사람 + Agent + 위임 범위
    |
    +-- 그 시스템이 나올 길
          카드 시스템을 고쳐 쓰는 길
          처음부터 Agent용으로 만든 새 시스템
```

```text
[English]
  What has to change
    |
    +-- The unit of payment
    |     one person  ==>  person + Agent + delegated scope
    |
    +-- Where that system will come from
          adapting the card system
          a new system built for Agents from the start
```

- 결제의 단위는 6.1절(결제 단위의 변화)에서, 그 시스템이 나올 길은 6.2절(결제 시스템)에서 다룸

### 6.1 결제 단위의 변화: Agent가 아니라 위임에 맞춘 시스템

- 1절(현재의 결제 시스템)의 문장을 "Agent에게 맞춘 시스템이 필요하다"로 쓰면 정확하지 않음
- Agent는 돈을 가질 수도 없고 책임을 질 수도 없음. 법적으로 주체가 아님
- 그래서 결제 시스템의 단위가 사람에서 Agent로 **넘어가는** 것이 아님. 책임은 여전히 사람이나 회사가 짐
- 바뀌는 것은 단위의 모양임

```text
[한국어]
지금의 결제 단위                    Agent 시대의 결제 단위

  사람 (카드 주인, 책임을 진다)        사람 (책임을 진다)
    |                                  |
    | 직접 결제한다                    | 맡긴다: 한도, 용처, 기간 (위임 범위)
    v                                  v
  가맹점                              Agent (판단하고 결제한다)
                                       |
                                       | 결제 + "위임받았다"는 증명
                                       v
                                     가맹점 (위임을 확인한다)
```

```text
[English]
Payment unit today                  Payment unit with Agents

  Person (cardholder, liable)        Person (liable)
    |                                  |
    | pays directly                    | delegates: limit, use, period (delegated scope)
    v                                  v
  Merchant                           Agent (judges and pays)
                                       |
                                       | payment + proof of delegation
                                       v
                                     Merchant (verifies the delegation)
```

- 지금은 결제하는 사람과 책임지는 사람이 같음
- Agent 시대에는 둘이 갈라짐. 사람은 책임을 지고 범위를 정하며, Agent는 그 범위 안에서 판단하고 결제함
- 그래서 Agent 시대의 결제에는 지금 없던 두 가지가 필요함
  - 사람이 Agent에게 **범위를 정해 맡기는** 방법: 4.2절(거래마다 미리 승인할 수 없음)과 4.3절(속도와 세밀함)의 문제
  - 가맹점이 그 위임을 **믿을 수 있게 하는** 방법: 5.2절(가상카드로 풀리지 않는 것)의 가맹점의 확인
- 정리하면, 필요한 것은 "Agent에게 맞춘 시스템"이 아니라 "**사람이 Agent에게 결제를 맡기는 일에 맞춘 시스템**"임

### 6.2 결제 시스템: 기존의 카드망을 고치거나, 처음부터 새로 짓거나

- 이 시스템이 어디서 나올지는 아직 정해지지 않음. 길은 둘임
  - **카드 시스템을 고쳐 쓰는 길**: 5.2절(가상카드로 풀리지 않는 것)에서 본 비자 TAP와 마스터카드 Agent Pay
  - **처음부터 Agent용으로 만든 새 시스템**: 스테이블코인과 x402, Circle의 Nanopayments
- 두 길은 서로를 끌어들이고 있음
  - x402 보고서: 카드는 "광범위한 가맹점망과 소비자 보호, 사기 탐지, 분쟁 처리 체계를 이미 갖추고 있다". 그래서 카드 네트워크가 에이전틱 커머스의 주요 결제 수단으로 "남을 가능성이 크다"고 판단함([Four Pillars, "x402에 대한 모든 것"](https://research.4pillars.io/ko/research/all-about-x402), PDF 55쪽)
  - 같은 보고서: 비자와 마스터카드는 x402 재단의 프리미어 회원이고, 비자는 카드 거래의 정산 일부를 스테이블코인으로 하고 있음(PDF 56쪽)
- 그래서 "카드 시스템은 사람용이니 새 시스템이 필요하다"까지는 말할 수 없음
- 말할 수 있는 것은 "**결제 시스템이 위임에 맞게 바뀌어야 한다**"까지임. 어느 길이 이길지, 둘이 나란히 갈지는 아직 모름

```text
[한국어]
  카드 시스템을 고쳐 쓰는 길             처음부터 Agent용으로 만든 새 시스템
  (비자 TAP, 마스터카드 Agent Pay)       (스테이블코인, x402, Nanopayments)
              |                                       |
              +----------->  서로 끌어들임  <---------+
                                  |
                 - 비자, 마스터카드가 x402 재단 회원임
                 - 비자가 카드 정산 일부를 스테이블코인으로 함
                                  |
                                  v
             어느 쪽이 이길지, 둘이 나란히 갈지 아직 모름
```

```text
[English]
  Adapting the card system               A new system built for Agents
  (Visa TAP, Mastercard Agent Pay)       (stablecoins, x402, Nanopayments)
              |                                       |
              +---------> pull each other in <--------+
                                  |
          - Visa and Mastercard are x402 Foundation members
          - Visa settles part of card payments in stablecoins
                                  |
                                  v
         Unknown which wins, or whether both run side by side
```

- 두 길은 따로 가지 않음. 카드 회사가 새 시스템에 들어가고, 새 시스템의 돈이 카드 정산에 쓰이고 있음
- 그래서 결론은 어느 한쪽이 아니라 "위임에 맞게 바뀌어야 함"까지임

## 7. 정리

- 정리: Agent Payment는 Agent(판단하는 프로그램)에게 사람의 결제 권한을 범위를 정해 맡기고, 돈을 받는 쪽이 그 위임을 믿을 수 있게 하는 기술임
- 앞으로 이야기될 것들
  - **판단의 정도**: 2.1절(Agent의 정의)은 판단을 Agent의 핵심으로 봄. 그런데 판단에도 정도가 있음. 사람이 상품과 가격을 정하고 Agent는 실행만 하는 경우와, 무엇을 살지까지 Agent가 정하는 경우는 필요한 위임 범위가 다름
  - **책임**: Agent가 받은 범위를 넘거나 잘못 판단한 결제는 누가 책임지는가. 맡긴 사람인가, Agent를 만든 회사인가, 결제를 처리한 회사인가
  - **어느 시장이 먼저인가**: 3.1절(흔한 오해)의 쿠팡 예는 소비자 구매임. 그런데 x402 보고서는 2028년까지 소비자 구매에서는 "건별 승인과 기존 체크아웃이 상당 부분 유지될 것"으로 보고, 분석을 기업 간 거래(B2B) 중심으로 했음([Four Pillars, "x402에 대한 모든 것"](https://research.4pillars.io/ko/research/all-about-x402), PDF 63쪽). 그렇다면 Agent Payment를 설명할 때 쿠팡 예보다 API나 데이터 구매 예가 더 맞을 수 있음
- 주의: 이렇게 Agent와 Agent Payment를 나눠서 말해도, 밖에서 둘을 섞어 쓴다면 그대로 받아들여야 함

```text
[한국어]
  Agent Payment
  =
  판단하는 프로그램에게 .................. <-- 판단의 정도: 어디까지 판단하는가
  사람의 결제 권한을 범위를 정해 맡기고 .. <-- 책임: 잘못된 결제는 누가 지는가
  받는 쪽이 그 위임을 믿을 수 있게 하는 기술

  이 기술이 먼저 쓰일 곳 ................. <-- 어느 시장이 먼저인가:
                                               소비자 구매인가, 기업 간 거래인가
```

```text
[English]
  Agent Payment
  =
  a technology that, for a program that judges, .....  <-- degree of judgment: how far does it judge?
  delegates a person's payment rights within a scope   <-- liability: who bears a wrong payment?
  and lets the payee trust that delegation

  Where this technology is used first ................ <-- which market comes first:
                                                           consumer purchases or B2B?
```

- 앞으로 이야기될 것들 가운데 둘은 정의 안에 걸림
- 판단의 정도는 "판단하는 프로그램"에, 책임은 "결제 권한을 범위를 정해 맡기는 일"에 걸림
- 어느 시장이 먼저인지는 정의 밖의 질문임. 이 기술이 어디서 먼저 쓰일지에 관한 것임
