---
date: 2026-09-28
type: analysis
tags: [business, blockchain, stablecoin]
status: review
source:
  - cb/works/circle-blog/2025-11-07-blog-circle-payments-network-cpn-a-concise-field-guide-for-prospective-network-participants/raw/2026-09-28T110123824601Z/circle-payments-network-cpn-a-concise-field-guide-for-prospective-network-participants.html
  - cb/works/circle-blog/2026-03-20-blog-a-deep-dive-into-circle-nanopayments-gas-free-usdc-transfers/raw/2026-09-28T110125140763Z/a-deep-dive-into-circle-nanopayments-gas-free-usdc-transfers.html
  - cb/works/circle-blog/2026-07-02-blog-build-a-voice-call-automation-with-circle-agent-wallet-ai-assistants/raw/2026-09-28T111117102751Z/build-a-voice-call-automation-with-circle-agent-wallet-ai-assistants.html
  - cb/works/circle-blog/2026-08-12-blog-building-the-open-agentic-economy/raw/2026-09-28T110125638903Z/building-the-open-agentic-economy.html
  - cb/works/web/2026-10-15-nanopayments-and-alternatives-primary/raw/circle-docs-gateway-nanopayments-concepts-x402.md
  - cb/works/web/2026-10-15-nanopayments-and-alternatives-primary/raw/docs-cdp-coinbase-com-x402-core-concepts-facilitator.md
  - cb/works/web/2026-10-15-nanopayments-and-alternatives-primary/raw/circle-docs-gateway-nanopayments.md
  - cb/works/web/2026-10-15-nanopayments-and-alternatives-primary/raw/circle-docs-gateway-nanopayments-concepts-batched-settlement.md
  - cb/works/web/2026-10-15-nanopayments-and-alternatives-primary/raw/docs-x402-org-schemes-overview.md
  - cb/works/web/2026-10-15-nanopayments-and-alternatives-primary/raw/docs-x402-org-schemes-batch-settlement.md
  - cb/works/web/2026-10-15-nanopayments-and-alternatives-primary/raw/docs-x402-org-dev-tools-facilitators.md
  - cb/works/web/2026-10-15-nanopayments-and-alternatives-primary/raw/mpp-dev-faq.md
  - cb/works/web/2026-10-06-machine-economy-primary/raw/d1-003-blog-cloudflare-com.html
analysis_runs:
  - date: 2026-09-28
    tool: codex
    model: gpt-6-sol
    model_class: deep-reasoning
    reasoning: high
    scope: "네 Circle 블로그 글 전체의 이해와 선택 판독; 본문 관찰 일부는 gpt-6-sol medium 하위 에이전트가 수행하고, 판정과 문서는 주 에이전트가 작성"
  - date: 2026-10-01
    tool: codex
    model: unknown
    model_class: unknown
    reasoning: unknown
    scope: "연결 검토. 기존 판독 전체를 읽고 네 자료가 다루는 기관 지급, 확인과 배치 정산, 통화 예제의 사람 권한 및 시장 비전을 비교표로 설명했다. 개념 이해 문서와 판독의 질문을 구별하여 연결했다. 기존 원장, 감사와 채택 및 보류의 판단은 유지했다. 표로 충분하여 그림을 추가하지 않았고 원본 HTML이나 현재 구현을 다시 검증한 실행으로 기록하지 않는다"
  - date: 2026-10-15
    tool: claude-code
    model: claude-opus-5-5
    model_class: deep-reasoning
    reasoning: unknown
    scope: "x402 정산 방식 비교 절을 더했다. Circle, Coinbase, x402 재단, MPP의 공식 문서 여덟 개와 Cloudflare 블로그 한 편을 주 에이전트가 읽고 썼으며, 인용과 숫자는 verifier 하위 에이전트가 원문과 대조했다. 기존 절의 판정은 바꾸지 않았다. 같은 실행에서 문서 전체의 영어판(circle-agentic-payments-reading.en.md)을 만들었다"
---

# Circle Payments Network(CPN), 나노결제와 에이전트 경제 글 판독

영어판은 범위가 같다.

## 한 문장 결론

