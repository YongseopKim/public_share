# 2026/10/15 Research

**큰 질문: Arc 해커톤 참여는 우리에게 그만한 가치가 있는가?**

## 목차

- [2026/10/15 Research](#20261015-research)
  - [목차](#목차)
  - [조사/정리한 것](#조사정리한-것)
  - [저의 결론](#저의-결론)

## 조사/정리한 것

- 자세한 내용: [조사한 것](sources.md)
- [Circle의 사업](sources.md#circle의-사업-고객-제품-매출)
  - Circle의 고객: 금융기관, 기업, 개발자
  - Circle 제품 3축: Circle이 2분기 공시(10-Q)에서 스스로 나눈 세 기둥
    - Arc와 개발자, 상호운용 인프라: Arc, Agent Stack(Agent Wallets, Nanopayments, Agent Marketplace, Circle CLI), App Kits, Circle Wallets, Circle Contracts, CCTP, Gateway
      - 에이전트 제품(Agent Stack)은 Circle이 Arc 쪽 기둥에 넣었음
    - 디지털 자산과 유동성: USDC, EURC, USYC, cirBTC, Circle Mint, xReserve
    - 애플리케이션: CPN, StableFX. 공시 목록 밖의 제품 페이지에는 CPN Managed Payments, Refund Protocol도 있음
  - Circle의 매출 관련 두 목표:
    - 1. USDC 유통량을 늘려 준비금 수익을 키운다
    - 2. 준비금 수익이 아닌 매출을 늘린다
  - 기업들은 지급 결제 관련 문제를 느끼지만, 스테이블코인으로 옮긴 기업은 아직 적음(공개 조사들의 기업 응답). 다만 응답한 지급 사업자와 금융기관은 49%가 이미 지급에 스테이블코인을 씀
  - [줄별 근거](sources.md#circle의-사업의-근거)
- [Arc의 위치](sources.md#arc의-자리-arc에서만-얻는-것과-arc가-맡는-몫)
  - Circle 고객의 문제 가운데 해외 지급 문제는 크기가 측정되어 있음:
    - 중소기업 B2B 해외 지급의 평균 비용 1.6% 가운데 외환이 1.4%
    - 은행 도달 뒤 마지막 구간이 전체 지급 시간의 80% 넘게 차지함
  - 하지만, Arc가 맡는 몫은 문제마다 일부 구간뿐. Arc에서만 얻는 기능은 좁음:
    - USDC로 내는 가스비, 빠른 확정, StableFX의 정산 정도
    - CPN, App Kits, Agent Stack은 Arc 없이도 돌아감
    - 즉, 현재까지는 Circle의 솔루션들 가운데 Arc가 있어야만 돌아가는 것은 적음.
  - [줄별 근거](sources.md#arc의-위치의-근거)
- [Circle Agent Stacks](sources.md#circle-agent-stacks)
  - 결제 기능을 2026년 상반기에 출시
  - 제품
    - Agent Wallets: 에이전트가 USDC를 들고 쓰는 지갑. 사람이 정한 정책(기간별 지출 한도, 허용 목록과 차단 목록) 안에서만 돈을 씀
    - Agent Marketplace: 에이전트용 서비스를 찾고 비교해서 붙이는 곳. 서비스 이용을 구독과 수동 연동에서 쓴 만큼 내는 방식으로 옮기려는 것
    - Circle CLI: 터미널이나 에이전트의 작업 흐름에서 명령으로 지갑을 만들고, 정책을 정하고, 서비스를 찾고, 거래를 실행하는 도구
    - Nanopayments: Gateway 위에서 가스비 없이 1센트보다 작은 금액도 보내는 소액 결제. x402로 받고 모아서 한 번에 정산함
    - Circle Skills: AI 코딩 도구로 개발하는 사람을 위해 Circle이 쓴 구현 패턴. 출시 글은 Agent Stack 다섯 가운데 하나로 들지만, 2분기 10-Q의 Agent Stack 구성에는 없음
  - 이 제품들이 풀고자 하는 문제
    - 에이전트를 만드는 개발자와 API, 데이터를 파는 쪽의 문제
    - Circle의 주된 고객(은행, PSP, 기업, 기관)의 문제와 관련되어 있지 않음
  - 참고: 에이전트 매출의 상한은 전체 매출의 0.76%(에이전트 수수료가 들어갈 공시 항목 전체의 비율)
  - Circle의 현재 에이전트 전략
    - 목표는 스테이블코인 채택. 새 고객군들을 통해 USDC 유통량을 늘려 준비금 수익을 키우는 것
    - 외부의 다른 회사들과 별반 다르지 않은 행보
      - Circle의 기존 고객이 가진 지급 문제를 에이전트가 풀지 못함
      - Nanopayments는 기업의 문제를 푸는 것보다 USDC로 들어오는 새 수요를 만드는 것에 가까움. 그 방향이 틀렸다는 뜻은 아님
  - [줄별 근거](sources.md#circle-agent-stacks의-근거)
- [그외 AI나 Agent가 붙은 Circle/Arc 제품들](sources.md#그외-ai나-agent가-붙은-circlearc-제품들)
  - App Kits: 앱 안에서 실행 중에 쓰는 SDK. Arc 전용이 아님
  - Build with AI: 개발할 때 쓰는 도구 넷(Arc Studio, Arc Studio CLI, Skills, MCP server)
  - 에이전트와 닿는 곳은 결제 Skills
  - [줄별 근거](sources.md#그외-ai나-agent가-붙은-circlearc-제품들의-근거)
- [외부의 AI Agent 제품들](sources.md#외부의-ai-agent-제품들)
  - x402: 결제 협상 방식은 회사마다 같고, 정산 방식이 다름
  - 시장은 아직 작음: x402와 MPP를 합친 2026-08 한 달 금액이 \$643,721
  - Circle Agent Stack이 하는 일은 외부 제품에도 있음.
  - [줄별 근거](sources.md#외부의-ai-agent-제품들의-근거)

| 하는 일                      | Circle                                                                                     | 외부                                                                    |
| ---------------------------- | ------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------- |
| 에이전트 지갑과 지출 한도    | Agent Wallets                                                                              | Coinbase CDP Agentic Wallet, MetaMask Agent Wallet                      |
| 모아서 정산하는 소액 결제    | Nanopayments                                                                               | Coinbase CDP Facilitator(batch-settlement), MPP Sessions(Tempo, Stripe) |
| 결제 협상 방식               | x402                                                                                       | x402(Coinbase 등), MPP(카드 결제까지 다룸)                              |
| 사용자의 위임 증명           | 지갑 정책(사람이 정한 한도, 허용과 차단 목록). 사용자가 검토하는 위임 문서는 Arc가 설계 중 | Google AP2(사용자가 서명한 위임서)                                      |
| 돈을 받는 쪽의 에이전트 확인 | 하지 않음(고지문에 명시). Arc는 확인에 쓸 기록을 담는 등록부(ERC-8004)만 둠                | Visa Trusted Agent Protocol, Mastercard Agent Pay, Stripe Radar         |

- [Arc 해커톤들](sources.md#arc-해커톤들)
  - 에이전트를 내건 공고의 개발 문제는 대부분 소액 결제, 에이전트 상거래, 작은 사업체의 자금 관리. CPN, StableFX 같은 기관용 제품은 기업 금융 해커톤에서 다룸
    - 에이전트 공고 넷
      - Agentic Commerce on Arc(LabLab, 2026-01): 소액 상거래, 에이전트의 신원과 정책, 자율 구매와 판매
      - Agentic Economy on Arc(LabLab, 2026-04): API, 데이터, 모델 추론을 쓴 만큼 과금. Arc 정산, USDC, Nanopayments를 씀
      - Lepton Agents(Canteen, 2026-06~07): 유료 자원을 사는 에이전트, 건별 판매, 에이전트 사이의 지급, 콘텐츠 수익화
      - Tameion Agents(Canteen, 2026-09~10, 초대받은 사람만): 작은 사업체의 자금 관리(공고는 프리랜서와 두 사람 회사도 예로 듦), 송장, 지급과 수금, 거래 상대 심사
    - 기관용 제품은 Arc x Encode Enterprise & DeFi(2026-02, 현장 3일)에서 다룸. CPN, StableFX, USYC는 접근 허가가 필요한 기업 제품이라 미리 등록하라고 안내함
  - Circle/Arc만의 AI Agent Payment라고 볼 것이 없음. 에이전트 결제 자체(Nanopayments, x402 정산)는 있음
    - Tameion 사례: 에이전트 공고 넷 가운데 사업체의 자금 업무를 내건 것은 Tameion뿐. 실제 사업에서 쓴 기록도 요구함
      - 그래도 공고가 안내한 도구는 Agent Stack, Wallets, CCTP, Gateway 같은 개발자 도구이고, CPN과 StableFX는 공고에 나오지 않음
      - 환전도 StableFX가 아니라 App Kit의 Swap 예제로 안내함
      - 다만 Tameion의 대상은 작은 사업체여서, 기관용 제품이 없는 것은 대상이 달라서일 수도 있음
  - [줄별 근거](sources.md#arc-해커톤들의-근거)
- [외부 AI Agent Payment 관련 해커톤들](sources.md#외부-ai-agent-payment-관련-해커톤들)
  - 앞으로 열리는 행사 셋: TUM Blockchain & AI(10/30~31), ETHGlobal Mumbai(11/5~7), Agent Pay - MERGE Madrid(11/27~29)
    - 각 행사
      - TUM Blockchain & AI: 뮌헨 현장 30시간, 약 200명. 주제가 "Agentic Payments"
      - ETHGlobal Mumbai: 이더리움 쪽의 범용 해커톤. 상금은 후원사 12곳이 각자 걸었고, Arc도 그중 하나(\$15,000)
      - Agent Pay - MERGE Madrid: 마드리드 현장 48시간. 주제는 Agent Commerce와 Agent Micropayments이고, 핀테크, 기업, 기관 쪽 청중이 함께 있음
  - 이미 열렸거나 신청이 닫힌 행사
    - Cronos x402 PayTech(결과 발표 2026-02): Cronos 체인의 x402 결제 앱 행사. 191개 제출
    - Claw & Order: CKB AI Agent Hackathon(2026-03): CKB 체인 위의 에이전트 행사. 1위는 마일스톤마다 돈을 풀어 주는 에스크로와 지급 시스템
    - Agentic Dollars on Bitcoin(토리노, 10/17~18, 신청 마감): 비트코인 위의 달러로 하는 에이전트 결제. RGB와 QVAC를 반드시 써야 함
  - [줄별 근거](sources.md#외부-ai-agent-payment-관련-해커톤들의-근거)

## 저의 결론

- 우리가 어떤 것에 가치를 크게 두는지에 따라 결정이 달라진다. 따라서, 우리가 해야 할 것은 무엇에 가치를 두느냐를 결정하는 것
- 지금까지 본 것 기반으로 중요 가치 대상들을 정리함

- Circle
  - 정의: 기업 지급 결제의 문제와, 그것을 풀려는 Circle의 방향과 제품에 강한 확신을 가지는 경우 고려해야 할 대상
  - 기업 지급 결제의 문제 세 가지
    - 지급 지시와 실행: 지급 지시가 진짜인지, 승인한 대로 실행되는지
    - 수납 이후의 정산과 고객자금: 판매자에게 돈이 도착하는지, 장부가 실제 돈과 맞는지
    - 국경을 넘는 지급: 송금을 요청해도 상대방이 대금을 받을 수 있는지
  - Circle의 방향:
    - 기업과 금융기관이 디지털 자산에 접근하고, 보관하고, 교환하고, 이동하는 기능을 연결
      - 접근: Circle Mint (은행 자금과 USDC, EURC를 서로 바꿈)
      - 보관: Circle Wallets (지급 요청, 서명 승인, 키 관리)
      - 교환: StableFX (기관끼리의 환전)
      - 이동: CCTP (체인 사이의 이전), Gateway (여러 체인의 USDC를 한 잔액으로 다룸), CPN (국경을 넘는 지급과 수납)
    - 기업 업무로는 지급, 외환, 자금 관리
      - 지급: CPN, CPN Managed Payments (Circle이 보관, 준법 처리, 온체인 운영을 대신 맡음)
      - 외환: StableFX, EURC
      - 자금 관리: USYC (토큰화한 머니마켓 펀드), Gateway, Circle Mint
  - 기회: 국내에 Circle 전문가가 없음
  - 제 개인적 판단
    - Circle의 현재 상태와 하려는 것의 방향은 잘 가고 있음
      - 문제 세 가지 가운데 국경을 넘는 지급은 실제로 크고, 크기가 측정되어 있음: 해외 지급 비용 1.6% 가운데 외환이 1.4%, 마지막 구간이 지급 시간의 80% 넘게 차지
      - Circle의 애플리케이션(CPN, StableFX)이 이 문제(해외 지급과 환전)를 직접 겨냥함
      - 다만 스테이블코인으로 옮긴 기업은 아직 적음
    - Circle의 에이전트 쪽: 현재 상태와 하려는 것의 방향에 물음표가 남음
      - Agent Stack의 방향:
        - Circle은 에이전트가 결제하는 기능(상반기 출시)에서 에이전트가 일을 팔아 버는 기능(하반기 계획)으로 가려 함. 2Q 발표 "from agent payment rail to agent labor market"
        - 이 방향은 기존 고객과 제품의 문제를 푸는 쪽이 아님
      - Nanopayments: Circle만의 엣지인가? No
      - Nanopayments: Circle이 해결하려는 문제와 해결 방법에 맞닿아 있는가? No
      - Circle만이 그리는 AI Agent 청사진이 있는가? No
    - 제가 그리는 쪽: Circle이 이미 가진 제품(CPN, Managed Payments, StableFX, App Kits)에 에이전트가 들어가는 것
      - but, not yet
      - 실망스럽긴함. 타기업과 비교했을 때 기대되는게 없음
  - 중요 가치로 판단시
    - Arc 행사 가운데 Circle 제품(CPN, StableFX 등)을 다루는 행사에 참여해야 함
  - [줄별 근거](sources.md#circle의-근거)
- Arc
  - 정의: 기관 금융을 위한 정산 네트워크인 Arc 네트워크에 대한 강한 확신을 가지는 경우 고려해야 할 대상
  - Circle과의 관계: Arc가 해결하는 것은 Circle이 원래 해결하려던 것의 일부
    - Circle은 Arc를 자사 애플리케이션의 조정을 위한 기반으로 만들려는 방향을 제시
    - 전체 제품군에서 Arc의 몫은 일부: 자산 이전과 계약 실행 결과를 처리하고 기록을 확정
  - Circle과 떼어 Arc만 고를 수도 있음: Arc는 Circle 제품의 기반이면서, 따로 토큰과 지분으로 값을 얻는 사업이기 때문
  - 기회: 국내에 Arc 전문가가 없음
    - Arc Architect가 된다면, 에어드롭 가능성이 있음
  - 제 개인적 판단
    - 조사하면 할수록 깨닫는 것은, 생각보다 Arc 자체가 Circle 안에서 큰 영향력을 갖지 않음
    - 하지만, 그것은 Circle이 뉴욕증권거래소(NYSE)에 상장된 나름 거대(?) 기업이라는 것을 감안할 때는 그게 오히려 맞음
    - Arc 자체는 Circle 기업의 입장에서는 잘 되면 정말 좋은, 나쁠 것 없는 아이템
    - 하지만 Agent 라는 눈으로 봤을 때 Arc만의 것은 아직 없음. Arc만의 에이전트 관련 무언가는 현재 설계나 로드맵 단계
    - Arc 라는 메인넷과 Arc House 라는 곳에서의 활약이 낫다고 판단되면 나쁠 것 없음
    - 물론 이 안에는 메인넷의 폭발적 성장과 토큰 가치의 폭등 그리고 에어드롭의 가능성이 있어야만 현실적으로 좋은 옵션이 됨
  - 중요 가치로 판단시
    - 굳이 AI agent 에 목매지 말고, 모든 Arc 행사에 참여해야 함
  - [줄별 근거](sources.md#arc의-근거)
- AI Agent Payment
  - 정의:
    - 에이전트가 돈을 내고 받는 일 자체(기업의 지급 결제 문제가 포함되겠지만, 그것으로 범위를 좁혀서 생각하는 게 아닌)에 확신을 가지는 경우 고려해야 할 대상
    - 따라서, 어느 회사의 제품 위에서 Agent Payment 관련 작업을 하든 상관없음
  - 지금 상황:
    - 시장은 아직 작음: x402와 MPP를 합친 2026-08 한 달 금액이 \$643,721
    - 카드사와 결제 회사도 관련 제품을 내놓고 있음: Visa Trusted Agent Protocol, Mastercard Agent Pay, Stripe Radar, Google AP2, Coinbase CDP
    - 결제 협상 방식(x402)은 회사마다 같고, 정산(settlement) 방식이 다름
    - 이 부분이 Circle의 매출로 이어지는지는 지금 판단할 수 없음
  - 기회: AI Agent 자체가 태동되는 시기여서, 결제 관련 제품은 나오고 있지만 실제로 쓰이는 결제는 아직 작음
  - 제 개인적 판단
    - 현재 상태로는 사실 맨땅에 해당하는 그런 영역
    - 유즈 케이스에 대해 계속 주장해야되며,
    - 어떤 기술 스택이 부족한지를 유즈 케이스를 상상하며 직접 진행해야 함
    - Circle/Arc 말고도 실제 이것에 대한 고려를 하는 것은 오히려 Visa/Master/Stripe 등 실제 결제 담당자들이기 때문에 오히려 이쪽으로 우회하는게 더 나을수도 있음
  - 중요 가치로 판단시
    - Circle/Arc 행사에 묶이지 말고, 외부 AI Agent Payment 행사까지 나가야 함
  - [줄별 근거](sources.md#ai-agent-payment의-근거)
- AI Agent
  - 정의:
    - 에이전트가 사람을 대신해 많은 업무를 자동화하고 판정까지 맡는 방향에 대한 확신을 가지는 경우 고려해야 할 대상
    - 이 안에 Agent Payment가 포함될 수 있음. 하지만, Circle이나 Arc에 묶이지 않음
  - 지금 상황:
    - Arc 밖에도 에이전트 해커톤이 열림: TUM Blockchain & AI(10/30~31), ETHGlobal Mumbai(11/5~7), Agent Pay - MERGE Madrid(11/27~29)
    - 다만 상금은 대부분 특정 체인이나 회사의 것: TUM은 공개된 상금 전부가 BSV와 Cardano 트랙이고, ETHGlobal은 상금 12개가 모두 후원사 상금임
  - 기회: 태동하고 있으며 이미 진행 중. 아직도 폭발적 성장의 가능성은 있음
  - 제 개인적 판단
    - 가장 무난하다고 할 수 있음. 그런데 이걸 또한 질문해봐야 함
    - CURG는 블록체인 학회인데 그냥 AI Agent라면 이게 어떤 의미를 갖는지 고민해야 함
    - 물론 이것을 선택하고 Agent Payment 틈틈이 할 수 있음
    - 그것은 우리의 자유
  - 중요 가치로 판단시
    - Circle/Arc 행사에 묶이지 말고, 외부 AI Agent 행사까지 나가야 함
  - [줄별 근거](sources.md#ai-agent의-근거)
