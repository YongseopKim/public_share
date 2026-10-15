# 6. Circle과 Arc의 방향이 맞는가?

이 문서는 일곱 질문 가운데 6번의 답입니다. 1번부터 5번까지가 넘긴 재료로 Circle과 Arc의 방향이 맞는지 판정하고, 그 판정을 7번(해커톤에 지원해도 되는가)에 넘깁니다.

이 답은 새 자료를 들이지 않았습니다. 1번부터 5번까지가 이미 확인한 원문의 행을 디스크에서 다시 열어 판정에 필요한 것만 인용했습니다. 숫자는 2026년 2분기 공시와 실적 콜 기준으로 고정된 값이고, 3분기 실적이 나오면 다시 봐야 합니다.

2026-10-14에 사용자 요청("문서 안에 중요 내용들을 선정하고, 그것들을 시각화 자료로 설명하는 내용을 추가할 것")에 따라 그림 다섯 개를 더했습니다. 본문은 고치지 않았고, 그림은 본문이 이미 인용한 자료만 씁니다. 다만 그림 3과 4를 위해 같은 자료에서 몇 행을 더 열었고(인용 위치 표에 더함), 각 그림의 설계와 근거는 `figures/q6-01.md`부터 `figures/q6-05.md`까지에 있습니다. 그림 2는 회사가 그리는 연결(나 절 1), 그림 3은 그 연결마다 있는 숫자(다 절 1), 그림 4는 기타 매출 가이던스의 계산(다 절 3), 그림 5와 그림 6은 두 기준의 판정과 운영 층(라 절 2와 3)입니다.

2026-10-15에 사용자 요청(원문 일부: "목차를 만들어서 내가 캐치하기 쉽게 만들 것", "제대로 된 목차인지 보고, 그렇지 않다면 수정할 것")에 따라 아래 목차를 더하고 절의 제목과 묶음을 다시 짰습니다. 판단과 인용 문장은 바꾸지 않았고, 절을 가리키는 말 몇 곳만 새 제목에 맞췄습니다. 옮긴 곳과 이유는 q6-report.md의 "목차와 제목을 다시 짠 것(2026-10-15)"에 있습니다.

같은 날 사용자 지적("이게 어떻게 한줄이라고 표현하지? 의미적으로 한줄이라는게 뭔지 생각해야 하는 것 아냐?")에 따라 한 줄 답을 판정 한 문장과 그 근거 목록으로 나눴습니다. 주장 여럿을 한 문단이나 한 bullet에 담은 곳도 주장 하나에 bullet 하나로 풀었습니다. 판단과 인용은 그대로이고, 고친 곳은 q6-report.md의 "한 줄 답을 한 줄로 고친 것(2026-10-15)"에 있습니다.

같은 날 사용자 질문(원문 일부: "이 세가지의 묶음 정보가 한눈에 들어왔음 좋겠음.", "에이전트의 매출은 사실상 0일거 같은데 그것도 확인하고 싶고.")에 따라 한 줄 답 바로 뒤에 "세 갈래 한눈에 보기" 절과 그림 1을 더하고, 한 줄 답의 에이전트 갈래에 한 줄을 더했습니다. 다른 절의 판단과 인용은 바꾸지 않았고, 새로 연 행은 인용 위치 표에 더했습니다. 경위는 q6-report.md의 "세 갈래 한눈에 보기를 더한 것(2026-10-15)"에 있습니다.

목차

