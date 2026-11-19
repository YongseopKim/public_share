# 근거 자료: Arc 해커톤 참여 판단 (2026/10/15)

> - 공개판(public.md)의 근거를 모은 문서. 2026-10-15에 research.md의 내용을 이 문서로 옮기고, 공개판의 줄마다 근거를 붙임. 공개판의 소제목마다 붙은 "줄별 근거" 링크가 이 문서 끝의 두 절로 이어짐
> - 근거는 둘 가운데 하나를 가리킴: 외부 주소, 또는 `sources/` 안의 문서
>   - `sources/`의 문서: vault 안의 문서를 통째로 복사하고 저장소 안의 링크를 지운 것. 줄 수가 원래 문서와 같아서 이 문서가 적은 행 번호가 그대로 맞음. 파일마다의 원래 위치와 커밋 검사에 맞춰 고친 줄은 [sources/README.md](sources/README.md)에 있음
>   - 원래 문서가 다시 인용한 원문(공시, 보고서, 공고 등)의 행 번호는 vault에 받아 둔 사본의 행 번호여서, `sources/` 안에서는 따라갈 수 없음. 원문은 외부 주소로 확인
> - "조사/정리한 것" 절들: 절 이름은 사용자가 그린 얼개 그대로. 다만 "Circle의 사업"과 "Arc의 자리" 두 절은 에이전트가 더함. 그 아래 내용은 에이전트가 채우고 사용자가 고침
> - "조사/정리한 것의 근거"와 "저의 결론의 근거" 두 절: 공개판의 줄과 근거를 짝지은 것은 에이전트
> - 판단의 주인: "우리 판단"은 사용자의 판단. "N번 답 작성 에이전트의 판단"은 그 답을 쓴 에이전트의 판단

## 목차

