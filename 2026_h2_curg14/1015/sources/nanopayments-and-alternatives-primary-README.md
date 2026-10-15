---
date: 2026-10-15
type: capture-collection
tags: [AI, business, stablecoin, blockchain]
status: review
---

# Circle Nanopayments와 다른 소액 결제 방식의 1차 자료: Circle, x402, Coinbase, MPP 공식 문서

Arc AI 에이전트 해커톤 지원 판단 대화에서 사용자가 물은 것("Nanopayments는 Circle만 할 수 있는가, Circle이 해결하려는 문제와 맞닿아 있는가")에 답하려고 받은 공식 문서다. Circle 쪽은 Nanopayments가 어떻게 동작하고 Circle이 무엇을 받는지, 비교 대상은 x402와 MPP가 같은 소액 결제를 어떤 방식으로 하는지를 담는다. 같은 날 이어진 물음("x402 결제를 다른 회사들도 같은 방식으로 처리하는가")에 답하려고 Circle의 x402 개념 문서와 Coinbase CDP Facilitator 문서 두 개를 더 받았다. 이 묶음은 원문과 그 검색용 사본만 담는다. 처음 열 개를 읽은 결과는 대화에 있고, 뒤의 두 개로 정리한 x402 정산 방식 비교는 판독 문서에 있다.

## 어떻게 받았나

2026-10-15에 주 세션이 `curl`로 받았다. 세 문서 사이트 모두 쪽마다 마크다운 원본(`.md`)을 내주므로 그것을 받았고, 주소는 각 사이트의 `llms.txt` 목차에서 골랐다. 요약 도구를 거친 것은 받지 않았다. 사용자 요청으로 보안 검사는 중지되어 있으며 통과 판정이 없다. Circle 블로그의 Nanopayments 글 세 편은 이미 Circle Blog 원문 모음에 있어 다시 받지 않았다. 뒤에 더한 두 문서(Circle x402 개념, CDP Facilitator)는 `llms.txt` 목차에서 고르지 않고, 각 사이트의 경로 구조를 보고 주소를 짐작해 받았다. 둘 다 200으로 응답했고, 본문 제목이 "What is x402?"와 "CDP Facilitator"인 것을 열어 확인했다. 같은 때 받은 Circle Facilitator Service 쪽과 CDP SDK 참조 쪽 네 개는 읽지 않았으므로 보관하지 않았다.

## 파일 목록

검색본은 원본을 그대로 복사한 것이다. 원본이 이미 텍스트여서 바꿀 것이 없고, `raw/`가 git에 들어가지 않으므로 추적되는 사본을 `pages/`에 둔다.

| 발행처 | 자료 | 검색본 | 무엇이 있나 |
| --- | --- | --- | --- |
| Circle | Gateway Nanopayments 개요 | 텍스트 | 최소 0.000001달러, 구매자의 오프체인 서명, 판매자 쪽 Gateway 잔액, x402를 Gateway의 배치 정산으로 처리한다는 설명과 7단계 흐름 |
| Circle | How batched settlement works | 텍스트 | 개별 정산과 배치 정산의 비교 표, 5단계 생애, AWS Nitro Enclave(TEE)와 온체인 서명 검증으로 이루어진 보안 모델, 잔액 상태 |
| Circle | Gateway fees | 텍스트 | 체인을 건너는 이체에만 붙는 0.005%(0.5bp) 이체 수수료, 체인별 가스비 표, 전달 서비스 수수료 0.05달러 |
| Circle | Agent wallet fees | 텍스트 | Agent Wallets의 수수료 표. "Gateway protocol fee"는 체인을 건너는 x402 결제에 0.5bp이고 같은 체인은 무료 |
| Circle | What is x402? | 텍스트 | Circle이 운영하는 x402 facilitator 둘: 결제마다 온체인 정산하는 Facilitator Service와 모아서 정산하는 Gateway Nanopayments. 둘 다 `exact` 방식이고 서명 대상(EIP-712 domain)만 다르다 |
| Coinbase | CDP Facilitator | 텍스트 | Coinbase가 운영하는 x402 facilitator. `exact`, `upto`, `batch-settlement` 세 방식, 망별 지원 표, 매달 온체인 거래 1,000건 무료 뒤 건당 0.001달러 |
| x402 Foundation | Payment Schemes | 텍스트 | x402의 네 방식(exact, upto, batch-settlement, auth-capture)과 결제 흐름 셋(authorization, upfront, escrow) |
| x402 Foundation | Batch Settlement | 텍스트 | 에스크로에 한 번 넣고 오프체인 누적 바우처로 결제한 뒤 모아서 정산하는 x402 방식. EVM과 Solana에서 쓸 수 있다 |
| x402 Foundation | Facilitators | 텍스트 | x402 결제를 검증하고 정산해 주는 운영 서비스 목록. 누구나 운영할 수 있다고 적는다 |
| MPP (Tempo, Stripe) | Sessions | 텍스트 | Tempo 위에서 채널에 예치하고 오프체인 바우처로 쓴 만큼 내는 MPP 세션의 구현 안내 |
| MPP (Tempo, Stripe) | FAQ | 텍스트 | MPP의 결제 수단(Tempo 스테이블코인, 카드, Lightning), 세션의 최소 0.0001달러, 비용, 공동 저자(Tempo와 Stripe) |
| MPP (Tempo, Stripe) | Payment methods | 텍스트 | MPP가 지원하는 결제 수단의 비교 |