네 글은 Circle이 설계하거나 제공한다고 밝힌 결제, 에이전트 제품과 아직 실현되지 않은 시장 구상을 함께 설명하며, 현재 작동 상태와 상업적 성과는 이 글들만으로 확인되지 않는다.

## 무엇을 함께 읽으며 왜 구별해야 하는가

이 판독은 CPN(Circle Payments Network)의 기관 지급, Nanopayments의 소액 확인과 배치 정산, Agent Wallet(에이전트용 지갑)을 이용하는 통화 자동화 예제 및 열린 에이전트 경제의 비전을 비교한다. 이들은 모두 결제와 자동화를 다루지만 같은 제품의 연속 단계는 아니다. 기관 역할, 확인 및 정산 시점, 사람의 권한과 시장 형성의 조건을 구별하는 것이 이 문서의 주제다.

아래 표는 기존 자료 역할 지도와 주장 원장의 내용을 입력, 행동과 결과에 따라 다시 정리한 것이다. 이 구분은 이 문서의 설명 구성이다. 별도 그림 없이 표에서 관계와 확인 범위를 읽을 수 있으므로 그림을 추가하지 않는다.

| 설명 대상 | 누가 무엇을 처리하는가 | 구별해야 하는 결과와 조건 |
|---|---|---|
| CPN의 지급 서비스 | 송금 시작 금융기관(OFI)이 현지 통화를 수납하고 스테이블코인을 보내며, 수취 금융기관(BFI)이 수취인에게 현지 통화를 지급한다. | 기관 사이 온체인 정산과 최종 이용자에게 지급하는 행동은 구별한다. 소개 글만으로 실제 비용과 속도 우위를 입증하지 않는다. |
| Nanopayments의 확인 및 정산 | 지급자가 서명한 소액 지급을 오프체인에서 확인하고, 모은 지급을 배치로 온체인 정산한다. | 확인 응답 뒤 디지털 자원을 제공할 수 있다는 설명과 배치 확정 뒤 온체인 잔액이 갱신되는 시점은 구별한다. 지급자 가스비와 배치 가스비도 다르다. |
| 통화 자동화 예제 | 사람이 지갑과 정책 설정에 인증하고 시험 통화를 확인한 뒤, 에이전트가 외부 서비스를 이용하도록 안내한다. | 예제의 실행 요청은 실제 통화 성공이나 무제한 자율 권한의 증거가 아니다. 인증 만료와 상태 변경에 따른 중지 조건을 유지한다. |
| 열린 에이전트 경제 비전 | Circle이 에이전트가 서비스를 찾고 구매하는 시장과 신뢰 가능한 발견을 제안한다. | 비전은 제품 발표나 출시 약속과 다르다. 서비스 수가 곧 품질이나 지속적인 수요를 입증하는 것은 아니다. |

오프체인 확인과 온체인 정산을 구별하는 이유는 디지털 자원 제공의 판단 시점과 자금 잔액 갱신의 시점이 다르기 때문이다. 그렇다고 확인 응답이 무의미하다고 판정하는 것도 아니다. 기존 판독은 Circle이 설명하는 동작을 채택하면서 구현과 운영 신뢰를 별도 검증 대상으로 남긴다.

제품 개념과 기능은 에이전트 경제 이해 문서에서 이어 읽을 수 있다. 이 판독은 그 설명을 독립 성과로 받아들일 수 있는지와 어떤 결론을 보류해야 하는지를 기록한다. 이번 연결 검토는 기존 판정과 한정 문구를 보존했으며, 원본 HTML이나 현재 제품 동작을 새로 검증한 것은 아니다.

## 자료 역할 지도

