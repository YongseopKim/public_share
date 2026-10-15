---
date: 2026-09-29
type: analysis
tags: [blockchain, business, stablecoin]
status: review
source:
  - cb/works/ai-chat/2026-09-29-circle-company-survey/outputs/circle-company-survey-bundle.md
  - cb/works/ai-chat/2026-09-29-circle-company-survey/raw/md/chatgpt.md
  - cb/works/ai-chat/2026-09-29-circle-company-survey/raw/md/claude.md
  - cb/works/ai-chat/2026-09-29-circle-company-survey/raw/md/grok.md
  - cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-fy2025-10k.md
  - cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-10q.md
  - cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-earnings-release.md
  - cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-earnings-call-transcript.md
  - cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-analyst-call-transcript.md
  - cb/works/web/2026-09-29-circle-sec-filings-sources/pages/web-circle-2021-08-06-s4.md
  - cb/works/web/2026-09-29-circle-sec-filings-sources/pages/web-circle-2025-06-05-424b4-ipo.md
  - cb/works/web/2026-09-29-circle-sec-filings-sources/pages/web-circle-2025-06-06-8k-ex3-1.md
  - cb/works/web/2026-09-29-circle-sec-filings-sources/pages/web-circle-2026-04-01-def14a.md
  - cb/works/web/2026-09-29-circle-sec-filings-sources/pages/web-circle-neville-form3-4.md
  - cb/works/web/2026-09-29-circle-sec-filings-sources/README.md
  - cb/works/circle-blog/README.md
  - cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-cpn-whitepaper.md
  - cb/works/web/2026-09-20-circle-arc-primary-sources/raw/circle-mainnet-launch.md
notes: .circle-company-survey-answer.md
---

# Circle 회사 조사: 하나로 합친 답

> **이 문서가 하는 일.** 사용자가 Circle에 대해 물은 여덟 가지 질문에 답 하나로 답한다. 재료는 ChatGPT, Claude, Grok이 여섯 회차에 낸 답 18개이고, 그 답들을 주제별로 다시 배열한 묶음 파일을 읽고 썼다. 사용자가 2026-09-29에 "최종적으로 한 대답을 하나 만들어내는게 내 목표", "중요한 것들을 다 포함했으면 함", "요약은 필요 없음", "너가 적극적으로 이 내용들에 대해서도 개입했으면"이라고 해서 만들었다.
>
> **여기 없는 것.** 세 모델의 글자 그대로의 답은 묶음 파일에 있고, 회차 구조와 반입 경위는 묶음 README에 있다. 세 답이 서로를 어떻게 평가했는지(묶음의 10번 주제)는 Circle에 관한 내용이 아니어서, 사실 관계를 바꾼 지적만 해당 주제에 옮겼다.
>
> **질문.** 사용자가 세 모델에 넣은 말은 묶음의 0번 주제에 있다(chatgpt.md:3, chatgpt.md:1844, chatgpt.md:4231, claude.md:3, claude.md:114, claude.md:241-248, claude.md:401, claude.md:509, claude.md:620, grok.md:3, grok.md:259-263, grok.md:1771-1779, grok.md:2026, grok.md:3445, grok.md:4473). 이 문서의 1장부터 8장까지가 그 질문의 순서다.
>
> **넣는 기준.** 세 답이 일치하는지는 기준이 아니다. 한 모델만 말한 것, 서로 어긋나는 것, 뒤 회차에서 철회된 것도 넣었고, 어긋나는 곳은 어긋난 채로 적었다(사용자 지시, 2026-09-29).
>
> **상태.** 2026-09-29에 썼고 사용자의 검토를 기다린다. 같은 날 사용자의 요청으로 SEC 공시 22건과 Neville의 지분 보고 20건을 더 받아 12장의 항목을 대조했고, 닫힌 것은 해당 장에 옮겼다. 대조한 범위는 "읽는 법"에, 아직 확인하지 못한 것은 12장에 있다.

## 읽는 법

**표지 다섯 가지.** 문장이나 항목 끝에 붙는다. 이 구분은 내가 정한 것이다.

| 표지 | 뜻 |
|---|---|
| `[공시 확인]` | vault에 있는 Circle의 공시(10-K, 10-Q, 실적 자료)에서 내가 해당 대목을 열어 확인했다. 줄 번호가 따라온다. |
| `[Circle 글 확인]` | vault에 보관된 Circle 공식 블로그와 백서에서 내가 해당 대목을 열어 확인했다. 회사가 그때 그렇게 말했다는 확인이고, 그 말이 사실이라는 확인은 아니다. |
| `[공시와 다름]` | 같은 공시가 답의 서술과 다르게 적고 있다. 공시의 글을 함께 적는다. |
| `[답의 주장]` | 세 모델의 답에만 있다. 답이 든 외부 링크는 열지 않았고 `[미독 - 외부 링크]`, vault의 공시에서도 확인하지 못했다. 틀렸다는 뜻이 아니라 내가 1차 자료로 확인하지 못했다는 뜻이다. |
| `[내 판단]` | 세 답에도 공시에도 없는, 내가 덧붙인 해석이나 평가다. |

표의 한 행은 표지 하나다.

**출처 표기.**

- `chatgpt.md:11-15`처럼 적은 것은 `cb/works/ai-chat/2026-09-29-circle-company-survey/raw/md/` 아래 검색본의 줄 번호다.
- `10-K:2991-2995`는 `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-fy2025-10k.md`(2025 회계연도 연차 보고서)의 줄 번호다.
- `10-Q2:줄`은 같은 폴더의 `web-circle-q2-2026-10q.md`(2026년 2분기 보고서), `10-Q1:줄`은 `web-circle-q1-2026-10q.md`(2026년 1분기 보고서)다.

- `블로그 focus-2020:45`처럼 적은 것은 `cb/works/circle-blog/` 아래 글의 `pages/*.en.md` 줄 번호다. 이름표와 글의 대응은 아래 표에 있다.

| 이름표 | 글 또는 폴더 | 낸 날 | 읽은 범위 |
|---|---|---|---|
| `about-2014` | `2014-05-16-blog-what-we-have-been-up-to-at-circle` | 2014-05-16 | 17-60행 |
| `centre-2016` | `2016-12-06-blog-centre-new-markets-app-messaging-and-bitcoin-changes` | 2016-12-06 | 전체 |
| `polo-acquire` | `2018-02-26-blog-circle-acquires-poloniex` | 2018-02-26 | 전체 |
| `review-2018` | `2019-01-03-blog-circle-2018-accomplishments-and-2019-themes` | 2019-01-03 | 검색으로 찾은 줄(27, 33, 53-64, 75-90, 102, 118) |
| `otc-5yr` | `2019-03-26-blog-circle-celebrates-five-years-of-crypto-otc-trading` | 2019-03-26 | 검색으로 찾은 줄(23-33, 45-55) |
| `policy-2019` | `2019-05-20-blog-us-crypto-policy-needs-to-change` | 2019-05-20 | 검색으로 찾은 줄(23-27, 39, 63) |
| `pay-sunset` | `2019-06-13-blog-circle-to-sunset-payment-app-continue-advancing-vision-of-crypto-based-payment-solutions-using-fiat-tokens` | 2019-06-13 | 전체 |
| `polo-spinout` | `2019-10-18-blog-poloniex-to-spin-out-of-circle` | 2019-10-18 | 전체 |
| `polo-us-end` | `2019-11-01-blog-trading-for-us-poloniex-customers-has-ended` | 2019-11-01 | 전체 |
| `focus-2020` | `2019-12-18-blog-circle-organizes-for-stablecoin-platform-focus-in-2020` | 2019-12-18 | 전체 |
| `three-phases` | `2020-07-18-blog-global-stablecoin-adoption` | 2020-07-18 | 검색으로 찾은 줄(29-65) |
| `mint-onramp` | Circle Mint의 기관용 발행과 상환 | 2025-07-01 | 전체 |
| `usyc-solana` | USYC의 지분 가격과 상환 유동성 | 2025-10-01 | 전체 |
| `usyc-bnb` | USYC의 청약, 상환과 관리 주체 | 2025-11-19 | 전체 |
| `cirbtc-ethereum` | cirBTC의 이더리움 출시와 Mint 지원 | 2026-06-08 | 전체 |
| `cirbtc-reserve` | cirBTC의 BTC 수탁, 발행과 상환 | 2026-09-04 | 전체 |
| `xreserve-launch` | xReserve의 예치, 증명과 상대 체인의 발행 | 2025-11-18 | 전체 |
| `gateway-guide` | Gateway의 예치 계약, 발행 계약과 증명 서비스 | 2025-12-19 | 전체 |
| `crosschain-consolidation` | CCTP 전송과 Gateway 예치를 연결하는 예 | 2026-03-12 | 전체 |
| `stablefx-build` | StableFX의 API와 Arc 정산 절차 | 2025-12-15 | 전체 |
| `managed-payments` | CPN Managed Payments의 운영 범위 | 2026-04-08 | 전체 |

표의 한 행은 글 하나다. "읽은 범위"는 내가 실제로 읽은 줄이고, 전체가 아닌 글에 대해서는 읽은 줄 밖의 내용을 말하지 않는다.

- `CPN 백서:줄`은 Circle Payments Network 백서의 검색본의 줄 번호다. 이번 보완에서 읽은 범위는 178-190행(금융기관 사이의 조정 역할)과 917-962행(블록체인 전송과 수취인 지급)이다.
- `Arc 메인넷 발표:줄`은 2026년 9월 16일 공식 발표문의 줄 번호다. 본문 전체를 읽었고, 출시 당시의 기능과 개발 계획을 구분하는 데 쓴다. 이 발표문도 `[Circle 글 확인]`으로 표시하며, 회사의 발표와 독립적인 검증을 구분한다.
- 2026-09-29에 사용자가 README의 내용 수정을 이 문서에도 적용하도록 요청해서 제품의 작동 방식을 위 공식 글과 대조했다. 아래의 기능별 분류는 내 구분이며, 제품을 나열한 순서는 필수 이용 순서가 아니다. 새로 확인한 작동 방식과 세 모델의 원래 주장은 해당 항목에서 구분한다.

- 2026-09-29에 더 받은 SEC 공시는 `cb/works/web/2026-09-29-circle-sec-filings-sources/pages/` 아래에 있고, 아래 이름표로 적는다. 표와 숫자는 줄 번호가 가리키는 변환본의 줄이다.

| 이름표 | 파일 | 무엇인가 | 읽은 범위 |
|---|---|---|---|
| `S-4` | `web-circle-2021-08-06-s4.md` | 2021년 8월 6일에 낸 SPAC 합병 등록 서류. 2019년과 2020년의 재무제표가 들어 있다 | 검색으로 찾은 줄(86, 967-975, 3265, 3315, 3597-3613, 3901-3908, 4010, 4067-4079, 5690, 5992-5998, 6136-6167, 6576-6618, 6761-6770) |
| `424B4` | `web-circle-2025-06-05-424b4-ipo.md` | 2025년 6월 5일의 IPO 투자설명서 | 98-112행(창업자 편지), 2299행(Carpenter의 채용 계약)만 |
| `정관` | `web-circle-2025-06-06-8k-ex3-1.md` | 2025년 6월 6일 8-K에 붙은 수정 정관 | 50-56행, 70행 |
| `주총자료` | `web-circle-2026-04-01-def14a.md` | 2026년 4월 1일에 낸 주주총회 자료(DEF 14A) | 검색으로 찾은 줄(216-229, 336-389, 1876-1972) |
| `8-K(날짜)` | `web-circle-<날짜>-8k.md` | 그 날짜에 낸 수시 공시. 2025-06-06, 2025-07-22, 2025-09-19, 2026-03-17, 2026-05-18, 2026-06-12, 2026-07-02, 2026-09-08, 2026-09-22, 2026-09-25의 열 건 | 본문 전체(표지의 서식 문구는 건너뜀. 2026-09-25의 표지에서 등록 증권 칸 37-38행은 읽음) |
| `Tazapay 발표` | `web-circle-2026-09-08-8k-announcement.md` | 2026-09-08 8-K에 붙은 보도자료 | 18행 |
| `Form4` | `web-circle-neville-form3-4.md` | Neville이 2025년 6월부터 2026년 9월까지 낸 지분 보고 20건을 한 파일로 옮긴 것 | 전체 |

표의 한 행은 이름표 하나다. 같은 폴더에 받아 두고 읽지 않은 것: 2022년 11월의 S-4 수정본, 2025년 8월의 후속 공모 투자설명서, 정관과 함께 붙은 부속 정관, Tazapay 주식 매매 계약 전문, 세 8-K에 붙은 보도자료 `[미독]`.

**1차 자료로 확인할 수 있는 범위.** vault에 있는 공시는 2025 회계연도 10-K, 2026년 1, 2분기 10-Q, 실적 발표 자료, 그리고 2026-09-29에 더 받은 위 표의 공시다. 2019년의 재무 숫자는 2021년의 S-4에 있어서 그 줄과 대조했다. 세 답은 이 숫자의 출처를 S-1이라고도 적었는데, 2025년의 IPO 서류가 다루는 기간에는 2019년이 없다(검색: `grep -c "December 31, 2019" web-circle-2025-06-05-424b4-ipo.md`, 0건). Circle이 2014년부터 낸 블로그 글은 vault의 circle-blog에 있어서, 세 답이 2016년과 2019년의 발표문을 인용한 대목은 원문과 대조했다. 인터뷰, 팟캐스트, 언론 보도는 vault에 없어서 확인하지 않았다 `[미독 - 외부 링크]`.

**세 답의 일치를 어떻게 읽을까.** 세 모델은 서로의 답을 세 번 읽은 뒤에 최종 답을 썼다. 그래서 최종 답에서 셋이 같은 말을 하는 것은 독립된 세 번의 확인이 아니다 `[내 판단]`. 1회차와 2회차(서로의 답을 보기 전)에 이미 같았던 것만 독립된 일치로 볼 수 있다.

**도식.** 코드 블록 안의 그림은 56개다(계수: ``rg -c '^```text$' cb/derived/circle-company-survey-answer.md``). 모두 내가 그렸고, 세 답의 그림을 글자 그대로 옮긴 것은 없다. 세 답은 그림을 126개 그렸고(묶음 파일에서 선이나 화살표 글자가 든 코드 블록의 수), 같은 그림을 회차마다 다시 그린 것이 많다. 세 답이 그린 주제는 모두 다루려 했고, 세 답이 그리지 않은 것도 본문의 표와 셈 가운데 그림으로 볼 만한 것은 그렸다. 막대는 `#`으로 그렸고 한 칸의 크기를 그림마다 적었다. 그림에 든 낱말과 숫자는 그 절의 표와 문장에 있는 것이고, 근거의 등급도 그 표와 문장에 붙은 표지를 따른다. 그림마다 아래에 무엇을 옮겼는지와 세 답이 그린 같은 모양의 그림이 어디에 있는지를 적었다. 2026-09-29에 사용자가 시각화 자료가 없다고 지적해서 넣었고, 넉넉하게 넣으라고 해서 늘렸다.

## 1. 어디에 상장했나

### 1.1. 거래소와 주식

- 회사의 법인명은 Circle Internet Group, Inc.이고, Class A 보통주가 2025년 6월 5일부터 뉴욕증권거래소(NYSE)에 티커 CRCL로 상장되어 있다 `[공시 확인]`. 10-K의 글은 "Since June 5, 2025, our Class A common stock has been listed on the New York Stock Exchange under the symbol CRCL"이다(10-K:2839). 세 답이 모두 같게 썼다(chatgpt.md:11-15, claude.md:15-19, grok.md:15-24).
- 보통주는 Class A, Class B, Class C 세 종류가 있고 시장에서 거래되는 것은 Class A뿐이다 `[공시 확인]`(10-K:2842-2843, 10-K:4430). 2026년 3월 5일 기준 발행 주식은 Class A 228,100,955주, Class B 18,714,651주, Class C 0주다(10-K:76). Class B의 의결권은 7.5절(지분과 의결권)에서 다룬다.
- 회사가 상장한 거래소는 NYSE 하나다. 독일 함부르크 등에서 ET9.HM으로 거래되는 것은 제3자가 올린 것이고 회사가 한 상장이 아니다 `[답의 주장]`(claude.md:15-19, grok.md:1653).
- 한국거래소 이중 상장은 확인되지 않고, 한국에서는 미국 주식 계좌로 CRCL을 매매한다 `[답의 주장]`(grok.md:15-24).
- 본사는 뉴욕이고 Russell 1000 구성 종목이다 `[답의 주장]`(grok.md:15-24).

### 1.2. IPO의 숫자: 세 답이 서로 다르게 쓴 이유

세 답은 1회차에 IPO 규모를 5.83억 달러(Claude), 약 10.5억 달러(Grok), 약 12억 달러(ChatGPT)로 다르게 썼다. 셋 다 틀린 숫자가 아니고 세는 대상이 다르다. 공시로 정리하면 다음과 같다.

| 무엇을 센 것인가 | 주식 수 | 금액 | 근거 |
|---|---|---|---|
| 회사가 새로 발행해 판 주식(초과배정 포함) | 1,990만 주 | 회사 순조달 5.83억 달러 | `[공시 확인]` 10-K:2991-2995 |
| 기존 주주가 판 주식 | 1,920만 주 | 회사로 들어온 돈 없음 | `[공시 확인]` 10-K:2994-2995 |
| 가격 확정 때의 기본 공모(신주 1,480만 + 구주 1,920만) | 3,400만 주 | 3,400만 x 31달러 = 10.54억 달러 | `[답의 주장]` grok.md:4496-4498 |
| 초과배정 510만 주까지 합친 전체 | 3,910만 주 | 약 12억 달러 | `[답의 주장]` chatgpt.md:11-15, grok.md:1635-1637 |

표의 한 행은 세는 방법 하나다.

```text
IPO에서 팔린 주식 3,910만 주 (공모가 31달러, 약 12억 달러)
|
+-- 회사가 새로 발행해 판 주식 1,990만 주   -->  회사 순조달 5.83억 달러
|      +-- 기본 물량   1,480만 주
|      +-- 초과배정      510만 주
|
+-- 기존 주주가 판 주식 1,920만 주          -->  회사로 들어온 돈 없음
```

**도식: IPO에서 팔린 주식의 분해.** 위 표와 아래 검산의 숫자를 나무 모양으로 놓았다. 1,480만 주와 510만 주는 Grok이 든 숫자이고, 합이 공시의 1,990만 주와 맞는다.

- 공모가는 주당 31달러다 `[공시 확인]`(10-K:2993).
- 10-K의 글은 "we issued and sold 19.9 million shares of Class A common stock, including the underwriters' over-allotment option which was exercised in full, at a public offering price of \$31.00 per share, which resulted in net proceeds to us of \$583.0 million"이고, 이어서 "Certain selling stockholders offered an additional 19.2 million shares ... for which we received no proceeds"라고 적는다(10-K:2991-2995).
- 검산: 1,990만 + 1,920만 = 3,910만 주이고, 3,910만 x 31달러 = 12.12억 달러다. ChatGPT의 "약 12억"과 맞는다 `[내 판단]`. Grok이 든 신주 1,480만 주에 초과배정 510만 주를 더하면 1,990만 주여서 공시와 맞는다.
- 그러므로 "회사가 IPO로 얼마를 조달했나"의 답은 5.83억 달러이고, "시장에 팔린 주식이 얼마어치인가"의 답은 약 12억 달러다. 이 구분은 Grok이 1회차 교차에서 처음 했다(grok.md:1635-1637, grok.md:1651).
- 상장 첫날 시초가는 69달러, 장중 최고가는 103.75달러(claude.md:15-19), 종가는 83.23달러로 공모가 대비 약 168% 올랐다(grok.md:15-24) `[답의 주장]`.
- 상장과 함께 상환전환우선주가 모두 Class A 1억 3,980만 주로 전환되었고, 공동창업자와 그들이 지배하는 법인이 가진 Class A 1,960만 주가 Class B로 바뀌었다 `[공시 확인]`(10-K:2997-2999). 세 답에는 없고 내가 공시에서 더했다.
- 상장으로 조건이 충족된 주식 보상 때문에 주식보상비용 4.238억 달러를 한 번에 인식했다 `[공시 확인]`(10-K:2999-3003). 2025년 한 해의 계속영업 손익이 7,000만 달러 손실(2024년은 1.57억 달러 이익)인 큰 원인이 이것이다 `[공시 확인]`(10-K:3110). 세 답은 2025년이 손실이었다는 것을 말하지 않았다.

### 1.3. 2025년 8월의 후속 공모

- 2025년 8월에 주당 130달러로 후속 공모를 했다 `[공시 확인]`(10-K:3006-3007). ChatGPT가 1회차에 썼고(chatgpt.md:11-15), Claude와 Grok은 1회차에 빠뜨렸다가 나중에 넣었다(grok.md:1644, claude.md:649-654).
- 회사가 판 주식 수는 답과 공시가 다르다 `[공시와 다름]`. Grok은 "회사 200만 주 + 기존 주주 800만 주, 그린슈 포함 회사 순조달 약 4.45억 달러"라고 썼다(grok.md:1644). 10-K는 "we issued and sold 3.5 million shares of our Class A common stock, including the underwriters' over-allotment option which was exercised in full"이라고 적고, 순조달은 4.448억 달러, 기존 주주가 판 주식은 800만 주라고 적는다(10-K:3006-3010).
- 두 숫자가 양립하는 읽기가 하나 있다: 기본 물량이 200만 주이고 초과배정이 150만 주이면 합이 350만 주가 된다. 이것은 내 추측이고 공시에는 그 분해가 없다 `[내 판단]`. 검산으로는 350만 x 130달러 = 4.55억 달러여서, 인수 수수료를 뺀 순조달 4.448억 달러와 맞는다. 200만 주만으로는 2.6억 달러여서 순조달 4.45억 달러가 나올 수 없다.
- IPO와 후속 공모로 회사에 들어온 현금은 합쳐서 10억 달러다 `[공시 확인]`(10-K:3458).

### 1.4. 그 전의 시도: SPAC 합병

- 2021년에 Concord Acquisition Corp.과 SPAC 합병으로 NYSE 상장을 추진했고, 2022년 12월에 끝났다. 세 답이 모두 썼다(chatgpt.md:28, claude.md:15-19, grok.md:15-24) `[답의 주장]`. vault의 10-K에는 Concord가 나오지 않는다(검색: `grep -n -i Concord web-circle-fy2025-10k.md`, 0건).
- 평가액은 처음 45억 달러였고 2022년 수정 계약에서 90억 달러였다 `[답의 주장]`(chatgpt.md:28). Grok은 이 숫자를 끝난 거래의 평가액으로만 읽어야 하고 실제 상장 가치와 섞으면 안 된다고 지적했다(grok.md:1677).
- **왜 끝났는가는 표현이 갈렸다.** Claude는 1회차에 "규제 문제로 무산"이라고 썼다(claude.md:15-19). ChatGPT는 이것이 너무 강한 표현이라고 지적하고, 거래 시한이 2022년 12월 10일이었고 SEC가 그때까지 S-4의 효력을 선언하지 않았으며 두 회사가 합의로 종료했고 Circle은 "transaction timed out"이라고 표현했다고 적었다(chatgpt.md:1385-1414). Claude는 최종 답에서 "규제 문제로"를 빼고 "2022년 말 무산"이라고만 썼다(claude.md:649-654).
- 내 읽기로는 ChatGPT의 서술이 더 정확하다 `[내 판단]`. "SEC가 심사를 끝내지 않아 시한을 넘겼다"는 사실이고, "규제 때문에 무산됐다"는 그 사실에 원인을 붙인 해석이다. SEC가 왜 효력을 선언하지 않았는지는 세 답 어디에도 근거가 없다.

### 1.5. 주식, USDC, ARC는 서로 다른 것이다

"Circle이 Coinbase에 상장했다"는 말은 틀렸다. 거래되는 대상을 나누면 다음과 같다(chatgpt.md:17-26, chatgpt.md:4261-4279, claude.md:657-665, grok.md:4485-4494). 세 답이 나눈 것은 CRCL, USDC와 EURC, ARC, USYC의 넷이고, cirBTC와 Class B 주식의 행은 내가 공시에서 찾아 더했다.

| 대상 | 무엇인가 | 거래되는 곳 |
|---|---|---|
| CRCL | Circle 회사의 Class A 주식 | NYSE. 거래소에 등록된 Circle의 증권은 이것 하나다 `[공시 확인]`(8-K(2026-09-25):37-38) |
| USDC, EURC | Circle이 발행하는 스테이블코인 | Coinbase, Binance, Kraken 같은 가상자산 거래소, 지갑, DeFi `[답의 주장]` |
| USYC | Circle이 인수한 Hashnote가 운용하는 토큰화 머니마켓펀드 | USYC 행을 둔 Grok도 거래되는 곳을 적지 않았고(grok.md:4494), ChatGPT와 Claude의 해당 대목에는 USYC가 없다(chatgpt.md:4261-4279, claude.md:657-665). 공시는 주로 디지털 자산 시장에서 담보로 쓰려는 것이고 증권법의 등록 면제에 기대어 제공된다고 적는다 `[공시 확인]`(10-K:450-452). 공개 시장에서 거래되는지는 확인하지 못했다. 4.2절(자산) |
| cirBTC | Circle이 발행하는 비트코인 담보 토큰 `[공시 확인]`(10-Q2:126) | 2분기 10-Q에 적혀 있지 않다(검색: `rg -n -i cirBTC cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-10q.md`, 126, 1111, 1865행의 3건이고 거래되는 곳을 적은 줄은 없다). 4.2절(자산) |
| ARC | Arc 네트워크의 토큰 | 기관 대상 사전 판매와 최초 발행을 공개 출시와 구분한다. 현재의 공개 거래 상태는 별도 확인할 항목이다(4.6절(네트워크 토큰: ARC)) |
| Class B 주식 | 공모 때 공동 창업자와 그들이 지배하는 법인이 가진 Class A 1,960만 주가 바뀐 것 `[공시 확인]`(10-K:5832-5833) | 공개 시장이 없다 `[공시 확인]`(10-K:2842). 보유자가 원하면 Class A와 1:1로 바꿀 수 있고, 허용된 경우가 아닌 양도에서는 저절로 Class A로 바뀐다(10-K:5836-5838) |

표의 한 행은 대상 하나다. CRCL 행의 상장 사실은 위에서도 공시로 확인했다(10-K:2839).

- Class C 주식은 표에 넣지 않았다. 수권만 되어 있고(10-K:5830) 발행된 주식이 없다 `[공시 확인]`(10-K:76, 10-K:2843).
- 전환사채도 넣지 않았다. 2025년 10월에 1,100만 달러어치가 약 67.5만 주로, 2026년 1월에 나머지 750만 달러어치가 약 46.5만 주로 Class A 주식이 되어 남은 것이 없다 `[공시 확인]`(10-Q2:1264-1268).
- SPAC을 추진하던 2021년에는 워런트를 "CRCL WS"로 상장하려 했다(S-4:86). 그 합병이 끝나서 이 워런트는 생기지 않았다고 나는 읽는다 `[내 판단]`.
- Partner Stablecoins는 개별 코인의 이름이 아니라 외부 발행사의 코인을 연결하는 협력 제도여서 별도 자산 행으로 넣지 않았다(4.12절(외부 자산 연결: Partner Stablecoins)). CRCL 옵션처럼 다른 회사가 만드는 파생상품은 vault의 공시로 확인할 수 없어서 다루지 않았다.

```text
Circle (회사)
|
+-- 회사 주식
|   +-- CRCL          Class A 주식                    -->  NYSE
|   +-- Class B       공동 창업자 쪽이 가진 주식      -->  양도하면 Class A로 바뀐다
|
+-- 스테이블코인과 토큰화 자산
|   +-- USDC, EURC    달러와 유로 스테이블코인        -->  가상자산 거래소, 지갑, DeFi
|   +-- USYC          토큰화 머니마켓펀드             -->  주로 담보용, 거래 시장은 추가 확인 필요
|   +-- cirBTC        비트코인 담보 토큰              -->  구체적인 거래 시장은 추가 확인 필요
|
+-- 네트워크 토큰
    +-- ARC           Arc 네트워크의 토큰             -->  사전 판매와 최초 발행, 공개 거래는 별도 확인
```

**도식: 주식, 발행 자산과 네트워크 토큰.** 위 표에서 성격이 다른 대상을 구분하려고 내가 다시 나눴다. ChatGPT의 도식은 CRCL, USDC, ARC를 거래 장소로 나눴지만(chatgpt.md:4264-4274), 이 도식은 자산의 성격을 기준으로 삼고 거래 시장을 확인하지 못한 항목은 따로 적었다. ARC의 사전 판매와 최초 발행은 4.6절(네트워크 토큰: ARC)의 근거를 따른다.

### 1.6. 한국에서의 USDC

이 절은 전부 `[답의 주장]`이다. vault의 공시에는 한국 거래소가 나오지 않는다 `[미독 - 확인하지 않음]`.

- 업비트는 USDC를 원화, BTC, USDT 마켓에 상장했고 당시 입출금은 이더리움 네트워크만 지원했다(claude.md:161-162, claude.md:657-665). Grok은 업비트의 USDC 거래 시작을 2024년 8월로 적었다(grok.md:26-33).
- 코인원은 2024년 3월에 솔라나 기반 USDC를 상장했다(claude.md:657-665).
- Grok은 1회차에 빗썸, 코인원, 코빗, 고팍스에도 상장되어 있다고 썼다(grok.md:26-33). Claude는 고팍스와 코빗의 상장을 확인하지 못했고 코빗은 Circle Alliance 참여사로만 확인된다고 적었다(claude.md:156). 이 어긋남은 뒤 회차에서 풀리지 않았다.
- **Arc 기반 USDC 입출금.** Grok은 1회차에 업비트가 2026년 9월에 Arc 체인 USDC 입출금을 지원한다고 썼다(grok.md:26-33). Claude는 이것이 과장이고, 두나무의 발표는 메인넷 이후 지원할 예정이라는 것이며 시점과 방식은 추후 공개한다고 했다고 바로잡았다(claude.md:151, claude.md:657-665). Grok의 최종 답에는 이 문장이 없다.
- 한국의 스테이블코인 거래량은 USDT가 우세하고 USDC의 점유율은 낮다(grok.md:26-33).
- Jeremy Allaire는 2026년 4월 13일에 방한해 KB, 신한, 하나의 경영진과 오찬을 했고, 두나무와 빗썸과 각각 MOU를 맺었다(claude.md:161-162, grok.md:26-33).

**이 장의 내용을 되풀이한 구간.** 읽었고 위에 적은 것 밖의 새 내용은 없다: chatgpt.md:4247-4259, chatgpt.md:4281, grok.md:1640, grok.md:1661.

## 2. 과거에는 무엇을 했나

### 2.1. 한눈에 보는 시기 구분

세 답의 최종 답이 그린 연혁을 합치면 다음과 같다(chatgpt.md:4285-4362, claude.md:669-688, grok.md:4502-4523). 시기를 나누는 방식은 세 답의 것이고, 셋이 거의 같다.

| 시기 | 회사의 모습 | 주요 사업 |
|---|---|---|
| 2013 | 창업. "돈을 인터넷의 정보처럼 움직이게 한다" | 구현 수단은 비트코인 |
| 2014-2017 | 비트코인 소비자 금융 회사 | Circle 앱, Circle Pay, Circle Trade(기관 장외거래) |
| 2016 | 비트코인 직접 매매 중단, Spark에서 CENTRE로 | "hybrid digital money": 법정화폐 가치를 블록체인으로 옮긴다 |
| 2018 | 확장기. 가상자산 종합 금융 회사 | Pay, Invest, Trade, Poloniex, SeedInvest, USDC |
| 2019 | 위기와 정리 | 감원, Pay 종료, Poloniex 분사, Trade 매각 |
| 2020-2024 | USDC 플랫폼 회사 | Invest 매각, USDC, EURC, Mint, API, CCTP, Wallets |
| 2025-2026 | 상장, 풀스택 플랫폼 | CPN, StableFX, Gateway, xReserve, USYC, Arc, Agent Stack |

표의 한 행은 시기 하나다. 시기 구분은 `[답의 주장]`을 따르되, Circle Invest의 매각은 공시의 2020년 3월 30일에 맞춰 2020-2024 행에 두었다 `[공시 확인]`(S-4:6576). 나머지 항목의 확인 범위는 아래 절에서 따로 표시한다.

```text
2013       창업. 구현 수단은 비트코인
  |
2014-2017  비트코인 소비자 금융: Circle 앱, Circle Pay, Circle Trade
  |
  +-- 2016   비트코인 직접 매매 중단, Spark에서 CENTRE로
  |
2018       확장기: Pay, Invest, Trade, Poloniex, SeedInvest, USDC
  |
2019       위기와 정리: 감원, Pay 종료, Poloniex 분사와 매각, Trade 매각
  |
2020-2024  USDC 플랫폼 회사: Invest 매각, USDC, EURC, Mint, API, CCTP, Wallets
  |
  +-- 2023   3월 SVB 사태, 8월 Centre의 남은 지분 50% 인수, 12월 Centre 해산
  |
2025-2026  상장과 확장: CPN, StableFX, Gateway, xReserve, USYC, Arc, Agent Stack
```

**도식: 연혁.** 위 표를 세로로 놓고 2.4절(USDC의 등장, CENTRE, Coinbase)과 2.7절(SVB 사태)의 2023년을 더했다. 세 답도 같은 모양의 연표를 그렸다(claude.md:672-686, grok.md:4508-4520, chatgpt.md:4319-4335). Circle Invest의 매각은 표와 도식 모두 공시의 2020년 시점에 맞췄다(6.4절(Circle Invest)).

- 창업 연도와 창업의 문제의식은 공시에 있다 `[공시 확인]`. 10-K는 "We were founded in 2013 on the belief that we could connect the world more deeply by building a new global economic system on the foundation of the internet, and facilitate the creation of a world where everyone, everywhere can share value as easily as we can today share information, content, and communications"라고 적는다(10-K:298-300).
- 세 답이 공통으로 강조하는 것은 2019년에 USDC를 갑자기 떠올린 것이 아니라는 점이다. 2016년의 CENTRE 발표에서 이미 법정화폐 가치를 블록체인으로 옮기는 방향이 나왔다(chatgpt.md:4285-4362). 이 논점은 5.2절(비전 쪽)에서 자세히 다룬다.
- Claude는 2020년에 재출발할 때의 인력을 약 60명으로 적었다(claude.md:669-688) `[답의 주장]`.

### 2.2. 2013-2017: 비트코인 소비자 금융

- 2013년에 Jeremy Allaire와 Sean Neville이 세웠다(chatgpt.md:100-136). 창업지는 보스턴이다(claude.md:22-25) `[답의 주장]`.
- 당시의 생각은 비트코인과 인터넷으로 소비자가 돈을 이메일처럼 쉽게 보내게 하자는 것이었다(chatgpt.md:100-136). Claude는 처음 목표를 "비트코인계의 PayPal"로 적고, 이후 Venmo와 경쟁하는 소셜 결제 회사로 방향을 바꾸면서 앱 이름을 Circle Pay로 바꿨다고 적었다(claude.md:22-25) `[답의 주장]`.
- 2014년 3월 26일에 시험판으로 나온 초기 소비자 앱은 미국과 영국 사용자가 신용카드나 직불카드를 연결해 비트코인을 사게 하는 서비스였다(chatgpt.md:100-136) `[Circle 글 확인]`(블로그 otc-5yr:23).
- **Circle Trade의 기원.** 고객에게 비트코인 유동성을 공급하려고 회사 안에서 비트코인을 사고팔기 시작했고, 이것이 커져서 기관용 장외거래 사업인 Circle Trade가 되었다(chatgpt.md:100-136) `[Circle 글 확인]`(블로그 otc-5yr:25-33). 이 점은 6.3절(Circle Trade)에서 Circle Trade를 판 이유를 읽을 때 중요하다: 처음부터 목표였던 사업이 아니라 소비자 앱을 돌리다 생긴 사업이다 `[내 판단]`.
- 2015년에 뉴욕주 BitLicense를 처음으로 받았다(claude.md:22-25, grok.md:59-67) `[답의 주장]`. 10-K는 현재 BitLicense를 보유한다는 맥락에서만 이 말을 쓴다(10-K:556).
- Barclays와 은행 관계를 맺었다(grok.md:59-67) `[답의 주장]`.
- 2016년에 앱 안의 비트코인 환전 지원을 중단했고 송금은 유지했다(grok.md:59-67) `[답의 주장]`.
- 중국, 한국, 필리핀으로 확장을 시도했고 Circle China는 이후 철수했다(grok.md:59-67) `[답의 주장]`. Grok만 썼다.
- **Circle Pay의 구조.** 보내는 사람이 달러, 유로, 파운드를 넣으면 Circle이 뒤에서 비트코인이나 블록체인으로 옮기고, 받는 쪽에서 다시 법정화폐로 바꿔 준다. 사용자는 비트코인을 의식하지 않아도 된다(chatgpt.md:100-136, chatgpt.md:4366-4411). Grok은 Circle Pay에 이모지와 GIF 송금 같은 소비자용 기능이 있었다고 적었다(grok.md:59-67) `[답의 주장]`.
- 2018년에 Circle은 Circle Pay로 미국, 영국, EU의 수백만 명에게 거의 즉각적인 송금을 제공했다고 밝혔다(chatgpt.md:100-136). Grok은 이것이 회사의 주장이고 마케팅의 어조라고 지적했다(grok.md:1674).
- **Circle Pay가 부딪힌 한계.** ChatGPT는 은행망과 계속 연결해야 하는 점, 카드망, 국가별 규제, 환전, 비트코인의 변동성, 수탁, 고객 확인과 자금세탁 방지, 사용자를 Circle이 직접 모아야 하는 점을 들었다(chatgpt.md:4366-4411). 2019년의 종료 발표에서 Circle이 기존 시스템과 토큰화되지 않은 법정화폐에 계속 의존해야 했던 문제를 직접 언급했다(chatgpt.md:4366-4411, grok.md:4527) `[Circle 글 확인]`(블로그 pay-sunset:25). 원문은 5.3절(앱보다 USDC였던 이유)에 옮겼다.

```text
보내는 사람
    |   달러, 유로, 파운드를 넣는다
    v
  Circle
    |   비트코인이나 블록체인으로 옮긴다 (사용자는 의식하지 않는다)
    v
  Circle
    |   법정화폐로 바꾼다
    v
받는 사람
```

**도식: Circle Pay의 구조.** 위 "Circle Pay의 구조" 항목의 문장을 옮겼다. ChatGPT가 같은 모양으로 그렸다(chatgpt.md:119-131).

### 2.3. 2018년: 확장기

- 2018년의 제품은 여섯 가지였다(chatgpt.md:140-155, chatgpt.md:4415-4446).

  | 제품 | 사업 |
  |---|---|
  | Circle Pay | 개인 간 송금 |
  | Circle Invest | 개인의 가상자산 투자 |
  | Circle Trade | 기관용 장외거래 |
  | Poloniex | 가상자산 거래소 |
  | SeedInvest | 주식 크라우드펀딩(증권) |
  | USDC | 스테이블코인 |

  표의 한 행은 제품 하나다.

- ChatGPT는 이 시기의 Circle을 작은 PayPal, Coinbase, Robinhood, 장외거래 데스크, 크라우드펀딩 플랫폼, 스테이블코인 발행사를 한 회사에 넣으려 한 것으로 묘사했다(chatgpt.md:4415-4446). Grok은 "크립토 종합상사"라고 불렀다(grok.md:4533).
- Poloniex는 2018년 2월에 인수했다 `[공시 확인]`. 10-K는 "In February 2018, one of our indirect wholly-owned subsidiaries acquired Poloniex, LLC"라고 적는다(10-K:6211). 인수가 약 4억 달러는 Claude가 적었고(claude.md:26) 공시의 이 대목에는 금액이 없다 `[답의 주장]`.
- Circle Invest는 2018년에 출시한 소매 투자 앱이다(claude.md:26) `[답의 주장]`.
- SeedInvest 인수는 2018년 10월에 발표했고, 브로커딜러를 포함한 크라우드펀딩 플랫폼이다(claude.md:26) `[답의 주장]`. 2018년 말에 계약을 맺었다는 것은 원문에 있다 `[Circle 글 확인]`(블로그 review-2018:102). 6.6절(SeedInvest)에서 다룬다. 10-K에는 SeedInvest 인수와 관련해 발행한 원금 2,400만 달러의 어음이 나온다 `[공시 확인]`(10-K:2867).
- Poloniex를 인수할 때 Circle은 그것을 알트코인 거래소가 아니라 법정화폐와 여러 토큰을 잇는 넓은 디지털 자산 시장으로 키우려 했다(chatgpt.md:4415-4446) `[Circle 글 확인]`(블로그 polo-acquire:49-55).
- 2018년 한 해에 175개국 이상에서 800만 명 이상의 고객을 두고, 약 2억 건, 약 750억 달러의 거래를 처리했다고 Circle이 발표했다(chatgpt.md:140-155, claude.md:137, claude.md:692). Grok은 이것이 당시 회사의 발표이고 감사받은 숫자와 같지 않을 수 있으므로 "당시 발표"라고 써야 한다고 지적했다(grok.md:1673). 회사가 그렇게 발표했다는 것은 원문에 있다 `[Circle 글 확인]`(블로그 review-2018:27). 숫자가 맞는지는 다른 물음이고 확인할 길이 없다.
- 내가 덧붙이는 읽기: 750억 달러는 거래액이고 매출이 아니다. 거래소와 장외거래 데스크는 거래액의 아주 작은 비율만 수익으로 남기므로, 이 숫자로 당시 회사의 크기를 재면 크게 부풀려진다 `[내 판단]`.

### 2.4. USDC의 등장, CENTRE, Coinbase

- USDC는 2018년 9월 26일에 출시되었다(chatgpt.md:176-201) `[답의 주장]`. Circle과 Coinbase가 함께 만든 CENTRE Consortium의 표준으로 나왔고 Circle이 첫 발행사였다.
- 10-K는 같은 일을 이렇게 적는다 `[공시 확인]`: "In 2018, we partnered with Coinbase, the leading U.S. digital asset exchange, through the Centre Consortium, a joint venture between Coinbase and us, to support the growth of USDC and promote broader adoption of stablecoins. While Coinbase was not required to distribute USDC, we shared reserve-related income to align incentives and support USDC liquidity and usage"(10-K:692-694).
- 출시 당시의 주된 쓰임은 거래소 사이의 달러 가치 이동, 헤지, 차익거래, 거래 담보였고, Circle도 스테이블코인의 주된 쓰임이 가상자산 거래와 헤지라고 설명했다(chatgpt.md:176-201) `[답의 주장]`. ChatGPT는 당시에는 Circle도 USDC가 회사 전체를 차지할 사업이 될지 확실히 알지 못했다고 적었다.
- **2023년 8월의 개편.** 여기서 답과 답이 부딪혔고 공시가 가려 준다.
  - ChatGPT는 1회차에 "2023년 Circle이 Coinbase의 CENTRE 지분 50%를 인수했습니다"라고 썼다(chatgpt.md:307-331).
  - Grok은 이것을 "표현이 거칠음"이라고 판정하고, 단순한 50% 지분 매수로 적으면 계약의 본질이 흐려진다고 했다(grok.md:1639).
  - 10-K는 "In August 2023, the Company acquired the remaining outstanding 50% equity interest in Centre Consortium, LLC ("Centre") from a digital asset exchange (the "Centre Acquisition"). Total consideration for the Centre Acquisition was \$209.9 million consisting of approximately 8.4 million common shares of the Company measured at fair value"라고 적는다(10-K:5038-5040) `[공시 확인]`.
  - 그러므로 ChatGPT의 문장은 공시의 표현과 같고, Grok의 지적은 받아들일 수 없다 `[내 판단]`. 다만 Grok이 덧붙인 내용, 곧 같은 때에 협약이 개정되어 Circle이 거버넌스를 단독으로 갖고 Coinbase가 Circle의 지분과 준비금 수익 분배를 받게 되었다는 것도 사실이다. 두 서술은 같은 거래의 두 면이다: 지분 50%를 사는 대가가 Circle의 주식 약 840만 주(2.099억 달러)였고, 그래서 Coinbase가 Circle의 주주가 되었다.
- Centre는 2023년 12월에 해산되었고 순자산은 Circle의 다른 완전 자회사로 넘어갔다 `[공시 확인]`(10-K:5040-5041). Grok은 1회차 표에서 "2023.8 Centre 해체"라고 적었는데(grok.md:75), 공시에 따르면 8월은 인수이고 해산은 12월이다 `[공시와 다름]`.
- 그 전까지 Circle은 Centre의 지분 50%를 지분법으로 회계 처리했다 `[공시 확인]`(10-K:4529-4530).
- 개정된 협약(Collaboration Agreement)의 내용은 3.4절(Coinbase와의 계약)에서 다룬다.

```text
2018년                                    2023년 8월 뒤

Circle   --+                              Circle  -->  USDC
           +-->  Centre  -->  USDC
Coinbase --+                              Coinbase는 Circle의 주주가 되었다
                                          (Centre 지분 50%의 대가로 Circle의 주식
각자 지분 50%                              약 840만 주, 2.099억 달러)

2023년 8월   Circle이 Centre의 남은 지분 50%를 인수
2023년 12월  Centre 해산
```

**도식: Centre의 앞과 뒤.** 위 항목의 공시 인용을 옮겼다. ChatGPT가 같은 모양으로 그렸다(chatgpt.md:312-320).

### 2.5. 2019년: 위기와 정리

Circle Pay를 종료하고 Poloniex와 Circle Trade를 정리하면서 USDC 플랫폼에 집중하기 시작한 해다. Circle Invest와 SeedInvest의 매각은 뒤의 해에 이어졌다. 이 해의 일은 뒤의 장들이 질문마다 나눠 다룬다: 왜 USDC로 방향을 틀었나는 5장, 사업을 왜 팔았나는 6장, 누가 나갔나는 7장과 8장이다. 이 절에는 그해에 무엇이 있었는지와 어디서 자세히 다루는지만 적고, 내용은 되풀이하지 않는다.

| 때 | 일 | 근거 | 자세히 다루는 곳 |
|---|---|---|---|
| 3월 | 자금 조달 목표를 2.5억 달러에서 1.5억 달러로 낮췄다는 보도 | `[답의 주장]` claude.md:292 | 5.4절(생존 쪽: 2019년에 무슨 일이 있었나) |
| 5월 | 직원의 10%, 약 30명 감원 | `[답의 주장]` claude.md:279 | 5.4절(생존 쪽) |
| 5월 | Poloniex가 미국에서 일부 자산의 거래를 막았다. Circle은 미국 규제 당국이 가상자산을 증권으로 넓게 보는 것을 이유로 들었다 | `[Circle 글 확인]` 블로그 policy-2019:23-25 | 5.4절(생존 쪽) |
| 6월 13일 | Circle Pay 종료 발표 | `[Circle 글 확인]` 블로그 pay-sunset:23 | 5.3절(앱보다 USDC였던 이유), 6.5절(Circle Pay) |
| 10월 18일 | Poloniex 분사 발표 | `[Circle 글 확인]` 블로그 polo-spinout:23 | 6.2절(Poloniex) |
| 11월 1일 | Poloniex의 미국 고객 거래 종료 | `[Circle 글 확인]` 블로그 polo-us-end:23 | 6.2절(Poloniex) |
| 12월 18일 | Circle Trade를 Kraken에 매각했다고 발표 | `[Circle 글 확인]` 블로그 focus-2020:45 | 6.3절(Circle Trade) |
| 12월 18일 | 공동 CEO Neville, CFO Ishaq, CLO Coldebella가 물러난다고 발표 | `[Circle 글 확인]` 블로그 focus-2020:55-57 | 7.3절(2019년에 나간 사람들), 8.2절(2019년과 2026년은 다르다) |

표의 한 행은 일 하나다. 5.4절(생존 쪽)의 표에서 2019년의 행을 옮기고, 행마다 그 일을 자세히 다루는 절을 붙였다.

- **돈.** 2019년의 계속영업 영업손실은 8,321만 달러이고, Poloniex의 처분손실을 더한 전체 순손실은 1.786억 달러다 `[공시 확인]`(S-4:6158, S-4:6167). 영업으로 5,970만 달러가 나갔다(S-4:4067). Poloniex를 판 대가는 현금 3,315만 달러와 조건부 대가 1,500만 달러다(S-4:6605-6606). 손익을 위에서 아래로 그린 도식은 5.4절(생존 쪽)의 "돈"에, 사업마다 받은 것은 6.1절(답의 뼈대)의 표에 있다.
- **사람.** 인력이 400명에서 450명쯤에서 2020년 초에 60명 안팎으로 줄었다는 것이 두 답의 서술이다 `[답의 주장]`(claude.md:286-287, chatgpt.md:2775-2831). 그 가운데 80명 넘게는 해고가 아니라 Poloniex와 함께 옮겨 갔다 `[Circle 글 확인]`(블로그 focus-2020:53). 5.4절(생존 쪽)의 "사람"에서 다룬다.
- **창업자의 회고.** Allaire는 2026년의 팟캐스트에서 2019년을 "darkest hour"라고 불렀다고 ChatGPT와 Grok이 옮겼다(chatgpt.md:2775-2831, grok.md:4379) `[답의 주장]` `[미독 - 외부 링크]`. Claude는 같은 인터뷰의 소개문에 2019년의 파산 위기가 적혀 있다고 쓰고, 인터뷰의 세부 내용은 원문으로 확인하지 못했다고 남겼다(claude.md:541). 그때의 공식 발표는 전략에 집중한다는 말이었고 회고는 살아남는 이야기여서 어조가 다르다. 5.4절(생존 쪽)의 "창업자의 회고"에서 다룬다.
- **이 해에 끝나지 않은 것.** Circle Invest의 매각은 2020년 3월 30일이다 `[공시 확인]`(S-4:6576). 6.4절(Circle Invest)에 있다. SeedInvest는 2023년 5월에 팔았다(6.6절(SeedInvest)). USDC는 남았다.
- 이 해의 정리가 USDC로 방향을 튼 것과 어떻게 이어지는지는 5장의 물음이다. 5.1절(답의 뼈대)의 답은 두 문장이 함께 참이라는 것이다: USDC는 2019년에 갑자기 나온 생각이 아니고, 2019년에 회사가 거의 죽을 뻔하지 않았다면 나머지 사업을 그만큼 자르지 못했을 가능성이 크다(grok.md:4590-4595).

### 2.6. 2020-2024: USDC 회사

- 준비금 수익의 구조는 단순하다. 고객이 1달러를 넣으면 USDC 1개를 발행하고, 그 1달러를 현금, 미국 국채, 머니마켓펀드로 보유해 이자를 받는다(chatgpt.md:253-303). 준비금 수익은 해당 기간의 유통량과 준비금 수익률에 따라 달라진다 `[공시 확인]`(10-Q2:1888-1889). 회사의 전체 실적을 설명하려면 기타 매출과 유통비용, 영업비용도 함께 봐야 한다 `[내 판단]`. 매출 구조는 3.3절(매출이 만들어지는 구조)에서 다룬다.
- 소비자에게 직접 서비스하던 것에서, 거래소, 핀테크, 개발자, 기업에 인프라를 공급하는 방식으로 바뀌었다(grok.md:84-108).
- 준비금은 BlackRock이 운용하는 Circle Reserve Fund(현금과 단기 국채)와 BNY Mellon 수탁을 중심으로 다시 짰다(grok.md:84-108) `[답의 주장]`.
- 2023년에 CCTP와 프로그래머블 월렛을 공개했다(grok.md:84-108) `[답의 주장]`.
- 2024년 1월에 IPO 서류를 비공개로 제출했다(grok.md:84-108) `[답의 주장]`.
- 2024년의 매출 및 준비금 수익은 16.76억 달러이고 계속영업 순이익은 1.57억 달러다 `[공시 확인]`(10-K:3107, 10-K:3110). Grok의 "16.8억 달러, 순이익 약 1.56억 달러"(grok.md:84-108)와 반올림 범위에서 맞는다.
- Tron에서 USDC 지원을 중단했다(grok.md:84-108) `[답의 주장]`. Grok만 썼다.

### 2.7. SVB 사태(2023년 3월)

- 10-K의 글 `[공시 확인]`: "in March 2023, we announced that we had initiated transfers of more than \$3 billion of deposits from Silicon Valley Bank ("SVB") to other banks, but those transfers failed to settle before the Federal Deposit Insurance Corporation (the "FDIC") placed the bank into receivership. Although all of these funds were ultimately made available and transferred to new banks, concerns related to Circle's access to these funds caused USDC to experience a temporary price dislocation on certain secondary trading markets"(10-K:1037-1042).
- Claude는 "30억 달러 이상"이라고 공시와 같게 썼고(claude.md:30-34), Grok은 "약 33억 달러"라고 썼다(grok.md:84-108). 33억 달러는 공시의 이 대목에 없는 숫자다 `[답의 주장]`.
- 공시는 이어서 그 뒤에 USDC의 유통량이 줄었다고 적는다(10-K:1042). 세 답은 디페깅만 말하고 유통량 감소는 말하지 않았다.
- Grok은 이후 준비금을 BNY Mellon 등으로 옮겼다고 적었다(grok.md:84-108) `[답의 주장]`.
- Claude의 연혁은 SVB 사태 다음에 Centre 해산과 Coinbase와의 새 협약을 놓는다(claude.md:669-688). 둘 사이에 인과가 있다고 말한 답은 없다.

### 2.8. 2025-2026: 상장과 확장

Grok의 1회차가 날짜를 가장 촘촘하게 적었다(grok.md:84-108). 전부 `[답의 주장]`이고, 제품마다의 확인은 4장에서 한다.

| 때 | 일 |
|---|---|
| 2025년 1월 | Hashnote 인수, USYC 편입 |
| 2025년 5월 | CPN 가동 |
| 2025년 6월 | NYSE 상장 |
| 2025년 하반기 | Gateway, StableFX, Partner Stablecoins, xReserve 공개 |
| 2025년 10월 | Arc 테스트넷 |
| 2025년 말 | Interop Labs의 팀과 지식재산 인수 합의 |
| 2026년 5월 | Agent Stack |
| 2026년 7월 | 통화감독청(OCC)의 국법신탁은행(Circle National Trust) 최종 승인 |
| 2026년 9월 16일 | Arc 메인넷 |

표의 한 행은 일 하나다.

- Claude의 연혁은 2026년에 ARC 사전 판매를 Arc 메인넷 앞에 놓는다(claude.md:669-688).
- Circle이 지금 자신을 부르는 말은 스테이블코인 발행사가 아니라 인터넷 금융 시스템을 위한 풀스택 플랫폼이고, 기둥은 셋이다: 인프라(Arc와 개발자 도구, 상호운용 도구), 디지털 자산과 유동성(USDC, EURC, USYC, cirBTC, Mint, xReserve), 애플리케이션(CPN, StableFX)(grok.md:84-108). 10-K도 애플리케이션을 "Circle Applications, which includes Circle Payments Network ("CPN") and StableFX"로 적는다 `[공시 확인]`(10-K:319).

**이 장의 내용을 되풀이한 구간.** 읽었고 위에 적은 것 밖의 새 내용은 없다: chatgpt.md:32-96, grok.md:55-57, grok.md:69-71.

## 3. 지금은 무엇을 하고, 돈은 어디서 나오나

### 3.1. 지금의 Circle을 어떻게 정의하나

- Circle이 스스로 나누는 사업의 층은 셋이다: 애플리케이션(CPN, StableFX), 디지털 자산과 서비스(USDC, EURC, USYC, cirBTC, Circle Mint, xReserve, Partner Stablecoins), Arc와 개발자 인프라(Arc, CCTP, Gateway, Wallets, Contracts, Paymaster, App Kits)(chatgpt.md:4650-4681). ChatGPT는 이 분류가 자신이 만든 것이 아니라 10-K와 2026년 제품 전략 글의 구조라고 밝혔다. 10-K에 애플리케이션 층의 정의가 있다 `[공시 확인]`(10-K:319). 2026년에 Digital Asset Accounts와 Agent Stack이 더해졌다(chatgpt.md:4650-4681).
- ChatGPT는 1회차에 지금의 Circle을 "USDC issuer + reserve-income business"로 정의했고, 1회차 교차에서 이 정의가 경제적으로는 여전히 맞지만 전략까지 넣으면 부족하다고 스스로 고쳤다(chatgpt.md:1782-1838). 고친 그림은 "지금 돈을 버는 Circle"(USDC, 준비금, 이자)과 "Circle이 짓고 있는 회사"(자산, 유동성, 상호운용, 블록체인, 환전과 결제, 계정, 최종 사용자)를 나눈다.
- 같은 대목에서 ChatGPT는 세 가지 층을 덧붙였다: Circle National Trust와 Circle New York Trust는 규제와 수탁의 층, Coinbase와 Binance는 유통의 층, Tazapay는 앞으로 법정화폐 지급의 마지막 구간을 맡을 층이다(chatgpt.md:1782-1838).
- Grok의 정의: 지금 Circle이 파는 것은 코인이 아니라 달러 토큰과 그 토큰이 도는 길이다. 발행과 상환(Mint), 결제망(CPN), 환전(StableFX), 체인 간 이동(CCTP, Gateway), 자체 체인(Arc), 개발자 도구, 수탁과 규제 준수가 그것이다. 그리고 "제품이 풀스택화한 것과, 돈이 어디서 나오느냐는 아직 다릅니다"원문 그대로.
- 세 답이 같은 결론에 이른다: 제품은 넓어졌지만 돈은 아직 USDC 준비금의 이자에서 나온다. 이 결론은 1회차부터 셋이 각자 쓴 것이어서 독립된 일치로 볼 수 있다 `[내 판단]`(chatgpt.md:945-1007, claude.md:30-34, grok.md:37-51).

```text
지금 돈을 버는 Circle         Circle이 짓고 있는 회사

USDC                          자산 (USDC, EURC, USYC, cirBTC)
  |                             |
  v                             v
준비금                        유동성 (Mint, xReserve)
  |                             |
  v                             v
이자                          상호운용 (CCTP, Gateway)
                                |
                                v
                              블록체인 (Arc)
                                |
                                v
                              환전과 결제 (StableFX, CPN)
                                |
                                v
                              기업용 서비스 (Digital Asset Accounts, Managed Payments)
                                |
                                v
                              최종 사용자
```

**도식: 버는 회사와 짓는 회사.** ChatGPT가 1회차 교차에서 고쳐 그린 그림을 바탕으로 했다(chatgpt.md:1793-1833). 괄호 안의 제품 이름은 ChatGPT의 그림에 있는 것이다. Digital Asset Accounts와 Managed Payments를 함께 적은 항목은 계정 제품과 결제 운영 서비스를 모두 포함하도록 내가 "기업용 서비스"로 고쳤다(4.8.3절(결제 운영 서비스), 4.11절(기업용 계정)) `[내 판단]`.

공시는 "The three pillars of our platform are designed to reinforce one another"라고 설명한다 `[공시 확인]`(10-K:324). 사업의 세 영역이 서로 보완하도록 설계되었다는 뜻이다. 따라서 오른쪽 도식의 화살표는 모든 고객이나 거래가 제품을 차례로 거쳐야 한다는 뜻으로 읽으면 안 된다. 공시는 애플리케이션이 Arc뿐 아니라 여러 블록체인에서도 쓰인다고 적는다 `[공시 확인]`(10-K:319-320). 이 도식은 Circle이 제공하려는 기능들의 관계를 정리한 그림으로 읽는 편이 맞다 `[내 판단]`.

**짓고 있는 회사를 문장으로 풀면**

Circle은 디지털 자산을 발행하는 데서 더 나아가, 그 자산을 실제 금융거래에 사용하는 데 필요한 기능을 연결해 제공하는 회사를 만들고 있다. 아래 설명은 공시의 사업 구분과 앞서 정리한 제품 설명을 바탕으로 내가 문장으로 재구성한 것이다 `[내 판단]`(10-K:315-326).

Circle은 달러와 유로 스테이블코인, 펀드 지분과 비트코인을 나타내는 토큰 등 서로 성격이 다른 디지털 자산을 제공한다. 그리고 기업과 금융기관이 자산의 종류에 맞춰 이를 확보하고, 보관하고, 현금으로 바꾸고, 여러 블록체인 사이에서 이동시킬 수 있도록 관련 서비스를 제공한다. USDC가 중심이지만 모든 자산이 USDC를 기반으로 하는 것은 아니다. 여기서 말하는 서비스는 자산의 발행, 상환, 보관과 이동을 지원하는 것이므로, 이 일을 통틀어 "유동화"라고 부르기보다는 각 기능을 구체적으로 적는 편이 뜻을 정확하게 전한다 `[내 판단]`(10-K:317-318, 10-Q2:126, 4.2절(디지털 자산), 4.3.1절(Mint), 4.4절(체인 사이의 이동)).

Circle은 이렇게 연결한 자산을 실제 환전과 결제에 사용할 수 있게 하려 한다. 이를 위해 금융거래에 맞춘 자체 블록체인 Arc도 구축한다. 자산을 제공하는 일, 자산이 이동하는 환경을 만드는 일, 그 자산으로 금융거래를 처리하는 일이 서로 연결되는 구조다. 이 설명에서 환전과 결제는 자산의 사용 목적이고, Arc는 그 거래를 지원하는 환경이다 `[내 판단]`(10-K:316-326).

계정과 관리형 서비스까지 포함하면, Circle이 추구하는 방향은 고객 기업이 지갑과 블록체인 전송 등의 기능을 일일이 조립해야 하는 부담을 줄이고, 이를 묶어 자신의 고객에게 금융 서비스를 제공할 수 있게 하는 것으로 설명할 수 있다 `[내 판단]`. 이 대목은 Digital Asset Accounts(고객 기업이 자기 상표로 디지털 자산 계좌를 제공하도록 지원하는 제품)와 Managed Payments(스테이블코인 결제 운영을 맡아 주는 서비스)에 관한 설명을 재구성한 것이다. Managed Payments의 운영 범위는 공식 글로 확인했고 `[Circle 글 확인]`(블로그 managed-payments:37-43), Digital Asset Accounts의 세부 기능은 아직 `[답의 주장]`으로 남아 있다(chatgpt.md:1209-1253, 4.8절(결제망과 결제 운영 서비스), 4.11절(Digital Asset Accounts의 구성과 근거)). 계정은 고객에게 기능을 제공하는 방식 가운데 하나이므로, 최종 사용자가 반드시 Circle의 계정 제품만 이용해야 한다는 뜻은 아니다 `[내 판단]`.

### 3.2. 2026년 2분기의 숫자

| 지표 | 값 | 근거 |
|---|---|---|
| 매출 및 준비금 수익 | 7.01억 달러(전년 같은 분기 6.58억 달러) | `[공시 확인]` 10-Q2:2057 |
| 준비금 수익 | 6.677억 달러 | `[공시 확인]` 10-Q2:314 |
| 기타 매출 | 3,358만 달러 | `[공시 확인]` 10-Q2:315 |
| 준비금 수익의 비중 | 95.2%(상반기 94.6%, 전년 96.4%) | `[공시 확인]` 10-Q2:1884-1886 |
| 유통비용을 뺀 매출(RLDC) | 2.89억 달러, 마진 41% | `[공시 확인]` 10-Q2:2058-2059 |
| 계속영업 순이익 | 4,800만 달러(전년 같은 분기 4.82억 달러 손실) | `[공시 확인]` 10-Q2:2060 |
| USDC 유통량, 분기 말 | 732.69억 달러(전년 613.33억 달러) | `[공시 확인]` 10-Q2:2051 |
| USDC 유통량, 분기 평균 | 765.24억 달러 | `[공시 확인]` 10-Q2:2052 |
| 준비금 수익률 | 3.5%(전년 4.1%) | `[공시 확인]` 10-Q2:2053 |
| Circle 플랫폼에 있는 USDC, 분기 말 | 124.42억 달러(전년 60.40억 달러) | `[공시 확인]` 10-Q2:2054 |
| 플랫폼 보유 비율, 일평균 가중 | 19.5%(전년 7.4%) | `[공시 확인]` 10-Q2:2055 |
| 온체인 거래량 | 분기 14.8조 달러 | `[답의 주장]` grok.md:37-51, grok.md:4535-4548 |
| 스테이블코인 점유율 | 유통량 기준 약 27%, 테더 다음 2위 | `[답의 주장]` grok.md:37-51 |
| 시가총액 | 2026-09-25 종가 89달러, 약 227억 달러(Claude), 9월 말 약 210억에서 220억 달러(Grok) | `[답의 주장]` claude.md:649-654, grok.md:37-51 |

표의 한 행은 지표 하나다.

```text
2026년 2분기 매출 및 준비금 수익 7.01억 달러 (막대 한 칸은 2%)

어디서 나왔나
  준비금 수익 6.677억 달러  ################################################    95.2%
  기타 매출   3,358만 달러  ##                                                  4.8%

어디로 갔나
  유통과 거래 비용    4.12억 달러   ##############################              59%
  유통비용을 뺀 매출  2.89억 달러   ####################                        41%

전년 같은 분기와 견주면
  USDC 유통량, 분기 평균  610.39억 달러   -->  765.24억 달러    25% 늘었다
  준비금 수익률           4.1%            -->  3.5%
  준비금 수익             6.343억 달러    -->  6.677억 달러     5% 늘었다
```

**도식: 2분기 매출이 나온 곳과 간 곳.** 위 표와 아래 항목의 숫자를 막대로 놓았다. 4.12억 달러는 3.3절(매출이 만들어지는 구조)의 문장에 있고, 59%는 100에서 마진 41%를 뺀 내 셈이다(4.12 / 7.01 = 58.8%). ChatGPT는 준비금 수익과 기타 매출의 합만 그렸다(chatgpt.md:5491-5494).

- 세 답이 쓴 2분기 숫자(claude.md:719-731, grok.md:4535-4548, chatgpt.md:5469-5509)는 공시와 모두 맞는다. 검산: 6.677억 / 7.01억 = 95.2%.
- 유통량의 전년 대비 증가율은 732.69 / 613.33 = 1.195, 곧 약 19%여서 Grok의 "+19%"와 맞는다.
- **세 답에 없고 내가 공시에서 더한 것: 플랫폼 보유 비율.** Circle 자신의 플랫폼에 있는 USDC의 비율이 1년 사이에 7.4%에서 19.5%로 늘었다. 이 숫자가 중요한 이유는 Coinbase에 주는 돈을 정하는 식 때문이다. 식에서 각자의 몫은 각자의 플랫폼에 있는 USDC의 양에 따라 정해진다(3.4절(Coinbase와의 계약)). 그래서 Circle의 플랫폼에 있는 양이 늘면 Circle에 남는 몫이 늘어난다 `[내 판단]`. RLDC 마진이 38%에서 41%로 오른 것과 방향이 같다.
- 금리가 내리면 유통량이 늘어도 이자가 줄어든다. 2분기에 유통량 평균은 25% 늘었는데(765.24 / 610.39) 준비금 수익은 5% 늘었다(6.677억 / 6.343억). 그 차이가 수익률이 4.1%에서 3.5%로 내린 효과다 `[내 판단]`.

### 3.3. 매출이 만들어지는 구조

- 공시의 설명 `[공시 확인]`: 준비금 수익은 유통 중인 스테이블코인의 양과 준비금 수익률의 함수다. 10-Q의 글은 "The reserve income that we generate is a function of (i) our stablecoins in circulation over a given period and (ii) the reserve return rate"이다(10-Q2:1888-1889). 준비금은 SOFR에 가까운 금리로 운용된다(10-Q2:1887).
- ChatGPT의 계산 예: USDC 1,000억 달러에 수익률 4%이면 한 해 준비금 수익이 약 40억 달러다(chatgpt.md:253-303).
- **선순환 구조(flywheel).** USDC의 순유통량 증가, 준비금 수익, 인프라 투자, 사용처 확대와 추가 수요를 잇는 것은 ChatGPT가 제시한 전략 해석이다(chatgpt.md:945-1007). 아래 도식도 그 가설을 설명하며, 모든 연결이 이미 실현되었다는 검증 결과는 아니다 `[내 판단]`. 금리와 유통비용도 달라지고, 거래 횟수가 늘어도 평균 유통량이 반드시 늘어나는 것은 아니므로, 이용량과 준비금 수익 사이의 관계는 별도로 확인해야 한다 `[내 판단]`(10-Q2:1888-1889).
- 준비금 수익과 총매출, 회사의 이익을 구분해야 한다. 2분기의 총매출 및 준비금 수익에서 유통, 거래와 기타 비용을 뺀 값은 701,315 - 412,470 = 288,845천 달러, 약 2.89억 달러다 `[공시 확인]`(`web-circle-q2-2026-earnings-release.md:431-439`). 이 값에서도 영업비용과 세금 등을 반영해야 순이익이 된다. Grok도 유통비용을 빼야 한다고 강조했다(grok.md:1682-1683).

```text
고객의 달러 --> Circle --> USDC 발행 (1달러에 1개)
                  |
                  v
               준비금 (현금, 미국 국채, 머니마켓펀드)
                  |
                  v
               준비금 수익                                 667,733천 달러
                  |
                  +---- 기타 매출 33,582천 달러를 더한다
                  v
               매출 및 준비금 수익                         701,315천 달러
                  |
                  +---- 유통, 거래와 기타 비용 412,470천 달러를 뺀다
                  |     (유통 협력사 지급과 그 밖의 비용)
                  v
               위 비용을 뺀 매출                           288,845천 달러
               영업비용과 세금 등을 반영하기 전의 값

전략 가설 (수익률과 비용, 수요 변화에 따른 조건부 연결)

+--> USDC의 순유통량이 는다
|         |
|         v
|    준비금이 는다
|         |
|         v
|    이자 수익이 는다
|         |
|         v
|    인프라에 투자한다 (Arc, CCTP, Gateway, CPN)
|         |
|         v
|    USDC를 쓸 곳이 는다
|         |
|         v
+--- USDC의 수요가 는다
```

**도식: 매출의 구성과 선순환 가설.** 위는 2026년 2분기 실적 발표의 손익계산서에 따른 것이다(`web-circle-q2-2026-earnings-release.md:431-439`). 단위는 천 달러이며, 준비금 수익과 기타 매출의 합계는 667,733 + 33,582 = 701,315이고 비용을 뺀 값은 701,315 - 412,470 = 288,845다. 아래의 고리는 ChatGPT가 그린 것을 옮겨 그렸다(chatgpt.md:985-1002). 준비금 수익은 해당 기간의 유통량과 수익률에 따라 달라지지만, 사용처 확대가 다시 순유통량 증가로 이어지는지는 별도로 검증해야 한다.

### 3.4. Coinbase와의 계약

- **지급액을 정하는 식** `[공시 확인]`(10-K:700-706). 공시의 글: "Payments to Coinbase are calculated from a daily payment base equal to net reserve income (after certain third-party reserve management fees and expenses), from which we retain an issuer portion, we and Coinbase receive allocations based on the amount of the stablecoin held on each party's platform, and Coinbase receives half of the remaining amount of income generated from stablecoins circulated in the broader ecosystem". 풀어 쓰면 네 단계다.
  1. 그날의 순 준비금 수익에서 Circle이 발행자 몫을 먼저 가진다.
  2. Circle과 Coinbase가 각자의 플랫폼에 있는 USDC의 양에 따라 몫을 받는다.
  3. 승인된 제3자 참여자에게 주는 돈을 뺀다.
  4. 남은 것, 곧 두 회사의 플랫폼 밖에서 도는 USDC에서 나온 수익의 절반을 Coinbase가 받는다.
```text
그날의 순 준비금 수익
  |
  +-- (1) Circle이 발행자 몫을 먼저 가진다
  |
  +-- (2) 각자의 플랫폼에 있는 USDC의 양에 따라 몫을 받는다
  |         +-- Circle의 플랫폼에 있는 양    -->  Circle
  |         +-- Coinbase의 플랫폼에 있는 양  -->  Coinbase
  |
  +-- (3) 승인된 제3자 참여자에게 주는 돈을 뺀다
  |
  +-- (4) 남은 것 (두 회사의 플랫폼 밖에서 도는 USDC에서 나온 수익)
            +-- 절반  -->  Coinbase

Circle의 플랫폼에 있는 USDC의 비율 (일평균 가중)
  전년 같은 분기   7.4%   ####
  2026년 2분기    19.5%   ##########
```

**도식: Coinbase에 주는 돈을 정하는 네 단계.** 위의 네 단계를 옮겼다. (4)에서 나머지 절반이 누구에게 가는지는 공시의 이 문장에 없어서 그리지 않았다. 아래 막대는 3.2절(2026년 2분기의 숫자)의 플랫폼 보유 비율이고 한 칸이 2%다. 세 답은 이 식을 그리지 않았다.

- Coinbase는 Circle의 소수 지분을 받았고, USDC와 EURC 상표를 영구히 쓸 수 있는 사용권도 받았다 `[공시 확인]`(10-K:696-699).
- **2025년에 Coinbase에 준 돈이 얼마인가에서 답이 갈렸고 공시가 가려 준다.**
  - ChatGPT는 1회차에 약 14억 달러라고 썼다(chatgpt.md:253-303). Claude는 교차 회차에서 이것을 확인하고 2024년은 9.245억 달러라고 덧붙였다(claude.md:136).
  - Grok은 "ChatGPT의 “2025년 Coinbase 관련 약 14억 달러”는 **과대일 가능성이 큽니다.**"[원문 그대로]라고 쓰고, 2025년은 여러 2차 자료가 약 9.08억 달러로 적는다고 했다(grok.md:1645-1646).
  - 10-K의 글: "For the years ended December 31, 2025 and 2024, we incurred \$1.4 billion and \$924.5 million respectively, of distribution costs in connection with our agreements with Coinbase"(10-K:3245-3246) `[공시 확인]`.
  - 그러므로 ChatGPT와 Claude가 맞고 Grok의 지적이 틀렸다 `[공시와 다름]`. 검산도 맞는다: 10-K는 2025년에 Coinbase에 준 유통비용이 4.384억 달러 늘었다고 적고(10-K:3366), 9.245억 + 4.384억 = 13.629억 달러여서 반올림하면 14억 달러다. Grok이 든 9.08억 달러는 2025년이 아닌 다른 해의 숫자로 보인다 `[내 판단]`. Grok의 최종 답에는 이 지적이 되풀이되지 않는다.
- 2026년의 지급액: 2분기 3.246억 달러(전년 3.323억 달러), 상반기 6.553억 달러(전년 6.355억 달러) `[공시 확인]`(10-Q2:2194-2196). Grok이 쓴 숫자와 같다(grok.md:1645-1646).
- 2025년 전체의 유통 및 거래 비용은 16.62억 달러이고 2024년은 10.11억 달러다 `[공시 확인]`(10-K:3328). 늘어난 6.507억 달러는 Coinbase 4.384억, Binance 1.521억, 그 밖의 유통 협력사 0.604억 달러로 나뉜다(10-K:3365-3368).
```text
Coinbase에 준 유통비용
  2024년  9.245억 달러    ############################
  2025년  약 14억 달러    #########################################

유통 및 거래 비용 전체
  2024년  10.11억 달러    ##############################
  2025년  16.62억 달러    ##################################################

2025년에 늘어난 6.507억 달러
  Coinbase              4.384억 달러    #############
  Binance               1.521억 달러    #####
  그 밖의 유통 협력사   0.604억 달러    ##
```

**도식: 유통비용의 크기.** 위 항목의 공시 숫자를 막대로 놓았다. 막대 세 칸이 1억 달러다. 2025년의 Coinbase 막대는 검산의 값 13.629억 달러로 그렸다. 세 답은 이것을 그리지 않았다.

- **계약의 기간과 갱신.** 첫 기간은 3년이고, 조건을 바꾸자는 합의가 없으면 3년씩 자동으로 갱신된다 `[공시 확인]`(10-K:714-716). Claude는 1회차에 2026년 8월에 만기가 오니 확인하라고 썼다가, 교차 회차에서 이미 결론이 나 있었다고 스스로 바로잡았다: Coinbase의 CFO가 7월 30일에 같은 조건으로 갱신된다고 밝혔고 Circle도 8월 5일에 2029년까지 3년 연장되었다고 확인했다는 것이다(claude.md:170) `[답의 주장]`. vault의 2분기 10-Q에서는 이 갱신을 찾지 못했다(검색: `grep -n -i -E 'three-year|renew' web-circle-q2-2026-10q.md`에서 Coinbase 계약에 관한 줄 0건).
- **상표를 잃을 수 있는 조항.** 10-K의 위험 요인에는 Coinbase와의 계약 때문에 상표의 소유나 사용을 잃을 수 있다는 항목이 따로 있다 `[공시 확인]`(10-K:2399-2419). 세 답에는 없고 9장에서 다룬다.
- **Open USD.** 2026년 6월에 Coinbase가 경쟁 스테이블코인 계획인 Open USD를 지지했고 CRCL 주가가 17% 넘게 내렸다는 보도가 있다. Claude가 2차 출처이고 확신도가 중간이라고 밝히고 썼다(claude.md:182) `[답의 주장]`. vault의 2분기 10-Q에는 Open USD가 나오지 않는다(검색: `grep -n -i 'Open USD' web-circle-q2-2026-10q.md`, 0건).

### 3.5. Binance와의 계약

이 절의 계약 내용은 2026년 9월 22일의 8-K로 확인했다 `[공시 확인]`(8-K(2026-09-22):45-51). 세 답의 읽기는 `[답의 주장]`이다.

- 2026년 9월 17일에 계약하고 9월 22일에 공개했다. Binance가 Circle의 주식 1억 달러어치를 샀고, 두 회사가 5년짜리 USDC 상업 계약을 맺었다(chatgpt.md:1313-1315, chatgpt.md:1656-1677, chatgpt.md:5307-5313, claude.md:719-731).
- Binance는 주당 80.84달러에 1,237,011주를 샀고 최대 2년 동안 팔 수 없다. 새 5년 계약은 2024년 11월과 2025년 8월의 계약을 대신한다(claude.md:451). 검산: 1,237,011 x 80.84 = 1.00억 달러 `[내 판단]`.
- 8-K의 글 `[공시 확인]`: "certain subsidiaries of Circle Internet Group, Inc. ... entered into arrangements with Binance that expand the parties’ existing strategic partnership relating to the promotion of USDC held through Circle’s Modular Smart Contract Wallet infrastructure service. The agreement supersedes and replaces the agreements the Company previously entered into with Binance in November 2024 and in August 2025"(8-K(2026-09-22):45, 굽은 아포스트로피는 [원문 그대로]). Circle은 그 지갑 서비스에 담긴 USDC의 양에 비례해 달마다 장려금을 준다(8-K(2026-09-22):46). 기간은 5년이고 정해진 일이 생기면 어느 쪽이든 끝낼 수 있다(8-K(2026-09-22):47).
- 주식 `[공시 확인]`: "1,237,011 shares ... at a purchase price of \$80.84 per share, for aggregate proceeds to the Company of \$100 million, reflecting a discount to the market price"(8-K(2026-09-22):49). 시장가보다 싸게 팔았다는 점은 세 답에 없다. 팔 수 없는 기간은 종결일부터 2년이 되는 날과 Binance가 정해진 사유로 상업 계약을 끝내는 날 가운데 이른 날까지다(8-K(2026-09-22):51).
- 세 답이 쓴 숫자(주식 수, 값, 5년, 앞선 두 계약을 대신함, 2년)는 모두 8-K와 맞는다.
- ChatGPT의 읽기: Circle의 병목은 USDC를 만들 수 있느냐가 아니라 USDC를 얼마나 많이 보유하고 유통하고 결제하게 만드느냐다. Coinbase에 더해 Binance까지 큰 유통 경로로 끌어들이고 있다는 뜻이다(chatgpt.md:1656-1677).
- Binance가 이미 큰 유통 협력사라는 점은 공시에 있다 `[공시 확인]`. 2025년에 Binance에 준 유통비용이 1.521억 달러 늘었다(10-K:3366-3367).
- 내가 덧붙이는 읽기: 유통 협력사가 Circle의 주주가 되는 것은 2023년에 Coinbase와 한 것과 같은 모양이다. 두 번 다 돈을 받아 가는 쪽에 회사의 지분을 주어서 이해를 묶었다 `[내 판단]`.

```text
                  USDC를 퍼뜨린다
Circle  <------------------------------  Coinbase, Binance

                  유통비용을 준다
Circle  ------------------------------>  Coinbase, Binance

                  Circle의 주식을 준다
Circle  ------------------------------>  Coinbase, Binance

  Coinbase   2023년 8월    약 840만 주 (Centre 지분 50%의 대가)
  Binance    2026년 9월    1,237,011주, 주당 80.84달러, 1억 달러
```

**도식: 유통 협력사가 주주가 되는 모양.** 위 "내가 덧붙이는 읽기"를 그렸다 `[내 판단]`. 숫자는 2.4절(USDC의 등장, CENTRE, Coinbase)과 이 절에 있다.

### 3.6. 규제 인가

- **Circle National Trust(연방 신탁은행).**
  - 10-Q의 글 `[공시 확인]`: "On July 9, 2026, the Company received final approval from the U.S. Office of the Comptroller of the Currency ("OCC") to establish First National Digital Currency Bank, N.A., a national trust bank that will operate under the name Circle National Trust. Circle National Trust opened on July 24, 2026 and is subject to direct federal oversight by the OCC. At opening, Circle National Trust offers fiduciary digital asset custody services to the Company and its affiliates"(10-Q2:1826-1828).
  - 최종 승인 날짜를 Claude는 2026년 7월 10일로 적었는데(claude.md:160), 공시는 7월 9일이다 `[공시와 다름]`. 하루 차이이고 발표일과 승인일의 차이일 수 있다 `[내 판단]`. 조건부 승인은 2025년 12월 12일이었다고 한다(claude.md:160) `[답의 주장]`.
  - 개업일 7월 24일은 세 답에 없고 공시에서 더했다.
  - **지금 하는 일과 앞으로 할 일을 나눠야 한다.** Grok은 1회차에 "준비금·수탁을 연방 감독 아래로 올리는 장치"[원문 그대로]라고 썼다(grok.md:166-167). ChatGPT와 Claude는 이것이 절반만 맞다고 지적했다: 지금 승인된 것은 디지털 자산 수탁이고, USDC 준비금의 운용은 앞으로의 일이다(chatgpt.md:1569-1597, claude.md:149-150). 공시의 글도 개업 때의 업무를 "the Company and its affiliates"를 위한 수탁으로만 적어서 두 답의 지적과 맞는다 `[공시 확인]`.
  - Claude는 1회차에 이 승인을 1차 출처로 확인하지 못했다고 썼다가(claude.md:63), 교차 회차에서 확인할 수 있는 사실이었고 준비금 운용이 뒤로 미뤄졌다는 조건을 놓쳤다고 스스로 바로잡았다(claude.md:171).
- **뉴욕주 신탁회사.** 10-Q의 글 `[공시 확인]`: "On July 31, 2026, the Company received a limited purpose trust charter from the New York Department of Financial Services to establish Circle Internet Trust Company LLC, a New York trust company"(10-Q2:1830-1831). 세 답은 이것을 "Circle New York Trust"라고 불렀다(chatgpt.md:1369-1383, claude.md:63). 공시의 법인명은 Circle Internet Trust Company LLC이고, 2분기 실적 보도자료는 같은 것을 "Circle New York Trust"라고 부른다 `[공시 확인]`(`web-circle-q2-2026-earnings-release.md:85-87`). 법인명과 영업상의 이름이 다른 것이다.
- **미국 밖의 인가.** 10-K가 2025년 말 기준으로 꼽는 주요 규제 체계는 다섯이다 `[공시 확인]`(10-K:580-593).

  | 곳 | 법인 | 인가 |
  |---|---|---|
  | 아부다비(ADGM) | Circle Internet MEA Ltd. | 금융 서비스 허가, 자금 서비스 제공자 |
  | 버뮤다 | Circle International Bermuda Limited | DABA 면허. USYC를 발행하고 Circle Mint 계정을 제공한다 |
  | 유럽연합 | Circle Internet Financial Europe SAS(프랑스) | 디지털 자산 서비스 제공자 등록, 전자화폐기관 면허. 유럽경제지역에서 USDC와 EURC를 발행한다 |
  | 싱가포르 | Circle Internet Singapore Pte Ltd. | 주요 결제기관 면허 |
  | 영국 | Circle UK Trading Limited | 전자화폐 발행 면허 |

  표의 한 행은 규제 체계 하나다.

  - Grok은 1회차에 캐나다와 일본을 넣었고 교차 회차에서도 그 목록을 자신의 장점으로 꼽았다(grok.md:112-125, grok.md:1663). Claude는 이것이 부정확하다고 지적했다: 10-K의 목록에 캐나다와 일본은 없고, 일본은 SBI VC Trade가 유통사 역할을 하는 구조여서 Circle이 직접 받은 인가가 아니다(claude.md:149-150). 공시의 목록은 Claude의 지적과 맞는다 `[공시 확인]`. 다만 공시의 목록은 "주요" 체계이므로 목록에 없다는 것만으로 캐나다에 등록이 전혀 없다고 말할 수는 없다 `[내 판단]`.
  - 버뮤다 법인이 USYC를 발행하고 Mint 계정을 제공한다는 점은 세 답에 없고 공시에서 더했다.
- 미국 안에서는 주마다의 송금업 면허와 뉴욕주 BitLicense를 가지고 있다 `[공시 확인]`(10-K:556).
- ChatGPT의 읽기: 규제 인가는 소프트웨어 제품은 아니지만 기관 금융으로 가려면 중요한 해자 후보다. Circle은 기술, 자산, 네트워크, 규제 인프라를 함께 쌓고 있다(chatgpt.md:5285-5303).
- Alliance Program이라는 협력사 제도가 있다(grok.md:166-167) `[답의 주장]`.

```text
미국
  +-- 연방    Circle National Trust
  |             2025년 12월 12일 조건부 승인 -> 2026년 7월 9일 최종 승인 -> 7월 24일 개업
  |             지금 하는 일: 회사와 계열사를 위한 디지털 자산 수탁
  |             앞으로의 일: USDC 준비금의 운용
  +-- 뉴욕주  Circle Internet Trust Company LLC (영업상의 이름 Circle New York Trust)
  |             2026년 7월 31일 한정 목적 신탁 인가
  +-- 주마다의 송금업 면허, 뉴욕주 BitLicense

미국 밖 (10-K가 꼽는 주요 규제 체계 다섯)
  +-- 아부다비(ADGM)   금융 서비스 허가
  +-- 버뮤다           DABA 면허. USYC 발행, Circle Mint 계정
  +-- 유럽연합(프랑스)  전자화폐기관 면허. USDC와 EURC 발행
  +-- 싱가포르         주요 결제기관 면허
  +-- 영국             전자화폐 발행 면허
```

**도식: 인가의 지도.** 위 항목과 표를 옮겼다. ChatGPT는 연방 신탁은행이 지금 하는 일과 앞으로 할 일을 나눠 그렸다(chatgpt.md:1569-1597).

### 3.7. 과거와 지금을 나란히 놓으면

ChatGPT와 Grok이 각자 만든 대비표를 합쳤다(chatgpt.md:5447-5465, grok.md:112-125). 표 전체가 `[답의 주장]`이다.

| 영역 | 과거 | 지금 |
|---|---|---|
| 소비자 앱 | Circle Pay, Circle Invest | 개인에게 직접 서비스하지 않는다. 결제는 CPN과 Managed Payments로 다른 회사에 공급한다 |
| 거래소와 중개 | Poloniex, Circle Trade | 직접 운영하지 않는다. 유통은 협력 거래소에 맡긴다 |
| 자본시장 | SeedInvest로 토큰화 증권 시도 | 크라우드펀딩은 철수했다. USYC, 실물자산 담보, Arc의 자본시장 인프라로 돌아서 들어간다 |
| 발행 자산 | 사실상 USDC 하나 | USDC, EURC, USYC, cirBTC, 협력사의 지역 스테이블코인 |
| 수익 | 처음에는 거래와 앱, 이후 준비금 이자 | 여전히 준비금 이자가 주력이고 기타 매출은 작다 |
| 고객 | 소매 이용자 | 은행, 결제 서비스 사업자, 거래소, 핀테크, 개발자, AI 에이전트 |
| 규제 | BitLicense 같은 주 단위 인가 | 여러 나라의 인가와 2026년의 연방 신탁은행 |
| 결제의 바탕 | 비트코인 | 스테이블코인 |
| 체인 | 남의 체인에 USDC를 발행 | 여러 체인을 유지하면서 자체 체인 Arc도 운영한다 |
| 중심 | 자체 앱 | 플랫폼과 네트워크 |

표의 한 행은 영역 하나다.

```text
과거                                          지금

Circle                                        Circle
  |  자체 앱 (Circle Pay, Circle Invest)        |  플랫폼과 네트워크
  v                                             v
소매 이용자                                   은행, 결제 서비스 사업자, 거래소, 핀테크, 개발자, AI 에이전트
                                                |
                                                v
                                              최종 사용자


ChatGPT가 그린 질문의 순서

돈을 인터넷처럼 움직일 수 없나                -->  USDC
그 돈을 어디서든 움직이게 하자                -->  CCTP, Gateway
그 돈이 돌아갈 체인도 만들자                  -->  Arc
그 위의 환전과 결제                           -->  StableFX, CPN
기업이 블록체인을 몰라도 쓰게 하자            -->  Digital Asset Accounts, Managed Payments
사람만이 아니라 AI도 경제 주체가 되게 하자    -->  Agent Stack
```

**도식: 직접 파는 회사에서 남을 거쳐 닿는 회사로.** 위 표의 "고객"과 "중심" 행, 그리고 아래 "전략의 끝 모양" 항목을 그렸다. ChatGPT의 그림을 옮겨 그렸다(chatgpt.md:5557-5586). 성공이 확인된 것은 USDC이고 나머지는 검증받는 단계라는 단서가 아래 항목에 있다.

- ChatGPT의 한 문장: Circle은 금융 상품을 소비자에게 직접 파는 회사에서, 다른 금융기관, 기업, 개발자, AI가 돈을 발행하고 보관하고 교환하고 옮기고 결제하게 하는 인프라 회사로 바뀌었다(chatgpt.md:5447-5465, chatgpt.md:874-941).
- Grok의 한 문장: 과거에는 여러 개의 가상자산 사업을 가진 회사였고, 지금은 규제받는 스테이블코인을 화폐 단위로 쓰는 금융 운영체제를 만들고 있다(grok.md:112-125).
- **바뀌지 않은 것.** ChatGPT는 Circle이 새 꿈을 꾸는 것처럼 보여도 2013년부터 하던 말이 되풀이된다고 읽었다. 처음에는 인터넷과 비트코인으로, 지금은 인터넷과 스테이블코인과 블록체인으로 돈을 데이터처럼 옮기려 한다. 달라진 것은 직접 소비자 서비스를 만들던 회사가 인프라 회사가 되었다는 점이다(chatgpt.md:874-941).
- **전략의 끝 모양.** ChatGPT는 질문이 이어지는 순서로 그렸다: 돈을 인터넷처럼 움직일 수 없나(USDC), 그 돈을 어디서든 움직이게 하자(CCTP, Gateway), 그 돈이 돌아갈 체인도 만들자(Arc), 그 위의 환전과 결제(StableFX, CPN), 기업이 블록체인을 몰라도 쓰게 하자(Digital Asset Accounts, Managed Payments), 사람만이 아니라 AI도 경제 주체가 되게 하자(Agent Stack)(chatgpt.md:5550-5592).
- 그리고 같은 대목의 단서: "**현재 성공이 확인된 것은 USDC이고, 나머지의 상당수는 아직 성공 여부를 검증받는 단계**"원문 그대로. 공시의 숫자가 이 단서를 받친다: 기타 매출은 2분기 매출의 4.8%다(3.2절(2026년 2분기의 숫자)).
- 내가 공시에서 더하는 것: 기타 매출의 구성. 10-Q는 기타 매출을 셋으로 나눈다: 구독과 서비스(통합과 유지보수, 펀드 운용, 기간제 이용, 사용자 수 기준 사용권), 거래 매출(스테이블코인과 USYC의 상환 수수료, 블록체인 보상, CCTP를 포함한 인프라 이용), 그 밖의 매출(되풀이되지 않는 서비스와 중단된 옛 제품의 수수료) `[공시 확인]`(10-Q2:1340-1357). 10-K는 2025년에 기타 매출이 9,470만 달러 늘어난 이유로 통합 서비스, 블록체인 보상, 상환 수수료, 펀드 운용 수수료를 든다 `[공시 확인]`(10-K:3361-3363). 이 목록에 CPN이나 StableFX의 수수료는 이름으로 나오지 않는다. 그래서 "기타 매출이 늘고 있다"는 것을 CPN이나 StableFX가 돈을 벌기 시작했다는 뜻으로 읽을 근거는 공시의 이 대목에는 없다 `[내 판단]`.

## 4. Arc, CCTP, StableFX, CPN만이 주요 기술인가

### 4.1. 답과 전체 지도

세 답의 공통된 답은 "아니다"다. 네 가지는 큰 축 넷을 짚었지만 전체의 일부다.

- 세 답이 1회차부터 같은 답을 했다(chatgpt.md:335-379, claude.md:36-38, grok.md:129-131). 서로의 답을 보기 전이므로 독립된 일치다 `[내 판단]`.
- 네 가지가 각각 맡는 자리는 이렇다: Arc는 블록체인, CCTP는 체인 사이의 이동, StableFX는 환전, CPN은 결제다(chatgpt.md:5336-5443, grok.md:4552-4586). ChatGPT는 질문이 큰 축 넷을 잘 짚었다고 평가하고, 이것만 보면 돈과 자산, 발행과 유동성, 개발자 도구, 기업용 계정, AI의 층이 빠진다고 했다.
- Grok이 꼽은, 빠져서는 안 되는 다섯: Gateway, Mint, Wallets, xReserve, USYC(grok.md:4552-4586).
- Claude의 판단: 사업으로 보면 핵심은 USDC와 그것을 받치는 Mint와 준비금 운용이고, 질문의 네 가지는 "준비금 이자 의존에서 벗어나기 위한 성장 옵션"[원문 그대로]에 가깝다(claude.md:67).
- 공시가 회사의 제품을 나누는 방식 `[공시 확인]`(10-K:317-319, 10-Q2:1865): Arc와 개발자 인프라, Circle Digital Assets and Services(USDC, EURC, USYC, cirBTC, Circle Mint, xReserve), Circle Applications(CPN, StableFX). cirBTC는 10-K에는 없고(검색: `grep -c cirBTC web-circle-fy2025-10k.md`, 0건) 2분기 10-Q에 들어갔다.

**제품과 사업 지원 구조의 지도.** 세 답의 최종 답을 합쳤다(chatgpt.md:5336-5443, claude.md:741-756, grok.md:4552-4586). ChatGPT의 기능별 분류를 참고하되, 자산, 제품과 서비스, 협력 제도와 법인을 구분하도록 내가 고쳤다 `[내 판단]`. 이 구분은 각 절에서 설명하는 항목의 성격과 역할을 반영한 것이며, 공시의 사업 분류를 그대로 옮긴 것은 아니다.

표에는 개별 제품과 서비스, 본문이 별도로 이름을 든 하위 결제 서비스, 사업을 지원하는 제도와 법인을 적었다. Agent Stack처럼 묶음으로 정의된 서비스의 구성 요소는 해당 절에서 풀었다. 근거 열은 각 절에서 확인한 범위를 옮긴 것이며, 공시에 있는 정의나 계약을 확인한 것과 현재의 출시 단계나 모든 세부 기능을 확인한 것을 구분한다.

| 영역 | 항목 | 하는 일 | 확인 범위와 유보 | 다루는 절 |
|---|---|---|---|---|
| 돈과 자산 | USDC, EURC | 달러와 유로 스테이블코인 | 정의와 상환 구조는 `[공시 확인]` | 4.2 |
| | USYC | 펀드 지분을 나타내며 운용 수익이 가격에 반영되는 자산 | 정의와 용도는 `[공시 확인]`; 청약과 상환은 `[Circle 글 확인]` | 4.2 |
| | cirBTC | 수탁한 BTC를 1:1로 담보하고 BTC로 상환하는 토큰 | 정의는 `[공시 확인]`; 수탁과 상환은 `[Circle 글 확인]`; 출시일의 차이는 본문 참조 | 4.2 |
| 발행과 유동성 | Circle Mint | 기관이 Circle에 USDC/EURC의 발행과 상환, BTC와 cirBTC의 교환을 요청하는 서비스 | 핵심 기능은 `[공시 확인]`; cirBTC 지원은 `[Circle 글 확인]` | 4.3.1 |
| | xReserve | 다른 체인이 USDC로 상환할 수 있고 USDC와 호환되는 자체 스테이블코인을 발행하도록 지원 | 기능과 구독료는 `[공시 확인]` | 4.3.2 |
| 체인 사이의 이동 | CCTP | 기존 체인의 USDC를 소각하고 목적 체인에서 다시 발행하는 프로토콜 | 전송 기능은 `[공시 확인]`; 작동 방식은 `[Circle 글 확인]`; 버전별 상태는 본문 참조 | 4.4.1 |
| | Gateway | 계약에 예치한 USDC를 통합 잔고로 관리하고 목적 체인에서 USDC로 받는 서비스 | 통합 잔고는 `[공시 확인]`; 예치와 목적 체인 발행은 `[Circle 글 확인]` | 4.4.2 |
| 블록체인 | Arc | 금융거래를 겨냥한 자체 체인 | 설계와 일정은 `[공시 확인]`; 공개 메인넷의 출시 주장과 예정일은 본문에서 구분한다 | 4.5 |
| 네트워크 토큰 | ARC | Arc의 지분 예치, 거버넌스 등에 쓰도록 계획한 토큰 | 계획과 사전 판매는 `[공시 확인]`; 공개 배포 조건은 본문 참조 | 4.6 |
| 개발자 도구 | Circle Wallets, Circle Contracts | 앱에 지갑을 넣고 스마트 계약을 만들고 관리한다 | 핵심 기능은 `[공시 확인]` | 4.7 |
| | App Kits | 공시가 핵심 개발자 서비스로 분류한 도구 | 분류는 `[공시 확인]`; Arc App Kits와의 관계는 미확인 | 4.7 |
| | Paymaster | 사용자가 USDC로 가스비를 내도록 지원한다 | 이 문서에서는 `[답의 주장]` | 4.7 |
| | Arc Studio, Arc App Kits, Arc Portal | 세 답이 Arc의 개발 도구로 소개한 항목 | `[답의 주장]`; App Kits와 Arc App Kits의 관계는 미확인 | 4.7 |
| 결제 | CPN | 금융기관 사이의 결제 경로, 규제 준수와 정산을 조정한다 | 결제망의 정의와 용도는 `[공시 확인]` | 4.8.1 |
| | Fiat Payments, Stablecoin Payments | Grok이 CPN의 하위 제품으로 열거한 항목 | 제품 구분은 `[답의 주장]`; 각각의 기능은 미확인 | 4.8.2 |
| | CPN Managed Payments | 고객은 법정화폐를 다루고 Circle이 전환, 지갑과 결제 운영을 맡는다 | 운영 범위는 `[Circle 글 확인]`; USDC 발행과 소각의 세부 절차는 `[답의 주장]` | 4.8.3 |
| 환전 | StableFX | 기관이 API로 환전 거래를 요청하고 Arc의 스마트 계약으로 정산한다 | 설계는 `[공시 확인]`; API와 계약의 역할은 `[Circle 글 확인]`; 베타 종료 여부는 본문 참조 | 4.9 |
| 에이전트 서비스 | Agent Stack | AI 에이전트의 지갑, 도구, 서비스 거래와 소액 결제를 묶어 제공한다 | 공시의 구성은 `[공시 확인]`; Circle Skills는 `[답의 주장]` | 4.10 |
| 기업용 계정 | Digital Asset Accounts | 고객 기업이 자기 상표로 스테이블코인 계정 서비스를 제공하도록 지원한다 | 기능 소개는 `[답의 주장]`; 자체 코인 발행과의 구분은 `[내 판단]` | 4.11 |
| 외부 자산 연결 | Partner Stablecoins | 제3자 스테이블코인 발행사를 CPN, StableFX, USDC 유동성과 잇는 협력 제도 | StableFX의 제3자 지원 설계는 `[공시 확인]`; 세부 연결 설명과 통화 목록은 `[답의 주장]` | 4.12 |
| 규제와 수탁 | Circle National Trust | 개업 때 회사와 계열사에 디지털 자산 수탁을 제공하는 연방 신탁은행 | 인가와 개업 때의 업무 범위는 `[공시 확인]` | 4.13 |
| | 뉴욕주 신탁회사 | 뉴욕주의 한정 목적 신탁 인가를 받은 법인 | 인가와 법인명은 `[공시 확인]` | 4.13 |
| 유통 협력사 | Coinbase, Binance | 계약을 통해 USDC 보유와 유통을 넓히는 협력사 | 계약은 `[공시 확인]`; 역할에 관한 해석은 각 절 참조 | 4.14 |
| 법정화폐 지급 | Tazapay(인수 진행 중) | 결제 후 법정화폐가 수취인에게 도달하는 구간을 지원하는 회사 | 인수 계약은 `[공시 확인]`; 앞으로의 통합은 완료된 기능과 구분한다 | 4.15 |

표의 한 행은 항목 하나 또는 같은 성격의 묶음이다. 빈 칸은 위 행과 같은 영역이라는 뜻이다. 아래 본문도 이 표와 같은 영역, 같은 순서로 구성했다. 결제는 결제망, 하위 결제 서비스, 결제 운영 서비스로 나눠 설명한다. 기능이 다른 영역과 연결되는 경우에는 해당 절을 가리키며, 인수 내역은 기능별 설명 뒤에서 함께 다룬다.

```text
제품과 서비스 (기능별로 나열한다)
|
+-- 돈과 자산          USDC, EURC, USYC, cirBTC
+-- 발행과 유동성      Circle Mint, xReserve
+-- 체인 사이의 이동   CCTP, Gateway
+-- 블록체인           Arc
+-- 네트워크 토큰      ARC (공시에서는 쓰임과 배포를 계획으로 설명한다)
+-- 개발자 도구
|     +-- Circle Wallets, Circle Contracts, App Kits
|     +-- Paymaster                                      [답의 주장]
|     +-- Arc Studio, Arc App Kits, Arc Portal            [답의 주장]
|           App Kits와 Arc App Kits의 관계는 미확인
+-- 결제
|     +-- 결제망        CPN
|     +-- 하위 서비스   Fiat Payments, Stablecoin Payments [답의 주장]
|     +-- 운영 서비스   CPN Managed Payments              운영 범위는 [Circle 글 확인]
+-- 환전               StableFX
+-- 에이전트 서비스    Agent Stack (구성 요소는 4.10절에서 구분한다)
+-- 기업용 계정        Digital Asset Accounts            [답의 주장]

사업을 지원하는 제도와 법인
|
+-- 외부 자산 연결     Partner Stablecoins (협력 제도)
+-- 규제와 수탁        Circle National Trust, 뉴욕주 신탁회사
+-- 유통 협력사        Coinbase, Binance
+-- 법정화폐 지급      Tazapay (인수 진행 중)
```

**도식: 제품과 사업 지원 구조.** 위 표를 기능별 목록으로 옮겼다. 나열 순서가 이용 순서나 기술적 의존 관계를 뜻하지는 않는다. 앞서 세 답의 층 구조를 참고해 그렸던 그림(claude.md:746-754, chatgpt.md:4655-4676, chatgpt.md:5386-5439)을 본문의 역할 구분에 맞춰 다시 그렸다 `[내 판단]`. 도식에서 따로 표시하지 않은 항목도 위 표의 확인 범위와 유보를 따른다.

- ChatGPT가 1회차에 아홉 단계로 줄인 것도 같은 지도다: 돈을 만든다(USDC, EURC, USYC), 돈을 은행과 잇는다(Mint), 여러 체인에서 움직인다(CCTP, Gateway), 남의 스테이블코인까지 끌어들인다(xReserve, Partner Stablecoins), 돈이 실행되는 체인도 만든다(Arc), 그 위에서 환전한다(StableFX), 국제 송금한다(CPN), 개발자가 금융 앱을 만든다(Wallets, Contracts, Paymaster), AI도 경제 활동을 한다(Agent Stack)(chatgpt.md:811-870).
- **지도가 회차마다 넓어졌다.** ChatGPT는 1회차 지도에 cirBTC, Digital Asset Accounts, 규제 인프라가 없었고 교차 회차에서 스스로 넣었다(chatgpt.md:1181-1207, chatgpt.md:1681-1759). Claude는 cirBTC를 빠뜨린 것을 자신의 가장 큰 누락으로 꼽았다(claude.md:172). 1회차에 cirBTC를 넣은 것은 Grok뿐이다(grok.md:144-148, grok.md:1660).
- **지도가 곧 매출은 아니다.** Grok은 Arc 메인넷이 이제 막 열렸으므로 이 제품들이 매출을 의미 있게 나누는 단계가 아니라고 적었다(grok.md:4552-4586, grok.md:169-178). 공시의 숫자는 3.2절(2026년 2분기의 숫자)에 있다.

### 4.2. 돈과 자산: USDC, EURC, USYC, cirBTC

**USDC.**

- 달러와 1:1로 바꿀 수 있는 스테이블코인이고 회사 경제의 중심이다. 발행은 Circle만 한다 `[공시 확인]`(10-K:443-449).
- Circle은 발행 주체이고, Circle Mint는 자격을 갖춘 기관 고객이 Circle에 발행과 상환을 요청하는 서비스다 `[Circle 글 확인]`(블로그 mint-onramp:25, 53, 59). 따라서 "Circle에 요청하거나 Mint에서 발행한다"는 별개의 발행사 선택으로 나누면 안 된다 `[내 판단]`. 거래소에서 이미 발행된 USDC를 사는 일과 새로운 법정화폐를 넣어 발행을 요청하는 일도 구분해야 한다 `[내 판단]`.
- 2025년 말 유통량은 750억 달러가 넘고, 30개의 공개 블록체인에 직접 발행되어 있다 `[공시 확인]`(10-K:349-351). Claude가 같게 썼다(claude.md:48-50).
- 2026년 2분기 말은 732.69억 달러다(3.2절(2026년 2분기의 숫자)). 9월의 Arc 메인넷 발표 때는 740억 달러가 넘었다(chatgpt.md:4685-4766) `[답의 주장]`. 2025년 말보다 줄어 있다는 점을 세 답은 말하지 않았다 `[내 판단]`.
- 1:1 준비금과 월마다의 증명 보고가 있다(grok.md:144-148) `[답의 주장]`.
- Circle Mint의 고객이 아닌 최종 사용자도 일부는 Circle에 직접 상환을 청구할 수 있고, Circle은 이것을 "redeemer of last resort"라고 부른다 `[공시 확인]`(10-K:445-447). Grok이 "최후 상환자 역할"이라고 쓴 것이 이것이다(grok.md:112-125).

**EURC.**

- 유로 스테이블코인이다. 2022년에 Euro Coin(EUROC)으로 나왔고 나중에 EURC로 이름을 맞췄다(chatgpt.md:408-438, grok.md:1676) `[답의 주장]`.
- EU의 MiCA 아래에서 발행된다(grok.md:144-148). 프랑스 법인이 전자화폐기관 면허로 유럽경제지역에서 USDC와 EURC를 발행한다 `[공시 확인]`(10-K:586-590).
- 준비금은 모두 현금으로만 보유한다 `[공시 확인]`(10-K:1035).

**USYC.**

- USDC와 성격이 다르다. USDC는 현금에 가깝고 이자가 없으며, USYC는 머니마켓펀드의 지분을 토큰으로 나타낸 것이어서 이자가 붙는다 `[공시 확인]`(10-K:450-453).
- **청약과 관리.** 적격 기관은 신원 확인과 자금세탁 방지 심사를 거치고 허용된 지갑을 등록한다. 청약과 상환은 USDC로 정산한다 `[Circle 글 확인]`(블로그 usyc-bnb:47-57, 블로그 usyc-solana:25-27, 62-68). 토큰이 나타내는 지분은 케이맨 제도의 Hashnote International Short Duration Fund Ltd. 지분이고, Circle International Bermuda Limited가 펀드의 토큰 관리자로 USYC를 관리한다 `[Circle 글 확인]`(블로그 usyc-bnb:57).
- **수익과 상환.** 운용 수익은 USYC의 가격에 반영되고, 고객은 USYC를 상환해 USDC를 받는다. 즉시 상환할 수 있는 범위와 처리 시점은 펀드의 유동성과 네트워크 상태 등에 좌우된다 `[Circle 글 확인]`(블로그 usyc-bnb:33-43, 57, 블로그 usyc-solana:53-58). USDC처럼 가격이 항상 1달러에 고정되는 구조로 설명하면 안 된다 `[내 판단]`. 같은 수량을 보유해도 지분 가격이 오르면 상환 금액이 커지는 구조다.
- 주로 디지털 자산 시장에서 담보로 쓰려는 것이다 `[공시 확인]`(10-K:450-451). 증권법의 등록 면제에 기대어 제공되고, 2025년 2월부터 버뮤다에서 미국 밖의 적격 고객에게 발행한다(10-K:451-452, 10-K:460-464).
- 2025년 1월에 Hashnote를 인수해서 얻었다 `[공시 확인]`(10-K:3013-3016). 인수 대가는 약 1.001억 달러이고 현금 1,020만 달러와 Class A 주식 약 290만 주로 이루어진다. ChatGPT의 "약 1억 달러"(chatgpt.md:408-438)와 Claude의 "1.001억 달러"(claude.md:779-780)가 공시와 맞는다.
- 인수 당시 USYC의 규모를 ChatGPT는 약 15.2억 달러로 적었고(chatgpt.md:408-438, chatgpt.md:4685-4766), Claude는 당시 보도가 12.5억에서 13억 달러였다고 의문을 달았다(claude.md:132). 이 어긋남은 풀리지 않았고, vault의 10-K에서 인수 당시의 운용 규모는 찾지 못했다 `[답의 주장]`.
- ChatGPT의 읽기: Circle이 결제용 돈을 넘어 토큰화된 자본시장과 실물자산으로 넓히려는 움직임이다(chatgpt.md:4685-4766). 공시도 담보 관행이 이자가 붙는 토큰화 펀드로 옮겨 가고 있다고 적는다 `[공시 확인]`(10-K:454-458).

**cirBTC.**

- 비트코인을 1:1로 담보한 토큰이고 Circle이 발행한다 `[공시 확인]`(10-Q2:126).
- **발행, 관리와 상환.** 기관 고객의 발행과 상환 요청은 Circle Mint가 지원한다 `[Circle 글 확인]`(블로그 cirbtc-ethereum:47). 담보 BTC는 Circle 계열사를 통해 보유하고 Circle National Trust가 회사의 일반 자산과 분리해 수탁하며, 이에 대응하는 cirBTC를 발행한다. 상환 때에는 대응하는 cirBTC를 유통에서 제거하고 BTC를 반환한다 `[Circle 글 확인]`(블로그 cirbtc-reserve:49-64). 이 과정에서 비트코인 네트워크의 BTC 자체를 새로 발행하거나 소각하는 것은 아니다 `[내 판단]`.
- **준비금 관찰.** 공개된 BTC 주소, Chainlink의 준비금 증명 서비스(Proof of Reserve), 발행된 cirBTC 수량을 함께 비교하도록 설계되어 있다 `[Circle 글 확인]`(블로그 cirbtc-reserve:55-62). 이 설명은 회사가 제시한 수탁과 검증 구조이며, 준비금이나 상환 권리를 내가 독립적으로 검증한 결과는 아니다.
- Claude는 2026년 6월 9일에 이더리움에서, 9월 21일에 Arc에서 나왔다고 적었다(claude.md:159, claude.md:779-780) `[답의 주장]`. 다만 Circle의 이더리움 출시 글에 표시된 날짜는 "June 8, 2026"이고, 그 글은 이미 가동 중이라고 발표했다 `[Circle 글 확인]`(블로그 cirbtc-ethereum:7-8, 27). 따라서 6월 9일을 확인된 출시일로 쓰지는 않는다. Arc의 정확한 출시일은 이 보완에서 확인하지 않았다.
- Grok은 기관용이고 온체인으로 준비금을 검증한다고 설명했고(grok.md:144-148), ChatGPT는 교차 회차에서 공식 제품이며 이더리움과 Arc에서 제공된다고 적었다(chatgpt.md:1482-1504). 위 공식 글로 수탁, 발행과 상환 구조를 보완했다. vault에 cirBTC를 다룬 문서가 있다: circle-cirbtc-reading.md.

```text
Circle이 다루는 자산
|
+-- USDC                  달러와 1:1로 바꾼다. 이자가 없다
+-- EURC                  유로 스테이블코인. 준비금은 모두 현금
+-- USYC                  펀드 지분을 나타낸다. 수익이 가격에 반영된다. USDC로 청약하고 상환한다
+-- cirBTC                비트코인을 1:1로 담보한 토큰. 이더리움과 Arc에서
```

**도식: Circle이 다루는 자산.** 위 자산 항목을 옮겼다. ChatGPT가 cirBTC를 따로 그렸다(chatgpt.md:1482-1504). cirBTC의 제공 체인은 위 항목의 `[답의 주장]`을 따른다.

### 4.3. 발행과 유동성

Circle Mint는 기관의 USDC/EURC 발행과 상환, BTC와 cirBTC의 교환을 지원한다. xReserve는 다른 체인이 USDC로 상환할 수 있는 자체 스테이블코인을 발행하도록 지원한다. 이 절에서는 발행을 지원하는 역할에 따라 두 도구를 함께 설명한다 `[내 판단]`(10-K:466-490, 블로그 cirbtc-ethereum:47).

#### 4.3.1. Circle Mint

- 기관이 법정화폐와 USDC, EURC를 서로 바꾸는 입구다. 자주 빠지지만 기초가 되는 제품이라고 ChatGPT가 강조했다(chatgpt.md:442-483, chatgpt.md:4770-4793).
- Circle에 직접 발행을 요청하는 일과 Circle Mint를 이용하는 일을 별개의 발행 주체로 나누지 않는다. Circle이 발행하고 Mint가 기관 고객의 요청을 받는 서비스다 `[Circle 글 확인]`(블로그 mint-onramp:25, 53, 59). USDC/EURC의 발행과 상환에서는 달러와 유로가 대응 자산이고, cirBTC에서는 BTC가 대응 자산이다. 유로를 USDC로 바꾸는 등 환전을 결합한 경로도 있으므로, 지원 자산들이 모두 서로 1:1로 교환되는 것으로 그리면 안 된다 `[내 판단]`(블로그 mint-onramp:31-33, 51).
- 공시의 설명 `[공시 확인]`(10-K:466-482):
  - 기관 고객에게 발행, 상환, 송수신, 수탁을 제공한다.
  - 계정을 열려면 법인, 소유자, 사업, 쓰려는 목적에 관한 서류를 내고 신원 확인, 제재 심사, 적합성 심사를 통과해야 한다.
  - 발행은 무료다. 상환은 두 가지다: 영업일 2일 안에 시작되는 기본 상환은 무료이고, 거의 즉시 시작되는 표준 상환은 소액의 수수료를 받는다.
  - 바탕은 은행망과의 연결이다. 정산 은행을 통해 1차 유동성(스테이블코인과 법정화폐의 교환)을 공급한다.
- 발행이 무료이고 상환 수수료가 작다는 것은 세 답에 없다. 나는 이 가격 정책을 USDC의 접근성과 유통을 넓히려는 방식으로 해석한다 `[내 판단]`. 다만 수수료가 작다는 사실만으로 Mint의 수익 역할을 부정할 수는 없다. 공시는 디지털 자산의 상환 수수료를 기타 매출에 포함한다 `[공시 확인]`(10-K:3231-3236).
- Mint에서 cirBTC도 다룬다는 설명은 세 답에 있었고(chatgpt.md:4770-4793, grok.md:152), 공식 글에서도 기관의 발행과 상환을 지원한다고 확인했다 `[Circle 글 확인]`(블로그 cirbtc-ethereum:47). 다만 Grok이 "법정화폐 ↔ USDC/EURC/cirBTC"원문 그대로로 쓴 것을 Claude가 바로잡았다: cirBTC는 비트코인을 담보로 하는 토큰이고 법정화폐로 바꾸는 상품이 아니다(claude.md:152). Claude는 Grok의 글을 "법정화폐 ↔ cirBTC"[원문 그대로]로 줄여서 옮겼다. ChatGPT의 최종 그림은 넣는 쪽을 "USD/EUR/BTC"로 적어서 이 지적과 맞는다.
- 185개국 이상으로 송금하는 길이 있다(grok.md:152) `[답의 주장]`.

```text
발행   은행 계좌의 법정화폐  -->  Circle Mint  -->  USDC, EURC          무료

상환   USDC, EURC  -->  Circle Mint  -->  은행 계좌의 법정화폐
         기본 상환 (영업일 2일 안에 시작)     무료
         표준 상환 (거의 즉시 시작)           소액의 수수료

cirBTC 발행   BTC를 수탁한다  -->  Circle Mint  -->  대응하는 cirBTC
cirBTC 상환   cirBTC를 유통에서 제거한다  -->  Circle Mint  -->  BTC 반환

계정을 열려면: 서류 제출, 신원 확인, 제재 심사, 적합성 심사
```

**도식: Circle Mint의 두 방향.** USDC/EURC는 위 공시의 설명을, cirBTC는 위 공식 글의 수탁과 교환 구조를 옮겼다. ChatGPT는 발행 쪽만 그렸고(chatgpt.md:4779-4788), 상환 쪽은 위 설명에서 내가 그렸다. 수수료 설명은 USDC/EURC에 관한 공시를 따른다.

#### 4.3.2. xReserve

- 2025년 11월에 나왔다 `[공시 확인]`(10-K:487).
- 푸는 문제 `[공시 확인]`(10-K:484-487): USDC가 직접 발행되지 않는 체인에서는 USDC를 스마트 계약에 잠그고 같은 양의 "bridged USDC"를 발행해 왔는데, 이것은 원래의 USDC와 호환되지 않아서 유동성이 체인마다 갇힌다.
- 하는 일: 체인을 운영하는 팀이 USDC로 상환할 수 있고 USDC와 호환되는 자체 스테이블코인을 내게 한다 `[공시 확인]`(10-K:487-488).
- **연결 방식.** xReserve는 다른 체인을 하나 더 만드는 제품이 아니라, USDC를 맡는 스마트 계약과 Circle의 증명 서비스(attestation service)를 연결하는 인프라다. 출시 글의 예에서는 이더리움의 xReserve 계약에 USDC를 예치하고, Circle이 예치를 확인한 증명에 서명하면 상대 체인이 그 증명을 사용해 자체 스테이블코인을 발행한다 `[Circle 글 확인]`(블로그 xreserve-launch:25-27, 43-46, 52-60). USDC는 준비금으로 남고 상대 체인에는 별도 토큰이 생긴다.
- **반대 방향과 다른 체인으로의 이동.** 상대 체인의 토큰을 소각한 뒤 출금을 요청하면 xReserve가 소각을 확인하고 증명에 서명한다. 목적 체인은 이 증명을 사용해 USDC 또는 USDC를 담보로 한 토큰을 지급하는 절차를 진행한다. 지원되는 경로에서는 CCTP나 Gateway를 연결한다 `[Circle 글 확인]`(블로그 xreserve-launch:36, 64-68). 새 체인을 경유해서 연결하는 방식으로 설명하면 안 된다 `[내 판단]`.
- 연결된 체인: Aleo, Canton, Cardano, Stacks, 그리고 Movement까지 다섯(chatgpt.md:487-580, claude.md:139, claude.md:778) `[답의 주장]`.
- **구독료를 받는가에서 답이 갈렸고 공시가 가려 준다.**
  - Claude는 1회차에 구독료를 받는다고 썼다(claude.md:52).
  - ChatGPT는 이 표현의 근거가 약하다고 하고, 약관에는 거래 크기와 네트워크 수수료에 따른 수수료가 있을 수 있다고만 되어 있어서 "이 표현은 삭제하는 게 맞습니다. **확신도: 높음.**"[원문 그대로]이라고 썼다(chatgpt.md:1416-1438). 같은 회차의 끝에서도 이것을 1차 자료로 다시 확인한 오류로 꼽았다(chatgpt.md:1782-1838).
  - 10-K의 글: "Participation in xReserve is permissioned and we charge a subscription fee for blockchain teams to use xReserve"(10-K:488-489) `[공시 확인]`.
  - 그러므로 Claude가 맞고, ChatGPT의 지적이 틀렸다 `[공시와 다름]`. Claude의 최종 표에는 구독료가 빠져 있는데(claude.md:778), 틀린 지적을 받아들여 맞는 내용을 뺀 것으로 보인다 `[내 판단]`.
  - 이 사례에서 배울 점: "확신도 높음"이라는 말은 확인의 근거가 아니다. ChatGPT는 개발자 약관을 보았고 10-K의 해당 문장은 보지 않았다 `[내 판단]`.
- 참여는 허가제다 `[공시 확인]`(10-K:488).
- ChatGPT의 읽기: 다른 체인의 스테이블코인이 자라면 그것을 받치는 USDC의 수요가 늘어난다. 남의 성장을 USDC의 수요로 바꾸는 구조다(chatgpt.md:487-580, chatgpt.md:4797-4887).

```text
xReserve: 예치와 소각의 증명으로 기존 체인을 연결한다

  발행: USDC를 xReserve 계약에 예치한다
          --> Circle이 예치를 증명한다
          --> 상대 체인이 자체 스테이블코인을 발행한다 (1:1)

  상환과 전송: 상대 체인의 자체 스테이블코인을 소각한다
                --> Circle이 소각을 확인하고 증명을 낸다
                --> 지원되는 목적 체인에서 USDC 또는 담보 토큰을 받는다

  다른 체인의 USDC에 연결하는 지원 경로: CCTP, Gateway

  그 전의 방식: USDC를 스마트 계약에 잠그고 "bridged USDC"를 발행한다
                원래의 USDC와 호환되지 않아서 유동성이 체인마다 갇힌다
```

**도식: xReserve의 발행 구조.** 위 공시와 공식 글의 설명을 옮겼다. ChatGPT가 예치와 발행의 구조를 그렸고(chatgpt.md:554-561), 소각과 목적 체인 수령의 방향은 공식 글로 보완했다.

### 4.4. 체인 사이의 이동: CCTP, Gateway

CCTP는 기존 체인에서 USDC를 소각하고 목적 체인에서 다시 발행하는 프로토콜이다. Gateway는 기존 체인의 계약에 예치한 USDC를 하나의 잔고로 접근하고 목적 체인에서 USDC를 받을 수 있게 하는 서비스다. 둘 다 기존 블록체인 위의 계약과 Circle의 증명 서비스를 사용하며 자체 블록체인은 아니다 `[Circle 글 확인]`(블로그 crosschain-consolidation:93, 블로그 gateway-guide:74-82). 발행을 지원하는 xReserve의 상세 설명은 4.3.2절(xReserve)에 두었다.

#### 4.4.1. CCTP(Cross-Chain Transfer Protocol)

- 보내는 체인에서 USDC를 태우고, Circle이 증명을 내고, 받는 체인에서 같은 양을 새로 발행한다. 다리(bridge)에 유동성을 쌓아 두는 방식이나 감싼 토큰을 쓰는 방식이 아니다(chatgpt.md:487-580, grok.md:136).
- 공식 구현 예도 기존 체인에서 소각하고 Circle의 증명을 받아 목적 체인에서 발행하는 순서다 `[Circle 글 확인]`(블로그 crosschain-consolidation:91-93). 이 발행은 기존 USDC의 가치를 체인 사이에서 옮기는 절차다. 새로운 달러 입금을 받아 USDC 공급을 늘리는 Circle Mint의 발행과 구분해야 한다 `[내 판단]`.
- 2023년에 나왔다(chatgpt.md:487-580) `[답의 주장]`. 2025년 3월에 V2가 나왔고, 빠른 전송을 고르면 수수료가 생긴다 `[공시 확인]`(10-K:424-425). Claude가 같게 썼다(claude.md:43-44).
- 지금은 V2가 표준이고 V1은 단계적으로 끝나고 있다(chatgpt.md:4797-4887) `[답의 주장]`.
- 누적 처리액: 2025년 말 약 1,260억 달러(grok.md:136, chatgpt.md:1518-1520, claude.md:164), 2025년 11월까지 1,100억 달러 이상(claude.md:772-773) `[답의 주장]`. 두 숫자는 시점이 다르고 서로 어긋나지 않는다.
- 다른 자산의 발행자에게도 여는 방향이다(grok.md:136) `[답의 주장]`.
- 공시는 CCTP를 아직 초기 단계라고 하면서 앞으로의 성장을 이끌 차별점으로 본다 `[공시 확인]`(10-K:425-426).
- vault에 CCTP와 CPN이 다른 제품임을 공시와 백서로 확인한 문서가 있다: circle-cpn-cctp-reading.md.

#### 4.4.2. Gateway

- CCTP와 닮아 보이지만 푸는 문제가 다르다. 세 답은 CCTP를 전송, Gateway를 여러 체인의 USDC에 대한 통합 잔고 접근으로 설명했다(chatgpt.md:487-580, chatgpt.md:4797-4887).
- **통합 잔고가 생기는 과정.** 사용자가 기존 체인의 Gateway Wallet 스마트 계약에 USDC를 예치하면 통합 잔고로 접근할 수 있다. Circle이 운영하는 체인 밖의 시스템이 전송 요청과 증명을 관리하고, 목적 체인의 Gateway Minter 계약이 증명을 받아 실제 USDC를 발행한다 `[Circle 글 확인]`(블로그 gateway-guide:31-40, 74-82). 잔고를 화면에 합쳐 보여 주는 기능으로만 설명하거나 "옮기지 않는다"고 설명하면 이 발행과 지급 과정을 빠뜨린다 `[내 판단]`.
- 2025년 7월에 나왔다 `[공시 확인]`(10-K:428-429).
- 공식 가이드는 예치와 거래 확정(finality)이 끝난 뒤 Gateway 전송이 0.5초 미만에 실행될 수 있다고 설명한다 `[Circle 글 확인]`(블로그 gateway-guide:40). 세 답도 빠른 접근을 소개했지만(chatgpt.md:487-580, grok.md:153-154), 이 시간에 최초 예치와 거래 확정까지 포함된다고 읽으면 안 된다 `[내 판단]`.
- 공시가 적는 쓸모: 최종 사용자에게는 체인을 넘나드는 경험이고, 기업에게는 필요한 때에 필요한 체인에서 쓰는 유동성이어서 자본 효율이 좋아진다 `[공시 확인]`(10-K:429-431).
- Agent Stack의 소액 결제가 Gateway 위에 있다(grok.md:4552-4586). 4.10절(에이전트 서비스: Agent Stack)에서 다룬다.

#### 4.4.3. 발행 도구와 체인 이동 도구의 비교

Mint와 xReserve는 4.3절(발행과 유동성)에서 설명했다. 여기서는 두 발행 도구와 체인 이동 도구의 역할을 비교한다.

Claude가 네 가지 유동성 도구를 한 줄씩 가른 표를 바탕으로(claude.md:758-765), Mint의 대응 자산과 Gateway의 예치 및 발행 과정을 위에서 확인한 설명에 맞춰 보완했다.

| 도구 | 바꾸는 것 | 방식 |
|---|---|---|
| Mint | USD와 USDC, EUR와 EURC, BTC와 cirBTC | 기관이 Circle에 발행과 상환을 요청한다 |
| CCTP | 체인 A의 USDC를 체인 B의 USDC로 | 태우고 다시 발행한다 |
| Gateway | 계약에 예치한 USDC를 통합 잔고에서 목적 체인의 USDC로 | 예치 후 증명을 받아 목적 체인에서 발행한다 |
| xReserve | USDC를 담보로 다른 체인의 자체 스테이블코인으로 | USDC를 맡기고 1:1로 발행한다 |

표의 한 행은 도구 하나다.

```text
CCTP: 태우고 다시 발행한다

  기존 체인 A              Circle의 증명 서비스       기존 체인 B
  USDC를 태운다    ----->    증명을 낸다    ----->    같은 양을 새로 발행한다


Gateway: 계약에 예치한 USDC를 통합 잔고로 접근한다

  체인 A의 Gateway 계약에 USDC 예치 --+
  체인 B의 Gateway 계약에 USDC 예치 --+--> 통합 잔고
  체인 C의 Gateway 계약에 USDC 예치 --+       |
                                            v
                                사용자의 전송 요청과 Circle의 증명
                                            |
                                            v
                                목적 체인의 계약에서 USDC 발행
```

**도식: CCTP와 Gateway가 하는 일.** 위 비교표와 4.4.1절(CCTP), 4.4.2절(Gateway)의 설명을 옮겼다. ChatGPT가 두 도구를 각각 그렸고(chatgpt.md:492-500, chatgpt.md:530-535), Gateway의 예치 계약, 증명과 목적 체인 발행은 공식 글로 보완했다. xReserve의 발행 구조는 4.3.2절(xReserve)의 도식에 있다.

### 4.5. 블록체인: Arc

vault에는 Arc를 따로 다룬 문서가 있다: circle-arc-hub.md. 여기서는 세 답이 말한 것과 공시를 적는다.

- 금융, 실시간 자금 이동, 에이전트 경제를 겨냥한 EVM 호환 자체 체인(L1)이다(chatgpt.md:5037-5091, grok.md:135).
- 2025년 8월에 발표하고 10월에 테스트넷을 열었으며 2026년 9월 16일에 공개 메인넷을 열었다(claude.md:41, chatgpt.md:383-404) `[답의 주장]`. 공시에는 테스트넷이 2025년 10월, 비공개 메인넷이 2026년 5월, 공개 메인넷은 2026년 9월 예정으로 적혀 있다 `[공시 확인]`(10-Q2:1916-1920). 비공개 메인넷이 5월에 있었다는 것은 세 답에 없다.
- 2026년 6월 30일까지 테스트넷은 누적 5.02억 건의 거래와 280만 개의 지갑을 처리했고, 7월 20일 기준 협력사는 100곳이 넘는다 `[공시 확인]`(10-Q2:1917-1919).
- 공시가 드는 Arc의 설계와 운영 계획 다섯 `[공시 확인]`(10-K:390-401). 이 목록이 모두 메인넷에서 구현된 기능이라는 뜻은 아니다.
  1. 가스비를 USDC와 EURC 같은 스테이블코인으로 낸다.
  2. 검증자는 허가를 받은, 신원이 알려진 기관이다.
  3. 거래가 1초 안에 되돌릴 수 없게 확정된다.
  4. 거래를 공개하지 않도록 설정할 수 있고, 감사와 규제를 위한 접근은 남긴다.
  5. 처음 개발은 Circle이 이끌지만 운영과 거버넌스는 넓게 나눈다.
- **출시 당시의 상태.** 9월 16일 메인넷 발표문은 가스비를 USDC로 낸다고 적고, 선택적 프라이버시 기능은 네트워크 전체 공개를 위해 개발 중이라고 명시한다 `[Circle 글 확인]`(Arc 메인넷 발표:25-27, 36). 따라서 위 공시의 EURC 가스와 프라이버시 설계를 이미 사용할 수 있는 기능으로 단정하지 않는다 `[내 판단]`.
- **검증자.** 창립 검증자는 11곳이다: BlackRock, DTCC, Galaxy, ICE, Mastercard, MoneyGram, SBI, Standard Chartered, Sumitomo, Visa, Worldpay(claude.md:183) `[답의 주장]`. Claude는 자신이 1회차에 인용한 요약 글이 "창립 검증자 100곳 이상"이라고 잘못 썼고, 그것은 "빌더 100곳 이상"을 검증자로 옮긴 오류였다고 밝혔다. Grok의 1회차는 "100개 이상 앱, 기관 빌더"로 맞게 썼다(grok.md:135).
- **합의 방식.** 처음에는 권위증명(Proof-of-Authority)으로 돌고, 나중에 지분증명(Proof-of-Stake)이나 위임 지분증명으로 바꿀 수 있다 `[공시 확인]`(10-Q2:1932-1933). Claude는 2027년에 전환을 검토한다고 적었다(claude.md:131, claude.md:771) `[답의 주장]`.
- 메인넷 발표문은 Arc Studio와 Arc App Kits의 출시, Arc Portal의 역할을 설명한다 `[Circle 글 확인]`(Arc 메인넷 발표:45, 75-80). Payment, Privacy, Agent의 세 부문(Sector)은 향후 계획에 들어 있다 `[Circle 글 확인]`(Arc 메인넷 발표:84-86). 세 답도 이 항목들을 함께 소개했지만(chatgpt.md:1255-1303), 발표와 실제 가동을 같은 상태로 취급하지 않는다 `[내 판단]`.
- **Arc를 어디에 놓을 것인가.** ChatGPT의 그림은 Arc를 맨 아래에 놓고, Circle이 돈만 만드는 회사에서 돈이 도는 체인까지 가진 회사로 간다고 읽는다(chatgpt.md:383-404, chatgpt.md:5037-5091). Grok은 이 그림이 전략으로는 설득력이 있지만 2026년 9월에도 USDC가 주로 정산되는 곳은 이더리움, 솔라나, Base이므로 Arc가 이미 바닥인 것처럼 읽히면 지나치다고 지적했다(grok.md:1678). 나는 Grok의 단서가 맞다고 본다: 공시도 Arc를 "a broader, interoperable multichain ecosystem"의 일부로 적는다(10-Q2:1923-1924) `[내 판단]`.
- Claude의 판단: 메인넷이 나온 지 2주가 안 되었고 검증자가 허가형이며 실제 사용량이 검증되지 않았으므로 Arc는 아직 판단하기 이르다(claude.md:69).

```text
Arc (금융을 겨냥한 EVM 호환 자체 체인)
|
+-- 네트워크
|     +-- 출시 발표 기준 가스비는 USDC, 공시의 설계에는 EURC도 포함
|     +-- 검증자는 허가를 받은, 신원이 알려진 기관이다 (창립 검증자 11곳)
|     +-- 거래가 1초 안에 확정된다
|     +-- 선택적 프라이버시는 네트워크 전체 공개를 위해 개발 중
|     +-- 합의: 처음에는 권위증명, 나중에 지분증명으로 바꿀 수 있다
|
+-- 개발 도구   Arc Studio, Arc App Kits, Arc Portal
|
+-- 부문        Payment, Privacy, Agent (향후 계획)
|
+-- 토큰        ARC (처음 공급량 100억 개. 쓰임은 지분 예치, 거버넌스)

일정
2025년 8월 발표 -> 10월 테스트넷 -> 2026년 5월 비공개 메인넷 -> 9월 16일 공개 메인넷
```

**도식: Arc의 구성과 일정.** 위 항목을 옮겼다. ChatGPT가 같은 나무 모양을 그렸다(chatgpt.md:1283-1300). 창립 검증자 11곳과 2025년 8월의 발표는 위 항목의 `[답의 주장]`을 따른다. 세 부문의 계획, 개발 도구와 출시 당시의 가스 및 프라이버시 상태는 메인넷 발표문으로 대조했다(Arc 메인넷 발표:25-27, 45, 75-86). 2분기 실적 자료의 9월 16일은 공개 메인넷의 예정일이며(`web-circle-q2-2026-earnings-release.md:35`), 실제 출시 발표의 날짜도 9월 16일이다(Arc 메인넷 발표:9, 17). 나머지 일정은 위 항목이 든 공시를 따른다.

### 4.6. 네트워크 토큰: ARC

- 메인넷 발표문은 그 주에 ARC 100억 개의 최초 발행(genesis mint)을 완료했다고 적는다 `[Circle 글 확인]`(Arc 메인넷 발표:87). 세 답도 이 발행을 소개했다(chatgpt.md:5037-5091, claude.md:41). 그 전 공시는 처음 공급량을 100억 개로 예상하고, 프로토콜의 작동으로 늘어날 수 있다고 적었다 `[공시 확인]`(10-Q2:1938-1939).
- 100억 개를 발행한 것과 공개 출시는 다르다. 메인넷 발표문도 최초 발행이 공개 출시의 약속이 아니라고 명시한다 `[Circle 글 확인]`(Arc 메인넷 발표:87). 세 답이 같은 구분을 했다(chatgpt.md:5037-5091, claude.md:131). 공시도 전환과 토큰의 넓은 배포의 시기, 구조, 조건, 범위가 정해지지 않았다고 적는다 `[공시 확인]`(10-Q2:1939-1940).
- 가스비는 ARC가 아니라 USDC로 낸다(chatgpt.md:5037-5091).
- 공시가 적는 ARC의 쓰임은 지분 예치, 거버넌스, 그 밖의 플랫폼 기능이다 `[공시 확인]`(10-Q2:1934-1938).
- Claude는 조사 당시 "ARC는 어디서도 거래되지 않습니다"라고 쓰면서, ChatGPT가 1회차 표의 "거래되는 곳" 칸에 ARC를 넣은 것을 바로잡았다(claude.md:131) `[답의 주장]`. 최초 발행이 공개 출시의 약속이 아니라는 공식 발표와 현재의 거래 상태는 구분해야 하며, 현재 상태는 별도 거래 공지로 확인할 항목이다 `[내 판단]`.

#### 4.6.1. ARC 사전 판매

세 답이 1회차에 모두 빠뜨렸다. 1회차 교차에서 ChatGPT와 Grok이 각자 꺼냈고(chatgpt.md:1319-1367, grok.md:1652), Claude가 2회차 교차에서 돌려받을 권리와 매출 인식을 더했다(claude.md:423-427). ChatGPT는 2회차 교차 2에서 이것을 Claude가 새로 잡은 사실이라고 적었는데(chatgpt.md:3455-3478), 판매 자체는 ChatGPT 자신이 1회차 교차에 이미 썼다. 세 답은 누가 먼저 찾았는지를 여러 번 잘못 적었고, Grok이 그 점을 따로 짚었다(grok.md:4391-4423).

| 항목 | 내용 | 근거 |
|---|---|---|
| 판 토큰 | 8.075억 개(5월 7.4억 개, 6월 말 6,750만 개) | `[공시 확인]` 10-Q2:1942-1943, 분해는 `[답의 주장]` chatgpt.md:3455-3478 |
| 가격 | 개당 0.30달러 | `[공시 확인]` 10-Q2:1950 |
| 총액 | 약 2.422억 달러. 2분기에 받은 돈은 2.22억 달러 | `[공시 확인]` 10-Q2:1382-1385 |
| 네트워크 가치 | 완전 희석 기준 30억 달러 | `[공시 확인]` 10-Q2:1950 |
| 판매 방식 | 기관 투자자에게 사모로. 증권법 등록을 면제받는 방식 | `[공시 확인]` 10-Q2:1943-1945 |
| 매도 제한 | 지분증명 전환일부터 1년 이상. 전환 뒤 4년까지 추가 제한이 있을 수 있다 | `[공시 확인]` 10-Q2:1945-1948 |
| 돈을 돌려받을 권리 | 토큰이 인도되지 않거나, 2028년 5월 8일까지 지분증명으로 전환하지 못하거나, 매수자별 법규 조건이 충족되지 않을 때 | `[공시 확인]` 10-Q2:1951-1954 |
| 회계 처리 | 받은 돈은 이연수익(부채). 의무를 이행하면 기타 매출로 인식 | `[공시 확인]` 10-Q2:783-786 |
| 특수관계자 | 지분 5% 이상 주주인 IDG Capital의 계열이 8,330만 개, 2,500만 달러어치를 샀다 | `[공시 확인]` 10-Q2:1387-1390 |
| 주도한 투자자 | a16z | `[답의 주장]` grok.md:1652 |

표의 한 행은 항목 하나다.

```text
판 토큰
  5월          7.4억 개
  6월 말     0.675억 개
  ----------------------
  합         8.075억 개   x  0.30달러  =  2.4225억 달러

받은 돈  -->  이연수익(부채)  -->  의무를 이행하면 기타 매출
                  |
                  +-- 돌려줘야 하는 때
                        토큰이 인도되지 않을 때
                        2028년 5월 8일까지 지분증명으로 전환하지 못할 때
                        매수자별 법규 조건이 충족되지 않을 때

전체 100억 개  x  0.30달러  =  30억 달러 (완전 희석 기준 네트워크 가치)
판 것은 100억 개 가운데 8.075억 개 (한 칸은 2%)
  판 것    ####                                                8.1%
  나머지   ##############################################      91.9%
```

**도식: ARC 사전 판매의 셈과 회계.** 위 표와 검산을 옮겼다. 8.1%는 8.075억을 100억으로 나눈 내 셈이고 91.9%는 100에서 그것을 뺀 값이다. ChatGPT가 셈을 그렸다(chatgpt.md:3465-3474).

- 검산: 7.4억 + 0.675억 = 8.075억 개, 8.075억 x 0.30달러 = 2.4225억 달러. 100억 개 x 0.30달러 = 30억 달러.
- IDG Capital이 샀다는 것은 세 답에 없고 공시에서 더했다.
- **기타 매출 전망과의 관계.** 2026년 기타 매출 전망이 1.5억에서 1.7억 달러였다가 3.1억에서 3.3억 달러로 올랐고, 각주는 "Includes recognized ARC Token presale revenue"라고 적는다 `[공시 확인]`(`web-circle-q2-2026-earnings-release.md:209`, 같은 파일 219행). 올라간 폭은 1.6억 달러다. Claude는 2026년에 약 1.8억 달러가 제품 단계의 달성에 따라 매출로 인식될 예정이라고 적었다(claude.md:423-427, claude.md:732-737) `[답의 주장]`.
- Claude의 추론: 이 매출은 되풀이되지 않는 성격이 강하므로 이자가 아닌 사업이 자리를 잡았다는 증거로 읽으면 안 된다(claude.md:732-737). 나도 같은 뜻이다. 그리고 토큰 판매를 빼면 기타 매출 전망은 오른 것이 아니라 내렸다. 9.2절(기타 매출과 ARC)에서 공시로 확인한다 `[내 판단]`.
- ChatGPT의 읽기: Arc는 이제 Circle의 블록체인 계획이 아니라 자체의 네트워크 경제까지 가진 사업이다(chatgpt.md:5037-5091).
- 이 사전 판매가 CFO 교체와 이어지는 논점은 9장에서 다룬다.

### 4.7. 개발자 도구

질문의 네 가지만 보면 이 영역을 통째로 놓친다고 ChatGPT가 지적했다(chatgpt.md:5095-5185). Circle의 개발자 페이지는 Arc, Wallets, Contracts, CCTP, Paymaster, Gateway, App Kits를 하나의 개발 플랫폼으로 내놓는다 `[답의 주장]`. 공시도 App Kits, Circle Wallets, Circle Contracts를 핵심 개발자 서비스로 묶는다 `[공시 확인]`(10-Q2:1899-1902).

- **Circle Wallets.** 다른 회사가 자기 앱 안에 지갑을 넣게 해 주는 서비스다. Circle이 소비자용 지갑 앱을 내는 것이 아니다(chatgpt.md:584-654, chatgpt.md:5095-5185). 사용자가 통제하는 지갑과 개발자가 통제하는 지갑, 일반 계정(EOA)과 스마트 계약 계정, 모듈형 지갑을 제공한다 `[답의 주장]`. 공시는 익숙한 인증 방식을 써서 가입의 걸림돌을 줄인다고 적는다 `[공시 확인]`(10-K:410-413).
- **Circle Contracts.** 스마트 계약을 만들고 배포하고 관리하고 지켜보는 플랫폼이다(chatgpt.md:584-654). 공시가 드는 쓸모는 셋이다 `[공시 확인]`(10-K:414-418): 개발자가 새 언어를 배울 필요를 없애고, 흔한 작업에는 기존 템플릿을 다시 쓰고, 감시와 관리를 단순하게 한다. 토큰화 템플릿도 있다(chatgpt.md:584-654).
- ChatGPT가 둘의 관계를 가른 말: Wallets는 누가 거래에 서명하는가이고 Contracts는 무엇을 실행하는가다(chatgpt.md:5095-5185).
- **App Kits.** 공시는 App Kits를 Circle Wallets, Circle Contracts와 함께 핵심 개발자 서비스로 분류한다 `[공시 확인]`(10-Q2:1899-1902). 아래에서 세 답이 Arc App Kits라고 부르는 항목과의 관계는 확인이 필요하다. 공시의 이름과 세 답의 이름을 동일 제품으로 합치지 않고 구분해 적었다 `[내 판단]`.
- **Paymaster.** 사용자가 ETH 같은 체인의 고유 토큰 없이 USDC로 가스비를 내게 한다. USDC로 결제하려는데 가스비를 낼 ETH가 따로 필요한 불편을 없앤다(chatgpt.md:584-654, claude.md:45, grok.md:158-160). ERC-4337의 스마트 계약 계정과 EIP-7702의 일반 계정을 모두 지원한다(chatgpt.md:5095-5185) `[답의 주장]`.
- **Arc의 개발 도구.** 세 답은 2026년 9월 메인넷과 함께 나온 도구로 셋을 소개했다(chatgpt.md:5253-5281, claude.md:783-784). 공식 발표문은 Studio와 App Kits의 출시 및 Portal의 역할을 설명한다 `[Circle 글 확인]`(Arc 메인넷 발표:45, 75-80).
  - Arc Studio: 자연어 설명으로 온체인 앱과 계약을 만드는 AI 코딩 에이전트.
  - Arc App Kits: 결제, 교환, 입금, 수익 상품을 넣는 SDK.
  - Arc Portal: 에이전트 지갑에 자금을 넣고 지출 한도를 설정하며 작업을 위임하는 사용자용 창구(Arc 메인넷 발표:45).
- **풀리지 않은 것.** Claude는 1회차에 Arc Studio를 Claude Code, Codex, Cursor의 서브에이전트로도 쓸 수 있다고 썼다(claude.md:61). ChatGPT는 공식 자료에서 그 설명을 확인하지 못했다며 거짓이 아니라 확인 불가로 두자고 했다(chatgpt.md:1440-1456, chatgpt.md:1782-1838). Claude의 최종 답에는 이 문장이 없다. 나도 확인하지 못했다 `[미독 - 외부 링크]`.

```text
다른 회사의 앱
|
+-- Circle Wallets                      누가 거래에 서명하는가
+-- Circle Contracts                    무엇을 실행하는가
+-- Paymaster                           가스비를 USDC로 낸다
+-- App Kits                           공시가 핵심 개발자 서비스로 분류한 도구
+-- CCTP, Gateway                      체인 사이의 이동과 잔고 접근 (4.4절)
+-- Arc의 개발 도구                    세 답의 설명 [답의 주장]
      +-- Arc Studio
      +-- Arc App Kits                 App Kits와의 관계는 확인이 필요하다
      +-- Arc Portal

Paymaster가 없을 때   USDC로 결제하려는데 가스비를 낼 ETH가 따로 필요하다
Paymaster가 있을 때   USDC만 가지고 있다  -->  USDC로 가스비를 낸다  -->  거래
```

**도식: 개발자 도구.** 위 항목을 옮겼다. ChatGPT가 같은 구성과 Paymaster의 앞뒤를 그렸다(chatgpt.md:5106-5120, chatgpt.md:633-649).

### 4.8. 결제

vault에 CPN을 따로 다룬 문서가 있다: circle-cpn-reading.md, circle-cpn-cctp-reading.md.

이 절은 지도에 맞춰 CPN 결제망, 하위 결제 서비스, 결제 운영 서비스로 나눴다. 금융기관을 연결하는 망과 고객 대신 결제 운영을 맡는 서비스의 차이를 드러내기 위한 구분이다 `[내 판단]`.

#### 4.8.1. 결제망: CPN(Circle Payments Network)

- 개발 라이브러리가 아니라 금융기관 사이의 결제망이다(chatgpt.md:658-721, chatgpt.md:4961-5033). 공시는 "a neutral enterprise-grade network that enables banks, PSPs, and enterprises to move money using stablecoins starting with cross-border payments"라고 적는다 `[공시 확인]`(10-K:496-497).
- 2025년 4월에 발표하고(chatgpt.md:658-721) 5월에 가동했다 `[공시 확인]`(10-K:497-498).
- 맡는 일은 경로 찾기, 규제 준수, 정산의 조정, 유동성이다(chatgpt.md:4961-5033).
- **블록체인과의 관계.** CPN은 금융기관 사이의 통신과 정산을 조정하는 결제망이며, 자체 블록체인은 아니다. 기본 네트워크에서는 참여 기관들이 자금을 옮기고 CPN은 거래와 정보를 조정한다. 백서의 송금 예에서도 기관 지갑 사이의 USDC 전송은 블록체인에 기록되고, 받는 기관이 수취인에게 현지 법정화폐를 지급한다 `[Circle 글 확인]`(CPN 백서:178-190, 917-962). Circle이 더 많은 운영을 맡는 Managed Payments는 아래에서 구분한다.
- 겨냥하는 쓰임 `[공시 확인]`(10-K:499-501): 에이전트 결제, 소비자 결제, 기업 간 결제, 해외 송금, 급여, 자본시장 정산, 기업 내부의 자금 운용.
- 참여하려면 자격을 갖춰야 한다: 인가, 자금세탁 방지, 재무 위험 관리, 사이버 보안 `[공시 확인]`(10-K:504-506).
- 공시는 CPN을 여러 편이 모이는 망이자 장터 같은 응용 계층으로 보고, 참여 기관과 경로가 늘수록 네트워크 효과가 생길 것으로 기대한다 `[공시 확인]`(10-K:507-509).
- **규모.** 2026년 2분기 말 기준으로 최근 30일을 한 해로 환산한 거래액이 147억 달러이고 전 분기보다 76% 늘었다. 가입한 금융기관은 175곳이고 전 분기보다 29% 늘었다 `[공시 확인]`(`web-circle-q2-2026-earnings-release.md:88-90`). ChatGPT와 Claude가 같게 썼다(chatgpt.md:658-721, claude.md:55).
  - Grok은 1회차에 "약 100억 달러 전후"라고 썼고(grok.md:138), 교차 회차에서 시점을 혼동했다고 스스로 바로잡았다(grok.md:1638, grok.md:1667). Claude도 같은 지적을 했다(claude.md:148).
  - 내가 덧붙이는 주의: 147억 달러는 한 달의 거래액에 12를 곱한 값이고 한 해 동안 실제로 처리한 금액이 아니다. 한 달로는 약 12.3억 달러다(147억 / 12). 그리고 이것은 거래액이지 Circle의 매출이 아니다 `[내 판단]`.

#### 4.8.2. 하위 결제 서비스: Fiat Payments, Stablecoin Payments

- Grok은 CPN의 하위 제품을 Fiat Payments, Stablecoin Payments, Managed Payments로 나눈다(grok.md:138) `[답의 주장]`. 지도에는 이 이름을 함께 적되, Fiat Payments와 Stablecoin Payments 각각의 기능은 이 문서에서 확인하지 못했으므로 이름만으로 설명을 만들지 않았다.

#### 4.8.3. 결제 운영 서비스: CPN Managed Payments

- **CPN Managed Payments.** 2026년 4월 8일에 나왔다(claude.md:138) `[답의 주장]`. 고객은 법정화폐만 다루고, USDC의 발행, 지갑, 블록체인 전송, 규제 준수, 경로, 소각까지 Circle이 맡는다는 설명은 세 답에 있다(chatgpt.md:658-721, chatgpt.md:4961-5033, claude.md:774-775) `[답의 주장]`.
- 공식 출시 글은 고객이 익숙한 법정화폐 업무를 계속하고 Circle이 자금의 전환, 지갑, 유동성, 결제 조정, 규제 준수와 블록체인 인프라를 맡는다고 설명한다 `[Circle 글 확인]`(블로그 managed-payments:37-43). 따라서 고객이 스테이블코인 운영을 직접 구성해야 하는 CPN 이용 방식과, Circle에 운영을 맡기는 서비스는 구분해야 한다 `[내 판단]`. 이 글만으로 USDC의 개별 발행과 소각 절차까지 확인한 것은 아니다.
- ChatGPT의 읽기: Circle이 블록체인 개발 도구 회사에서, 일반 금융회사가 블록체인을 몰라도 쓸 수 있는 Stripe나 SWIFT 같은 층으로 올라가려는 움직임이다(chatgpt.md:4961-5033).
- vault의 문서 circle-cpn-cctp-reading.md는 CPN 백서의 "자금을 옮기지 않는다"는 설명을 Managed Payments가 좁힌다는 점을 다룬다. 세 답은 이 긴장을 말하지 않았다 `[내 판단]`.

```text
CPN

보내는 쪽: 은행, 결제 서비스 사업자, 기업
      |
      v
     CPN     경로 찾기, 규제 준수, 정산의 조정, 유동성
      |      (참여 기관이 기존 블록체인에서 스테이블코인으로 정산한다)
      v
받는 쪽: 은행, 결제 서비스 사업자, 기업


CPN Managed Payments

고객 (법정화폐만 다룬다)
      |
      v
   Circle
      +-- 법정화폐와 스테이블코인의 전환
      +-- 지갑
      +-- 블록체인 전송
      +-- 규제 준수
      +-- 경로와 유동성
      |
      v
   법정화폐


규모 (2026년 2분기 말)
  최근 30일을 한 해로 환산한 거래액 147억 달러 = 한 달 약 12.3억 달러 x 12
  가입한 금융기관 175곳
```

**도식: CPN과 Managed Payments.** 위 항목을 옮겼다. ChatGPT가 둘을 그렸고(chatgpt.md:676-690, chatgpt.md:5015-5030), 참여 기관의 블록체인 정산과 Managed Payments의 운영 범위는 백서와 공식 글로 보완했다.

### 4.9. 환전: StableFX

- 기관용 스테이블코인 환전 엔진이고 Arc 위에서 돈다 `[공시 확인]`(10-K:511). 2025년 11월에 발표했다(chatgpt.md:725-767) `[답의 주장]`.
- 기관이 견적 요청(RFQ) 방식으로 값을 받고, 체인 위에서 양쪽이 동시에 지급하는 방식(PvP)으로 정산한다(chatgpt.md:4921-4957, grok.md:137). 연중무휴로 돈다.
- 공시가 적는 정산의 방식 `[공시 확인]`(10-K:512-515): 스마트 계약에 돈을 맡겨 두는 방식이고, 양쪽이 다 정산하거나 아무도 하지 않는 조건, 즉시 정산과 나중 정산을 고를 수 있다. 상대방마다 따로 계약하고 신용 한도를 정해야 하는 부담을 줄이려는 것이다.
- **API와 Arc의 역할.** 기관의 시스템은 StableFX API로 견적을 요청하고 거래를 만들며, 서명으로 거래 조건과 자금 이동을 승인한다. 실제 지급은 Arc의 스마트 계약에서 지원되는 스테이블코인으로 정산한다 `[Circle 글 확인]`(블로그 stablefx-build:25-47, 126-200, 206-210, 473-577). 따라서 연결하는 기관의 환전 시스템 전체가 Arc 위의 앱이어야 한다는 뜻은 아니다. API로 연결하는 업무 시스템과 Arc에서 실행하는 정산 계약의 역할을 나눠 읽어야 한다 `[내 판단]`.
- **다른 체인의 자금과 연결하는 경우.** CCTP는 다른 체인의 USDC를 Arc로 가져오는 데 쓰고, StableFX는 Arc에서 환전과 정산을 처리하는 데 쓸 수 있다 `[내 판단]`(블로그 crosschain-consolidation:25-31, 91-93, 블로그 stablefx-build:25-47). 예를 들면 `다른 체인의 USDC -> CCTP -> Arc의 USDC -> StableFX -> Arc의 EURC`다. 이것은 두 제품의 역할을 조합한 설명이며, CCTP가 다른 환전 엔진을 자동으로 연결한다는 뜻은 아니다.
- **베타인가.** 10-K는 "StableFX is currently in beta"라고 적는다(10-K:511) `[공시 확인]`. 이것은 2025년 말 기준의 서술이다. Claude는 1회차에 베타라고 썼다가, 교차 회차에서 오래된 정보라고 스스로 바로잡았다: Arc 메인넷 발표 기준으로 USDC, EURC, KRW1, JPYC, BRLA, MXNB 등 22종이 연결되었거나 연결 중이다(claude.md:173, claude.md:776) `[답의 주장]`. ChatGPT는 AUDD, BRLA, JPYC, KRW1, MXNB를 들었다(chatgpt.md:725-767).
- 메인넷 발표문도 StableFX가 22종의 스테이블코인을 지원 중이거나 도입 중이라고 적는다 `[Circle 글 확인]`(Arc 메인넷 발표:32). 이 발표로 통화 목록은 대조했지만, 그것만으로 베타 종료를 확정하지는 않는다 `[내 판단]`.
- 22종이 "연결되었거나 연결 중"이라는 말은 실제로 거래되는 통화쌍의 수가 아니다. 베타가 끝났는지, 거래량이 얼마인지는 세 답 어디에도 없다 `[내 판단]`.
- Partner Stablecoins 제도가 StableFX에 통화를 공급한다(chatgpt.md:725-767, chatgpt.md:4921-4957).
- 원화 스테이블코인 KRW1이 목록에 있다는 점은 한국 독자에게 따로 볼 만하다 `[내 판단]`.

```text
기관의 업무 시스템  -->  StableFX API  -->  유동성 공급자의 견적
기관의 업무 시스템  <--  견적과 거래 조건  <--  StableFX API

기관 A  --->  Arc의 스마트 계약에 맡긴다  <---  기관 B
                     |
                     v
        양쪽이 동시에 지급한다(PvP)
        둘 다 정산하거나 아무도 하지 않는다

통화의 공급
지역 통화의 발행사  -->  Partner Stablecoins  -->  StableFX (Arc 위에서 돈다)
```

**도식: StableFX의 정산.** 위 항목을 옮겼다. ChatGPT는 통화쌍과 통화의 공급을 그렸다(chatgpt.md:4930-4940, chatgpt.md:4946-4953). API를 통한 요청과 Arc의 동시 지급은 위 공시와 공식 글에서 내가 그렸다.

### 4.10. 에이전트 서비스: Agent Stack

vault에 에이전트 결제를 다룬 문서가 있다: circle-agentic-payments-reading.md, circle-agentic-economy-reading.md.

- 2026년 5월에 나왔다 `[공시 확인]`(`web-circle-q2-2026-earnings-release.md:91-92`). Claude는 5월 11일로 적었다(claude.md:60) `[답의 주장]`.
- 공시의 정의 `[공시 확인]`(10-Q2:107-114): AI 에이전트가 독립된 경제 주체로 움직이게 하는 개발자 서비스와 금융 인프라의 묶음이다.
- **구성 요소의 수가 답과 공시에서 다르다** `[공시와 다름]`. 세 답은 다섯 가지를 들었다: Agent Wallets, Agent Marketplace, Circle CLI, Nanopayments, Circle Skills(chatgpt.md:771-807, claude.md:60, grok.md:161). 10-Q는 "Agent Stack consists of four components"라고 적고 넷만 든다(10-Q2:108, 10-Q2:1900). Circle Skills가 빠져 있다. 제품 페이지와 공시의 정의가 다른 것으로 보이고, 어느 쪽이 맞다고 할 일은 아니다 `[내 판단]`.

  | 구성 요소 | 공시의 설명 |
  |---|---|
  | Agent Wallets | 정해진 권한과 지출 한도 안에서 에이전트가 USDC를 보유하고 보내고 받는 지갑 |
  | Circle CLI | 개발자와 에이전트가 지갑, 결제, 정책 관리에 접근하는 명령줄 도구 |
  | Agent Marketplace | 에이전트가 다른 에이전트나 제3자의 서비스를 찾고 값을 치르는 곳 |
  | Nanopayments | Gateway 위에서 도는 소액 결제. 0.000001달러까지 가스비 없이 USDC를 보낸다 |

  표의 한 행은 구성 요소 하나다. 표 전체가 `[공시 확인]`이다(10-Q2:108-114).

- Nanopayments는 x402(에이전트 결제 프로토콜)의 흐름 위에서 돈다(claude.md:60, chatgpt.md:771-807) `[답의 주장]`.
- 유료 서비스가 900개가 넘고, x402 에이전트 결제액의 99.3%가 USDC로 정산된다 `[공시 확인]`(`web-circle-q2-2026-earnings-release.md:92-93`). Grok과 Claude는 이것을 "Circle은 주장합니다"라고 단서를 달아 썼다(grok.md:161, claude.md:781). 보도자료에 있는 회사의 말이므로 그 단서가 맞다. 그리고 99.3%는 비율이고 금액이 아니다. x402의 전체 결제액이 얼마인지는 보도자료의 이 대목에 없다 `[내 판단]`.
- 하반기에는 에이전트가 돈을 버는 기능을 넣을 계획이다 `[공시 확인]`(`web-circle-q2-2026-earnings-release.md:93-94`).
- ChatGPT의 읽기: Circle은 AI 에이전트도 앞으로 경제 주체가 된다고 보고 있고, 이것은 Arc의 Agent 부문과 이어진다(chatgpt.md:5218-5249).

```text
AI 에이전트
|
+-- Agent Wallets       정해진 권한과 지출 한도 안에서 USDC를 보유하고 보내고 받는다
+-- Circle CLI          지갑, 결제, 정책 관리에 접근하는 명령줄 도구
+-- Agent Marketplace   다른 에이전트나 제3자의 서비스를 찾고 값을 치른다
+-- Nanopayments        Gateway 위의 소액 결제. 0.000001달러까지 가스비 없이
+-- Circle Skills       세 답은 들었고, 10-Q의 네 구성 요소에는 없다
```

**도식: Agent Stack의 구성.** 위 표를 옮겼다. ChatGPT가 에이전트가 하는 일을 같은 모양으로 그렸다(chatgpt.md:5235-5242).

### 4.11. 기업용 계정: Digital Asset Accounts

- 핀테크 같은 회사가 자기 상표로 스테이블코인 계좌를 내게 하는 제품이다. 수탁, 법정화폐와 스테이블코인의 전환, 가입 절차, 규제 준수, 송수신, 체인 간 이동, 가스비 처리를 Circle이 한꺼번에 맡는다(grok.md:162, chatgpt.md:1209-1253, chatgpt.md:5189-5214, claude.md:163).
- **계정의 상표와 코인의 발행사는 구분해야 한다.** 위 설명에서 고객 기업의 상표가 붙는 것은 계정 서비스다. 고객이 USDC/EURC 같은 기존 스테이블코인을 보관하고 보내고 받는 계정과, 기업 이름의 별도 스테이블코인을 발행하는 일은 다르다 `[내 판단]`(chatgpt.md:1215-1225). 법정화폐 입금에 맞춰 USDC/EURC를 발행하는 기능을 결합하더라도 그 자산의 발행 주체는 Circle이다(4.2절(돈과 자산), 4.3.1절(Circle Mint)). 다른 체인의 자체 스테이블코인 발행을 지원하는 xReserve와도 구분한다(4.3.2절(xReserve)).
- 1회차에 이 제품을 쓴 것은 Grok뿐이다. ChatGPT와 Claude가 교차 회차에서 그것을 확인하고 받아들였다(chatgpt.md:1506-1516, claude.md:163).
- 허가제로 운영한다(claude.md:782) `[답의 주장]`.
- ChatGPT의 읽기: 예전에는 개발자가 지갑, Mint, 규제 준수를 따로 조립했고, 이제는 Circle이 묶어서 준다. Circle이 소비자 사업으로 돌아온 것이 아니라 다른 회사를 거쳐 소비자에게 닿는 인프라 회사가 되고 있다는 예다(chatgpt.md:1209-1253, chatgpt.md:5189-5214).
- 제품의 세부 기능 소개는 `[답의 주장]`이다. 계정의 상표와 별도 코인 발행을 나눈 설명은 그 소개를 읽은 `[내 판단]`이며, 이 보완에서 제품 문서나 약관을 추가로 검증한 것은 아니다. vault의 10-K와 2분기 10-Q에서 Digital Asset Accounts라는 이름은 찾지 못했다(검색: `rg -n -i 'Digital Asset Accounts' cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-fy2025-10k.md cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-10q.md`, 0건).

```text
예전: 개발자가 지갑, Mint, 규제 준수를 따로 조립했다

지금:
핀테크 같은 회사 (자기 상표로 계좌 서비스를 낸다)
      |
      v
Digital Asset Accounts
      +-- 기존 스테이블코인을 사용하는 계정
      +-- 수탁
      +-- 법정화폐와 스테이블코인의 전환
      +-- 가입 절차, 규제 준수
      +-- 송수신
      +-- 체인 간 이동
      +-- 가스비 처리
      |
      v
최종 사용자
```

**도식: Digital Asset Accounts.** 위 항목을 옮겼다. ChatGPT가 같은 모양으로 그렸다(chatgpt.md:5196-5207). 세부 기능은 `[답의 주장]`이고, 자기 상표가 붙는 계정과 기존 스테이블코인을 구분한 것은 위에서 설명한 `[내 판단]`이다.

### 4.12. 외부 자산 연결: Partner Stablecoins

Partner Stablecoins는 Circle이 직접 발행하는 자산이 아니라 외부 발행사의 스테이블코인을 연결하는 협력 제도이므로 자산 절에서 분리했다 `[내 판단]`.

- 지역 통화의 스테이블코인 발행사를 Circle의 망에 끌어들여 CPN, StableFX, USDC 유동성과 잇는 제도다(chatgpt.md:4891-4917). 그래서 Circle이 모든 통화를 직접 발행할 필요가 없다.
- Grok이 든 통화: 브라질 헤알, 원, 엔, 호주 달러, 캐나다 달러(grok.md:144-148) `[답의 주장]`.
- 공시는 StableFX가 협력 제도로 들어온 제3자 스테이블코인을 지원하도록 설계되었다고 적는다 `[공시 확인]`(10-K:515-517).
- xReserve와 다른 제도다: xReserve는 USDC를 담보로 새 코인을 발행하게 하는 것이고, Partner Stablecoins는 이미 있는 남의 코인을 잇는 것이다(chatgpt.md:4891-4917).

```text
외부 발행사와의 협력 제도
지역 통화의 발행사  -->  Partner Stablecoins  -->  CPN, StableFX, USDC 유동성

xReserve              USDC를 담보로 새 코인을 발행하게 한다
Partner Stablecoins   이미 있는 남의 코인을 잇는다
```

**도식: 외부 발행사와의 협력 제도.** 위 Partner Stablecoins 항목과 4.3.2절(xReserve)의 설명을 비교했다. ChatGPT가 Partner Stablecoins의 연결을 그렸다(chatgpt.md:4906-4914). 협력 제도의 세부 연결은 위 항목의 `[답의 주장]`을 따른다.

### 4.13. 규제와 수탁

규제 인가를 받은 법인과 수탁 업무는 소프트웨어 제품과 구별해 이 영역에 두었다 `[내 판단]`. 인가의 날짜, 법인명, 미국 밖의 인가와 세 답의 오류는 3.6절(규제 인가)에서 자세히 다룬다.

- **Circle National Trust.** 개업 때 회사와 계열사에 디지털 자산 수탁을 제공하는 연방 신탁은행이다 `[공시 확인]`(10-Q2:1826-1828). 현재의 수탁 업무와 앞으로의 USDC 준비금 운용을 구분해야 한다.
- **뉴욕주 신탁회사.** 공시의 법인명은 Circle Internet Trust Company LLC이고 뉴욕주의 한정 목적 신탁 인가를 받았다 `[공시 확인]`(10-Q2:1830-1831).

### 4.14. 유통 협력사: Coinbase, Binance

Coinbase와 Binance는 Circle의 개별 기술 제품이 아니라 USDC 보유와 유통을 넓히는 계약 상대방이므로, 사업을 지원하는 협력사로 구분했다 `[내 판단]`.

- **Coinbase.** 계약에 따라 USDC 보유와 유통에서 발생하는 준비금 수익의 일부를 받는다. 지급액을 정하는 식, 상표 사용권과 갱신 조건은 3.4절(Coinbase와의 계약)에서 다룬다.
- **Binance.** Circle의 지갑 인프라에 보유한 USDC의 양에 비례해 장려금을 받는다. 상업 계약과 Circle 주식 매입 조건은 3.5절(Binance와의 계약)에서 다룬다.

계약 내용은 위 두 절의 `[공시 확인]` 범위를 따른다. 유통 협력사가 있다는 사실을 Circle이 법정화폐 지급까지 직접 처리한다는 뜻으로 읽어서는 안 된다 `[내 판단]`.

### 4.15. 법정화폐 지급: Tazapay(인수 진행 중)

- **Tazapay.** 싱가포르의 국경 간 결제 회사다. 은행과 핀테크 협력사가 60곳 이상이고 지급할 수 있는 시장이 100곳 이상이다(chatgpt.md:1305-1311, chatgpt.md:1601-1654). 회사의 보도자료에 같은 숫자가 있다 `[공시 확인]`(Tazapay 발표:18).
  - 세 답에 없고 8-K에서 더하는 것 `[공시 확인]`.
    - 계약일은 2026년 9월 4일이고 발표일이 9월 8일이다. Circle의 자회사 Taurus Acquisition Inc.가 Tazapay Pte. Ltd.의 주식 가운데 Circle 쪽이 아직 가지지 않은 것을 모두 산다(8-K(2026-09-08):45). 8-K의 표현은 "not already held by Purchaser or its affiliates"인데, 계약서에 흔히 쓰는 문구여서 이것만으로 Circle이 이미 지분을 가지고 있었다고 할 수는 없다 `[내 판단]`. 8-K에 붙은 계약서에서 이 표현을 찾았지만 없었고(검색: `grep -c -i "already held" web-circle-2026-09-08-8k-share-purchase-agreement.md`, 0건), 계약서는 읽지 않았다 `[미독]`.
    - 대가는 4억 달러를 종결 전 20거래일의 평균 주가로 나눈 수의 Class A 주식이다. 빚, 거래 비용, 보유 현금에 따라 조정한다. 그 가운데 5%와 3%는 배상 청구에 대비해 묶어 둔다(8-K(2026-09-08):47).
    - 종결 뒤에 Tazapay 직원에게 2,500만 달러어치의 RSU를 준다(8-K(2026-09-08):67).
    - 종결 조건에는 규제 승인, 지정한 직원의 75% 이상이 남아 있을 것, 일부 고위 경영진이 계속 일할 것이 들어 있다(8-K(2026-09-08):69). 기한은 9개월이고 규제 승인이 남으면 15개월까지 늘어난다. 8-K는 해지 수수료에 대해 "The Share Purchase Agreement does not provide for any termination fee payable by the Sellers or Purchaser upon termination"이라고 적는다(8-K(2026-09-08):71-72).
    - 보도자료는 종결을 2027년으로 예상하고 싱가포르 통화청의 승인을 조건으로 든다. Tazapay의 연 환산 결제액은 250억 달러가 넘고 그 가운데 약 60%에 스테이블코인이 들어 있다고 한다. Tazapay는 2025년부터 CPN의 설계 협력사였다(Tazapay 발표:18).
  - 아직 끝난 인수가 아니므로 "인수했다"가 아니라 "인수 계약을 맺었고 2027년에 끝날 예정"이라고 써야 한다(chatgpt.md:1601-1654).
  - ChatGPT의 읽기: Binance는 USDC의 유통을 넓히는 쪽이고 Tazapay는 은행과 지급의 마지막 구간을 넓히는 쪽이다. Circle이 체인 위의 기술만이 아니라 법정화폐가 실제로 계좌에 닿는 구간까지 내려오고 있다(chatgpt.md:5315-5332, chatgpt.md:1601-1654).
  - ChatGPT는 교차 회차에서 Tazapay와 Binance 계약을 "세 답변 모두 놓친 중요한 최신 내용"으로 꼽았다(chatgpt.md:1601-1654). Claude와 Grok의 최종 답에는 Tazapay가 없다.

```text
Tazapay가 더하는 구간

USDC  -->  CPN  -->  스테이블코인으로 정산  -->  Tazapay  -->  법정화폐 지급의 마지막 구간
                                                    은행과 핀테크 협력사 60곳 이상
                                                    지급할 수 있는 시장 100곳 이상

Binance   USDC의 유통을 넓히는 쪽
Tazapay   은행과 지급의 마지막 구간을 넓히는 쪽
```

**도식: Tazapay가 더하는 지급 구간.** 위 Tazapay 항목을 옮겼다. ChatGPT가 같은 구간을 그렸다(chatgpt.md:1625-1646). 이 그림은 인수 뒤에 기대하는 연결을 나타내며, 인수 완료나 통합 기능의 가동을 확인한 것은 아니다.

### 4.16. 인수로 얻은 것

| 대상 | 때 | 얻은 것 | 값 | 근거 |
|---|---|---|---|---|
| Hashnote | 2025년 1월 | USYC를 발행하는 펀드의 운용사 | 약 1.001억 달러(현금 1,020만 달러와 주식 약 290만 주) | `[공시 확인]` 10-K:3013-3016 |
| Interop Labs, Rapidx Labs | 2026년 1월 | 체인 간 상호운용 기술 | 1,000만 달러 | `[공시 확인]` 10-Q2:1041-1043 |
| 블록체인 기술 특허 | 2026년 2분기 | 특허 | 2,000만 달러 | `[공시 확인]` 10-Q2:1039-1040 |
| Tazapay | 2026년 9월 4일 계약, 9월 8일 발표, 2027년 완료 예정 | 법정화폐 지급의 마지막 구간 | 4억 달러어치의 Class A 주식(조정 있음) | 계약과 값은 `[공시 확인]` 8-K(2026-09-08):45-47 |

표의 한 행은 인수 하나다. "답에 없음"은 세 답이 값을 적지 않았다는 뜻이다.

- **Hashnote.** Grok은 교차 회차에서 인수 값 1억 달러를 공식으로 확인하지 못했으니 단정하지 말자고 했다(grok.md:1675). 공시에 있는 숫자이므로 단정해도 된다 `[공시 확인]`. Claude가 적은 분해(현금 1,020만 달러와 주식 약 290만 주)도 공시와 같다(claude.md:135). 같은 인수와 관련해 2025년 1월에 Class A 3,857,332주(공정가치 1.202억 달러)를 발행했고, 여기에는 인수 뒤의 근무에 대한 보상으로 처리한 주식이 들어 있다 `[공시 확인]`(10-K:2854-2855).
- **Interop Labs.** Axelar를 만든 팀이다. 팀과 독점 지식재산만 인수했고 이 기술을 Arc와 CCTP에 넣을 예정이다. AXL 토큰과 Axelar 네트워크는 인수 대상에서 빠져서 논란이 있었다(claude.md:62, claude.md:786) `[답의 주장]`. Grok은 2025년 말에 합의했다고 적었다(grok.md:84-108).
  - 공시는 이것을 사업 인수가 아니라 자산 인수로 회계 처리했고, 값은 1,000만 달러이며 2년에 걸쳐 상각한다고 적는다 `[공시 확인]`(10-Q2:1041-1043). 값과 Rapidx Labs라는 이름은 세 답에 없다.
  - 1,000만 달러는 Hashnote의 10분의 1이다. 팀을 데려오는 데 든 보상은 이 값에 들어 있지 않을 수 있다: 2분기 보도자료에는 2026년 1월에 끝난 자산 인수와 관련한 일회성 특별 보상이 따로 나온다 `[공시 확인]`(`web-circle-q2-2026-earnings-release.md:603`). 그 금액은 확인하지 않았다 `[내 판단]`.
- **특허 2,000만 달러.** 세 답에 없고 공시에서 더했다. 무엇에 관한 특허인지는 공시의 이 대목에 없다.

Tazapay가 담당하는 지급 구간과 인수 계약의 상세 조건은 4.15절(법정화폐 지급: Tazapay)에서 설명했다.

```text
인수의 값 (막대 한 칸은 1,000만 달러)

2025년 1월        Hashnote                      약 1.001억 달러     ##########
2026년 1월        Interop Labs, Rapidx Labs     1,000만 달러        #
2026년 2분기      블록체인 기술 특허            2,000만 달러        ##
2026년 9월 계약   Tazapay (2027년 완료 예정)    4억 달러어치 주식   ########################################
```

**도식: 인수의 크기.** 위 표의 인수 대가를 옮겼다. Tazapay는 인수 계약 단계이고, 지급 구간은 4.15절(법정화폐 지급: Tazapay)의 도식에 있다.

### 4.17. 제품 절의 끝에: 무엇이 확인되었고 무엇이 아닌가

이 절은 전부 `[내 판단]`이다.

제품의 작동 구조를 더 조사할 공식 백서, 기술 가이드와 보안 감사 PDF 경로는
제품별 심화 기술 자료 조사에 모았다.
자료의 존재와 다루는 범위를 확인한 조사이며, 현재 구현의 안전성이나 사업 성과를 검증한 결론과 구분한다.

- 공시로 확인한 것은 제품이 있다는 것과 나온 때, 그리고 회사가 그 제품을 어떻게 설명하는가다. 제품이 얼마나 쓰이는가는 CPN의 연환산 거래액과 가입 기관 수, Arc 테스트넷의 누적 거래 수, Agent Stack의 서비스 수만 확인했다.
- 이번 보완에서는 공식 글로 USYC의 청약과 상환, cirBTC의 수탁과 반환, xReserve의 증명, Gateway의 예치와 목적 체인 발행, StableFX의 API와 Arc 정산을 대조했다. 작동 방식을 확인한 것이며, 실제 이용량이나 각 서비스의 수익성을 확인한 것은 아니다. Digital Asset Accounts의 자체 코인 발행 여부는 제품 문서를 새로 검증한 결과가 아니라 기존 소개에서 계정과 자산의 역할을 나눈 설명이다.
- 제품마다의 매출은 어디에도 없다. 공시는 기타 매출을 제품으로 나누지 않는다(3.7절(과거와 지금을 나란히 놓으면)).
- 세 답은 회차를 거듭하면서 제품 목록을 넓히는 데 힘을 썼고, 제품이 쓰이는 정도를 따지는 데는 힘을 덜 썼다. 그래서 4장은 "무엇이 있는가"에는 충분히 답하고 "무엇이 중요한가"에는 Claude의 한 줄(4.1절(답과 전체 지도)의 성장 옵션)과 Grok의 한 줄(매출을 나누는 단계가 아니다)로만 답한다.
- 두 번, 교차 검증에서 "틀렸다"고 판정된 내용이 공시로는 맞았다(xReserve의 구독료, Coinbase에 준 14억 달러). 한 번은 "거칠다"고 판정된 표현이 공시의 표현과 같았다(Centre 지분 50% 인수). 세 모델이 서로를 검증한 결과를 그대로 믿으면 맞는 내용이 빠진다.

**이 장의 내용을 되풀이한 구간.** 읽었고 위에 적은 것 밖의 새 내용은 없다: claude.md:142, grok.md:1654, claude.md:51, claude.md:777, claude.md:42, claude.md:56.

## 5. 왜 중간에 USDC로 강하게 방향을 틀었나

### 5.1. 답의 뼈대: 두 문장이 함께 참이다

Grok의 최종 답이 가장 짧게 적었다(grok.md:4590-4595).

1. USDC는 2019년에 갑자기 나온 생각이 아니다.
2. 2019년에 회사가 거의 죽을 뻔하지 않았다면 나머지 사업을 그만큼 자르지 못했을 가능성이 크다.

- 세 답이 최종 답에서 모두 이 결론에 섰다(chatgpt.md:4482-4520, claude.md:706-715, grok.md:4590-4595). 다만 처음부터 같았던 것은 아니다. 2회차에 ChatGPT는 전략 쪽에, Grok은 생존 쪽에 무게를 두었고 교차 회차를 거치며 가운데로 모였다. 그 과정은 5.5절(해석)에 적는다.
- "망해서 우연히 하나 남겼다"도 아니고 "여유 있게 비전만 보고 다 버렸다"도 아니다(grok.md:4611-4627). ChatGPT도 2회차에 같은 두 과장을 나란히 부정했다(chatgpt.md:2287-2325).
- Grok은 이유를 네 겹으로 나눴다: 창업자가 말하는 비전, 2019년의 현실, 거래소가 짐이 된 사정, 바깥의 신호(grok.md:1789-1791). 아래 절은 이 순서를 따르되 세 번째는 6장에서 다룬다.

```text
비전 쪽 (5.2절)                           생존 쪽 (5.4절)

2013  창업의 문제의식                     2019  위기: 감원, 사업의 종료와 매각
2016  CENTRE 발표                           |
2018  USDC 출시                             |
        |                                   |
        +-----------------+-----------------+
                          |
                          v
            나머지 사업을 자르고 USDC에 집중
```

**도식: 두 문장이 만나는 자리.** 위의 두 문장을 두 갈래로 그렸다. ChatGPT는 2019년의 위기에서 USDC에 회사를 거는 데까지를 한 줄기로 그렸고(chatgpt.md:4147-4162), 비전 쪽과 생존 쪽을 두 갈래로 나란히 놓은 것은 내가 한 것이다 `[내 판단]`.

### 5.2. 비전 쪽: 2013년, 2016년, 2018년

**2013-2014년에 무엇을 하려 했나.**

- 세 답의 서술: Allaire와 Neville의 출발점은 비트코인 거래소가 아니라 돈을 인터넷처럼 움직이게 하는 것이었고, 비트코인은 그때 가장 나은 공개 네트워크여서 고른 구현 수단이었다(chatgpt.md:1863-1983, grok.md:1793-1801, grok.md:4597-4601).
- 2014년 5월의 글 `[Circle 글 확인]`: 두 창업자는 회사를 "an Internet-based consumer finance company"라고 부르고, 목표를 "promoting and supporting Bitcoin as a payment utility and as a secure store of value"라고 적었다. 투기에는 관심이 없다고 했다: "We're not interested in or focused on the speculative value of Bitcoin"(블로그 about-2014:33, about-2014:41). 제품도 사고파는 것이 아니라 넣고 빼고 보내는 것으로 짰다: "The metaphors are deposits, withdrawals, sending and spending, not buying and selling and exchanging"(블로그 about-2014:57).
- 같은 글의 첫 문단은 이렇다: "we grew obsessed with evolving consumer finance, giving people greater control of their own money, and enabling Bitcoin as a mainstream solution globally"(블로그 about-2014:25).
- 내 읽기: 세 답이 옮긴 서사는 절반만 원문과 맞는다 `[내 판단]`. 거래소를 하려던 회사가 아니었다는 것은 원문이 분명히 받친다. 그러나 2014년의 Circle은 비트코인을 세계의 주류 해법으로 만들겠다고 썼다. "비트코인은 수단일 뿐이었다"는 말은 2016년 이후에 회사가 자신의 과거를 다시 설명한 말에 더 가깝다. 바로 아래 2016년 글의 "We have never been focused on..."이 그 다시 설명하기의 첫 사례다.
- Allaire는 2008년의 금융위기 뒤에 돈이 무엇인가에 몰두하게 되었고, 2025년 S-1의 창업자 편지에서 인터넷 기반의 신용시장과 결합한 완전준비(full-reserve) 디지털 화폐가 더 안전한 금융 시스템이 될 수 있다고 썼다(claude.md:282-285). S-1의 같은 편지에 "HTTP for Money"라는 표현이 있고, 비트코인 자체가 답이라고 확신한 것은 아니었다고 썼다고 한다(chatgpt.md:2835-2879, grok.md:4597-4601). 이 셋은 IPO 투자설명서의 창업자 편지에 있다 `[공시 확인]`: "eventually one where full-reserve digital currency can be intermediated with internet-based credit markets to create what could ultimately become a safer financial system"(424B4:102), "While I was not sold on the idea that Bitcoin itself would become the answer"(424B4:103), "We envisioned the development of an “HTTP for Money,” a protocol for dollars and other fiat digital currency tokens"(424B4:110, 굽은 따옴표는 [원문 그대로]).
- 2020년의 연설에서 Allaire는 같은 말을 했다 `[Circle 글 확인]`: 2013년에 자신들을 들뜨게 한 것은 공개 네트워크를 "traditional central bank money"에 잇는 것이었다(블로그 three-phases:39). 그리고 구상한 것은 "a fiat token standard, a protocol like an HTTP for money"였다(블로그 three-phases:57). "HTTP for money"라는 표현이 S-1보다 5년 앞선 회사의 글에 있다는 점은 확인된다.
- Neville의 2025년 회고: 2013년에 필요한 것이 디지털 달러라는 사실이 더 분명했어야 했을지도 모르고, 비트코인에서 시작했지만 비전은 달라지지 않았다(chatgpt.md:1863-1983) `[답의 주장]`. Claude는 이 인용을 확인하지 못했다고 적었다(claude.md:440).

**2016년 12월: CENTRE.** 세 답이 가장 오래 다툰 대목이고 원문이 vault에 있다.

- 원문 첫 문장의 뒷부분 `[Circle 글 확인]`: "the introduction of CENTRE (the project formerly known as Spark is now known as CENTRE), a new blockchain-based protocol to facilitate trusted, compliant money transfers between participating individuals and institutions over the Bitcoin network. As part of this launch, we are also eliminating the ability for customers to buy and sell bitcoin directly on Circle, and introducing a new preferred bitcoin exchange partnership with Coinbase"(블로그 centre-2016:23).
- 같은 글 `[Circle 글 확인]`: "We have never been focused on convincing consumers to replace their familiar native currencies with bitcoin ... This 'hybrid digital money' model has been in our sights for a long time"(블로그 centre-2016:41).
- CENTRE가 무엇이었나 `[Circle 글 확인]`: "a set of protocol additions that provides a way for digital wallets to exchange value using blockchains, including Bitcoin, as settlement layers"(블로그 centre-2016:43). 곧 코인을 발행하는 것이 아니라 지갑과 지갑을 잇는 규약이고, 비트코인을 정산의 층으로 썼다.
- 첫 적용은 한국의 Korbit과 필리핀의 Coins.ph였다 `[Circle 글 확인]`(블로그 centre-2016:49). 사용자는 법정화폐를 넣고 법정화폐를 받는다: "a pure fiat-to-fiat consumer experience"(블로그 centre-2016:53). Grok이 1회차에 쓴 "한국, 필리핀 확장 시도"(2.2절(2013-2017 비트코인 소비자 금융))가 이것이다.
- 같은 글은 회사가 더는 소비자용 비트코인 거래소가 아니라고 적는다 `[Circle 글 확인]`: "Circle is now more than ever not a consumer bitcoin exchange"(블로그 centre-2016:57).
- 그리고 같은 글의 끝에 장외거래의 씨앗이 보인다 `[Circle 글 확인]`: "Over the past three years, Circle's treasury operation has evolved into a major liquidity provider and trading counterparty in both the exchange-traded and OTC digital currency markets"(블로그 centre-2016:69). 2.2절(2013-2017 비트코인 소비자 금융)의 Circle Trade의 기원과 맞는다.

**Spark를 둘러싼 다툼과 그 결말.**

| 회차 | 누가 | 무엇을 말했나 | 근거 |
|---|---|---|---|
| 2회차 | Claude | 2015년에 이더리움의 스마트 계약을 보고, 이더리움 위에 법정화폐 담보 토큰 프로토콜을 만드는 내부 계획(코드명 Spark)을 시작했다 | claude.md:282-285 |
| 2회차 | Grok | Allaire가 대담에서 Spark를 말한다. 비트코인을 결제 인프라로 쓰는 대신 이더리움 위의 법정화폐 토큰으로 가겠다는 전환이다 | grok.md:1793-1801 |
| 2회차 교차 1 | ChatGPT | Spark는 있었다. 2016년 Wired가 다통화 이전을 하려는 오픈소스 계획이라고 보도했다. S-1에는 이름이 없다. 이더리움 직후의 내부 프로토콜이라는 설명은 근거가 더 필요하다 | chatgpt.md:3007-3041 |
| 2회차 교차 2 | ChatGPT | 2016년 12월의 글에 "the project formerly known as Spark is now known as CENTRE"가 있고, CENTRE는 "over the Bitcoin network"로 설명된다. Claude와 Grok의 설명은 시간 순서를 지나치게 줄인 것이다 | chatgpt.md:3792-3858 |
| 2회차 교차 2 | Claude | 자신의 설명은 Fortune의 2023년 기사를 옮긴 것이었고 1차 자료와 모순된다. 이더리움으로 옮겨 간 때와 경위는 확인되지 않았다 | claude.md:526-529 |
| 2회차 교차 2 | Grok | Spark와 다통화 이전 지향은 2016년 보도로 있다. "코드명 Spark가 USDC의 직계"는 한 칸 더 나간 서술이다 | grok.md:4387 |

표의 한 행은 발언 하나다.

- 원문으로 확정되는 것 `[Circle 글 확인]`: Spark는 CENTRE의 옛 이름이고, 2016년 12월의 CENTRE는 비트코인 네트워크 위의 송금 규약이다(블로그 centre-2016:23). ChatGPT가 인용한 두 구절은 원문과 글자가 같다.
- 이더리움으로 옮겨 간 때는 Allaire의 2020년 연설에 있다 `[Circle 글 확인]`: "by early 2017, we became very excited about second-generation blockchains like Ethereum"(블로그 three-phases:53), "So we really began work in 2017 on sort of a second attempt at solving this problem that was through the creation of CENTRE. And then eventually the introduction of USD Coin"(블로그 three-phases:55). Claude가 확인되지 않았다고 남긴 것(claude.md:526-529)이 이 글로 채워진다: 2017년 초다. ChatGPT는 2회차에 이 연설을 인용했는데(chatgpt.md:1863-1983), 뒤 회차의 Spark 다툼에서는 아무도 이 글로 돌아가지 않았다 `[내 판단]`.
- 그래서 순서는 이렇다: 2013년 비트코인으로 가치 이전, 2016년 12월 CENTRE(비트코인 위, 법정화폐로 표시한 돈을 옮긴다), 2017년 초부터 이더리움 위에서 두 번째 시도, 2018년 9월 USDC. 법정화폐의 가치를 인터넷 위로 올린다는 생각은 일찍 있었지만, 처음부터 이더리움 스테이블코인을 만들던 것은 아니다(chatgpt.md:3792-3858).
- 내가 덧붙이는 것: 2016년과 2018년에 "CENTRE"라는 같은 이름이 서로 다른 것을 가리킨다. 2016년의 CENTRE는 지갑을 잇는 규약이고, 2018년의 CENTRE Consortium은 Coinbase와 만든 합작 법인이다(2.4절(USDC의 등장, CENTRE, Coinbase)). 세 답은 이 둘을 한 줄로 이어 썼고, 이름이 이어진다는 것과 기술이 이어진다는 것은 다른 주장이다 `[내 판단]`.

```text
2013년        비트코인으로 가치 이전
   |
2016년 12월   CENTRE (옛 이름 Spark)
   |          비트코인 네트워크 위의 송금 규약. 법정화폐로 표시한 돈을 옮긴다
   |
2017년 초     이더리움 위에서 두 번째 시도를 시작
   |
2018년 9월    USDC


이름이 같은 둘
  2016년의 CENTRE              지갑과 지갑을 잇는 규약
  2018년의 CENTRE Consortium   Coinbase와 만든 합작 법인
```

**도식: 비트코인에서 USDC까지의 순서.** 위 "그래서 순서는 이렇다" 항목과 "내가 덧붙이는 것"을 그렸다. ChatGPT가 같은 순서를 그렸다(chatgpt.md:3835-3852).

**"원래부터 USDC가 목표였다"를 어디까지 믿을까.**

- 회사의 공식 서사는 방향을 튼 것이 아니라 돌아온 것이다. Grok은 Circle Pay가 비트코인을 숨기고 달러를 보내려 한 것과 USDC가 체인 위에서 달러를 보내는 것을 "같은 문장의 다른 구현"이라고 불렀다(grok.md:1793-1801). ChatGPT는 같은 문제를 풀려고 구현을 비트코인, 블록체인 위의 법정화폐, 스테이블코인으로 바꾼 것이라고 했다(chatgpt.md:1863-1983).
- 2019년 12월의 글도 같은 말을 한다 `[Circle 글 확인]`: "Our vision and mission remain unchanged since we founded Circle in the summer of 2013. We have, however, course-corrected many times"(블로그 focus-2020:65).
- 그러나 이것은 창업자의 서사다. 2018년에 회사는 실제로 거래소, 증권, 장외거래에 큰돈을 썼다(grok.md:3369). ChatGPT도 2018년에는 여러 방향에 함께 걸었고 그 가운데 상당수가 실패하거나 핵심이 아니라고 판정되었다고 적었다(chatgpt.md:2706-2765).
- Claude는 S-1의 기준으로 보면 거래소는 곁가지였고 USDC가 원래 목표였다고 썼는데(claude.md:282-285), 이것은 2025년에 쓴 문서로 2018년의 결정을 읽은 것이다 `[내 판단]`.
- 2019년 6월에도 회사는 거래소와 크라우드펀딩을 앞날의 축으로 꼽았다 `[Circle 글 확인]`: "Whether it's launching new wallet services, building upon the success of USDC, driving crypto adoption through Poloniex, or expanding ways entrepreneurs can raise capital on the internet through SeedInvest"(블로그 pay-sunset:51). 그리고 2019년 10월에 Poloniex를 내보내면서도 SeedInvest를 키우겠다고 썼다(블로그 polo-spinout:25). USDC 하나만 남긴다는 결정은 2019년 12월에야 글로 나온다. 세 답에 없는 관찰이고, "원래부터"라는 서사를 가장 직접 깎는 증거다 `[내 판단]`.

### 5.3. 앱보다 USDC였던 이유

**Circle Pay에서 배운 것.**

- 2019년 6월의 종료 발표 `[Circle 글 확인]`: "Circle Pay has clarified the path forward by highlighting the robust, global demand for people to exchange value as seamlessly as they exchange information. However, that demand largely relied on interfacing with the traditional financial system and untokenized fiat currencies"(블로그 pay-sunset:25). 이어서 "With the creation of fiat tokens and stablecoins such as USD Coin (USDC), people can seamlessly transfer fiat value over blockchains without the risk of cryptocurrency volatility ... As such, we believe that it is appropriate to retire Circle Pay at this time"(블로그 pay-sunset:27).
- ChatGPT가 옮긴 내용(chatgpt.md:1987-2128, chatgpt.md:4366-4411)은 원문과 맞는다. 다만 ChatGPT가 인용 블록으로 적은 문장은 원문의 글자가 아니라 뜻을 옮긴 것이다.
- 종료 일정 `[Circle 글 확인]`(블로그 pay-sunset:39-42): 7월 8일부터 입금과 송금 중단, 7월 31일부터 남은 돈을 연결된 계좌로 반환, 9월 30일에 지원 종료. 세 답에는 없다.
- 구조의 차이: Circle Pay에서는 Circle이 은행, 카드, 환전, 정산의 복잡함을 모두 떠안았다. USDC에서는 공개 블록체인 위에서 거래소, 지갑, DeFi, 핀테크가 각자 쓴다(chatgpt.md:1987-2128).

**고객을 누가 모으는가.**

- Circle Pay와 Circle Invest는 Circle이 고객을 한 명씩 모아야 한다. USDC는 Coinbase, Kraken, 지갑, DeFi, 핀테크가 고객을 모으고 Circle은 그 밑의 돈이 된다(chatgpt.md:1987-2128, chatgpt.md:4602-4646, grok.md:4603). ChatGPT의 말: "**다른 회사가 성장해도 USDC가 성장할 수 있습니다.**"원문 그대로
- 이것이 응용 사업과 플랫폼 사업의 차이다(chatgpt.md:4602-4646).

**2018년 말에 이미 보인 신호.**

- 2019년 1월의 글 `[Circle 글 확인]`: USDC는 시가총액 2.8억 달러로 법정화폐 스테이블코인 가운데 둘째이고 주마다 거의 10%씩 자란다. 체인 위의 전송이 석 달에 19억 달러를 넘었다(블로그 review-2018:88). 거래소 40곳 이상과 회사 80곳 이상이 지원한다(블로그 review-2018:90).
- ChatGPT가 쓴 숫자(chatgpt.md:1987-2128)가 원문과 모두 맞는다. Grok은 이것을 방향을 틀기 전에 이미 지렛대가 보였다는 논거로 받았다(grok.md:3343).
- 같은 글의 2018년 전체 숫자도 확인된다 `[Circle 글 확인]`: "we now serve more than 8 million customers from over 175 countries. Across all products and services, we facilitated more than 200 million transactions that totaled roughly \$75 billion in value"(블로그 review-2018:27). 2.3절(2018년)에서 `[답의 주장]`으로 둔 2018년 숫자는 이 글에 있다. 다만 Grok이 단서를 단 대로 회사가 낸 숫자다.
- 내가 덧붙이는 읽기: 2.8억 달러는 지금의 733억 달러와 견주면 0.4%다. 2018년 말에 회사가 본 것은 크기가 아니라 자라는 속도와 남이 퍼뜨려 준다는 구조였다 `[내 판단]`.

**이미 만든 인프라를 다시 쓴다.**

- 2019년 12월의 글 `[Circle 글 확인]`: "Circle's platform services quietly supported our Pay, Invest, Trade and USDC products and businesses by providing robust underlying custody, risk and identity management, compliance management, data science, card and banking gateways, and blockchain gateways. These platform services are analogous to the massive foundation of an iceberg not visible beneath the water while our products were the small visible crest above"(블로그 focus-2020:33). 그리고 "In 2020, we're excited to surface this core of what we've built and expose these powerful services through new APIs"(블로그 focus-2020:35).
- Claude는 이 빙산의 비유에서 결론을 끌어냈다: "**피벗의 본질은 "앱을 버린 것"이 아니라 "앱 밑의 인프라를 상품화한 것"**"원문 그대로. ChatGPT는 소프트웨어 회사의 눈으로 보아도 자연스러운, 응용에서 플랫폼으로의 전환이라고 했다(chatgpt.md:1987-2128).
- Circle Pay의 기술은 버려지지 않았다 `[Circle 글 확인]`: "the underlying platform technologies, battled-tested with millions of users and billions of dollars in transactions, will be part of our new stablecoin platform services"(블로그 focus-2020:49).
- 이 논점은 지금의 제품과 곧바로 이어진다: 수탁, 규제 준수, 은행 연결을 묶어서 남에게 주는 것이 2026년의 Digital Asset Accounts와 CPN Managed Payments다(4.8절(CPN), 4.11절(Digital Asset Accounts)). 2019년에 약속한 것을 7년 뒤에 제품으로 낸 셈이다 `[내 판단]`.

```text
Circle Pay                              USDC

Circle이 고객을 한 명씩 모은다          Coinbase, Kraken, 지갑, DeFi, 핀테크가 고객을 모은다
      |                                       |
      v                                       v
Circle이 은행, 카드, 환전, 정산의       공개 블록체인 위에서 각자 쓴다
복잡함을 모두 떠안는다                        |
                                              v
                                        Circle은 그 밑의 돈이 된다


빙산의 비유 (2019년 12월의 글)

  물 위    Pay, Invest, Trade, USDC (제품)
  ------------------------------------------------------------------
  물 밑    수탁, 위험과 신원 관리, 규제 준수 관리, 데이터 과학,
           카드와 은행 연결, 블록체인 연결 (플랫폼 서비스)


2018년 말에 보인 신호
  USDC 시가총액 2.8억 달러, 주마다 거의 10%씩 자람
  지원하는 거래소 40곳 이상, 회사 80곳 이상
```

**도식: 앱과 USDC의 차이.** 위 항목을 옮겼다. ChatGPT가 고객을 누가 모으는지와 인프라를 다시 쓰는 것을 그렸다(chatgpt.md:2003-2016, chatgpt.md:4624-4637, chatgpt.md:2099-2121).

### 5.4. 생존 쪽: 2019년에 무슨 일이 있었나

**2019년의 순서.** Claude의 2회차가 가장 촘촘하게 적었다(claude.md:266-277). 교차 회차에서 Grok은 5월의 순서를 Claude가 가장 잘 잡았다고 평가했다(grok.md:3358).

| 때 | 일 | 근거 |
|---|---|---|
| 2019년 3월 | 자금 조달 목표를 2.5억 달러에서 1.5억 달러로 낮췄다는 보도 | `[답의 주장]` claude.md:292, chatgpt.md:2983-3003. 익명 소식통 보도여서 두 답 모두 확신도가 낮다고 적었다 |
| 2019년 5월 | 직원의 10%, 약 30명 감원. 이유로 미국의 규제 환경을 들었다 | `[답의 주장]` claude.md:279 |
| 2019년 5월 | Poloniex가 미국에서 일부 자산의 거래를 막았다. 글의 표현은 "some assets"이고, 9개라는 수는 그 문장에 걸린 링크의 주소(`...trading-of-9-assets-to-us-customers...`)에만 있다. 링크된 글은 열지 않았다 `[미독 - 외부 링크]` | `[Circle 글 확인]` 블로그 policy-2019:23-25 |
| 2019년 6월 13일 | Circle Pay 종료 발표 | `[Circle 글 확인]` 블로그 pay-sunset:23 |
| 2019년 10월 18일 | Poloniex 분사 발표 | `[Circle 글 확인]` 블로그 polo-spinout:23 |
| 2019년 11월 1일 | Poloniex의 미국 고객 거래 종료 | `[Circle 글 확인]` 블로그 polo-us-end:23 |
| 2019년 12월 18일 | Circle Trade를 Kraken에 매각했다고 발표. 공동 CEO Neville, CFO Ishaq, CLO Coldebella가 자리에서 물러난다 | `[Circle 글 확인]` 블로그 focus-2020:45, focus-2020:55-57 |
| 2020년 3월 30일 | Circle Invest를 Voyager에 매각. Claude는 2월로 적었다(claude.md:266-277) | `[공시 확인]` S-4:6576 |

표의 한 행은 일 하나다.

```text
2019년
  |  3월         자금 조달 목표를 낮췄다는 보도
  |  5월         직원 10% 감원. Poloniex가 미국에서 일부 자산의 거래를 막음
  |  6월 13일    Circle Pay 종료 발표
  |  10월 18일   Poloniex 분사 발표
  |  11월 1일    Poloniex의 미국 고객 거래 종료
  |  12월 18일   Circle Trade 매각 발표. 공동 CEO, CFO, CLO가 물러남
2020년
  |  3월 30일    Circle Invest 매각
```

**도식: 2019년의 순서.** 위 표를 세로로 놓았다. Claude가 같은 모양으로 적었다(claude.md:269-274).

**규제.**

- 2019년 5월의 글 `[Circle 글 확인]`: "We are deeply frustrated that we needed to take these steps, but they are the direct result of the signaling from the recent guidance, in which US regulators are taking an extremely broad view of what crypto assets might be deemed securities"(블로그 policy-2019:25). Claude와 ChatGPT가 옮긴 내용과 맞는다(claude.md:279, chatgpt.md:2983-3003).
- 2019년 12월의 글은 거래소를 떠나는 이유에 규제를 넣었다 `[Circle 글 확인]`: "in order to gain focus on our stablecoin platform mission as well as practical US regulatory reality, we determined that we should exit the exchange business"(블로그 focus-2020:47).
- 2019년 10월의 글 `[Circle 글 확인]`: "we have also faced challenges as a US company growing a competitive international exchange"(블로그 polo-spinout:29).

**돈.** 이 대목의 숫자는 2021년의 S-4에 있는 2019년 재무제표와 대조했다. 단위는 S-4가 천 달러이고 아래 표는 만 달러로 옮겼다.

| 2019년의 항목 | 세 답의 값 | 누가 썼나 | S-4의 값(천 달러) | 근거 |
|---|---|---|---|---|
| 계속영업 영업손실 | 8,321만 달러 | chatgpt.md:2287-2325, claude.md:435 | (83,209) | `[공시 확인]` S-4:6158 |
| 계속영업 순손실 | 2,628만 달러 | chatgpt.md:2287-2325, claude.md:435 | (26,280) | `[공시 확인]` S-4:6162 |
| 전체 순손실 | 1.786억 달러 | chatgpt.md:2287-2325, claude.md:435 | (178,565) | `[공시 확인]` S-4:6167 |
| Poloniex 처분손실 | 약 1.568억 달러 | chatgpt.md:4482-4520 | 156,824 | `[공시 확인]` S-4:6165, S-4:6611 |
| 영업 현금 유출 | 약 5,970만 달러 | chatgpt.md:2287-2325 | (59,701) | `[공시 확인]` S-4:4067 |
| 영업비용 | 8,772만 달러 | chatgpt.md:3862-3902 | 87,724 | `[공시 확인]` S-4:6157 |
| USDC 준비금 이자 수익 | 623만 달러 | chatgpt.md:2132-2154 | 6,232 | `[공시 확인]` S-4:6142 |
| USDC 유통 협력사에 준 돈 | 491만 달러 | chatgpt.md:2132-2154 | 4,908 | `[공시 확인]` S-4:6147 |
| Poloniex 매출 | 1,130만 달러 | chatgpt.md:2132-2154 | 11,333 | `[공시 확인]` S-4:6769 |
| Circle Trade 매출 | 730만 달러 | chatgpt.md:2132-2154 | 7,276 | `[공시 확인]` S-4:6770 |

표의 한 행은 항목 하나다. 세 답의 숫자 열 개가 모두 S-4와 맞는다. Claude가 확인하지 못했다고 남긴 다섯(claude.md:440)도 S-4에 있다.

```text
2019년 계속영업의 손익 (단위: 만 달러)

   USDC 준비금 이자 수익                                      623.2
+  SeedInvest 매출                                            319.1
-  USDC 유통 협력사에 준 돈                                   490.8
-  영업비용                                                   8,772.4
     그 가운데 인건비 4,346, SeedInvest 영업권 손상 1,395
------------------------------------------------------------------------
=  영업손실                                                   -8,320.9
+  기타수익                                                   6,466
     그 대부분은 워런트의 값이 내려 생긴 일회성 이익 5,950
------------------------------------------------------------------------
=  세전 손실                                                  -1,855

   계속영업 순손실                                            -2,628
   중단사업까지 더한 전체 순손실                              -17,856.5
```

**도식: 2019년의 손익을 위에서 아래로.** 위 표와 검산, S-4에서 더한 항목의 숫자를 한 줄로 이었다. 단위를 만 달러로 맞췄다(S-4의 83,209천 달러는 8,320.9만 달러이고 178,565천 달러는 17,856.5만 달러다). 세 답은 이것을 그리지 않았다.

- 검산 `[내 판단]`: 앞서 나는 이자 623.2만 - 유통비 490.8만 - 영업비용 8,772.4만 = -8,640만 달러가 영업손실 -8,320.9만 달러와 319만 달러 차이 난다고 적고 닫지 못했다. S-4로 닫힌다. 2019년에는 SeedInvest 매출 319.1만 달러가 있었다(S-4:6143). 6,232 + 3,191 = 9,423(매출 합계, S-4:6144), 9,423 - 4,908 - 87,724 = -83,209.
- 세 답에 없고 S-4에서 더하는 것 `[공시 확인]`.
  - 영업비용 8,772만 달러 가운데 인건비가 4,346만 달러이고, SeedInvest 영업권 손상이 1,395만 달러다(S-4:6150, S-4:6156). 손상의 이유는 Poloniex를 판 뒤에 두 사업 사이의 상승효과가 없어진 것이다(S-4:3600).
  - 영업손실이 8,321만 달러인데 세전 손실이 1,855만 달러인 것은 기타수익 6,466만 달러 때문이고(S-4:6159-6160), 그 대부분은 Poloniex 인수 때 발행한 워런트의 공정가치가 내려서 생긴 일회성 이익 5,950만 달러다(S-4:3908). 곧 2019년의 계속영업 순손실 2,628만 달러는 현금이 아닌 이익 덕분에 작아 보이는 숫자다 `[내 판단]`.
  - 2019년의 투자활동 현금은 3,720만 달러 유입이고, Poloniex를 판 돈 3,320만 달러와 디지털 자산을 처분한 돈 1,540만 달러가 주된 것이다(S-4:4079).
  - 2020년에 인건비가 56.4% 줄었고, 이유는 Poloniex와 Circle Trade를 판 뒤 평균 인원이 58.6% 줄어서다(S-4:3901). 2021년 6월 30일의 직원은 233명이다(S-4:3265).
- Claude의 지적: Grok은 ChatGPT가 낸 미확인 숫자를 "숫자로 닫습니다"라며 확정된 것처럼 받았다(grok.md:3344). 다른 AI의 숫자를 검증 없이 받아들인 오류다(claude.md:564). 이 지적은 옳고, 이 문서가 세 답의 일치를 확인으로 치지 않는 이유와 같다.

**사람.**

- 인력: Poloniex 시절 400명에서 2020년 초 60명으로(Claude, Boston Globe 보도 기준, claude.md:286-287), 또는 2019년 약 450명에서 2020년 1월 59명으로(ChatGPT, Allaire의 Grit 인터뷰 기준, chatgpt.md:2775-2831) `[답의 주장]`. 크게 줄었다는 것은 같고 두 시점의 정확한 수는 자료마다 다르다(grok.md:4385). S-4에는 두 시점의 인원수가 없고 평균 인원이 한 해 사이에 58.6% 줄었다는 것만 있다 `[공시 확인]`(S-4:3901).
- 원문으로 확인되는 것은 하나다 `[Circle 글 확인]`: "As part of the successful Poloniex spin out, more than 80 Circle employees transitioned to the new standalone company"(블로그 focus-2020:53).
- 그러므로 줄어든 사람 가운데 80명 남짓은 해고가 아니라 분사한 회사로 옮겨 간 것이다(claude.md:286-287). 5월의 감원 30명을 더하면 110명쯤이 설명되고, 나머지 230명에서 280명이 어떻게 떠났는지는 세 답에 없다 `[내 판단]`.

**창업자의 회고.**

- 2026년 1월 26일의 Kleiner Perkins Grit 팟캐스트. 공식 소개가 "Circle faced the threat of bankruptcy in 2019"라고 적고, Allaire는 2019년을 "darkest hour"라고 불렀다(chatgpt.md:2775-2831, chatgpt.md:3862-3902, claude.md:541, grok.md:4379) `[답의 주장]` `[미독 - 외부 링크]`.
- Allaire가 말한 내용으로 세 답이 옮긴 것(chatgpt.md:2775-2831, grok.md:1803-1816, grok.md:4605-4609):
  - 돈을 벌던 제품이 현금을 쓰기 시작했다.
  - 2019년 여름부터 9월까지 새 투자자를 구하기 어려웠다.
  - 거래소와 중개 사업을 팔고 다른 제품을 끝냈다.
  - 자산을 판 돈으로 새 지분 투자 없이 버텼다.
  - 그 와중에 USDC에서 처음으로 시장의 반응이 보였다.
  - 그래서 회사 전체를 걸었다. 당시 USDC의 수익은 거의 없었다.
- Allaire는 스타트업을 등반에 견주며 죽을 뻔한 순간이 오면 방향을 틀어야 한다고 말했고(claude.md:286-287), "모자에서 토끼를 수없이 꺼냈다"고도 했다(claude.md:450) `[답의 주장]`.
- Fortune은 USDC가 빠르게 자라지 않았다면 Poloniex 인수가 회사를 가라앉혔을 것이라고 평가했다(claude.md:286-287) `[답의 주장]`.
- **이 회고를 읽을 때의 단서 셋.**
  1. 성공한 뒤의 회고다. 세부 서사에는 결과를 아는 사람의 치우침이 있을 수 있다(chatgpt.md:3862-3902, grok.md:3368).
  2. 소개문의 말은 "위협"이고 법원에 파산을 신청한 것이 아니다(grok.md:4379).
  3. Grok은 2회차에 Allaire의 말을 직접 인용처럼 늘어놓았는데("현금이 바닥났다", "2019년 가을 다시 파산 직전") 출처가 요약 수준이었다(claude.md:456). Claude는 인터뷰의 세부 수치를 원문으로 확인하지 못했다고 끝까지 남겼다(claude.md:541, claude.md:582-583).
- 공식 발표와 회고는 어조가 다르다. Grok의 정리: "**대외 메시지는 전략 집중, 회고 인터뷰는 생존**입니다. 둘 다 사실일 수 있습니다."원문 그대로 Claude의 최종 답은 둘을 표로 나란히 놓았다(claude.md:706-715).
- 내가 덧붙이는 읽기: 2019년 12월의 글에도 어려움의 흔적이 있다. 같은 글 안에서 공동 CEO, CFO, CLO 세 사람이 한꺼번에 떠난다고 알리고(블로그 focus-2020:55-57), Poloniex에 대해서는 "published reports continue to misrepresent both the original acquisition and the context of the spin out"이라고 언론 보도에 맞선다(블로그 focus-2020:47). 전략에 집중한다는 글치고는 방어하는 문장이 많다. 다만 글 어디에도 현금이나 파산에 관한 말은 없다 `[내 판단]`.

### 5.5. 해석: 무엇 때문이 아니었고, 무엇을 얻었나

**이자를 벌려고 한 선택은 아니었다.** 세 답이 2회차에 각자 같은 결론을 냈다. 서로의 답을 보기 전이므로 독립된 일치다 `[내 판단]`.

- ChatGPT: 2019년의 USDC 이자 수익은 623만 달러였고 협력사에 준 돈이 491만 달러였다. 지금 있는 매출을 버리고 아직 작은 USDC에 건 것에 가깝다(chatgpt.md:2132-2154).
- Claude: 2020년 초 USDC의 규모는 약 4억 달러였고 2020년 3월 뒤로 미국의 금리는 거의 0이었다. 이자 엔진은 2022년의 금리 인상 뒤에야 커졌다(claude.md:294-297). Claude는 금리에 관한 부분이 배경지식이라고 밝혔다.
- Grok: 2020년 뒤에 USDC가 수억 달러에서 수백억 달러로 커진 것은 방향을 튼 원인이 아니라 결과다. 그때는 확신이 아니라 생존과 가설이었다(grok.md:1836-1850, grok.md:82, grok.md:4611-4627).
- 2021년의 SPAC 자료에서도 USDC는 둘째 사업이었다: 2021년 예상 매출 1.15억 달러 가운데 USDC가 4,000만 달러, 거래와 재무 서비스(TTS)가 6,500만 달러였다(claude.md:452) `[답의 주장]`. 방향을 튼 지 2년이 지나서도 USDC의 매출이 가장 크지 않았다는 뜻이다.
- 당시 CFO였던 Naeem Ishaq는 2025년에 회사가 돈을 버는 제품을 모두 처분하면서 USDC에 집중했다고 돌아보았다(chatgpt.md:2132-2154) `[답의 주장]`. Claude는 이 인용을 확인하지 못했다(claude.md:440).

**중립성.** Claude가 2회차에 낸 논점이고 Grok이 세 답 가운데 가장 분명하다고 평가했다(claude.md:294-297, grok.md:3360).

- 스테이블코인을 발행하는 회사가 거래소와 장외거래 데스크도 하면, USDC를 퍼뜨려 주는 거래소들과 경쟁하게 된다. 그 사업을 정리했기 때문에 누구에게나 USDC를 공급하는 중립 인프라가 될 수 있었고, 지금의 Coinbase와 Binance 유통 구조가 그 위에 서 있다.
- Claude는 이것을 확신도 중간의 추론으로 표시했다. 회사가 중립성을 이유로 들었다는 자료는 세 답에 없고, 내가 읽은 2019년의 글 넷에도 없다 `[내 판단]`. 결과로 얻은 것이지 그때 밝힌 동기는 아니다.
- 그래도 이 논점은 3.4절(Coinbase와의 계약), 3.5절(Binance와의 계약)과 맞물린다: 2025년에 Coinbase와 Binance에 준 유통비용이 매출의 큰 몫이고, 두 회사는 Circle의 주주이기도 하다. Circle이 자기 거래소를 가지고 있었다면 이 구조가 서기 어려웠을 것이다 `[내 판단]`.

**바깥의 신호.** Grok만 넣었다(grok.md:1830-1832) `[답의 주장]`.

- Circle의 대변인은 2019년 말에 Facebook의 리브라, 중국의 디지털 화폐, 테더와 USDC의 성장 때문에 2020년이 스테이블코인의 해가 될 것이라고 말했다.
- 2019년 12월의 글에도 같은 읽기가 있다 `[Circle 글 확인]`: "The global interest in stablecoins and digital currency backed by central bank money, the introduction of third generation public blockchains, and the accelerated global policy interest in crypto all provide an exciting backdrop"(블로그 focus-2020:67).

**전략과 생존의 비율.**

- ChatGPT는 2회차에 전략적 집중이 60에서 70%, 구조조정의 압력이 30에서 40%라고 썼고, 이 비율이 자신의 해석이라고 밝혔다(chatgpt.md:2287-2325).
- Claude와 Grok은 근거 없는 수치라고 지적했다(claude.md:444, grok.md:3353).
- ChatGPT는 2회차 교차 1에서 "**이 비율은 철회하는 게 맞습니다.**"[원문 그대로]라고 쓰고, 생존의 압력이 처음 생각보다 훨씬 컸다고 고쳤다(chatgpt.md:2775-2831). Claude는 이것을 정직한 수정이라고 평가했다(claude.md:541).
- 세 답의 마지막 입장: 둘 다 실제로 있었고 비율은 자료로 정할 수 없다(claude.md:480, claude.md:574, claude.md:706-715, grok.md:4431-4432).
- 나도 비율을 정하지 않는다. 다만 순서는 말할 수 있다 `[내 판단]`: 생각이 먼저 있었고(2016년), 제품이 나왔고(2018년 9월), 신호가 보였고(2018년 말), 위기가 왔고(2019년), 그 뒤에 나머지를 잘랐다(2019년 6월부터 2020년 3월). 위기가 없었다면 USDC는 여섯 사업 가운데 하나로 남았을 수 있다. 위기가 방향을 만든 것이 아니라 방향 하나만 남긴 것이다.

```text
생각이 먼저 있었다          2016년
        |
        v
제품이 나왔다               2018년 9월
        |
        v
신호가 보였다               2018년 말
        |
        v
위기가 왔다                 2019년
        |
        v
나머지를 잘랐다             2019년 6월부터 2020년 3월
```

**도식: 비율이 아니라 순서.** 위 "나도 비율을 정하지 않는다" 항목을 그렸다 `[내 판단]`.

**ChatGPT가 낸 전체 그림.** 2013년의 질문(돈을 인터넷처럼 만들 수 있을까)에서 비트코인으로, 소비자 앱과 거래로 갔고, 직접 해 보니 비트코인의 변동성, 기존 금융망에 대한 의존, 규제와 운영의 복잡함을 알게 되었으며, 앱이나 거래소가 핵심이 아니라는 결론에서 디지털 달러로, 열린 표준과 인프라로 갔다. 지금의 Arc, CCTP, CPN, StableFX가 그 위에 있다(chatgpt.md:2706-2765). ChatGPT는 방향을 튼 것이 뒤늦게 결과를 보고 만든 성공담만은 아니라고 하면서도, Poloniex를 사고 1년 남짓 만에 크게 손해를 보고 판 것까지 넣으면 경영진이 처음부터 완벽한 전략을 알았다고 꾸며서도 안 된다고 적었다.

```text
2013년의 질문: 돈을 인터넷처럼 만들 수 있을까
                    |
                    v
                 비트코인
                    |
          +---------+---------+
          |                   |
      소비자 앱              거래
          |                   |
          +---------+---------+
                    |
            직접 해 보니 알게 된 것
                    |
     +--------------+--------------+
     |              |              |
비트코인의      기존 금융망에    규제와 운영의
변동성          대한 의존        복잡함
     |              |              |
     +--------------+--------------+
                    |
                    v
     앱이나 거래소가 핵심이 아니라는 결론
                    |
                    v
          디지털 달러: 열린 표준과 인프라
                    |
                    v
       지금의 Arc, CCTP, CPN, StableFX
```

**도식: ChatGPT가 낸 전체 그림.** 위 문단이 말로 옮긴 그림을 다시 그렸다(chatgpt.md:2713-2758).

**이 장의 내용을 되풀이한 구간.** 읽었고 위에 적은 것 밖의 새 내용은 없다: claude.md:436, claude.md:573, claude.md:691, claude.md:280, chatgpt.md:2885-2895, chatgpt.md:3333-3359, grok.md:3414-3415.

## 6. 다른 사업을 왜 헐값에 팔았나, 어차피 안 될 것을 알아서였나

### 6.1. 답의 뼈대: 질문의 전제를 사업마다 나눠야 한다

세 답이 2회차부터 같은 말로 시작했다: 한 바구니로 묶으면 안 된다(chatgpt.md:2158-2174, grok.md:1854-1856, grok.md:4631-4633, chatgpt.md:3363-3394).

| 사업 | 어떻게 끝났나 | 받은 것 | 세 답의 읽기 |
|---|---|---|---|
| Poloniex | 2019년 10월 분사 발표, 11월 매각 | 현금 3,315만 달러와 조건부 1,500만 달러. 처분손실 1.568억 달러 | 크게 손해 보고 판 것. 다만 손실의 대부분은 비싸게 산 값(영업권)이다. 안 될 것을 알아채고 나온 쪽에 가깝다 |
| Circle Trade | 2019년 12월 Kraken에 매각 | 현금 190만 달러와 조건부 Kraken 주식 | 실패한 사업이 아니다. 190만 달러는 사업 전체의 값이 아니다. 집중과 생존을 위해 놓은 것 |
| Circle Invest | 2020년 3월 30일 Voyager에 매각. Claude는 2월로 적었다(6.4절(Circle Invest)) | 처분이익 62.5만 달러 | 원래 작은 사업 |
| Circle Pay | 2019년 종료 | 판 것이 아니다 | 기술은 플랫폼에 다시 썼다 |
| SeedInvest | 2023년 5월 StartEngine에 매각 | StartEngine 주식 96만 주. 처분이익 2,160만 달러 | 2019년의 정리가 아니다 |

표의 한 행은 사업 하나다. 근거는 아래 절마다 적는다.

```text
2018년의 여섯 사업        어떻게 되었나

Circle Pay     ------->  2019년 종료 (판 것이 아니다)
Poloniex       ------->  2019년 10월 분사 발표, 11월 매각
Circle Trade   ------->  2019년 12월 Kraken에 매각
Circle Invest  ------->  2020년 3월 Voyager에 매각
SeedInvest     ------->  2023년 5월 StartEngine에 매각
USDC           ------->  남았다
```

**도식: 여섯 사업의 끝.** 2.3절(2018년: 확장기)의 여섯 제품을 왼쪽에, 위 표의 "어떻게 끝났나" 칸을 오른쪽에 놓았다. ChatGPT가 2019년의 정리를 가지 모양으로 그렸다(chatgpt.md:4319-4335).

- 두 과장을 함께 버린다: "안 될 것들을 미리 알아보고 잘 버렸다"도 아니고 "멀쩡한 사업을 비전 때문에 모두 희생했다"도 아니다(chatgpt.md:3363-3394).
- Grok의 말로는 "안 될 줄 알고 버렸다"와 "될 줄 알았는데 현금이 없어 버렸다"가 섞여 있다(grok.md:1854-1856).
- 세 답이 모인 문장: "**가격 극대화보다 복잡성, 규제, 이해상충을 빨리 제거했다. 그중 Poloniex는 실패, Trade는 전략적 포기.**"원문 그대로 Claude는 같은 뜻을 "가치를 따지기보다 규제 리스크와 복잡성을 빨리 떼어내는 것을 우선했다"고 썼다(claude.md:320-324).
- 회사가 스스로 쓴 말 `[Circle 글 확인]`: "Focusing effectively on stablecoin platforms means we must reduce complexity, tighten our product portfolio, and organize our teams to execute with greater agility"(블로그 focus-2020:41).
- 공시가 뒤에 붙인 설명: 투기적인 가상자산 거래와 관련된 사업을 처분하고 스테이블코인 중심으로 맞추기 시작했다(chatgpt.md:4450-4478, chatgpt.md:225-249) `[답의 주장]`.

**"헐값"이라는 말을 어떻게 다룰까.**

- 회계상의 손익과 헐값인가는 다른 물음이다. ChatGPT가 Claude의 "회계상 헐값 매각에 해당하는 것은 사실상 Poloniex뿐"이라는 표현을 두고 지적했다(chatgpt.md:3596-3694). 장부가가 0인 자산을 팔면 얼마를 받아도 회계상 이익이 나지만, 그것이 제값을 받았다는 뜻은 아니다.
- 그래서 세 답의 마지막 입장은 조금씩 다르다. Claude와 Grok은 "헐값의 회계 증거는 사실상 Poloniex뿐"이라고 남겼고(claude.md:481, claude.md:704, grok.md:4434-4435), ChatGPT는 Circle Trade가 헐값이었는지는 공개 자료로 확정할 수 없다고 남겼다(chatgpt.md:3596-3694, chatgpt.md:4560-4598).
- 나는 ChatGPT의 구분이 맞다고 본다 `[내 판단]`. 헐값인지를 말하려면 팔린 것의 공정한 값을 알아야 하는데, 세 답 어디에도 그 값은 없다. 있는 것은 받은 돈과 장부가뿐이다. 그러니 이 문서가 말할 수 있는 것은 "얼마를 받았고 왜 서둘렀나"까지이고 "제값이었나"는 열어 둔다.

**판 돈으로 회사를 살렸는가.**

- Grok은 2회차에 세 사업을 팔아 긴급 자금을 만들었다고 썼다가(grok.md:1803-1816), 교차 회차에서 스스로 낮췄다: Poloniex에서 들어온 현금이 약 3,300만 달러이고 Trade와 Invest의 현금은 작으므로, 판 돈으로 회사를 살렸다고 하면 과장이다. 더 큰 효과는 비용, 규제, 인력을 덜어 낸 것이다(grok.md:3338, grok.md:4645). Claude는 이 수정이 숫자와 맞는다고 평가했다(claude.md:560).
- 검산: 3,315만 + 190만 + 62.5만 = 3,567.5만 달러. 2019년 계속영업의 영업손실이 8,321만 달러였다고 하므로(5.4절(생존 쪽)), 판 돈은 한 해 손실의 절반에 못 미친다 `[내 판단]`. 여기에 Trade에서 남긴 운전자본을 현금으로 바꾼 돈이 더해지는데 그 크기는 S-4에도 금액으로 나오지 않는다(6.3절(Circle Trade)). 받은 돈과 쓴 돈은 S-4의 현금흐름으로 확인된다 `[공시 확인]`: 2019년에 영업으로 5,970만 달러가 나갔고(S-4:4067) 투자활동으로 3,720만 달러가 들어왔다(S-4:4079).
- 이 검산은 Allaire의 회고(자산을 판 돈으로 새 지분 투자 없이 버텼다, 5.4절(생존 쪽))와 긴장이 있다. 둘이 함께 참이려면 운전자본을 현금으로 바꾼 돈이 컸거나, 인력을 450명에서 59명으로 줄여 쓰는 돈이 크게 줄었어야 한다. 세 답은 이 긴장을 짚지 않았다 `[내 판단]`.

**대가를 무엇으로 받았나.**

- Claude는 2회차에 대가를 현금보다 인수자의 주식으로 받았다고 일반화했다가(claude.md:320-324), 교차 회차에서 틀렸다고 바로잡았다: 주식으로 받은 것은 Invest(Voyager 지분)와 SeedInvest뿐이고, Poloniex는 현금 중심이며, Trade는 현금에 조건부 주식이 붙었다(claude.md:415-418).
- Claude는 같은 자리에서 "매각가는 대부분 비공개"라고 쓴 것도 틀렸다고 바로잡았다. 언론 보도에서는 비공개였지만 2021년의 SPAC 합병 공시(S-4)에 금액이 있다(claude.md:415-418).
- S-4로 확인한 것 `[공시 확인]`: Poloniex는 현금 3,315만 달러와 조건부 대가 1,500만 달러(S-4:6605-6606), Trade는 현금 190만 달러와 조건부 주식(S-4:6589), Invest는 현금 10만 달러와 Voyager 주식 52.5만 달러어치다(S-4:6579-6580). Claude가 바로잡은 뒤의 서술이 공시와 맞는다.

**결과로 보면.**

- 2022년의 Voyager 파산과 FTX 붕괴를 생각하면, 소매 거래 사업을 들고 있었을 때보다 나은 선택이었다(claude.md:320-324, grok.md:3361). Claude는 이것이 결과를 알고 하는 말이라고 밝혔다.
- 뒤에서 보면 USDC에 다 건 것이 맞았다. 그때의 기대값으로는 도박이었다(grok.md:1866-1877).
- Paxos의 전 임원 Austin Campbell의 평: 다트를 여러 개 던지고 되는 것을 보자는 전략이었고 꽂힌 다트가 USDC였다(grok.md:1818-1828) `[답의 주장]`.

### 6.2. Poloniex

**무엇을 하려고 샀나.**

- 2018년 2월에 인수했다 `[공시 확인]`(10-K:6211), `[Circle 글 확인]`(블로그 polo-acquire:25).
- 인수 발표의 글 `[Circle 글 확인]`: Pay, Trade, Invest에 더해 Poloniex가 "An open global token marketplace"라는 자리를 채운다(블로그 polo-acquire:27-29). 앞날의 그림은 "a robust multi-sided distributed marketplace that can host tokens which represent everything of value: physical goods, fundraising and equity, real estate, creative productions ..."(블로그 polo-acquire:55).
- 세 답의 요약, 곧 알트코인 거래소가 아니라 모든 가치가 토큰으로 거래되는 장터로 키우려 했다는 것(chatgpt.md:157-172, chatgpt.md:4415-4446, grok.md:1818-1828)은 원문과 맞는다.
- 같은 글에는 실사에 관한 문장이 있다 `[Circle 글 확인]`: "completed extensive due diligence together"(블로그 polo-acquire:37). 그리고 인수 직후의 과제로 고객 지원과 "scale risk, compliance, and technical operations"를 들었다(블로그 polo-acquire:43). 회사가 Poloniex의 규제 준수가 약하다는 것을 알고 샀다는 정황이다. 세 답은 이 글의 이 대목을 인용하지 않았다 `[내 판단]`.
- 2019년 1월의 글은 이 인수를 "one of the largest acquisitions in the history of the cryptocurrency industry"라고 불렀다 `[Circle 글 확인]`(블로그 review-2018:33).

**얼마에 샀나.**

- 약 4억 달러라는 숫자는 당시 언론의 보도다. Claude와 Grok은 1회차와 2회차에 사실처럼 썼고(claude.md:26, grok.md:76, grok.md:1860), ChatGPT가 세 번 지적했다(chatgpt.md:1526-1546, chatgpt.md:2943-2979, chatgpt.md:3698-3788).
- ChatGPT의 근거: Circle의 공식 발표는 금액을 밝히지 않았고, 회사는 뒤에 보도가 틀렸다고 말했다. 그 문장은 원문에 있다 `[Circle 글 확인]`: "Although published reports continue to misrepresent both the original acquisition and the context of the spin out"(블로그 focus-2020:47). 인수 발표의 글에도 금액은 없다(블로그 polo-acquire:21-64).
- Claude는 2회차 교차 1의 끝에서 다시 "2018년에 4억 달러를 주고 산 결정"이라고 썼고(claude.md:481), ChatGPT는 이것을 "명확한 퇴행"이라고 불렀다(chatgpt.md:3698-3788). Claude는 다음 회차에서 고쳤다: 4억 달러는 Fortune이 익명의 소식통으로 보도한 금액이고, 자신이 본 SEC 자료에 인수 대가는 없다(claude.md:531-534).
- 세 답의 마지막 표기: "보도상 약 4억 달러"(claude.md:575-576, claude.md:700, grok.md:4386, grok.md:4637).
- 내가 덧붙이는 것: 회사의 그 문장은 보도가 "틀렸다"고만 하고 무엇이 어떻게 틀렸는지는 말하지 않는다. 그래서 4억 달러가 너무 큰지 작은지, 구조가 달랐는지는 이 문장으로 알 수 없다. 넘긴 장부의 영업권이 1.856억 달러라는 것(아래)은 인수 때 순자산보다 적어도 그만큼을 더 주었다는 뜻이므로, 값이 수억 달러 단위였다는 것은 장부와 어긋나지 않는다 `[내 판단]`.
- S-4에도 인수 대가의 합계는 없다. 2018년의 인수는 S-4가 싣는 재무제표의 기간(2019년과 2020년) 밖이다. 대신 조각이 셋 있다 `[공시 확인]`.
  - 인수하려고 2018년 2월 21일에 Silicon Valley Bank에서 2,000만 달러를 연 8%로 빌렸고 2019년 11월에 모두 갚았다(S-4:4010).
  - 대가의 일부는 나중에 주는 돈과 매출에 따라 주는 돈이었다. 판 쪽(Ophelix)에 남아 있던 빚이 합의 전에 6,390만 달러였고, 2020년 7월의 중재 합의로 3,070만 달러만 주기로 해서 3,320만 달러의 이익을 기록했다(S-4:5994-5998). Circle은 OFAC의 조사와 도지코인 관련 손실을 이유로 2018년 12월부터 지급을 멈췄었다.
  - 인수 때 발행한 워런트가 있었고 2019년에 그 값이 5,950만 달러 내렸다(S-4:3908).
  - 이 조각들은 인수 값이 현금 한 번으로 치른 것이 아니라 대출, 뒤로 미룬 지급, 매출 연동 지급, 워런트를 섞은 구조였다는 것을 보여 준다. 합계가 4억 달러였는지는 여전히 알 수 없다 `[내 판단]`.

**얼마에 팔았나.** 아래 숫자는 S-4의 처분손실 계산표와 대조했다 `[공시 확인]`(S-4:6603-6614).

| 항목 | 값 | 세 답의 근거 | S-4(천 달러) |
|---|---|---|---|
| 받은 현금 | 3,315만 달러 | chatgpt.md:2178-2259, chatgpt.md:3698-3788 | 33,150, S-4:6605 |
| 조건부 대가 | 1,500만 달러 | 같은 곳 | 15,000, S-4:6606 |
| 받은 것의 합 | 4,815만 달러 | 같은 곳 | 표에는 합계 줄이 없다. 33,150 + 15,000 |
| 넘긴 순자산의 장부가 | 약 2.049억 달러 | 같은 곳 | 2.049억 달러, S-4:6614 |
| 그 가운데 영업권 | 1억 8,555.5만 달러 | chatgpt.md:3698-3788 | 185,555, S-4:6609 |
| 그 가운데 그 밖의 무형자산 | 1,936만 달러 | chatgpt.md:3698-3788 | 19,360, S-4:6608 |
| 그 가운데 디지털 자산 | 5.9만 달러 | chatgpt.md:3698-3788 | 59, S-4:6610 |
| 처분손실 | 1억 5,682.4만 달러 | chatgpt.md:2943-2979 | (156,824), S-4:6611 |

표의 한 행은 항목 하나다.

```text
넘긴 순자산의 장부가                            받은 것
  영업권              1억 8,555.5만 달러          현금          3,315만 달러
  그 밖의 무형자산    1,936만 달러                조건부 대가   1,500만 달러
  디지털 자산         5.9만 달러
  ----------------------------------------                            ----------------------------
  합                  2억 497.4만 달러            합            4,815만 달러

2억 497.4만 달러  -  4,815만 달러  =  1억 5,682.4만 달러 (처분손실)

장부가 가운데 영업권의 몫 (한 칸은 2%)
  영업권    #############################################   약 90%
  나머지    #####

조건부 대가 1,500만 달러를 받는 때
  2020년 1,000만 -> 2021년 5월 200만 -> 2021년 11월 100만 -> 2022년 5월 100만 -> 2024년 11월 100만
```

**도식: Poloniex 처분손실의 셈.** 위 표와 검산을 옮겼다. ChatGPT가 같은 셈을 그렸다(chatgpt.md:3707-3726).

- 검산: 1억 8,555.5만 + 1,936만 + 5.9만 = 2억 497.4만 달러(장부가). 2억 497.4만 - 4,815만 = 1억 5,682.4만 달러(처분손실). 세 숫자가 서로 맞는다 `[내 판단]`.
- 영업권을 Claude는 1.855억, ChatGPT는 1.856억 달러로 적었다(claude.md:433). 1억 8,555.5만 달러를 버리느냐 올리느냐의 차이다.
- Claude는 받은 현금을 3,320만 달러로 적었다(claude.md:415-418). 같은 숫자의 반올림이다.
- S-4 안에서도 디지털 자산의 숫자가 둘이다. 계산표는 5.9만 달러이고(S-4:6610), 같은 주석의 글은 "cryptocurrency of \$1.7 million"이라고 적는다(S-4:6614). 장부가 2.049억 달러는 글의 숫자로 더해야 맞고(185.5 + 19.4 = 204.9), 처분손실은 표의 숫자로 계산해야 맞는다. 어느 쪽이 맞는지는 S-4만으로 알 수 없다 `[내 판단]`.
- 조건부 대가 1,500만 달러는 2020년에 1,000만 달러가 들어왔고, 나머지는 2021년 5월 200만, 2021년 11월 100만, 2022년 5월 100만, 2024년 11월 100만 달러로 나눠 받기로 되어 있었다 `[공시 확인]`(S-4:6614).
- Poloniex가 고객 대신 가지고 있던 가상자산은 팔 때 약 10억 달러어치였다. 미국 밖 고객의 것은 새 회사로 넘겼고, 미국 고객과 제재 대상 고객의 것은 Circle에 남았다 `[공시 확인]`(S-4:3613).
- **손실의 뜻.** 2억 달러어치의 현금 같은 자산을 4,800만 달러에 넘긴 것이 아니다. 장부가의 90%가 영업권, 곧 2018년에 살 때 순자산보다 더 얹어 준 값이다. 그 기대가 무너져서 팔 때 사라진 것이다(chatgpt.md:2178-2259, grok.md:3345, grok.md:4528). ChatGPT의 문장: Poloniex는 2019년에 너무 싸게 판 것보다 2018년의 인수 판단이 실패한 것에 가깝다(chatgpt.md:3698-3788, chatgpt.md:4530-4556). Claude도 같은 말을 했다(claude.md:481).
- vault의 10-K에는 처분손실 숫자가 나오지 않는다. 2019년은 10-K가 다루는 기간(2023년부터 2025년) 밖이어서, 위 숫자의 근거는 S-4다.

**왜 팔았나.**

- 회사의 설명 `[Circle 글 확인]`: "we have also faced challenges as a US company growing a competitive international exchange"(블로그 polo-spinout:29). 그리고 "in order to gain focus on our stablecoin platform mission as well as practical US regulatory reality, we determined that we should exit the exchange business"(블로그 focus-2020:47).
- 새 회사는 Polo Digital Assets, Ltd.이고 아시아의 투자 그룹이 뒤에 있다. 거래소에 1억 달러 넘게 투자할 계획이라고 했다 `[Circle 글 확인]`(블로그 polo-spinout:23, polo-spinout:31).
- 미국 고객은 2019년 11월 1일부터 거래할 수 없게 되었다 `[Circle 글 확인]`(블로그 polo-spinout:33, polo-us-end:23). 곧 새 주인은 미국의 규제 밖에서 거래소를 운영하기로 한 것이다. Grok은 이것을 두고 판 값이 사업의 값이 아니라 규제 차이를 넘겨주는 값에 가깝다고 읽었다(grok.md:1866-1877).
- 시장점유율이 2019년 중반에 1.1%까지 떨어졌다(claude.md:291, chatgpt.md:2897-2909) `[답의 주장]`. The Block의 조사다. ChatGPT는 이 숫자를 Grok이 찾았다고 적었는데 Claude가 먼저 냈다(claude.md:547-552).
- 2019년 Poloniex의 매출은 약 1,130만 달러였고, 공시된 직접 비용만 더해도 1,700만 달러가 넘는다(chatgpt.md:2178-2259). S-4와 맞는다 `[공시 확인]`(S-4:6615): 매출 1,130만 달러에 제작비 230만, 블록체인 수수료 30만, 전문 용역 370만, 보험과 규제 280만, 일반관리 170만, 기타 30만, 무형자산 상각 640만 달러다. 비용의 합은 1,750만 달러다(2.3 + 0.3 + 3.7 + 2.8 + 1.7 + 0.3 + 6.4 = 17.5).
- 2019년에 증거금 대출에서 1,800 BTC 규모의 손실이 나서 분쟁이 이어졌다(chatgpt.md:2178-2259). ChatGPT만 썼고 S-4에 있다 `[공시 확인]`(S-4:5992).
- Grok의 읽기: 미국의 규제(고객 확인, 제재, BitLicense 계열의 의무)를 얹으면 알트코인 거래소가 돈을 버는 방식과 부딪친다(grok.md:1818-1828). 규제받는 달러 발행사가 투기 거래소의 주인이면 뒤에 은행, Visa, BlackRock과 일하기 어렵다(grok.md:1866-1877).
- 분사 때 직원 80명 넘게가 새 회사로 옮겼다 `[Circle 글 확인]`(블로그 focus-2020:53).

**규제 문제는 언제부터 있었고, 회사는 알고 샀나.**

| 때 | 일 | 근거 |
|---|---|---|
| 2017년 12월 | SEC가 Poloniex에 관한 조사를 시작했다(인수 두 달 전) | `[공시 확인]` S-4:3315. 글은 "Between December 2017 and March 2020 ... the SEC served Poloniex, LLC with several subpoenas"이다. claude.md:309-313, chatgpt.md:3230-3271 |
| 2018년 2월 | Circle이 인수 | `[공시 확인]` 10-K:6211 |
| 2018년 4월 | OFAC가 Poloniex에 행정 소환장을 보냈다 | `[공시 확인]` 10-K:6212-6213 |
| 2019년 9월 | OFAC의 두 번째 소환장 | `[공시 확인]` 10-K:6213 |
| 2021년 8월 | SEC에 약 1,040만 달러를 냈다. SEC는 2017년 7월부터 2019년 11월까지 등록하지 않은 거래소를 운영했다고 판단했다 | 금액은 `[공시 확인]` S-4:975(2021년 3월에 합의를 제안했고 약 1,040만 달러). 낸 달과 SEC의 판단 기간은 `[답의 주장]` claude.md:309-313, chatgpt.md:3230-3271 |
| 2023년 4월, 5월 | OFAC와 합의하고 760만 달러를 냈다 | `[공시 확인]` 10-K:6214-6215 |
| 2023년 11월 | 새 주인 아래에서 약 1억 달러 규모의 해킹 | `[답의 주장]` claude.md:309-313 |

표의 한 행은 일 하나다.

```text
2017년 12월       SEC의 조사 시작
2018년 2월        Circle이 인수               <-- 조사가 시작되고 두 달 뒤
2018년 4월        OFAC의 첫 소환장
2019년 9월        OFAC의 두 번째 소환장
2019년 11월       매각                        <-- 그 뒤에도 과거의 운영에 대한 책임이 남았다
2021년            SEC에 약 1,040만 달러
2023년 4월, 5월   OFAC와 합의, 760만 달러
```

**도식: Poloniex의 규제 문제와 인수, 매각의 순서.** 위 표에 6.1절(답의 뼈대)의 매각 시점을 더했다. 세 답은 이것을 그리지 않았다.

- 10-K의 글 `[공시 확인]`: OFAC는 "accounts opened and/or closed on the Poloniex digital asset trading platform by persons potentially located in Iran, Cuba, Syria, North Korea, Crimea, and Sudan"에 관한 자료를 요구했고, "In April 2023, Poloniex executed a settlement agreement with OFAC regarding its investigation and paid OFAC a settlement fee of \$7.6 million in May 2023"(10-K:6212-6215).
- SEC에 낸 1,040만 달러는 vault의 10-K에서 찾지 못했다(검색: `grep -n -E '\$10\.4 million' web-circle-fy2025-10k.md`, 0건). ChatGPT는 이 숫자의 출처로 10-K도 들었는데(chatgpt.md:3230-3271), 적어도 이 10-K에는 없다 `[내 판단]`. 2021년의 S-4에는 있다(S-4:975).
- OFAC에 낼 돈을 회사가 처음에 110만에서 280만 달러로 추정했다고 ChatGPT가 적었다(chatgpt.md:2178-2259) `[답의 주장]`. 실제로 낸 돈은 760만 달러여서 추정의 위쪽 끝의 2.7배다 `[내 판단]`.
- **판 뒤에도 책임이 남았다.** Claude는 2회차에 "값을 받고 판 것이 아니라 리스크를 떼어낸 거래"라고 썼고(claude.md:309-313), ChatGPT가 절반만 맞다고 지적했다: 앞으로의 운영, 자본, 규제의 부담은 덜었지만 과거의 운영에 대한 법적 책임은 남았다(chatgpt.md:3230-3271). Claude와 Grok이 이 지적을 받아들였다(claude.md:543, grok.md:3359). 공시가 이 지적을 받친다: 2019년에 판 사업의 합의금을 2023년에 Circle 쪽이 냈다 `[공시 확인]`. Claude는 회사가 인수 때 규제 책임의 일부를 떠안기로 했다고 밝혔다고 적었고(claude.md:309-313), S-4에 그 문장이 있다 `[공시 확인]`: "as part of the acquisition agreed to assume certain potential regulatory liabilities"(S-4:967).
- **알고 샀나.** 여기서 ChatGPT와 Claude가 끝까지 갈렸다.
  - ChatGPT: SEC의 조사가 인수 전부터 있었다는 것은 확인되지만, 경영진이 실사에서 무엇을 얼마나 알았는지는 공개 자료로 확정하기 어렵다(chatgpt.md:3230-3271).
  - Claude: 지나치게 신중하다. 인수 당시 뉴욕타임스의 기자가 공개한 Circle의 내부 자료에 SEC가 과거의 활동에 대해 집행 조치를 하지 않을 것이라는 취지가 있었고, Fortune에 따르면 Allaire는 기밀 발표 자료에서 Poloniex의 제재 위반 이력을 인정했다. 회사는 문제를 알았고 풀렸다고 판단하고 샀으며 그 판단이 틀렸다. 다만 문제의 범위를 얼마나 알았는지는 여전히 알 수 없다(claude.md:547-552, claude.md:578, claude.md:704).
  - Grok도 Allaire가 내부 자료에서 제재 위반 이력을 인정했다는 보도를 들었다(grok.md:1818-1828).
  - 내 읽기: Claude 쪽이 더 받쳐진다 `[내 판단]`. 회사 자신의 인수 발표문이 "extensive due diligence"를 했다고 쓰고 규제 준수의 확충을 첫 과제로 든다(위). 실사를 넓게 했다고 스스로 말한 회사가 두 달 전에 시작된 SEC의 조사를 몰랐다고 보기는 어렵다. S-4가 이 읽기를 더 받친다: SEC의 소환장은 인수 두 달 전인 2017년 12월부터 나왔고(S-4:3315), 회사는 인수하면서 규제 책임을 떠안기로 약속했다(S-4:967). 책임을 떠안는 조항을 계약에 넣었다는 것은 그 책임이 있을 수 있음을 알았다는 뜻이다. 다만 Claude가 든 두 보도는 내가 열지 않았다 `[미독 - 외부 링크]`.
- "안 될 것을 알아서였나"에 대한 세 답의 답: Poloniex에 한해서는 그렇다고 볼 증거가 많다(chatgpt.md:2178-2259, claude.md:309-313, grok.md:4643).

### 6.3. Circle Trade

**어떤 사업이었나.**

- 소비자 앱에 비트코인을 대려고 회사 안에서 사고팔던 일이 커진 장외거래 데스크다. 2019년 3월의 글이 그 경위를 적는다 `[Circle 글 확인]`: "As users of the app bought and sold bitcoin, Circle employees were in the background buying bitcoin to meet customer demand"(블로그 otc-5yr:29).
- 2018년의 실적 `[Circle 글 확인]`: 장외거래 1만 건 이상, 상대방 600곳 가까이, 명목 거래액 240억 달러(블로그 review-2018:75-78). 세 답이 쓴 숫자와 같다(chatgpt.md:2263-2283, grok.md:77, claude.md:177).
- 회사는 팔면서도 성공이라고 불렀다 `[Circle 글 확인]`: "Circle Trade represents an enormous success for the industry as well as for Circle"(블로그 focus-2020:45).
- 2019년의 매출은 727.6만 달러였다(chatgpt.md:3596-3694) `[공시 확인]`(S-4:6770).
- 2017년에서 2018년 사이에 석 달 동안 6,000만 달러 넘게 벌었다고 Claude가 썼다가(claude.md:315-318), 원문은 이익이 아니라 매출이라고 바로잡았다(claude.md:536) `[답의 주장]`.
- 내가 덧붙이는 읽기: 석 달 매출 6,000만 달러(2017-2018년의 정점)와 한 해 매출 727.6만 달러(2019년)를 나란히 놓으면, 팔 때의 Trade는 정점의 3% 크기였다(727.6만 / 2.4억). "잘되던 사업을 팔았다"는 세 답의 표현은 2018년의 Trade에 맞고 2019년 말의 Trade에는 덜 맞는다 `[내 판단]`. 727.6만 달러는 S-4로 확인했고 6,000만 달러는 확인하지 못했다.

**무엇을 팔았나.** 아래는 S-4의 주석과 대조했다 `[공시 확인]`(S-4:6589-6601). 세 답이 쓴 숫자가 모두 맞는다.

- Kraken을 운영하는 Payward에 넘긴 것은 Circle Trade의 "internally generated intangible assets", 곧 회사 안에서 만든 무형자산이다(chatgpt.md:1548-1567, chatgpt.md:3596-3694).
- 받은 것:
  - 현금 190만 달러.
  - 조건부 Payward 주식. 실적 조건에 최대 252,017주, 인력 유지 조건에 최대 100,807주, 기준가는 주당 19.84달러(claude.md:559). 실제로는 2021년 4월에 83,186주를 받았다(claude.md:415-418).
  - 검산: 83,186 x 19.84 = 165.0만 달러. Claude의 "약 165만 달러"와 맞는다. 최대로 받을 수 있던 것은 (252,017 + 100,807) x 19.84 = 700.0만 달러여서, 실제로는 최대치의 24%를 받았다 `[내 판단]`.
  - 소개(referral)에 대해서는 답이 갈렸다. ChatGPT는 새 장외거래 고객 거래액의 0.1%를 받는 소개 대금이 따로 있다고 썼고(chatgpt.md:3596-3694), Claude는 공시에서 소개는 따로 받는 수수료가 아니라 주식을 받기 위한 조건 가운데 하나라고 썼다(claude.md:566). S-4로 풀린다 `[공시 확인]`. 글은 둘을 따로 적는다: 조건부 주식은 "dependent on earnout, retention and referral conditions"이고, 그것과 별도로 "Additionally, the Company is entitled to receive referral payments from the Buyer based on 0.1% of gross OTC volume from new clients for the first year"이다(S-4:6589). 곧 ChatGPT가 맞고, Claude가 읽은 것은 앞 문장이다. 그리고 실제로는 한 푼도 받지 못했다: "there were no referral share payments due as no referrals were made in the one-year period"(S-4:6592). Grok의 최종 답은 "소개수수료"를 따로 적었다(grok.md:4529, grok.md:4638).
- Circle에 남은 것: Circle Trade가 가지고 있던 법정화폐와 가상자산, 곧 운전자본. 가상자산은 판 직후에 법정화폐로 바꿨다(chatgpt.md:2158-2174, chatgpt.md:3596-3694).
- 남은 운전자본이 얼마였는지는 끝까지 금액으로 나오지 않았다(grok.md:3352, grok.md:4388). ChatGPT는 "significant"라는 공시의 말만 옮겼다. S-4도 그렇다 `[공시 확인]`: "Circle Trade held significant fiat currency and cryptocurrency which were retained by the Company under the terms of the sale. All material cryptocurrency working capital was liquidated to fiat currency in December 2019 following the sale"(S-4:6600). 같은 줄에 따르면 Trade는 2,400 BTC를 빌려 쓰고 있었고 판 뒤에 모두 갚았다. 남긴 것에서 갚은 것을 뺀 순액은 S-4에 없다.
- 회계상으로는 처분이익이 났다. 회사 안에서 만든 무형자산은 장부가가 0이기 때문이다(claude.md:434, chatgpt.md:3596-3694).
- 세 답에 없고 S-4에서 더하는 것 `[공시 확인]`(S-4:6599): 2019년에 Trade는 매출 730만 달러에 미실현 손실 90만, 거래 비용 70만, 인건비 170만, 비트코인 대출과 한도 대출의 이자 170만, 임차료 10만 달러가 있었다. 계속영업 밖의 Trade 손익은 2019년에 327만 달러 이익이다(처분이익 190만 달러 포함, S-4:6164). 곧 팔던 해에도 Trade는 이익을 내고 있었다 `[내 판단]`.

```text
Circle Trade
|
+-- 회사 안에서 만든 무형자산        -->  Kraken을 운영하는 Payward에 넘겼다
|       받은 것
|         현금 190만 달러
|         조건부 Payward 주식: 최대 352,824주 가운데 83,186주를 받음 (약 165만 달러)
|         새 고객 거래액의 0.1%의 소개 대금을 받을 권리 (실제로 받은 것은 없다)
|
+-- 법정화폐와 가상자산 (운전자본)   -->  Circle에 남았다
        금액은 공시에 없다


견줄 수 없는 것    거래액 240억 달러 (2018년)   과   받은 현금 190만 달러
견줄 수 있는 것    매출 727.6만 달러 (2019년)   과   받은 것 355만 달러 (현금 190만 + 주식 165만)
```

**도식: Circle Trade에서 넘긴 것과 남긴 것.** 위 항목과 아래 "내가 덧붙이는 것"을 그렸다. 352,824주는 252,017주와 100,807주를 더한 내 셈이다. ChatGPT가 넘긴 것과 남긴 것을 그렸다(chatgpt.md:3640-3652, chatgpt.md:4587-4593).

**그래서 헐값인가.**

- 1회차에 Grok이 "현금 약 190만 달러"라고 썼고(grok.md:77), Claude는 출처가 없다고 했으며(claude.md:155), ChatGPT는 숫자가 맞다고 확인하면서 그것을 사업 전체의 값으로 읽으면 안 된다고 했다(chatgpt.md:1548-1567).
- 2회차에 Grok은 "헐값 논란의 핵심"이고 "fire sale"이라는 말이 나왔다고 썼다(grok.md:1861). ChatGPT와 Claude가 과장이라고 지적했고(chatgpt.md:2915-2939, claude.md:455), Grok은 자신의 핵심 약점이었다고 받아들였다(grok.md:3337).
- 세 답의 마지막 입장: 한 해 240억 달러를 거래하던 사업을 190만 달러에 팔았다는 비교는 거래액과 판 대상을 혼동한 것이다(chatgpt.md:4560-4598, claude.md:699, grok.md:4529).
- 내가 덧붙이는 것: 이 비교에는 혼동이 하나 더 있다. 240억 달러는 거래액이고 매출이 아니다. 매출은 727.6만 달러였다고 하므로, 받은 현금 190만 달러에 실제로 받은 주식 165만 달러를 더한 355만 달러는 한 해 매출의 절반쯤이다(355 / 727.6 = 0.49). 고객 관계와 상표만 넘기는 거래로서 터무니없는 값은 아니다 `[내 판단]`.

**왜 팔았나.**

- Claude의 추론(확신도 중간): 약세장에서 장외거래의 이윤이 줄었고, 발행사가 시장을 만드는 상대방이 되는 이해상충이 있었고, 사람이 빠져나가고 있었다(claude.md:315-318). 2019년의 감원 직후에 핵심 트레이더들이 떠나고 있었고, 그 가운데 한 사람은 뒤에 FTX 쪽의 핵심 인물이 되었다고 한다 `[답의 주장]`. Grok은 이 보도를 1차로 다시 확인하지 않았다고 남겼다(grok.md:3364).
- Grok의 읽기: 안 되어서가 아니라, 되면 현금이 나오지만 집중과 생존을 위해 판 것이다. 지금 현금을 만드는 것이 내년의 가능성보다 급했다(grok.md:1866-1877). 그리고 발행사가 거래소와 장외거래를 들고 있으면 USDC를 받아 주는 거래소와 경쟁하게 된다(grok.md:4645).
- ChatGPT의 읽기: 돈이 되는 사업도 팔았다는 것이 USDC에 집중한 선택이 얼마나 강했는지를 보여 준다(chatgpt.md:2263-2283).
- 세 답은 Trade를 "반례"라고 불렀다: 실패해서 버린 사업이 아니다(claude.md:315-318, grok.md:4645).
- 내가 덧붙이는 것: 사는 쪽이 Kraken이라는 점도 볼 만하다. 회사의 글은 "We have known and admired Jesse and his team at Kraken for many years"라고 적는다 `[Circle 글 확인]`(블로그 focus-2020:45). Kraken은 USDC를 받아 주는 거래소다. 경쟁하던 사업을 유통 협력사에 넘긴 셈이어서, 5.5절(해석)의 중립성 논점과 맞는다 `[내 판단]`.

### 6.4. Circle Invest

- 2018년 봄에 낸 소매용 투자 앱이다 `[Circle 글 확인]`(블로그 review-2018:55). 구매의 30% 이상이 정기 구매였다(블로그 review-2018:64).
- 2020년 3월 30일에 Voyager Digital에 팔았다 `[공시 확인]`(S-4:6576). ChatGPT의 최종 답이 3월로 적은 것이 맞고(chatgpt.md:4450-4478), Claude의 2월(claude.md:305-307, claude.md:701-702)은 공시와 다르다 `[공시와 다름]`.
- 계좌는 4만 개였다(claude.md:305-307) `[답의 주장]`.
- 받은 것 `[공시 확인]`(S-4:6576-6583): 현금 10만 달러와 Voyager 주식 3,495,156주(주당 0.15달러, 52.5만 달러어치, 당시 Voyager 발행 주식의 약 4.0%)이고 처분이익은 62.5만 달러다. Grok의 분해(현금 10만 달러와 주식 약 52.5만 달러, grok.md:1862-1864)와 Claude의 "지분 약 4%"(claude.md:305-307)가 모두 맞는다. Claude는 Grok의 분해를 확인하지 못했다고 남겼었다(claude.md:457). 2019년 매출 56.7만 달러(chatgpt.md:2158-2174)도 맞는다(S-4:6768).
- 세 답의 읽기: 사업이 원래 작았다. 값은 거의 남은 값이다.
- 2019년 11월에도 회사는 Invest를 계속 운영한다고 알렸다 `[Circle 글 확인]`: "Circle's other products and services including Circle Trade, Circle Invest, and USDC are not impacted by this change to Poloniex"(블로그 polo-us-end:27). 그리고 2019년 12월의 글은 Trade, Poloniex, Pay, SeedInvest를 하나씩 다루면서 Invest의 앞날은 말하지 않는다(블로그 focus-2020:45-51). 석 달 남짓 뒤에 팔았다 `[내 판단]`.
- Voyager는 2022년에 파산했다(claude.md:305-307, grok.md:4530-4531) `[답의 주장]`. 세 답은 받은 주식을 어떻게 했는지 적지 않았는데 S-4에 있다 `[공시 확인]`: Circle은 2021년 1월과 2월에 Voyager 주식을 모두 팔아 2,610만 달러를 받았다(S-4:5690, 수수료와 환차손 10만 달러를 뺀 값이다. 같은 서류의 다른 대목은 2,790만 달러로 적는다, S-4:3605). 52.5만 달러로 받은 주식이 열 달 뒤에 약 50배가 되었고, Voyager가 파산하기 전에 처분했다.
- 내가 덧붙이는 읽기 `[내 판단]`: 세 답은 Invest를 "값이 거의 남은 값"인 작은 거래로 적었다. 계약 때의 값으로는 맞다. 그런데 실제로 손에 쥔 돈으로 보면 Invest(약 2,610만 달러)는 Trade(현금 190만 달러와 주식 165만 달러어치)보다 훨씬 많고, Poloniex에서 받은 현금 3,315만 달러에 가깝다. "헐값에 팔았다"는 전제는 Invest에서 가장 크게 어긋난다. 다만 이것은 Voyager의 주가가 2021년 초에 크게 오른 결과이고, 팔 때 회사가 내다본 값은 아니다.

```text
2020년 3월 30일   Voyager에 매각
      |             받은 것: 현금 10만 달러 + Voyager 주식 52.5만 달러어치
      v
2021년 1, 2월     받은 주식을 모두 팔았다: 2,610만 달러 (약 50배)
      |
      v
2022년            Voyager 파산
```

**도식: Circle Invest의 대가가 된 주식.** 위 항목을 옮겼다. 세 답은 이것을 그리지 않았다.

### 6.5. Circle Pay

- 판 것이 아니라 끝낸 것이다. 2019년 6월 13일에 알렸고 7월 8일부터 출금만 되었으며 9월 30일에 완전히 끝났다 `[Circle 글 확인]`(블로그 pay-sunset:39-42). Claude와 Grok이 쓴 날짜와 같다(claude.md:174-176, claude.md:698, grok.md:78-80).
- 기술은 플랫폼 서비스에 다시 썼다 `[Circle 글 확인]`(블로그 focus-2020:49). Grok은 이것을 "기술은 플랫폼에 잔류한다고 주장"이라고 단서를 달아 썼다(grok.md:1862-1864). 회사의 말이므로 그 단서가 맞다.
- 왜 끝냈는지는 5.3절(앱보다 USDC였던 이유)에 있다.

### 6.6. SeedInvest

- 주식형 크라우드펀딩 플랫폼이고 등록된 브로커딜러이자 대체거래시스템이다 `[Circle 글 확인]`(블로그 focus-2020:51).
- **산 때.** Claude는 2018년 10월에 인수를 발표했다고 썼고(claude.md:26), Grok은 2019년 3월 인수라고 썼다(grok.md:78-80). 둘 다 맞을 수 있다: 2018년 말에 계약을 맺었고(블로그 review-2018:102), 2019년에 인수를 끝냈다(블로그 polo-spinout:41) `[Circle 글 확인]`. 달은 S-4에 있다 `[공시 확인]`: "We acquired SeedInvest in March 2019"(S-4:3598). 대가는 4,020만 달러이고 현금 760만 달러, 공정가치 2,960만 달러의 전환사채, 조건부 대가 310만 달러로 이루어졌다. 영업권 3,800만 달러를 기록했고 같은 해에 1,390만 달러를 손상 처리했다(S-4:3600).
- 인수 대가의 일부로 원금 2,400만 달러의 어음을 발행했다 `[공시 확인]`(10-K:2867).
- **2019년에는 팔지 않았다.** 2019년 10월에 회사는 SeedInvest를 키우겠다고 썼고(블로그 polo-spinout:25), 12월에는 독립된 계열사로 계속 운영한다고 썼다(블로그 focus-2020:51) `[Circle 글 확인]`. 세 답이 모두 2019년의 정리와 때가 다르다고 적었다(chatgpt.md:2158-2174, claude.md:305-307, grok.md:4530-4531).
- **판 때와 받은 것** `[공시 확인]`(10-K:5050-5054): 2022년 10월에 StartEngine의 자회사에 자산을 팔기로 계약했고, 규제 승인을 받아 2023년 5월에 끝났다. 받은 것은 StartEngine 보통주 96만 주이고, 처분이익 2,160만 달러를 기록했다. Claude는 5월 9일로 적었다(claude.md:174-176).
- 주식 수와 처분이익은 세 답에 없고 공시에서 더했다. 이익이 났다는 것은 "헐값"이라는 전제와 가장 멀다. 다만 받은 것이 상장되지 않은 회사의 주식이어서, 2,160만 달러는 현금이 아니라 평가한 값이다 `[내 판단]`.
- 왜 팔았나: Allaire는 토큰화 증권이 규제 때문에 느리게 진행되었고, 거래소에서 이미 나왔으니 브로커딜러 면허 묶음도 필요 없어졌다고 말했다(grok.md:1834) `[답의 주장]`. 공시는 "strategic decision to focus on its core business"라고만 적는다 `[공시 확인]`(10-K:5050).

### 6.7. 두 번째 질문에 대한 답

이 절은 세 답의 결론을 모으고 내 판단을 더한 것이다.

- **헐값이었나.** 전부는 아니다. 크게 손해를 본 것은 Poloniex 하나이고, 그 손해는 팔 때의 값보다 살 때의 값에서 나왔다. Trade는 받은 돈이 작지만 넘긴 것도 고객 관계와 상표뿐이었다. Invest는 원래 작았다. Pay는 판 것이 아니다. SeedInvest는 4년 뒤에 이익을 내고 팔았다.
- **어차피 안 될 것을 알아서였나.** Poloniex는 그렇다. 미국 회사가 그 거래소를 운영할 수 없다는 것을 회사가 글로 밝혔다. Trade는 아니다. Pay는 절반쯤 그렇다: 수요는 확인했지만 그 방식으로는 기존 금융망에서 벗어날 수 없다는 것을 배웠다. SeedInvest는 뒤늦게 그렇게 되었다.
- **왜 서둘렀나.** 회사가 위태로웠기 때문이다(5.4절(생존 쪽)). 값을 지키는 것보다 돈이 새는 곳, 규제에 걸리는 곳, 사람이 많이 드는 곳을 빨리 닫는 것이 급했다.
- Grok의 문장이 이 장을 가장 잘 줄인다: "2018년에는 모든 크립토 금융을 한 회사에 넣으려 했고, 2019년에는 그 포트폴리오가 현금, 규제, 브랜드를 동시에 잠식한다는 것을 배웠다. 배운 뒤에는 가격을 지키기보다 생존과 라이선스 정체성을 지켰다."원문 그대로
- 내가 덧붙이는 것 `[내 판단]`: 질문은 "굳이 헐값에 팔고 간 것도 이상함"이었다. 이상하게 보이는 까닭은 지금의 Circle(시가총액 200억 달러대, 분기 매출 7억 달러)을 기준으로 2019년의 결정을 보기 때문이다. 2019년의 Circle은 한 해에 8,000만 달러를 잃고 새 투자를 받지 못하던 회사였다. 그 회사에게 3,500만 달러의 현금과 인력 300명 남짓의 비용 절감은 작은 것이 아니었다.

```text
판 사업에서 받은 것 (막대 한 칸은 200만 달러)

Poloniex        현금 3,315만 달러                       #################
Circle Trade    현금 190만 + 주식 165만 달러            ##
Circle Invest   계약 때 62.5만 달러                     #
                실제로 쥔 돈 약 2,610만 달러            #############

견줄 것         2019년 계속영업 영업손실 8,321만 달러   ##########################################
```

**도식: 받은 것의 크기.** 6.1절(답의 뼈대)의 검산과 6.2절(Poloniex), 6.3절(Circle Trade), 6.4절(Circle Invest)의 숫자를 막대로 놓았다 `[내 판단]`. Circle Invest의 첫 막대는 한 칸에 못 미치는 값을 한 칸으로 그렸다. SeedInvest는 받은 것이 상장되지 않은 회사의 주식 96만 주여서 넣지 않았다.

**이 장의 내용을 되풀이한 구간.** 읽었고 위에 적은 것 밖의 새 내용은 없다: chatgpt.md:205-209, grok.md:1662, grok.md:3363, chatgpt.md:4524-4528, chatgpt.md:217-219, claude.md:27, claude.md:303, chatgpt.md:221-223, claude.md:304, claude.md:577, chatgpt.md:211-215, claude.md:28, claude.md:178, grok.md:4639-4641.

## 7. 창업자와 초기 멤버는 지금 어디에 있나

### 7.1. "초기 멤버"를 어디까지로 볼 것인가

- 2013년에서 2014년의 첫 직원 명단은 공개 자료로 되살릴 수 없다. Circle은 2014년 초에 14명이었고 연말에 50명이 되었다는 것만 밝혔다(chatgpt.md:2329-2351) `[답의 주장]`. ChatGPT와 Grok이 이 한계를 먼저 적었다(grok.md:4649-4667, grok.md:3354).
- 그래서 세 답이 본 것은 창업자 둘, 2013년부터의 이사, 그리고 이름이 확인되는 초기 임원이다. 초기의 엔지니어와 제품 담당자 개인은 공개 자료에 거의 없다(grok.md:1883-1919).
- 범위에 따라 답이 달라진다. ChatGPT가 나눈 표가 이것을 가장 분명하게 보여 준다(chatgpt.md:3045-3140).

  | 범위 | 지금 남은 사람 |
  |---|---|
  | 공동창업자 | Jeremy Allaire뿐 |
  | 2013년의 이사회까지 | M. Michele Burns도 |
  | 2016년까지의 임원 | Elisabeth Carpenter도 |

  표의 한 행은 범위 하나다.

### 7.2. 사람마다의 현황

| 사람 | 처음의 역할 | 2026년 9월 29일 기준 | 근거 |
|---|---|---|---|
| Jeremy Allaire | 공동창업자, CEO | CEO이자 이사회 의장 | `[공시 확인]` 10-K:8527 |
| Sean Neville | 공동창업자, CTO와 사장, 뒤에 공동 CEO. 2016년부터 이사 | 2019년 12월에 경영에서 물러남. 2026년 9월 25일에 이사 사임. Catena Labs 창업 | 2019년은 `[Circle 글 확인]` 블로그 focus-2020:55. 2016년 5월부터 이사, 2013년 8월부터 2019년 12월까지 CTO와 사장은 `[공시 확인]` 주총자료:349. 2026년의 사임은 `[공시 확인]` 8-K(2026-09-25):45 |
| Rajeev Date | 2013년 10월부터 이사, 2024년 11월부터 선임 사외이사 | 2026년 6월 12일에 사임 | 선임 사외이사였다는 것은 `[공시 확인]` 10-K:8365, 10-K:8531. 사임은 `[공시 확인]` 8-K(2026-06-12):45 |
| M. Michele Burns | 2013년 12월부터 이사 | 이사로 남아 있다 | 2026년 3월에 이사라는 것은 `[공시 확인]` 10-K:8533. 취임한 때는 `[공시 확인]` 주총자료:356 |
| Elisabeth Carpenter | 2016년 6월 6일쯤 최고인사책임자로 입사, 뒤에 약 9년 COO | 2025년 1월부터 Chief Strategic Engagement Officer | `[답의 주장]` chatgpt.md:3045-3140, claude.md:521-524 |
| John Beccia | 2014년의 법무 책임자, 준법 책임자 | 오래전에 떠남. 규제 자문사 FS Vector의 공동창업자 | `[답의 주장]` chatgpt.md:2329-2351 |
| Paul Camp | 2014년의 CFO | 2017년 앞뒤에 떠남. 뒤에 HSBC, BNY Mellon | `[답의 주장]` chatgpt.md:2329-2351 |
| Josh Hawkins | 초기의 마케팅 핵심 인력 | 2025년에 떠나 Aleo로 | `[답의 주장]` chatgpt.md:2329-2351 |
| Naeem Ishaq | CFO. 재임 기간을 2017년에서 2019년으로 적은 것은 ChatGPT이고(chatgpt.md:2342) Circle의 글에는 기간이 없다 `[답의 주장]` | 2019년 12월에 떠남 | 직책과 떠난 것만 `[Circle 글 확인]` 블로그 focus-2020:57 |
| Gus Coldebella | 2019년의 최고법무책임자 | 2019년 12월에 떠남. 자문은 계속 | `[Circle 글 확인]` 블로그 focus-2020:57 |
| Jeremy Fox-Geen | 2021년 5월부터 CFO. 초기 멤버가 아니다 | 2026년 12월 31일까지 남기로 하고 사임을 알림 | 2026년 8월에 CFO라는 것은 `[공시 확인]` 10-Q2:3053-3054. 사임은 `[공시 확인]` 8-K(2026-09-25):48 |

표의 한 행은 사람 하나다.

```text
                            2013  2015  2017  2019  2021  2023  2025
                            |     |     |     |     |     |     |
Allaire     CEO             =========================================>
Neville     CTO, 공동 CEO    ===================x
            이사                      ===============================x
Date        이사              ======================================x
Burns       이사              =======================================>
Carpenter   임원                      ===============================>
Ishaq       CFO                                 x
Coldebella  최고법무책임자                      x
Fox-Geen    CFO                                      ================o

=  그 자리에 있던 기간        >  2026년 9월 29일에도 그 자리에 있다
x  떠난 때                    o  2026년 12월 31일까지 남기로 하고 사임을 알렸다
```

**도식: 사람마다 있던 기간.** 위 표에 온 때나 떠난 때가 달까지 적힌 사람을 그렸다. 글자 세 칸이 한 해이고, 막대의 시작과 끝은 넉 달 단위로 어림한 자리다. Allaire의 막대는 회사를 세운 2013년부터 그렸다. Ishaq과 Coldebella는 표에 온 때가 없어서 떠난 때만 표시했다. Beccia, Camp, Hawkins는 표에 시작과 끝의 달이 없어서 그리지 않았다. ChatGPT는 사람마다 한 줄씩 선으로 이은 그림을 그렸고(chatgpt.md:3404-3419), 해를 눈금으로 놓은 것은 내가 한 것이다.

- 2026년의 사임 셋(Date, Neville, Fox-Geen)은 2분기 10-Q의 본문에 나오지 않는다(검색: `grep -n -i -E 'Lead Independent|resign' web-circle-q2-2026-10q.md`, 0건). 세 답이 근거로 든 8-K를 2026-09-29에 받아 대조했고, 세 사임 모두 8-K에 있다 `[공시 확인]`(8-K(2026-06-12):45-48, 8-K(2026-09-25):45-49).
- 10-K에 서명한 이사는 여덟이고 서명란에 적힌 날짜는 2026년 3월 6일이다 `[공시 확인]`(10-K:8523-8537). 회사 이름으로 CFO가 서명한 날짜는 3월 9일이다(10-K:8517). 서명한 이사: Allaire, Date, Craig Broderick, Burns, Bradley Horowitz, Neville, Danita Ostling, Adam Selipsky. 세 답은 Date의 사임으로 이사회가 9명에서 8명이 되었다고 썼다(claude.md:419, chatgpt.md:4017-4048). 나는 3월에 서명한 이사가 8명인 것과 맞지 않는다고 적었었는데, 8-K로 풀린다 `[공시 확인]`. 이사회는 2026년 3월 16일에 정원을 9명으로 늘리고 Kirk Koenigsbauer(Microsoft의 Experiences and Devices 부문 사장 겸 COO)를 이사로 뽑았다(8-K(2026-03-17):44-47). 10-K의 서명일(3월 6일)보다 열흘 뒤다. 세 답은 이 사람을 말하지 않았다.
- 이사회 인원의 변화를 공시로 이으면 다음과 같다 `[공시 확인]`.

  | 날짜 | 일 | 뒤의 인원 | 근거 |
  |---|---|---|---|
  | 2025년 7월 21일 | Adam Selipsky(전 Amazon Web Services CEO)를 뽑음 | 9 | 8-K(2025-07-22):45-48 |
  | 2025년 9월 17일 | David Orfao 사임 | 8 | 8-K(2025-09-19):44-45 |
  | 2026년 3월 16일 | Kirk Koenigsbauer를 뽑음 | 9 | 8-K(2026-03-17):44 |
  | 2026년 6월 12일 | Rajeev Date 사임 | 8 | 8-K(2026-06-12):45-46 |
  | 2026년 9월 25일 | Sean Neville 사임 | 7 | 8-K(2026-09-25):45-46 |

  표의 한 행은 일 하나다. 세 답은 2026년의 두 사임만 세었다. 1년 남짓 사이에 이사 셋이 나가고 둘이 들어왔으며, 들어온 둘은 모두 큰 기술 회사의 경영자다. 회사가 8-K에서 되풀이한 "orderly process of Board refreshment"라는 말은 이 흐름과 맞는다 `[내 판단]`.

```text
2025년 7월 21일   9명   #########   Selipsky가 들어옴
2025년 9월 17일   8명   ########    Orfao가 나감
2026년 3월 16일   9명   #########   Koenigsbauer가 들어옴
2026년 6월 12일   8명   ########    Date가 나감
2026년 9월 25일   7명   #######     Neville이 나감
```

**도식: 이사회 인원의 변화.** 위 표를 막대로 놓았다. 세 답은 이것을 그리지 않았다.
- 2026년 5월 14일의 주주총회에서 Allaire, Broderick, Neville이 2029년까지의 이사로 다시 뽑혔다 `[공시 확인]`(8-K(2026-05-18):46, 8-K(2026-05-18):53-56). 곧 Neville은 3년 임기로 다시 뽑힌 지 넉 달 남짓 만에 사임했다. 반대표는 Allaire 444.7만, Broderick 415.1만, Neville 1,508.9만 표로 Neville이 셋 가운데 가장 많았다. 세 답에 없다.
- ChatGPT만 Beccia, Camp, Hawkins를 따라갔다. Grok은 쓸모 있지만 첫 14명의 운명을 대표하지는 않는다고 평가했다(grok.md:3370). Claude는 Beccia와 Camp의 경력을 확인하지 못했다고 남겼다(claude.md:440).
- Carpenter는 Allaire의 앞 회사 Brightcove에서 수석 부사장이었다(claude.md:521-524) `[답의 주장]`. 창업자와 오래 함께한 사람이다.
- Date의 뒤를 이어 Craig Broderick이 선임 사외이사가 되었다(chatgpt.md:2355-2392) `[공시 확인]`(8-K(2026-06-12):48).
- Burns가 2013년 12월부터 이사였다는 것은 ChatGPT가 주주총회 자료를 근거로 썼다(chatgpt.md:3045-3140). Claude는 2021년의 SPAC 서류에서 Burns가 이사 명단에 있는 것까지만 확인했다고 남겼고(claude.md:428), Grok은 여러 이사 소개가 2013년을 가리키므로 Claude가 지나치게 조심했다고 적었다(grok.md:4391-4423). 주주총회 자료의 글은 "Michele Burns has served as a member of our Board since December 2013"이다 `[공시 확인]`(주총자료:356). ChatGPT가 맞다.

**지금의 경영진.** Grok이 가장 자세히 적었다(grok.md:1883-1919). 전체가 `[답의 주장]`이다.

| 이름 | 자리 | 온 때와 배경 |
|---|---|---|
| Jeremy Allaire | CEO, 의장 | 창업자 |
| Heath Tarbert | 사장(2025년 1월부터). 그 앞은 최고법무책임자(2023년 7월부터) | 전 상품선물거래위원회(CFTC) 의장 |
| Jeremy Fox-Geen | CFO | 2021년 5월 |
| Nikhil Chandhok | 최고제품기술책임자 | 2022년 2월 |
| Dante Disparte | 최고전략책임자, 정책 | 뒤에 영입 |
| Li Fan | Chief Technology and AI Officer | 뒤에 영입 |
| Kash Razzaghi | 최고영업책임자 | 뒤에 영입 |
| Elisabeth Carpenter | Chief Strategic Engagement Officer | 2016년 6월 |

표의 한 행은 사람 하나다.

- 10-K의 첨부 목록에 Fox-Geen, Razzaghi, Tarbert, Chandhok의 채용 제안서가 있다 `[공시 확인]`(10-K:8439-8442). 네 사람이 임원이라는 것은 이것으로 받쳐진다.
- Grok의 읽기: 지금의 Circle은 창업자 한 사람과 규제, 제품의 전문 경영진이다. 몇 해 동안 Meta의 스테이블코인 계획(Novi, Diem)에서 온 사람과 규제, 금융 출신을 많이 넣었다(grok.md:1883-1919).

**이 주제에서 가장 크게 고쳐진 것.**

- Claude는 2회차에 "2013~2016년에 합류한 다른 초기 직원 중 지금도 Circle에 있는 사람은 확인하지 못했습니다. 현 경영진은 전원 2021년 이후에 합류했습니다. 사실상 **2020년에 조직을 재건한 "두 번째 Circle"**입니다."[원문 그대로]라고 썼다(claude.md:326-338).
- ChatGPT가 Carpenter와 Burns를 들어 틀렸다고 지적했다(chatgpt.md:3045-3140). Carpenter는 SEC에 있는 채용 계약으로 2016년 6월 6일 입사가 확인된다고 했다.
- Claude는 받아들였다. 자신이 2회차에 본 경영진 명단에 Carpenter가 이미 있었는데 입사한 때를 확인하지 않았다고 했다(claude.md:521-524). Grok도 Claude의 문장이 명백히 틀렸다고 확인했다(grok.md:4377-4378).
- Claude가 덧붙인 단서가 중요하다: Carpenter는 2025년에 COO에서 대외 관계를 맡는 자리로 옮겼다. 그래서 "**운영 라인의 초기 인력 연속성은 2025년에 약해졌다**"[원문 그대로]고 보는 편이 정확하다(claude.md:521-524). Claude는 이것을 추론이라고 밝혔다.
- 세 답의 마지막 문장: 창업 경영자는 Allaire 한 사람이 맞다. 그러나 초기의 사람이 모두 사라졌다는 것은 과장이다(grok.md:4649-4667, chatgpt.md:3906-3930, claude.md:793).
- 내가 덧붙이는 읽기 `[내 판단]`: 남은 세 사람의 자리를 보면 Claude의 단서가 더 무겁다. Allaire는 경영을 하고, Burns는 사외이사이고, Carpenter는 2025년부터 운영을 맡지 않는다. 날마다 회사를 움직이는 자리에 2019년 앞부터 있던 사람은 Allaire뿐이다. ChatGPT가 Claude의 문장을 바로잡은 것은 사실로는 옳고, Claude의 처음 직관(조직이 한 번 새로 지어졌다)은 운영의 면에서는 크게 틀리지 않았다.

### 7.3. 2019년에 나간 사람들

- 2019년 12월 18일의 글에서 세 사람의 퇴장을 함께 알렸다 `[Circle 글 확인]`(블로그 focus-2020:55-57).
  - Neville: "I (Sean) determined that these successful business changes make the timing appropriate to exit my co-CEO management position, though I will remain connected to the company as an independent director on the Circle Board of Directors ... This will be my final blog post co-authored with Jeremy."
  - Ishaq와 Coldebella: "our Chief Financial Officer Naeem Ishaq and Chief Legal Officer Gus Coldebella are also transitioning from the company into new adventures befitting their expertise. Gus will continue to advise the company on a number of important government relations issues."
- ChatGPT와 Grok이 옮긴 내용이 원문과 맞는다(chatgpt.md:2396-2437, grok.md:1883-1919).
- Neville은 같은 글에서 CENTRE를 통해 일을 이어 가겠다고 했다 `[Circle 글 확인]`: "I also expect to propel the mission forward through CENTRE and other new complementary paths"(블로그 focus-2020:55). Grok이 Centre와 한동안 이어져 있었다고 쓴 것(grok.md:1883-1919)이 이것이다.
- Poloniex와 함께 직원 80명 넘게가 옮겼다 `[Circle 글 확인]`(블로그 focus-2020:53).
- 세 답의 읽기: 이때의 이탈은 옛 사업 모델을 해체한 것이다. 거래소, 장외거래, Pay를 버리면 그 사업을 맡던 CFO, 법무 책임자, 거래소 인력이 함께 빠지는 것이 자연스럽다(grok.md:1883-1919). ChatGPT는 있던 조직을 해체하고 새 Circle을 만드는 수준의 구조조정이었고, 그때 누가 문제가 있다고 보았다면 합리적인 판단이었을 것이라고 적었다(chatgpt.md:2470-2664).

### 7.4. 2026년에 나간 사람들

이 절의 사실은 세 답이 8-K, Form 4, 보도자료에서 가져왔다고 밝힌 것이다. 2026-09-29에 8-K 둘과 Neville의 Form 4를 받아 대조했고, 아래에서 `[공시 확인]`이 붙은 것이 그 결과다. 보도자료의 인용과 주가는 대조하지 않았다.

**Rajeev Date, 6월 12일.**

- 2013년 10월부터 이사였고 선임 사외이사였다. 회사는 개인 사유, 질서 있는 이사회 교체, 이견 없음이라고 공시했다(chatgpt.md:2355-2392). 8-K의 글과 같다 `[공시 확인]`: "for personal reasons ... part of an orderly process of Board refreshment, and not due to any disagreement with the operations, policies or practices of the Company"(8-K(2026-06-12):45).
- Claude와 Grok은 2회차에 Date를 빠뜨렸고, ChatGPT가 넣었다. 두 답 모두 빠진 사실이 해석을 바꾼다고 받아들였다(claude.md:419, grok.md:3339).
- 공시에서 더하는 것 `[공시 확인]`: Date는 2025년 12월 9일에 Class A 45,833주까지 파는 계획(Rule 10b5-1)을 세웠고 기한은 2027년 3월 5일이다(10-K:8365-8368). Burns도 같은 날 50,000주까지 파는 계획을 세웠고 기한은 2026년 8월 31일이다(10-K:8361-8364). 곧 남은 이사 Burns도 주식을 팔고 있다. 세 답은 Burns의 매도를 Grok이 한 줄로만 스쳤다(grok.md:4377-4378).

**Sean Neville, 9월 25일.**

- 개인 사유로 즉시 사임했다. 회사는 이사회 교체이고 운영, 정책, 관행에 대한 이견이 없다고 밝혔다. 이사회는 8명에서 7명이 되었다(claude.md:340-344, grok.md:1921-1928) `[공시 확인]`(8-K(2026-09-25):45-46). Date의 8-K와 문장이 거의 같다.
- 5월에 받은 확정 전의 RSU 2,018주는 사임과 함께 대가 없이 몰수되었다(claude.md:461-462, chatgpt.md:3934-4013) `[공시 확인]`(Form4:332).
- 실제로 경영에서 떠난 것은 2019년이다. 2026년은 남아 있던 이사회의 자리가 끝난 것이다(chatgpt.md:2396-2437, chatgpt.md:3144-3173, grok.md:1883-1919).
- 사임의 실제 까닭은 알 수 없다. 공시에 있는 것은 개인 사유뿐이다(claude.md:584).
- 이미 다른 회사 Catena Labs의 창업자이자 CEO였다(chatgpt.md:2396-2437) `[공시 확인]`(주총자료:349). Claude는 이 회사를 AI 네이티브 은행이라고 적었다(claude.md:326-338).
- **공시에서 더하는 것** `[공시 확인]`(10-K:4757-4759, 10-K:4764-4769). 세 답에 없다.
  - Circle은 2022년 11월 7일에 어느 신생 회사에 30만 달러를 투자했고, Neville이 그 회사의 창업자이자 CEO이며 지분 40%를 가지고 있다. 공시는 회사의 이름을 적지 않고 "a startup focused on consumer interaction with the digital economy"라고만 적는다. 지금의 이사 Bradley Horowitz도 그 회사의 소수 투자자다.
  - Circle은 2025년에 Neville의 성인 자녀를 임원이 아닌 자리에 고용했고 보수는 12만 달러가 넘는다.
  - 이 신생 회사가 Catena Labs인지는 공시만으로는 알 수 없다 `[내 판단]`. 맞다면 Circle은 Neville의 회사의 주주이기도 하다.

**Jeremy Fox-Geen, 9월 25일에 알림.**

- 2021년 5월에 CFO로 와서 재무 조직을 세우고 IPO를 맡았다(chatgpt.md:2470-2664).
- 바로 떠나지 않는다. 후임이 정해지거나 2026년 12월 31일이 될 때까지 CFO로 남는다. 회사는 외부의 임원 채용 회사를 써서 후임을 찾고 있다. 이견 때문이 아니라고 공시했다(chatgpt.md:2470-2664, grok.md:1921-1928) `[공시 확인]`(8-K(2026-09-25):48).
- 본인은 여러 목표를 이뤘으니 쉬었다가 다음을 시작하겠다고 했다(claude.md:340-344).
- 조건(chatgpt.md:3177-3194, grok.md:1921-1928). 아래 다섯이 모두 8-K에 있다 `[공시 확인]`(8-K(2026-09-25):49):
  - 연봉 50만 달러, 2026년 성과급 목표 110%.
  - 퇴임 뒤 현금 105만 달러.
  - RSU 2개월 추가 확정.
  - 옵션 행사 기간 12개월 연장.
  - 12개월 경쟁 회사 취업 금지, 24개월 직원 빼 가기 금지.
- Claude는 연봉, 성과급 목표, RSU 추가 확정을 확인하지 못했다고 남겼다(claude.md:554). 105만 달러와 12개월 취업 금지는 세 답이 모두 썼다. Claude가 확인하지 못한 셋도 8-K에 있으므로 ChatGPT와 Grok이 쓴 것이 맞다. 105만 달러는 취업 금지 같은 약속을 지키고 회사에 대한 청구를 포기하는 대가이고, 사임한 날부터 12개월 동안 달마다 나눠 준다.
- 발표한 날 주가는 4.1% 내려 89달러로 끝났다(claude.md:340-344).
- 1회차에 이 사임을 쓴 것은 Claude뿐이고 검색 결과의 제목으로만 확인했다고 밝혔다(claude.md:20). Grok은 교차 회차에서 Circle의 공식 보도로 확인된다고 적었다(grok.md:1650).
- 공시에서 더하는 것 `[공시 확인]`: Circle은 2022년 10월 7일에 대출 서류를 디지털 자료로 바꾸는 신생 회사의 시리즈 A에 30만 달러를 투자했고, Fox-Geen은 그 회사의 창업자이자 CEO의 동거 배우자다(10-K:4770-4773). 금액이 작고 사임과 이어진다는 근거는 없다.

**같은 날이라는 것.**

- Neville의 사임과 Fox-Geen의 사임은 같은 날 공시되었다. 8-K는 둘을 하나의 인과로 묶지 않는다(grok.md:1921-1928) `[공시 확인]`: 한 8-K의 같은 항목(5.02) 안에 두 문단으로 따로 적혀 있고, 보도자료는 Fox-Geen의 것만 냈다(8-K(2026-09-25):45-51).
- 같은 날 창업 이사와 IPO를 맡은 CFO가 함께 공시되면 시장은 이야기를 하나로 읽는다(grok.md:1932-1973 뒤의 대목, 묶음 8번 주제).
- 회사의 "이견 없음"은 공식 설명이고, 내부에 갈등이 없다는 독립된 증명은 아니다(chatgpt.md:2470-2664). Grok은 이 문장이 미국 공시의 관용구이지만, 이견이 있으면 그렇게 써야 하는 자리에서 쓰지 않았다는 것은 최소한의 정보라고 읽었다.

```text
2026년
  |  3월 16일    이사회 정원을 9명으로 늘리고 Koenigsbauer를 뽑음
  |  5월 14일    주주총회: Allaire, Broderick, Neville을 2029년까지의 이사로 다시 뽑음
  |  6월 8일     Neville이 옵션을 모두 행사하고 1,034,396주를 팖
  |  6월 12일    Date 사임. Broderick이 선임 사외이사가 됨
  |  7월 9일     연방 신탁은행 최종 승인
  |  9월 16일    Arc 공개 메인넷
  |  9월 17일    Binance와 계약 (9월 22일 공개)
  |  9월 25일    Neville 이사 사임. Fox-Geen이 사임을 알림
  |  12월 31일   Fox-Geen이 CFO로 남기로 한 마지막 날
```

**도식: 2026년의 순서.** 7.2절(사람마다의 현황), 7.5절(지분과 의결권), 3.5절(Binance와의 계약), 3.6절(규제 인가), 4.5절(블록체인: Arc), 4.6절(네트워크 토큰: ARC)의 날짜를 한 줄에 놓았다. 나란히 놓은 것이 인과를 뜻하지는 않는다 `[내 판단]`. ChatGPT는 세 사람의 퇴장만 그렸다(chatgpt.md:4024-4035).

### 7.5. 지분과 의결권

**Class B의 구조.**

- Class A는 1주에 1표, Class B는 1주에 5표다. 다만 Class B 전체의 의결권은 회사 전체 의결권의 30%를 넘을 수 없다. Class C는 의결권이 없다 `[공시 확인]`(10-K:2517-2519).
- 2025년 12월 31일 기준으로 공동창업자와 그 관계 법인이 가진 의결권은 약 29.6%다 `[공시 확인]`(10-K:2521).
- Class B는 가진 사람이 원하면 Class A로 1:1로 바꿀 수 있고, 정관이 허락한 경우 말고는 남에게 넘기면 저절로 Class A가 된다 `[공시 확인]`(10-K:5836-5838).
- **저절로 바뀌는 조건.** Claude는 Allaire가 CEO와 의장을 모두 내려놓으면 Class B가 일반주로 바뀐다고 적었고(claude.md:461-462, claude.md:655), ChatGPT는 조건이 더 있다고 적었다(chatgpt.md:3934-4013): Allaire가 가진 Class B가 처음의 50% 밑으로 내려갈 때, Allaire가 CEO도 의장도 아닐 때, 효력 발생 뒤 5년이 지났을 때 가운데 가장 빠른 때다. 정관으로 확인했다 `[공시 확인]`(정관:53). ChatGPT가 든 셋이 모두 있고, Claude가 든 것은 그 가운데 하나다. 정관의 조건은 여섯이고 가장 이른 것이 적용된다: (1) 허락된 이전이 아닌 이전, (2) 주식을 가진 신탁이나 법인이 Allaire나 Neville의 것이 아니게 될 때, (3) Class B 주주 과반의 찬성, (4) Allaire 쪽이 가진 Class B가 효력 발생일의 50% 밑으로 내려간 첫날, (5) "the first day on which Jeremy Allaire is neither the Chief Executive Officer of the Corporation nor the Chairperson of the Board", (6) "the date that is five years after the day of the Effective Time". (4)에서 (6)은 Neville의 것을 포함한 Class B 전부에 적용된다. 효력 발생일은 상장 때이므로 5년의 기한은 2030년 6월쯤이다 `[내 판단]`.
- ChatGPT의 읽기: 힘이 Allaire에게 몰려 있는 것은 맞지만, 기한 없이 이어지는 강한 차등의결권 구조는 아니다. 5년의 기한이 지배구조의 위험을 덜어 준다(chatgpt.md:3934-4013).
- Claude의 읽기: Neville이 떠나면서 창업자의 의결권은 사실상 Allaire 한 사람에게 모였고, 이 장치가 Allaire 개인에게 묶여 있다. 핵심 인물 위험의 구체적인 모양이다(claude.md:461-462).
- 검산 `[내 판단]`: 2026년 3월 5일의 발행 주식(Class A 228,100,955주, Class B 18,714,651주, 10-K:76)으로 계산하면 Class B의 의결권은 18,714,651 x 5 = 93,573,255표이고, 전체는 228,100,955 + 93,573,255 = 321,674,210표다. 93,573,255 / 321,674,210 = 29.1%. 30%의 상한 바로 밑이다. Class B가 조금만 더 있었다면 상한에 걸렸을 것이므로, 상한은 이름만 있는 조항이 아니다.

```text
Class A   1주에 1표     228,100,955주     228,100,955표     70.9%
Class B   1주에 5표     18,714,651주      93,573,255표      29.1%  (상한 30%)
Class C   의결권 없음   0주
                                          --------------
                                          321,674,210표

의결권 (한 칸은 2%)
  Class A   ###################################   70.9%
  Class B   ###############                       29.1%

Class B가 저절로 Class A로 바뀌는 때 (정관의 여섯 조건 가운데 ChatGPT가 든 셋, 가장 이른 것이 적용된다)
  +-- Allaire가 가진 Class B가 처음의 50% 밑으로 내려갈 때
  +-- Allaire가 CEO도 의장도 아닐 때
  +-- 효력 발생 뒤 5년이 지났을 때
```

**도식: 의결권의 셈과 Class B가 끝나는 조건.** 위 항목과 검산을 옮겼다. 70.9%는 100에서 29.1%를 뺀 내 셈이다. ChatGPT가 조건을 나무 모양으로 그렸다(chatgpt.md:3962-3972).

**Allaire.**

- 2026년 3월 16일 기준으로 Class B 17,708,642주, Class B의 79.8%, 전체 의결권의 23.9%(chatgpt.md:2668-2702, claude.md:437-438, grok.md:4649-4667) `[공시 확인]`(주총자료:1902). 이 숫자는 실질 소유 기준이고 네 조각의 합이다(주총자료:1925-1929): 본인이 가진 15,859,769주, 60일 안에 확정될 RSU 30,388주, 60일 안에 행사할 수 있는 옵션 1,482,801주, 신탁이 가진 335,684주. 곧 실제로 발행된 주식은 16,195,453주다(15,859,769 + 335,684).
- ChatGPT의 읽기: 창업 초기와 지금을 잇는 사람은 Allaire다. 비트코인, Circle Pay, Poloniex, USDC, SPAC 시도, IPO, CPN, Arc를 모두 같은 사람이 이끌었다. 창업자가 빠지고 전문 경영인이 맡은 회사가 아니다(chatgpt.md:2668-2702).
- 공시도 Allaire를 이름으로 든다 `[공시 확인]`: "our future success is highly dependent on the talents and contributions of our senior management team, including Jeremy Allaire, our co-founder, Chairman, and Chief Executive Officer"(10-K:2486-2488).

**Neville.**

- 2026년 3월 16일 기준으로 Class B 4,488,271주, Class B의 20.2%, 전체 의결권의 6.1%(chatgpt.md:2441-2466) `[공시 확인]`(주총자료:1912). 실질 소유 기준이고 세 조각의 합이다(주총자료:1951-1953): 본인이 가진 2,366,356주, 행사할 수 있는 옵션 1,969,073주, 신탁이 가진 152,842주.
- 9월 1일에 5만 주를 Class A로 바꿔 팔았고, 미리 정한 매도 계획(10b5-1)에 따른 것이다(chatgpt.md:2441-2466) `[공시 확인]`(Form4:310-313). 값은 주당 92.09달러다.
- 사임한 9월 25일의 Form 4 기준으로 직접 가진 Class B 3,015,909주, 신탁으로 가진 Class B 132,966주가 남아 있다(chatgpt.md:2441-2466, claude.md:437-438) `[공시 확인]`(Form4:324-332). 옵션은 남아 있지 않다.
- **떠나는 것인가 남는 것인가.** ChatGPT는 2회차에 이사회에서 나간 것이 지분을 모두 정리한 것은 아니므로 도망간다는 해석의 반대 증거라고 썼다(chatgpt.md:2441-2466). Claude는 절반만 맞다고 했다: 3월의 약 449만 주와 9월의 약 315만 주를 견주면 반년 사이에 약 30%가 줄었다(claude.md:443). 세 답의 마지막 입장은 두 사실을 함께 적는 것이다: 많이 남아 있고, 계획에 따라 줄이고 있다(chatgpt.md:3934-4013, grok.md:3346-3347).
- 검산: 3,015,909 + 132,966 = 3,148,875주. 주주총회 자료의 정확한 수로 다시 하면 4,488,271 - 3,148,875 = 1,339,396주가 줄었고 1,339,396 / 4,488,271 = 29.8%다. 약 30%가 줄었다는 Claude의 계산과 맞는다. Claude와 Grok은 이것이 두 자료를 산술로 견준 추론이라고 밝혔다(claude.md:443, grok.md:4389).
- Grok은 "2026년 내내 10b5-1로 꾸준히 매도"라고 썼고(grok.md:3346-3347, grok.md:4649-4667), Claude는 과장이라고 지적했다: 확인된 매도는 9월 1일의 한 건이다(claude.md:565). **Form 4로 보면 Grok이 맞고 Claude의 지적이 틀렸다** `[공시와 다름]`. Neville은 2026년에 열 날에 걸쳐 팔았다: 2월 26일, 3월 2일, 4월 1일, 5월 1일, 6월 1일, 6월 8일, 6월 9일, 7월 1일, 8월 3일, 9월 1일(Form4:120-313). 거의 달마다 한 번이고, 2025년 12월부터는 매도가 있는 보고서에 모두 10b5-1 계획에 따른 거래라는 표시가 있다. 매도가 없는 보고서 넷(2026년 1월 6일, 5월 15일, 5월 18일, 9월 25일)에는 표시가 없다.
- **내가 찾은 어긋남과 그 답.** 세 답이 든 3월의 숫자를 더하면 Class B의 발행 주식 18,714,651주(10-K:76)보다 348만 주 많다는 점을 앞서 적었고, 주주총회 자료의 숫자가 옵션과 RSU를 넣은 것일 수 있다고 짐작했다. 주주총회 자료로 확인했다 `[공시 확인]`: 두 사람의 합은 22,196,913주이고(17,708,642 + 4,488,271. 이사와 임원 14명 전체의 Class B 합계 줄에도 같은 수가 있다, 주총자료:1916), 그 가운데 옵션과 RSU가 3,482,262주다(30,388 + 1,482,801 + 1,969,073). 22,196,913 - 3,482,262 = 18,714,651로 발행 주식 수와 꼭 맞는다. 표의 비율(79.8%와 20.2%)은 두 사람의 실질 소유를 더한 수로 나눈 값이다(17,708,642 / 22,196,913 = 79.8%, 4,488,271 / 22,196,913 = 20.2%). 발행 주식으로 나눈 비율이 아니다. 이 문단의 나눗셈은 내가 했고 검증 에이전트는 거치지 않았다.
- **"30%가 줄었다"는 비교는 같은 것끼리의 비교다.** 나는 3월의 숫자(옵션 포함)와 9월의 숫자(실제 주식)를 견준 것이 서로 다른 것을 견준 계산일 수 있다고 적었는데, 틀렸다 `[내 판단]`. 9월에는 옵션이 하나도 남아 있지 않아서 9월의 실질 소유와 실제 보유가 같다. 줄어든 1,339,396주는 3월 17일부터 9월 25일 사이에 판 주식의 합과 꼭 같다 `[공시 확인]`(Form4:337).
- **그 30%의 대부분은 하루에 팔렸고, 이유가 공시에 있다** `[공시 확인]`. 6월 8일에 Neville은 옵션 1,879,073주를 모두 행사하고(행사가 0.08달러, Form4:244) 그 가운데 1,034,396주를 팔았다(Form4:237-247, Form4:338). 각주는 이렇게 적는다: "to facilitate a sale, pursuant to a 10b5-1 trading plan, to cover tax withholding obligations on expiring stock options"(Form4:248). 곧 만기가 다가온 옵션을 행사하면서 세금을 낼 만큼을 판 것이다. 그 결과 실제로 가진 Class B는 3월의 2,519,198주(2,366,356 + 152,842)에서 9월의 3,148,875주로 오히려 늘었다.
- 상장 뒤 전체로는 열네 날에 2,738,339주를 팔았고 주식 수에 값을 곱한 합은 약 1.856억 달러다(Form4:339). 이 합에는 Neville이 실질 소유를 부인하는 가족 신탁(Calico Trust)의 매도 33,569주가 들어 있고(Form4:66), 그것을 빼면 2,704,770주다(2,738,339 - 33,569). 상장일의 100만 주(주당 29.30달러)와 2025년 8월 후속 공모 때의 260,374주(주당 127.075달러)가 들어 있다(Form4:34, Form4:54).
- 내 읽기 `[내 판단]`: 세 답의 마지막 입장(많이 남아 있고, 계획에 따라 줄이고 있다)은 공시와 맞는다. 다만 세 답 모두 가장 큰 사실을 놓쳤다. 줄어든 30%의 77%(1,034,396 / 1,339,396)는 옵션의 만기와 세금 때문에 하루에 판 것이어서, 회사를 어떻게 보는지를 말해 주는 매도로 읽기 어렵다. 나머지는 달마다 3만 5천 주나 5만 주씩 판 것이다. 6월 8일은 Date가 사임하기 나흘 전인데, 미리 정한 계획에 따른 거래이므로 두 일을 이을 근거는 없다.

```text
Neville의 Class B 실질 소유

2026년 3월 16일   4,488,271주
      |             본인 2,366,356 + 옵션 1,969,073 + 신탁 152,842
      |
      |   1,339,396주가 줄었다 (29.8%)
      |     +-- 6월 8일 하루에 1,034,396주 (77%)
      |     |     만기가 다가온 옵션을 행사하면서 세금을 낼 만큼을 팔았다
      |     +-- 나머지 305,000주
      |           달마다 나눠 팔았다
      v
2026년 9월 25일   3,148,875주
                    본인 3,015,909 + 신탁 132,966. 옵션은 남아 있지 않다


Allaire의 Class B 실질 소유 (2026년 3월 16일)   17,708,642주
                    본인 15,859,769 + RSU 30,388 + 옵션 1,482,801 + 신탁 335,684
```

**도식: 줄어든 30%의 속.** 위 항목의 숫자를 옮겼다. 305,000주는 1,339,396에서 1,034,396을 뺀 내 셈이다. ChatGPT는 "도망갔다"와 "전혀 줄이지 않는다"를 둘 다 부정하는 그림을 그렸다(chatgpt.md:3999-4010).

**이 장의 내용을 되풀이한 구간.** 읽었고 위에 적은 것 밖의 새 내용은 없다: claude.md:542, claude.md:579, claude.md:580, grok.md:4380-4381, claude.md:794-797.

## 8. 초기 멤버의 이탈은 회사의 위기 신호인가

질문은 세 답의 의견을 물었다("너의 의겨도 들려주고"[원문 그대로], chatgpt.md:1844, claude.md:247, grok.md:1777). 그래서 이 장은 세 답의 판단을 먼저 적고 내 판단을 따로 적는다.

### 8.1. 일반론: 언제 이탈이 경고가 되는가

세 답이 각자 조건을 적었다. 합치면 다음과 같다(claude.md:346-370, grok.md:1932-1973, grok.md:4671-4691, chatgpt.md:2470-2664).

| 조건 | 누가 들었나 |
|---|---|
| 떠난 사람이 운영에 실제로 영향을 주는 자리였는가 | Claude |
| 여러 퇴장이 한꺼번에 몰렸는가. 창업자 여러 명이 경영과 이사회에서 함께 사라졌는가 | Claude, Grok |
| 절차가 갑작스러웠는가. 후임 계획 없이 바로 떠났는가 | Claude, Grok, ChatGPT |
| 실적 충격, 회계 문제, 규제 조사와 같은 때인가 | Grok, Claude |
| CFO가 감사 철 바로 앞에 떠났는가. 감사인과 갈등이 있는가. 재무제표를 고쳐 냈는가 | Grok, ChatGPT |
| 내부자가 크게 팔았는가 | Grok |
| 내부통제 문제가 함께 터졌는가 | ChatGPT |
| CFO나 회계 책임자가 잇달아 떠나는가 | ChatGPT |

표의 한 행은 조건 하나다.

- 회사의 나이와 단계를 보아야 한다. Circle은 13년 된 회사다. 13년 뒤에도 첫 10명에서 20명이 대부분 남아 있는 것이 오히려 드물다(chatgpt.md:2470-2664).
- 회사가 비상장 스타트업에서 가상자산 스타트업, 규제받는 핀테크, 세계적인 금융 인프라, 상장사로 바뀌면 필요한 경영진이 달라진다. 처음에는 가상자산 엔지니어, 소비자 앱 담당, 여러 일을 하는 사람이 필요했고 지금은 상장사의 CFO, 규제 전문가, 은행 경영자, 자본시장과 기관 영업의 인력이 필요하다(chatgpt.md:2470-2664).
- 상장 1, 2년 차의 회사가 창업 이사를 줄이고 사외이사를 늘리는 것은 흔한 지배구조 정비다(grok.md:1932-1973).
- **빼기로 한 일반론.** Claude와 Grok은 2회차에 IPO를 마친 CFO가 12개월에서 18개월 뒤에 떠나는 것은 흔하다고 썼다. Claude는 통계로 검증한 것이 아니라고 표시했다(claude.md:346-370). ChatGPT가 통계 근거가 없으니 빼자고 했고(chatgpt.md:3198-3226), Claude와 Grok이 받아들였다(claude.md:544, grok.md:4671-4691).

### 8.2. 2019년과 2026년은 다르다

Claude의 2회차 표에 Date를 더해 고쳤다(claude.md:346-370, claude.md:419).

| 견주는 것 | 2019년 12월 | 2026년 6월에서 9월 |
|---|---|---|
| 떠난 사람 | 공동 CEO, CFO, 최고법무책임자가 함께 | 이사 둘(Date, Neville)과 CFO 하나 |
| 절차 | 감원과 사업 매각이 함께 | 이사는 바로 사임, CFO는 석 달 인수인계와 후임 찾기 |
| 사업의 상태 | 점유율이 무너지고 자금 조달이 줄었다는 보도 | USDC 유통량 전년 대비 19% 증가, Arc 출시 |
| 운영에 미친 영향 | 핵심 경영진이 바뀜 | Neville은 2019년부터 운영에 없었다 |
| 세 답의 판정 | 강한 신호 | 주의(yellow flag) |

표의 한 행은 견주는 항목 하나다.

```text
2019년 12월                                 2026년 6월에서 9월

공동 CEO, CFO, 최고법무책임자가 함께        이사 둘(Date, Neville)과 CFO 하나
      +                                           +
감원과 사업 매각이 함께                     CFO는 석 달 인수인계와 후임 찾기
      +                                           +
핵심 경영진이 바뀜                          Neville은 2019년부터 운영에 없었다
      |                                           |
      v                                           v
강한 신호                                   주의(yellow flag)
```

**도식: 2019년과 2026년.** 위 표를 옮겼다. ChatGPT는 2019년에 물러난 세 사람을 따로 그렸다(chatgpt.md:2590-2593).

- 2019년은 강한 신호였다. 다만 그 위기의 실체는 회사가 죽는다가 아니라 옛 모델이 죽는다였고, 결과는 USDC 집중이었다(grok.md:1932-1973, grok.md:4671-4691).

### 8.3. 세 사람마다의 무게

ChatGPT가 2회차에 세기를 매겼다(chatgpt.md:2470-2664).

| 사건 | ChatGPT의 세기 | 이유 |
|---|---|---|
| Neville의 이사 사임 | 낮음에서 중간 | 7년 전에 경영에서 물러났다. 다른 회사를 운영한다. Class B를 여전히 많이 가지고 있다(9월 25일에 3,148,875주, Form4:324-332) |
| Date의 이사 사임 | 중간 밑 | 13년 일했다. 이사회 교체로 설명된다. 후임 선임 사외이사가 바로 정해졌다 |
| Fox-Geen의 CFO 퇴임 | 중간 | 지금의 핵심 임원이다. IPO 뒤 15개월이다. Arc와 CPN을 크게 넓히는 때다. 후임이 아직 없다 |
| 셋을 합쳐 | 주의(yellow flag) | |

표의 한 행은 사건 하나다. 빈 칸은 ChatGPT가 따로 이유를 적지 않았다는 뜻이다.

- 세 답이 모두 Neville보다 CFO가 더 중요하다고 보았다(chatgpt.md:2470-2664, claude.md:346-370, grok.md:4671-4691).
- **Neville에 관한 가설 하나.** Claude는 Neville의 Catena Labs가 AI 에이전트를 위한 금융을 내세우고 있어서 Circle의 Agent Stack과 영역이 겹치므로, 이해상충을 피하려는 정리일 수 있다고 썼다(확신도 낮음에서 중간, claude.md:346-370). Grok은 하나의 가설로 받았고(grok.md:3362), ChatGPT는 근거 없는 추론이니 최종 분석에 넣지 않겠다고 했다(chatgpt.md:3144-3173). Grok의 최종 답은 가능하지만 확정처럼 쓰지 않는다고 적었다(grok.md:4671-4691).
  - 내 읽기 `[내 판단]`: 7.4절(2026년에 나간 사람들)에서 공시로 본 것(Circle이 Neville이 세운 회사에 투자했고, 다른 이사도 그 회사의 투자자다)을 더하면 이 가설에 조금 더 무게가 실린다. 이사가 세운 회사와 회사의 제품이 겹치고 회사가 그 회사의 주주이기도 하면, 이사회에서 나오는 것이 자연스러운 정리다. 그래도 공시된 사유는 개인 사유뿐이고, 그 신생 회사가 Catena Labs인지도 확인하지 못했다.
- **Fox-Geen이 중요한 까닭.** Grok이 가장 구체적으로 적었다: Fox-Geen은 ARC 사전 판매의 매출 인식, 연방 신탁은행, 유통비용, 기타 매출 전망을 숫자로 설명하던 사람이다. 후임이 누구인가가 앞으로 두세 분기의 공시의 질을 가른다(grok.md:1932-1973 뒤의 대목, 묶음 8번 주제). Claude는 ARC 사전 판매 대금 약 1.8억 달러를 제품 단계에 따라 매출로 인식해야 하는 해에 CFO가 바뀐다는 것을 가장 구체적인 볼 거리로 꼽았다(claude.md:482-484, claude.md:586).

### 8.4. 세 답의 판정과 그것이 바뀐 과정

| 회차 | ChatGPT | Claude | Grok |
|---|---|---|---|
| 2회차 | 셋을 합쳐 주의. 위기라고 볼 직접 증거는 없다(chatgpt.md:2470-2664, chatgpt.md:2706-2765) | 위기 신호로 보지 않는다, 확신도 중간(claude.md:346-370) | 영업 위기의 앞 징조로 보기에는 근거가 약하다. 아무 일도 아닌 것도 아니다(grok.md:1932-1973) |
| 2회차 교차 1 | Neville은 낮은 신호, CFO는 중간의 볼 거리. 위기라는 결론은 근거 부족(chatgpt.md:3398-3445) | 한 단계 올려 주의, 확신도 중간(claude.md:482-484) | 2019년은 강한 신호, 2026년은 노란 깃발(grok.md:3421-3423) |
| 2회차 교차 2 | Claude의 주의가 알맞다(chatgpt.md:4017-4048) | 주의를 유지(claude.md:586) | 위기의 증거가 아니라 볼 것의 목록(grok.md:4437-4438) |
| 최종 | 묶음 8번 주제에 최종 답의 구간이 없다. 9장에서 본다 | 주의, 확신도 중간(claude.md:798) | 영업 위기의 앞 징조로 보기에는 근거가 약하다(grok.md:4671-4691) |

표의 한 행은 회차 하나다.

```text
          2회차           2회차 교차 1          2회차 교차 2        최종
ChatGPT   주의            -> 위기는 근거 부족   -> 주의가 알맞다    -> (구간 없음)
Claude    위기 아님       -> 주의               -> 주의             -> 주의
Grok      근거가 약하다   -> 노란 깃발          -> 볼 것의 목록     -> 근거가 약하다
```

**도식: 판정이 움직인 길.** 위 표를 줄였다. 세 답은 이것을 그리지 않았다.

- Claude가 판정을 올린 까닭은 둘이다: 석 달 사이에 초기 이사 두 사람이 떠났다는 것(Date를 뒤늦게 알았다), 그리고 CFO가 바뀌는 때가 ARC 대금의 매출 인식과 겹친다는 것(claude.md:482-484).
- ChatGPT는 처음에 위험을 조금 낮게 보았다가 Date, Neville, Fox-Geen을 시간 순으로 놓고 보니 주의가 알맞다고 했다. 석 달 사이에 초기의 이사 둘이 빠진 것은 지배구조의 교체라고 부를 만한 변화이지만 그것만으로 위기의 증거는 아니다(chatgpt.md:4017-4048).
- 세 답이 서로를 읽은 뒤에 같은 판정에 이르렀으므로, 이 일치는 독립된 세 의견이 아니다 `[내 판단]`. 2회차(서로 보기 전)의 세 판정은 "주의", "위기 아님", "근거가 약함"으로 조금씩 달랐다.

**가볍게 넘기기 어려운 점.** Grok과 Claude가 적었다(grok.md:1932-1973 뒤의 대목, claude.md:346-370).

- 창업자 쪽 사람이 경영과 이사회에서 모두 사라지고 결정이 한 사람에게 더 몰린다. Claude는 이번 퇴장보다 이 구조가 더 큰 위험이라고 했다.
- 금리가 내려 준비금 수익률이 떨어지고, Arc가 막 나왔고, 실적 전망을 고쳐야 하는 때에 재무 책임자가 바뀐다.
- Circle의 주가는 이미 금리, Coinbase 계약, Open USD 같은 경쟁에 민감하다. 지배구조 소식은 사업의 위기보다 할인율에 붙는다.

**위기 신호로 보기 어려운 점.** Grok이 적었다(grok.md:1932-1973 뒤의 대목).

- 회사는 상장사이고 USDC 유통량이 약 730억 달러, 분기 매출이 7억 달러대다.
- Fox-Geen은 바로 떠나지 않고 석 달 동안 인수인계한다.
- 8-K가 이견을 분명히 부정한다.
- Neville은 2019년부터 경영에 없었다.
- 같은 주 앞뒤에 Binance의 1억 달러 지분 참여와 5년 계약이 있었다. 밖의 유통 협력사가 지분을 사는 때와 겹친다. Claude도 같은 점을 들었다(claude.md:346-370).

**세 답이 함께 하는 말.** 위기를 찾고 싶다면 인사보다 먼저 볼 것이 있다: 준비금 수익률, USDC 유통량, Coinbase 같은 유통 협력사에 주는 몫, 경쟁 스테이블코인. 인사는 그 위에 붙는 지배구조의 일이다(grok.md:4671-4691).

### 8.5. 내 의견

이 절은 전부 `[내 판단]`이다.

**판정.** 세 답의 "주의"에 동의한다. 다만 이유의 무게를 다르게 둔다.

1. **Neville의 사임은 거의 신호가 아니다.** 경영에서 떠난 것은 2019년이고 그때의 글이 남아 있다. 2026년에 끝난 것은 이사회의 자리다. 질문의 걱정(초기 멤버가 떠나는 것)에 가장 잘 맞는 사건처럼 보이지만 실제로는 가장 가벼운 사건이다. 다만 다시 뽑힌 지 넉 달 남짓 만에 사임했다는 점은 아래에 따로 적는다.
2. **Date의 사임이 Neville보다 무겁다.** 선임 사외이사는 의장을 겸하는 CEO를 견제하는 자리다. Allaire가 CEO와 의장을 겸하고 Class B로 의결권의 4분의 1 가까이를 가진 회사에서, 13년 동안 그 자리에 가까이 있던 사람이 나갔다. 세 답은 Date를 Neville과 묶어 "초기 이사 둘"이라고 세었는데, 두 사람의 자리는 무게가 다르다.
3. **Fox-Geen의 사임이 가장 무겁고, 까닭은 시기다.** ARC를 팔아 받은 2.42억 달러는 지금 부채(이연수익)이고, 조건이 충족되지 않으면 돌려줘야 하는 돈이다(4.6절(네트워크 토큰: ARC)). 그 돈을 언제 얼마만큼 매출로 옮길지는 판단이 많이 들어가는 회계 결정이고, 2026년 기타 매출 전망을 두 배로 올린 근거가 바로 그 결정이다. 그 결정을 내리고 설명하던 사람이 결정이 실행되는 해의 끝에 떠난다. 이것이 사임의 원인이라는 증거는 없다. 그러나 후임이 같은 회계 판단을 이어받을지는 볼 만하다.

**세 답이 덜 본 것.**

- 질문은 "초기 멤버의 이탈"을 물었는데, 2026년의 세 사건 가운데 질문에 꼭 맞는 것은 없다. Neville은 7년 전에 떠났고, Date는 직원이 아니라 이사이며, Fox-Geen은 초기 멤버가 아니다. 질문에 꼭 맞는 사건은 2019년에 있었고, 그것은 실제로 위기였다(5.4절(생존 쪽)). 그러니 "초기 멤버의 이탈은 위기 신호인가"에 대한 Circle의 답은 "2019년에는 그랬다"이다.
- 남은 이사 Burns도 주식을 팔 계획을 세웠다(7.4절(2026년에 나간 사람들)). 떠나는 사람의 매도만 보고 남는 사람의 매도를 보지 않으면 그림이 기운다. 다만 상장 뒤에 오래된 주주가 계획을 세워 파는 것은 흔한 일이고, 5만 주는 큰 양이 아니다.
- 7.5절(지분과 의결권)에서 본 대로 Neville의 실질 소유가 반년에 30% 줄어든 것은 사실이지만, 그 대부분은 만기가 온 옵션을 행사하면서 세금을 내려고 하루에 판 것이다. 세 답은 줄어든 비율만 적고 이 까닭을 적지 않았다.
- Neville은 2026년 5월의 주주총회에서 3년 임기로 다시 뽑혔고 넉 달 남짓 뒤에 사임했다(7.2절(사람마다의 현황)). 다시 뽑힐 때는 물러날 계획이 없었거나 알리지 않았다는 뜻이다. 이것이 "질서 있는 교체"라는 회사의 설명과 어긋난다고까지 할 수는 없지만, 세 답이 Neville의 사임을 가볍게 본 근거(7년 전에 이미 떠났다)에 더할 사실이다 `[내 판단]`.
- 이사회의 인원은 세 답이 적은 것보다 더 많이 움직였다. 2025년 7월부터 2026년 9월까지 셋이 나가고 둘이 들어왔다(7.2절(사람마다의 현황)). 나간 사람만 세면 이탈이고 들어온 사람까지 세면 교체다.

**판정을 바꿀 것.** 세 답이 든 목록(9장)에 동의하고 순서를 이렇게 둔다.

1. 후임 CFO가 12월 31일까지 정해지는가, 그리고 누구인가.
2. 3분기 실적에서 ARC 매출 인식과 기타 매출 전망이 유지되는가.
3. 감사인 교체나 재무제표 재작성 공시가 나오는가. 나오면 주의가 아니라 경고다.
4. Date의 자리가 채워지는가, 이사회를 7명으로 둘 것인가.
5. Tarbert, Chandhok 같은 다른 임원이 떠나는가.
6. Allaire가 계획에 없던 큰 매도를 하는가.

## 9. 세 답이 덧붙인 것: 위험과 앞으로 볼 것

사용자가 묻지 않았지만 세 답이 모두 답의 끝에 적었다. 8장의 판정이 기대는 내용이어서 넣는다.

### 9.1. 금리

- 유통량이 늘어도 단기 금리가 내리면 준비금 수익이 깎인다. 2026년 2분기가 그 모양이다(grok.md:182-190, claude.md:68). 숫자는 3.2절(2026년 2분기의 숫자)에 있다.
- **금리가 1%포인트 움직일 때.** Claude는 준비금 수익이 약 6.2억 달러, 유통비용이 약 3.2억 달러 함께 움직인다고 쓰고 2025년 중반 기준이라고 밝혔다(claude.md:800-806). 공시에 있는 숫자다 `[공시 확인]`: 2025년 6월의 평균 수익률 4.26%를 기준으로 100bp가 움직이면 준비금 수익 6.18억 달러, 유통 및 거래 비용 3.15억 달러가 달라진다(10-Q2:2845-2849).
- 같은 표의 더 새로운 숫자가 있다 `[공시 확인]`(10-Q2:2837-2842). Claude는 옛 숫자를 썼다.

  | 기준 | 100bp 움직일 때 준비금 수익 | 100bp 움직일 때 유통 및 거래 비용 | 둘의 차 |
  |---|---|---|---|
  | 2025년 6월, 평균 수익률 4.26% | 6.18억 달러 | 3.15억 달러 | 3.03억 달러 |
  | 2026년 6월, 평균 수익률 3.49% | 7.37억 달러 | 3.60억 달러 | 3.77억 달러 |

  표의 한 행은 기준 시점 하나다. 앞의 두 값은 공시의 값이고 "둘의 차"는 내가 뺀 값이다.

```text
금리가 1%포인트 움직일 때 한 해에 달라지는 돈 (막대 한 칸은 0.2억 달러)

2025년 6월 기준   준비금 수익         6.18억 달러   ###############################
                  유통 및 거래 비용   3.15억 달러   ################
                  둘의 차             3.03억 달러   ###############

2026년 6월 기준   준비금 수익         7.37억 달러   #####################################
                  유통 및 거래 비용   3.60억 달러   ##################
                  둘의 차             3.77억 달러   ###################
```

**도식: 금리에 걸린 돈.** 위 표를 막대로 놓았다. 공시는 유통량이 바뀌지 않는다고 가정했다. 세 답은 이것을 그리지 않았다.

- 이 표가 말하는 것 `[내 판단]`: 금리가 1%포인트 내리면 회사에 남는 돈(유통비용을 뺀 매출)이 한 해에 약 3.77억 달러 줄어든다. 2026년 상반기의 유통비용을 뺀 매출이 5.76억 달러였으므로(10-Q2:2058), 한 해로 치면 약 11.5억 달러이고 그 3분의 1이다. 유통량이 늘면서 금리에 걸린 돈도 한 해 사이에 커졌다.
- 공시는 이 계산의 전제를 밝힌다: 유통량이 2026년 6월 30일의 수준에서 바뀌지 않는다고 가정했고, 금리와 유통량의 관계는 "complex, highly uncertain, and unproven"이라고 적는다 `[공시 확인]`(10-Q2:2826-2833).

### 9.2. 기타 매출과 ARC: 세 답이 끝에 가서 가장 중요하다고 본 것

- 2026년 기타 매출 전망은 1.5억에서 1.7억 달러였다가 3.1억에서 3.3억 달러로 올랐다(claude.md:68, claude.md:732-737, chatgpt.md:3482-3592). 공시는 4.6절(네트워크 토큰: ARC)에 있다.
- CFO Fox-Geen이 2분기 실적 발표에서 한 말 `[공시 확인]`: "We expect to recognize this token presale revenue as certain product milestones are achieved. Based on our product road map, we expect to achieve approximately 75% of the milestones in revenue in 2026 and have included \$180 million in the revised guide. As this revenue is recognized, it will flow directly to the bottom line. The remainder of our products are expected to deliver between \$130 million and \$150 million"(`web-circle-q2-2026-earnings-call-transcript.md:526-529`).
- ChatGPT와 Claude가 쓴 1.8억 달러(chatgpt.md:3482-3592, claude.md:423-427)가 이 말과 맞는다. 검산: 2.422억 x 75% = 1.817억 달러.
- **세 답이 보지 못한 것** `[내 판단]`. ChatGPT는 나머지 제품의 전망을 "약 \$130~150M 예상"이라고 옮겼다(chatgpt.md:3482-3592). 그런데 처음 전망은 1.5억에서 1.7억 달러였다. 곧 ARC를 뺀 기타 매출 전망은 2,000만 달러 내렸다. 회사는 그 까닭을 밝혔다 `[공시 확인]`: "This reflects our strategic decision to focus resources on the development of Arc instead of additional blockchain partnerships as well as moderation in commercial opportunities with new blockchain partners"(`web-circle-q2-2026-earnings-call-transcript.md:531-532`).
  - 그래서 전망 표의 "두 배로 올랐다"는 두 가지가 합쳐진 것이다: 토큰 판매 1.8억 달러가 더해졌고, 나머지는 2,000만 달러 줄었다.
  - 줄어든 부분은 다른 블록체인과 맺는 협력에서 나오던 매출이다. 3.7절(과거와 지금을 나란히 놓으면)에서 본 기타 매출의 구성(통합 서비스)과 맞는다. Circle이 자체 체인을 만들면서 다른 체인에서 받던 돈을 놓고 있다는 뜻이다.
  - 다만 같은 발표의 질의응답에서는 1.8억 달러를 빼면 흐름이 앞서 낸 전망 범위의 가운데쯤을 향한다는 말도 나온다(`web-circle-q2-2026-earnings-call-transcript.md:1037-1038`). 두 말이 어떻게 함께 서는지는 확인하지 못했다.
- 1.8억 달러가 3분기와 4분기에 어떻게 나뉘는지는 회사가 밝히지 않았고, 하반기에 1.8억 달러만 인식하면 나머지는 2027년에 인식된다고 했다 `[공시 확인]`(`web-circle-q2-2026-analyst-call-transcript.md:278-292`). 회사가 말한 비율은 2026년의 약 75%이고(`web-circle-q2-2026-earnings-call-transcript.md:526-527`), 남은 몫을 25%로 적는 것은 100에서 75를 뺀 내 셈이다 `[내 판단]`. 비용이 붙지 않아서 거의 그대로 이익이 된다(같은 곳).
- ChatGPT의 제안: 앞으로 Circle의 매출은 셋으로 나눠 보아야 한다. 준비금 수익, 운영에서 나오는 매출(구독, 거래 수수료, 서비스, CPN, 개발자 제품), 네트워크와 토큰에서 나오는 매출(ARC)(chatgpt.md:5513-5546, chatgpt.md:4108-4225). 기타 매출이라는 한 줄만 보면 사업이 실제보다 빨리 넓어지는 것처럼 보인다.
- **ARC의 회계와 CFO의 교체를 잇는 것에 대하여.** Grok이 먼저 이었고(grok.md:1932-1973 뒤의 대목) Claude가 가장 날카로운 지적이라고 평가했다(claude.md:449). ChatGPT는 선을 그었다: 볼 거리로 삼는 것은 타당하지만, CFO가 ARC의 회계 때문에 떠난다는 증거는 없다(chatgpt.md:3482-3592). Claude는 ChatGPT와 Grok이 CFO의 위험을 말하면서 ARC를 넣지 않았다고 되받았다(claude.md:553). 세 답의 마지막 입장은 같다: 인과는 확인되지 않았고, 후임이 이 회계를 어떻게 이어 가는지는 볼 만하다.
- ChatGPT의 말로는 지금 가장 볼 것은 떠난 사람이 왜 떠났는가가 아니라 새 CFO가 ARC의 회계와 이자가 아닌 사업을 어떻게 설명하는가다(chatgpt.md:4052-4104).

```text
2026년 기타 매출 전망 (막대 한 칸은 0.1억 달러, 범위의 가운데 값으로 그렸다)

처음의 전망                   1.5억에서 1.7억 달러    ################
고친 전망                     3.1억에서 3.3억 달러    ################################
  ARC 사전 판매의 매출 인식   1.8억 달러              ##################
  나머지 제품                 1.3억에서 1.5억 달러    ##############

ARC 사전 판매 2.422억 달러가 매출이 되는 때
  2026년   약 75%, 1.8억 달러
  2027년   나머지


ChatGPT가 제안한 매출의 세 갈래
  +-- 준비금 수익
  +-- 운영에서 나오는 매출: 구독, 거래 수수료, 서비스, CPN, 개발자 제품
  +-- 네트워크와 토큰에서 나오는 매출: ARC
```

**도식: 기타 매출 전망의 속.** 위 항목을 옮겼다. 나머지 제품의 범위 1.3억에서 1.5억 달러는 ChatGPT가 옮긴 숫자다. ChatGPT가 같은 분해와 세 갈래를 그렸다(chatgpt.md:3523-3532, chatgpt.md:5528-5541).

### 9.3. 유통을 남에게 기대는 것

- Coinbase에 주는 돈이 크다(claude.md:68). 숫자는 3.4절(Coinbase와의 계약)에 있다.
- 공시는 이것을 위험 요인으로 든다 `[공시 확인]`: "the market for distribution of stablecoins is concentrated among a few key distributors ... Should any of these digital asset distributors take action to promote other digital assets in advance of ours or should they stop supporting our digital assets, such distributors may be difficult to replace"(10-K:1433-1437).
- Open USD(3.4절(Coinbase와의 계약))가 바로 이 위험이 드러난 사례다. 계약의 갱신으로 일단 가라앉았지만 기대는 정도는 그대로다(claude.md:800-806).
- 상표를 잃을 수 있는 조항이 있다 `[공시 확인]`(10-K:2399-2419). 세 답에 없다. 공시에 따르면 Coinbase와의 계약에는 법이나 명령 때문에 Circle이 협약을 이행할 수 없게 되거나 지급을 다시 시작하지 못할 때 상표의 일부를 넘겨야 하는 조항이 있다. 조항의 세부는 읽지 않았고 있다는 것만 확인했다 `[열람: 10-K 2399-2419행의 제목과 첫 문단]`.

### 9.4. 규제

- GENIUS Act와 금리, 유통 계약의 갱신 같은 실적 변수는 1회차에 Claude만 깊게 다뤘다고 Grok이 평가했다(grok.md:1682-1683).
- 공시의 설명 `[공시 확인]`(10-K:533-549): GENIUS Act는 미국에서 결제용 스테이블코인의 발행을 연방이나 주의 감독을 받는 허가된 발행사로 제한하고, 준비금의 구성, 제때의 상환, 금융 범죄 방지, 공시, 검사의 기준을 둔다. 효력은 2027년 1월 18일, 또는 감독 기관이 시행 규정을 낸 날부터 120일 가운데 빠른 날에 생긴다. 허가된 발행사가 낸 결제용 스테이블코인은 증권도 상품도 아니게 된다.
- 회사는 이 법의 준비금과 상환 요건이 자신이 이미 하는 것과 맞는다고 본다(10-K:542-547). 동시에 위험 요인의 목록에도 넣었다: "the GENIUS Act, which will change the payment stablecoin ecosystem and may affect our business in ways that cannot yet be known"(10-K:239).
- 법이 허가된 발행사를 늘리면 경쟁도 는다. 공시가 위험 요인의 첫 줄에 놓은 것이 경쟁이다(10-K:227) `[내 판단]`.

### 9.5. Arc는 아직 검증되지 않았다

- 메인넷이 2026년 9월 16일에 열렸으므로 결제, 환전, 에이전트의 쓰임이 실제로 붙는지는 이제 시작이다(grok.md:182-190, claude.md:800-806).
- 검증자가 허가형이다(claude.md:69). 공시는 이것을 위험이 아니라 특징으로 적는다(4.5절(블록체인: Arc)).
- 지분증명으로 바꾸지 못하면 ARC를 산 투자자에게 돈을 돌려줘야 한다(4.6절(네트워크 토큰: ARC)). 기한은 2028년 5월 8일이다. 세 답은 이 조항을 적었지만 위험의 목록에는 넣지 않았다. 2.42억 달러를 돌려줘야 할 수 있다는 것은 Arc의 기술 일정이 곧 재무의 일정이라는 뜻이다 `[내 판단]`.

### 9.6. 그 밖에 세 답이 든 것

- 테더와의 자리: 세계의 온체인 결제와 규제의 신뢰에서는 USDC가 강하고, 한국 같은 일부 거래소 시장에서는 USDT가 강하다(grok.md:182-190).
- SVB(2023년): 준비금이 한곳에 몰린 위험이 한 번 현실이 되었고, 그 뒤에 수탁과 공시의 구조를 강화했다(grok.md:182-190). 2.7절(SVB 사태)에 있다.
- 핵심 인물: 창업자의 의결권이 Allaire 한 사람에게 모였다(claude.md:800-806). 7.5절(지분과 의결권)에 있다.
- 방향을 튼 것의 평가: 2019년에 다 정리하지 않았다면 지금의 상장과 규제상의 자리가 나오기 어려웠다(grok.md:182-190).
- Claude는 1회차에 더 볼 것으로 기타 매출의 구성, Coinbase 협약의 갱신 조건, 그리고 "계속영업이익"이라는 표현 뒤에 중단사업이 있는지를 들었다(claude.md:71). 중단사업은 있다 `[공시 확인]`: 10-K의 손익계산서에 중단사업 손실이 한 줄로 있고, 가운데 열의 해에 132.4만 달러다(10-K:6089). 크기가 작다. 기타 매출의 구성은 3.7절(과거와 지금을 나란히 놓으면)에, 협약의 갱신은 3.4절(Coinbase와의 계약)에 있다.
- Claude는 2회차 교차 2의 표에서 CFO 교체의 위험의 핵심을 ARC 대금의 매출 인식과 Binance와의 새 계약으로 적었다(claude.md:581).

### 9.7. 앞으로 볼 것

세 답이 든 것을 모았다(claude.md:346-370, claude.md:482-484, claude.md:800-806, chatgpt.md:3398-3445, grok.md:4437-4438, grok.md:4671-4691).

| 볼 것 | 왜 | 누가 들었나 |
|---|---|---|
| 후임 CFO가 12월 31일까지 정해지는가. 안에서 올리는가 밖에서 데려오는가. 가상자산 출신인가 전통 금융 출신인가 | 앞으로 두세 분기의 공시의 질을 가른다 | 셋 모두 |
| 3분기 실적에서 ARC 매출 인식과 기타 매출 전망이 유지되는가 | 2026년 기타 매출 전망의 절반 넘게가 ARC다 | 셋 모두 |
| 감사인 교체나 재무제표 재작성 공시(8-K의 4.01, 4.02 항목) | 나오면 분명한 위험 신호다 | Claude, ChatGPT |
| Tarbert, Chandhok, Carpenter 같은 다른 임원이 잇달아 떠나는가 | 한 사람의 교체와 연쇄는 다르다 | 셋 모두 |
| Allaire의 역할, 의결권, 지분에 큰 변화가 있는가. 계획에 없던 큰 매도 | Class B의 구조가 Allaire에게 묶여 있다 | 셋 모두 |
| 이사회를 7명으로 둘 것인가 채울 것인가 | Date와 Neville의 자리 | Grok |
| 준비금 수익률, USDC 분기 말 유통량, Coinbase에 주는 몫, 경쟁 스테이블코인 | 인사보다 먼저 볼 사업의 지표 | Grok |

표의 한 행은 볼 것 하나다.

- 3분기 실적의 발표일: Claude는 "11월 초"라고 썼고(claude.md:482-484), ChatGPT는 2026년 9월 29일 현재 발표일이 공지되지 않았으므로 확정된 일정으로 쓰면 안 된다고 지적했다. 2025년의 3분기 실적은 11월 12일에 나왔다(chatgpt.md:4052-4104).
- ChatGPT가 끝에 남긴 두 물음이 이 장을 줄인다(chatgpt.md:5596-5645): 새 제품이 실제로 USDC의 유통량을 늘리는가, 그리고 준비금 수익 밖에서 되풀이해 돈을 버는 독립된 사업으로 자라는가. ChatGPT는 앞의 것은 상당히 진행 중이고 뒤의 것은 아직 증명해야 하는 단계라고 보았다.
- 내가 덧붙이는 것 `[내 판단]`: 앞의 물음에 대한 ChatGPT의 평가("상당히 진행 중")는 근거가 약하다. USDC의 분기 말 유통량은 2025년 말의 750억 달러 남짓에서 2026년 6월 말의 733억 달러로 줄었다(4.2절(자산)). 새 제품이 많이 나온 반년 동안 유통량은 늘지 않았다. 분기 평균은 765억 달러여서 분기 안에서 오르내린 것일 수 있지만, 제품의 수와 유통량이 함께 간다는 증거는 아직 공시에 없다.

## 10. 세 답을 읽으면서 알게 된 것

묶음의 10번 주제(세 답이 서로를 평가한 부분)에서 Circle이 아니라 답에 관한 것을 추렸다. 사용자가 이 조사 방식을 다시 쓸 때 쓸모가 있어서 넣는다.

### 10.1. 세 답이 서로에게 매긴 평가

| 모델 | 세 답이 함께 인정한 강점 | 세 답이 함께 지적한 약점 |
|---|---|---|
| ChatGPT | 구조를 이해시키는 그림. 공시의 숫자로 질문의 전제를 고치는 힘. 스스로 고친 것을 가장 분명히 밝힘 | 길고 되풀이가 많다. 붙여 넣으면 출처가 사라진다. 최신의 일(ARC 사전 판매, Binance)을 늦게 넣었다. 누가 찾았는지를 잘못 적었다 |
| Claude | 출처와 확신도를 항목마다 적음. 사실, 추론, 미확인을 나눔. 자신의 오류를 먼저 적음 | 검색 결과에 있던 사실을 끝까지 따라가지 않았다(Carpenter의 입사일, 매각 대가). 2차 기사를 1차 사실처럼 옮겼다(Spark, 4억 달러) |
| Grok | 범위가 넓고 한국의 사정을 넣음. 공식 발표와 회고를 나란히 읽음 | 출처가 없거나 약하다. 다른 답의 숫자를 검증 없이 받아서 오류가 회차를 넘어 퍼지는 길이 되었다 |

표의 한 행은 모델 하나다. 근거는 chatgpt.md:1118-1179, chatgpt.md:1458-1474, chatgpt.md:1478-1480, claude.md:143, claude.md:166, claude.md:204-211, grok.md:1627-1629, grok.md:1668-1669, grok.md:3329-3331, grok.md:3348, grok.md:3425, claude.md:561, claude.md:567, chatgpt.md:1763-1778, chatgpt.md:3275-3327, claude.md:185-202, claude.md:464-476, claude.md:588-595, grok.md:1687-1714, grok.md:3374-3406, grok.md:4391-4423이다.

- 세 답이 함께 꼽은 좋은 조합: ChatGPT의 그림과 거래 구조, Claude의 출처 태도와 2019년의 규제 순서, Grok의 범위와 "대외 발표와 회고"의 구분(grok.md:1687-1714, grok.md:3374-3406).
- 그림에 대한 Grok의 단서: 그림은 모델의 해석이고 출처가 아니다. 확인되지 않은 숫자를 그림 옆에 붙이면 그림의 설득력이 숫자까지 보증하는 것처럼 보인다(grok.md:1687-1714).

```text
ChatGPT   그림과 거래 구조                  --+
Claude    출처 태도와 2019년의 규제 순서    --+-->  좋은 조합
Grok      범위, 대외 발표와 회고의 구분     --+

Grok의 단서
  그림  +  확인되지 않은 숫자  -->  그림의 설득력이 숫자까지 보증하는 것처럼 보인다
  그림은 모델의 해석이고 출처가 아니다
```

**도식: 세 답의 좋은 조합과 그림에 대한 단서.** 위 두 항목을 옮겼다. Grok의 단서는 이 문서의 그림에도 해당해서, 그림마다 아래에 숫자와 등급이 어느 표와 문장에서 왔는지를 적었다. 세 답은 서로에 대한 평가를 그림으로 그리지 않았다. 묶음의 10번 주제에 든 그림 셋은 ChatGPT가 평가하면서 Circle의 구조를 다시 그린 것이다.

### 10.2. 회차를 거듭하며 드러난 것

- Claude의 정리: 회차마다 새 1차 자료(S-4, Form 4, SEC의 채용 계약, Grit)가 나올 때 결론이 움직였다. 요약 기사나 다른 AI의 답을 근거로 한 주장은 거의 매번 고쳐야 했다(claude.md:588-595).
- Grok의 정리: 사실 관계는 충분히 모였고, 다음에 열 가치가 있는 것은 해석을 다시 하는 것이 아니라 1차 자료 넷이다. Grit 에피소드의 녹취, S-4의 Trade 운전자본과 Kraken 주식 대목, 2026년 주주총회 자료의 Burns 약력과 Carpenter 소개, 424B4의 Class B 전환과 의결권 상한(grok.md:4442-4451).
- Grok은 Claude가 판정을 주의로 올린 것을 "취향에 가깝습니다"라고 했다. 근거가 "사람이 더 보였다"이지 "회사가 더 나빠졌다"가 아니라는 것이다(grok.md:4391-4423). 8.5절(내 의견)의 내 의견은 이 지적을 받아들인 것이다: 판정을 올릴 근거는 사람의 수가 아니라 ARC의 회계와 겹치는 시기다.

```text
Grok이 다음에 열 자료로 꼽은 것          이 문서에서 어떻게 되었나

Grit 에피소드의 녹취                -->  열지 않았다. 받지 않은 자료로 남겼다
S-4의 Trade 운전자본 대목           -->  열었다. "significant"라는 말뿐이고 금액은 없다
S-4의 Kraken 주식 대목              -->  열었다. 세 답의 숫자가 맞다 (받은 주식 83,186주)
주주총회 자료의 Burns 약력          -->  열었다. 2013년 12월에 이사가 되었다
주주총회 자료의 Carpenter 소개      -->  주주총회 자료에는 Carpenter가 없다
                                         채용 계약은 IPO 투자설명서(424B4)에 있다
424B4의 Class B 전환과 의결권 상한  -->  424B4의 이 대목은 읽지 않았다
                                         같은 내용을 10-K와 정관에서 확인했다
```

**도식: Grok이 꼽은 다음 자료와 이 문서가 한 것.** 위 두 번째 항목의 넷을 왼쪽에 놓고, 대목이 둘인 것은 두 줄로 나눴다. 오른쪽은 이 문서가 그 자료를 어떻게 다뤘는지다. Grit은 12장(확인하지 못하고 남긴 것)의 받지 않은 것에, S-4의 두 대목은 6.3절(Circle Trade)(S-4:6589-6601)에, Burns는 12장의 닫힌 것에, Class B는 7.5절(지분과 의결권)(10-K:2517-2519, 정관:53)에 있다. 주주총회 자료에 Carpenter가 없다는 것은 검색으로 보았다(검색: `grep -c -i carpenter web-circle-2026-04-01-def14a.md`, 0). Carpenter의 채용 계약은 424B4에 있다: "We entered into an offer letter with Ms. Carpenter, dated as of May 16, 2016"(424B4:2299). 7.2절(사람마다의 현황)의 입사일 2016년 6월 6일쯤(`[답의 주장]`)과 어긋나지 않지만, 계약서의 날짜는 입사일이 아니어서 그 등급은 바꾸지 않았다. 세 답은 이것을 그리지 않았다.

### 10.3. 내가 공시와 Circle의 글로 대조해서 본 것

이 절은 전부 `[내 판단]`이다. 근거는 앞의 절마다 있다.

**교차 검증이 맞는 내용을 틀렸다고 한 경우.**

| 내용 | 누가 썼나 | 누가 틀렸다고 했나 | 1차 자료 | 다룬 절 |
|---|---|---|---|---|
| xReserve는 구독료를 받는다 | Claude | ChatGPT("삭제하는 게 맞습니다", 확신도 높음) | 10-K에 그대로 있다 | 4.3.2 |
| 2025년에 Coinbase에 준 유통비용은 약 14억 달러 | ChatGPT, Claude | Grok("과대일 가능성이 큽니다") | 10-K에 14억 달러로 있다 | 3.4 |
| Circle이 Coinbase의 CENTRE 지분 50%를 인수했다 | ChatGPT | Grok("표현이 거칠음") | 10-K의 표현과 같다 | 2.4 |
| Hashnote를 약 1억 달러에 인수했다 | ChatGPT | Grok("단정하지 않는 편이 낫습니다") | 10-K에 1.001억 달러로 있다 | 4.16 |
| Neville이 2026년 내내 계획에 따라 꾸준히 팔았다 | Grok | Claude("확인된 매도는 9월 1일의 한 건") | Form 4에 열 날의 매도가 있다 | 7.5 |
| Circle Trade를 팔 때 소개 대금(거래액의 0.1%)이 따로 있었다 | ChatGPT | Claude(소개는 주식을 받는 조건의 하나) | S-4가 둘을 따로 적는다 | 6.3 |

표의 한 행은 사례 하나다.

```text
맞게 쓴 쪽              틀렸다고 한 쪽  내용

Claude            <--   ChatGPT         xReserve의 구독료
ChatGPT, Claude   <--   Grok            Coinbase에 준 유통비용 약 14억 달러
ChatGPT           <--   Grok            CENTRE 지분 50%의 인수
ChatGPT           <--   Grok            Hashnote 약 1억 달러
Grok              <--   Claude          Neville의 꾸준한 매도
ChatGPT           <--   Claude          Circle Trade의 소개 대금

틀렸다고 한 쪽                맞게 쓴 쪽 (한 사례에 둘이면 둘 다 센다)
  Grok     ###   3            ChatGPT  ####  4
  Claude   ##    2            Claude   ##    2
  ChatGPT  #     1            Grok     #     1
```

**도식: 누가 누구의 맞는 내용을 틀렸다고 했나.** 위 표를 옮겼다. 화살표는 틀렸다고 한 쪽에서 맞게 쓴 쪽으로 간다. 막대 한 칸이 사례 하나다. 틀렸다고 한 쪽의 수(Grok 셋, Claude 둘, ChatGPT 하나)는 아래 "여기서 끌어낼 것"에 있고, 맞게 쓴 쪽의 수는 내 셈이다: 유통비용의 행은 ChatGPT와 Claude를 하나씩 세어 합이 일곱이다. 세 모델 모두 한 번 이상 맞는 내용을 틀렸다고 했고, 한 번 이상 맞게 쓴 것을 지적받았다. 세 답은 이것을 그리지 않았다.

**세 답이 모두 놓친 것.**

| 내용 | 1차 자료 | 다룬 절 |
|---|---|---|
| ARC를 뺀 2026년 기타 매출 전망은 2,000만 달러 내렸다 | 2분기 실적 발표 녹취 | 9.2 |
| Circle 자신의 플랫폼에 있는 USDC의 비율이 7.4%에서 19.5%로 늘었다 | 2분기 10-Q | 3.2 |
| USDC의 분기 말 유통량이 2025년 말보다 2026년 6월 말에 적다 | 10-K, 2분기 10-Q | 4.2, 9.7 |
| Agent Stack의 구성 요소는 공시에서 넷이다 | 2분기 10-Q | 4.10 |
| Circle이 Neville이 세운 신생 회사에 투자했다 | 10-K | 7.4 |
| 특수관계자인 IDG Capital의 계열이 ARC 사전 판매에 참여했다 | 2분기 10-Q | 4.6 |
| SeedInvest는 처분이익 2,160만 달러를 내고 팔았다 | 10-K | 6.6 |
| 2019년 6월과 10월에도 회사는 Poloniex와 SeedInvest를 앞날의 축으로 꼽았다 | Circle의 글 둘 | 5.2 |
| 이더리움으로 옮겨 간 때는 2017년 초다 | Circle의 2020년 글 | 5.2 |
| 후속 공모에서 회사가 판 주식은 350만 주다 | 10-K | 1.3 |
| 2026년 3월에 이사 Koenigsbauer가 들어왔고, 2025년 9월에 이사 Orfao가 나갔다 | 8-K 둘 | 7.2 |
| Neville은 2026년 5월에 3년 임기로 다시 뽑혔고 반대표가 가장 많았다 | 8-K | 7.2 |
| Neville의 지분이 30% 줄어든 것의 77%는 만기가 온 옵션의 세금 때문에 하루에 판 것이다 | Form 4 | 7.5 |
| Circle Invest를 팔고 받은 Voyager 주식을 2021년 초에 약 2,610만 달러에 처분했다 | S-4 | 6.4 |
| 2019년의 계속영업 순손실이 작아 보이는 것은 워런트 평가이익 5,950만 달러 때문이다 | S-4 | 5.4 |
| Binance에 판 주식은 시장가보다 싸게 팔았다 | 8-K | 3.5 |
| Tazapay의 값은 4억 달러어치의 주식이다 | 8-K | 4.15 |

표의 한 행은 항목 하나다.

```text
세 답이 모두 놓친 것을 1차 자료로 나누면 (한 칸이 한 가지)

8-K                     ####  4
10-K                    ###   3
2분기 10-Q              ###   3
S-4                     ##    2
Circle의 글             ##    2
10-K와 2분기 10-Q       #     1
2분기 실적 발표 녹취    #     1
Form 4                  #     1
                              --
                        합계  17

교차 검증이 맞는 것을 틀렸다고 한 것    6
세 답이 모두 놓친 것                    17
                                        --
1차 자료를 열어서 나온 것               23
```

**도식: 세 답이 놓친 것은 어느 자료에서 나왔나.** 위 표의 "1차 자료" 칸을 그대로 셌다. 8-K 둘을 든 행도 한 가지로 세었고, 두 자료를 함께 든 행 하나(10-K와 2분기 10-Q)는 따로 두었다. 17과 23(6 + 17)은 내 셈이고, 23은 아래 "여기서 끌어낼 것"의 스물세 가지와 같다. 세 답은 이것을 그리지 않았다.

**여기서 끌어낼 것.**

- 세 모델이 서로를 검증하는 것은 오류를 줄이지만 없애지 못하고, 때로는 맞는 내용을 지운다. 위의 여섯 사례에서 틀렸다고 한 쪽은 모두 자신 있게 말했다. 틀렸다고 한 쪽은 Grok이 셋, Claude가 둘, ChatGPT가 하나다.
- 세 답이 최종 답에서 일치하는 것은 세 번의 독립된 확인이 아니다. 서로의 답을 세 번 읽은 뒤의 일치다.
- 1차 자료를 한 번 여는 것이 교차 검증 한 회차보다 값졌다. 이 문서의 대조는 공시와 실적 자료, Circle의 글 열한 편, 그리고 2026-09-29에 더 받은 SEC 공시를 열거나 해당 줄을 찾아 읽은 것이 전부인데, 거기서 위 두 표의 스물세 가지가 나왔다.
- 나도 틀렸다. Neville의 "30%" 비교가 서로 다른 것을 견준 것일 수 있다고 적었는데 Form 4를 열어 보니 같은 것끼리의 비교였다(7.5절(지분과 의결권)). 자료를 열기 전의 짐작은 세 답의 것이든 내 것이든 같은 값으로 다뤄야 한다.
- 세 답이 2019년의 숫자에 대해 든 출처(S-1)는 맞지 않았고 숫자 자체는 모두 맞았다. 숫자는 2021년의 S-4에 있다. 출처의 이름이 틀렸다고 해서 내용이 틀린 것은 아니었다.

```text
독립된 일치

  ChatGPT  --+
  Claude   --+-->  서로의 답을 보기 전에 이미 같았던 것
  Grok     --+


최종 답의 일치

  세 답  -->  서로의 답을 읽고 평가 (세 번)  -->  최종 답에서 같은 말
                   |
                   +-- 검증 없이 받은 숫자가 다음 회차로 넘어간다
                   +-- 맞는 내용을 자신 있게 틀렸다고 한다 (위 표의 여섯 가지)


1차 자료를 연 것

  공시, 실적 자료, Circle의 글  -->  위 두 표의 스물세 가지
  열기 전의 짐작                -->  세 답의 것이든 내 것이든 같은 값으로 다룬다
                                     (Neville의 30%: 열어 보니 내 짐작이 틀렸다)


출처의 이름과 내용은 따로 맞고 틀린다 (2019년의 숫자)

  세 답이 든 출처   S-1     맞지 않았다
  세 답이 쓴 숫자   열 개   모두 맞았다. 2021년의 S-4에 있다
```

**도식: 교차 검증과 1차 자료.** 위 "여기서 끌어낼 것"의 다섯 항목을 그렸다 `[내 판단]`. 독립된 일치의 기준은 "읽는 법"의 문단(세 답의 일치를 어떻게 읽을까)에 있다. 검증 없이 받은 숫자가 넘어간다는 것은 10.1절(세 답이 서로에게 매긴 평가)의 표에서 세 답이 Grok의 약점으로 꼽은 것이고, 숫자 열 개는 12장(확인하지 못하고 남긴 것)의 첫 행에 있다. 세 답은 이것을 그리지 않았다.

## 11. 여덟 질문에 대한 답

앞의 장들을 질문의 순서로 한 문단씩 다시 적는다. 근거와 단서는 해당 장에 있고, 여기에는 적지 않는다. 이 장은 앞 장들을 줄인 것이어서 앞 장들을 대신하지 않는다.

세 답도 회차마다 머리말과 맺음말에서 자신의 답을 줄여 적었다. 묶음의 11번 주제에 있고, 읽었으며, 앞의 장들에 적은 것 밖의 새 사실은 없다: chatgpt.md:9, chatgpt.md:1011-1058, claude.md:9-13, grok.md:9, chatgpt.md:1064-1114, claude.md:120-124, grok.md:1608-1623, grok.md:1718-1729, chatgpt.md:1850-1859, claude.md:254-260, grok.md:1785, grok.md:1977-1981, chatgpt.md:2771-2773, claude.md:407-409, grok.md:3312-3325, grok.md:3410-3412, chatgpt.md:3451-3453, claude.md:515-517, grok.md:4354-4369, grok.md:4427-4429, chatgpt.md:4237-4243, claude.md:626-641, grok.md:4479-4481.

1. **어떤 거래소에 상장했나.** 뉴욕증권거래소다. Class A 보통주가 2025년 6월 5일부터 CRCL로 거래된다. 공모가는 31달러였고 회사는 1,990만 주를 팔아 5.83억 달러를 조달했다. 2025년 8월에 130달러로 후속 공모를 했다. USDC나 ARC가 거래되는 곳과 회사의 주식이 거래되는 곳은 다르다(1장).
2. **과거에는 무엇을 했나.** 2013년에 비트코인으로 소비자의 돈을 옮기는 회사로 시작했다. 2016년에 비트코인 매매를 앱에서 빼고 법정화폐를 블록체인으로 옮기는 쪽으로 기울었다. 2018년에는 송금 앱, 투자 앱, 장외거래, 거래소, 크라우드펀딩, 스테이블코인을 한꺼번에 했다. 2019년에 거의 다 정리했다(2장).
3. **지금은 무엇을 하나.** USDC와 EURC를 발행하고, 그 돈이 도는 길(발행과 상환, 체인 사이의 이동, 자체 체인, 결제망, 환전, 개발자 도구)을 다른 회사에 공급한다. 2026년에 연방 신탁은행을 열었다(3장).
4. **주요 사업은 과거에 무엇이었고 지금은 무엇인가.** 과거에는 소비자에게 직접 파는 사업 여섯 가지였다. 지금 돈을 버는 사업은 하나다: USDC 준비금의 이자가 매출의 95%다. 그 가운데 큰 몫이 Coinbase와 Binance로 간다. 나머지 제품은 USDC를 더 쓰이게 하려는 투자이고, 따로 버는 돈은 아직 작다(3장).
5. **Arc, CCTP, StableFX, CPN만이 주요 기술인가.** 아니다. 넷은 블록체인, 체인 사이의 이동, 환전, 결제라는 큰 축 넷을 짚었지만 돈 자체(USDC, EURC, USYC, cirBTC), 들어오고 나가는 문(Mint), 잔고를 합치는 것(Gateway), 남의 코인을 받치는 것(xReserve), 개발자 도구, 기업용 계정, 에이전트 도구가 더 있다. 사업으로 보면 가장 중요한 것은 넷 가운데 어느 것도 아니고 USDC와 Mint다(4장).
6. **왜 USDC로 강하게 방향을 틀었나.** 생각은 2016년부터 있었고 제품은 2018년에 나왔다. 2019년에 회사가 위태로워지자 나머지를 자르고 그것 하나만 남겼다. 이자를 벌려고 한 선택은 아니었다: 그때 USDC의 이자 수익은 몇백만 달러였다. 회사가 "원래부터 이것이 목표였다"고 말하는 것은 절반만 받아들일 수 있다. 2019년 10월까지도 회사는 다른 사업을 키우겠다고 썼다(5장).
7. **다른 사업을 왜 헐값에 팔았나.** 전부 헐값은 아니다. 크게 손해 본 것은 Poloniex이고 손해의 대부분은 살 때 너무 많이 준 데서 나왔다. Circle Trade는 고객 관계만 넘겼고, Invest는 원래 작았고, Pay는 닫았고, SeedInvest는 4년 뒤에 이익을 내고 팔았다. 서두른 까닭은 회사가 위태로웠기 때문이다. Poloniex는 안 될 것을 알고 나왔고, Trade는 그렇지 않았다(6장).
8. **창업자와 초기 멤버는 남아 있나, 그들의 이탈은 위기 신호인가.** 창업자 둘 가운데 Allaire만 경영에 남았다. Neville은 2019년에 경영에서, 2026년 9월에 이사회에서 떠났다. 2013년의 이사 Burns와 2016년에 온 Carpenter가 남아 있다. 2026년에는 선임 사외이사 Date와 CFO Fox-Geen도 떠나거나 떠나기로 했다. 세 답의 판정은 위기가 아니라 주의다. 나도 같고, 그 까닭은 떠난 사람의 수가 아니라 CFO가 바뀌는 때가 ARC 판매 대금을 매출로 옮기는 때와 겹친다는 데 있다. 초기 멤버의 이탈이 실제로 위기였던 때는 2019년이다(7장, 8장).

```text
여덟 답을 이야기의 순서로 놓으면 (괄호 안은 질문의 번호)

2013년  비트코인으로 소비자의 돈을 옮기는 회사로 시작했다 (2)
   |
   v
2016년  법정화폐를 블록체인으로 옮기는 쪽으로 기울었다 (2, 6)
   |
   v
2018년  여섯 사업을 한꺼번에 했다 (2)
   |      송금 앱, 투자 앱, 장외거래, 거래소, 크라우드펀딩, 스테이블코인
   |      USDC가 이때 나왔다 (6)
   v
2019년  회사가 위태로워졌다
   |      +-- USDC 하나만 남겼다. 이자를 벌려는 선택은 아니었다 (6)
   |      +-- 나머지는 팔거나 닫았다. 전부 헐값은 아니다 (7)
   |      +-- 초기 멤버가 떠났다. 이때가 실제로 위기였다 (8)
   v
2025년  뉴욕증권거래소에 상장했다. CRCL (1)
   |
   v
지금    USDC와 EURC를 발행하고 그 돈이 도는 길을 다른 회사에 공급한다 (3)
        매출의 95%가 준비금의 이자이고 큰 몫이 Coinbase와 Binance로 간다 (4)
        질문의 넷 밖에도 제품이 더 있고, 가장 중요한 것은 USDC와 Mint다 (5)
        2026년에 연방 신탁은행을 열었다 (3)
        2026년에 Neville, Date, Fox-Geen이 떠나거나 떠나기로 했다. 판정은 주의다 (8)
```

**도식: 여덟 답을 한 줄로.** 위 여덟 문단의 문장을 줄여 해의 순서로 놓고 줄마다 그 문장이 있는 문단의 번호를 붙였다. 순서로 놓은 것은 내가 한 것이다 `[내 판단]`. 해마다의 근거는 2장(과거에는 무엇을 했나)의 연혁 도식과 각 장에 있다. ChatGPT도 회차의 맺음말에서 회사의 이야기를 해의 순서로 그렸다(chatgpt.md:1073-1099, chatgpt.md:4113-4163, chatgpt.md:5601-5631). ChatGPT의 그림은 회사가 어떤 회사였는지로 시기를 나눴고, 이 그림은 질문의 답을 이야기 위에 놓았다.

**질문마다 볼 도식.** 앞 장들의 도식을 질문에 따라 모았다. 도식의 이름은 각 도식 아래 설명의 첫머리에 있는 이름이다.

| 질문 | 장 | 그 장의 도식 |
|---|---|---|
| 1. 어떤 거래소에 상장했나 | 1장(어디에 상장했나) | IPO에서 팔린 주식의 분해, 주식과 발행 자산 및 네트워크 토큰의 구분 |
| 2. 과거에는 무엇을 했나 | 2장(과거에는 무엇을 했나) | 연혁, Circle Pay의 구조, Centre의 앞과 뒤 |
| 3. 지금은 무엇을 하나, 4. 주요 사업은 과거에 무엇이었고 지금은 무엇인가 | 3장(지금은 무엇을 하고, 돈은 어디서 나오나) | 버는 회사와 짓는 회사, 2분기 매출이 나온 곳과 간 곳, 매출의 구성과 선순환 가설, Coinbase에 주는 돈을 정하는 네 단계, 유통비용의 크기, 유통 협력사가 주주가 되는 모양, 인가의 지도, 직접 파는 회사에서 남을 거쳐 닿는 회사로 |
| 5. Arc, CCTP, StableFX, CPN만이 주요 기술인가 | 4장(Arc, CCTP, StableFX, CPN만이 주요 기술인가) | 제품과 사업 지원 구조, Circle이 다루는 자산, Circle Mint의 두 방향, xReserve의 발행 구조, CCTP와 Gateway가 하는 일, Arc의 구성과 일정, ARC 사전 판매의 셈과 회계, 개발자 도구, CPN과 Managed Payments, StableFX의 정산, Agent Stack의 구성, Digital Asset Accounts, 외부 발행사와의 협력 제도, Tazapay가 더하는 지급 구간, 인수의 크기 |
| 6. 왜 USDC로 강하게 방향을 틀었나 | 5장(왜 중간에 USDC로 강하게 방향을 틀었나) | 두 문장이 만나는 자리, 비트코인에서 USDC까지의 순서, 앱과 USDC의 차이, 2019년의 순서, 2019년의 손익을 위에서 아래로, 비율이 아니라 순서, ChatGPT가 낸 전체 그림 |
| 7. 다른 사업을 왜 헐값에 팔았나 | 6장(다른 사업을 왜 헐값에 팔았나) | 여섯 사업의 끝, Poloniex 처분손실의 셈, Poloniex의 규제 문제와 인수, 매각의 순서, Circle Trade에서 넘긴 것과 남긴 것, Circle Invest의 대가가 된 주식, 받은 것의 크기 |
| 8. 창업자와 초기 멤버는 남아 있나, 그들의 이탈은 위기 신호인가 | 7장(창업자와 초기 멤버는 지금 어디에 있나), 8장(초기 멤버의 이탈은 회사의 위기 신호인가) | 사람마다 있던 기간, 이사회 인원의 변화, 2026년의 순서, 의결권의 셈과 Class B가 끝나는 조건, 줄어든 30%의 속, 2019년과 2026년, 판정이 움직인 길 |

표의 한 행은 질문 하나다. 질문 3과 4는 같은 장이 답해서 한 행에 두었다. 9장(세 답이 덧붙인 것: 위험과 앞으로 볼 것)의 도식 둘(금리에 걸린 돈, 기타 매출 전망의 속)은 여덟 질문 밖의 것이어서 넣지 않았다.

## 12. 확인하지 못하고 남긴 것
2026-09-29에 사용자의 요청으로 SEC 공시를 받아 아래 표의 항목을 대조했다. 받은 자료의 목록과 받은 방법은 공시 묶음의 README에 있다.

**닫힌 것.**

| 남겼던 것 | 결과 | 닫은 자료 | 다룬 절 |
|---|---|---|---|
| 2019년의 재무 숫자(영업손실, Poloniex 처분 내역, 사업별 매출, USDC 이자) | 세 답의 숫자 열 개가 모두 맞다 | S-4 | 5.4, 6.2 |
| Circle Trade를 팔 때 소개 대금이 따로 있었는지 | 따로 있었고 실제로는 받지 못했다 | S-4 | 6.3 |
| Date, Neville, Fox-Geen의 사임의 세부 | 세 답의 서술이 맞다. Fox-Geen의 조건 다섯도 모두 맞다 | 8-K 둘 | 7.4 |
| Binance와의 계약 | 세 답의 숫자가 맞다 | 8-K | 3.5 |
| Tazapay 인수 계약 | 값과 조건을 더했다 | 8-K와 보도자료 | 4.15 |
| Allaire와 Neville이 가진 Class B의 정확한 수 | 17,708,642주와 4,488,271주. 옵션과 RSU를 넣은 수다 | 주주총회 자료 | 7.5 |
| Burns가 이사가 된 때 | 2013년 12월 | 주주총회 자료 | 7.2 |
| Class B가 저절로 바뀌는 조건 | 여섯 가지이고 ChatGPT가 든 셋이 그 안에 있다 | 정관 | 7.5 |
| 10-K에 서명한 이사가 8명인데 세 답은 9명에서 8명이 되었다고 한 것 | 서명 열흘 뒤에 이사 한 사람이 들어왔다 | 8-K | 7.2 |
| Neville이 꾸준히 팔았는지, 30%가 줄었는지 | 둘 다 맞다. 다만 대부분은 옵션 만기와 세금 때문이다 | Form 4 | 7.5 |

표의 한 행은 항목 하나다.

**자료를 열었지만 닫히지 않은 것.**

| 남긴 것 | 연 자료에 있던 것 | 아직 없는 것 |
|---|---|---|
| Circle Trade에 남긴 운전자본의 크기 | "significant"라는 말, 빌린 2,400 BTC를 갚았다는 것(S-4:6600) | 금액 |
| Poloniex를 얼마에 샀는지 | 대출 2,000만 달러, 판 쪽에 남은 빚 6,390만 달러, 워런트(S-4:4010, S-4:5998, S-4:3908) | 합계. S-4가 싣는 기간 밖이다 |
| 회사가 Poloniex의 규제 문제를 얼마나 알고 샀는지 | 인수 전부터 SEC의 소환장이 있었고 규제 책임을 떠안기로 했다는 것(S-4:3315, S-4:967) | 경영진이 실사에서 본 범위. 뉴욕타임스와 Fortune의 보도는 열지 않았다 `[미독 - 외부 링크]` |
| 2019년에 직원이 몇 명에서 몇 명으로 줄었는지 | 평균 인원이 58.6% 줄었다는 것, 2021년 6월에 233명(S-4:3901, S-4:3265) | 두 시점의 인원수. Grit 팟캐스트는 열지 않았다 `[미독 - 외부 링크]` |
| Coinbase와의 계약이 2029년까지 갱신되었는지 | 2026년 6월부터 9월까지의 8-K 다섯 건에 Coinbase라는 말이 없다(검색: `grep -c -i Coinbase web-circle-2026-0[6-9]*-8k.md`, 다섯 파일 모두 0) | 갱신을 적은 공시. 3분기 10-Q는 아직 나오지 않았다 |

표의 한 행은 항목 하나다.

**이번에 받지 않은 것.** SEC 공시가 아니어서 받지 않았고, 받으려면 사용자가 정해 주어야 한다.

| 남긴 것 | 무엇이 있으면 닫히나 |
|---|---|
| 한국 거래소의 USDC 상장 현황(코빗, 고팍스) | 각 거래소의 공지 |
| USYC의 인수 당시 운용 규모(15.2억 달러인가 12.5억에서 13억 달러인가) | 인수 발표문 |
| Arc Studio가 Claude Code, Codex, Cursor의 서브에이전트로 쓰이는지 | Arc의 개발 문서 |
| StableFX가 베타를 끝냈는지, 거래량이 얼마인지 | 2026년 3분기 공시(아직 나오지 않았다) |
| 2019년의 회고(Allaire의 Grit 인터뷰, Neville과 Ishaq의 2025년 회고) | 팟캐스트 녹취와 글 |
| Poloniex의 인수 값과 시장점유율에 관한 보도 | 뉴욕타임스, Fortune, The Block |

표의 한 행은 남긴 것 하나다.

- 세 답도 끝에 확신도와 남은 빈자리를 적었다. Claude는 Poloniex의 인수 대가, Spark가 이더리움으로 옮겨 간 경위, 2019년의 사업별 매출, Grit 인터뷰의 세부 수치, Burns가 이사가 된 때, Neville의 사임 사유를 미확인으로 남겼다(claude.md:810-822). Grok은 Trade가 남긴 운전자본의 크기, 2019년의 생존 압력의 비율, 2026년 인사의 내부 사정을 확신도 중간 밑으로 남겼다(grok.md:4695-4699). 위 표는 이 둘을 받고 내가 찾은 것을 더한 것이다. 이 가운데 Spark의 경위는 5.2절(비전 쪽)에서 Circle의 글로 채웠고, 2019년의 사업별 매출은 5.4절(생존 쪽)에서 S-4로, Burns가 이사가 된 때는 7.2절(사람마다의 현황)에서 주주총회 자료로 채웠다.
- 세 답이 든 외부 링크(묶음의 12번 주제, claude.md:73-108, grok.md:192-253, claude.md:213-235, grok.md:1731-1765, claude.md:372-395, grok.md:1983-2020, claude.md:486-503, grok.md:3427-3439, claude.md:597-614, grok.md:4453-4467, claude.md:824-863, grok.md:4701-4718)는 이 문서에 옮기지 않았고, 그 목록 구간은 읽지 않았다 `[미독]`. 링크는 묶음 파일의 12번 주제와 각 구간 안에 있다. 나는 그 링크를 열지 않았다 `[미독 - 외부 링크]`.
- 묶음의 구간 가운데 이 문서가 출처로 든 것과 들지 않은 것은 circle-company-survey-answer-coverage.txt에 있다.