## 명세와 한계

수집 명세는 요청 URL, 응답, 원본 SHA-256과 크기를 담는다. 이 저장소는 `cb/works/web/*/raw/`를 git에 넣지 않으므로(`.gitignore`), 원본은 이 컴퓨터에만 있고 git이 추적하는 크기와 해시는 아래 표다.

| 원본 | 바이트 | SHA-256 |
| --- | ---: | --- |
| `raw/circle-docs-gateway-nanopayments.md` | 9,129 | `dc13d2125cc8c54f6f70caf89a7b807fdb62a15410bd53daeaa0f98c61f47a65` |
| `raw/circle-docs-gateway-nanopayments-concepts-batched-settlement.md` | 10,253 | `8f3ad8c4c029f955c63efac71202cd142bd7d8b8433b24b976d12c430ff8d505` |
| `raw/circle-docs-gateway-references-fees.md` | 8,127 | `7bfe270273acfe283e9d10b7226f4a8cc6d44b366ac21e03d85d7d3417cf6682` |
| `raw/circle-docs-agent-stack-agent-wallets-fees.md` | 5,799 | `467c047efb191aa67d247b25b53ec4e92408f8fd781ed9b61b9a3f32ebb22ff8` |
| `raw/circle-docs-gateway-nanopayments-concepts-x402.md` | 11,632 | `3bb7bedd54ffe02913894b2c3de2222e3ed01c71dedf4c26efe484f09a26fdf7` |
| `raw/docs-cdp-coinbase-com-x402-core-concepts-facilitator.md` | 5,936 | `57a7bf294f89eee61953d5e044d0c93a4adf00aec5da044c4ef070278b8a365e` |
| `raw/docs-x402-org-schemes-overview.md` | 4,719 | `8a6b743b17ae066de704f596a58bcd7186254af27ffe5034d6790b5c3cf532ad` |
| `raw/docs-x402-org-schemes-batch-settlement.md` | 36,622 | `e7b1de33bb2954dbcd318e353c5af0b27c886ddf3fae0636c158920fbe4a067a` |
| `raw/docs-x402-org-dev-tools-facilitators.md` | 4,161 | `d090b68bd9e9fa98ca13eee36e2fd1b877ef4153f9299eaa54b75d1500f5b0f2` |
| `raw/mpp-dev-payment-methods-tempo-session.md` | 23,799 | `d8587b8745e647f02c548c4f209e7cb844981791ea0a45390b913b791709e435` |
| `raw/mpp-dev-faq.md` | 7,713 | `42e3bf1424e862ea2e2d306a14ba155f3d3f5c2bedce666dd89a77ff49a2d6fd` |
| `raw/mpp-dev-payment-methods.md` | 3,075 | `10691cd90a642a836ba9e4d239abb2b16034e2951eec88f40a6ddab16d5e7ebe` |

- 모두 날짜가 적히지 않은 문서 사이트이므로, 받은 날(2026-10-15)의 내용이다. 문서는 예고 없이 바뀐다.
- MPP FAQ는 x402를 두고 "x402 requires an on-chain transaction per request."라고 적는다(`pages/mpp-dev-faq.md` 25행). 그런데 같은 날 받은 x402 문서에는 배치 정산 방식(`pages/docs-x402-org-schemes-batch-settlement.md`)이 있다. 뒤에 받은 두 문서로 보면, MPP의 문장은 `exact` 방식에만 맞는다. Coinbase 문서는 `exact`에서는 결제마다 온체인 거래가 하나씩 생기지만 `batch-settlement`에서는 거래 하나가 수천 건을 처리한다고 적는다(`pages/docs-cdp-coinbase-com-x402-core-concepts-facilitator.md` 40-43행).
- Cloudflare의 x402 `deferred` 방식 제안은 이 묶음이 아니라 기계 경제 1차 자료의 `pages/d1-003-blog-cloudflare-com.txt`에 있다. Pay per crawl 뒤에 나온 과금 기능은 받지 않았다.

## 쓰이는 곳

- Arc AI 에이전트 해커톤 지원 판단의 대화에서, Nanopayments가 Circle만의 것인지와 Circle이 해결하려는 문제와 맞닿아 있는지를 답하는 데 썼다.
- Circle CPN, 나노결제와 에이전트 경제 글 판독의 x402 정산 방식 비교 절이 Circle x402 개념, CDP Facilitator, x402 방식 문서를 근거로 쓴다.
- 사업 허브 6절(원 기록의 위치)에 등록돼 있다.