- [근거 자료: Arc 해커톤 참여 판단 (2026/10/15)](#근거-자료-arc-해커톤-참여-판단-20261015)
  - [목차](#목차)
  - [Circle의 사업: 고객, 제품, 매출](#circle의-사업-고객-제품-매출)
  - [Arc의 자리: Arc에서만 얻는 것과 Arc가 맡는 몫](#arc의-자리-arc에서만-얻는-것과-arc가-맡는-몫)
  - [Circle Agent Stacks](#circle-agent-stacks)
  - [그외 AI나 Agent가 붙은 Circle/Arc 제품들](#그외-ai나-agent가-붙은-circlearc-제품들)
  - [외부의 AI Agent 제품들](#외부의-ai-agent-제품들)
  - [Arc 해커톤들](#arc-해커톤들)
  - [외부 AI Agent Payment 관련 해커톤들](#외부-ai-agent-payment-관련-해커톤들)
  - [저번주에 조사한 자료들](#저번주에-조사한-자료들)
  - [조사/정리한 것의 근거](#조사정리한-것의-근거)
  - [저의 결론의 근거](#저의-결론의-근거)

## Circle의 사업: 고객, 제품, 매출

- 자료: [1번 답](sources/q1-answer.md), [6번 답](sources/q6-answer.md). 아래 그림과 표는 두 답을 쓴 에이전트가 만든 것
- 전체 지도 ([q1-answer.md](sources/q1-answer.md) 115-136행)
  - 준비금 수익과 기타 매출의 비율은 1번 답 나 절(회사의 문제), 토큰 사전판매는 라 절(Arc와 회사의 문제)에 근거가 있음

```text
고객에서 회사의 매출까지, 그리고 Arc의 자리

  고객
  금융기관, 기업, 개발자
     |
     | 쓴다
     v
  제품: 세 기둥
  (i) Arc와 개발자 인프라  (ii) 스테이블코인과 유동성  (iii) CPN, StableFX
     |
     +--- 유통량을 늘린다 ---> USDC 유통량
     |                            |
     |                            | x 수익률 (SOFR에 가까운 단기 금리)
     |                            v
     |                         준비금 수익: 매출의 95.2%
     |
     +--- 직접 번다 --------> 기타 매출: 매출의 4.8-5.4%

  Arc의 자리
    고객에게: 해외 지급 경로 가운데 기관 사이 전송 한 구간
    회사에게: 토큰 사전판매 약 2.42억 달러, 한 번 들어오는 돈
```

- Circle이 말하는 고객과 제품 ([q1-answer.md](sources/q1-answer.md) 250-262행)
  - 기준: 공시와 Circle 글의 제품 기준. 공개판 "저의 결론"의 Circle은 기업 업무 기준([외부 공유 자료 목차](sources/circle-arc-public-material-outline.md)의 문제 셋)이어서 나누는 방식이 다름
  - "겨냥하는 문제" 칸은 1번 답을 쓴 에이전트가 붙인 말. 다만 CPN, StableFX, Agent Stack은 공시가 목적을 직접 적음 ([q1-answer.md](sources/q1-answer.md) 262행)
  - 근거 칸: 1번 답이 줄여 쓴 이름(survey, kit)을 그 문서로 풀어 적음 ([q1-answer.md](sources/q1-answer.md) 1203, 1205행)

| 고객                               | 겨냥하는 문제                                                 | 제품                    | 근거                                                                                                                                       |
| ---------------------------------- | ------------------------------------------------------------- | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| 은행, PSP, 기업                    | 해외 송금                                                     | CPN                     | [공시] "move money using stablecoins starting with cross-border payments" ([survey](sources/circle-company-survey-answer.md) 1125행)       |
| 블록체인을 직접 다루기 어려운 기업 | 스테이블코인 운영 부담                                        | Managed Payments        | [Circle 글] Circle이 전환, 지갑, 유동성, 규제 준수를 맡습니다 ([survey](sources/circle-company-survey-answer.md) 1143행)                   |
| 기관                               | 환전할 때 상대방마다 계약과 신용 한도를 따로 정해야 하는 부담 | StableFX                | [공시] ([survey](sources/circle-company-survey-answer.md) 1186행)                                                                          |
| 앱 개발자                          | 결제와 이동 기능을 직접 구현하는 부담                         | App Kits 등 개발자 도구 | 메인넷을 지원하며 Arc 전용이 아닙니다 ([kit](sources/arc-app-kit-vs-build-ai-guide.md) 124행)                                              |
| 에이전트를 만드는 개발자           | 에이전트가 독립된 경제 주체로 움직일 수단                     | Agent Stack             | [공시] ([survey](sources/circle-company-survey-answer.md) 1216행)                                                                          |

- 회사의 두 목표와 세 갈래: 회사 자료가 말하는 연결 ([q6-answer.md](sources/q6-answer.md) 228-253행)

```text
목표 1. USDC 유통량을 늘려 준비금 수익을 키운다

  A. 기관 금융 정산(CPN)    B. Arc 네트워크 사업      C. 에이전트
            |                         |                    |
            +------------+------------+                    |
                         v                                 v
          다른 회사가 그 위에 제품을 만든다        스테이블코인 채택
                         |                                 |
                         +----------------+----------------+
                                          v
                        Circle 자산 수요 증가(USDC 유통량 증가)
                                          |
                                          v
                                   준비금 수익 증가

목표 2. 매출 구성을 다변화한다(준비금 수익이 아닌 매출)

  A. 기관 금융 정산      --> CPN 수익화
  B. Arc 네트워크 사업   --> ARC 토큰 사전판매, 스테이킹, 거래 수수료, 제휴
  C. 에이전트            --> 프로토콜 자체의 매출("some")
```

- 고객이 느끼는 중요도: 문제는 느끼지만, 스테이블코인으로 옮긴 기업은 아직 적음 (1번 답 작성 에이전트의 판단, 확신도 중간. [q1-answer.md](sources/q1-answer.md) 797-812행)
  - 자료: 공개 조사 여덟 건 ([조사 묶음의 목록](sources/corporate-stablecoin-demand-surveys-README.md))
  - 응답자를 돈을 내는 기업과, 지급 사업자 및 금융기관으로 나눔. 이 구분은 1번 답을 쓴 에이전트가 정함. 두 집단의 답이 크게 달라서 나눔
  - 위치 칸: 각 조사의 공개 주소. 행 번호는 vault에 받아 둔 사본의 것이어서 뺐고, 1번 답의 같은 표에 남아 있음 ([q1-answer.md](sources/q1-answer.md) 797-812행)

| 무엇을 보는가          | 조사(응답자, 조사 시기)                                                  | 내용                                                                                                                                                                                                                                                                    | 위치                                       |
| ---------------------- | ------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| 기업이 겪는 문제       | Rapyd(6개국 중대형 B2B 기업 715곳, 2023년 2월)                           | 해외 지급에 건당 10달러 이상의 수수료를 내는 곳이 76%, 5일 이상의 지연을 겪은 곳이 38%입니다.                                                                                                                                                                           | [rapyd](https://www.rapyd.net/company/news/press-releases/cross-border-businesses-focus-on-expansion-but-common-payment-challenges-curb-growth/)                             |
| 기업의 관심            | EY-Parthenon(기업 250곳과 금융기관 100곳의 의사결정자, 2025년 6월)       | 앞으로 5년간 가장 관심 있는 용도는 해외 공급사 지급(77%)이고, 관심 이유는 거래 비용 절감(52%)과 빠른 해외 지급(45%)입니다. 이용자의 41%가 "cost savings of at least 10%, primarily in B2B cross-border payments using USD-denominated stablecoins"를 보고했습니다.      | [ey](https://www.ey.com/en_us/insights/financial-services/cost-savings-and-speed-drive-stablecoin-adoption)                         |
| 기업의 관심            | Deloitte(북미 매출 10억 달러 이상 기업의 CFO 200명, 2025년 6월)          | 스테이블코인 도입 동기로 고객 개인정보 보호(45%)와 더 효율적인 해외 거래(39%)를 꼽았습니다.                                                                                                                                                                             | [deloitte](https://www.deloitte.com/us/en/about/press-room/cfo-signals-survey-north-american-cfos-anticipate-significant-uptick-in-corporate-cryptocurrency-adoption-2027.html)                             |
| 기업의 실제 이용       | EY-Parthenon                                                             | 이용률은 13%이고, 금융기관이 23%, 기업이 9%입니다.                                                                                                                                                                                                                      | [ey](https://www.ey.com/en_us/insights/financial-services/cost-savings-and-speed-drive-stablecoin-adoption)                                   |
| 기업의 실제 이용       | AFP(미국 재무 담당자 309명, 2026년 3월)                                  | 스테이블코인과 토큰화 상품은 "only 1% are piloting or using them in a limited capacity, while 9% are actively exploring the technology"입니다.                                                                                                                          | [afp](https://www.financialprofessionals.org/about/learn-more/press-releases/Details/afp-survey-finds-stablecoins-remain-peripheral-to-liquidity-strategies-as-cash-reserves-rise)                                   |
| 기업의 실제 이용       | PYMNTS(미국 중견기업 CFO 60명, 2026년 1월)                               | 이용 13%, 검토한 적 없음 58%입니다. 3년 안에 스테이블코인이 "even somewhat important"해질 것이라고 본 CFO는 4분의 1이 안 됩니다.                                                                                                                                        | [pymnts-waiting](https://www.pymnts.com/study_posts/waiting-for-certainty-why-most-cfos-are-holding-back-on-crypto-and-stablecoins/)                    |
| 도입을 가르는 조건     | PYMNTS                                                                   | 도움이 될 것으로 대형 은행과의 연동(45%)과 규제 명확성(40%)을 꼽았고, 빠른 정산과 유동성 개선은 25%, 비용 절감은 22%였습니다. 보고서는 "The issue is thus about trust, not efficiency or cost"라고 적습니다. 걸림돌은 규제 불확실성(67%)과 기존 시스템 연동(43%)입니다. | [pymnts-waiting](https://www.pymnts.com/study_posts/waiting-for-certainty-why-most-cfos-are-holding-back-on-crypto-and-stablecoins/), [pymnts-promise](https://www.pymnts.com/study_posts/stablecoins-gain-ground-why-cfos-see-more-promise-there-than-in-crypto/)   |
| 도입을 가르는 조건     | EY-Parthenon                                                             | 걸림돌 1위는 규제 불확실성(73%), 2위는 회계와 세무 처리(38%)입니다. ERP 연동이 있으면 더 도입하겠다는 기업이 70%입니다.                                                                                                                                                 | [ey](https://www.ey.com/en_us/insights/financial-services/cost-savings-and-speed-drive-stablecoin-adoption)                              |
| 받은 뒤 하는 일        | EY-Parthenon, PYMNTS                                                     | 기업의 79%가 거래 직후 법정화폐로 바꾸고(EY), 받은 스테이블코인의 88%를 바로 달러로 바꿉니다(PYMNTS).                                                                                                                                                                   | [ey](https://www.ey.com/en_us/insights/financial-services/cost-savings-and-speed-drive-stablecoin-adoption), [pymnts-waiting](https://www.pymnts.com/study_posts/waiting-for-certainty-why-most-cfos-are-holding-back-on-crypto-and-stablecoins/)              |
| 지급 사업자와 금융기관 | Fireblocks(은행, 결제 사업자, 핀테크, 암호화폐 사업자 295명, 2025년 3월) | 49%가 지급에 스테이블코인을 쓰고 있습니다. 이점은 빠른 정산(48%)이 1위이고 비용 절감(30%)이 가장 낮습니다. 같은 조사의 보도자료는 비용 절감을 32%로 적습니다.                                                                                                           | [fireblocks-pr](https://seekingalpha.com/pr/20106152-fireblocks-report-stablecoins-move-from-experiment-to-production-with-revenue-growth-as-top), [fireblocks](https://www.fireblocks.com/report/state-of-stablecoin) |

- 공개판의 "Circle 제품 3축"과 매출 목표가 기대는 원문 (2026-10-15에 모은 것. 원문 인용 안의 긴 대시와 둥근 따옴표는 ASCII로 바꿔 적음)
  - Circle은 사업을 세 기둥으로 나눔: [2026년 2분기 10-Q](https://d18rn0p25nwr6d.cloudfront.net/CIK-0001876042/ea208256-f5a3-44b0-b51e-845285336f68.pdf)의 "Our business is organized around three reinforcing pillars: (i) Arc, an open Layer-1 blockchain network and related developer/interoperability infrastructure; (ii) Circle Digital Assets and Services, including USDC, EURC, USYC, cirBTC, and related liquidity infrastructure such as Circle Mint and xReserve; and (iii) Circle Applications, including products like CPN and StableFX that deliver real-world utility on Arc and across a multichain ecosystem."
  - 기둥마다 들어가는 제품: [같은 10-Q](https://d18rn0p25nwr6d.cloudfront.net/CIK-0001876042/ea208256-f5a3-44b0-b51e-845285336f68.pdf)
    - 첫째 기둥: "Arc is our open, Layer-1 blockchain ... supported by our Agent Stack (consisting of Agent Wallets, Nanopayments, Agent Marketplace and Circle CLI), core developer services (including App Kits, Circle Wallets and Circle Contracts) and interoperability services (including CCTP and Gateway)"
    - 둘째 기둥: "Circle Mint and xReserve provide institutional liquidity and trust infrastructure for Circle Digital Assets"
    - 셋째 기둥: "Our application-layer products build on Circle Digital Assets and Arc to deliver practical utility, including CPN ... and StableFX"
  - 10-Q 목록 밖의 애플리케이션 둘
    - [CPN Managed Payments 문서](https://developers.circle.com/cpn/managed-payments.md): "CPN Managed Payments gives partners stablecoin settlement without needing in-house custody, compliance, or onchain systems."
    - [Refund Protocol 글](https://www.circle.com/blog/refund-protocol-non-custodial-dispute-resolution-for-stablecoin-payments): "Stablecoin payments, however, have no refund or chargeback mechanisms."
  - 에이전트가 매출에 닿는 길, CEO의 말: [2026년 2분기 실적 발표 통화(2026-08-05) 녹취](https://s206.q4cdn.com/265218871/files/doc_earnings/2026/q2/transcript/Q226-Earnings-Transcript.pdf), Jeremy Allaire의 "So we see the agentic stack as driving some revenue around the protocols themselves, but fundamentally driving stablecoin adoption, which drives revenue and driving Arc infrastructure adoption, which drives revenue as well."
  - 에이전트 매출의 상한 0.76%: [같은 10-Q](https://d18rn0p25nwr6d.cloudfront.net/CIK-0001876042/ea208256-f5a3-44b0-b51e-845285336f68.pdf)
    - 원문: "Transaction revenue 5,330"(2026년 2분기, 천 달러), "Total revenue and reserve income \$ 701,315"
    - Transaction revenue의 정의: "Transaction revenue is generated from usage-based, volume-based, or event-driven transactions. This includes fees associated with the redemption of Circle stablecoins and USYC, blockchain rewards revenue and use of Circle infrastructure in facilitating digital asset transactions (including CCTP)."
    - 계산: 5,330 / 701,315 = 0.76%
    - 에이전트 결제 수수료가 공시에 잡힌다면 사용량 기반 수수료인 이 항목에 들어갈 것으로 봄. 공시가 적은 것이 아니라 추정. 이 항목 안에서 에이전트 몫은 따로 밝히지 않으므로 0.76%는 에이전트 매출이 아니라 그 상한
    - 이 항목은 1분기 673만 달러에서 2분기 533만 달러로 줄었음(상반기 1,206만 달러에서 2분기 533만 달러를 뺀 값이 1분기). 같은 판단: [q6-answer.md](sources/q6-answer.md) 64행

## Arc의 자리: Arc에서만 얻는 것과 Arc가 맡는 몫

- 자료: [1번 답](sources/q1-answer.md) 다 절(Arc와 고객의 문제, [q1-answer.md](sources/q1-answer.md) 550-795행). 아래 그림과 표는 1번 답을 쓴 에이전트가 만든 것
- Arc에서만 얻는 기능은 좁음 (1번 답 작성 에이전트의 판단, 확신도 중간)
  - 기능의 범위에 대한 판단. 고객 문제의 무게에 대한 판단이 아님
  - 공시에 적힌 Arc의 설계 다섯: 가스비를 스테이블코인으로 냄, 검증자는 허가받은 기관, 1초 안에 확정, 거래를 비공개로 설정 가능, 운영과 거버넌스를 넓게 나눔 ([circle-company-survey-answer.md](sources/circle-company-survey-answer.md) 992-997행)
  - Circle의 다른 제품은 대부분 Arc 없이도 돌아감
    - CPN: 환경 문서가 Ethereum, Polygon, Solana를 예로 듦 ([arc-section-02-why-understanding.md](sources/arc-section-02-why-understanding.md) 305행). 공식 지원 체인 문서도 Arc, Ethereum, Polygon PoS, Solana를 함께 나열 ([arc-section-04-business.md](sources/arc-section-04-business.md) 1161행)
    - App Kits: Arc 전용이 아님("not just Arc", [arc-app-kit-vs-build-ai-guide.md](sources/arc-app-kit-vs-build-ai-guide.md) 124행)
    - Agent Stack: Arc 없이도 동작. Arc 메인넷 지원은 2026-09-16에야 추가 ([circle-arc-agent-products-guide.md](sources/circle-arc-agent-products-guide.md) 210행)
    - 공시도 애플리케이션이 여러 블록체인에서 쓰인다고 적음 ([circle-company-survey-answer.md](sources/circle-company-survey-answer.md) 443행)
  - 반대로 StableFX는 Arc 위에서 돌아간다고 공시에 적힘 (같은 문서 1184행)
  - 따라서 지금 고객이 Arc에서만 얻는 기능: USDC로 내는 가스비, 빠른 확정, StableFX의 정산 장소 정도
- 문제의 무게 자체는 무거움 (1번 답 작성 에이전트의 판단, 확신도 높음. [q1-answer.md](sources/q1-answer.md) 567-577행)
  - FSB 2025: 중소기업 B2B 해외 지급의 평균 비용 1.6%, 그 가운데 외환이 1.4%(87.1%) ([FSB 2025 보고서](https://www.fsb.org/uploads/P091025-1.pdf))
  - SWIFT: 은행에 도달한 뒤의 마지막 구간이 전체 지급 시간의 "over 80%" ([SWIFT 안내](https://www.swift.com/payments/how-long-does-swift-payment-take))
  - BIS 2026: 외환 결제의 "10%, or \$1.4 trillion, remained exposed" ([BIS 분기 보고서 2026년 6월호](https://www.bis.org/publ/qtrpdf/r_qt2606c.htm))
- Arc가 맡는 몫: 문제마다 일부 구간에만 닿음 (확신도 중간. [q1-answer.md](sources/q1-answer.md) 579-589행)
  - 연구 원고 04(사업 이해)가 문제마다 "Arc가 맡는 부분"과 "해결되지 않고 남는 것"을 나란히 둠 ([arc-section-04-business.md](sources/arc-section-04-business.md) 1107-1127행). 원고는 제품 설명 열이 효과를 측정한 결과가 아니라고 스스로 밝힘 (같은 원고 1107행)
  - 처리 시간: Arc는 기관 사이의 전송을 확정. 남는 것은 "은행 도달 뒤 고객 계좌 입금까지의 구간" (같은 원고 1112행). 위 SWIFT 자료에서 이 구간이 전체 시간의 80% 넘게 차지
  - 지급 비용: Arc가 맡는 것은 체인 실행의 가스비. 남는 것은 외환 가격이고 FSB 예시에서 그 몫은 87.1% (같은 원고 1113행)
    - FSB의 외환 비용은 환율 자체가 아니라 은행 간 환율 위에 얹은 몫. Arc에서 정산하는 StableFX가 이 몫을 겨냥함 (아래 그림 9)
  - 자금 배치: 미리 두는 자금을 줄이는 것은 CPN의 기능. Arc는 CPN이 지원하는 체인 가운데 하나 (같은 원고 1111행)
  - 상대국의 달러 부족: Arc가 맡는 부분은 "없다" (같은 원고 1126행)
  - 예외는 외환의 상대방 위험: StableFX의 `FxEscrow` 계약은 Arc에서 실행되고, 두 통화를 함께 인도하거나 둘 다 인도하지 않음 (같은 원고 1114행). 위 BIS 자료의 PvP(두 통화를 동시에 주고받는 결제) 접근 문제와 같은 종류의 위험을 겨냥. 다만 BIS의 비율은 StableFX의 효과를 잰 값이 아님
- 그림 7은 아래 그림 8, 9, 10의 지도(번호는 1번 답의 그림 번호를 그대로 씀). 그림 8, 9, 10이 문제의 종류(시간, 비용, 위험과 자금)마다 하나씩 자세히 봄 ([q1-answer.md](sources/q1-answer.md) 591-780행)

```text
그림 7. 해외 지급의 문제와 Arc의 몫: 그림 8, 9, 10의 지도

  문제                측정된 크기                              Arc의 몫                              그림
  --------------------------------------------------------------------------------------------------------
  시간                마지막 구간이 전체 시간의 80% 넘게 차지  일부                                  8
  비용                평균 1.6% 가운데 외환이 1.4%(87.1%)      가스비는 작음, 외환은 StableFX로 간접  9
  외환 결제 위험      외환 결제의 10%, 1.4조 달러가 노출       일부                                  10
  미리 둔 자금        여러 통화로 미리 쌓아 둠                 간접                                  10
  상대국의 달러 부족  -                                        없음                                  10
```

```text
그림 8. 시간: 지급 한 건이 지나는 두 구간

  송금 은행
     |
     |  [1] 기관 사이 전송
     |      지금: SWIFT 지급의 75%가 10분 안에 수취 은행에 도달
     |            평균으로 전체 지급 시간의 20% 미만
     |      Arc: 이 구간을 맡는다 (1초 안의 확정)
     v
  수취 은행
     |
     |  [2] 마지막 구간: 고객 계좌 입금
     |      지금: 전체 지급 시간의 80% 넘게 차지
     |      Arc: 없음
     v
  수취 기업 계좌

  전체 지급 시간을 100으로 놓으면 (SWIFT 측정, 평균)
  |<--- 20 미만 --->|<------------------ 80 넘게 ------------------>|
   [1] 기관 사이 전송      [2] 마지막 구간

  전체 결과: B2B 지급의 45% 미만이 영업일 하루 안에 결제 (FSB 2025)
```

```text
그림 9. 비용: 평균 1.6%의 구성과 Arc가 닿는 두 길

  중소기업 B2B 해외 지급의 평균 비용 1.6% (FSB 2025, 2만 달러 지급 기준)

  |############################################|######|
  |<----------- 외환 1.4% (87.1%) ------------>|수수료|
                        ^                       0.2%
                        |                         ^
                        |                         |
                        |                        (1) Arc의 가스비가 들어갈 수 있는 자리
                        |                            FSB가 잰 기존 지급의 수수료이고,
                        |                            가스비가 그중 얼마를 대신하는지는 미측정
                        |
                       (2) Arc에서 정산하는 StableFX가 줄일 수 있는 자리
                           가격은 여러 공급자가 체인 밖에서 정하고, Arc는 정산만 맡음
                           StableFX의 가격과 수수료는 공개되지 않음

  외환 1.4%: 지급에 적용한 환율과 은행 간 환율의 차이(FSB의 정의)
             통화를 바꾸는 값 자체가 아니라, 그 위에 얹은 몫
```

```text
그림 10. 위험과 자금: 문제에서 제품을 거쳐 Arc까지

  문제                      이 문제에 닿는 Circle 제품             그 제품과 Arc
  -----------------------------------------------------------------------------------------------
  외환 결제 위험       ---> StableFX의 FxEscrow               ---> Arc 위에서 실행
  10%, 1.4조 달러 노출      두 통화를 함께 주거나 둘 다 안 줌
  미리 둔 자금         ---> CPN                               ---> Arc는 지원 체인 넷 가운데 하나
  여러 통화로 쌓아 둠
  상대국의 달러 부족   ---> 없음                                   -
```

## Circle Agent Stacks

- 구성: 에이전트용 지갑(Agent Wallets), CLI, Agent Marketplace, x402 결제, 가스비 없는 소액 이체(Gateway 위의 Nanopayments) ([3번 답](sources/q3-answer.md) 177-178행)
  - 별도로, 에이전트가 Circle API를 바로 쓰게 하는 skills 라이브러리와 MCP 서버가 4분기 실적 발표에서 언급됨 ([q3-answer.md](sources/q3-answer.md) 63행)
- 출시 상태: 2분기 발표 자료 18쪽의 "from agent payment rail to agent labor market" ([q3-answer.md](sources/q3-answer.md) 266-300행)
  - 결제하는 기능은 상반기에 출시, 버는 기능은 하반기에 짓는 중

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
```

- 지금 푸는 문제: 두 가지 ([q3-answer.md](sources/q3-answer.md) 38-41행)
  - 에이전트를 만드는 개발자: 개인 키를 코드에 넣거나 사람용 계정과 수동 승인에 기대야 했던 문제
  - API와 데이터를 파는 쪽: 구독제 말고는 작은 금액을 받을 방법이 없던 문제
  - Circle의 주된 고객(은행, PSP, 기업, 기관)의 문제에는 아직 에이전트 장치가 붙지 않음
  - 고객별로 회사가 말한 에이전트의 역할 ([q1-answer.md](sources/q1-answer.md) 969-981행). 열은 1번 답을 쓴 에이전트가 정함
  - 근거 칸: 1번 답이 줄여 쓴 이름(10-K, CPN 백서, litepaper, 메인넷, Agent Stack 블로그 등)을 공개 주소로 바꿈. 원문 안의 행 번호는 vault에 받아 둔 사본의 것이어서 뺐고, 1번 답의 같은 표와 끝의 "인용 위치" 표에 남아 있음 ([q1-answer.md](sources/q1-answer.md) 969-981행, 1189행부터)

| 고객                                                                                               | 회사가 말한 에이전트의 역할                                                                                                                                                                                                                                                                                                                                                                       | 도움이 닿는 쪽                                                                              | 상태                                                                                                                                                                                        | 근거                                                                                                                                                                  |
| -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1. 은행, PSP, 기업 (CPN)                                                                           | CPN이 지원하려는 용도에 "agentic payments"가 들어 있습니다(10-K 500행) [공시]. CPN 백서는 물류 회사의 에이전트가 싱가포르 운송사를 고르면, CPN에 연결된 금융기관이 달러를 USDC로 바꿔 보내고 싱가포르 쪽 기관이 SGD로 지급하는 예를 듭니다 [Circle 글]. litepaper에는 기업 자금을 운용하고 지출 정책을 실행하는 Smart Treasury Agents가 있고, 이것을 CPN과 함께 쓴다고 적혀 있습니다 [Circle 글]. | 에이전트는 물류 회사나 기업 재무 부서의 것입니다. 은행과 PSP는 그 결제를 처리하는 쪽입니다. | 계획 단계입니다("In the future", CPN 백서 443행). Smart Treasury Agents는 Arc 로드맵 항목입니다.                                                                                            | [10-K](https://d18rn0p25nwr6d.cloudfront.net/CIK-0001876042/1282dfbb-5003-4185-8ae3-88ff8f0b7bc5.pdf), [CPN 백서](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/Whitepapers/CPN_Whitepaper.pdf), [litepaper](https://www.arc.io/litepaper)                                                                                                               |
| 2. 블록체인을 직접 다루기 어려운 기업 (Managed Payments)                                           | Managed Payments 출시 글 두 편에는 에이전트 이야기가 나오지 않습니다.                                                                                                                                                                                                                                                                                                                             | -                                                                                           | -                                                                                                                                                                                           | 없다(검색: `rg -n -i 'agent' <MP 글 두 편>`, 일치 0건). [MP 글 1](https://www.circle.com/blog/simplify-stablecoin-adoption-with-cpn-managed-payments), [MP 글 2](https://www.circle.com/blog/cpn-managed-payments-stablecoin-settlement-made-simple)                                                                                                                |
| 3. 기관 환전 (StableFX)                                                                            | StableFX 제품 페이지와 10-K의 StableFX 절(510-515행)에는 에이전트 설명이 나오지 않습니다. 메인넷 발표문은 에이전트가 이미 "executing trades, managing payments, routing liquidity" 같은 일을 한다고 적었지만(메인넷 42행), StableFX를 직접 언급하지는 않습니다.                                                                                                                                   | -                                                                                           | -                                                                                                                                                                                           | 없다(검색: `rg -n -i 'agent' <StableFX 페이지>`, 일치 1줄이고 그 줄은 메뉴의 Agent Stack 링크. `sed -n '510,515p' <10-K> \| rg -c -i 'agent'`, 일치 0건). [StableFX 페이지](https://developers.circle.com/stablefx.md), [10-K](https://d18rn0p25nwr6d.cloudfront.net/CIK-0001876042/1282dfbb-5003-4185-8ae3-88ff8f0b7bc5.pdf), [메인넷](https://www.circle.com/pressroom/circle-launches-arc-mainnet-an-economic-operating-system-for-the-internet) |
| 4. 앱 개발자 (App Kits, Arc Studio, Skills)                                                        | 이 행에서 에이전트는 돈을 쓰는 주체가 아니라 개발을 돕는 도구입니다. Arc Studio는 "an onchain coding agent"이고(메인넷 77행), Circle Skills는 AI 코딩 도구로 개발하는 사람을 위한 구현 패턴입니다 [Circle 글].                                                                                                                                                                                    | 개발자 본인                                                                                 | 출시되었습니다. 다만 "Arc Studio deploys to Arc testnet only."입니다 [Team Arc 글].                                                                                                         | [메인넷](https://www.circle.com/pressroom/circle-launches-arc-mainnet-an-economic-operating-system-for-the-internet), [Agent Stack 블로그](https://www.circle.com/blog/introducing-circle-agent-stack-financial-infrastructure-for-the-agentic-economy), [arc-studio-cli](https://docs.arc.io/ai/arc-studio-cli.md)                                                                                                            |
| 5. 에이전트를 만드는 개발자 (Agent Stack)                                                          | 에이전트가 돈을 보관하고, 서비스를 찾고, 값을 치르게 합니다. 블로그가 지적한 문제는 에이전트 전용 지갑이 없어서 개인 키를 코드에 넣거나, 사람용 계정과 수동 승인에 기대야 했다는 점입니다. 해법은 사람이 정한 정책(기간별 지출 한도, 주소 허용 목록과 차단 목록)을 지갑이 실행 전에 검사하는 것입니다 [Circle 글].                                                                                | 개발자와 개발자가 만든 에이전트                                                             | Wallets, Marketplace, CLI는 2026년 5월에 출시되었습니다. 에이전트가 돈을 버는 기능은 하반기 계획입니다. Agent Sector(에이전트 신원과 감사 기록)는 로드맵 항목이고, AgentVM은 설계 중입니다. | [Agent Stack 블로그](https://www.circle.com/blog/introducing-circle-agent-stack-financial-infrastructure-for-the-agentic-economy), [실적 보도자료](https://s206.q4cdn.com/265218871/files/doc_news/2026/Aug/05/CIRCLE_Q2-2026.pdf), [메인넷](https://www.circle.com/pressroom/circle-launches-arc-mainnet-an-economic-operating-system-for-the-internet)                                                                                                  |
| 6. (1번 답의 고객 다섯에 없던 고객) API와 데이터를 파는 쪽 (Agent Marketplace, x402, Nanopayments) | Agent Stack 블로그는 Agent Marketplace가 서비스 이용을 "human-scale subscriptions and manual integrations"에서 사용량 기반 결제로 옮긴다고 적습니다. Nanopayments는 가스비 없이 1센트보다 작은 금액도 옮기는 장치입니다 [Circle 글].                                                                                                                                                              | 서비스를 파는 쪽입니다. 돈을 쓰는 것은 사는 쪽의 에이전트입니다.                            | 결제를 받는 장치는 나왔습니다. "Agents can earn"은 하반기에 짓는 중입니다("H2 2026 - BUILDING").                                                                                            | [Agent Stack 블로그](https://www.circle.com/blog/introducing-circle-agent-stack-financial-infrastructure-for-the-agentic-economy), [2분기 발표 자료](https://s206.q4cdn.com/265218871/files/doc_presentations/2026/Aug/05/Q2-2026-Earnings-Presentation.pdf)                                                                                                                  |
| 7. (1번 답의 고객 다섯에 없던 고객) 에이전트에게 일을 맡기는 사람 (Arc Portal)                     | Arc Portal은 "lets people fund agent wallets, set spend limits, and delegate onchain tasks"라고 소개됩니다 [Circle 글].                                                                                                                                                                                                                                                                           | 일을 맡기는 사람                                                                            | 메인넷 발표문은 이미 쓸 수 있는 창구로 소개합니다.                                                                                                                                          | [메인넷](https://www.circle.com/pressroom/circle-launches-arc-mainnet-an-economic-operating-system-for-the-internet)                                                                                                                                                           |

  - 왜 아직인가: 회사 스스로 기관 수요는 운영 층("operating layer")이 생기기 전에는 늘기 어렵다고 씀 ([Circle의 Beyond 글](https://www.circle.com/current/beyond-agentic-payments-the-operating-layer-for-the-agentic-economy)). 아래는 그 조건과 Agent Stack의 대응 ([q3-answer.md](sources/q3-answer.md) 293-299행)

```text
[3] 기관 수요의 조건 (Circle의 Beyond 글): authorize, govern, audit, underwrite

  [1]의 지출 정책 ......> authorize와 govern의 일부 (에이전트 주인 쪽의 한도)
  [2]의 Reputation .....> underwrite의 재료가 될 수 있음
  audit ................> 이 쪽에 맡는 장치 없음 (Agent Sector는 로드맵)

  (점선 화살표는 3번 답을 쓴 에이전트의 대응, 확신도 중간)
```

- 약관상 에이전트: 사용자를 대신하는 도구. 일이 잘못되면 책임은 사용자 ([2번 답](sources/q2-answer.md) 510행)
- 매출: 에이전트 매출이 들어갈 공시의 줄 전체가 매출의 0.76%. 그 줄은 2분기에 오히려 줄어듦 ([6번 답](sources/q6-answer.md) 64행)
- Nanopayments의 동작과 수수료: Circle 공식 문서로 확인 ([Nanopayments와 다른 소액 결제 방식의 1차 자료](sources/nanopayments-and-alternatives-primary-README.md))
- 우리의 판정
  - Nanopayments는 Circle만의 엣지인가: x
  - Nanopayments는 Circle이 해결하려는 문제와 해결 방법에 맞닿아 있는가: x
    - 에이전트를 만드는 개발자에게는 맞음
    - Circle의 기존 고객과 제품에 무엇을 해결해 주는지는 보이지 않음
  - Agent Stack으로 에이전트 문제를 푸는 방향: 다르게 본다

- 정리 (우리 판단)
  - Agent Stack으로 본 그들의 AI Agent 시대: 외부의 다른 회사들과 별반 다르지 않음
  - payment 부분의 문제: Circle의 기존 고객이 가진 지급 문제는 풀지 못함
  - Nanopayments: 이름과 달리 지금 기업의 문제를 해결하는 것이 아님. USDC로 들어오는 새로운 수요를 만들려는 것에 가까움
  - 그 방향이 틀렸다는 뜻은 아님
- 근거
  - 모아서 정산하는 방식은 Circle만의 것이 아님: Coinbase CDP Facilitator도 오프체인 바우처를 모아 한 번에 처리하는 batch-settlement 방식을 제공 ([Circle 에이전트 결제 판독](sources/circle-agentic-payments-reading.md) 151행)
  - 에이전트 결제(x402 전체, Nanopayments 하나가 아님)가 영향을 미치는 세 갈래 ([5번 답](sources/q5-answer.md) 56-73행)
    - 바뀐 것은 [1] 갈래의 두 고객까지이고, 기존 고객의 돈이 에이전트를 거쳐 움직이는 [3] 갈래는 아직 없음 ([q5-answer.md](sources/q5-answer.md) 42-44행)

```text
에이전트 결제가 영향을 미치는 세 갈래

  가. 시장의 크기: 세 갈래가 함께 딛고 있는 숫자
      결제 금액(흐름): 1,500만 달러에서 1억 달러 이상까지, 세는 방식에 따라 다름
      USDC의 몫: 98.6%에서 99.8%
        |
        +--> [1] 소액 결제의 정산 자산이라는 USDC의 자리 .......... 이미 생김
        |        바뀐 고객: API와 데이터 판매자, 에이전트 개발자
        |        한계: 바뀐 곳이 0.30달러 아래 구간이라 금액이 작음
        |
        +--> [2] Circle의 매출 ...................................... 보이지 않음
        |        닿는 길: 결제 금액이 아니라 에이전트가 쥔 USDC 잔액
        |        한계: 그 잔액의 숫자가 없어서 판단할 수 없음
        |
        +--> [3] 은행, PSP, 기업의 돈이 에이전트를 거쳐 움직이는 일 .. 아직 없음
                 근거: "institutional volume hasn't shown up yet"
                 필요한 조건: 신뢰와 통제 층, 규제, 수요
                 세 조건 모두 Circle 혼자 쥔 것이 아님
```

  - Circle의 주된 고객(은행, PSP, 기업, 기관)의 문제에는 아직 에이전트 장치가 붙지 않음 ([q3-answer.md](sources/q3-answer.md) 41행)
  - 에이전트가 Circle 매출이 되는 경로 가운데 CEO가 "fundamentally"라고 한 것: USDC 채택과 Arc 채택 ([q3-answer.md](sources/q3-answer.md) 45행)
  - 6번 답의 판단: 에이전트는 매출 논리가 아니라 채택 논리 ([6번 답](sources/q6-answer.md) 49행). 위 "Circle의 사업"의 목표 그림에서 C 갈래(에이전트)가 목표 1에는 스테이블코인 채택으로, 목표 2에는 "some"으로만 닿음

## 그외 AI나 Agent가 붙은 Circle/Arc 제품들

- 자료: [Arc App Kits와 Build with AI 읽기 안내](sources/arc-app-kit-vs-build-ai-guide.md) (2026-10-13, 2026-10-07에 보관한 Arc 공식 문서와 대조)
- 둘의 차이: 쓰는 주체가 다름 (안내 32행)
  - App Kits: 앱 코드 안에 설치해 호출하는 SDK. 앱이 실행될 때 씀
  - Build with AI: 개발자와 AI 코딩 도구가 앱을 만들 때 쓰는 도구 묶음. 완성된 앱 안에는 들어가지 않음
- App Kits
  - 기능 일곱: Send, Bridge, Swap, Unified Balance, Onramp, Earn, Borrow (안내 127행)
  - 메인넷 체인도 지원. Arc 전용이 아님("not just Arc") (안내 123-124행)
- Build with AI: 도구 넷 (안내 120-124행)
  - Arc Studio: 프롬프트로 앱 생성, 테스트넷 배포. Arc와 USDC가 기본값
  - Arc Studio CLI: Studio 기능을 터미널과 코딩 도구에서 호출. 테스트넷에만 배포
  - Skills: Arc와 Circle 사용법 지식. 그중 셋(bridge-stablecoin, swap-tokens, unify-balance)이 App Kits 사용법을 다룸 (안내 129행)
  - MCP server: Arc 문서 검색. 문서만 읽음
- 에이전트와 닿는 곳: 결제 Skills (안내 139행)
  - 결제 스킬을 받은 코딩 에이전트는 실행 중에 스스로 돈을 쓸 수 있음
  - 이때 쓰는 것은 App Kits가 아니라 Circle CLI와 에이전트 지갑으로 보임 (안내 작성자의 추론, 확신도 중간)
- 확인되지 않은 것: Arc Studio가 만든 앱이 App Kits를 쓰는지. Studio와 CLI 문서에 언급이 없음 (안내 136행)

## 외부의 AI Agent 제품들

- x402(판매자가 HTTP 402 응답으로 값을 알리고, 사는 쪽이 서명해서 다시 요청하는 결제 협상 방식): 협상은 회사마다 같고 정산은 다름 ([Circle 에이전트 결제 판독](sources/circle-agentic-payments-reading.md) 143-154행)
  - Circle: facilitator(결제를 검증하고 정산해 주는 운영 서비스) 둘을 운영. 한 건마다 온체인으로 정산하는 것과 Gateway로 모아서 정산하는 것
  - Coinbase: 건별 정산과 모아서 정산하는 방식 모두 제공
- x402 말고 다른 소액 결제 방식: MPP. 둘의 공식 문서는 위의 1차 자료 묶음에 있음
- 시장의 크기: 아직 작음 ([5번 답](sources/q5-answer.md) 33-39행)
  - x402 누적 금액: 세는 방식에 따라 1,500만 달러에서 1억 달러 이상까지 갈림
  - x402와 MPP를 합친 2026-08 한 달 금액: 643,721달러
  - Visa, Stripe, Circle 모두 에이전트 결제가 원래 사업에 견주어 0.0001%보다 작음. 에이전트 결제 매출을 따로 밝힌 회사는 없음
- 에이전트를 부르는 말: 회사마다 다름 ([q2-answer.md](sources/q2-answer.md) 212-215행)
  - 다른 회사들: 대체로 "사람을 대신하는 대리인"이나 "새로운 고객"
  - 노동이나 일꾼이라고 부른 곳: 비교한 범위에서 Circle과 Arc뿐
  - 날짜순으로 합친 표 ([q2-answer.md](sources/q2-answer.md) 325-361행)
    - Circle 목소리와 다른 회사의 표를 날짜순으로 합친 것. 칸의 글은 원래 표에서 그대로 옮김
    - "분류" 열은 2번 답을 쓴 에이전트가 만든 것. Circle 목소리 행과 다른 회사 행은 분류의 촘촘한 정도가 다름

| 날짜       | 누구의 말     | 자료                                                                     | 원문                                                                                                                                                                                                                                                                                                                                                                             | 분류                                  |
| ---------- | ------------- | ------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------- |
| 2024-11-06 | Circle 목소리 | 개발자 블로그 (Blessing Adesiji)                                         | "enables AI agents to operate and transact independently using digital dollars"                                                                                                                                                                                                                                                                                                  | 혼자 거래하는 존재                    |
| 2025-01    | 다른 회사     | South 외 논문, 2025-01                                                   | "on behalf of a user" / "It remains uncertain how established agency doctrines will adapt to AI agents that can learn, self-modify, or operate autonomously"                                                                                                                                                                                                                     | 대리인으로 부르는 쪽                  |
| 2025-04-29 | 다른 회사     | Mastercard Agent Pay 발표, 2025-04-29                                    | "require trusted AI agents to be registered" (이어서 "on behalf of their users")                                                                                                                                                                                                                                                                                                 | 대리인으로 부르는 쪽                  |
| 2025-09-10 | 다른 회사     | Mastercard 발표, 2025-09-10                                              | "Agent Sign-Up: A simple way for those using the Agent Toolkit to identify their agents"                                                                                                                                                                                                                                                                                         | 대리인으로 부르는 쪽                  |
| 2025-09-12 | Circle 목소리 | x402 예제 글 (Anthony Kelani)                                            | "A Langchain-based AI agent acting on behalf of a user."                                                                                                                                                                                                                                                                                                                         | 대리인                                |
| 2025-09-17 | 다른 회사     | Google AP2 발표, 2025-09-17                                              | "AI agents are capable of transacting on behalf of users"                                                                                                                                                                                                                                                                                                                        | 대리인으로 부르는 쪽                  |
| 2025-09-26 | Circle 목소리 | OOAK 글 (Mira Belenkiy)                                                  | "we need to shield secrets from the LLM that powers the agent"                                                                                                                                                                                                                                                                                                                   | 믿으면 안 되는 코드                   |
| 2025-10-10 | Circle 목소리 | Gateway 마이크로페이먼트 글 (Marcus Boorstin)                            | "a new class of participants: AI agents capable of transacting, learning, and creating economic value on their own with stablecoins" [원문의 링크 표기는 뺐습니다]                                                                                                                                                                                                               | 참여자                                |
| 2025-12-18 | 다른 회사     | Visa 보도자료, 2025-12-18 (TAP를 내놓은 시점은 본문의 "In October 2025") | Trusted Agent Protocol은 "distinguish between malicious bots and legitimate AI agents acting on behalf of consumers"                                                                                                                                                                                                                                                             | 대리인으로 부르는 쪽                  |
| 2026-02-03 | Circle 목소리 | OpenClaw 해커톤 공지 (Elton Tay)                                         | "AI agents are no longer just tools, they are becoming participants."                                                                                                                                                                                                                                                                                                            | 참여자                                |
| 2026-02-24 | 다른 회사     | Stripe 연례 서한, 2026-02-24                                             | "(Autonomous agents, themselves, are emerging as a new customer type for internet businesses to sell to.)"                                                                                                                                                                                                                                                                       | 고객이나 참여자로 부르는 쪽           |
| 2026-02-25 | Circle 목소리 | 4분기 실적 콜 (Allaire)                                                  | "tens or hundreds of billions of AI agents will interact and perform economic functions" / "AI agents as consumers of this as essentially end customers"                                                                                                                                                                                                                         | 고객                                  |
| 2026-03-10 | Circle 목소리 | Nanopayments 테스트넷 글 (Team Circle)                                   | "robots and agents increasingly exist as fully independent economic actors"                                                                                                                                                                                                                                                                                                      | 경제 주체                             |
| 2026-03-10 | Circle 목소리 | Moltbook 해커톤 연구 글 (Austin Bennett)                                 | "agents engaged in potentially adversarial behavior"                                                                                                                                                                                                                                                                                                                             | 관찰 대상                             |
| 2026-04-02 | Circle 목소리 | HackMoney Arc 트랙 글 (Blessing Adesiji)                                 | "AI agents are the primary users of financial infrastructure"                                                                                                                                                                                                                                                                                                                    | 사용자                                |
| 2026-04-28 | 다른 회사     | Visa 2분기 실적 콜, 2026-04-28 (CEO Ryan McInerney)                      | "the limiting factor for agentic commerce is trust"                                                                                                                                                                                                                                                                                                                              | 대리인으로 부르는 쪽                  |
| 2026-04-29 | 다른 회사     | Stripe Sessions 2026 정리, 2026-04-29 (Will Gaybrick)                    | Radar가 "distinguish legitimate AI agents from fraudulent actors"                                                                                                                                                                                                                                                                                                                | 고객이나 참여자로 부르는 쪽           |
| 2026-05-11 | Circle 목소리 | Agent Stack 출시 글 (Team Circle)                                        | "enable agents as autonomous economic actors"                                                                                                                                                                                                                                                                                                                                    | 경제 주체                             |
| 2026-05-29 | 다른 회사     | Base 블로그, 2026-05-29                                                  | "they are becoming paying customers" / "The next evolution is agents earning." / "The same wallets and payment rails that make agents internet customers can make them internet businesses."                                                                                                                                                                                     | 고객이나 참여자로 부르는 쪽           |
| 2026-07-14 | 다른 회사     | Visa와 Artemis 보고서 소개, 2026-07-14 마지막 수정 (Tim Conrad)          | macro: "the agent is acting for a person" / micro: "small, frequent payments that one piece of software makes to another"                                                                                                                                                                                                                                                        | 대리인으로 부르는 쪽                  |
| 2026-07-14 | 다른 회사     | x402 Foundation 출범 보도자료, 2026-07-14                                | 회원사 발언들입니다. Linux Foundation CEO Jim Zemlin "active participants in the global economy", AWS의 Peyton Rice "first-class participants in digital commerce", Stripe의 Kevin Miller "empower agents to become economic actors on the internet". 같은 보도자료 안에서 Monad의 Raj Parekh는 "on behalf of the people and businesses they serve"라고 대리인 쪽으로 말했습니다 | 고객이나 참여자로 부르는 쪽           |
| 2026-07-31 | Circle 목소리 | API 수익화 글 (Jasper Kim)                                               | "the buyers are not people. They are agents."                                                                                                                                                                                                                                                                                                                                    | 구매자                                |
| 2026-08-05 | Circle 목소리 | 2분기 실적 콜 (Allaire)                                                  | "a labor market emerges for those agents" / "That agent has its own identity" / "We are building toward operating an agentic corporation."                                                                                                                                                                                                                                       | 노동, 회사                            |
| 2026-08-05 | Circle 목소리 | Steve 소개 글 (Danny Organ)                                              | "something a builder runs and controls, not a service Circle operates."                                                                                                                                                                                                                                                                                                          | 만든 사람이 통제하는 참조 구현        |
| 2026-08-06 | 다른 회사     | MetaMask Agent Wallet 소개, 2026-08-06                                   | "a self-custodial wallet built for AI agents. It lets an agent attempt onchain actions through a CLI while staying inside user-defined rules and transaction checks."                                                                                                                                                                                                            | 지갑 회사: 이름 없이 장치만 말하는 쪽 |
| 2026-08-12 | Circle 목소리 | 열린 에이전트 경제 글 (Jasper Kim, Hao Min)                              | "turning software from a tool people operate into labor they can delegate to"                                                                                                                                                                                                                                                                                                    | 위임받는 노동                         |
| 2026-09-16 | Circle 목소리 | Arc 블로그 "unfinished business" 글 (Team Arc)                           | "The opportunity isn't the agents themselves, it’s the businesses they become: zero-person companies"                                                                                                                                                                                                                                                                            | 회사 [원문 그대로]                    |
| 2026-09-16 | Circle 목소리 | Arc 블로그의 메인넷 글 (Team Arc)                                        | "For agents to act as trusted autonomous workers, businesses need to know which registered agent performed the work"                                                                                                                                                                                                                                                             | 조건이 붙은 일꾼                      |
| 2026-09-17 | Circle 목소리 | Arc Studio 소개 (Team Arc)                                               | "an AI coding agent that lets you create onchain apps, contracts, and agents through prompts"                                                                                                                                                                                                                                                                                    | 개발 도구                             |
| 날짜 미상  | 다른 회사     | Google AP2 명세 (날짜 미상)                                              | "even well-behaving Agents need to have their behavior tightly constrained above what a normal authorization model would require of human users" / mandate 정의: "Agreement between a user and an agent (or chain of agents) to authorize future payment actions."                                                                                                               | 대리인으로 부르는 쪽                  |
| 날짜 미상  | 다른 회사     | Coinbase CDP 문서 (날짜 미상)                                            | "Give your AI agent a wallet. Pay for APIs, send money, and trade tokens safely, with built-in spending limits."                                                                                                                                                                                                                                                                 | 지갑 회사: 이름 없이 장치만 말하는 쪽 |

- 정당한 에이전트와 그렇지 않은 것을 누가 가려내는가: 회사마다 자리가 다름 ([q2-answer.md](sources/q2-answer.md) 416-444행)

```text
정당한 에이전트와 그렇지 않은 것을 누가 가려내는가

[돈을 받는 쪽, 들어오는 에이전트를 가려내야 하는 자리]
  Mastercard   프로그램이 직접 요구: "require trusted AI agents to be registered",
               Agent Sign-Up으로 에이전트를 식별
  Visa         가맹점이 가려내도록 틀을 줌: Trusted Agent Protocol은 "an open framework"
  Stripe       결제 처리자가 직접: Radar가 정당한 에이전트와 사기 행위자를 구별

[판별이 덜 필요하게 만드는 쪽]
  Google AP2   사용자가 서명한 위임(mandate)으로 행동 범위를 묶음:
               "without them having to be inherently trustworthy"
               믿을 만한 에이전트만 받을지는 다른 층으로: "left to the Commerce Protocol layer"

[돈을 내는 쪽, 에이전트의 지갑 자리]
  Circle       판별하지 않는다고 고지문에 적음: "Circle does not verify, screen, monitor ..."
               Circle이 심사하는 것은 에이전트가 아니라 마켓플레이스의 서비스

[네트워크]
  Arc          판별에 쓸 기록을 담는 그릇을 둠: ERC-8004 레지스트리 (메인넷)
               점수는 응용이 계산하고, 평판은 외부 관찰자가 기록
               "open trust layer"는 설계 단계: "is designed to provide"
  Circle 스스로: "registries are only containers"

[비교 범위의 다른 암호화폐 쪽]
  x402, Coinbase CDP, Base   판별하는 이름이나 장치가 나오지 않음
  MetaMask                   에이전트가 아니라 거래 단위로:
                             "malicious or flagged transactions"에 2단계 인증
```

- 공개판의 "하는 일" 표가 기대는 원문 (2026-10-15에 모은 것. 원문 인용 안의 긴 대시와 둥근 따옴표는 ASCII로 바꿔 적음)
  - 표는 하는 일에 따라 묶었음. 이 묶음은 공개판을 쓰면서 정한 것이고, 각 회사가 쓴 분류는 아님
  - 에이전트 지갑과 지출 한도
    - Circle Agent Wallets: [Agent Stack 출시 글(2026-05-11)](https://www.circle.com/blog/introducing-circle-agent-stack-financial-infrastructure-for-the-agentic-economy)의 "Agent Wallets give agents a way to hold and move USDC under human-defined policies. Users can create wallets designed for machine-initiated operation for their agents, then configure controls such as time-bound USDC spending limits for transfers and x402 services, as well as allowlists and blocklists"
    - Coinbase CDP Agentic Wallet: [Coinbase 개발자 문서](https://docs.cdp.coinbase.com/agentic-wallet/cli/welcome.md)의 "Give your AI agent a wallet. Pay for APIs, send money, and trade tokens safely, with built-in spending limits."
    - MetaMask Agent Wallet: [MetaMask 소식(2026-08-06)](https://metamask.io/news/introducing-metamask-agent-wallet)의 "MetaMask Agent Wallet ... officially launches today, giving traders and builders a self-custodial way to let AI agents execute onchain actions while staying inside user-defined rules."
  - 모아서 정산하는 소액 결제
    - Circle Gateway Nanopayments: [Circle 개발자 문서](https://developers.circle.com/gateway/nanopayments.md)의 "Gasless USDC micropayments down to \$0.000001 via x402 and batched settlement. For pay-per-request APIs, AI agent payments, streaming."
    - Coinbase CDP Facilitator: [Coinbase 개발자 문서](https://docs.cdp.coinbase.com/x402/core-concepts/facilitator.md)의 "With `batch-settlement`, vouchers are verified offchain for free and claimed together, so one onchain transaction can process thousands of payments."
    - MPP Sessions(Tempo, Stripe): [MPP 문서](https://mpp.dev/payment-methods/tempo/session.md)의 "The `session` intent enables high-frequency, pay-as-you-go payments over unidirectional payment channels."
  - 결제 협상 방식
    - x402: [Circle 개발자 문서 "What is x402?"](https://developers.circle.com/gateway/nanopayments/concepts/x402.md)의 "x402 is not a payment system itself. It is a negotiation protocol, agnostic to how payments are constructed, verified, or settled."
    - MPP: [MPP FAQ](https://mpp.dev/faq.md)의 "MPP supports stablecoins, cards, wallets, and custom rails through extensible payment method specifications. x402 only supports blockchains."와 "MPP is co-authored by Tempo and Stripe."
  - 사용자의 위임 증명
    - Google AP2: [Google Cloud 블로그 AP2 발표(2025-09-17)](https://cloud.google.com/blog/products/ai-machine-learning/announcing-agents-to-payments-ap2-protocol)의 "AP2 builds trust by using Mandates-tamper-proof, cryptographically-signed digital contracts that serve as verifiable proof of a user's instructions."
  - 돈을 받는 쪽의 에이전트 확인
    - Visa Trusted Agent Protocol: [Visa 보도자료(2025-12-18)](https://corporate.visa.com/en/sites/visa-perspectives/newsroom/visa-partners-complete-secure-agentic-transactions.html)의 "In October 2025, Visa and more than 10 partners introduced Trusted Agent Protocol , an open framework ... helping merchants to distinguish between malicious bots and legitimate AI agents acting on behalf of consumers."
    - Mastercard Agent Pay: [Mastercard 보도자료(2025-04-29)](https://s25.q4cdn.com/479285134/files/doc_news/Mastercard-Unveils-Agent-Pay-Pioneering-Agentic-Payments-Technology-to-Power-Commerce-in-the-Age-of-AI-2025.pdf)의 "Securely registering and authenticating trusted agents: The program will require trusted AI agents to be registered"
    - Stripe Radar: [Stripe 블로그 Sessions 2026 정리(2026-04-29)](https://stripe.com/blog/everything-we-announced-at-sessions-2026)의 "We previewed Radar's bot abuse prevention , designed to accurately distinguish legitimate AI agents from fraudulent actors."

## Arc 해커톤들

- Arc 커뮤니티 페이지의 이벤트 카드 178개 전부 수집 ([Arc 이벤트 전체 수집](sources/arc-events-complete-README.md), 2026-10-08)
  - 해커톤 말고도 워크숍, 기술 상담, 데모 데이, Microgrants(보조금), 지역 모임이 섞여 있음
- 에이전트를 내건 공고의 개발 문제: 대부분 소액 결제, 에이전트 상거래, 작은 사업체의 자금 관리 ([공고별 개발 문제 비교](sources/arc-event-product-themes-reading.md) 42-52행)
  - Lepton: 유료 자원을 사는 에이전트, 에이전트 서비스의 건별 판매, 에이전트 사이의 지급, 콘텐츠 수익화
  - LabLab Agentic Economy: API, 자료, 모델 추론을 쓴 만큼 과금하는 앱. Arc 정산과 Nanopayments 필수
  - LabLab Agentic Commerce: 소액 상거래, 에이전트의 신원과 정책, 자율 구매와 판매
  - Tameion: 기업 자금 관리, 지급과 수금 업무의 자동화, 거래 상대의 위험 심사
- CPN, StableFX 같은 기관용 제품: 에이전트 행사가 아니라 기업 금융 해커톤(Arc x Encode Enterprise and DeFi, 2026-02)에서 다룸 ([행사별 정리](sources/arc-all-events-reading.md) 6531-6534행)
- 행사가 주는 것과 요구하는 것: 행사마다 다름 ([7번 답](sources/q7-answer.md) 나 절)
  - Arc House 점수: 해커톤 참가 500점, 수상 1,000점. 주제는 따지지 않음 ([q7-answer.md](sources/q7-answer.md) 163행)
  - 행사 뒤에 남는 것: 공개 저장소와 시연 영상
  - Circle 팀과의 정기 만남(분기 브리핑): Arc House 2등급(3,500점)부터 ([q7-answer.md](sources/q7-answer.md) 164행)
  - 참가 조건: Tameion은 실제 사업체, Microgrants는 Arc 메인넷에 배포한 결과물 필요

- 정리 (우리 판단)
  - 여기에서는 Circle/Arc의 엣지가 보이지 않음
  - 지금 그들이 그리는 AI Agent는 외부의 AI Agent와 다를 것이 없음
  - 따라서 여기에서 Circle/Arc만의 AI Agent Payment라고 볼 것이 없음. 에이전트 결제 자체(Nanopayments, x402 정산)는 있음
- 근거
  - 공고가 내건 개발 문제에 쓰는 에이전트 제품(Agent Wallets, Gateway): Arc를 포함한 여러 체인에서 돌아감 ([4번 답](sources/q4-answer.md) 47행)
  - Arc 문서가 에이전트용으로 드는 두 표준(ERC-8004, ERC-8183): 이더리움 쪽 공동 표준이라 Arc에 묶이지 않음. 둘 다 아직 초안 ([q4-answer.md](sources/q4-answer.md) 48행)
  - Arc만의 에이전트 장치(신뢰 층, Agent Sector, AgentVM): 아직 설계나 로드맵 단계 ([q4-answer.md](sources/q4-answer.md) 49행)
  - 에이전트가 일을 팔아 사업체가 된다는 말은 Base에도 있음 ([q2-answer.md](sources/q2-answer.md) 215행)
  - Arc에서만 얻는 기능은 USDC로 내는 가스비, 빠른 확정, StableFX의 정산 장소 정도 (위의 "Arc의 자리")

- 공개판의 공고별 설명이 기대는 공고 원문 (2026-10-15에 모은 것. 원문 인용 안의 긴 대시와 화살표는 ASCII로 바꿔 적음)
  - Agentic Commerce on Arc(LabLab, 2026-01): [공고](https://lablab.ai/event/agentic-commerce-on-arc)의 "developers will build the next generation of agentic commerce systems on Arc with USDC", "Jan 9 - 23 (Online Phase)"
  - Agentic Economy on Arc(LabLab, 2026-04): [공고](https://lablab.ai/ai-hackathons/nano-payments-arc)의 "developers will build the next generation of Agentic economic applications using Circle's Nanopayments infrastructure with settlement on Arc in USDC.", "April 20 - 26, 2026", "Build the Agentic Economy on Arc using USDC and Nanopayments."
  - Lepton Agents(Canteen, 2026-06~07): [공고](https://lepton.thecanteenapp.com/)의 "Online, 3 weeks", "Jun 15 -> Jul 6", "a builder series for AI agents and creators that pay, receive, and stream value at the smallest scale, settled on Arc"
  - Tameion Agents(Canteen, 2026-09~10): [공고](https://tameion.thecanteenapp.com/)
    - "An event covering the treasury, invoices, contractors, autonomous operations, and the audit trail behind all of it. Settled on Arc in USDC."
    - "Online, 3 weeks", "Sep 27 - Oct 17", "Invite-only"
    - "You will also be asked traction questions: how many businesses you have onboarded, how much value the agent moved, and what problems you are solving for them."
    - "Circle's developer platform on Arc, the primitives suited to an agent that holds and disburses a company's money. Use what you need."
    - 안내한 도구: Circle Agent Stack, Wallets, Paymaster(가스비 대납), CCTP, Gateway, USYC, Contracts, USDC와 EURC
    - "circlefin/arc-stablecoin-fx: USDC<->EURC FX swaps via the App Kit Swap SDK."
    - "Do I need a real business to build for?" / "Yes, and it can be a small one. Yours counts." / "A freelancer chasing three invoices, a two-person agency paying contractors abroad, a small studio with an unused seat on six SaaS tools: all of these are the traction we mean."
    - 공고 본문에 StableFX와 CPN이 나오지 않음(검색: 2026-10-08에 받은 공고 사본에 `rg -c 'StableFX|CPN'`, 0건)
    - 일정: 주최자 페이지는 "Sep 27 - Oct 17"(제출 마감 10월 17일)이고, Arc 커뮤니티 페이지의 공개 데이터는 2026-09-27부터 10-10까지 ([arc-all-events-reading.md](sources/arc-all-events-reading.md) 376행)
  - 기관용 제품을 다룬 행사, Arc x Encode Enterprise & DeFi(2026-02-27): [공고](https://community.arc.io/public/events/arc-x-encode-enterprise-and-defi-hackathon-vcm38l2yye)의 "Hosted at Encode Hub, this is a 3-day IRL hackathon", "Some tools - StableFX, USYC and Circle Payments Network are permissioned enterprise products. If you plan to build with them, register early so we can share the right access credentials and onboarding support."

## 외부 AI Agent Payment 관련 해커톤들

- 자료
  - [에이전트 결제에 맞는 해커톤 조사](sources/agent-payment-hackathon-scout.md): 2026-08-07부터 이어 온 조사. 1절(결제 제품과 직접 맞는 행사)이 이 절과 겹침
  - [블록체인 AI 에이전트 해커톤 공식 공고 대조](sources/aiagents-hackathon-official-notices.md) (2026-10-10): 위 조사의 일정을 공식 공고로 다시 확인
- 앞으로 열리는 행사 (2026-10-15 기준)
  - TUM Blockchain & AI: 10/30~31, 뮌헨 현장 30시간. 주제가 "Agentic Payments". 등록 마감 10/29 (조사 문서 198-203행, 2026-08-07 확인)
  - ETHGlobal Mumbai: 11/5~7, 뭄바이 현장. 범용 행사. 개별 바운티, 등록 마감, 신규 작업 규칙은 확인 안 됨 (공고 대조 22행)
  - Agent Pay - MERGE Madrid: 11/27~29, 마드리드 현장 48시간. Agent Commerce, Agent Micropayments 위의 제품 (조사 문서 211-216행)
    - 10-10 대조에서는 해커톤 주소가 입장권 페이지로 넘어가서 공고 본문을 확인하지 못함 (공고 대조 33행)
- 신청이 닫힌 행사: Agentic Dollars on Bitcoin, Turin. 10/17~18 행사, 신청 마감 10/5 (공고 대조 23행)
- Arc 행사와 다른 점: 쓸 체인과 회사 제품이 정해져 있지 않음. 공개판 "저의 결론"의 "AI Agent Payment" 정의에서 "어느 회사의 제품 위에서 Agent Payment 관련 작업을 하든 상관없음"과 맞닿음

- 공개판의 행사별 설명이 기대는 공고 원문 (2026-10-15에 모은 것)
  - TUM Blockchain & AI(2026-10-30~31, 뮌헨): [공고](https://tum.devfolio.co/)의 "Oct 30 - 31, 2026", "München, Germany", "The Theme: Agentic Payments", "30-hour build sprint", "Teams of 1 to 5", "~200 builders on site", "\$10,000 Available in Prizes"와 그 아래 트랙 둘(BSV Blockchain \$4,000, Cardano \$6,000), "More sponsor tracks to be announced"
  - ETHGlobal Mumbai(2026-11-05~07, 뭄바이): [상금 페이지](https://ethglobal.com/events/mumbai/prizes)의 "12" / "Prizes"
    - 후원사와 금액: World \$12,500, 1inch \$7,000, 0G \$15,000, Uniswap Foundation \$15,000, Arc \$15,000, Hedera \$15,000, Arkiv \$15,000, Whitechain \$15,000, Ethereum Foundation \$15,000, ENS \$10,000, Definitive \$5,000, Chainlink \$5,000
    - Arc 항목: "Prize details coming soon"
    - 일정 11-05~07: 2026-10-10의 공고 대조 ([aiagents-hackathon-official-notices.md](sources/aiagents-hackathon-official-notices.md) 22행)
  - Agent Pay - MERGE Madrid(2026-11-27~29, 마드리드): 2026-08-07에 확인한 기록 ([agent-payment-hackathon-scout.md](sources/agent-payment-hackathon-scout.md) 211-216행). 2026-10-10과 10-15 모두 [해커톤 주소](https://www.mmerge.io/hackathon-2026)가 입장권 페이지("Buy Tickets for Merge")로 넘어가서, 공고 본문은 확인하지 못함
  - Cronos x402 PayTech(결과 발표 2026-02-27): [결과 발표 글](https://blog.cronos.com/p/announcing-the-cronos-x402-hackathon)의 "After reviewing 191 global submissions, our panel of judges has selected the teams that best embody the precision and utility required for the Cronos and Crypto.com ecosystems.", "Main Track: x402 Applications (Broad Use Cases)". 발표일은 [aiagents-hackathon-official-notices.md](sources/aiagents-hackathon-official-notices.md) 28행
  - Claw & Order: CKB AI Agent Hackathon(2026-03-11~25): [결과 발표 글](https://talk.nervos.org/t/claw-order-ckb-ai-agent-hackathon-results/10173)의 "The hackathon ran from March 11 to March 25, 2026 - a two-week sprint to build autonomous, user-authorized AI agents on CKB.", "1st Place - PactAgent (\$5,000)" / "PactAgent is a milestone-based escrow and payment system built on CKB"
  - Agentic Dollars on Bitcoin(2026-10-17~18, 토리노): [공고](https://rgbprotocol.org/agentic-dollars-hackathon/)의 "Applications closed", "RGB and QVAC are required for every project. WDK is optional, but strongly encouraged"

## 저번주에 조사한 자료들

- 범위: 2026-10-05부터 10-11까지 만든 자료
  - 10-13, 10-14에 답한 [질문 일곱](sources/arc-hackathon-questions-README.md)은 이번 주 작업이어서 위의 항목들에 나눠 넣음
- [Arc 조사 원고](sources/arc-research-structure-README.md): Arc를 무엇인가, 왜 만들었나, 프로토콜, 사업, 개발자, 가치와 토큰, 시기로 나눠 조사
  - 사업 절: Circle 제품마다 쓰는 방법과 "해결되지 않고 남는 것"을 나란히 정리 ([arc-section-04-business.md](sources/arc-section-04-business.md) 1107-1127행)
- [Circle과 Arc 외부 공유 자료 목차](sources/circle-arc-public-material-outline.md) (2026-10-08): 기업 지급 결제에서 시작해 Circle 제품과 Arc 프로그램으로 이어지는 설명 순서
- [Arc 이벤트 전체 수집](sources/arc-events-complete-README.md) (2026-10-08): 위의 "Arc 해커톤들"이 쓴 자료
- [블록체인 AI 에이전트 해커톤 조사 대화](sources/aiagents-hackathon-README.md) (2026-10-10): Arc 밖까지 포함한 AI 에이전트 해커톤 조사와 공식 공고 대조

## 조사/정리한 것의 근거

- 공개판 "조사/정리한 것"의 줄을 따옴표 안에 그대로 옮기고, 그 아래에 근거를 둠. 줄과 근거를 짝지은 것은 에이전트
- 소제목만 있는 줄(예: "제품", "각 행사")과 절 이름 줄은 짝짓지 않음. 절 이름 줄은 이미 이 문서의 같은 이름 절로 이어짐
- 공개판의 표는 "외부의 AI Agent 제품들" 아래에 줄마다 따로 적음

### Circle의 사업의 근거

- <a id="ev-r01"></a>"Circle의 고객: 금융기관, 기업, 개발자"
  - [q1-answer.md](sources/q1-answer.md) 115-136행(그림 1의 고객 칸)
- <a id="ev-r02"></a>"Circle 제품 3축: Circle이 2분기 공시(10-Q)에서 스스로 나눈 세 기둥"
  - 원문: [2026년 2분기 10-Q](https://d18rn0p25nwr6d.cloudfront.net/CIK-0001876042/ea208256-f5a3-44b0-b51e-845285336f68.pdf)의 "Our business is organized around three reinforcing pillars"
- <a id="ev-r03"></a>"Arc와 개발자, 상호운용 인프라: Arc, Agent Stack(Agent Wallets, Nanopayments, Agent Marketplace, Circle CLI), App Kits, Circle Wallets, Circle Contracts, CCTP, Gateway"
  - 원문: [같은 10-Q](https://d18rn0p25nwr6d.cloudfront.net/CIK-0001876042/ea208256-f5a3-44b0-b51e-845285336f68.pdf)의 "Arc is our open, Layer-1 blockchain ... supported by our Agent Stack (consisting of Agent Wallets, Nanopayments, Agent Marketplace and Circle CLI), core developer services (including App Kits, Circle Wallets and Circle Contracts) and interoperability services (including CCTP and Gateway)"
  - [q1-answer.md](sources/q1-answer.md) 177-194행(기둥별 제품 표)
- <a id="ev-r04"></a>"에이전트 제품(Agent Stack)은 Circle이 Arc 쪽 기둥에 넣었음"
  - 위와 같은 10-Q 문장: Agent Stack이 첫째 기둥(Arc)의 설명 안에 있음
  - [q1-answer.md](sources/q1-answer.md) 180행
- <a id="ev-r05"></a>"디지털 자산과 유동성: USDC, EURC, USYC, cirBTC, Circle Mint, xReserve"
  - 원문: [같은 10-Q](https://d18rn0p25nwr6d.cloudfront.net/CIK-0001876042/ea208256-f5a3-44b0-b51e-845285336f68.pdf)의 "(ii) Circle Digital Assets and Services, including USDC, EURC, USYC, cirBTC, and related liquidity infrastructure such as Circle Mint and xReserve"
- <a id="ev-r06"></a>"애플리케이션: CPN, StableFX. 공시 목록 밖의 제품 페이지에는 CPN Managed Payments, Refund Protocol도 있음"
  - 원문: [같은 10-Q](https://d18rn0p25nwr6d.cloudfront.net/CIK-0001876042/ea208256-f5a3-44b0-b51e-845285336f68.pdf)의 "(iii) Circle Applications, including products like CPN and StableFX"
  - 목록 밖의 둘: [CPN Managed Payments 문서](https://developers.circle.com/cpn/managed-payments.md), [Refund Protocol 글](https://www.circle.com/blog/refund-protocol-non-custodial-dispute-resolution-for-stablecoin-payments)
- <a id="ev-r07"></a>"Circle의 매출 관련 두 목표:"
  - [q6-answer.md](sources/q6-answer.md) 228-253행(회사의 두 목표와 세 갈래 그림)
- <a id="ev-r08"></a>"1. USDC 유통량을 늘려 준비금 수익을 키운다"
  - [q6-answer.md](sources/q6-answer.md) 228-253행의 목표 1
  - CEO의 말: [2분기 실적 발표 통화 녹취](https://s206.q4cdn.com/265218871/files/doc_earnings/2026/q2/transcript/Q226-Earnings-Transcript.pdf)의 "fundamentally driving stablecoin adoption, which drives revenue"
- <a id="ev-r09"></a>"2. 준비금 수익이 아닌 매출을 늘린다"
  - [q6-answer.md](sources/q6-answer.md) 228-253행의 목표 2
- <a id="ev-r10"></a>"기업들은 지급 결제 관련 문제를 느끼지만, 스테이블코인으로 옮긴 기업은 아직 적음(공개 조사들의 기업 응답). 다만 응답한 지급 사업자와 금융기관은 49%가 이미 지급에 스테이블코인을 씀"
  - [q1-answer.md](sources/q1-answer.md) 797-812행(공개 조사 여덟 건의 표)
  - 49%: [Fireblocks 보고서](https://www.fireblocks.com/report/state-of-stablecoin)
  - 조사별 공개 주소: 이 문서 "Circle의 사업" 절의 조사 표

### Arc의 위치의 근거

- <a id="ev-r11"></a>"Circle 고객의 문제 가운데 해외 지급 문제는 크기가 측정되어 있음:"
  - [q1-answer.md](sources/q1-answer.md) 567-577행
- <a id="ev-r12"></a>"중소기업 B2B 해외 지급의 평균 비용 1.6% 가운데 외환이 1.4%"
  - [q1-answer.md](sources/q1-answer.md) 567-577행
  - 원문: [FSB 2025 보고서](https://www.fsb.org/uploads/P091025-1.pdf)
- <a id="ev-r13"></a>"은행 도달 뒤 마지막 구간이 전체 지급 시간의 80% 넘게 차지함"
  - [q1-answer.md](sources/q1-answer.md) 567-577행
  - 원문: [SWIFT 안내](https://www.swift.com/payments/how-long-does-swift-payment-take)의 "over 80%"
- <a id="ev-r14"></a>"하지만, Arc가 맡는 몫은 문제마다 일부 구간뿐. Arc에서만 얻는 기능은 좁음:"
  - [q1-answer.md](sources/q1-answer.md) 579-589행
  - [arc-section-04-business.md](sources/arc-section-04-business.md) 1107-1127행(문제마다 "Arc가 맡는 부분"과 "해결되지 않고 남는 것")
- <a id="ev-r15"></a>"USDC로 내는 가스비, 빠른 확정, StableFX의 정산 정도"
  - [q1-answer.md](sources/q1-answer.md) 552행(1번 답 작성 에이전트의 판단, 확신도 중간)
  - 공시에 적힌 Arc의 설계: [circle-company-survey-answer.md](sources/circle-company-survey-answer.md) 992-997행
  - StableFX가 Arc 위에서 돈다는 공시: [circle-company-survey-answer.md](sources/circle-company-survey-answer.md) 1184행
- <a id="ev-r16"></a>"CPN, App Kits, Agent Stack은 Arc 없이도 돌아감"
  - CPN: [arc-section-02-why-understanding.md](sources/arc-section-02-why-understanding.md) 305행, [arc-section-04-business.md](sources/arc-section-04-business.md) 1161행
  - App Kits: [arc-app-kit-vs-build-ai-guide.md](sources/arc-app-kit-vs-build-ai-guide.md) 124행
  - Agent Stack: [circle-arc-agent-products-guide.md](sources/circle-arc-agent-products-guide.md) 210행
- <a id="ev-r17"></a>"즉, 현재까지는 Circle의 솔루션들 가운데 Arc가 있어야만 돌아가는 것은 적음."
  - [q1-answer.md](sources/q1-answer.md) 552행
  - 위 두 줄의 근거를 합친 것

### Circle Agent Stacks의 근거

- <a id="ev-r18"></a>"결제 기능을 2026년 상반기에 출시"
  - [q3-answer.md](sources/q3-answer.md) 266-300행(2분기 발표 자료 18쪽의 "H1 2026 SHIPPED")
  - 원문: [2026년 2분기 발표 자료](https://s206.q4cdn.com/265218871/files/doc_presentations/2026/Aug/05/Q2-2026-Earnings-Presentation.pdf)
- <a id="ev-r19"></a>"Agent Wallets: 에이전트가 USDC를 들고 쓰는 지갑. 사람이 정한 정책(기간별 지출 한도, 허용 목록과 차단 목록) 안에서만 돈을 씀"
  - 원문: [Agent Stack 출시 글](https://www.circle.com/blog/introducing-circle-agent-stack-financial-infrastructure-for-the-agentic-economy)의 "Agent Wallets give agents a way to hold and move USDC under human-defined policies"와 "time-bound USDC spending limits ... as well as allowlists and blocklists"
  - [circle-company-survey-answer.md](sources/circle-company-survey-answer.md) 1221행
- <a id="ev-r20"></a>"Agent Marketplace: 에이전트용 서비스를 찾고 비교해서 붙이는 곳. 서비스 이용을 구독과 수동 연동에서 쓴 만큼 내는 방식으로 옮기려는 것"
  - [q1-answer.md](sources/q1-answer.md) 980행(Agent Stack 블로그의 "human-scale subscriptions and manual integrations")
  - 원문: [Agent Stack 출시 글](https://www.circle.com/blog/introducing-circle-agent-stack-financial-infrastructure-for-the-agentic-economy)
- <a id="ev-r21"></a>"Circle CLI: 터미널이나 에이전트의 작업 흐름에서 명령으로 지갑을 만들고, 정책을 정하고, 서비스를 찾고, 거래를 실행하는 도구"
  - [circle-company-survey-answer.md](sources/circle-company-survey-answer.md) 1222행(공시의 설명: 지갑, 결제, 정책 관리에 접근하는 명령줄 도구)
  - [circle-arc-agent-products-guide.md](sources/circle-arc-agent-products-guide.md) 499행
- <a id="ev-r22"></a>"Nanopayments: Gateway 위에서 가스비 없이 1센트보다 작은 금액도 보내는 소액 결제. x402로 받고 모아서 한 번에 정산함"
  - 원문: [Circle 개발자 문서](https://developers.circle.com/gateway/nanopayments.md)의 "Gasless USDC micropayments down to \$0.000001 via x402 and batched settlement"
  - [circle-company-survey-answer.md](sources/circle-company-survey-answer.md) 1224행
- <a id="ev-r23"></a>"Circle Skills: AI 코딩 도구로 개발하는 사람을 위해 Circle이 쓴 구현 패턴. 출시 글은 Agent Stack 다섯 가운데 하나로 들지만, 2분기 10-Q의 Agent Stack 구성에는 없음"
  - 출시 글의 다섯 구성: [circle-arc-agent-products-guide.md](sources/circle-arc-agent-products-guide.md) 426행
  - 10-Q는 넷만 듦("Agent Stack consists of four components"): [circle-company-survey-answer.md](sources/circle-company-survey-answer.md) 1217행
  - 구현 패턴이라는 설명: [q1-answer.md](sources/q1-answer.md) 978행
- <a id="ev-r24"></a>"에이전트를 만드는 개발자와 API, 데이터를 파는 쪽의 문제"
  - [q3-answer.md](sources/q3-answer.md) 38-40행
- <a id="ev-r25"></a>"Circle의 주된 고객(은행, PSP, 기업, 기관)의 문제와 관련되어 있지 않음"
  - [q3-answer.md](sources/q3-answer.md) 41행
- <a id="ev-r26"></a>"참고: 에이전트 매출의 상한은 전체 매출의 0.76%(에이전트 수수료가 들어갈 공시 항목 전체의 비율)"
  - 원문: [2026년 2분기 10-Q](https://d18rn0p25nwr6d.cloudfront.net/CIK-0001876042/ea208256-f5a3-44b0-b51e-845285336f68.pdf)의 "Transaction revenue 5,330", "Total revenue and reserve income \$ 701,315". 계산: 5,330 / 701,315 = 0.76%
  - [q6-answer.md](sources/q6-answer.md) 64행
  - 에이전트 수수료가 이 항목에 들어간다는 것은 공시가 아니라 추정. 이 문서 "Circle의 사업" 절 끝에 적음
- <a id="ev-r27"></a>"목표는 스테이블코인 채택. 새 고객군들을 통해 USDC 유통량을 늘려 준비금 수익을 키우는 것"
  - [q3-answer.md](sources/q3-answer.md) 45행
  - [q6-answer.md](sources/q6-answer.md) 49행
  - 원문: [2분기 실적 발표 통화 녹취](https://s206.q4cdn.com/265218871/files/doc_earnings/2026/q2/transcript/Q226-Earnings-Transcript.pdf)의 "driving some revenue around the protocols themselves, but fundamentally driving stablecoin adoption"
- <a id="ev-r28"></a>"외부의 다른 회사들과 별반 다르지 않은 행보"
  - 모아서 정산하는 방식은 Coinbase에도 있음: [circle-agentic-payments-reading.md](sources/circle-agentic-payments-reading.md) 151행
  - 에이전트를 부르는 말의 회사별 비교: [q2-answer.md](sources/q2-answer.md) 212-215행
- <a id="ev-r29"></a>"Circle의 기존 고객이 가진 지급 문제를 에이전트가 풀지 못함"
  - [q3-answer.md](sources/q3-answer.md) 41행
  - [q5-answer.md](sources/q5-answer.md) 42-44행
- <a id="ev-r30"></a>"Nanopayments는 기업의 문제를 푸는 것보다 USDC로 들어오는 새 수요를 만드는 것에 가까움. 그 방향이 틀렸다는 뜻은 아님"
  - [q5-answer.md](sources/q5-answer.md) 56-73행(바뀐 것은 API와 데이터 판매자, 에이전트 개발자. 은행, PSP, 기업의 돈이 에이전트를 거쳐 움직이는 일은 아직 없음)

### 그외 AI나 Agent가 붙은 Circle/Arc 제품들의 근거

- <a id="ev-r31"></a>"App Kits: 앱 안에서 실행 중에 쓰는 SDK. Arc 전용이 아님"
  - [arc-app-kit-vs-build-ai-guide.md](sources/arc-app-kit-vs-build-ai-guide.md) 32행
  - [arc-app-kit-vs-build-ai-guide.md](sources/arc-app-kit-vs-build-ai-guide.md) 124행
- <a id="ev-r32"></a>"Build with AI: 개발할 때 쓰는 도구 넷(Arc Studio, Arc Studio CLI, Skills, MCP server)"
  - [arc-app-kit-vs-build-ai-guide.md](sources/arc-app-kit-vs-build-ai-guide.md) 120-124행
- <a id="ev-r33"></a>"에이전트와 닿는 곳은 결제 Skills"
  - [arc-app-kit-vs-build-ai-guide.md](sources/arc-app-kit-vs-build-ai-guide.md) 139행

### 외부의 AI Agent 제품들의 근거

- <a id="ev-r34"></a>"x402: 결제 협상 방식은 회사마다 같고, 정산 방식이 다름"
  - [circle-agentic-payments-reading.md](sources/circle-agentic-payments-reading.md) 143-154행
  - 원문: [Circle 개발자 문서 "What is x402?"](https://developers.circle.com/gateway/nanopayments/concepts/x402.md)의 "It is a negotiation protocol, agnostic to how payments are constructed, verified, or settled."
- <a id="ev-r35"></a>"시장은 아직 작음: x402와 MPP를 합친 2026-08 한 달 금액이 \$643,721"
  - [q5-answer.md](sources/q5-answer.md) 37행
  - [q5-answer.md](sources/q5-answer.md) 225행(2026-08: 1,530만 건, 643,721달러)
- <a id="ev-r36"></a>"Circle Agent Stack이 하는 일은 외부 제품에도 있음."
  - 아래 표의 줄마다 단 근거
- <a id="ev-r37"></a>표의 줄 "에이전트 지갑과 지출 한도"
  - Circle Agent Wallets: [Agent Stack 출시 글](https://www.circle.com/blog/introducing-circle-agent-stack-financial-infrastructure-for-the-agentic-economy)의 "Agent Wallets give agents a way to hold and move USDC under human-defined policies"
  - Coinbase CDP Agentic Wallet: [Coinbase 개발자 문서](https://docs.cdp.coinbase.com/agentic-wallet/cli/welcome.md)의 "Give your AI agent a wallet. ... with built-in spending limits."
  - MetaMask Agent Wallet: [MetaMask 소식](https://metamask.io/news/introducing-metamask-agent-wallet)의 "let AI agents execute onchain actions while staying inside user-defined rules"
- <a id="ev-r38"></a>표의 줄 "모아서 정산하는 소액 결제"
  - Nanopayments: [Circle 개발자 문서](https://developers.circle.com/gateway/nanopayments.md)의 "via x402 and batched settlement"
  - Coinbase CDP Facilitator: [Coinbase 개발자 문서](https://docs.cdp.coinbase.com/x402/core-concepts/facilitator.md)의 "With `batch-settlement`, vouchers are verified offchain for free and claimed together"
  - MPP Sessions: [MPP 문서](https://mpp.dev/payment-methods/tempo/session.md)의 "high-frequency, pay-as-you-go payments over unidirectional payment channels"
- <a id="ev-r39"></a>표의 줄 "결제 협상 방식"
  - x402: [Circle 개발자 문서 "What is x402?"](https://developers.circle.com/gateway/nanopayments/concepts/x402.md)의 "It is a negotiation protocol"
  - MPP: [MPP FAQ](https://mpp.dev/faq.md)의 "MPP supports stablecoins, cards, wallets, and custom rails"와 "MPP is co-authored by Tempo and Stripe."
- <a id="ev-r40"></a>표의 줄 "사용자의 위임 증명"
  - 지갑 정책: [Agent Stack 출시 글](https://www.circle.com/blog/introducing-circle-agent-stack-financial-infrastructure-for-the-agentic-economy)의 "time-bound USDC spending limits ... as well as allowlists and blocklists"
  - Arc가 설계 중인 위임 문서("typed mandates a user reviews"): [q2-answer.md](sources/q2-answer.md) 392행
  - Google AP2: [Google Cloud 블로그](https://cloud.google.com/blog/products/ai-machine-learning/announcing-agents-to-payments-ap2-protocol)의 "cryptographically-signed digital contracts that serve as verifiable proof of a user's instructions"
- <a id="ev-r41"></a>표의 줄 "돈을 받는 쪽의 에이전트 확인"
  - [q2-answer.md](sources/q2-answer.md) 416-444행(누가 에이전트를 가려내는가)
  - 원문: [Visa 보도자료](https://corporate.visa.com/en/sites/visa-perspectives/newsroom/visa-partners-complete-secure-agentic-transactions.html), [Mastercard 보도자료](https://s25.q4cdn.com/479285134/files/doc_news/Mastercard-Unveils-Agent-Pay-Pioneering-Agentic-Payments-Technology-to-Power-Commerce-in-the-Age-of-AI-2025.pdf), [Stripe 블로그](https://stripe.com/blog/everything-we-announced-at-sessions-2026)

### Arc 해커톤들의 근거

- <a id="ev-r42"></a>"에이전트를 내건 공고의 개발 문제는 대부분 소액 결제, 에이전트 상거래, 작은 사업체의 자금 관리. CPN, StableFX 같은 기관용 제품은 기업 금융 해커톤에서 다룸"
  - [arc-event-product-themes-reading.md](sources/arc-event-product-themes-reading.md) 42-52행(공고별 개발 문제)
  - 기관용 제품을 다룬 행사: [arc-all-events-reading.md](sources/arc-all-events-reading.md) 6531-6534행
- <a id="ev-r43"></a>"Agentic Commerce on Arc(LabLab, 2026-01): 소액 상거래, 에이전트의 신원과 정책, 자율 구매와 판매"
  - [arc-event-product-themes-reading.md](sources/arc-event-product-themes-reading.md) 47행
  - 원문: [공고](https://lablab.ai/event/agentic-commerce-on-arc)의 "developers will build the next generation of agentic commerce systems on Arc with USDC", "Jan 9 - 23 (Online Phase)"
- <a id="ev-r44"></a>"Agentic Economy on Arc(LabLab, 2026-04): API, 데이터, 모델 추론을 쓴 만큼 과금. Arc 정산, USDC, Nanopayments를 씀"
  - [arc-event-product-themes-reading.md](sources/arc-event-product-themes-reading.md) 46행
  - 원문: [공고](https://lablab.ai/ai-hackathons/nano-payments-arc)의 "Build the Agentic Economy on Arc using USDC and Nanopayments.", "April 20 - 26, 2026"
- <a id="ev-r45"></a>"Lepton Agents(Canteen, 2026-06~07): 유료 자원을 사는 에이전트, 건별 판매, 에이전트 사이의 지급, 콘텐츠 수익화"
  - [arc-event-product-themes-reading.md](sources/arc-event-product-themes-reading.md) 44행
  - 원문: [공고](https://lepton.thecanteenapp.com/)의 "Jun 15 -> Jul 6", "AI agents and creators that pay, receive, and stream value at the smallest scale, settled on Arc"
- <a id="ev-r46"></a>"Tameion Agents(Canteen, 2026-09~10, 초대받은 사람만): 작은 사업체의 자금 관리(공고는 프리랜서와 두 사람 회사도 예로 듦), 송장, 지급과 수금, 거래 상대 심사"
  - [arc-event-product-themes-reading.md](sources/arc-event-product-themes-reading.md) 45행
  - 원문: [공고](https://tameion.thecanteenapp.com/)의 "Sep 27 - Oct 17", "Invite-only", "A freelancer chasing three invoices, a two-person agency paying contractors abroad"
- <a id="ev-r47"></a>"기관용 제품은 Arc x Encode Enterprise & DeFi(2026-02, 현장 3일)에서 다룸. CPN, StableFX, USYC는 접근 허가가 필요한 기업 제품이라 미리 등록하라고 안내함"
  - [arc-all-events-reading.md](sources/arc-all-events-reading.md) 6531-6534행
  - 원문: [공고](https://community.arc.io/public/events/arc-x-encode-enterprise-and-defi-hackathon-vcm38l2yye)의 "this is a 3-day IRL hackathon", "StableFX, USYC and Circle Payments Network are permissioned enterprise products. If you plan to build with them, register early"
- <a id="ev-r48"></a>"Circle/Arc만의 AI Agent Payment라고 볼 것이 없음. 에이전트 결제 자체(Nanopayments, x402 정산)는 있음"
  - 에이전트 제품은 Arc를 포함한 여러 체인에서 돎: [q4-answer.md](sources/q4-answer.md) 47행
  - 에이전트용 두 표준은 Arc에 묶이지 않음: [q4-answer.md](sources/q4-answer.md) 48행
  - Arc만의 에이전트 기능은 설계나 로드맵 단계: [q4-answer.md](sources/q4-answer.md) 49행
  - 에이전트가 사업체가 된다는 말은 Base에도 있음: [q2-answer.md](sources/q2-answer.md) 215행
- <a id="ev-r49"></a>"Tameion 사례: 에이전트 공고 넷 가운데 사업체의 자금 업무를 내건 것은 Tameion뿐. 실제 사업에서 쓴 기록도 요구함"
  - 공고 넷 가운데 사업체의 자금 업무를 내건 것: [arc-event-product-themes-reading.md](sources/arc-event-product-themes-reading.md) 44-47행
  - 실제 사업 사용과 지급 기록 요구: [arc-event-product-themes-reading.md](sources/arc-event-product-themes-reading.md) 45행
  - 원문: [Tameion 공고](https://tameion.thecanteenapp.com/)의 "You will also be asked traction questions: how many businesses you have onboarded, how much value the agent moved"
- <a id="ev-r50"></a>"그래도 공고가 안내한 도구는 Agent Stack, Wallets, CCTP, Gateway 같은 개발자 도구이고, CPN과 StableFX는 공고에 나오지 않음"
  - 원문: [Tameion 공고](https://tameion.thecanteenapp.com/)의 "Circle's developer platform on Arc, the primitives suited to an agent that holds and disburses a company's money."
  - 공고 본문에 StableFX와 CPN이 나오지 않음: 이 문서 "Arc 해커톤들" 절 끝의 검색 기록(2026-10-08에 받은 공고 사본에 `rg -c 'StableFX|CPN'`, 0건)
- <a id="ev-r51"></a>"환전도 StableFX가 아니라 App Kit의 Swap 예제로 안내함"
  - 원문: [Tameion 공고](https://tameion.thecanteenapp.com/)의 "circlefin/arc-stablecoin-fx: USDC<->EURC FX swaps via the App Kit Swap SDK."
- <a id="ev-r52"></a>"다만 Tameion의 대상은 작은 사업체여서, 기관용 제품이 없는 것은 대상이 달라서일 수도 있음"
  - 원문: [Tameion 공고](https://tameion.thecanteenapp.com/)의 "Do I need a real business to build for?" / "Yes, and it can be a small one."

### 외부 AI Agent Payment 관련 해커톤들의 근거

- <a id="ev-r53"></a>"앞으로 열리는 행사 셋: TUM Blockchain & AI(10/30~31), ETHGlobal Mumbai(11/5~7), Agent Pay - MERGE Madrid(11/27~29)"
  - [agent-payment-hackathon-scout.md](sources/agent-payment-hackathon-scout.md) 198-216행
  - 일정의 공식 공고 대조: [aiagents-hackathon-official-notices.md](sources/aiagents-hackathon-official-notices.md) 22행(ETHGlobal Mumbai), 33행(MERGE)
- <a id="ev-r54"></a>"TUM Blockchain & AI: 뮌헨 현장 30시간, 약 200명. 주제가 "Agentic Payments""
  - [agent-payment-hackathon-scout.md](sources/agent-payment-hackathon-scout.md) 198-203행
  - 원문: [공고](https://tum.devfolio.co/)의 "The Theme: Agentic Payments", "30-hour build sprint", "~200 builders on site"
- <a id="ev-r55"></a>"ETHGlobal Mumbai: 이더리움 쪽의 범용 해커톤. 상금은 후원사 12곳이 각자 걸었고, Arc도 그중 하나(\$15,000)"
  - 일정: [aiagents-hackathon-official-notices.md](sources/aiagents-hackathon-official-notices.md) 22행
  - Arc 상금 15,000달러: [arc-all-events-reading.md](sources/arc-all-events-reading.md) 800행, [q7-answer.md](sources/q7-answer.md) 364행
  - 후원사 12곳: 원문 [상금 페이지](https://ethglobal.com/events/mumbai/prizes)의 "12" / "Prizes"와 후원사 목록(이 문서 "외부 AI Agent Payment 관련 해커톤들" 절 끝). `sources/` 안에는 없음
- <a id="ev-r56"></a>"Agent Pay - MERGE Madrid: 마드리드 현장 48시간. 주제는 Agent Commerce와 Agent Micropayments이고, 핀테크, 기업, 기관 쪽 청중이 함께 있음"
  - [agent-payment-hackathon-scout.md](sources/agent-payment-hackathon-scout.md) 211-216행
  - 2026-10-10에는 [해커톤 주소](https://www.mmerge.io/hackathon-2026)가 입장권 페이지로 넘어가서 공고 본문을 확인하지 못함: [aiagents-hackathon-official-notices.md](sources/aiagents-hackathon-official-notices.md) 33행. 10-15의 같은 확인은 이 문서 "외부 AI Agent Payment 관련 해커톤들" 절 끝에 적음
- <a id="ev-r57"></a>"Cronos x402 PayTech(결과 발표 2026-02): Cronos 체인의 x402 결제 앱 행사. 191개 제출"
  - [aiagents-hackathon-official-notices.md](sources/aiagents-hackathon-official-notices.md) 28행
  - 원문: [결과 발표 글](https://blog.cronos.com/p/announcing-the-cronos-x402-hackathon)의 "After reviewing 191 global submissions"
- <a id="ev-r58"></a>"Claw & Order: CKB AI Agent Hackathon(2026-03): CKB 체인 위의 에이전트 행사. 1위는 마일스톤마다 돈을 풀어 주는 에스크로와 지급 시스템"
  - [aiagents-hackathon-official-notices.md](sources/aiagents-hackathon-official-notices.md) 29행
  - 원문: [결과 발표 글](https://talk.nervos.org/t/claw-order-ckb-ai-agent-hackathon-results/10173)의 "PactAgent is a milestone-based escrow and payment system built on CKB"
- <a id="ev-r59"></a>"Agentic Dollars on Bitcoin(토리노, 10/17~18, 신청 마감): 비트코인 위의 달러로 하는 에이전트 결제. RGB와 QVAC를 반드시 써야 함"
  - [aiagents-hackathon-official-notices.md](sources/aiagents-hackathon-official-notices.md) 23행
  - 원문: [공고](https://rgbprotocol.org/agentic-dollars-hackathon/)의 "Applications closed", "RGB and QVAC are required for every project."

## 저의 결론의 근거

- 공개판 "저의 결론"의 줄을 따옴표 안에 그대로 옮기고, 그 아래에 근거를 둠. 줄과 근거를 짝지은 것은 에이전트
- 근거를 모으지 않은 줄은 "모은 자료 없음"으로 적음
- 소제목만 있는 줄(예: "제 개인적 판단", "중요 가치로 판단시")은 짝짓지 않음

### 머리말의 근거

- <a id="ev-c01"></a>"우리가 어떤 것에 가치를 크게 두는지에 따라 결정이 달라진다. 따라서, 우리가 해야 할 것은 무엇에 가치를 두느냐를 결정하는 것"
  - 모은 자료 없음
- <a id="ev-c02"></a>"지금까지 본 것 기반으로 중요 가치 대상들을 정리함"
  - 모은 자료 없음

### Circle의 근거

- <a id="ev-c03"></a>"정의: 기업 지급 결제의 문제와, 그것을 풀려는 Circle의 방향과 제품에 강한 확신을 가지는 경우 고려해야 할 대상"
  - 모은 자료 없음
- <a id="ev-c04"></a>"기업 지급 결제의 문제 세 가지"
  - 이 구분은 그 목차를 쓴 에이전트가 제안하고 사용자가 승인한 것: [circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 44행
- <a id="ev-c05"></a>"지급 지시와 실행: 지급 지시가 진짜인지, 승인한 대로 실행되는지"
  - [circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 50행
- <a id="ev-c06"></a>"수납 이후의 정산과 고객자금: 판매자에게 돈이 도착하는지, 장부가 실제 돈과 맞는지"
  - [circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 60행
- <a id="ev-c07"></a>"국경을 넘는 지급: 송금을 요청해도 상대방이 대금을 받을 수 있는지"
  - [circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 70행
- <a id="ev-c08"></a>"기업과 금융기관이 디지털 자산에 접근하고, 보관하고, 교환하고, 이동하는 기능을 연결"
  - [circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 110행, 114행
  - 그 목차가 기댄 원문: [Circle의 2026년 제품 비전](https://www.circle.com/blog/building-the-internet-financial-system-circles-product-vision-for-2026)
  - 네 동사에 제품을 짝지은 것은 아래 표의 설명을 보고 공개판을 쓰면서 정함. 목차는 같은 제품을 기업 업무의 순서로 늘어놓음([circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 129행)
- <a id="ev-c09"></a>"접근: Circle Mint (은행 자금과 USDC, EURC를 서로 바꿈)"
  - [circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 199행
- <a id="ev-c10"></a>"보관: Circle Wallets (지급 요청, 서명 승인, 키 관리)"
  - [circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 200행
- <a id="ev-c11"></a>"교환: StableFX (기관끼리의 환전)"
  - [circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 203행
- <a id="ev-c12"></a>"이동: CCTP (체인 사이의 이전), Gateway (여러 체인의 USDC를 한 잔액으로 다룸), CPN (국경을 넘는 지급과 수납)"
  - [circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 201행(CCTP), 202행(Gateway), 204행(CPN)
- <a id="ev-c13"></a>"기업 업무로는 지급, 외환, 자금 관리"
  - [circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 110행, 115행
- <a id="ev-c14"></a>"지급: CPN, CPN Managed Payments (Circle이 보관, 준법 처리, 온체인 운영을 대신 맡음)"
  - [circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 204행(CPN), 205행(CPN Managed Payments)
  - [CPN Managed Payments 문서](https://developers.circle.com/cpn/managed-payments.md): "CPN Managed Payments gives partners stablecoin settlement without needing in-house custody, compliance, or onchain systems."
- <a id="ev-c15"></a>"외환: StableFX, EURC"
  - [circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 203행(StableFX), 198행(EURC)
- <a id="ev-c16"></a>"자금 관리: USYC (토큰화한 머니마켓 펀드), Gateway, Circle Mint"
  - [circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 206행(USYC), 202행(Gateway), 199행(Circle Mint)
- <a id="ev-c17"></a>"기회: 국내에 Circle 전문가가 없음"
  - 모은 자료 없음
- <a id="ev-c18"></a>"Circle의 현재 상태와 하려는 것의 방향은 잘 가고 있음"
  - 모은 자료 없음
- <a id="ev-c19"></a>"문제 세 가지 가운데 국경을 넘는 지급은 실제로 크고, 크기가 측정되어 있음: 해외 지급 비용 1.6% 가운데 외환이 1.4%, 마지막 구간이 지급 시간의 80% 넘게 차지"
  - [q1-answer.md](sources/q1-answer.md) 567-577행(FSB 2025와 SWIFT의 표)
  - 원문: [FSB 2025 보고서](https://www.fsb.org/uploads/P091025-1.pdf), [SWIFT 안내](https://www.swift.com/payments/how-long-does-swift-payment-take)
- <a id="ev-c20"></a>"Circle의 애플리케이션(CPN, StableFX)이 이 문제(해외 지급과 환전)를 직접 겨냥함"
  - CPN: 공시의 "move money using stablecoins starting with cross-border payments" ([circle-company-survey-answer.md](sources/circle-company-survey-answer.md) 1125행)
  - StableFX: 상대방마다 계약하고 신용 한도를 정해야 하는 부담을 줄이려는 정산 방식 ([circle-company-survey-answer.md](sources/circle-company-survey-answer.md) 1186행)
  - 외환 비용과 StableFX: [q1-answer.md](sources/q1-answer.md) 579-589행
- <a id="ev-c21"></a>"다만 스테이블코인으로 옮긴 기업은 아직 적음"
  - [q1-answer.md](sources/q1-answer.md) 797-812행
  - 원문: 이 문서 "Circle의 사업" 절의 조사 표에 적은 공개 조사 여덟 건의 주소
- <a id="ev-c22"></a>"Circle의 에이전트 쪽: 현재 상태와 하려는 것의 방향에 물음표가 남음"
  - 모은 자료 없음
- <a id="ev-c23"></a>"Circle은 에이전트가 결제하는 기능(상반기 출시)에서 에이전트가 일을 팔아 버는 기능(하반기 계획)으로 가려 함. 2Q 발표 "from agent payment rail to agent labor market""
  - [q3-answer.md](sources/q3-answer.md) 266-300행
  - 원문: [2026년 2분기 발표 자료](https://s206.q4cdn.com/265218871/files/doc_presentations/2026/Aug/05/Q2-2026-Earnings-Presentation.pdf)
- <a id="ev-c24"></a>"이 방향은 기존 고객과 제품의 문제를 푸는 쪽이 아님"
  - [q3-answer.md](sources/q3-answer.md) 38-42행(지금의 에이전트 제품이 푸는 두 문제, 주된 고객의 문제에는 아직 붙지 않음)
- <a id="ev-c25"></a>"Nanopayments: Circle만의 엣지인가? No"
  - 모아서 정산하는 방식은 Coinbase CDP Facilitator에도 있음: [circle-agentic-payments-reading.md](sources/circle-agentic-payments-reading.md) 151행
  - 원문: [Coinbase CDP Facilitator 문서](https://docs.cdp.coinbase.com/x402/core-concepts/facilitator.md)
- <a id="ev-c26"></a>"Nanopayments: Circle이 해결하려는 문제와 해결 방법에 맞닿아 있는가? No"
  - 주된 고객의 문제에는 에이전트 제품이 아직 붙지 않음: [q3-answer.md](sources/q3-answer.md) 41행
  - 에이전트 결제가 바꾼 것은 두 고객까지이고, 기존 고객의 돈이 에이전트를 거쳐 움직이는 일은 아직 없음: [q5-answer.md](sources/q5-answer.md) 42-44행, 56-73행
- <a id="ev-c27"></a>"Circle만이 그리는 AI Agent 청사진이 있는가? No"
  - 지금의 에이전트 제품은 Arc를 포함한 여러 체인에서 돌고, Arc만의 에이전트 기능은 설계나 로드맵에 있음: [q4-answer.md](sources/q4-answer.md) 47-50행
  - 에이전트가 일을 팔아 사업체가 된다는 말은 Base에도 있음: [q2-answer.md](sources/q2-answer.md) 215행
- <a id="ev-c28"></a>"제가 그리는 쪽: Circle이 이미 가진 제품(CPN, Managed Payments, StableFX, App Kits)에 에이전트가 들어가는 것"
  - 고객별로 회사가 말한 에이전트의 역할과 상태(CPN은 계획 단계, Managed Payments와 StableFX에는 에이전트 이야기가 없음): [q1-answer.md](sources/q1-answer.md) 969-981행
- <a id="ev-c29"></a>"but, not yet"
  - 위와 같음: [q1-answer.md](sources/q1-answer.md) 969-981행
- <a id="ev-c30"></a>"실망스럽긴함. 타기업과 비교했을 때 기대되는게 없음"
  - 다른 회사와의 비교: [q2-answer.md](sources/q2-answer.md) 212-215행, [circle-agentic-payments-reading.md](sources/circle-agentic-payments-reading.md) 143-154행
- <a id="ev-c31"></a>"Arc 행사 가운데 Circle 제품(CPN, StableFX 등)을 다루는 행사에 참여해야 함"
  - CPN, StableFX를 다룬 행사는 기업 금융 해커톤: [arc-all-events-reading.md](sources/arc-all-events-reading.md) 6531-6534행
  - 원문: [Arc x Encode Enterprise & DeFi 공고](https://community.arc.io/public/events/arc-x-encode-enterprise-and-defi-hackathon-vcm38l2yye)

### Arc의 근거

- <a id="ev-c32"></a>"정의: 기관 금융을 위한 정산 네트워크인 Arc 네트워크에 대한 강한 확신을 가지는 경우 고려해야 할 대상"
  - "기관 금융을 위한 Circle 주도의 정산 네트워크"라는 시각: [q4-answer.md](sources/q4-answer.md) 38행, 517-525행
- <a id="ev-c33"></a>"Circle과의 관계: Arc가 해결하는 것은 Circle이 원래 해결하려던 것의 일부"
  - [q1-answer.md](sources/q1-answer.md) 579-589행(Arc가 맡는 몫은 문제마다 일부 구간)
- <a id="ev-c34"></a>"Circle은 Arc를 자사 애플리케이션의 조정을 위한 기반으로 만들려는 방향을 제시"
  - [circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 170행
  - 그 목차가 기댄 원문: [Circle의 2026년 제품 비전](https://www.circle.com/blog/building-the-internet-financial-system-circles-product-vision-for-2026)
- <a id="ev-c35"></a>"전체 제품군에서 Arc의 몫은 일부: 자산 이전과 계약 실행 결과를 처리하고 기록을 확정"
  - [circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 196행
- <a id="ev-c36"></a>"Circle과 떼어 Arc만 고를 수도 있음: Arc는 Circle 제품의 기반이면서, 따로 토큰과 지분으로 값을 얻는 사업이기 때문"
  - "토큰과 지분으로 값을 얻는 네트워크 사업"이라는 시각: [q4-answer.md](sources/q4-answer.md) 38행, 517-525행
  - ARC 토큰 사전판매 약 2억 4,220만 달러와 조건: [q4-answer.md](sources/q4-answer.md) 416-422행
- <a id="ev-c37"></a>"기회: 국내에 Arc 전문가가 없음"
  - 모은 자료 없음
- <a id="ev-c38"></a>"Arc Architect가 된다면, 에어드롭 가능성이 있음"
  - Arc Architects 프로그램: [circle-arc-public-material-outline.md](sources/circle-arc-public-material-outline.md) 269행
  - Arc House 1등급 혜택의 Architect 행사: [q7-answer.md](sources/q7-answer.md) 164행
  - 에어드롭: 모은 자료 없음
- <a id="ev-c39"></a>"조사하면 할수록 깨닫는 것은, 생각보다 Arc 자체가 Circle 안에서 큰 영향력을 갖지 않음"
  - 회사 쪽에서 본 2026년의 Arc: [q4-answer.md](sources/q4-answer.md) 437-438행
  - 소개의 무게는 기관 금융 쪽: [q4-answer.md](sources/q4-answer.md) 163행
- <a id="ev-c40"></a>"하지만, 그것은 Circle이 뉴욕증권거래소(NYSE)에 상장된 나름 거대(?) 기업이라는 것을 감안할 때는 그게 오히려 맞음"
  - 모은 자료 없음
- <a id="ev-c41"></a>"Arc 자체는 Circle 기업의 입장에서는 잘 되면 정말 좋은, 나쁠 것 없는 아이템"
  - 모은 자료 없음
- <a id="ev-c42"></a>"하지만 Agent 라는 눈으로 봤을 때 Arc만의 것은 아직 없음. Arc만의 에이전트 관련 무언가는 현재 설계나 로드맵 단계"
  - [q4-answer.md](sources/q4-answer.md) 47-50행
- <a id="ev-c43"></a>"Arc 라는 메인넷과 Arc House 라는 곳에서의 활약이 낫다고 판단되면 나쁠 것 없음"
  - Arc House 점수와 등급별 혜택: [q7-answer.md](sources/q7-answer.md) 163-164행
- <a id="ev-c44"></a>"물론 이 안에는 메인넷의 폭발적 성장과 토큰 가치의 폭등 그리고 에어드롭의 가능성이 있어야만 현실적으로 좋은 옵션이 됨"
  - 모은 자료 없음
- <a id="ev-c45"></a>"굳이 AI agent 에 목매지 말고, 모든 Arc 행사에 참여해야 함"
  - Arc 커뮤니티 페이지의 이벤트 카드 178개: [arc-events-complete-README.md](sources/arc-events-complete-README.md) 10행
  - Arc House는 해커톤 참가에 500점, 수상에 1,000점을 줌: [q7-answer.md](sources/q7-answer.md) 163행

### AI Agent Payment의 근거

- <a id="ev-c46"></a>"에이전트가 돈을 내고 받는 일 자체(기업의 지급 결제 문제가 포함되겠지만, 그것으로 범위를 좁혀서 생각하는 게 아닌)에 확신을 가지는 경우 고려해야 할 대상"
  - 모은 자료 없음
- <a id="ev-c47"></a>"따라서, 어느 회사의 제품 위에서 Agent Payment 관련 작업을 하든 상관없음"
  - 모은 자료 없음
- <a id="ev-c48"></a>"시장은 아직 작음: x402와 MPP를 합친 2026-08 한 달 금액이 \$643,721"
  - [q5-answer.md](sources/q5-answer.md) 33-39행
- <a id="ev-c49"></a>"카드사와 결제 회사도 관련 제품을 내놓고 있음: Visa Trusted Agent Protocol, Mastercard Agent Pay, Stripe Radar, Google AP2, Coinbase CDP"
  - 원문: [Visa 보도자료](https://corporate.visa.com/en/sites/visa-perspectives/newsroom/visa-partners-complete-secure-agentic-transactions.html), [Mastercard 보도자료](https://s25.q4cdn.com/479285134/files/doc_news/Mastercard-Unveils-Agent-Pay-Pioneering-Agentic-Payments-Technology-to-Power-Commerce-in-the-Age-of-AI-2025.pdf), [Stripe 블로그](https://stripe.com/blog/everything-we-announced-at-sessions-2026), [Google Cloud 블로그](https://cloud.google.com/blog/products/ai-machine-learning/announcing-agents-to-payments-ap2-protocol), [Coinbase 개발자 문서](https://docs.cdp.coinbase.com/agentic-wallet/cli/welcome.md)
  - 회사마다 에이전트를 가려내는 자리: [q2-answer.md](sources/q2-answer.md) 416-444행
- <a id="ev-c50"></a>"결제 협상 방식(x402)은 회사마다 같고, 정산(settlement) 방식이 다름"
  - [circle-agentic-payments-reading.md](sources/circle-agentic-payments-reading.md) 143-154행
  - 원문: [Circle 개발자 문서 "What is x402?"](https://developers.circle.com/gateway/nanopayments/concepts/x402.md)
- <a id="ev-c51"></a>"이 부분이 Circle의 매출로 이어지는지는 지금 판단할 수 없음"
  - [q5-answer.md](sources/q5-answer.md) 40-41행(에이전트가 쥔 잔액의 숫자가 없음)
- <a id="ev-c52"></a>"기회: AI Agent 자체가 태동되는 시기여서, 결제 관련 제품은 나오고 있지만 실제로 쓰이는 결제는 아직 작음"
  - [q5-answer.md](sources/q5-answer.md) 33-39행
- <a id="ev-c53"></a>"현재 상태로는 사실 맨땅에 해당하는 그런 영역"
  - 모은 자료 없음
- <a id="ev-c54"></a>"유즈 케이스에 대해 계속 주장해야되며,"
  - 모은 자료 없음
- <a id="ev-c55"></a>"어떤 기술 스택이 부족한지를 유즈 케이스를 상상하며 직접 진행해야 함"
  - 모은 자료 없음
- <a id="ev-c56"></a>"Circle/Arc 말고도 실제 이것에 대한 고려를 하는 것은 오히려 Visa/Master/Stripe 등 실제 결제 담당자들이기 때문에 오히려 이쪽으로 우회하는게 더 나을수도 있음"
  - 돈을 받는 쪽에서 에이전트를 가려내는 것은 Mastercard, Visa, Stripe: [q2-answer.md](sources/q2-answer.md) 416-444행
- <a id="ev-c57"></a>"Circle/Arc 행사에 묶이지 말고, 외부 AI Agent Payment 행사까지 나가야 함"
  - 외부 행사의 조사와 공고 대조: [agent-payment-hackathon-scout.md](sources/agent-payment-hackathon-scout.md) 198-216행, [aiagents-hackathon-official-notices.md](sources/aiagents-hackathon-official-notices.md) 22-33행

### AI Agent의 근거

- <a id="ev-c58"></a>"에이전트가 사람을 대신해 많은 업무를 자동화하고 판정까지 맡는 방향에 대한 확신을 가지는 경우 고려해야 할 대상"
  - 모은 자료 없음
- <a id="ev-c59"></a>"이 안에 Agent Payment가 포함될 수 있음. 하지만, Circle이나 Arc에 묶이지 않음"
  - 모은 자료 없음
- <a id="ev-c60"></a>"Arc 밖에도 에이전트 해커톤이 열림: TUM Blockchain & AI(10/30~31), ETHGlobal Mumbai(11/5~7), Agent Pay - MERGE Madrid(11/27~29)"
  - [agent-payment-hackathon-scout.md](sources/agent-payment-hackathon-scout.md) 198-216행, [aiagents-hackathon-official-notices.md](sources/aiagents-hackathon-official-notices.md) 22행, 33행
  - 원문: [TUM 공고](https://tum.devfolio.co/), [ETHGlobal Mumbai 상금 페이지](https://ethglobal.com/events/mumbai/prizes), [MERGE 해커톤 주소](https://www.mmerge.io/hackathon-2026)
- <a id="ev-c61"></a>"다만 상금은 대부분 특정 체인이나 회사의 것: TUM은 공개된 상금 전부가 BSV와 Cardano 트랙이고, ETHGlobal은 상금 12개가 모두 후원사 상금임"
  - 원문: [TUM 공고](https://tum.devfolio.co/)의 "\$10,000 Available in Prizes"와 그 아래 트랙 둘(BSV Blockchain \$4,000, Cardano \$6,000), [ETHGlobal Mumbai 상금 페이지](https://ethglobal.com/events/mumbai/prizes)의 후원사 12곳
- <a id="ev-c62"></a>"기회: 태동하고 있으며 이미 진행 중. 아직도 폭발적 성장의 가능성은 있음"
  - 모은 자료 없음
- <a id="ev-c63"></a>"가장 무난하다고 할 수 있음. 그런데 이걸 또한 질문해봐야 함"
  - 모은 자료 없음
- <a id="ev-c64"></a>"CURG는 블록체인 학회인데 그냥 AI Agent라면 이게 어떤 의미를 갖는지 고민해야 함"
  - 모은 자료 없음
- <a id="ev-c65"></a>"물론 이것을 선택하고 Agent Payment 틈틈이 할 수 있음"
  - 모은 자료 없음
- <a id="ev-c66"></a>"그것은 우리의 자유"
  - 모은 자료 없음
- <a id="ev-c67"></a>"Circle/Arc 행사에 묶이지 말고, 외부 AI Agent 행사까지 나가야 함"
  - [agent-payment-hackathon-scout.md](sources/agent-payment-hackathon-scout.md) 198-216행, [aiagents-hackathon-official-notices.md](sources/aiagents-hackathon-official-notices.md) 22-33행