| 자료 | 역할과 한계 |
|---|---|
| Circle, 2025-11-07, Circle Payments Network(CPN, Circle의 기관 간 결제망) 참여자 안내 글 (영어 본문, 원본 HTML) | Circle의 공식 제품 설명이다. 송금 시작 금융기관(Originating Financial Institution, OFI), 수취 금융기관(Beneficiary Financial Institution, BFI), 온체인 정산과 오프체인 정보 교환을 설명하지만, 실제 비용, 속도 비교나 참여 기관의 운영 성과를 입증하지 않는다. |
| Circle, 2026-03-20, Circle Nanopayments(소액 결제를 오프체인에서 모아 온체인으로 정산하는 제품) 기술 설명 (영어 본문, 원본 HTML) | Circle의 자체 메커니즘 설명이다. 서명, 오프체인 잔액, 신뢰 실행 환경(TEE), 배치 정산의 관계를 서술하지만 실제 구현과 보안은 독립 검증하지 않는다. |
| Circle, 2026-07-02, 음성 통화 자동화 예제 (영어 본문, 원본 HTML) | Circle Agent Wallet(에이전트용 지갑)과 외부 서비스를 연결하는 사용 안내다. 실행 전 승인과 중단 조건을 설명하지만, 예제는 실제 성공 기록이나 일반적인 신뢰성 측정이 아니다. |
| Circle, 2026-08-12, 에이전트가 서비스를 사고파는 열린 경제(open agentic economy) 비전 글 (영어 본문, 원본 HTML) | Circle의 비전과 초기 구상을 제시한다. 글은 스스로 제품 발표나 약속이 아니라고 한정하므로 로드맵이나 구현 보장으로 읽을 수 없다. |

네 글 모두 Circle이 자사 제품과 전략을 설명하는 자료다. 서로 다른 날짜와 글 형식이지만 같은 조직의 이해관계를 공유한다. 따라서 반복되는 설명은 Circle의 일관된 자기 설명이지, 독립된 확인 여러 건이 아니다.

## 주장 원장

| 위치 | 유형과 Circle의 주장 | 근거 | 판정과 확신 | 시간 민감도와 확인 경로 |
|---|---|---|---|
| CPN 글, `How CPN works, end to end` | 메커니즘: OFI가 발신자의 현지 통화를 모아 스테이블코인으로 바꾸고 BFI가 수취인에게 현지 통화로 지급한다. | "OFIs collect funds from senders in local currencies, convert them to stablecoins, and send them to BFIs, which pay out receivers in their respective currencies." | 글의 설계 설명으로 확인, 확신 높음. 실제 참여자의 역할 수행과 결과는 미검증. | 구조 변경에 민감하다. 영어 본문 해당 절을 원본 HTML과 대조했다. |
| CPN 글, `Roles: OFIs, BFIs, and the broader ecosystem of service providers` | 계획, 초안: 유동성, 외환, 보고, 지갑 제공자를 추가할 것으로 예상한다. | "we anticipate onboarding providers that offer liquidity, FX venues, reporting systems, wallet infrastructure" | 미래형 문구라는 점은 확인, 확신 높음. 현재 제공 중인 서비스 전체 목록으로 바꾸어 읽지 않는다. | 온보딩 시점에 민감하다. 영어 본문의 같은 절과 원본 HTML을 대조했다. |
| Nanopayments 글, `Gas economics` | 메커니즘: 지급자는 개별 소액 전송의 가스비를 내지 않지만 배치 정산에는 가스 비용이 든다. | "gas free to the payer, while still incurring gas costs at the batch settlement level." | 글의 비용 구조 설명으로 확인, 확신 높음. 우선 처리 수수료는 표에서 제외됐다고 글이 밝힌다. | 실제 수수료는 네트워크와 시점에 민감하다. 영어 본문 해당 절과 표 각주를 원본 HTML과 대조했다. |
| Nanopayments 글, `Verify instantly` 및 `Settle onchain asynchronously` | 메커니즘: API 응답은 오프체인 확인 직후 반환할 수 있고, 온체인 잔액 갱신은 배치 최종화 뒤에 일어난다. | "the payment is final, so the API response or digital resource can be released immediately." / "Once that batch finalizes, the corresponding onchain balances are updated" | Circle이 설명하는 확인과 최종 정산의 구분으로 채택, 확신 높음. 운영 신뢰는 외부 증거로 검증하지 않았다. | 제품 구현 변경에 민감하다. 영어 본문 두 절과 원본 HTML을 대조했다. |
| 음성 통화 글, `Prerequisites`, 설정 예제와 반복 실행 지침 | 메커니즘: 지갑 생성 및 정책 변경에 사람의 이메일 OTP가 필요하며, 첫 시험 통화도 확인 후 실행하고 상태가 바뀌면 반복 실행을 멈춘다. | "Authentication is email OTP-based, and sessions expire after 28 days"; "Place one short test call only after I confirm." | 글의 절차 설명으로 확인, 확신 높음. 실제 자동화 실행은 미검증이다. | API와 도구 버전에 민감하다. 영어 본문과 설정 코드의 문구를 원본 HTML과 대조했다. |
| 열린 경제 비전 글, `About this paper` | 계획, 초안: 글은 비전 문서이며 제품 약속이 아니고, 발견 순위 구상은 바뀌거나 구현되지 않을 수 있다. | "This is a vision paper offered for discussion. It describes an open direction, not a product announcement or commitment." / "The discovery ranking described in Section 04 is preliminary and may change or never be implemented." | Circle 자신의 명시적 한정으로 확인, 확신 높음. | 현재 제품 상태의 증거로 쓰지 않는다. 영어 본문 고지와 원본 HTML을 대조했다. |
| 열린 경제 비전 글, `The stack: what an open agent economy requires` | 공식 자기규정: 신뢰할 수 있는 검색과 순위가 아직 빠진 층이라고 말한다. | "The capstone, trusted discovery, is still missing." | 글이 작성된 시점에 대한 Circle의 진술로 채택, 확신 높음. 이후 구현 여부는 별도 확인이 필요하다. | 제품 상태에 민감하다. 영어 본문 해당 절과 원본 HTML을 대조했다. |