- [한 줄 답](#한-줄-답)
- [세 갈래 한눈에 보기: 매출 비중과 성장 지표](#세-갈래-한눈에-보기-매출-비중과-성장-지표)
  - [1. 매출과 성장 지표: 세 갈래를 한 표에](#1-매출과-성장-지표-세-갈래를-한-표에)
    - 그림 1. 세 갈래의 매출과 성장 지표(2026년 2분기 기준)
  - [2. 에이전트 매출: 사실상 0인가](#2-에이전트-매출-사실상-0인가)
- [가. 회사가 말하는 방향: Circle과 Arc는 스스로 무엇을 하겠다고 하는가](#가-회사가-말하는-방향-circle과-arc는-스스로-무엇을-하겠다고-하는가)
  - [1. 10-Q: 새 제품에 건 두 목표](#1-10-q-새-제품에-건-두-목표)
  - [2. CEO의 말: Arc의 크기, 기간, 기타 매출](#2-ceo의-말-arc의-크기-기간-기타-매출)
  - [3. 메인넷 보도자료: Arc의 쓰임 세 가지](#3-메인넷-보도자료-arc의-쓰임-세-가지)
- [나. 판정의 틀: 방향을 무엇으로 나누고 무엇에 비추는가](#나-판정의-틀-방향을-무엇으로-나누고-무엇에-비추는가)
  - [1. 세 갈래: 회사의 말을 A, B, C로 나누고 두 목표에 잇기](#1-세-갈래-회사의-말을-a-b-c로-나누고-두-목표에-잇기)
    - 그림 2. 세 갈래가 회사의 두 목표에 닿는 길(회사 자료가 말하는 연결)
  - [2. 세 기준: 회사가 적은 목표, 고객의 문제, 말과 실행](#2-세-기준-회사가-적은-목표-고객의-문제-말과-실행)
- [다. 갈래별 판정: 세 갈래를 세 기준에 비추면](#다-갈래별-판정-세-갈래를-세-기준에-비추면)
  - [1. 판정 표: 세 갈래와 세 기준을 한 표에, 두 목표를 한 그림에](#1-판정-표-세-갈래와-세-기준을-한-표에-두-목표를-한-그림에)
    - 그림 3. 그림 2의 길마다 2026년 2분기 자료에 있는 숫자
  - [2. A 기관 금융 정산: 고객 근거는 가장 강하고 수익화는 시작 전](#2-a-기관-금융-정산-고객-근거는-가장-강하고-수익화는-시작-전)
  - [3. B Arc 네트워크 사업: 2026년 다변화를 만든 한 번의 사전판매](#3-b-arc-네트워크-사업-2026년-다변화를-만든-한-번의-사전판매)
    - 그림 4. 2026년 기타 매출 가이던스를 나눈 계산
  - [4. C 에이전트: 회사가 가장 크게 말하지만 매출 근거는 가장 약한 갈래](#4-c-에이전트-회사가-가장-크게-말하지만-매출-근거는-가장-약한-갈래)
- [라. 종합 판정: 그래서 방향이 맞는가](#라-종합-판정-그래서-방향이-맞는가)
  - [1. 회사 기준: 큰 방향은 맞고, 에이전트는 채택 논리](#1-회사-기준-큰-방향은-맞고-에이전트는-채택-논리)
  - [2. 제 기준(금리 의존): 금리와 무관한 반복 매출은 아직 시작 전](#2-제-기준금리-의존-금리와-무관한-반복-매출은-아직-시작-전)
    - 그림 5. 같은 세 갈래를 두 기준으로 판정하면
  - [3. 운영 층: 회사 스스로 적은 가장 큰 빈칸](#3-운영-층-회사-스스로-적은-가장-큰-빈칸)
    - 그림 6. 에이전트 결제의 두 층: 레일은 있고 운영 층은 짓는 중
- [마. 7번으로 넘기는 것: 회사가 바라는 것과 비어 있는 칸](#마-7번으로-넘기는-것-회사가-바라는-것과-비어-있는-칸)
- [한계](#한계)
- [인용 위치](#인용-위치)

## 한 줄 답

[제 판단, 확신도 중간] 큰 방향은 맞고, 에이전트는 매출 논리가 아니라 채택 논리이며, 가장 큰 빈칸은 회사 스스로 적은 운영 층(통제, 구제, 기록)입니다.

- 판정의 기준은 Circle이 2분기 10-Q에 적은 새 제품의 두 목표입니다(1895-1897행).
  - 목표 1: 네트워크가 커져 USDC 유통량이 늘고, 그것이 준비금 수익을 키운다.
  - 목표 2: 매출 구성을 다변화한다.
- 이 두 목표에 비춰 보면 방향은 회사 기준으로 일관됩니다.
  - 큰 방향: USDC를 인터넷 금융의 정산 자산으로 만들고, Arc로 정산 장소와 네트워크 가치를 갖는 것
- 다만 갈래마다 근거의 상태가 다릅니다.
  - 기관 금융 정산(CPN, StableFX): 고객 쪽 근거가 가장 강합니다. 그러나 CPN 수익화는 2026년 하반기에 시작하므로, 다변화 기여는 아직 시작 전입니다.
  - Arc 네트워크 사업: 2026년 다변화를 실제로 만들었습니다. 다만 한계가 셋 있습니다.
    - 그 돈은 한 번 들어오는 토큰 사전판매입니다.
    - 2028-05-08 PoS 조건이 붙어 있습니다.
    - 사전판매를 뺀 기타 매출 전망은 원래보다 낮아졌습니다.
  - 에이전트: 회사가 가장 크게 말하는 갈래입니다. 그러나 근거는 아직 약합니다.
    - 공시에서 매출이 따로 보이지 않습니다.
    - 확인해 보니 사실상 0입니다. 들어갈 줄 전체가 매출의 0.76%이고, 그 줄은 2분기에 오히려 줄었습니다(세 갈래 한눈에 보기 2).
    - Circle의 주된 고객에게는 아직 닿지 않았습니다.

방향을 세 갈래로 나눈 것과 판정 기준 세 가지는 제 구분입니다.

- 세 갈래: 4번 라 절의 세 시각(기관 금융 정산 네트워크, 네트워크 사업, 에이전트 경제의 기반)을 그대로 이었습니다.
- 세 기준: 사용자가 정한 두 가지에서 왔습니다.
  - 1번에서 사용자가 고른 picker 답: "고객의 문제와 회사의 문제를 나눠서 (추천)"
  - 2번을 시작할 때 사용자가 정한 목적: "서클/아크의 이런 부분에서 부족한 점이 드러나는 부분을 캐치"
- 회사의 문제는 제 해석(금리 의존)이 아니라 회사가 스스로 적은 목표로 먼저 겁니다. 제 해석은 나 절 2에 따로 두었습니다.

## 세 갈래 한눈에 보기: 매출 비중과 성장 지표

세 갈래(나 절 1)의 매출과 성장 지표를 한 그림에 모읍니다. 숫자는 이 답의 다른 절과 같은 2026년 2분기 자료에서 왔고, 이 절을 위해 몇 행을 더 열었습니다(인용 위치 표).

### 1. 매출과 성장 지표: 세 갈래를 한 표에

그림 1. 세 갈래의 매출과 성장 지표(2026년 2분기 기준)

한국어

```text
2026년 2분기 총매출 7억 131만 5천 달러(100%)
  준비금 수익 ......................  6억 6,773만  95.2%
  기타 매출 ........................      3,358만   4.8%
    Subscription and services ......      2,816만   4.0%
    Transaction revenue ............        533만  0.76%  <- C가 들어갈 줄
    Other ..........................        9.6만  0.01%
기타 매출이 1년 전보다 41.1% 늘어난 이유(10-Q): 통합 서비스, 토큰화 펀드의
운용 수수료, 스테이블코인 상환 수수료. A, B, C는 이 이유에 없음.

(단위: 달러)

                    2분기 매출            2026년 전체             성장 지표
                    (총매출 대비)         (회사 가이던스)         (매출이 아님, 갈래마다 단위가 다름)
------------------  --------------------  ----------------------  ------------------------------------
A. 기관 금융 정산   0으로 봄              따로 밝히지 않음        CPN 연환산 결제액(달러)
                    CPN 수익화는          (나머지 제품            57억(2/20) -> 147억(6/30)
                    하반기에 시작         1.3억-1.5억 안)         -> 230억(7/31)
                                                                  금융기관 55곳(2/20) -> 175곳(6/30)

B. Arc 네트워크     사전판매분 0          사전판매 인식분 1.8억   Arc 테스트넷 누적 거래 수
   사업             2.42억은 전액         = 기타 매출 가이던스    1.66억 건 넘음(2/20)
                    이연 매출(부채)로     3.1억-3.3억의 55-58%    -> 5.02억 건(6/30)
                    잡힘                  한 번뿐이고 조건부      메인넷 출시 9/16

C. 에이전트         따로 밝히지 않음      따로 밝히지 않음        같은 기준의 시계열 없음
                    상한은 들어갈 줄      (나머지 제품            x402 시장 30일 처리액 2,424만(4/29)
                    전체인 533만(0.76%)   1.3억-1.5억 안)         Agent Stack 유료 서비스 900개 이상
                                                                  들어갈 줄: 582.5만(25년 2분기)
                                                                  -> 673만(1분기) -> 533만(2분기)
```

English

```text
Q2 2026 total revenue USD 701.3M (100%)
  Reserve income ...................       667.7M  95.2%
  Other revenue ....................        33.6M   4.8%
    Subscription and services ......        28.2M   4.0%
    Transaction revenue ............        5.33M  0.76%  <- where C would sit
    Other ..........................         0.1M  0.01%
Why other revenue grew 41.1% year over year (10-Q): integration services,
fund management fees for tokenized funds, stablecoin redemption fees.
A, B and C are not among the reasons.

(USD)

                    Q2 revenue            FY 2026                 Growth indicator
                    (share of total)      (company guidance)      (not revenue; units differ by row)
------------------  --------------------  ----------------------  ------------------------------------
A. Institutional    taken as 0            not disclosed           CPN annualized TPV (USD)
   settlement       CPN monetization      (inside the USD         5.7B (2/20) -> 14.7B (6/30)
                    starts in H2          130M-150M remainder)    -> 23B (7/31)
                                                                  institutions 55 (2/20) -> 175 (6/30)

B. Arc network      presale part: 0       presale recognized      Arc testnet cumulative txs
   business         all USD 242.2M        USD 180M = 55-58% of    over 166M (2/20)
                    booked as deferred    USD 310M-330M other-    -> 502M (6/30)
                    revenue (liability)   revenue guidance;       mainnet launched 9/16
                                          one-off, conditional

C. Agents           not disclosed         not disclosed           no like-for-like series
                    ceiling: the whole    (inside the USD         x402 30-day volume USD 24.24M (4/29)
                    line it would sit     130M-150M remainder)    Agent Stack: 900+ paid services
                    in, USD 5.33M                                 that line: USD 5.83M (Q2 2025)
                    (0.76%)                                       -> 6.73M (Q1) -> 5.33M (Q2)
```

그림 1은 세 갈래(A, B, C는 나 절 1에서 회사의 말을 나눈 제 구분)를 매출과 성장 지표로 한 번에 놓은 것입니다. 위 블록은 2분기 매출 전체이고, 아래 표는 그 매출 안에서 세 갈래가 차지하는 자리입니다.

- 위 블록: 2분기 총매출의 95.2%는 준비금 수익이고, 기타 매출은 4.8%입니다(10-Q 1323-1329행).
  - 기타 매출이 1년 전보다 늘어난 이유로 10-Q가 드는 것은 통합 서비스, 토큰화 펀드의 운용 수수료, 스테이블코인 상환 수수료입니다(2303-2306행). 세 갈래 가운데 어느 것도 이 이유에 없습니다.
- 2분기 매출 열: 세 갈래 모두 2분기 손익계산서에 따로 보이는 매출이 없습니다.
  - A: 0으로 본 것은 제 판단입니다. 공시가 CPN 매출을 따로 적지 않고, Allaire는 수익화가 "the second half / of this year"에 시작한다고 말합니다(실적 콜 670-671행). 2026년 2월 콜에서도 "partners are already starting to monetize this"라고 해, 수익을 내기 시작한 쪽이 Circle이 아니라 파트너였습니다(4분기 콜 731-732행).
  - B: 사전판매 대금 2.42억 달러는 전액 이연 매출(아직 매출로 잡지 않은 받은 돈, 부채)로 잡혔습니다(10-Q 1383-1385행). 토큰 인도 같은 의무를 다한 뒤에 기타 매출로 옮깁니다(784-786행).
  - C: 에이전트 수수료가 들어갈 줄(Transaction revenue) 전체가 533만 달러, 총매출의 0.76%입니다. 그 줄 안의 에이전트 몫은 밝히지 않으므로, 이 값은 상한입니다. 확인한 것은 이 절의 2(에이전트 매출: 사실상 0인가)에 있습니다.
- 2026년 전체 열: 숫자가 있는 것은 B의 사전판매 인식분 1.8억 달러뿐입니다(실적 콜 527-528행).
  - 기타 매출 가이던스 3.1억-3.3억 달러의 약 55-58%입니다(`python3 -c "print(round(180/330*100,1), round(180/310*100,1))"`, 결과 54.5와 58.1).
  - 총매출에서 차지하는 비율은 낼 수 없습니다. 회사의 가이던스 표에는 USDC 유통량, 기타 매출, RLDC 마진, 조정 영업비용만 있고, 준비금 수익과 총매출은 없습니다(실적 보도자료 206-213행).
  - A와 C는 사전판매를 뺀 나머지 제품 1.3억-1.5억 달러(실적 콜 529행) 안에 들어 있을 수 있지만, 회사는 그 안을 나누지 않습니다.
- 성장 지표 열: 매출이 아니라 사용량이고, 갈래마다 단위가 다릅니다. 그래서 행끼리 크기를 견주면 안 됩니다.
  - A: CPN 연환산 결제액은 2026-02-20 57억 달러(4분기 실적 보도자료 48-51행)에서 2분기 말 147억 달러(전분기보다 76% 증가, 2분기 실적 보도자료 88-90행), 7월 31일 230억 달러(실적 콜 346-347행)로 늘었습니다. 금융기관은 55곳에서 175곳이 되었습니다. 세 숫자는 모두 최근 30일 결제액을 연으로 환산한 같은 정의입니다.
  - B: Arc 테스트넷의 누적 거래 수는 2026-02-20에 1억 6,600만 건을 넘었고(4분기 실적 보도자료 42-46행), 6월 30일에 5억 200만 건이었습니다(10-Q 1917-1918행). 테스트넷 거래는 매출도 실제 결제도 아닙니다. 메인넷은 2026-09-16에 열렸습니다(메인넷 보도자료 17행).
  - C: 같은 정의로 이어지는 시계열이 없습니다. x402 숫자는 자료마다 무엇을 셌는지가 달라 서로 이을 수 없고(5번 가 절), 표의 2,424만 달러는 x402 시장 전체의 30일 처리액이지 Circle의 매출이 아닙니다(Agent Stack 출시 글 209행). 유료 서비스 900개 이상은 2분기 실적 보도자료의 한 시점 숫자입니다(91-92행).
  - C 칸의 마지막 줄은 에이전트 수수료가 들어갈 줄의 분기별 값입니다. 1분기 값 673만 달러는 상반기 1,206만 달러에서 2분기 533만 달러를 뺀 것입니다(10-Q 1326행, `python3 -c "print(12060-5330)"`).
- 정리하면 [제 판단, 확신도 높음] 매출로 보면 세 갈래 모두 2분기에는 0이거나 공시에 보이지 않고, 2026년에 숫자가 생기는 것은 한 번뿐인 B의 사전판매입니다. 성장으로 보면 숫자가 가장 빨리 크는 것은 A의 결제액이지만 아직 매출이 아닙니다. C는 매출 숫자도, 이어지는 성장 숫자도 없습니다.

그림의 설계와 근거: figures/q6-00.md

### 2. 에이전트 매출: 사실상 0인가

- [제 판단, 확신도 높음] 사실상 0이라는 짐작은 맞다고 봅니다. 다만 공시가 0이라고 적은 것은 아니므로, 확인할 수 있는 것은 상한 하나와 정황 넷입니다.
- 상한: 에이전트 수수료가 들어갈 줄(Transaction revenue)은 2분기 533만 달러, 총매출의 0.76%입니다(10-Q 1326행, 그 줄이라고 본 근거는 3번 나 절 2).
  - 이 줄에는 에이전트 말고도 스테이블코인과 USYC의 상환 수수료, 블록체인 보상, CCTP 같은 인프라 사용료가 함께 들어갑니다(10-Q 1349-1351행). 그러므로 에이전트 몫은 533만 달러보다 작습니다.
- 정황 1: 기타 매출이 늘어난 이유를 적은 문단(10-Q 2303-2306행)에 에이전트가 없습니다. 10-Q에서 agent가 나오는 줄은 용어 정의, 제품 목록, AI 위험 요인뿐입니다(3번 나 절 2).
- 정황 2: Agent Stack이 나온 2분기(2026년 5월 출시)에 이 줄은 오히려 줄었습니다.
  - 1분기 673만 달러에서 2분기 533만 달러로 20.8% 줄었고, 1년 전 582.5만 달러보다 8.5% 줄었습니다(`python3 -c "print(12060-5330, round((5330/6730-1)*100,1), round((5330/5825-1)*100,1))"`, 결과 6730, -20.8, -8.5).
  - 줄어든 이유는 공시가 밝히지 않으므로, 이것으로 에이전트 몫을 잴 수는 없습니다. 다만 에이전트 수수료가 이 줄을 키우지는 못했습니다.
- 정황 3: 공개된 요금 구조에서 Circle이 받는 몫은 작거나 보이지 않습니다.
  - Nanopayments 테스트넷 출시 글은 묶음 정산에 드는 온체인 비용을 Circle이 부담한다고 적습니다("with onchain costs covered by Circle at the batch settlement layer", 37행).
  - Nanopayments 글 세 편에서 fee가 나오는 20줄은 모두 기존 결제 수단의 수수료나 체인의 가스비 이야기이고, Circle이 받는 수수료를 적은 줄은 없습니다(검색: `rg -n -i '\bfees?\b'`를 세 글의 pages 파일에 실행, 20줄).
  - Nanopayments는 Gateway를 기반으로 합니다(10-Q 113행, "powered by Circle Gateway"). Arc 문서가 Unified Balance 지출에 적은 Gateway 프로토콜 수수료는 출발과 도착 체인이 다를 때만 0.5bp(0.005%)이고, 같은 체인이면 0입니다(Arc 문서 Unified Balance 수수료 34행).
  - Agent Wallets의 수수료 문서는 이번에 열지 않았습니다 [미독].
- 정황 4: CEO가 스스로 프로토콜 자체의 매출은 "some", 채택은 "fundamentally"라고 나눕니다(실적 콜 991-993행).
- 그래서 에이전트가 Circle의 매출에 닿는 주된 길은 수수료가 아니라, 에이전트가 쥔 USDC 잔액이 준비금 수익을 키우는 길입니다. 그 잔액을 밝힌 숫자는 없습니다(다 절 4, 5번 나 절).

## 가. 회사가 말하는 방향: Circle과 Arc는 스스로 무엇을 하겠다고 하는가

### 1. 10-Q: 새 제품에 건 두 목표

- 2분기 10-Q는 사업을 세 기둥(Arc, 디지털 자산과 서비스, 응용)으로 나누고 "The three pillars of our platform are designed to reinforce one another"라고 적습니다(1863-1866행) [공시].
- 준비금 수익 말고 다른 제품에 대해서는 이렇게 적습니다. "We also expect growth in our network / to drive increases in our stablecoins in circulation and thereby drive our reserve income. We anticipate growing these offerings in the coming years, diversifying / our revenue profile."(1895-1897행) [공시]
- 그래서 회사가 새 제품에 건 목표는 둘입니다.
  - (1) 유통량을 늘려 준비금 수익을 키운다.
  - (2) 매출 구성을 다변화한다.
  - 이 둘로 나눈 것은 원문의 "and thereby drive our reserve income"과 "diversifying our revenue profile"을 그대로 따른 것입니다.

### 2. CEO의 말: Arc의 크기, 기간, 기타 매출

- 실적 콜에서 Allaire는 "we look at Arc as potentially as bigger than an opportunity / than USDC itself"라고 말합니다(878-879행).
- 이어서 "an incredible amount of financial activity, economic activity, agentic activity are going to / move on to these operating systems"라고 말하고, 그 기간을 "over the next 3 to 5 years"로 둡니다(882-883행).
- Arc를 "a source of major other revenue going forward"로 설명하고(891행), 2026년 이후의 숫자에 대해서는 "I'm not sure we have that much to say"라고 말합니다(897-898행).
- 기타 매출을 두고는 "from essentially 0 to now a / guided range of around \$300 million in 2026"이라고 말합니다(649-650행).

### 3. 메인넷 보도자료: Arc의 쓰임 세 가지

- Arc는 "purpose-built for financial markets, real-time money movement, and agentic economic activity"입니다(메인넷 보도자료 17행) [Circle 글].
- 부제는 "built for the Agentic Economic Era"입니다(15행).

## 나. 판정의 틀: 방향을 무엇으로 나누고 무엇에 비추는가

방향을 나누는 세 갈래와 판정에 쓰는 세 기준은 원문에 없는 제 구분입니다. 그렇게 고른 이유는 한 줄 답의 둘째 문단에 있습니다.

### 1. 세 갈래: 회사의 말을 A, B, C로 나누고 두 목표에 잇기

가 절의 소개를 4번 라 절의 세 시각에 맞춰 세 갈래로 나눕니다.

| 갈래 | 회사 자료에서 해당하는 것 |
|---|---|
| A. 기관 금융 정산 | CPN, StableFX, 창립 검증자 11곳(메인넷 보도자료 50행) |
| B. Arc 네트워크 사업 | ARC 토큰, Circle의 25% 몫(실적 콜 886행), 검증자로서 받는 수수료 |
| C. 에이전트 | Agent Stack. 10-Q의 정의는 "designed to enable autonomous artificial / intelligence agents to function as independent economic actors"입니다(107-108행) [공시]. |

그림 2. 세 갈래가 회사의 두 목표에 닿는 길(회사 자료가 말하는 연결)

한국어

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

English

```text
Goal 1. Grow USDC in circulation and thereby reserve income

  A. Institutional          B. Arc network            C. Agents
     settlement (CPN)          business
            |                         |                    |
            +------------+------------+                    |
                         v                                 v
          third parties build products            stablecoin adoption
                         |                                 |
                         +----------------+----------------+
                                          v
                      more demand for Circle Digital Assets
                            (more USDC in circulation)
                                          |
                                          v
                                 more reserve income

Goal 2. Diversify the revenue profile (revenue other than reserve income)

  A. Institutional       --> monetizing CPN
     settlement
  B. Arc network         --> ARC token presale, staking, transaction fees,
     business                partnerships
  C. Agents              --> revenue around the protocols themselves ("some")
```

그림 2는 가 절에서 인용한 회사 자료의 말을 연결로 그린 것입니다. 화살표는 회사가 기대하는 인과이고, 측정한 결과가 아닙니다.

- 목표 1 쪽: 두 경로가 모두 USDC 유통량을 거쳐 준비금 수익에서 끝납니다.
  - A와 B는 10-Q가 적은 경로로 들어갑니다. Arc, 개발자 인프라, CPN 위에 다른 회사가 제품을 만들면 Circle 자산의 수요가 늘어난다는 경로입니다(10-Q 1984-1988행).
  - C는 CEO가 말한 경로인 스테이블코인 채택으로 들어갑니다(실적 콜 991-993행).
- 목표 2 쪽: 세 화살표는 준비금 수익이 아닌 매출입니다.
  - A: CPN 수익화(353-354, 670-671행)
  - B: 사전판매와 Allaire가 든 스테이킹, 거래 수수료, 제휴(654-660행)
  - C: CEO가 "some"이라고 한 프로토콜 자체의 매출(991행)
- 각 화살표에 2026년 2분기 기준으로 어떤 숫자가 있는지는 다 절의 그림 3에서 이어서 봅니다.

그림의 설계와 근거: figures/q6-01.md

### 2. 세 기준: 회사가 적은 목표, 고객의 문제, 말과 실행

| 기준 | 내용 | 출처 |
|---|---|---|
| 1. 회사가 적은 목표 | 유통량을 늘려 준비금 수익을 키우는가, 매출 구성을 다변화하는가 | 10-Q 1895-1897행 |
| 2. 고객의 문제 | 1-1의 고객(은행, PSP, 기업, 기관, 개발자)의 문제에 닿는가 | 1번 |
| 3. 말과 실행 | 회사가 한 말과 지금 나와 있는 것이 맞는가 | 1-5, 2-5, 5번 |

[제 판단] 기준 1 옆에 둘 제 해석이 하나 있습니다.

- 2분기 매출의 95.2%가 준비금 수익입니다(10-Q 1885행).
- 같은 분기 준비금 수익은 두 방향으로 움직였습니다(2299-2302행).
  - 유통량 증가로 1억 4,740만 달러가 늘었습니다.
  - 수익률이 66bp 내려 1억 1,390만 달러가 줄었습니다.
- 그래서 저는 1번에서 회사의 문제를 "금리 의존"으로 읽었습니다.
- 다만 회사의 목표는 금리 의존을 줄이는 것이 아니라 준비금 수익을 키우면서 다변화하는 것입니다. 그래서 판정은 회사의 목표로 하고, 제 해석은 이 자리에만 둡니다.

## 다. 갈래별 판정: 세 갈래를 세 기준에 비추면

### 1. 판정 표: 세 갈래와 세 기준을 한 표에, 두 목표를 한 그림에

| 갈래 | 기준 1: 회사가 적은 목표 | 기준 2: 고객의 문제 | 기준 3: 말과 실행 |
|---|---|---|---|
| A. 기관 금융 정산 | CPN 결제액은 크게 늘었지만 수익화는 2026년 하반기에 시작합니다. 2분기 기타 매출 증가 이유에 CPN은 없습니다. 다변화 기여는 아직 시작 전입니다. | 가장 강합니다. 금융기관 175곳, 58개국 이상 | 10-K의 StableFX "currently in beta"는 2026년 2분기 10-Q에서 빠졌습니다. 프라이버시는 아직 "in development"입니다. |
| B. Arc 네트워크 사업 | 2026년 다변화를 실제로 만들었습니다. 다만 한 번 들어오는 사전판매이고, PoS 조건이 붙으며, 사전판매를 뺀 기타 매출 전망은 원래보다 낮습니다. | 간접적입니다. | Arc가 USDC보다 클 수 있다는 것은 말이고(878-879행), 2026년 이후 숫자는 "not sure we have that much to say"입니다. |
| C. 에이전트 | 매출이 공시에 따로 보이지 않습니다. 회사 스스로 프로토콜 매출은 "some", 채택은 "fundamentally"라고 나눕니다. | 개발자와 API 판매자에게는 닿습니다. 은행, PSP, 기업에는 아직 닿지 않았습니다. | "Agents can earn"은 짓는 중이고, 운영 층은 회사 스스로 아직 없다고 적습니다. 이름과 고지문, 구제 칸, 규모 숫자가 서로 어긋납니다. |

그림 3. 그림 2의 길마다 2026년 2분기 자료에 있는 숫자

한국어

```text
                     목표 1: 유통량 ->             목표 2: 다변화
                     준비금 수익
                     ----------------------------  ----------------------------
A. 기관 금융 정산    [고객 숫자: 있음]             [시작 전]
                     CPN 연환산 결제액             CPN 수익화는 2026년
                     약 150억 달러(2분기 말)       하반기에 시작
                     -> 230억 달러(7월 31일)       2분기 기타 매출이 늘어난
                     금융기관 175곳, 58개국 이상   이유에 CPN은 없음
                     [유통량 숫자: 없음]
                     CPN이 늘린 USDC 유통량

B. Arc 네트워크 사업 [유통량 숫자: 없음]           [2026년 숫자: 있음]
                     Arc 위의 제품이 늘린          ARC 사전판매 약 2.42억 달러,
                     USDC 유통량                   그중 1.8억 달러를
                     (있는 것: 테스트넷 누적       수정 가이던스에 넣음(그림 4)
                     거래 5.02억 건)               [한 번뿐이고 조건부]
                                                   2028-05-08까지 PoS로 못 옮기면
                                                   상환 권리

C. 에이전트          [유통량 숫자: 없음]           [따로 보이지 않음]
                     에이전트가 쥔 USDC 잔액       Transaction revenue 533만
                                                   달러(매출의 0.76%), 에이전트
                                                   몫은 밝히지 않음
```

English

```text
                     Goal 1: circulation ->        Goal 2: diversification
                     reserve income
                     ----------------------------  ----------------------------
A. Institutional     [customer numbers: yes]       [not started]
   settlement        CPN annualized payment        CPN monetization starts
                     volume: about USD 15B         in H2 2026
                     (Q2 end) -> USD 23B           Q2 other-revenue growth
                     (July 31)                     drivers do not include CPN
                     175 financial institutions,
                     more than 58 countries
                     [circulation number: none]
                     USDC added by CPN

B. Arc network       [circulation number: none]    [2026 number: yes]
   business          USDC added by products        ARC presale about USD 242.2M,
                     built on Arc                  USD 180M of it in the
                     (what exists: 502M            revised guide (Figure 4)
                     cumulative testnet txs)       [one-off and conditional]
                                                   repayment rights if no PoS
                                                   by 2028-05-08

C. Agents            [circulation number: none]    [not shown separately]
                     USDC balances held            Transaction revenue USD 5.33M
                     by agents                     (0.76% of revenue); agent
                                                   share not disclosed
```

그림 3은 그림 2의 길마다 2026년 2분기 자료에서 확인한 숫자를 붙인 것입니다. 대괄호 안의 표시는 그 길에 숫자가 있는지에 대한 제 구분입니다.

- 목표 1 열: 세 갈래 모두 그 갈래가 늘린 USDC 유통량을 따로 밝힌 숫자가 없습니다.
  - A에는 결제액과 금융기관 수가 있고 B에는 테스트넷 거래 수가 있지만, 둘 다 유통량은 아닙니다.
  - 회사가 먼저 적은 목표에 대해 갈래별 근거가 비어 있다는 뜻입니다.
- 목표 2 열: B만 2026년 숫자를 가졌고, 그 숫자는 한 번뿐이며 조건이 붙어 있습니다(그림 4).
  - A는 시작 전이고, C는 공시에서 따로 보이지 않습니다.
- 위의 표가 세 기준을 나란히 놓았다면, 이 그림은 기준 1을 두 목표로 나눠 어느 칸이 비었는지를 보여 줍니다.

그림의 설계와 근거: figures/q6-02.md

### 2. A 기관 금융 정산: 고객 근거는 가장 강하고 수익화는 시작 전

- 고객 쪽 근거가 가장 강합니다. 2분기 말 CPN의 연환산 결제액은 "nearly \$15 / billion"이고, 금융기관은 175곳입니다(실적 콜 339-344행). 7월 31일 기준으로는 "\$23 billion"이며 "more than 58 countries"에 닿습니다(346-349행).
- 수익화는 이제 시작입니다. Allaire는 "we are excited / about beginning to monetize CPN"이라고 말하고(353-354행), 시기를 "that will start really in the second half / of this year"라고 말합니다(670-671행).
- 공시에서도 아직 보이지 않습니다.
  - 2분기 기타 매출은 1년 전보다 41.1% 늘었는데, 10-Q가 든 이유는 통합 서비스, 토큰화 펀드의 운용 수수료, 스테이블코인 상환 수수료입니다(2303-2306행). 이 문단에 CPN은 없습니다.
  - 10-Q 전체에서 CPN이라는 낱말은 세 곳(1865, 1909, 1986행)에만 나오고, 셋 다 제품을 소개하거나 성장 기회를 말하는 문단입니다(`rg -n -w 'CPN' cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-10q.md`).
- 준비금 수익에 대한 기여는 회사의 기대입니다. 10-Q는 Arc와 CPN 위에 다른 회사가 제품을 만들면 "increase demand for Circle Digital Assets"할 것으로 봅니다(1984-1988행). CPN이 늘린 유통량을 따로 밝힌 숫자는 이번 자료에 없습니다.
- 말과 실행:
  - StableFX: 1-5에서 확인하지 못했던 이 행은 "2026년 자료는 베타라는 말 없이 운영 중인 제품으로 적는다"로 닫습니다.
    - 2025년 10-K는 "StableFX is currently in beta."라고 적었습니다(10-K 511행).
    - 2분기 10-Q는 StableFX를 "an institutional stablecoin / foreign exchange engine built on Arc"라고만 적고(1910-1911행), 10-Q 전체에 beta라는 낱말이 없습니다(`rg -c -i 'beta' cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-10q.md`, 일치 0건).
    - 메인넷 보도자료는 StableFX가 "enables 24/7 programmable FX trading"이라고 현재형으로 적고 연결된 지역 스테이블코인을 나열합니다(32행).
  - 프라이버시: 메인넷 보도자료는 "Opt-in privacy"를 설계 항목에 넣으면서 "in development for network-wide release"라고 적습니다(27행).
- [제 판단, 확신도 중간] A는 세 갈래 가운데 고객 근거가 가장 강하고, 회사의 두 목표 가운데 다변화에 닿을 수 있는 경로도 분명합니다. 다만 그 경로는 2026년 하반기에 시작하므로, 지금 판정할 수 있는 것은 "결제액은 늘었다"까지입니다.

### 3. B Arc 네트워크 사업: 2026년 다변화를 만든 한 번의 사전판매

- 2026년 다변화를 실제로 만든 것은 ARC 토큰 사전판매입니다.
  - 개당 0.30달러에 팔아 "aggregate gross proceeds to us of approximately \$242.2 million"을 받기로 했습니다(10-Q 1950-1951행).
  - CFO는 그 가운데 "\$180 million"을 수정 가이던스에 넣었다고 말합니다(실적 콜 527-528행).
- 기타 매출 가이던스는 1억 5천만-1억 7천만 달러에서 3억 1천만-3억 3천만 달러로 올랐습니다(실적 보도자료 209행).
  - 사전판매를 빼면 나머지 제품은 "between \$130 million and \$150 million"입니다(실적 콜 529행).
  - 원래 가이던스보다 양 끝에서 2,000만 달러씩 낮습니다(`python3 -c "print(310-180, 330-180)"`, 결과 130과 150).
- 낮아진 이유를 CFO는 "our strategic decision to focus resources on the development of Arc instead of additional / blockchain partnerships"와 시장 둔화로 듭니다(531-533행).
- 사전판매에는 조건이 붙어 있습니다. 토큰이 인도되지 않거나, Arc가 "on or before May 8, 2028"까지 PoS로 옮기지 못하면 상환 권리가 생깁니다(10-Q 1951-1953행).
- 앞으로의 수입원으로 Allaire는 스테이킹, 네트워크 거래 수수료, Arc 위의 파트너 관계를 들고, 거래 수수료는 "other stakeholders and validators on the network will be able to collect"라고 말합니다(실적 콜 654-660행).
- [제 판단, 확신도 중간] B는 회사의 두 목표 가운데 다변화에 2026년 숫자로 닿는 유일한 갈래입니다.
  - 그러나 그 숫자는 반복되지 않는 수입이고, 조건이 붙어 있으며, 다른 체인과의 제휴 매출 일부를 내준 대가입니다.
  - 회사가 말한 크기와 회사가 낸 숫자 사이의 거리가 세 갈래 가운데 가장 큽니다.
    - 말한 크기: Arc가 USDC보다 클 수 있다(실적 콜 878-879행)
    - 낸 숫자: 2026년 이후는 "not sure we have that much to say"

그림 4. 2026년 기타 매출 가이던스를 나눈 계산

한국어

```text
2026년 기타 매출 가이던스(단위: 백만 달러)

원래 가이던스                     150 ~ 170
수정 가이던스                     310 ~ 330
  = ARC 사전판매 인식분           180
  + 나머지 제품                   130 ~ 150     (310 - 180, 330 - 180)

나머지 제품 - 원래 가이던스       양 끝 -20     (130 - 150, 150 - 170)

수정 - 원래                       양 끝 +160    = 사전판매 180 - 감소 20

늘어난 160은 사전판매 180에서 나머지 제품의 감소 20을 뺀 값이다.
```

English

```text
2026 other-revenue guidance (USD millions)

Original guidance                 150 ~ 170
Revised guidance                  310 ~ 330
  = ARC presale recognized        180
  + remainder of products         130 ~ 150     (310 - 180, 330 - 180)

Remainder - original guidance     -20 (both)    (130 - 150, 150 - 170)

Revised - original                +160 (both)   = presale 180 - decline 20

The increase of 160 is the presale's 180 minus the remaining products'
decline of 20.
```

그림 4는 B 갈래가 만든 다변화를 숫자로 나눈 것입니다.

- 수정 가이던스 3억 1천만-3억 3천만 달러(실적 보도자료 209행)는 두 부분의 합입니다(실적 콜 528-529행).
  - 사전판매 인식분: 1억 8천만 달러
  - 나머지 제품: 1억 3천만-1억 5천만 달러
- 나머지 제품을 원래 가이던스 1억 5천만-1억 7천만 달러와 견주면 양 끝에서 2,000만 달러씩 낮습니다.
  - CFO는 그 이유를 Arc에 자원을 모으기로 한 결정과 시장 둔화로 듭니다(531-533행).
- 그래서 늘어난 1억 6천만 달러는 사전판매 1억 8천만 달러에서 나머지 제품의 감소 2,000만 달러를 뺀 값입니다.
- 원래 가이던스와 나머지 제품을 견준 것은 원래 범위에 사전판매가 들어 있지 않았다고 본 것입니다. 근거는 둘입니다.
  - 보도자료는 사전판매 매출을 포함한다는 각주(3)를 수정 범위에만 붙였습니다(209, 219행).
  - CFO도 증가가 "driven by Arc"라고 말합니다(실적 콜 521행).
- 계산은 `python3 -c "print(310-180, 330-180, 130-150, 150-170, 310-150, 330-170)"`로 다시 할 수 있고, 결과는 130, 150, -20, -20, 160, 160입니다.

그림의 설계와 근거: figures/q6-03.md

### 4. C 에이전트: 회사가 가장 크게 말하지만 매출 근거는 가장 약한 갈래

- 매출: 에이전트 수수료가 들어갈 줄(Transaction revenue)은 2분기 533만 달러로 매출의 0.76%이고, 에이전트 몫은 따로 밝히지 않습니다(10-Q 1326행, 3번 나 절). 기타 매출이 늘어난 이유를 적은 문단(2303-2306행)도 에이전트를 들지 않습니다.
- 회사가 기대는 경로는 채택입니다.
  - Allaire는 "some revenue around the protocols themselves, but fundamentally driving stablecoin adoption"이라고 말합니다(실적 콜 991-993행, 2-4 한 줄 답).
  - 그런데 준비금 수익으로 이어지려면 에이전트가 쥔 USDC 잔액이 커져야 하고, 그 숫자는 없습니다(5번 나 절).
- 고객: 지금 나와 있는 에이전트 제품이 푸는 문제는 에이전트를 만드는 개발자와 API를 파는 쪽의 문제입니다(3번 가 절). 1-1의 은행, PSP, 기업, 기관에는 에이전트 장치가 아직 붙지 않았습니다.
- 말과 실행:
  - 구성 요소의 수가 자료마다 다릅니다.
    - Agent Stack 출시 글(2026-05-11)은 "five core components"를 들고 Circle Skills를 넣습니다(204행).
    - 2분기 10-Q는 "Agent Stack consists of four components"라고 적고 Circle Skills를 넣지 않습니다(108-114행).
  - "Agents can earn"은 "H2 2026 - BUILDING"입니다(2분기 발표 자료 528행).
  - Circle의 Beyond 글은 "Until the “operating layer” is built out, volume will struggle to grow."라고 씁니다(45행)[원문 그대로].
  - 홍보 글과 공시의 첫머리는 에이전트를 "economic actors"라고 부르지만, 고지문과 약관은 에이전트를 사용자에게 딸린 도구로 적습니다(2-1, 2-2 한 줄 답).
  - 구제(잘못된 결제를 되돌리거나 보상받는 길)는 2025-08 litepaper에서 Arc 로드맵의 결제 모듈이었다가, 2026년 자료에서는 표준, 견본 코드, 은행의 몫, 고지문으로 흩어졌습니다(2-5 한 줄 답). 메인넷 보도자료의 고지문은 "the absence of recourse for transaction errors or losses"를 위험으로 적습니다(114행).
  - 규모 숫자는 같은 x402를 두고도 1,500만 달러에서 1억 달러 이상까지 갈립니다(5번 가 절).
- [제 판단, 확신도 중간] C는 회사의 목표 1(유통량을 늘려 준비금 수익을 키운다)과는 일관됩니다. 회사가 에이전트를 USDC와 Arc를 쓰게 만드는 이유로 내세우기 때문입니다. 그러나 목표 2(다변화)에 닿는 근거는 세 갈래 가운데 가장 약하고, 회사가 가장 크게 말하는 갈래이기도 합니다.

## 라. 종합 판정: 그래서 방향이 맞는가

### 1. 회사 기준: 큰 방향은 맞고, 에이전트는 채택 논리

- [제 판단, 확신도 중간] 큰 방향은 맞다고 봅니다. USDC를 인터넷 금융의 기본 정산 자산으로 만들고, Arc로 그 정산 장소와 네트워크 가치를 갖는다는 방향은 회사가 적은 두 목표와 일관되고, 고객 쪽 근거(CPN의 결제액과 금융기관 수)도 있습니다.
- [제 판단, 확신도 중간] 갈래별로는 근거의 상태가 다릅니다. A는 고객 근거가 강하고 매출은 아직 시작 전이며, B는 2026년 매출이 있지만 한 번뿐이고 조건이 붙었고, C는 회사가 가장 크게 말하지만 매출 근거가 가장 약합니다.
- 4번이 넘긴 질문("에이전트를 앞세우는 논리가 매출 논리인가 채택 논리인가")에는 이렇게 답합니다. [제 판단, 확신도 중간]
  - 에이전트는 채택 논리입니다.
  - Arc는 채택 논리이면서, 토큰과 지분을 통해 매출 논리이기도 합니다.
  - CEO의 "some"과 "fundamentally"(실적 콜 991-993행)가 이 구분을 스스로 보여 줍니다.

### 2. 제 기준(금리 의존): 금리와 무관한 반복 매출은 아직 시작 전

- 제 해석(금리 의존)으로 보면 결론이 달라집니다. [제 판단, 확신도 중간]
  - 2026년에 금리와 무관한 매출을 크게 더한 것은 B의 사전판매뿐이고, 그것은 반복되지 않습니다.
  - 반복되는 수입으로 금리 의존을 줄일 후보는 A의 CPN 수수료인데, 아직 시작 전입니다.
  - C는 회사 스스로 채택(유통량을 거쳐 준비금 수익으로 가는 길)을 주된 경로로 둡니다.
- 회사의 목표 문장(1895-1897행)은 준비금 수익을 키우는 것을 먼저 적으므로, 금리 의존을 줄이는 것은 회사의 목표가 아니라 제 기준입니다.

그림 5. 같은 세 갈래를 두 기준으로 판정하면

한국어

```text
                     회사 기준                   제 기준
                     (회사가 적은 두 목표)       (금리 의존을 줄이는 반복 매출)
                     --------------------------  --------------------------
A. 기관 금융 정산    결제액과 기관 수는 늘었고   반복 수입 후보(CPN 수수료),
                     수익화는 2026년 하반기      아직 시작 전

B. Arc 네트워크 사업 2026년 다변화를 실제로      금리와 무관한 매출을 더했지만
                     만듦(사전판매)              반복되지 않음

C. 에이전트          목표 1(채택)과 일관,        주된 경로는 채택: 유통량을
                     목표 2의 근거는 가장 약함   거쳐 준비금 수익으로 간다
-----------------------------------------------------------------------
판정                 큰 방향은 맞다              2026년에 금리와 무관한
                                                 매출을 크게 더한 것은
                                                 반복되지 않는 사전판매뿐
```

English

```text
                     Company yardstick           My yardstick
                     (its two stated goals)      (recurring revenue that
                                                 reduces rate dependence)
                     --------------------------  --------------------------
A. Institutional     volume and institutions     recurring candidate (CPN
   settlement        grew; monetization in       fees), not started yet
                     H2 2026

B. Arc network       created real 2026           added revenue not tied to
   business          diversification (presale)   rates, but it does not recur

C. Agents            consistent with goal 1      main path is adoption:
                     (adoption); weakest         through circulation to
                     evidence for goal 2         reserve income
-----------------------------------------------------------------------
Verdict              the broad direction         the only large 2026 revenue
                     is right                    not tied to rates is the
                                                 non-recurring presale
```

그림 5는 라 절 1의 첫째 판단(큰 방향은 맞다)과 라 절 2의 판단(제 해석으로 보면 결론이 달라진다)을 나란히 놓은 것입니다.

- 왼쪽 열은 회사가 적은 두 목표로 판정한 것입니다.
- 오른쪽 열은 제 해석(금리 의존)에서 나온 기준으로 판정한 것입니다. 오른쪽 기준은 회사의 목표가 아니라 제 기준입니다(나 절 2).
- 같은 사실이 기준에 따라 다르게 읽힙니다.
  - B의 사전판매는 왼쪽에서는 다변화를 실제로 만든 근거가 되고, 오른쪽에서는 반복되지 않는 한 번의 수입이 됩니다.
  - C는 왼쪽에서는 목표 1과 일관되지만, 오른쪽에서는 주된 경로가 유통량을 거쳐 준비금 수익으로 가므로 금리 의존을 줄이는 매출이 되지 않습니다 [제 판단].
- 맨 아래 판정 줄처럼, 결론은 어느 기준을 쓰느냐에 따라 달라집니다.

그림의 설계와 근거: figures/q6-04.md

### 3. 운영 층: 회사 스스로 적은 가장 큰 빈칸

- 가장 큰 빈칸은 회사 스스로 적은 운영 층입니다.
  - Beyond 글은 에이전트 결제를 기관 규모로 "authorize, govern, audit, and underwrite"할 인프라가 "still being created"라고 씁니다(45행).
  - Arc의 Agent Sector("verifiable agent identity and auditable records")는 로드맵 항목입니다(메인넷 보도자료 84, 86행).
  - 구제는 2-5에서 본 대로 Circle 바깥으로 옮겨졌습니다.

그림 6. 에이전트 결제의 두 층: 레일은 있고 운영 층은 짓는 중

한국어

```text
+-- 운영 층: 기관 규모의 에이전트 결제를 허가, 통제, 감사, 보증하는 장치
|   Beyond 글: "authorize, govern, audit, and underwrite" ...
|              "still being created"
|
|   회사가 내놓은 것                        상태
|   Arc Agent Sector: 검증 가능한           로드맵 항목
|     에이전트 신원, 감사 가능한 기록       (메인넷 보도자료 84, 86행)
|   구제: 잘못된 결제를 되돌리거나          Arc 고지문은 "absence of
|     보상받는 길                           recourse"를 위험으로 적음(114행).
|                                           2026년 자료에서는 표준, 견본 코드,
|                                           은행, 고지문으로 흩어짐(2번 답 2-5)
|
|   |  이 층이 갖춰지기 전에는 레일 위의 거래량이 늘기 어렵다
|   |  (Beyond 글: "volume will struggle to grow")
|   v
+-- 레일: 에이전트가 돈을 보내고 받는 길
|   Beyond 글: "The rails work and are being used at scale"
|   "Agents can pay"    H1 2026 - SHIPPED   (2분기 발표 자료 528행)
|   "Agents can earn"   H2 2026 - BUILDING  (같은 행)
+--
```

English

```text
+-- Operating layer: what lets institutions authorize, govern, audit and
|   underwrite agent payments at institutional volume
|   Beyond post: "authorize, govern, audit, and underwrite" ...
|                "still being created"
|
|   What the company has put forward        Status
|   Arc Agent Sector: verifiable agent      roadmap item
|     identity and auditable records        (mainnet release lines 84, 86)
|   Recourse: a way to reverse or be        Arc's disclaimer lists "absence of
|     compensated for a wrong payment       recourse" as a risk (line 114).
|                                           2026 materials spread it across
|                                           standards, sample code, banks and
|                                           disclaimers (answer 2, 2-5)
|
|   |  until this layer is built, volume on the rails will struggle to grow
|   |  (Beyond post: "volume will struggle to grow")
|   v
+-- Rails: the path agents use to send and receive money
|   Beyond post: "The rails work and are being used at scale"
|   "Agents can pay"    H1 2026 - SHIPPED   (Q2 presentation line 528)
|   "Agents can earn"   H2 2026 - BUILDING  (same line)
+--
```

그림 6은 라 절 3의 판단(가장 큰 빈칸은 운영 층)을 회사 자료의 말로 그린 것입니다.

- 아래층의 레일은 에이전트가 돈을 보내고 받는 길이고, 회사는 이 층이 작동한다고 적습니다(Beyond 글 45행).
  - "Agents can pay"는 출시되었고, "Agents can earn"은 짓는 중입니다(2분기 발표 자료 528행).
- 위층의 운영 층은 기관이 에이전트 결제를 허가하고 통제하고 감사하고 보증하는 장치입니다.
  - 같은 Beyond 글은 이 층이 "still being created"이고, 갖춰지기 전에는 거래량이 늘기 어렵다고 씁니다.
- 운영 층에서 레일로 내려가는 화살표가 이 조건입니다. 운영 층이 갖춰져야 레일 위의 거래량이 늘 수 있다는 뜻이고, 레일만으로는 기관 규모의 거래량이 오지 않는다는 회사 자신의 진단입니다.
- 운영 층 안의 두 줄은 회사가 내놓은 대응입니다.
  - Arc의 Agent Sector는 로드맵 항목입니다(메인넷 보도자료 84, 86행).
  - 구제는 Arc 고지문에 위험으로 적혀 있고(114행), 2026년 자료에서는 Circle 바깥의 표준, 견본 코드, 은행, 고지문으로 흩어졌습니다(2번 답의 2-5 절).
- 네 기능과 두 대응을 하나씩 짝짓지는 않았습니다. 회사 자료가 그렇게 짝짓지 않기 때문입니다.

그림의 설계와 근거: figures/q6-05.md

## 마. 7번으로 넘기는 것: 회사가 바라는 것과 비어 있는 칸

- 회사가 에이전트 갈래에서 바라는 것은 매출이 아니라 USDC와 Arc의 채택입니다(라 절). 4번 라 절의 말로 하면, Arc 쪽에서 에이전트는 "Arc를 쓸 이유"를 만들어야 하는 영역입니다.
- 회사 스스로 비었다고 적은 칸은 운영 층(허가, 통제, 감사, 보증)이고, 그 가운데 구제는 Circle 바깥에 맡겨져 있습니다.

## 한계

- CPN의 매출, CPN이 늘린 USDC 유통량, 에이전트가 쥔 USDC 잔액은 이번 자료에 숫자가 없습니다. 그래서 A와 C의 회사 쪽 판정은 "아직 판단할 수 없음"에 가깝습니다.
- 3분기 공시는 vault에 아직 들어와 있지 않습니다(`ls cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages | rg 'q3-2026'`, 일치 0건). CPN 수익화와 사전판매 매출 인식은 하반기의 일이므로, 이 답의 판정은 3분기 공시에서 다시 봐야 합니다.
- 주가, 밸류에이션, 투자 판단은 다루지 않았습니다. 질문은 회사의 방향이 맞는지이고, 투자 판단이 아닙니다.
- 사용자가 과거에 정리한 판단(09-21 방향, 에이전트 역할 정리 등)은 담지 않습니다. 처음 쓴 답의 마 절에는 7번의 판정 축(사용자의 과거 문서에서 이름을 지은 네 가지)을 미리 적은 항목이 하나 있었고, 2026-10-15에 뺐습니다(q6-report.md의 "과거 문서의 틀을 뺀 것(2026-10-15)").
- 경쟁사(다른 스테이블코인 발행사, 다른 L1)와의 비교는 2-1부터 2-4까지에서 에이전트 관점에 한해 했고, 사업 전체의 비교는 하지 않았습니다.

## 인용 위치

행 번호는 1부터 셉니다(`sed -n` 기준). 인용 안의 " / "는 원문의 줄바꿈입니다. 실적 콜 파일에는 폭 없는 공백이 들어 있어, 행 번호는 그것을 지운 뒤에도 같습니다.

| 인용한 곳 | 경로와 행 |
|---|---|
| 2분기 10-Q | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-10q.md:107-114, 784-786, 1323-1329, 1349-1351, 1383-1385, 1863-1866, 1885, 1895-1897, 1909-1911, 1917-1918, 1950-1953, 1984-1988, 2276, 2299-2306` |
| 2025년 10-K | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-fy2025-10k.md:511` |
| 2분기 실적 콜 | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-earnings-call-transcript.md:339-349, 353-354, 521, 527-533, 649-650, 654-660, 670-671, 878-879, 882-883, 886, 891, 897-898, 991-993` |
| 2분기 실적 보도자료 | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-earnings-release.md:88-92, 206-213, 219` |
| 2025년 4분기 실적 보도자료 | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q4-2025-earnings-release.md:42-46, 48-51` |
| 2025년 4분기 실적 콜 | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q4-2025-earnings-call-transcript.md:731-732` |
| 2분기 발표 자료 | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-earnings-presentation.md:528` |
| Circle 메인넷 보도자료 | `cb/works/web/2026-09-20-circle-arc-primary-sources/raw/circle-mainnet-launch.md:15, 17, 27, 32, 50, 84, 86, 114` |
| Agent Stack 출시 글 | `cb/works/web/2026-10-13-circle-agent-stack-sources/pages/circle-blog-introducing-agent-stack.txt:204, 209` |
| Circle Beyond 글 | `cb/works/circle-blog/undated-current-beyond-agentic-payments-the-operating-layer-for-the-agentic-economy/pages/beyond-agentic-payments-the-operating-layer-for-the-agentic-economy.en.md:45` |
| Nanopayments 테스트넷 출시 글 | `cb/works/circle-blog/2026-03-10-blog-circle-nanopayments-launches-on-testnet-as-the-core-primitive-for-agentic-economic-activity/pages/circle-nanopayments-launches-on-testnet-as-the-core-primitive-for-agentic-economic-activity.en.md:37` |
| Nanopayments 글 세 편(fee 검색) | 위 파일과 `cb/works/circle-blog/2026-03-20-blog-a-deep-dive-into-circle-nanopayments-gas-free-usdc-transfers/pages/a-deep-dive-into-circle-nanopayments-gas-free-usdc-transfers.en.md`, `cb/works/circle-blog/2026-04-29-blog-nanopayments-powered-by-circle-gateway-is-now-live-on-mainnet/pages/nanopayments-powered-by-circle-gateway-is-now-live-on-mainnet.en.md` |
| Arc 문서 Unified Balance 수수료 | `cb/works/web/2026-10-07-arc-official-library/pages/en/docs/app-kit/concepts/unified-balance-fees.md:34` |