## 독립성과 이해관계 감사

이 자료군 안에는 Circle과 독립된 제품 관찰자나 운영 기록이 없다. CPN 안내문과 비전 글은 같은 회사의 결제 및 에이전트 시장 구상을 설명하고, Nanopayments 글과 통화 자동화 안내는 자사 기술과 도구의 사용을 권한다. 그러므로 네 글이 함께 말하는 즉시성, 저비용, 생태계 확장성은 외부 성과 자료로 확인되지 않았다.

글 안에서 확인되는 제한 문구는 판독에 중요하다. CPN 글은 일부 서비스 제공자를 앞으로 추가할 것으로 예상한다고 쓴다. Nanopayments 비용 비교는 우선 수수료를 제외한다. 통화 자동화 글은 사람의 승인과 상태 변화 때 중지를 요구한다. 비전 글은 제품 발표가 아니며 순위 구상이 구현되지 않을 수도 있다고 말한다. 이 한정은 Circle의 설명 범위를 좁히지만, 그 설명을 독립 검증하지는 않는다.

## 충돌과 논리 사다리

네 글 사이에 직접적인 사실 충돌은 찾지 못했다. 다만 독자가 과도하게 이어 읽을 수 있는 연결이 있다.

1. Nanopayments는 오프체인에서 즉시 결제 확인을 제공한다고 Circle이 설명한다. 이 메커니즘 설명은 글 안에서 **지원됨**.
2. 확인 응답을 받은 판매자가 디지털 자원을 즉시 내줄 수 있다. Circle의 구현 예시로 **가능성은 있음**.
3. 따라서 지연 없는 확인이 독립 보안이나 최종 정산과 동등하다. 글은 이를 입증하지 않으므로 **근거 없음**.
4. 글의 기본 수수료 표가 실제 전체 비용 우위를 보여 준다. 우선 처리 수수료를 제외했다고 각주에 적혀 있어 **성립하지 않음**.

또한 에이전트가 서비스를 구매하고 외부 업무를 수행할 수 있다는 시연에서 시장의 자율 노동이나 신뢰 가능한 서비스 검색이 이미 성립했다고 추론할 수 없다. 비전 글 스스로 신뢰 가능한 발견 계층이 빠졌다고 한다. 거래량, 독립 구매자, 서비스 품질, 분쟁 해결이 연결되는 근거가 더 필요하다.

## 선택 검증

### 검증 범위와 기준

주요 검증 기준은 Circle 글이 현재 기능, 미래 계획, 예시, 성과를 구별해 쓰는지다. 네 영어 본문을 전부 읽고 원본 HTML 및 추출본을 대조한 뒤, 주요 메커니즘과 한정 문구를 선택 검증했다. 이번 검증은 외부 제품 문서나 코드 저장소를 추가로 열지 않았으므로 작동 상태의 독립 검증을 뜻하지 않는다.

### 미검증 잔여

- CPN의 실제 처리 속도, 비용 우위, 참여 기관 수와 현재 온보딩 상태.
- Nanopayments의 TEE 위협 모델, 배치 실패, 정산 지연 시 복구, 실제 단위 비용과 사용량.
- 음성 통화 자동화 예제가 현재 API와 도구 버전에서 재현되는지, 전화 구매, 통화 비용과 외부 서비스의 성능.
- 열린 경제 비전 글의 900여 서비스, x402(HTTP 요청에 결제 조건을 붙이는 방식) 결제 점유율 및 거래 통계, 추천 순위 구현 상태. 이 글에 연결된 외부 근거와 링크는 이번 판독에서 열지 않았다.
- 서로 다른 제품을 하나의 통합된 Circle agent economy로 묶을 수 있는지, 그 구조가 실제 고객의 수요나 매출로 이어지는지.

## 채택과 보류

### 채택해도 되는 이해

- Circle의 CPN 설명은 기관 간 현지 통화 수납, 스테이블코인 이동, 현지 통화 지급의 역할 구분을 제시한다.
- Circle의 Nanopayments 설명은 지급자 가스비와 배치 정산 가스비를 구분하고, 오프체인 확인과 온체인 잔액 갱신의 시점을 나눈다.
- 음성 통화 자동화 예제는 사람 승인, 인증 만료와 반복 실행의 중지 조건을 포함한다.
- Circle은 신뢰할 수 있는 에이전트 서비스 검색을 아직 미완성으로 설명하며, 순위 구상에 구현 보장을 하지 않는다.

### 보류해야 하는 결론

- 실제로 CPN이 기존 결제망보다 싸거나 빠르다는 결론.
- TEE 설명만으로 Nanopayments가 무신뢰 또는 독립 검증된 결제라는 결론.
- 자동화 예제가 제품의 안정성, 자율 실행 범위 또는 제3자 서비스의 품질을 보장한다는 결론.
- Circle의 비전 글이 시장의 형성이나 제품 출시 시기를 약속한다는 결론.
- 거래량이나 등록 서비스 수가 품질, 지속적인 수요 또는 Circle의 가치 포착을 증명한다는 결론.

## x402 정산 방식: Circle, Coinbase, Cloudflare는 같은 방식으로 처리하는가 (2026-10-15 추가)

Arc AI 에이전트 해커톤 지원 판단 대화에서 사용자가 "Circle의 x402를 이용하는 방식은 다른 이런 식의 결제를 지원하는 회사들도 같은 방식으로 처리하고 있는가?"라고 물었다. 이 절은 그 물음에 대한 답이다. 위 절들은 Circle 블로그 네 편을 읽었고, 이 절은 2026-10-15에 받은 공식 문서와 Cloudflare 블로그 한 편을 쓴다. 아래에서 `N/`은 `cb/works/web/2026-10-15-nanopayments-and-alternatives-primary/pages/`를 줄인 것이다.

### 협상과 정산: x402가 정하는 것과 정하지 않는 것

이 절은 x402 결제를 협상과 정산 둘로 나누어 비교한다. 이 구분은 이 문서가 고른 것이지만, Circle 문서가 스스로 x402를 이렇게 한정한다: "x402 is not a payment system itself. It is a negotiation protocol, agnostic to how payments are constructed, verified, or settled."(`N/circle-docs-gateway-nanopayments-concepts-x402.md` 27-28행). 판매자가 402 응답으로 값을 알리고 사는 쪽이 서명해서 다시 요청하는 데까지가 x402이고, 돈을 언제 어떻게 옮길지는 facilitator(결제를 검증하고 정산해 주는 운영 서비스)와 결제 방식(scheme)이 정한다. 그래서 협상은 회사마다 같고, 정산은 회사마다 다르다.

### 회사별 정산: 건마다 정산, 모아서 정산, 미뤄서 청구

| 장치 | x402 방식(scheme) | 돈이 움직이는 방식 | 근거 |
|---|---|---|---|
| Circle Facilitator Service | `exact`(일부 망은 `upto`) | 결제 한 건마다 Circle relayer가 온체인 정산하고, 가스는 Circle이 낸다 | `N/circle-docs-gateway-nanopayments-concepts-x402.md` 30-32, 130, 134-135, 150행 |
| Circle Gateway Nanopayments | `exact`(서명 대상만 `GatewayWalletBatched`) | 사는 쪽이 Gateway 잔액에서 내고, Circle이 모아서 순액만 온체인 정산한다 | 같은 문서 130-132, 164-172행 |
| Coinbase CDP Facilitator | `exact`, `upto`, `batch-settlement` | `exact`와 EVM `upto`는 건마다 온체인 거래 1건, `batch-settlement`는 오프체인 바우처를 모아 한 번에 처리한다 | `N/docs-cdp-coinbase-com-x402-core-concepts-facilitator.md` 21-23, 40-43행 |
| Cloudflare (pay per crawl) | `deferred` 방식을 x402에 제안 | 하루 동안 쌓인 요금을 카드나 은행 계좌로 한 번에 청구한다 | `cb/works/web/2026-10-06-machine-economy-primary/pages/d1-003-blog-cloudflare-com.txt` 3행 |

- Circle은 x402 facilitator를 둘 운영한다("Circle operates two x402 facilitators.", 같은 Circle 문서 30행). 둘 다 `exact` 방식을 쓰고, 정산 방식이 달라 서명 대상(EIP-712 domain)만 다르다("They sign against different EIP-712 domains because they use different settlement models.", 130-132행).
- Coinbase는 망별 표에서 Base, Polygon, Arbitrum 등 EVM 망에 세 방식을 모두 열고, Solana에는 `exact`와 `upto`만 연다(CDP 문서 71-81행).
- Cloudflare는 "we're proposing a new deferred payment scheme for the x402 protocol."이라고 적고, 비공개 베타의 크롤러가 "be charged a single fee via a connected credit card or bank account at the end of each day."라고 설명한다(Cloudflare 블로그 3행).

### 모아서 정산하는 두 방식: Circle Gateway와 x402 batch-settlement

모아서 정산한다는 생각은 같아도, 모으는 방법은 Circle과 Coinbase가 다르다.

- **Circle Gateway**: 사는 쪽이 Gateway에 한 번 넣은 잔액으로 결제한다("Once deposited, the buyer can make gasless payments from this balance.", `N/circle-docs-gateway-nanopayments-concepts-batched-settlement.md` 77-78행). Circle은 배치에 든 결제 전체의 순액을 계산한다("Compute net balance changes across all payments in the batch", 같은 문서 124행). 이것은 x402 표준의 `batch-settlement` 방식이 아니고, 표준 `exact` 방식 아래에 Circle 자체 정산을 얹은 것이다. Circle 문서도 "From x402's perspective, Gateway Nanopayments is just another payment method."라고 적는다(x402 개념 문서 172행).
- **x402 batch-settlement (Coinbase)**: x402 재단의 공개 표준이다. EVM 구현은 "stateless unidirectional payment channels"를 쓰고, 사는 쪽이 에스크로에 한 번 넣은 뒤 요청마다 누적 바우처에 서명한다(`N/docs-x402-org-schemes-batch-settlement.md` 9행). 판매자 쪽 channel manager가 여러 채널의 최신 바우처를 거래 하나로 claim한다(같은 문서 18행). 채널마다 받는 쪽의 `receiverAuthorizer`가 묶이므로(487행), 예치금은 판매자 한 곳에 묶인다고 이 문서는 읽는다. 이것은 해석이고 확신은 중간이다. "채널 하나에 판매자 하나"라고 적은 문장은 찾지 못했다.
- **수수료**: Coinbase는 매달 온체인 거래 1,000건까지 무료이고, 그 뒤로는 온체인 거래 한 건에 0.001달러를 받는다(CDP 문서 25-26행). 요금이 결제 건수가 아니라 온체인 거래 수에 붙으므로, `batch-settlement`에서는 결제 한 건이 지는 몫이 작아진다(같은 문서 37-38, 46-47행). Circle Nanopayments는 "neither party pays per-transaction fees"라고 적는다(`N/circle-docs-gateway-nanopayments.md` 44행).

### 판정과 한계: 같은 방식인가

- **판정**: 주고받는 절차(x402 협상)는 같고, 정산 방식은 회사마다 다르다. 모아서 정산하는 장치는 Circle만 가진 것이 아니며, Coinbase가 공개 표준(`batch-settlement`)으로 제공한다. Circle 쪽에만 있는 것은 판매자 누구에게나 쓰는 Gateway 잔액 하나와, 그 잔액 전체를 두고 Circle이 계산하는 순액이다. 이 판정의 확신은 중간이다. 근거가 모두 각 회사의 자기 문서이고, 실제 동작은 확인하지 않았다.
- **MPP FAQ와의 충돌**: MPP FAQ는 "x402 requires an on-chain transaction per request."라고 적는다(`N/mpp-dev-faq.md` 25행). 위 문서들로 보면 이 문장은 `exact` 방식에만 맞는다.
- **`deferred`의 지위**: 2026-10-15에 받은 x402 문서는 방식을 넷만 든다: "Choose between exact, upto, batch-settlement, and auth-capture payment schemes in x402."(`N/docs-x402-org-schemes-overview.md` 7행). `deferred`라는 말은 이 파일에 없다(검색: `rg -n -i deferred N/docs-x402-org-schemes-overview.md`, 0줄). 공식 목록에 오른 것은 확인하지 못했다.
- **보지 않은 곳**: x402 문서의 facilitator 목록에는 15곳이 있다(`N/docs-x402-org-dev-tools-facilitators.md`, `grep -c '^| \['` 15). Coinbase 말고 나머지 14곳이 어느 방식을 지원하는지는 각 문서를 열지 않았다 [미독].
- `upto`와 `batch-settlement`의 다른 면(사용량 상한, 쉬는 채널의 환불)은 기계 경제의 세 역할의 x402 확장 기능 목록에 있다.
- 모두 날짜가 적히지 않은 문서 사이트이므로, 받은 날(2026-10-15)의 내용이다.

## vault 대조

### 신규

네 글을 한데 모아 Circle의 사업 설명, 작동 방식, 계획과 한정 문구를 비교한 판독은 새 자료다. 이 묶음은 Circle의 자기 설명을 모은 것이며, 독립된 성능 평가가 아니다.

### 확인

- 사업 허브 1절(에이전트 금융 사업 방향)은 에이전트의 권한, 통제와 결제에 관한 사용자 사업 구상을 담는다. Circle의 제품은 비교할 외부 사례로 붙일 수 있지만, 사용자 명제를 대신 뒷받침하지 않는다.
- Circle과 Arc 허브는 Arc 및 Circle의 금융 인프라를 다룬다. 여기서는 Arc에 한정하지 않고 CPN과 에이전트 제품 자료를 다룬다.

### 충돌

기존 사업 허브의 사용자 명제와 네 Circle 글 사이에 직접 충돌은 확인하지 않았다. Circle의 비전과 사업 허브가 같은 주제를 다룬다는 이유만으로 사용자 사업 판단을 Circle의 전망에 맞추지 않는다.

이 판독과 네 글은 사업 허브 6절(원 기록의 위치)에 등록했다. 원문 네 글을 독립 명제로 승격하지 않았고, 승격과 허브의 판단 변경은 사용자 결정으로 남긴다.

## 증거 관측과 한계

판독을 갱신할 증거는 실제 CPN 참여, 정산 기록, 수수료 전액과 비교 기준, Nanopayments의 독립 보안 검토와 실패 복구 자료, 자동화 예제의 재현 기록, 에이전트 서비스의 구매, 반복 이용, 분쟁 자료다. 글에 붙은 공식 문서와 외부 자료는 열지 않았으므로 해당 자료의 주장에 기대지 않았다.

범위는 Circle이 게시한 영어 본문 네 편이며, 네 편 모두 전체를 읽었다. 다만 x402 정산 방식 비교 절은 2026-10-15에 받은 공식 문서와 Cloudflare 블로그를 따로 쓰며, 그 범위는 해당 절에 적었다. 회사가 이해관계를 가진 자기 설명이라는 한계가 있고, 제품과 수치는 시점에 따라 바뀔 수 있다. 이 문서는 앞부분의 `analysis_runs`에 기재한 설정으로 작성한 LLM 산출물이다.
