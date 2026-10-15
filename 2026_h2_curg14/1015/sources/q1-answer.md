# 1. Circle과 Arc가 해결하려는 문제와 솔루션은 무엇인가?

이 답은 2026-10-13 대화에서 보낸 두 답을 한 파일로 합친 뒤 여러 차례 고친 것입니다. 고친 순서는 다음과 같고, 고친 이유와 원래 문장은 마지막의 두 기록 절("뒤에서 고친 것", "사용자 피드백으로 고친 것")에 있습니다. 그 밖의 문장은 대화에서 보낸 내용 그대로입니다.

- 2026-10-13: 대화에서 답을 두 번에 나눠 보냈습니다(10:47:48Z와 11:02:18Z, UTC).
- 2026-10-14: 두 답을 한 파일로 합쳤습니다. 라 절(1-4)은 뒤의 답에서 다시 정리한 판으로 바꿨고, 마 절(고객별로 에이전트가 주는 도움)은 뒤의 답에서 가져왔습니다.
- 2026-10-14: 2번부터 6번까지를 쓰면서 고친 다섯 곳을 본문에 반영했습니다("뒤에서 고친 것" 절).
- 2026-10-14: 사용자 피드백 세 차례에 따라 가 절, 나 절, 다 절을 다시 쓰고 절마다 그림을 더했습니다("사용자 피드백으로 고친 것" 절의 1번부터 9번까지).
- 2026-10-15: 네 번째 피드백(ARC 가격, StableFX와 외환 비용)에 따라 나 절 3번과 다 절을 고쳤습니다(같은 절 10번과 11번).
- 2026-10-15: 다섯 번째 피드백(목차)에 따라 목차를 더하고 절과 소절의 제목을 다시 붙였습니다(같은 절 12번).
- 2026-10-15: 여섯 번째 피드백(한 줄 답의 모양)에 따라 한 줄 답을 실제 한 문장과 절별 요점으로 나누고, 목록이어야 할 긴 문단 여덟 곳을 목록과 표로 바꿨습니다(같은 절 13번).

## 목차

절 제목(가-바)은 이 답이 나눈 물음이고, 소절 제목은 그 소절의 답이나 내용을 줄인 것입니다. 절 줄의 링크 뒤 콜론에는 그 절의 답을 한 줄로 적었습니다. 괄호는 그 자리에 있는 그림과 표입니다.

- [한 줄 답](#한-줄-답)
- [읽는 법: 소질문의 구분, 표지의 뜻, 근거의 종류](#읽는-법-소질문의-구분-표지의-뜻-근거의-종류)
- [이 답의 지도: 고객에서 회사의 매출까지, 그리고 Arc의 자리](#이-답의-지도-고객에서-회사의-매출까지-그리고-arc의-자리) (그림 1)
- [가. 1-1 고객과 제품: Circle의 고객은 누구이고, 제품마다 어떤 문제를 푸는가?](#가-1-1-고객과-제품-circle의-고객은-누구이고-제품마다-어떤-문제를-푸는가): 고객은 금융기관, 기업, 개발자이고, 제품마다 겨냥하는 문제가 다릅니다.
  - [가-1. 제품 목록: Arc에 묶인 것은 Arc 자체, StableFX, App Kits의 Arc 쪽 기능 정도다](#가-1-제품-목록-arc에-묶인-것은-arc-자체-stablefx-app-kits의-arc-쪽-기능-정도다) (그림 2)
  - [가-2. 고객 다섯 부류: 해외 송금, 스테이블코인 운영 부담, 기관 환전, 결제 기능 구현, 에이전트의 돈 관리](#가-2-고객-다섯-부류-해외-송금-스테이블코인-운영-부담-기관-환전-결제-기능-구현-에이전트의-돈-관리)
- [나. 1-2 회사의 문제: Circle 회사 자신의 문제는 무엇인가?](#나-1-2-회사의-문제-circle-회사-자신의-문제는-무엇인가): 회사가 적은 목표는 준비금 수익을 키우면서 매출을 다변화하는 것이고, 제가 읽은 문제는 매출의 95.2%가 금리에 묶인 준비금 수익이라는 점입니다.
  - [나-1. 금리: 1%p가 움직이면 준비금 수익은 7.37억 달러, 비용을 뺀 차이는 3.77억 달러 움직인다](#나-1-금리-1p가-움직이면-준비금-수익은-737억-달러-비용을-뺀-차이는-377억-달러-움직인다) (그림 3)
  - [나-2. USDC 집중: 매출 쪽에서는 문제가 맞고, 제품 쪽에서는 절반만 맞다](#나-2-usdc-집중-매출-쪽에서는-문제가-맞고-제품-쪽에서는-절반만-맞다)
    - [USDC 중심 인프라라는 해석: 제품을 설명하는 틀로는 맞고, 돈이 도는 방향은 반대다](#usdc-중심-인프라라는-해석-제품을-설명하는-틀로는-맞고-돈이-도는-방향은-반대다) (그림 4)
  - [나-3. ARC 토큰: 가격이 10배가 되어도 금리 수입을 대신하기는 어렵다](#나-3-arc-토큰-가격이-10배가-되어도-금리-수입을-대신하기는-어렵다)
    - [커지는 것과 금리 1%p: 크기를 아는 것은 한 번뿐인 값이고, 반복될 수 있는 것은 크기를 모른다](#커지는-것과-금리-1p-크기를-아는-것은-한-번뿐인-값이고-반복될-수-있는-것은-크기를-모른다) (그림 5, 비교 표)
    - [가격별 크기: 10배면 보유분의 값은 연간 준비금 수익의 약 3년 치다](#가격별-크기-10배면-보유분의-값은-연간-준비금-수익의-약-3년-치다) (그림 6, 가격별 표)
- [다. 1-3 Arc와 고객의 문제: Arc는 고객의 어떤 문제를 푸는가?](#다-1-3-arc와-고객의-문제-arc는-고객의-어떤-문제를-푸는가): Arc에서만 얻는 기능(USDC로 내는 가스비, 빠른 확정, StableFX의 정산 장소)의 범위는 좁습니다. 고객 문제의 무게는 그와 따로 다-1부터 다-4까지에서 봅니다.
  - [다-1. 문제의 무게: 해외 지급의 비용, 속도, 위험은 무거운 문제다](#다-1-문제의-무게-해외-지급의-비용-속도-위험은-무거운-문제다)
  - [다-2. Arc가 맡는 몫: 문제마다 일부 구간에만 닿는다](#다-2-arc가-맡는-몫-문제마다-일부-구간에만-닿는다) (그림 7, 지도 표)
    - [시간: 전체 시간의 80% 넘게 쓰이는 마지막 구간에는 Arc가 닿지 않는다](#시간-전체-시간의-80-넘게-쓰이는-마지막-구간에는-arc가-닿지-않는다) (그림 8)
    - [비용: Arc는 가스비와 StableFX라는 두 길로 닿는다](#비용-arc는-가스비와-stablefx라는-두-길로-닿는다) (그림 9)
    - [외환 1.4%를 StableFX로 줄인다면: 채울 수 있는 숫자와 비어 있는 칸](#외환-14를-stablefx로-줄인다면-채울-수-있는-숫자와-비어-있는-칸) (계산)
    - [위험과 자금: Arc는 Circle 제품을 거쳐서만 닿는다](#위험과-자금-arc는-circle-제품을-거쳐서만-닿는다) (그림 10)
  - [다-3. 고객이 느끼는 중요도: 문제는 느끼지만, 스테이블코인으로 옮긴 기업은 아직 적다](#다-3-고객이-느끼는-중요도-문제는-느끼지만-스테이블코인으로-옮긴-기업은-아직-적다) (그림 11, 12)
  - [다-4. 확인하는 방법: 같은 조건에서 기존 방식과 전체 비용과 시간을 비교한다](#다-4-확인하는-방법-같은-조건에서-기존-방식과-전체-비용과-시간을-비교한다)
  - [다-5. 고객 쪽 정리: 문제는 무겁고 Arc는 그 일부에 닿지만, 도입은 다른 조건이 좌우한다](#다-5-고객-쪽-정리-문제는-무겁고-arc는-그-일부에-닿지만-도입은-다른-조건이-좌우한다)
- [라. 1-4 Arc와 회사의 문제: Arc는 Circle 회사의 어떤 문제를 푸는가?](#라-1-4-arc와-회사의-문제-arc는-circle-회사의-어떤-문제를-푸는가): 지금 실제로 들어온 돈은 한 번뿐인 토큰 사전판매입니다. 꾸준한 수입은 PoS 전환 뒤에 생기거나 금액이 공개되지 않아, 금리 의존은 아직 줄지 않습니다. (그림 13)
- [마. 고객별 에이전트: 에이전트는 고객마다 어떤 도움을 주는가?](#마-고객별-에이전트-에이전트는-고객마다-어떤-도움을-주는가): 에이전트 기능이 출시된 곳은 개발자, 파는 쪽, 개인 쪽이고, 금융기관과 기업 쪽은 예시와 로드맵 단계입니다. (그림 14)
- [바. 1-5 발표와 실제: 발표한 것과 실제로 낸 것은 어디서 어긋나는가?](#바-1-5-발표와-실제-발표한-것과-실제로-낸-것은-어디서-어긋나는가): Arc 프라이버시, Agent Stack의 구성 수, 계획 단계인 Arc의 세 부문과 에이전트가 돈을 버는 기능, 아직 쓸 수 없는 에이전트 제품 3개, 테스트넷에만 배포하는 Arc Studio에서 어긋납니다. StableFX의 베타 표기는 2026년 자료에서 빠졌습니다.

답 뒤에 붙인 것:

- [1번의 결과를 다음 질문에서 쓰는 곳](#1번의-결과를-다음-질문에서-쓰는-곳)
- [한계](#한계)
- [뒤에서 고친 것](#뒤에서-고친-것)
- [사용자 피드백으로 고친 것](#사용자-피드백으로-고친-것)
  - [첫 번째 피드백(2026-10-14): 제품 목록, 금리와 토큰, 고객 문제의 전제](#첫-번째-피드백2026-10-14-제품-목록-금리와-토큰-고객-문제의-전제)
  - [두 번째 피드백(2026-10-14): 시각화, 외부 조사, USDC 중심 인프라](#두-번째-피드백2026-10-14-시각화-외부-조사-usdc-중심-인프라)
  - [세 번째 피드백(2026-10-14): 그림 열셋, 다 절 그림, USDC 그림](#세-번째-피드백2026-10-14-그림-열셋-다-절-그림-usdc-그림)
  - [네 번째 피드백(2026-10-15): ARC 가격, StableFX와 외환 비용](#네-번째-피드백2026-10-15-arc-가격-stablefx와-외환-비용)
  - [다섯 번째 피드백(2026-10-15): 목차](#다섯-번째-피드백2026-10-15-목차)
  - [여섯 번째 피드백(2026-10-15): 한 줄 답의 모양](#여섯-번째-피드백2026-10-15-한-줄-답의-모양)
- [인용 위치](#인용-위치)

## 한 줄 답

[제 판단] Circle은 제품으로 고객의 지급 문제를 겨냥하지만 회사의 매출은 금리에 묶인 USDC 준비금 수익이고, Arc는 고객의 문제에도 회사의 문제에도 아직 일부만 닿습니다.

이 한 문장을 절마다 나누면 다음과 같습니다.

- 고객과 제품(가 절)
  - Circle은 사업을 세 기둥으로 나눕니다: Arc와 개발자 인프라, 스테이블코인과 유동성 인프라, CPN과 StableFX 같은 애플리케이션입니다.
  - 고객은 금융기관, 기업, 개발자입니다.
  - 제품마다 겨냥하는 고객 문제가 다릅니다: 해외 송금, 스테이블코인 운영 부담, 기관 환전, 결제 기능 구현, 에이전트의 돈 관리입니다.
- 회사의 문제(나 절)
  - 회사가 스스로 적은 목표는 준비금 수익을 키우면서 매출을 다변화하는 것입니다.
  - 저는 매출의 95.2%가 금리에 묶인 준비금 수익이라는 점을 회사의 문제로 읽었습니다.
  - 회사 공시에 따르면 금리가 1%p 바뀌면 12개월 동안 준비금 수익은 7.37억 달러, 유통과 거래 비용은 3.6억 달러 바뀝니다.
  - 매출이 사실상 USDC 하나에서 나오므로, USDC 의존과 금리 의존은 같은 문제의 두 면입니다.
  - ARC 가격이 사전판매 가격의 10배가 되면 Circle 보유분의 값은 연간 준비금 수익의 약 3년 치여서 무시할 수 없는 크기입니다. 그래도 한 번 매기는 값이어서 해마다 들어오는 금리 수입을 대신하기는 어렵다고 판단합니다.
- Arc와 고객의 문제(다 절)
  - Arc에서만 얻는 기능의 범위는 좁습니다: USDC로 내는 가스비, 빠른 확정, StableFX의 정산 장소입니다.
  - 다만 고객의 문제 자체는 무겁습니다.
  - 중소기업 B2B 해외 지급의 평균 비용 1.6% 가운데 외환 1.4%에는 Arc에서 정산하는 StableFX를 거쳐 간접으로 닿습니다. StableFX의 가격과 수수료가 공개되지 않아, 얼마나 줄어드는지는 아직 계산할 수 없습니다.
  - 공개 조사 여덟 건을 보면 기업은 해외 지급의 비용과 지연을 문제로 느낍니다. 그러나 스테이블코인으로 옮기는 결정은 규제, 은행과 ERP 연동, 회계가 좌우하고, 빠른 정산은 앞순위가 아닙니다.
- Arc와 회사의 문제(라 절)
  - Arc가 지금 회사에 실제로 가져온 돈은 한 번 들어오는 토큰 사전판매입니다.
- 고객별 에이전트(마 절)
  - 에이전트 기능이 실제로 출시된 곳은 개발자, API와 데이터를 파는 쪽, 개인 쪽입니다.
  - Circle 매출과 가까운 금융기관과 기업 쪽은 아직 예시와 로드맵 단계입니다.
- 발표와 실제(바 절)
  - Arc 프라이버시, Agent Stack의 구성 수, 계획 단계인 Arc의 세 부문과 에이전트가 돈을 버는 기능, 아직 쓸 수 없는 에이전트 제품 3개, 테스트넷에만 배포하는 Arc Studio에서 발표와 실제가 어긋납니다.

## 읽는 법: 소질문의 구분, 표지의 뜻, 근거의 종류

소질문을 다섯 개(1-1부터 1-5까지)로 나눈 것과 마 절 표의 열은 제 구분입니다. 고객의 문제와 회사의 문제를 나눈 것은 사용자가 picker로 고른 방식("고객의 문제와 회사의 문제를 나눠서 (추천)")입니다. 마 절은 사용자의 요청("지금 너가 얘기하는 고객들에게 에이전트가 어떤 도움을 줄건지도 정리할 것")에 따라 더했습니다.

표지의 뜻은 다음과 같습니다.

| 표지 | 가리키는 근거 |
|---|---|
| [공시] | 10-K와 10-Q |
| [Circle 글] | Circle과 Arc의 백서, 발표문, 블로그 |
| [Circle 발언] | 2분기 애널리스트 콜에서 CEO와 CFO가 한 말 |
| [Team Arc 글] | Arc 개발 문서 |
| [답] | AI 답변의 주장 |
| [제 판단] | 제가 내린 판단 |

근거의 종류는 절마다 다릅니다.

- 가 절부터 다 절까지와 바 절: 근거의 대부분이 vault의 2차 문서(survey, why, kit, products)이고, 그 절의 [공시]와 [Circle 글] 표지는 해당 문서가 원문과 대조해 붙인 것입니다. 다만 나 절의 회사 목표 문장과 바 절의 세 행(StableFX, Agent Stack 구성, Arc Studio)은 뒤에서 1차 자료로 바꿨습니다.
- 2026-10-14에 다시 쓴 부분(가 절의 제품 목록, 나 절의 근거와 세 소절, 다 절): 1차 자료(2분기와 1분기 10-Q, 제품 페이지, Arc 개발 문서, 토큰 백서, FSB, BIS, SWIFT 자료)를 직접 열었고, 연구 원고 01, 04, 06도 함께 썼습니다. 연구 원고는 2차 문서이므로 원고의 판단을 인용할 때는 원고의 판단이라고 밝혔습니다.
- 라 절과 마 절: 1차 자료를 직접 열었습니다.

약칭이 가리키는 파일은 인용 위치 표에 있습니다.

## 이 답의 지도: 고객에서 회사의 매출까지, 그리고 Arc의 자리

아래 그림은 이 답 전체의 지도입니다. 고객, 제품, 회사의 매출이 어떻게 이어지는지와 Arc가 그 안에서 어디에 있는지를 보여 줍니다. 각 칸 옆의 절 이름은 그 내용을 자세히 다루는 절입니다.

```text
[한국어판] 그림 1. 1번 답의 지도: 고객에서 회사의 매출까지, 그리고 Arc의 자리

  고객 (가 절)
  금융기관, 기업, 개발자
     |
     | 쓴다
     v
  제품 (가 절): 세 기둥
  (i) Arc와 개발자 인프라  (ii) 스테이블코인과 유동성  (iii) CPN, StableFX
     |
     +--- 유통량을 늘린다 ---> USDC 유통량 (나 절)
     |                            |
     |                            | x 수익률 (SOFR에 가까운 단기 금리)
     |                            v
     |                         준비금 수익: 매출의 95.2%
     |
     +--- 직접 번다 --------> 기타 매출: 매출의 4.8-5.4%

  Arc의 자리
    고객에게 (다 절): 해외 지급 경로 가운데 기관 사이 전송 한 구간
    회사에게 (라 절): 토큰 사전판매 약 2.42억 달러, 한 번 들어오는 돈
```

```text
[English] Figure 1. Map of answer 1: from customers to Circle's revenue, and where Arc sits

  Customers (section ga)
  Financial institutions, businesses, developers
     |
     | use
     v
  Products (section ga): three pillars
  (i) Arc and developer infra  (ii) stablecoins and liquidity  (iii) CPN, StableFX
     |
     +--- grow circulation ---> USDC in circulation (section na)
     |                             |
     |                             | x return rate (short-term rate near SOFR)
     |                             v
     |                          Reserve income: 95.2% of revenue
     |
     +--- earn directly ------> Other revenue: 4.8-5.4% of revenue

  Where Arc sits
    For customers (section da): one segment of the cross-border path
                                (the institution-to-institution transfer)
    For Circle (section ra): token pre-sale of about USD 242 million, money that arrives once
```

그림은 위에서 아래로 읽습니다. 고객이 제품을 쓰면 두 갈래로 돈이 됩니다. 하나는 제품이 USDC 유통량을 늘리고, 유통량에 수익률을 곱한 준비금 수익이 매출의 95.2%가 되는 갈래입니다. 다른 하나는 제품이 직접 버는 기타 매출이고, 매출의 4.8-5.4%입니다. 두 갈래의 비중 차이가 나 절의 판단(매출이 금리에 묶여 있다)의 출발점입니다.

Arc는 제품 가운데 하나이지만, 고객과 회사에게 주는 것이 달라서 아래에 따로 적었습니다. 고객에게는 해외 지급 경로의 한 구간(다 절)이고, 회사에게는 지금까지 한 번 들어온 토큰 판매 대금입니다(라 절). 고객이 제품을 쓰는 이유(가 절)와 고객이 문제를 얼마나 중요하게 여기는지(다 절 3번)는 이 지도에 넣지 않았습니다. 아래 절의 그림이 이 지도의 각 칸을 자세히 그립니다.

## 가. 1-1 고객과 제품: Circle의 고객은 누구이고, 제품마다 어떤 문제를 푸는가?

고객은 금융기관, 기업, 개발자로 나뉘고, 제품마다 겨냥하는 문제가 다릅니다. 이 절은 2026-10-14 사용자 피드백("Circle이 주도하는 제품들을 다시 리스팅하고 다시 제시")에 따라 2분기 10-Q의 제품 목록에서 다시 시작했습니다.

### 가-1. 제품 목록: Arc에 묶인 것은 Arc 자체, StableFX, App Kits의 Arc 쪽 기능 정도다

2분기 10-Q는 사업을 세 기둥(pillar)으로 나눕니다 [공시] (10-Q 1863-1869행). (i) Arc와 개발자 및 상호운용 인프라, (ii) USDC, EURC, USYC, cirBTC와 이를 받치는 유동성 인프라(Circle Mint, xReserve), (iii) CPN과 StableFX 같은 애플리케이션입니다. 회사는 세 기둥이 "designed to reinforce one another"라고 적습니다(1866행). 아래 표의 기둥과 행은 이 분류와 10-Q의 제품 목록(1898-1911행)을 따랐고, 목록에 없는 제품 둘은 맨 아래에 따로 두었습니다.

열은 제가 정했습니다. "주 고객"과 "Arc와의 관계"는 제가 붙인 구분입니다. "겨냥하는 문제"는 원문이 문제나 목적을 직접 적은 경우 원문을 인용했고, 원문이 기능만 적은 경우 "기능 설명"이라고 표시했습니다. 10-Q는 (i) 기둥의 개발자 도구와 상호운용 서비스 전체의 목적을 한 문장으로 적습니다: "designed to reduce complexity and help developers and enterprises build and operate onchain applications that move value across networks"(1901-1902행). 표에서는 이 문장을 "(i) 공통 목적"이라고 줄여 적습니다.

| 기둥         | 제품                                                                     | 주 고객                            | 겨냥하는 문제                                                                                                                                                                                                                                                                                          | Arc와의 관계                                                                                                    | 근거                                                       |
| ------------ | ------------------------------------------------------------------------ | ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| (i)          | Arc                                                                      | 기관, 앱 개발자                    | 가스 토큰 가격에서 생기는 비용 변동, 확률적 최종성 때문에 확인을 기다리는 시간, 공개 거래 자료로 드러나는 금융 정보입니다. 제공자가 밝힌 설계 취지이며 측정한 결과가 아닙니다(04 1123행).                                                                                                              | 그 자체입니다.                                                                                                  | 10-Q 1899행, 04 1123행                                     |
| (i)          | Agent Stack (Agent Wallets, Nanopayments, Agent Marketplace, Circle CLI) | 에이전트를 만드는 개발자           | (i) 공통 목적. 기능 설명: 에이전트의 지갑과 지급입니다.                                                                                                                                                                                                                                                | Arc 없이도 동작합니다. Agent Wallets는 9개 체인을 지원하고, Arc 메인넷 지원은 2026-09-16에 더해졌습니다.        | 10-Q 1900행, products 210행                                |
| (i)          | App Kits                                                                 | 앱 개발자                          | (i) 공통 목적. 기능 설명: 체인마다 저수준 연동을 따로 조합하지 않고 여러 체인의 지급과 유동성 흐름을 구성하는 SDK 모음입니다(Send, Bridge, Swap, Unified Balance, Onramp, Earn, Borrow).                                                                                                               | 여러 체인용입니다. Arc에서는 Swap이 USDC, EURC, cirBTC를 교환하고, Borrow가 cirBTC를 담보로 USDC를 빌려 줍니다. | 10-Q 1900-1901행, 01 739, 745, 749행                       |
| (i)          | Circle Wallets                                                           | 앱 개발자, 기업                    | (i) 공통 목적. 기능 설명: 서명 승인과 거래 제출입니다.                                                                                                                                                                                                                                                 | 이번에 확인하지 않았습니다.                                                                                     | 10-Q 1901행, 01 719행                                      |
| (i)          | Circle Contracts                                                         | 앱 개발자                          | (i) 공통 목적. 기능 설명은 이번 자료에서 확인하지 않았습니다.                                                                                                                                                                                                                                          | 이번에 확인하지 않았습니다.                                                                                     | 10-Q 1901행                                                |
| (i)          | CCTP                                                                     | 앱 개발자, 기관                    | (i) 공통 목적. 기능 설명: 체인 사이의 소각과 발행입니다.                                                                                                                                                                                                                                               | 여러 체인을 잇는 장치입니다.                                                                                    | 10-Q 1901행, 01 721행                                      |
| (i)          | Gateway                                                                  | 앱 개발자                          | (i) 공통 목적. 기능 설명: 예치한 USDC를 지원 체인에서 쓰는 통합 잔액입니다.                                                                                                                                                                                                                            | 여러 체인을 잇는 장치입니다.                                                                                    | 10-Q 1901행, 01 722행                                      |
| (ii)         | USDC, EURC                                                               | 기관, 거래소, 앱 사용자            | 기능 설명: 달러와 유로 표시 스테이블코인입니다. 매출 쪽에서 EURC 준비금은 "held only in cash at banks and not material"입니다(2673행).                                                                                                                                                                 | Arc의 가스는 USDC로만 냅니다. EURC는 Arc에 처음부터 배포되어 있습니다.                                          | 10-Q 1864행, stablecoin-native-model 12, 92-94, 132-137행  |
| (ii)         | USYC                                                                     | 미국 밖의 기관(최소 10만 달러)     | "intended primarily for use as collateral in digital asset markets, providing yield to token holders"                                                                                                                                                                                                  | Arc에 처음부터 배포된 자산입니다.                                                                               | 10-Q 1903-1905행, stablecoin-native-model 92-94, 111-112행 |
| (ii)         | cirBTC                                                                   | 기관, 앱 사용자                    | 기능 설명: 회사가 발행하고 같은 양의 BTC로 "fully backed"인 토큰입니다.                                                                                                                                                                                                                                | App Kits의 Swap과 Borrow가 Arc에서 cirBTC를 다룹니다. 실제 보관과 상환 구조는 확인되지 않았습니다(01 515행).    | 10-Q 126-127행, 01 515행                                   |
| (ii)         | Circle Mint                                                              | 기관                               | 기능 설명: "minting, redeeming, and moving USDC and EURC"입니다.                                                                                                                                                                                                                                       | 이번에 확인하지 않았습니다.                                                                                     | 10-Q 1906-1907행                                           |
| (ii)         | xReserve                                                                 | 자기 스테이블코인을 내려는 개발자  | "enabling third-party developers to deploy USDC-interoperable stablecoins"                                                                                                                                                                                                                             | 확인하지 않았습니다. 연구 원고에도 보존한 제품 문서가 없습니다(01 723행).                                       | 10-Q 1907-1908행                                           |
| (iii)        | CPN                                                                      | 은행, PSP, 기업                    | "connects eligible financial institutions to facilitate near-instant, 24/7/365 payment settlement"(10-Q). 제품 페이지는 "Enter new markets faster without having to integrate locally or negotiate complex bilateral agreements"와 "Eliminate the need for prefunding local nostro accounts"를 듭니다. | 지원 체인 넷(Arc, Ethereum, Polygon PoS, Solana) 가운데 하나입니다.                                             | 10-Q 1909-1910행, cpn-product 66-67행, 04 1155행           |
| (iii)        | StableFX                                                                 | 기관                               | "an institutional stablecoin foreign exchange engine built on Arc that supports onchain settlement and configurable escrow-based trade settlement"(10-Q). 제품 페이지는 "Eliminate T+2 settlement delays and counterparty risk"라고 적습니다.                                                          | Arc 위에서 실행됩니다. 두 통화를 함께 인도하는 `FxEscrow` 계약이 Arc에서 돌아갑니다.                            | 10-Q 1910-1911행, stablefx-overview 81행, 04 1108행        |
| 10-Q 목록 밖 | CPN Managed Payments                                                     | 블록체인을 직접 다루기 어려운 기업 | "stablecoin settlement without needing in-house custody, compliance, or onchain systems"                                                                                                                                                                                                               | 지원 체인 목록에 Arc가 있습니다.                                                                                | cpn-managed 24-25행, 04 1109행                             |
| 10-Q 목록 밖 | Refund Protocol                                                          | 상거래 사업자                      | "Stablecoin payments, however, have no refund or chargeback mechanisms."                                                                                                                                                                                                                               | Arc의 상거래 안내가 비슷한 조건부 보관 계약 사례(`arc-escrow`)를 연결합니다.                                    | refund-protocol 39행, 04 1110행                            |

- 마지막 두 행은 근거가 공시가 아니라 Circle의 제품 페이지입니다 [Circle 글].
- 제품마다 운영하는 법인은 연구 원고 01의 표(01 716-727행)에 있습니다. 예를 들어 Arc 메인넷은 Arc Network Services LLC가, Wallets, StableFX, CPN은 Circle Technology Services, LLC가 맡습니다.
- [제 판단] 표에서 Arc에 묶여 있는 것은 Arc 자체, StableFX, App Kits의 Arc 쪽 기능(cirBTC를 다루는 Swap과 Borrow) 정도입니다. 나머지는 여러 체인에서 쓰도록 만들어졌거나, 이번에 Arc와의 관계를 확인하지 않았습니다.

위 표의 "Arc와의 관계" 열을 묶어 그리면 다음과 같습니다. 네 묶음은 제가 정한 구분입니다.

```text
[한국어판] 그림 2. Circle 제품과 Arc: Arc에 묶인 것과 아닌 것

  Arc에 묶여 있음
    Arc 자체
    StableFX                 FxEscrow 계약이 Arc에서 실행
    App Kits의 Arc 쪽 기능   Swap(USDC, EURC, cirBTC), Borrow(cirBTC 담보로 USDC)

  Arc 위에 처음부터 배포된 자산
    USDC, EURC, USYC         Arc의 가스는 USDC로만 냄

  Arc를 포함한 여러 체인에서 씀
    CPN                      지원 체인 넷(Arc, Ethereum, Polygon PoS, Solana)
    CPN Managed Payments     지원 체인 목록에 Arc가 있음
    Agent Stack              9개 체인, Arc 메인넷 지원은 2026-09-16에 추가
    App Kits, CCTP, Gateway  여러 체인용

  Arc와의 관계를 이번에 확인하지 않음
    Circle Wallets, Circle Contracts, Circle Mint, xReserve
    Refund Protocol          Arc 안내가 비슷한 계약 사례를 연결할 뿐
```

```text
[English] Figure 2. Circle products and Arc: what is tied to Arc and what is not

  Tied to Arc
    Arc itself
    StableFX                     the FxEscrow contract runs on Arc
    Arc-side App Kits functions  Swap (USDC, EURC, cirBTC), Borrow (USDC against cirBTC)

  Assets deployed on Arc from genesis
    USDC, EURC, USYC             gas on Arc is paid only in USDC

  Used on several chains, Arc among them
    CPN                          four supported chains (Arc, Ethereum, Polygon PoS, Solana)
    CPN Managed Payments         Arc is on its supported-chain list
    Agent Stack                  9 chains; Arc mainnet support added 2026-09-16
    App Kits, CCTP, Gateway      multi-chain

  Relation to Arc not checked this time
    Circle Wallets, Circle Contracts, Circle Mint, xReserve
    Refund Protocol              Arc's guide only links a similar contract example
```

이 그림은 바로 위 bullet의 판단("표에서 Arc에 묶여 있는 것은 Arc 자체, StableFX, App Kits의 Arc 쪽 기능 정도")을 보이게 하려고 그렸습니다. 표는 제품마다 한 줄씩 적어서, Arc 없이는 돌아가지 않는 제품이 몇 개인지 한눈에 보이지 않습니다. 그래서 표의 행을 Arc에 기대는 정도로 다시 묶었습니다. 이 그림은 맨 위 지도의 "제품" 칸을 Arc 쪽에서 자세히 본 것입니다.

첫 묶음의 셋만 Arc가 없으면 쓸 수 없습니다. 두 번째 묶음은 Arc에 올라 있는 자산이고, 세 번째 묶음은 Arc를 여러 선택지 가운데 하나로 둡니다. 네 번째 묶음은 "관계가 없다"는 뜻이 아니라 이번에 확인하지 않았다는 뜻입니다.

### 가-2. 고객 다섯 부류: 해외 송금, 스테이블코인 운영 부담, 기관 환전, 결제 기능 구현, 에이전트의 돈 관리

위 표를 고객 쪽에서 묶으면 다음 다섯 부류가 됩니다. 3번, 5번, 6번은 이 다섯 부류를 그대로 씁니다. 이 표는 대화에서 처음 보낸 그대로 두었고, 근거 칸의 survey 행은 그때 대조한 것입니다.

| 고객                               | 겨냥하는 문제                                                 | 제품                    | 근거                                                                                      |
| ---------------------------------- | ------------------------------------------------------------- | ----------------------- | ----------------------------------------------------------------------------------------- |
| 은행, PSP, 기업                    | 해외 송금                                                     | CPN                     | [공시] "move money using stablecoins starting with cross-border payments" (survey 1125행) |
| 블록체인을 직접 다루기 어려운 기업 | 스테이블코인 운영 부담                                        | Managed Payments        | [Circle 글] Circle이 전환, 지갑, 유동성, 규제 준수를 맡습니다 (survey 1143행)             |
| 기관                               | 환전할 때 상대방마다 계약과 신용 한도를 따로 정해야 하는 부담 | StableFX                | [공시] (survey 1186행)                                                                    |
| 앱 개발자                          | 결제와 이동 기능을 직접 구현하는 부담                         | App Kits 등 개발자 도구 | 메인넷을 지원하며 Arc 전용이 아닙니다 (kit 87-88행)                                       |
| 에이전트를 만드는 개발자           | 에이전트가 독립된 경제 주체로 움직일 수단                     | Agent Stack             | [공시] (survey 1216행)                                                                    |

이 표의 "겨냥하는 문제" 칸은 제가 붙인 말입니다. 다만 CPN, StableFX, Agent Stack은 공시가 목적을 직접 적었으므로 그 내용을 따랐습니다. Agent Stack은 1번에서 제품 하나로만 다루고, 에이전트 이야기는 2번과 3번으로 넘기기로 제가 정했습니다. 그 뒤 사용자의 요청으로 마 절을 더했습니다.

## 나. 1-2 회사의 문제: Circle 회사 자신의 문제는 무엇인가?

회사가 스스로 적은 목표와 제가 읽은 문제를 나눠 적습니다.

- 회사의 목표: 2분기 10-Q는 새 제품에 대해 두 가지를 적습니다. 네트워크가 커지면 USDC 유통량이 늘어 "thereby drive our reserve income"이 되고, 이 제품들을 키워 "diversifying our revenue profile"을 하겠다는 것입니다 [공시] (10-Q 1896-1897행). 회사의 목표는 금리 의존을 줄이는 것이 아니라 준비금 수익을 키우면서 매출을 다변화하는 것입니다.
- 제가 읽은 문제 [제 판단]: 매출이 금리에 묶여 있다는 점입니다. 회사는 이것을 목표로 적지 않았지만, 10-Q의 시장 위험 항목(Interest rate risk)에서 금리 변화가 준비금 수익과 유통 비용을 바꾼다고 공시합니다(10-Q 2817-2835행). 사용자도 2026-10-14에 이 판단을 받아들였습니다("매출이 금리에 묶여있다는 것은 오케이"). 근거는 아래와 같습니다.

- 2026년 2분기 매출은 7억 131만 5천 달러이고, 그중 준비금 수익이 6억 6,773만 달러로 95.2%를 차지합니다. 기타 매출은 3,358만 달러입니다 [공시] (10-Q 2274-2276행, 1885행).
- 준비금 수익은 "a function of (i) our stablecoins in circulation over a given period and (ii) the reserve return rate"이고, 수익률은 "close to the prevailing SOFR"입니다 [공시] (10-Q 1886-1889행).
- 같은 분기의 준비금 수익은 1년 전보다 3,350만 달러(5.3%) 늘었습니다. USDC 일평균 유통량이 25.2% 늘어 1억 4,740만 달러를 더했지만, 평균 수익률이 66bp 내려 1억 1,390만 달러를 깎았습니다(147.4 - 113.9 = 33.5) [공시] (10-Q 2299-2302행).
- 유통, 거래와 기타 비용은 4억 1,247만 달러로 매출의 58.8%입니다(412,470 / 701,315, 10-Q 2280, 2276행). 10-Q의 RLDC 마진 41%(2059행)는 100%에서 이 비율을 뺀 값과 맞습니다.
- 세 AI 답변이 각자 같은 결론을 냈습니다. "제품은 넓어졌지만 돈은 아직 USDC 준비금의 이자에서 나온다" [답] (survey 415행).
- 회사의 목표로 보면 1-1의 제품 확장은 준비금 수익을 키우면서 매출을 다변화하려는 시도입니다. 확장이 금리 의존을 줄이는지는 제 기준입니다. 그래서 6번은 회사의 방향을 회사가 적은 두 목표로 판정하고, 금리 의존은 제 해석으로 한 줄만 두었습니다(q6-answer.md 나 절).

아래 세 소절은 2026-10-14 사용자 피드백의 세 물음(금리가 오르내리면 어떻게 되는가, USDC 하나로 모든 것을 하려는 것도 문제인가, ARC 토큰의 가치가 커지면 어떻게 되는가)에 하나씩 답합니다.

### 나-1. 금리: 1%p가 움직이면 준비금 수익은 7.37억 달러, 비용을 뺀 차이는 3.77억 달러 움직인다

10-Q는 금리가 바뀔 때 다음 12개월의 준비금 수익과 유통 및 거래 비용이 얼마나 바뀌는지 회사 내부 모델로 계산해 공시합니다 [공시] (10-Q 2828-2842행). 가정은 세 가지입니다. USDC 유통량은 2026-06-30 수준에 머물고, 금리는 2026-07-01에 바뀐 뒤 12개월 동안 그대로이며, 준비자산의 배분은 바뀌지 않습니다(2830-2834행).

| 금리 변화 (2026년 6월 평균 수익률 3.49% 기준) | 준비금 수익 | 유통과 거래 비용 | 둘의 차이 [제 계산] |
| --------------------------------------------- | ----------- | ---------------- | ------------------- |
| +200bp                                        | +1,475      | +720             | +755                |
| +100bp                                        | +737        | +360             | +377                |
| -100bp                                        | -737        | -360             | -377                |
| -200bp                                        | -1,475      | -720             | -755                |

단위는 백만 달러이고, 앞의 두 열은 10-Q 2837-2842행 그대로입니다. "둘의 차이"는 표의 두 열만 뺀 값입니다. 운영비와 세금은 넣지 않았으므로 이익의 변화가 아닙니다.

이 표에서 읽은 것은 다섯 가지입니다. 다섯으로 나눈 것은 제 구분입니다.

1. 비용이 수익 변화의 절반쯤을 함께 움직입니다. 360 / 737 = 48.8%입니다. 회사는 준비금 수익이 "a contributor to distribution and transaction costs"라고 적습니다(2821-2822행). 그래서 금리가 1%p 내리면 준비금 수익은 7.37억 달러 줄지만, 두 열의 차이로 보면 3.77억 달러가 줄어듭니다.
2. 금리 1%p는 준비금 수익의 약 28.7%입니다. 표의 737은 6월 30일 USDC 유통량 732.69억 달러(10-Q 2051행)의 1%인 7.33억 달러와 거의 같습니다. 같은 기준에서 3.49% 수익률의 연간 준비금 수익은 737 × 3.49 = 2,572백만 달러이고, 1%p 하락은 그 1 / 3.49 = 28.7%입니다. 이 2,572는 2분기 실제 준비금 수익을 네 배 한 2,671백만 달러(667.7 × 4)와 다릅니다. 표는 6월 30일 유통량을 기준으로 하고, 2분기 실제 값은 분기 평균 유통량 765.24억 달러(2052행)에서 나왔기 때문입니다. 765.24억 달러 × 3.49% = 26.71억 달러이므로 두 값은 서로 맞습니다.
3. 금리 1%p 하락을 유통량으로 메우려면 유통량이 40% 늘어야 합니다. 수익률이 3.49%에서 2.49%로 내리면 같은 준비금 수익을 내는 데 필요한 유통량은 3.49 / 2.49 = 1.40배입니다. 2분기의 실제 흐름(유통량 +25.2%, 수익률 -66bp, 준비금 수익 +5.3%)이 이 경주를 보여 줍니다.
4. USDC가 커질수록 금리 1%p가 움직이는 금액도 커집니다. 1년 전 표(2025년 6월 4.26% 기준)의 +100bp 값은 618이고, 올해는 737입니다(2844-2849행). 두 표 모두 "그 시점의 유통량 × 1%"이므로 737 / 618 = 1.193은 두 시점의 유통량 비율에 해당하고, 기말 유통량의 실제 비율 73,269 / 61,333 = 1.195(2051행)와 맞습니다. 그러므로 유통량이 늘어나는 것은 금리 의존을 줄이지 않고, 금리가 움직이는 금액을 키웁니다.
5. 금리가 USDC 수요를 바꾸는 경로는 표에 들어 있지 않습니다. 회사는 금리가 오른다고 유통량이 반드시 줄지는 않고("an increase in interest rates does not necessarily result in a decrease in USDC in circulation (and vice versa)"), 둘의 관계는 "complex, highly uncertain, and unproven"이라고 적습니다(2826-2827행). 최근에 정리한 금리 문서도 높은 금리가 USDC 수요 감소로 "기계적으로 이어지지는 않는다"고 적고(guide 274행), 경기나 시장 악화에 대응한 인하라면 "자산 가격 하락과 변동성 확대가 함께 일어날 수도 있다"고 적습니다(guide 278행). 그러므로 금리가 내릴 때 유통량이 늘어 빈자리를 메워 준다는 보장은 없습니다.

위 표와 다섯 가지 읽기를 금리 1%p 하락 한 경우로 따라가면 다음과 같습니다.

```text
[한국어판] 그림 3. 금리 1%p가 내릴 때: 공시 표에서 남는 몫까지

  출처: 2분기 10-Q 2837-2842행. 기준은 2026년 6월 평균 수익률 3.49%, 12개월, 단위 백만 달러
  가정: USDC 유통량은 2026-06-30 수준(732.69억 달러)에 머문다

  금리 -1%p
     |
     v
  준비금 수익          -737   (유통량 732.69억 달러의 약 1%)
     |
     | 유통 파트너에게 가던 몫도 함께 줄어든다: 360 / 737 = 48.8%
     v
  유통과 거래 비용     -360
     |
     v
  두 열의 차이         -737 - (-360) = -377
                       (운영비와 세금을 빼기 전이므로 이익의 변화가 아님)

  메우려면     같은 준비금 수익에 필요한 유통량 = 3.49 / 2.49 = 1.40배
  커지는 이유  +100bp 값이 1년 전 618에서 737로: 737 / 618 = 1.193
               같은 기간 기말 유통량 61,333에서 73,269로: 1.195
```

```text
[English] Figure 3. When the rate falls by 1 percentage point: from the disclosed table to what is left

  Source: Q2 10-Q lines 2837-2842. Base: June 2026 average return 3.49%, 12 months, USD millions
  Assumption: USDC in circulation stays at the 2026-06-30 level (USD 73,269 million)

  Rate -1 pp
     |
     v
  Reserve income                       -737   (about 1% of USD 73,269 million in circulation)
     |
     | the share paid to distribution partners falls with it: 360 / 737 = 48.8%
     v
  Distribution and transaction costs   -360
     |
     v
  Gap between the two columns          -737 - (-360) = -377
                                       (before opex and tax, so not a profit change)

  To offset     circulation needed for the same reserve income = 3.49 / 2.49 = 1.40x
  Why it grows  the +100bp value rose from 618 a year earlier to 737: 737 / 618 = 1.193
                period-end circulation rose from 61,333 to 73,269: 1.195
```

이 그림은 계산 도식입니다. 표의 네 행 가운데 -100bp 한 행을 골라, 숫자가 어디서 오고 어디로 가는지 순서대로 적었습니다. 표만 보면 준비금 수익 -737과 비용 -360이 나란히 있어서, 비용이 수익 변화의 절반쯤을 함께 움직인다는 점(읽기 1)과 그 결과 남는 몫이 -377이라는 점이 잘 보이지 않습니다.

아래 두 줄은 읽기 3과 4입니다. 1%p 하락을 유통량으로 메우려면 유통량이 1.40배가 되어야 합니다. 그리고 유통량이 커질수록 1%p가 움직이는 금액도 커집니다. 금리가 USDC 수요를 바꾸는 경로(읽기 5)는 공시 표에 없어서 그림에도 넣지 않았습니다. 이 그림은 맨 위 지도의 "준비금 수익" 칸을 자세히 본 것입니다.

### 나-2. USDC 집중: 매출 쪽에서는 문제가 맞고, 제품 쪽에서는 절반만 맞다

[제 판단, 확신도 중간] 매출 쪽에서는 문제가 맞고, 제품 쪽에서는 절반만 맞습니다. 매출 쪽에서 USDC 의존과 금리 의존은 같은 문제의 두 면입니다.

- 매출 쪽: 준비금 수익은 유통량과 수익률의 곱입니다(10-Q 1888-1889행). 그런데 EURC 준비금은 "held only in cash at banks and not material"이므로(2673행), 유통량은 사실상 USDC 하나이고, 수익률은 SOFR에 가까운 달러 단기 금리 하나입니다(1886-1887행). 확장의 목표도 "drive increases in our stablecoins in circulation and thereby drive our reserve income"입니다(1896행). 기타 제품의 몫은 매출의 4.8%에서 5.4%입니다(1892-1893행).
- 제품 쪽: 자산은 넓어졌습니다. 디지털 자산 기둥에는 EURC, USYC, cirBTC가 함께 있습니다(1864-1865행). 그러나 Arc는 "Arc launches with USDC as the sole gas token"이고, paymaster를 통한 다른 스테이블코인의 가스 지불은 출시 시점에 지원하지 않습니다(stablecoin-native-model 132-137행). xReserve도 다른 회사의 스테이블코인을 "USDC-interoperable"하게 만드는 장치입니다(10-Q 1907-1908행).
- 반론: 회사는 이것을 의도한 구조로 적습니다. 새 제품이 플랫폼과 Circle 자산의 사용을 늘려 "a flywheel of growth"를 만든다고 합니다(1894-1895행). 회사에게 USDC 집중은 실수가 아니라 고른 전략입니다. 문제가 되는 때는 USDC 수요가 꺾이거나 금리가 내릴 때이고, 그때 받쳐 줄 다른 수입이 지금은 매출의 5% 안팎뿐이라는 점입니다.
- 해커톤 질문과 이어지는 쪽 [제 판단]: Arc에서 만드는 서비스는 가스와 기본 결제 단위가 USDC로 정해집니다. 그래서 달러가 아닌 통화를 쓰는 사용자를 받으려면 EURC나 StableFX 같은 환전 단계를 설계에 넣어야 합니다.

#### USDC 중심 인프라라는 해석: 제품을 설명하는 틀로는 맞고, 돈이 도는 방향은 반대다

사용자는 2026-10-14에 이 소절을 읽고 이렇게 물었습니다: "USDC 기반이 아니라, 정확히는 USDC를 지원하고 제공하는 인프라/제품 기반인거네? 그렇게 하면, EURC, USYC, cirBTC 등등도 모두 이해가 되고. 지금 표면은 USDC이지만, 따지고 보면, USDC를 모두 쓴다면, 자연스럽게 그와 연결된 이 거대한 스테이블코인 기반의 인프라와 연결되는게 맞니?"

이 물음을 저는 세 주장으로 나눠 읽었습니다. 이 구분은 제가 정했습니다.

1. Circle의 기반은 USDC라는 토큰보다 USDC를 지원하고 제공하는 인프라와 제품이다.
2. 그렇게 보면 EURC, USYC, cirBTC가 왜 있는지 설명된다.
3. USDC를 쓰면 그와 연결된 스테이블코인 인프라에 자연스럽게 연결된다.

[제 판단, 확신도 중간] 세 주장에 대한 제 의견은 다음과 같습니다.

1. **제품을 설명하는 틀로는 맞고, 돈이 도는 방향은 반대입니다.** 10-Q도 세 기둥이 "designed to reinforce one another"라고 적으므로(1866행), 제품을 하나의 묶음으로 보는 것은 회사의 설명과 같습니다. 그러나 회사가 적은 화살표는 인프라에서 USDC로 향합니다. 제품을 키우는 목적이 "drive increases in our stablecoins in circulation and thereby drive our reserve income"이고(1896행), 인프라가 직접 버는 기타 매출은 4.8%에서 5.4%입니다(1892-1893행). 돈으로 보면 기반은 여전히 USDC 유통량이고, 인프라는 그것을 늘리는 수단입니다.
2. **대체로 맞습니다. 다만 세 자산은 USDC에서 벗어나는 분산이 아니라 USDC로 돌아오는 고리입니다.**
   - EURC: StableFX는 "supports USDC and EURC"입니다(stablefx-overview 29행). EURC는 달러와 유로 사이 환전의 한쪽입니다. 2026-10-15에 다시 받은 개요는 "supports USDC and EURC alongside partner stablecoins spanning major global currencies"라고 적고(StableFX 개요 29행), 지원 토큰 표에는 원화 KRW1을 포함해 16개(13개 통화)가 있습니다(StableFX 지원 통화 28-43행).
   - cirBTC: Arc에서 App Kits의 Borrow는 cirBTC를 담보로 USDC를 빌려 줍니다(01 749행). BTC를 가진 사람이 USDC를 쓰게 만드는 경로입니다.
   - USYC: "intended primarily for use as collateral in digital asset markets, providing yield to token holders"입니다(10-Q 1903-1905행). 이자를 주지 않는 USDC 옆에서, 수익이 필요한 기관 자금을 Circle의 상품 안에 두는 자리로 읽힙니다 [확신도 낮음]. USYC와 USDC 사이의 전환 경로는 이번에 확인하지 않았습니다.
   - xReserve도 다른 회사의 스테이블코인을 "USDC-interoperable"하게 만듭니다(10-Q 1907-1908행).
   - 그래서 이 해석은 앞의 판정을 바꾸지 않고 오히려 뒷받침합니다. 자산은 넓어졌지만 모두 USDC를 중심으로 돌기 때문에, 매출 쪽의 USDC 집중은 그대로입니다.
3. **절반만 맞습니다.** 연결이 강제되는 곳은 Arc 하나입니다. Arc에서는 가스를 USDC로만 냅니다(stablecoin-native-model 132행). Arc 밖에서는 연결이 저절로 생기지 않습니다.
   - USDC를 쓰는 사람이 Circle의 인프라를 반드시 거치지는 않습니다. CPN도 Arc 말고 Ethereum, Polygon PoS, Solana를 지원합니다(04 1155행). USDC가 다른 체인과 거래소에서 Circle 제품 없이 쓰인다는 것은 제 일반 지식이고, 이번에 자료로 확인하지 않았습니다.
   - 기업은 받은 스테이블코인을 오래 들고 있지 않습니다. EY 조사에서 기업의 79%가 거래 직후 법정화폐로 바꾸고, PYMNTS 조사에서는 받은 스테이블코인의 88%를 바로 달러로 바꿉니다(다 절 3번의 표). 기업 고객에게 USDC는 머무는 곳이 아니라 지나가는 통로에 가깝습니다. Circle이 Mint, CPN, Wallets 같은 연동 제품을 따로 내놓는 것은, 연결이 저절로 생기지 않기 때문이라고 읽습니다 [제 판단].
   - "거대한"이라는 말은 제품 수에는 맞지만 매출에는 맞지 않습니다. 매출로는 기타 매출 5% 안팎입니다.

정리하면, 사용자의 틀을 "USDC를 중심에 두고 그 유통량을 늘리도록 짜인 인프라 묶음"으로 고쳐 쓰면 제품과 매출을 함께 설명할 수 있습니다. 그렇게 보아도 이 소절의 판정(매출 쪽에서는 문제가 맞고, 제품 쪽에서는 절반만 맞음)은 바뀌지 않습니다.

세 주장에 대한 의견을 한 그림으로 그리면 다음과 같습니다. 그림은 제가 그렸고, 세 부분은 위의 1, 2, 3번에 하나씩 대응합니다.

```text
[한국어판] 그림 4. USDC 중심 인프라: 돈이 흐르는 방향, USDC로 돌아오는 고리, 연결이 강제되는 곳

  화살표의 뜻   ===>   돈이 흐름      --->   USDC 쪽으로 이어짐
                - - ?  확인하지 않음  <...   빠져나감

  (1) 돈이 흐르는 방향: 인프라가 USDC를 늘리고, 돈은 USDC에서 나온다

      인프라와 제품 (세 기둥이 "서로를 강화")
         |
         +---> USDC 유통량 ===> 준비금 수익: 매출의 95.2%
         |
         +===> 기타 매출: 매출의 4.8-5.4%

  (2) 다른 자산과 제품도 USDC로 돌아온다

      EURC      StableFX에서 USDC와 맞바꾸는 한쪽 통화      ---> USDC와 거래
      cirBTC    Arc의 Borrow에서 맡기는 담보                ---> USDC를 빌림
      xReserve  다른 회사의 스테이블코인을 USDC와 호환      ---> USDC와 호환
      USYC      수익이 필요한 기관 자금을 Circle 상품에 둠  - - ? USDC와의 전환 경로 미확인

  (3) 연결이 강제되는 곳은 Arc 하나다

      Arc 안    가스를 USDC로만 낸다. 그래서 Arc에서 거래하려면 USDC가 있어야 한다
      Arc 밖    기업은 받은 스테이블코인을 바로 법정화폐로 바꾼다 (EY 79%, PYMNTS 88%)
                USDC <... 빠져나감: 머무는 곳이 아니라 지나가는 통로

  정리: "USDC를 중심에 두고, 그 유통량을 늘리도록 짜인 인프라 묶음"
```

```text
[English] Figure 4. USDC-centred infrastructure: which way money flows, what loops back to USDC, where the link is forced

  Arrows   ===>   money flows  --->   leads to USDC
           - - ?  not checked  <...   leaves

  (1) Direction of money: the infrastructure grows USDC, and the money comes from USDC

      Infrastructure and products (the three pillars "reinforce one another")
         |
         +---> USDC in circulation ===> Reserve income: 95.2% of revenue
         |
         +===> Other revenue: 4.8-5.4% of revenue

  (2) Other assets and products also loop back to USDC

      EURC      one side of USDC/EURC trades on StableFX                     ---> traded against USDC
      cirBTC    collateral in Borrow on Arc                                  ---> USDC borrowed
      xReserve  makes other issuers' stablecoins USDC-compatible             ---> compatible with USDC
      USYC      keeps yield-seeking institutional money in a Circle product  - - ? conversion path to USDC not checked

  (3) The link is forced in one place only: Arc

      On Arc       gas is paid only in USDC, so transacting on Arc requires holding USDC
      Off Arc      businesses convert received stablecoins to fiat at once (EY 79%, PYMNTS 88%)
                   USDC <... leaves: a passage, not a place to stay

  In short: "an infrastructure bundle centred on USDC and built to grow its circulation"
```

그림은 화살표를 세 가지 뜻으로 나눠 썼습니다. 굵은 화살표(===>)는 돈이 흐르는 방향이고, 가는 화살표(--->)는 제품이나 자산이 USDC 쪽으로 이어진다는 뜻이며(유통량을 늘리거나 USDC와 거래하게 만듦), 점선 물음표(- - ?)는 이번에 확인하지 않은 고리입니다. 산문으로는 세 주장이 한 줄씩 이어져서, 세 주장이 서로 다른 종류의 관계라는 점이 잘 보이지 않습니다.

(1)은 사용자의 틀(인프라가 기반이다)과 회사의 화살표(인프라가 USDC를 늘린다)가 반대라는 점을 보여 줍니다. 매출의 95.2%는 USDC 유통량에서 나오는 준비금 수익입니다. (2)는 EURC, cirBTC, xReserve가 모두 USDC로 끝나는 고리라는 점을 보여 줍니다. USYC는 확신도가 낮아서 화살표를 긋지 않았습니다. (3)은 Arc 안에서만 연결이 강제되고, Arc 밖에서는 기업이 받은 스테이블코인을 바로 바꾸어 빠져나간다는 점을 보여 줍니다. 이 그림은 맨 위 지도의 "USDC 유통량" 칸을 자세히 본 것입니다.

### 나-3. ARC 토큰: 가격이 10배가 되어도 금리 수입을 대신하기는 어렵다

[제 판단, 확신도 낮음] 가격이 오르면 Circle이 가진 토큰의 평가액, 앞으로의 토큰 판매 대금, 새로 발행하는 토큰에서 나오는 스테이킹 보상은 커집니다. 가격이 사전판매 가격의 10배면 보유분의 값은 연간 준비금 수익의 약 3년 치이므로, 회사 가치와 재무 여력에서는 무시할 수 없는 크기입니다. 그러나 해마다 들어오는 금리 수입에 대한 의존을 대신하기는 어렵습니다. 금액이 작아서가 아니라, 큰 몫은 한 번 매기는 값이고 해마다 반복될 수 있는 몫 가운데 가격과 함께 커지는 것은 일부이기 때문입니다. 근거는 아래와 같고, 가격별 크기는 이 소절 끝의 두 번째 표에 있습니다.

- 이미 판 토큰의 값은 정해져 있습니다. 8억 750만 개를 개당 0.30달러에 팔았고, 대금은 약 2억 4,220만 달러입니다(10-Q 1942-1951행). 가격이 올라도 이 대금은 늘지 않습니다.
- 커지는 것 1, 보유분의 가치: Circle의 몫은 100억 개의 25%인 25억 개입니다(토큰 백서 435-445행).
  - 사전판매 가격으로 매기면 7.5억 달러(25억 × 0.30)이고, 10-Q도 이 가격이 "a fully diluted network valuation of \$3.0 billion"을 뜻한다고 적습니다(1950행).
  - 1분기 10-Q는 "We expect to hold a material number of ARC Tokens on our consolidated balance sheet"라고 적었습니다(1분기 10-Q 2801행).
  - 다만 2분기 10-Q에서 보유분의 회계 처리를 적은 문장은 찾지 못했습니다(검색: `rg -n -i 'arc token' <10-Q>`, 22줄을 모두 읽음). 그래서 가격 상승이 손익에 어떻게 나타나는지는 모릅니다.
  - 보유분을 언제부터 팔 수 있는지도 정해지지 않았습니다. 백서는 "Exact unlock and release schedules will be announced in the coming months"라고만 적습니다(토큰 백서 436-437행).
- 커지는 것 2, 앞으로의 판매: 토큰 판매 대금은 Other revenue로 인식합니다. 이유는 "because the sale and distribution of ARC Tokens are part of the Company's ongoing major or central operations"입니다(10-Q 783-786행). 백서의 생태계 몫 60%에는 "token sales"가 들어 있습니다(토큰 백서 438-439행). 가격이 오르면 같은 수량을 팔아도 매출이 커집니다. 다만 CEO는 추가 사전판매에 대해 "We have no plans at this moment for any future pre-sale"라고 했습니다(콜 790행).
- 커지는 것 3, 스테이킹: CEO는 "future staking revenue, but the network needs to evolve into its proof of stake status"라고 했습니다(콜 312행). PoS 전환 전에는 생기지 않습니다. 백서는 보상의 원천을 둘로 적습니다: "inflation-funded issuance and fee-derived revenue converted into ARC at the protocol level"(토큰 백서 234-235행). 새로 발행하는 토큰에서 나오는 몫은 가격이 오르면 달러 가치도 커집니다. 다만 발행률은 "programmatically declines according to a predefined schedule"이고(327행), 이 몫은 다른 보유자의 몫을 희석해서 생기는 돈입니다 [제 판단]. 수수료에서 나오는 몫은 수수료가 "priced in reference to stablecoins"이므로(376행), ARC 가격이 올라도 달러 금액이 늘지 않고 더 적은 ARC로 바뀔 뿐입니다 [제 추론].
- 크기를 바로 비교할 수 없습니다. 보유분 7.5억 달러는 한 번 매긴 재고의 값이고, 금리 1%p가 움직이는 7.37억 달러는 해마다 반복되는 흐름입니다. 토큰이 금리 의존을 대신하려면 해마다 반복되는 수입이 되어야 합니다. 연구 원고 06은 이 조건을 "얼마의 지속 가능한 수입이 ARC 토큰에 연결되며"라는 물음으로 적습니다(06 1188행). 지금 수수료는 USDC로 내고 블록 수혜자에게 적립되며, ARC로 바꾸고 소각하는 장치는 백서의 제안이고 활성화는 확인되지 않았습니다(06 492행).
- 회사가 공시한 쪽은 하락뿐입니다. "The market price of ARC Tokens could be highly volatile and may decline significantly"(1분기 10-Q 2798행), "If the ARC Token declines significantly in value or becomes illiquid, our business model, to the extent it depends on the ARC Token, could be materially harmed"(2808-2809행)입니다. 가격이 오를수록 Circle의 매도와 금고 배분, 사전판매분의 베스팅 해제가 가격을 누를 수 있다고도 적습니다(2810-2814행).
- 금리와 함께 내릴 수 있습니다. 회사는 토큰 가격의 요인으로 "demand (or lack thereof) for use of Arc"와 "macroeconomic conditions"를 듭니다(1분기 10-Q 2804-2805행). guide 278행대로 경기 악화에 대응한 금리 인하가 자산 가격 하락과 함께 온다면, 금리 수입이 줄 때 토큰 가치도 함께 내려갈 수 있습니다. 그 경우 분산 효과는 보이는 것보다 약합니다.
- [확신도 낮음] 증권 판정과의 긴장도 있습니다. 회사는 ARC가 증권이 아니라는 입장의 근거로 "the degree to which its value is expected to depend on factors other than our managerial efforts"를 듭니다(1분기 10-Q 2744-2745행). 토큰의 가치가 Circle의 사업 성과에 크게 기대는 것처럼 보일수록 이 근거와 부딪힐 수 있습니다. 법적 판단은 제가 할 수 있는 범위 밖이고, 긴장이 있다는 점만 적습니다.
- 사전판매에는 2028-05-08까지 PoS로 전환하지 못하면 환불하는 조건이 붙어 있습니다(10-Q 1951-1953행). 가격이 올라도 이 조건은 그대로입니다.

#### 커지는 것과 금리 1%p: 크기를 아는 것은 한 번뿐인 값이고, 반복될 수 있는 것은 크기를 모른다

위 bullet들을 크기와 반복 여부로 나란히 놓으면 다음과 같습니다. 열은 제가 정했습니다.

```text
[한국어판] 그림 5. ARC 가격이 오를 때 커지는 것과 금리 1%p의 비교

  커지는 것              크기                       해마다 반복되는가      조건
  이미 판 토큰 대금      약 2.42억 달러             아니오, 끝난 거래      가격이 올라도 늘지 않음
  Circle 보유분 25억 개  7.5억 달러(0.30달러 기준)  아니오, 한 번 매긴 값  회계 처리 문장을 찾지 못함, 해제 일정 미발표
  앞으로의 토큰 판매     공개된 금액 없음           팔 때마다              추가 사전판매 계획은 없다고 함
  스테이킹 수입          공개된 금액 없음           반복될 수 있음         PoS 전환 뒤에만 생김, 가격과 함께 커지는 것은 발행분 몫뿐
  -------------------------------------------------------------------------------------------------------
  비교: 금리 1%p         준비금 수익 7.37억 달러    그렇다, 해마다         유통량이 클수록 커짐
```

```text
[English] Figure 5. What grows when the ARC price rises, compared with a 1 pp rate move

  What grows                   Size                     Repeats every year?   Condition
  Tokens already sold          about USD 242M           no, a closed sale     does not grow with the price
  Circle's 2.5 billion tokens  USD 750M at USD 0.30     no, a one-time value  no accounting sentence found; unlock schedule not announced
  Future token sales           no amount disclosed      each time it sells    no further pre-sale planned
  Staking income               no amount disclosed      could repeat          only after the move to PoS; only the issuance part grows with the price
  --------------------------------------------------------------------------------------------------------
  Compare: rate 1 pp           USD 737M reserve income  yes, every year       grows with circulation
```

이 표는 "ARC 가치가 크게 올라도 금리 수입을 대신하기 어렵다"는 판단의 근거를 한곳에 모았습니다. 위 bullet은 항목마다 따로 적어서, 크기를 아는 것은 한 번뿐인 값이고 반복될 수 있는 것은 크기를 모른다는 대비가 드러나지 않습니다. 맨 아래 줄은 비교 대상인 금리 1%p이며, 해마다 반복되고 금액도 공시되어 있습니다.

그래서 7.5억 달러와 7.37억 달러는 숫자가 비슷해도 같은 종류가 아닙니다. 앞의 것은 한 번 매긴 재고의 값이고, 뒤의 것은 해마다 반복되는 흐름입니다. 이 표는 맨 위 지도의 "회사에게" 줄을 가격 쪽에서 자세히 본 것이고, 시점 쪽은 라 절의 그림이 다룹니다.

#### 가격별 크기: 10배면 보유분의 값은 연간 준비금 수익의 약 3년 치다

위 표의 크기는 사전판매 가격 하나로 매긴 값입니다. 가격이 2배와 10배일 때의 크기는 다음과 같습니다.

```text
[한국어판] 그림 6. ARC 가격별로 본 크기와 금리 수입의 비교 (단위: 억 달러)

  ARC 가격                                    0.30달러     0.60달러     3.00달러
                                              (사전판매)   (2배)        (10배)
  Circle 보유분 25억 개의 값                  7.5          15           75
  같은 수량(8억 750만 개)을 다시 판다면       2.42         4.85         24.2
  이미 판 토큰 대금                           2.42         2.42         2.42
  ----------------------------------------------------------------------------------
  보유분은 금리 1%p 효과의                    약 1.0년 치  약 2.0년 치  약 10.2년 치
    (연 7.37)
  보유분은 연간 준비금 수익의                 약 0.3년 치  약 0.6년 치  약 2.8-2.9년 치
    (연 25.7-26.7)
```

```text
[English] Figure 6. Sizes by ARC price, compared with reserve income (USD billions)

  ARC price                                   USD 0.30     USD 0.60     USD 3.00
                                              (presale)    (2x)         (10x)
  Value of Circle's 2.5 billion tokens        0.75         1.5          7.5
  Selling the presale amount (807.5M) again   0.242        0.485        2.42
  Tokens already sold                         0.242        0.242        0.242
  ----------------------------------------------------------------------------------
  Holding in years of the 1 pp effect         about 1.0    about 2.0    about 10.2
    (0.737 per year)
  Holding in years of reserve income          about 0.3    about 0.6    about 2.8-2.9
    (2.57-2.67 per year)
```

이 표는 가격이 2배와 10배일 때의 크기를 계산해 위 표의 "크기" 열을 가격 쪽으로 늘린 것입니다. 위 표는 0.30달러 한 가격만 적어서, 가격이 오를 때 금액이 얼마나 커지는지 보이지 않았습니다. 0.30달러는 사전판매 가격이고 시장 가격은 이번에 확인하지 않았으며, 2배와 10배는 예측이 아니라 크기를 보려는 가정입니다.

윗부분의 계산은 모두 수량 × 가격입니다(25억 개, 8억 750만 개). "같은 수량을 다시 판다면"도 크기를 보려는 가정이고, 회사는 추가 사전판매 계획이 없다고 했습니다(콜 790행). 아랫부분의 분모는 나 절 1번의 값입니다. 금리 1%p 효과는 연 7.37억 달러이고, 연간 준비금 수익은 737 × 3.49 = 25.72억 달러와 2분기 실적의 네 배인 26.71억 달러(667.7 × 4)입니다. 예를 들어 10배일 때 75 / 7.37 = 10.2, 75 / 25.72 = 2.9, 75 / 26.71 = 2.8입니다.

가격이 10배면 보유분의 값은 연간 준비금 수익의 약 3년 치입니다. 이 경우를 무시할 수는 없습니다. 그래도 금리 의존을 대신하기 어렵다는 판단은 유지합니다. 그 근거는 금액이 아니라 다음 세 가지입니다.

1. 한 번 매기는 값입니다. 돈으로 바꾸려면 팔아야 하는데, Circle의 매도는 가격을 누를 수 있고(1분기 10-Q 2810-2814행) 해제 일정은 아직 발표되지 않았습니다(토큰 백서 436-437행).
2. 2분기 10-Q에서 회계 처리 문장을 찾지 못해, 손익에 어떻게 잡히는지 모릅니다.
3. 해마다 반복될 수 있는 스테이킹 보상 가운데 가격과 함께 커지는 것은 새로 발행하는 토큰에서 나오는 몫뿐이고, 그 발행률은 줄어들도록 설계되어 있습니다(위 스테이킹 bullet).

## 다. 1-3 Arc와 고객의 문제: Arc는 고객의 어떤 문제를 푸는가?

[제 판단, 확신도 중간] Arc에서만 얻는 기능의 범위는 좁습니다. 이것은 기능의 범위에 대한 판단이고, 고객 문제의 무게에 대한 판단이 아닙니다. 고객 문제의 무게는 아래 다-1부터 다-4까지에 따로 적었습니다.

- 공시에 적힌 Arc의 설계는 다섯 가지입니다. 가스비를 스테이블코인으로 내고, 검증자는 허가받은 기관이며, 거래는 1초 안에 확정됩니다. 거래를 비공개로 설정할 수 있고, 운영과 거버넌스는 넓게 나눕니다 [공시] (survey 992-997행).
- 그런데 Circle의 다른 제품은 대부분 Arc 없이도 돌아갑니다.
  - CPN의 환경 문서는 Ethereum, Polygon, Solana를 예로 듭니다 (why 305행). 공식 CPN 지원 체인 문서도 Arc, Ethereum, Polygon PoS, Solana를 함께 나열합니다(04 1155행).
  - App Kits는 Arc 전용이 아닙니다("not just Arc", kit 88행).
  - Agent Stack은 Arc 없이도 동작하며, Arc 메인넷 지원은 2026-09-16에야 추가되었습니다 (products 210행).
  - 공시도 애플리케이션이 여러 블록체인에서 쓰인다고 적습니다 [공시] (survey 443행).
- 반대로 StableFX는 Arc 위에서 돌아간다고 공시에 적혀 있습니다 [공시] (survey 1184행).
- 따라서 지금 고객이 Arc에서만 얻는 기능은 USDC로 내는 가스비, 빠른 확정, StableFX의 정산 장소 정도입니다. 나머지는 기존 체인과 같은 조건에서 비교해 봐야 할 후보입니다 [제 판단]. 이 기능이 고객의 문제를 얼마나 줄이는지는 아래에 나눠 적었습니다.

다-1부터 다-4까지는 2026-10-14 사용자의 물음(고객의 문제가 핵심적이지 않다는 전제를 어떻게 아는가, 원문은 "사용자 피드백으로 고친 것" 3번)에 답합니다. 이 넷은 처음에 "고객의 문제가 핵심적이지 않다는 것을 어떻게 아는가"라는 소절 아래의 번호 항목이었고, 2026-10-15에 목차를 만들면서 소절로 올렸습니다.

직답: 알 수 없었고, 저는 그것을 판단하지 않았습니다. 처음 문장("Arc에서만 풀리는 고객 문제는 좁습니다")은 기능의 범위를 말하려던 것인데, 고객 문제가 가볍다는 뜻으로도 읽히게 썼습니다. 그 문장은 근거보다 많이 말했습니다. 아래에서는 물음을 넷(문제의 무게, Arc가 맡는 몫, 고객이 중요하게 여기는지, 확인하는 방법)으로 나눴습니다. 이 구분은 제가 정했습니다.

### 다-1. 문제의 무게: 해외 지급의 비용, 속도, 위험은 무거운 문제다

문제 자체는 무겁습니다 [확신도 높음]. 국경 간 지급의 비용, 속도, 위험은 국제기구가 여러 해 동안 측정해 온 문제입니다.

| 출처     | 내용                                                                                                                                                                                                                                                                                                                      | 위치                                                                                                                     |
| -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| FSB 2020 | 국경 간 지급의 과제로 "challenges of high costs, low speed, limited access and insufficient transparency"를 듭니다. 기관이 "to hold precautionary funding"을 해야 하고, 그 자금은 "often in multiple currencies"라고 적습니다.                                                                                            | `cb/works/web/2026-10-07-enterprise-payment-process-sources/pages/P090420-1.txt` 32-33, 46행                             |
| FSB 2023 | "FX costs constitute more than 50% of total cost for all use cases"                                                                                                                                                                                                                                                       | `cb/works/web/2026-10-07-enterprise-payment-process-sources/pages/P091023-1.txt` 172행                                   |
| FSB 2025 | 중소기업 B2B 지급의 평균 비용은 1.6%입니다. B2B 비용 가운데 외환은 1.4%, 수수료는 0.2%이고, 외환의 비중은 87.1%입니다. "B2B and B2P use cases exhibited less than 45% of payments settled within one business day"                                                                                                        | `cb/works/web/2026-10-05-arc-builder-research-checks/pages/revision-fsb-cross-border-2025.md` 2540, 2571, 1447-1448행    |
| SWIFT    | "75% of Swift payments reach the beneficiary bank within 10 minutes". 은행에 도달한 뒤의 마지막 구간(last mile)이 전체 지급 시간의 "over 80%"를 차지한다고 적습니다.                                                                                                                                                      | `cb/works/web/2026-10-05-arc-builder-research-checks/pages/revision-swift-payment-time-web.md` 209, 228행                |
| BIS 2026 | 외환 결제의 "10%, or \$1.4 trillion, remained exposed"입니다. 위험에 노출된 비율은 비금융 고객과의 거래에서 "with non-financial customers (22%)"로 높습니다. PvP(두 통화를 동시에 주고받는 결제)를 쓸 수 없었던 거래에서 가장 흔한 이유는 상대방이 "did not have direct or indirect access to PvP systems (57%)"였습니다. | `cb/works/web/2026-10-08-enterprise-payment-problem-sources/pages/bis-qr-2026-06-fx-settlement-risk.txt` 837, 893, 907행 |

### 다-2. Arc가 맡는 몫: 문제마다 일부 구간에만 닿는다

Arc가 맡는 몫은 그 문제의 일부입니다 [확신도 중간]. 연구 원고 04는 문제마다 "Arc가 맡는 부분"과 "해결되지 않고 남는 것"을 나란히 놓았습니다(04 1101-1123행). 이 표의 행과 열은 원고 작성자가 정했고, 제품 설명 열은 효과를 측정한 결과가 아니라고 원고가 스스로 밝힙니다(04 1101행).
- 처리 시간: Arc는 기관 사이의 전송을 확정합니다. 남는 것은 "은행 도달 뒤 고객 계좌 입금까지의 구간"입니다(04 1106행). 위 SWIFT 자료에서는 이 구간이 전체 시간의 80% 넘게 차지합니다. 원고도 "체인 구간이 짧아져도 다른 구간이 그대로라면 전체 시간은 그만큼 줄지 않"는다고 적습니다(04 2376행).
- 지급 비용: Arc가 맡는 것은 체인 실행의 가스비입니다. 원고는 남는 것을 외환 가격으로 적고, FSB 예시에서 그 몫은 87.1%입니다(04 1107행). 다만 FSB의 외환 비용은 환율 자체가 아니라 은행 간 환율 위에 얹은 몫이고, Arc에서 정산하는 StableFX가 이 몫을 겨냥합니다. 이 경로와 그 계산은 아래 그림 9에 있습니다.
- 자금 배치: 미리 두는 자금을 줄이는 것은 CPN의 기능이고, Arc는 CPN이 지원하는 체인 가운데 하나입니다(04 1105행).
- 상대국의 달러 부족: Arc가 맡는 부분은 "없다"입니다(04 1120행).
- 예외는 외환의 상대방 위험입니다. StableFX의 `FxEscrow` 계약은 Arc에서 실행되고, 두 통화를 함께 인도하거나 둘 다 인도하지 않습니다(04 1108행). 위 BIS 자료의 PvP 접근 문제와 같은 종류의 위험을 겨냥합니다. 다만 BIS의 비율은 StableFX의 효과를 잰 값이 아닙니다.

다-1(문제의 무게)과 다-2(Arc가 맡는 몫)를 지도 표 하나와 그림 셋으로 나눠 그렸습니다. 지도 표(그림 7)는 문제 다섯이 그림 8, 9, 10 가운데 어디서 다뤄지는지를 보여 주고, 그림 8, 9, 10이 문제의 종류(시간, 비용, 위험과 자금)마다 하나씩 자세히 봅니다. 숫자는 모두 위 출처 표와 이 소절 첫머리 bullet에서 가져왔고, 그림과 표는 제가 그렸습니다.

```text
[한국어판] 그림 7. 해외 지급의 문제와 Arc의 몫: 그림 8, 9, 10의 지도

  문제                측정된 크기                              Arc의 몫                              그림
  --------------------------------------------------------------------------------------------------------
  시간                마지막 구간이 전체 시간의 80% 넘게 차지  일부                                  8
  비용                평균 1.6% 가운데 외환이 1.4%(87.1%)      가스비는 작음, 외환은 StableFX로 간접  9
  외환 결제 위험      외환 결제의 10%, 1.4조 달러가 노출       일부                                  10
  미리 둔 자금        여러 통화로 미리 쌓아 둠                 간접                                  10
  상대국의 달러 부족  -                                        없음                                  10
```

```text
[English] Figure 7. Problems in cross-border payments and Arc's share: a map of figures 8, 9 and 10

  Problem                 Measured size                                    Arc's share                            Figure
  ----------------------------------------------------------------------------------------------------------------------
  Time                    the last mile takes over 80% of total time       partial                                8
  Cost                    of the 1.6% average, FX is 1.4% (87.1%)          gas: small; FX: indirect via StableFX  9
  FX settlement risk      10% of FX settlement, USD 1.4 trillion, exposed  partial                                10
  Prefunded balances      held in advance in several currencies            indirect                               10
  Dollar shortage abroad  -                                                none                                   10
```

이 표는 문제 다섯을 한 줄씩 놓고, 측정된 크기와 Arc의 몫을 나란히 적었습니다. "Arc의 몫" 칸의 값(일부, 간접, 없음, 그리고 비용 행의 "가스비는 작음, 외환은 StableFX로 간접")은 이 소절 첫머리 bullet의 판단을 줄인 말입니다. 비용 행은 2026-10-15에 고쳤고, 이유는 그림 9 아래에 있습니다. 문제를 나눈 방식은 원고 04의 표(04 1101-1123행)에서 이 질문에 필요한 행만 고른 것입니다.

#### 시간: 전체 시간의 80% 넘게 쓰이는 마지막 구간에는 Arc가 닿지 않는다

그림 8은 시간입니다. 지급 한 건이 지나는 두 구간과, 전체 시간이 어디에 쓰이는지를 그렸습니다.

```text
[한국어판] 그림 8. 시간: 지급 한 건이 지나는 두 구간

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
[English] Figure 8. Time: the two segments one payment passes through

  Sending bank
     |
     |  [1] Institution-to-institution transfer
     |      Now: 75% of Swift payments reach the beneficiary bank within 10 minutes
     |           on average under 20% of total payment time
     |      Arc: takes this segment (finality within 1 second)
     v
  Beneficiary bank
     |
     |  [2] Last mile: credit to the customer account
     |      Now: over 80% of total payment time
     |      Arc: none
     v
  Beneficiary business account

  Total payment time set to 100 (Swift measurement, average)
  |<--- under 20 -->|<------------------ over 80 ------------------>|
   [1] in-flight           [2] last mile

  Overall: under 45% of B2B payments settle within one business day (FSB 2025)
```

그림 8은 위쪽에 구간의 순서를, 아래쪽에 시간의 비중을 그렸습니다. Arc가 맡는 [1]은 지금도 SWIFT 지급의 75%가 10분 안에 지나는 구간이고, 시간의 대부분은 Arc가 닿지 않는 [2]에서 쓰입니다. 원고 04도 "체인 구간이 짧아져도 다른 구간이 그대로라면 전체 시간은 그만큼 줄지 않"는다고 적습니다(04 2376행).

아래 막대의 두 값은 SWIFT가 직접 잰 평균입니다. SWIFT는 송금 은행에서 중개 기관을 거쳐 수취 은행에 닿기까지를 in-flight 시간이라 부르고, 그것이 전체의 "less than 20%"이며 마지막 구간이 "over 80%"라고 적습니다(SWIFT 자료 212-213, 228행). 두 값과 75%는 Arc를 쓰지 않는 SWIFT 지급의 값입니다. SWIFT의 두 구간이 송금 은행에서 시작하므로 그림도 송금 은행에서 시작합니다.

#### 비용: Arc는 가스비와 StableFX라는 두 길로 닿는다

그림 9는 비용입니다. 평균 비용 1.6%가 무엇으로 이루어지는지와, Arc가 그 비용에 닿는 두 길을 그렸습니다.

```text
[한국어판] 그림 9. 비용: 평균 1.6%의 구성과 Arc가 닿는 두 길

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
[English] Figure 9. Cost: what the 1.6% average is made of, and Arc's two routes to it

  Average cost of an SME B2B cross-border payment: 1.6% (FSB 2025, a USD 20,000 payment)

  |############################################|######|
  |<----------- FX 1.4% (87.1%) -------------->| fees |
                        ^                       0.2%
                        |                         ^
                        |                         |
                        |                        (1) where Arc's gas fee could sit
                        |                            fees FSB measured on existing payments;
                        |                            how much gas would replace is unmeasured
                        |
                       (2) where StableFX, which settles on Arc, could cut
                           prices are set off-chain by competing providers; Arc only settles
                           StableFX prices and fees are not published

  FX 1.4%: the gap between the FX rate charged and the interbank rate (FSB definition)
           not the cost of converting itself, but what sits on top of it
```

그림 9는 막대 하나로 비용의 구성을 그렸습니다. 막대의 길이는 1.4와 0.2의 비율에 가깝게 그렸습니다(44칸과 6칸, 88%와 12%). FSB는 외환 비용을 "the difference between the FX rate charged by a service and the interbank rate"로 정의합니다(FSB 방법론 399-401행). 그래서 1.4%는 통화를 바꾸는 값 자체가 아니라, 제공자가 은행 간 환율 위에 얹은 몫이고, 경쟁으로 줄어들 수 있는 값입니다.

Arc가 이 막대에 닿는 길은 둘입니다.

- (1) 수수료 쪽: Arc가 맡는 것은 체인 실행의 가스비이고(04 1107행), 가스비가 들어갈 자리는 수수료 0.2% 쪽이라고 저는 판단합니다 [제 판단]. 0.2%는 FSB가 기존 지급에서 잰 값이고, Arc의 가스비가 그중 얼마를 대신하는지는 측정되지 않았습니다.
- (2) 외환 쪽: StableFX를 거쳐 닿습니다. StableFX에서 가격을 정하는 일은 체인 밖에서 일어납니다. 견적은 Talos 플랫폼을 거쳐 받고, "Makers choose the rate of exchange for their quote response"입니다(StableFX 기술 안내서 139-140행). Arc는 그 거래를 정산하는 곳입니다. 그래서 외환 비용이 줄어든다면 그 몫은 주로 공급자 사이의 경쟁에서 나오고, Arc는 정산 장소로서 간접적으로 닿는다고 봅니다 [제 판단].

처음에는 (2)를 빠뜨리고 "비용의 87.1%를 차지하는 외환 가격은 Arc가 바꾸지 않습니다"라고 적었습니다. 원고 04가 지급 비용 행의 "남는 것"으로 외환 가격을 적은 것(04 1107행)을 따져 보지 않고 옮긴 것입니다. 원고 04는 "체인 전송의 가스가 저렴해도 기업의 전체 지급 비용이 저렴하다는 결론은 별도다"라고도 적습니다(04 2428행).

#### 외환 1.4%를 StableFX로 줄인다면: 채울 수 있는 숫자와 비어 있는 칸

2026-10-15 사용자의 물음("결국 Arc를 통해 외한 비용을 아낀다면? 그러면 계산을 다시 할 수 있는게 아냐?"[원문 그대로])에 따라, 아래 식의 칸마다 공개 자료를 찾았습니다(StableFX 외환 비용 자료 묶음). 식은 제가 세웠습니다. 비교는 달러에서 유로로 보내는 2만 달러 B2B 지급을 기준으로 했습니다. 2만 달러는 FSB가 B2B KPI에 쓰는 송금액이고(FSB 방법론 367행), 달러와 유로는 StableFX가 처음부터 지원한 쌍입니다.

    절감 = 지금의 외환 비용
           - StableFX에서 받는 가격의 마진 - StableFX 수수료
           - 양끝의 전환 비용(은행 돈 -> USDC 발행, EURC 상환 -> 은행 돈)

| 칸 | 값 | 무엇을 잰 값인가 | 위치 |
|---|---|---|---|
| 지금의 외환 비용, 평균 | 1.4%(140bp) | 모든 통로의 중소기업 B2B 평균이고, 은행 간 환율과의 차이입니다. | FSB 2025 2571행, FSB 방법론 399-401행 |
| 지금의 외환 비용, 달러에서 유로 | B2B 핀테크 82.6bp. 대형 은행의 개인 송금은 230.2bp와 299.5bp | HBS가 Bloomberg 기준 환율과 비교해 잰 값입니다. 핀테크 쪽은 지역 은행과 교육 기관이 한 플랫폼에서 보낸 거래이고, 은행 쪽은 개인 송금입니다. 중소기업의 달러와 유로 값만 따로 잰 자료는 찾지 못했습니다. | HBS 197, 151, 156행 |
| StableFX 견적의 마진 | 공개된 값 없음 | 가격은 공급자가 정합니다. 견적이 기준 환율에서 "acceptable spread"를 넘으면 거절하지만, 그 폭도 공개되지 않았습니다. | StableFX 기술 안내서 139-140행, StableFX API 명세 821-822행 |
| StableFX 수수료 | 공개된 값 없음 | 견적 응답에 수수료가 들어 있습니다. 문서의 예시는 1,000 USDC에 1.50 USDC(15bp)이지만 설명용 예시입니다. | StableFX 기술 안내서 100행, taker 안내 82, 95행 |
| 비슷한 시장의 마진(대용) | Coinbase EURC-USDC에서 2만 달러어치를 살 때 1.28bp, 최우선 호가 차이 0.9bp. Kraken의 최우선 호가 차이 1.71bp | 2026-10-14T15:44Z 한 순간의 호가창을 제가 잰 값입니다. 기준은 호가창의 가운데 값이고, 은행 간 환율이 아닙니다. | 자료 묶음 README의 "호가창 측정" |
| 비슷한 시장의 마진(대용) | 평균 -8.2bp, 표준편차 35.8bp | HBS가 중앙화 거래소의 스테이블코인 환산 유로 환율을 Bloomberg 기준 환율과 비교한 값입니다. HBS는 "Reliable pricing is not guaranteed over time."이라고 덧붙입니다. | HBS 353, 364행 |
| 양끝의 전환 비용, 기관 | EURC 상환 0bp(Basic 등급, 처리는 최대 영업일 이틀) 또는 5bp(Standard는 하루 200만 달러까지 무료, Institutional은 총액에). USDC 발행 수수료는 찾지 못함 | Circle Mint의 2026-03-15부터의 상환 수수료입니다. | Circle Mint 상환 수수료 41-47, 87행 |
| 양끝의 전환 비용, 거래소를 쓸 때 | 예: 거래소 거래 수수료 1%, SEPA 송금 1유로, 가스 0.19달러(100달러 송금) | HBS의 설명용 예시입니다. | HBS 294, 305, 337행 |

공개된 값만 넣으면 기관 쪽 경로의 비용은 시장 마진 1.28bp에 상환 0-5bp를 더한 1.3-6.3bp, 그리고 공개되지 않은 StableFX 수수료(F)와 USDC 발행 수수료(M)입니다. 지금 비용과의 차이는 다음과 같습니다.

- FSB 평균과 비교: 140 - (1.3에서 6.3) - F - M = 133.7-138.7bp - F - M
- 달러와 유로의 B2B 핀테크와 비교: 82.6 - (1.3에서 6.3) - F - M = 76.3-81.3bp - F - M
- 예를 들어 F가 문서 예시와 같은 15bp이고 M이 0이면, 차이는 각각 약 119-124bp와 61-66bp입니다. 이것은 예시 값을 넣은 계산이고, 추정이 아닙니다.
- 1.28bp는 호가창 가운데 값과의 차이입니다. 은행 간 환율과 비교한 140bp에서 바로 빼려면, 호가창 가운데 값이 은행 간 환율과 같다고 가정해야 합니다. HBS의 값(평균 -8.2bp, 표준편차 35.8bp)은 이 가정이 평균으로는 맞지만, 시점마다 수십 bp씩 어긋날 수 있음을 보여 줍니다.

[제 판단, 확신도 중간] 기관 사이의 달러와 유로 교환만 보면, 외환 비용의 대부분이 사라질 수 있다는 계산이 나옵니다. 그러나 세 가지 이유로 이것을 중소기업의 절감이나 Arc의 효과로 바로 읽을 수는 없습니다.

1. 중소기업은 StableFX를 직접 쓰지 못합니다. StableFX는 "permissioned platform is designed for financial institutions"입니다(StableFX 개요 26행). 기업이 받는 가격은 그 사이의 지급 사업자가 정하고, 사업자가 줄어든 비용을 기업에 넘기는지는 알 수 없습니다. 기업이 거래소를 직접 쓰면 HBS 예시처럼 거래 수수료 1%가 붙어, 달러와 유로의 B2B 핀테크 값(82.6bp)보다 오히려 비쌀 수 있습니다.
2. 비용이 줄어든다면 그 원인은 기술보다 경쟁입니다. HBS는 Wise가 보낸 한 건의 한계 비용을 0.24파운드와 0.06%로 보이고(HBS 400행), 결론을 "The cost advantage is regulatory and operational, not technological."로 적습니다(HBS 409행). 1.4%의 대부분은 통화를 바꾸는 원가가 아니라 제공자가 매긴 가격이고, 이 가격은 스테이블코인 없이도 핀테크의 경쟁으로 내려갑니다. StableFX는 그 경쟁에 들어온 장소 가운데 하나입니다.
3. Arc의 몫은 정산 장소입니다. 가격은 체인 밖에서 정해지고, StableFX가 Arc 메인넷을 지원하기 시작한 것은 2026-09-16입니다(StableFX 2026 릴리스 노트 29행). StableFX의 실제 가격과 거래량은 공개된 자료에서 찾지 못했습니다.

그래서 다시 계산할 식은 생겼지만, 그 식에서 가장 중요한 칸(StableFX의 가격과 수수료, 지급 사업자의 마진)은 여전히 비어 있습니다. 지도 표의 비용 행은 이 판단에 맞춰 "가스비는 작음, 외환은 StableFX로 간접"으로 고쳤습니다.

#### 위험과 자금: Arc는 Circle 제품을 거쳐서만 닿는다

그림 10은 위험과 자금입니다. 순서가 있는 경로가 아니라 지급 어디서나 걸리는 조건이어서, 문제마다 어느 Circle 제품이 닿고 그 제품이 Arc와 어떤 관계인지를 그렸습니다.

```text
[한국어판] 그림 10. 위험과 자금: 문제에서 제품을 거쳐 Arc까지

  문제                      이 문제에 닿는 Circle 제품             그 제품과 Arc
  -----------------------------------------------------------------------------------------------
  외환 결제 위험       ---> StableFX의 FxEscrow               ---> Arc 위에서 실행
  10%, 1.4조 달러 노출      두 통화를 함께 주거나 둘 다 안 줌
  미리 둔 자금         ---> CPN                               ---> Arc는 지원 체인 넷 가운데 하나
  여러 통화로 쌓아 둠
  상대국의 달러 부족   ---> 없음                                   -
```

```text
[English] Figure 10. Risk and funding: from the problem through a product to Arc

  Problem                         Circle product that reaches it           That product and Arc
  ------------------------------------------------------------------------------------------------------------
  FX settlement risk         ---> StableFX FxEscrow                   ---> runs on Arc
  10%, USD 1.4T exposed           delivers both currencies or neither
  Prefunded balances         ---> CPN                                 ---> Arc is one of four supported chains
  held in several currencies
  Dollar shortage abroad     ---> none                                     -
```

그림 10의 화살표는 "이 문제에 이 제품이 닿는다"와 "이 제품은 Arc와 이런 관계다"를 뜻합니다. 돈이나 시간의 흐름이 아닙니다. 이렇게 그린 이유는, Arc가 이 문제들에 직접 닿지 않고 언제나 Circle 제품을 거쳐 닿기 때문입니다. 외환 결제 위험은 Arc에서 실행되는 StableFX를 쓸 때 줄어들 수 있고, 미리 둔 자금은 CPN의 기능이며 Arc는 CPN이 고를 수 있는 체인 가운데 하나입니다. 상대국의 달러 부족에는 닿는 제품이 없습니다(04 1120행).

10%는 외환 결제 전체에 대한 BIS의 추정이고, StableFX의 효과를 잰 값이 아닙니다. BIS는 PvP를 쓸 수 없던 거래의 가장 흔한 이유로 상대방이 PvP 시스템에 접근하지 못한 것(57%)을 들었고, FxEscrow는 같은 종류의 위험을 겨냥합니다.

### 다-3. 고객이 느끼는 중요도: 문제는 느끼지만, 스테이블코인으로 옮긴 기업은 아직 적다

고객이 이 문제를 얼마나 중요하게 여기는가: 문제는 느끼지만, 스테이블코인으로 옮기는 기업은 아직 적습니다 [확신도 중간]. 처음에는 "모릅니다"라고만 적었습니다. 2026-10-14 사용자 피드백("충분히 외부 검색을 통해서도 힌트를 얻을 수 있는 것 같은데?")에 따라 공개 조사 여덟 건을 받아 읽었습니다(조사 묶음의 목록). 응답자를 돈을 내는 기업과, 지급 사업자 및 금융기관으로 나눠 읽었습니다. 이 구분은 제가 정했고, 두 집단의 답이 크게 달라서 나눴습니다. 표의 위치 칸은 인용 위치 표의 "조사 묶음" 행에 적은 파일의 행 번호입니다.

| 무엇을 보는가          | 조사(응답자, 조사 시기)                                                  | 내용                                                                                                                                                                                                                                                                    | 위치                                       |
| ---------------------- | ------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| 기업이 겪는 문제       | Rapyd(6개국 중대형 B2B 기업 715곳, 2023년 2월)                           | 해외 지급에 건당 10달러 이상의 수수료를 내는 곳이 76%, 5일 이상의 지연을 겪은 곳이 38%입니다.                                                                                                                                                                           | rapyd 91, 93행                             |
| 기업의 관심            | EY-Parthenon(기업 250곳과 금융기관 100곳의 의사결정자, 2025년 6월)       | 앞으로 5년간 가장 관심 있는 용도는 해외 공급사 지급(77%)이고, 관심 이유는 거래 비용 절감(52%)과 빠른 해외 지급(45%)입니다. 이용자의 41%가 "cost savings of at least 10%, primarily in B2B cross-border payments using USD-denominated stablecoins"를 보고했습니다.      | ey 393, 439, 453행                         |
| 기업의 관심            | Deloitte(북미 매출 10억 달러 이상 기업의 CFO 200명, 2025년 6월)          | 스테이블코인 도입 동기로 고객 개인정보 보호(45%)와 더 효율적인 해외 거래(39%)를 꼽았습니다.                                                                                                                                                                             | deloitte 392행                             |
| 기업의 실제 이용       | EY-Parthenon                                                             | 이용률은 13%이고, 금융기관이 23%, 기업이 9%입니다.                                                                                                                                                                                                                      | ey 418행                                   |
| 기업의 실제 이용       | AFP(미국 재무 담당자 309명, 2026년 3월)                                  | 스테이블코인과 토큰화 상품은 "only 1% are piloting or using them in a limited capacity, while 9% are actively exploring the technology"입니다.                                                                                                                          | afp 99행                                   |
| 기업의 실제 이용       | PYMNTS(미국 중견기업 CFO 60명, 2026년 1월)                               | 이용 13%, 검토한 적 없음 58%입니다. 3년 안에 스테이블코인이 "even somewhat important"해질 것이라고 본 CFO는 4분의 1이 안 됩니다.                                                                                                                                        | pymnts-waiting 23, 44행                    |
| 도입을 가르는 조건     | PYMNTS                                                                   | 도움이 될 것으로 대형 은행과의 연동(45%)과 규제 명확성(40%)을 꼽았고, 빠른 정산과 유동성 개선은 25%, 비용 절감은 22%였습니다. 보고서는 "The issue is thus about trust, not efficiency or cost"라고 적습니다. 걸림돌은 규제 불확실성(67%)과 기존 시스템 연동(43%)입니다. | pymnts-waiting 46행, pymnts-promise 20행   |
| 도입을 가르는 조건     | EY-Parthenon                                                             | 걸림돌 1위는 규제 불확실성(73%), 2위는 회계와 세무 처리(38%)입니다. ERP 연동이 있으면 더 도입하겠다는 기업이 70%입니다.                                                                                                                                                 | ey 401, 462행                              |
| 받은 뒤 하는 일        | EY-Parthenon, PYMNTS                                                     | 기업의 79%가 거래 직후 법정화폐로 바꾸고(EY), 받은 스테이블코인의 88%를 바로 달러로 바꿉니다(PYMNTS).                                                                                                                                                                   | ey 465행, pymnts-waiting 41행              |
| 지급 사업자와 금융기관 | Fireblocks(은행, 결제 사업자, 핀테크, 암호화폐 사업자 295명, 2025년 3월) | 49%가 지급에 스테이블코인을 쓰고 있습니다. 이점은 빠른 정산(48%)이 1위이고 비용 절감(30%)이 가장 낮습니다. 같은 조사의 보도자료는 비용 절감을 32%로 적습니다.                                                                                                           | fireblocks-pr 126, 128행, fireblocks 187행 |

위 표의 기업 쪽 행을 단계 순서로 놓고, 지급 사업자와 금융기관 쪽을 옆에 두면 다음과 같습니다.

```text
[한국어판] 그림 11. 돈을 내는 기업: 단계마다 다른 조사가 잰 값
  (단계 사이를 화살표로 잇지 않았습니다. 조사마다 응답자와 질문이 달라서,
   한 단계의 값이 다음 단계의 값으로 줄었다고 읽을 수 없습니다)

  단계                값                                        조사
  ------------------  ----------------------------------------  ---------------------------
  문제를 겪는다       건당 수수료 10달러 이상 76%               Rapyd 2023, 기업 715곳
                      5일 이상 지연 38%
  관심이 있다         관심 용도 1위가 해외 공급사 지급 77%      EY 2025, 기관 350곳
  실제로 쓴다         1% (검토 중 9%)                           AFP 2026, 재무 담당자 309명
                      기업 9%                                   EY 2025
                      13%                                       PYMNTS 2026, CFO 60명
  받으면 바로 바꾼다  기업의 79%가 거래 직후 법정화폐로         EY 2025
                      받은 스테이블코인의 88%를 바로 달러로     PYMNTS 2026

  비교: 지급 사업자와 금융기관은 49%가 이미 지급에 씀 (Fireblocks 2025, 295명)
```

```text
[English] Figure 11. Businesses that pay: each stage measured by a different survey
  (No arrows join the stages. The surveys ask different people different questions,
   so a value cannot be read as having fallen to the next stage's value)

  Stage             Value                                         Survey
  ----------------  --------------------------------------------  ----------------------------------
  Feel the problem  fees of USD 10+ per payment 76%               Rapyd 2023, 715 firms
                    delays of 5+ days 38%
  Are interested    top use case: paying suppliers abroad 77%     EY 2025, 350 organisations
  Actually use      1% (exploring 9%)                             AFP 2026, 309 treasury professionals
                    corporates 9%                                 EY 2025
                    13%                                           PYMNTS 2026, 60 CFOs
  Convert at once   79% of firms convert to fiat right after      EY 2025
                    88% of stablecoins received go to USD at once PYMNTS 2026

  Compare: 49% of payment firms and financial institutions already use them for payments
  (Fireblocks 2025, 295 people)
```

이 그림은 위 표의 기업 쪽 행을 단계 순서로 다시 놓은 것입니다. 표는 조사별로 행을 나눠서, 문제를 느끼고 관심을 가진 기업은 많은데 실제로 쓰는 기업은 적다는 대비가 한눈에 보이지 않습니다. 단계 이름은 제가 붙였습니다.

단계 사이를 화살표로 잇지 않은 것은 각 단계의 값이 서로 다른 조사에서 왔기 때문입니다. 같은 응답자를 따라간 값이 아니므로, 76%에서 13%로 줄었다고 읽으면 안 됩니다. 마지막 단계의 두 값도 단위가 다릅니다. EY의 79%는 기업 수의 몫이고, PYMNTS의 88%는 받은 스테이블코인 금액의 몫입니다. 이 그림이 보여 주는 것은 각 조사가 같은 방향을 가리킨다는 점까지입니다. 마지막 단계는 기업이 스테이블코인을 쓰더라도 오래 들고 있지 않는다는 뜻이며, 나 절의 USDC 그림(그림 4)의 (3)과 이어집니다.

도입을 가르는 조건은 PYMNTS의 물음 하나로 막대를 그리면 다음과 같습니다.

```text
[한국어판] 그림 12. 무엇이 스테이블코인을 더 의미 있게 만들까: CFO의 답
  (PYMNTS, 미국 중견기업 CFO 60명, 2026년 1월. 막대 한 칸은 약 2%)

  대형 은행과의 연동      ###################### 45%
  규제 명확성             ####################   40%
  빠른 정산, 유동성 개선  ############           25%   <- Arc가 내세우는 쪽
  비용 절감               ###########            22%
```

```text
[English] Figure 12. What would make stablecoins more meaningful: CFOs' answers
  (PYMNTS, 60 CFOs at US mid-sized companies, January 2026. One mark is about 2%)

  Integration with major banks         ###################### 45%
  Regulatory clarity                   ####################   40%
  Faster settlement, better liquidity  ############           25%   <- what Arc offers
  Lower costs                          ###########            22%
```

막대는 PYMNTS 보고서의 한 문단(pymnts-waiting 46행)에 나온 네 값만 그렸습니다. 보고서가 이 문단에서 다른 항목을 더 들었는지는 이 페이지에 없습니다. Arc가 내세우는 빠른 확정에 해당하는 항목은 셋째 줄이고, 은행 연동과 규제보다 아래에 있습니다. 보고서는 이것을 "The issue is thus about trust, not efficiency or cost"라고 요약합니다. 응답자가 60명이므로 몇 %p 차이는 의미가 크지 않습니다.

[제 판단] 표에서 읽은 것은 다음과 같습니다.
- 문제의 체감은 있습니다. 지연과 수수료를 겪는 기업이 적지 않고(Rapyd), 관심을 가진 기업이 꼽는 용도 1위가 해외 지급입니다(EY, Deloitte). 그러므로 "고객 문제가 가볍다"는 전제는 이 조사들과도 맞지 않습니다.
- 그러나 돈을 내는 기업 가운데 실제로 옮긴 곳은 적습니다(AFP 1%, EY의 기업 9%, PYMNTS 13%). 세 수치가 다른 것은 질문이 달라서입니다. AFP는 유동성 운용 안에서 스테이블코인과 토큰화 상품을 물었고, EY와 PYMNTS는 이용 여부를 물었습니다.
- 도입을 가르는 것은 체인의 성능보다 규제, 은행과 ERP 연동, 회계입니다. 그림 8에서 Arc가 맡는 [1] 구간의 빠른 확정을 도움이 될 것으로 꼽은 CFO는 PYMNTS 응답에서 4분의 1이었습니다(위 막대 그림). 이 조건들은 모두 그림 8의 경로 밖에 있습니다.
- 지급 사업자와 금융기관은 훨씬 적극적입니다(Fireblocks 49%, EY의 금융기관 23%). Circle의 CPN과 StableFX가 금융기관을 고객으로 삼는 것은 이 차이와 맞습니다.
- 기업은 받은 스테이블코인을 오래 들고 있지 않습니다. 나 절과 이어 보면, 준비금 수익은 유통량에서 나오므로 통로로만 쓰이는 거래는 거래량에 비해 유통량을 적게 늘립니다 [확신도 낮음].
- 한계도 있습니다. 모두 의견과 의향을 물은 조사이고 실제 거래량이나 비용을 잰 것이 아닙니다. Fireblocks와 Rapyd는 관련 서비스를 파는 회사이고, EY와 Deloitte는 자문 회사입니다. 응답자는 미국이 많고, 한국이나 아시아 기업을 따로 물은 조사는 없습니다. Arc를 직접 물은 조사도 없습니다.
- 실제 사용의 측정은 여전히 비어 있습니다. 원고 04는 "이번 연구는 그 효과를 측정하지 않았다"고 적습니다(04 2327행). Circle의 HIFI 사례 글에 나오는 CPN 체인은 Ethereum, Polygon, Solana이고, Arc 실거래를 검증한 자료는 아닙니다(04 2402행). 반대로 "개별 실거래 자료를 확보하지 못한 것은 실제 사용이 없다는 증거가 아니다"(04 2406행)라는 점도 그대로 적용됩니다.
### 다-4. 확인하는 방법: 같은 조건에서 기존 방식과 전체 비용과 시간을 비교한다

- 원고 04는 실제 사용을 확인할 때 "참여 발표, 데모와 운영 실거래를 나눈다"고 적습니다(04 2408-2412행).
- 도입 판단의 기준은 비용, 운영 모델, 조직 요구, 법적 조건 넷입니다(04 2422행). 비용에 대해서는 "체인 전송의 가스가 저렴해도 기업의 전체 지급 비용이 저렴하다는 결론은 별도다"라고 적습니다(04 2428행).
- [제 판단] 해커톤 질문에 맞추면, 고객 한 부류(예: 해외 공급사에 대금을 보내는 중소기업)를 정하고, 같은 금액과 같은 수취 방식에서 기존 방식과 Arc를 쓰는 방식의 전체 비용과 전체 시간을 비교하는 것이 가장 직접적인 확인입니다.

### 다-5. 고객 쪽 정리: 문제는 무겁고 Arc는 그 일부에 닿지만, 도입은 다른 조건이 좌우한다

정리하면, 고객의 문제는 무겁고 [확신도 높음], Arc에서만 얻는 기능은 그 문제의 일부 구간에 닿습니다 [확신도 중간]. 공개 조사로 보면 기업은 그 문제를 느끼지만, 스테이블코인으로 옮기는 결정은 규제, 은행과 ERP 연동, 회계가 좌우하고 빠른 정산은 앞순위가 아닙니다 [확신도 중간]. 고객이 Arc 자체를 얼마나 중요하게 여기는지 물은 조사는 없습니다.

## 라. 1-4 Arc와 회사의 문제: Arc는 Circle 회사의 어떤 문제를 푸는가?

첫 답에서는 "자기 체인을 가지면 수수료와 서비스 수익을 얻을 자리가 생긴다"는 가설(확신도 낮음)을 적었습니다. 1차 자료를 열어 보니 절반만 맞았습니다. 수수료는 Circle 회사로 바로 들어가지 않고 검증자(validator)에게 갑니다. Circle은 검증자 무리의 "key participant"로서(콜 308행) 처음 검증자 무리에 든 다른 회사들과 함께 그 수수료를 나눠 받습니다. 수수료가 어디로 가는지는 자료가 나온 시점에 따라 설명이 다릅니다.

| 시점               | 자료                    | 수수료가 가는 곳                                                                                                                                                                   |
| ------------------ | ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2025년 8월         | litepaper [Circle 글]   | 출시 시점의 수수료는 "onchain Arc Treasury"로 갑니다(litepaper 229-230행). 이 금고를 누가 관리하는지는 이번 자료에서 확인하지 못했습니다.                                          |
| 1분기 실적 발표 때 | 토큰 백서 [Circle 글]   | 수수료를 ARC로 바꿔 검증자와 스테이커에게 나누고, 일부는 소각합니다. 나누는 비율은 거버넌스가 조정합니다(토큰 백서 374-385행).                                                     |
| 2분기 실적 콜      | CEO [Circle 발언]       | USDC로 낸 수수료는 "flows to validators"이고, Circle은 검증자 무리의 "key participant"입니다. 처음 검증자 무리에 든 다른 회사들도 이 수수료를 나눠 받을 수 있습니다(콜 304-310행). |
| 2026-09-16         | 메인넷 발표 [Circle 글] | 수수료는 앞으로도 USDC로 냅니다. PoS 전환은 2027년에 검토합니다(메인넷 87행).                                                                                                      |

이 내용을 바탕으로 1-4를 다음 네 항목으로 정리했습니다. 네 항목으로 나눈 것은 제 구분입니다. 다만 수입원의 목록은 CEO가 콜에서 든 것을 그대로 따랐습니다.

1. 지금 실제로 돈이 되는 것은 토큰 사전판매입니다 [공시][Circle 발언].
   - ARC 8억 750만 개를 개당 0.30달러에 팔기로 했고, 받을 돈은 약 2억 4,220만 달러입니다. 이 가운데 2억 2,200만 달러는 2분기에 이미 받았습니다(10-Q 1382-1384행).
   - 수익은 토큰 발행, 전달, PoA 전환, PoS 전환 같은 단계를 지날 때마다 인식합니다. 하반기에 1억 8,000만 달러를 인식하고, 나머지는 2027년에 인식합니다(콜 266-292행).
   - 이 수익에는 비용이 붙지 않아서 거의 그대로 이익이 됩니다(콜 285-289행).
   - 다만 2028년 5월 8일까지 PoS로 전환하지 못하면 환불해야 하는 조건이 있습니다(10-Q 1951-1953행). 추가 사전판매는 "no plans at this moment"라고 했습니다(콜 790행).
2. 나머지는 앞으로 생길 수입원입니다 [Circle 발언][Circle 글]. CEO는 PoS 전환 뒤의 스테이킹 수익, 토큰 인센티브, Arc 위에서 Circle이 만드는 제품을 들었습니다(콜 312-316행). Circle은 ARC 100억 개 가운데 25%를 가집니다(토큰 백서 435-445행). Arc 위의 USDC가 Circle의 수입이 되는지는 "partner by partner"라고 답했습니다(콜 826-836행).
3. Circle은 Arc에 자원을 모으고 있습니다 [Circle 발언]. CFO는 다른 블록체인과 제휴를 늘리는 대신 Arc 개발에 자원을 집중하기로 했다고 말했고, 이 결정을 기타 매출 전망을 바꾼 요인 가운데 하나로 들었습니다(콜 481-486행).
4. [제 판단, 확신도 중간] 회사의 목표와 제 해석에서 답이 다릅니다.
   - 회사의 목표(다변화)로 보면 Arc는 2026년에 토큰 사전판매로 금리와 무관한 매출을 실제로 더했지만, 그 돈은 한 번 들어오는 돈입니다(q6-answer.md 한 줄 답).
   - 제 해석(금리 의존)으로 보면 Arc는 아직 이 문제를 풀지 못했습니다. 1-2에서 제가 회사의 문제로 읽은 것은 매출의 95.2%가 금리에 묶인 준비금 수익이라는 점이었습니다(survey 462행).
     - Arc가 지금 금리와 상관없이 더해 준 돈은 한 번뿐인 토큰 판매 수익입니다.
     - 꾸준히 들어올 수입(검증자 몫, 스테이킹, Arc 위의 제품)은 PoS 전환 이후에 생기거나, 금액이 공개되지 않았습니다.
     - 또 Arc 위에 USDC가 쌓여서 생기는 이자는 여전히 준비금 수익입니다.
     - 그래서 이 경로로는 금리 의존이 줄지 않습니다.

네 항목을 시점 순서로 놓으면 다음과 같습니다.

```text
[한국어판] 그림 13. Arc가 Circle에 가져다주는 돈: 시점과 반복 여부

  2026 (지금)
    토큰 사전판매: 약 2.42억 달러, 그중 2.22억 달러는 2분기에 받음
      한 번 들어오는 돈. 하반기에 1.8억 달러, 나머지는 2027년에 수익으로 인식
      조건: 2028-05-08까지 PoS로 바꾸지 못하면 환불
     |
     v
  PoS 전환 뒤 (메인넷 발표는 2027년에 검토한다고 적음)
    스테이킹 수익, 토큰 인센티브, Arc 위에서 Circle이 만드는 제품
      반복될 수 있으나 금액은 공개되지 않음

  시점과 상관없이 그대로인 것
    Arc 위에 쌓인 USDC의 이자 = 여전히 준비금 수익 (금리에 묶여 있음)
```

```text
[English] Figure 13. Money Arc brings Circle: when it arrives and whether it repeats

  2026 (now)
    Token pre-sale: about USD 242 million, of which USD 222 million received in Q2
      Money that arrives once. USD 180 million recognised in H2, the rest in 2027
      Condition: refund if the move to PoS is not made by 2028-05-08
     |
     v
  After the move to PoS (the mainnet release says it will be reviewed in 2027)
    Staking revenue, token incentives, Circle products built on Arc
      Could repeat, but no amounts are disclosed

  Unchanged regardless of timing
    Interest on USDC held on Arc = still reserve income (tied to rates)
```

이 그림은 라 절의 네 항목을 시점으로 줄 세웠습니다. 산문에서는 "지금 실제로 돈이 되는 것"과 "앞으로 생길 수입원"이 다른 항목에 나뉘어 있어서, 확정된 돈은 한 번뿐이고 반복될 돈은 아직 시점과 금액이 없다는 대비가 잘 보이지 않습니다. 맨 아래 칸은 4번 항목의 판단입니다. Arc가 커져도 Arc 위의 USDC에서 나오는 이자는 준비금 수익이므로, 이 경로로는 금리 의존이 줄지 않습니다.

이 그림은 맨 위 지도의 "회사에게" 줄을 시점 쪽에서 자세히 본 것이고, 가격 쪽은 나 절 3번의 표가 다룹니다.

## 마. 고객별 에이전트: 에이전트는 고객마다 어떤 도움을 주는가?

표의 행에는 1-1의 고객 다섯 부류를 쓰고, 1-1에 없던 고객 둘을 더했습니다. 6행(API와 데이터를 파는 쪽)은 2번에서 드러나 3번에서 더한 고객이고, 7행(Arc Portal)은 이 답에서 자료를 읽다가 더한 고객입니다. 열은 제가 정했습니다. 특히 "도움이 닿는 쪽" 열은 에이전트가 누구의 것인지 구분하려고 넣었습니다.

| 고객                                                                                                | 회사가 말한 에이전트의 역할                                                                                                                                                                                                                                                                                                                                                                       | 도움이 닿는 쪽                                                                              | 상태                                                                                                                                                                                        | 근거                                                                                                                                                                  |
| --------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1. 은행, PSP, 기업 (CPN)                                                                            | CPN이 지원하려는 용도에 "agentic payments"가 들어 있습니다(10-K 500행) [공시]. CPN 백서는 물류 회사의 에이전트가 싱가포르 운송사를 고르면, CPN에 연결된 금융기관이 달러를 USDC로 바꿔 보내고 싱가포르 쪽 기관이 SGD로 지급하는 예를 듭니다 [Circle 글]. litepaper에는 기업 자금을 운용하고 지출 정책을 실행하는 Smart Treasury Agents가 있고, 이것을 CPN과 함께 쓴다고 적혀 있습니다 [Circle 글]. | 에이전트는 물류 회사나 기업 재무 부서의 것입니다. 은행과 PSP는 그 결제를 처리하는 쪽입니다. | 계획 단계입니다("In the future", CPN 백서 443행). Smart Treasury Agents는 Arc 로드맵 항목입니다.                                                                                            | 10-K 500-501행, CPN 백서 442-448행, litepaper 735-762행                                                                                                               |
| 2. 블록체인을 직접 다루기 어려운 기업 (Managed Payments)                                            | Managed Payments 출시 글 두 편에는 에이전트 이야기가 나오지 않습니다.                                                                                                                                                                                                                                                                                                                             | -                                                                                           | -                                                                                                                                                                                           | 없다(검색: `rg -n -i 'agent' <MP 글 두 편>`, 일치 0건)                                                                                                                |
| 3. 기관 환전 (StableFX)                                                                             | StableFX 제품 페이지와 10-K의 StableFX 절(510-515행)에는 에이전트 설명이 나오지 않습니다. 메인넷 발표문은 에이전트가 이미 "executing trades, managing payments, routing liquidity" 같은 일을 한다고 적었지만(메인넷 42행), StableFX를 직접 언급하지는 않습니다.                                                                                                                                   | -                                                                                           | -                                                                                                                                                                                           | 없다(검색: `rg -n -i 'agent' <StableFX 페이지>`, 일치 1줄이고 그 줄은 메뉴의 Agent Stack 링크. `sed -n '510,515p' <10-K> \| rg -c -i 'agent'`, 일치 0건), 메인넷 42행 |
| 4. 앱 개발자 (App Kits, Arc Studio, Skills)                                                         | 이 행에서 에이전트는 돈을 쓰는 주체가 아니라 개발을 돕는 도구입니다. Arc Studio는 "an onchain coding agent"이고(메인넷 77행), Circle Skills는 AI 코딩 도구로 개발하는 사람을 위한 구현 패턴입니다 [Circle 글].                                                                                                                                                                                    | 개발자 본인                                                                                 | 출시되었습니다. 다만 "Arc Studio deploys to Arc testnet only."입니다 [Team Arc 글].                                                                                                         | 메인넷 77행, Agent Stack 블로그 223행, arc-studio-cli 24행                                                                                                            |
| 5. 에이전트를 만드는 개발자 (Agent Stack)                                                           | 에이전트가 돈을 보관하고, 서비스를 찾고, 값을 치르게 합니다. 블로그가 지적한 문제는 에이전트 전용 지갑이 없어서 개인 키를 코드에 넣거나, 사람용 계정과 수동 승인에 기대야 했다는 점입니다. 해법은 사람이 정한 정책(기간별 지출 한도, 주소 허용 목록과 차단 목록)을 지갑이 실행 전에 검사하는 것입니다 [Circle 글].                                                                                | 개발자와 개발자가 만든 에이전트                                                             | Wallets, Marketplace, CLI는 2026년 5월에 출시되었습니다. 에이전트가 돈을 버는 기능은 하반기 계획입니다. Agent Sector(에이전트 신원과 감사 기록)는 로드맵 항목이고, AgentVM은 설계 중입니다. | Agent Stack 블로그 204-213행, 실적 보도자료 91-94행, 메인넷 46, 86행                                                                                                  |
| 6. (1-1에 없던 고객, 2번에서 드러남) API와 데이터를 파는 쪽 (Agent Marketplace, x402, Nanopayments) | Agent Stack 블로그는 Agent Marketplace가 서비스 이용을 "human-scale subscriptions and manual integrations"에서 사용량 기반 결제로 옮긴다고 적습니다. Nanopayments는 가스비 없이 1센트보다 작은 금액도 옮기는 장치입니다 [Circle 글].                                                                                                                                                              | 서비스를 파는 쪽입니다. 돈을 쓰는 것은 사는 쪽의 에이전트입니다.                            | 결제를 받는 장치는 나왔습니다. "Agents can earn"은 하반기에 짓는 중입니다("H2 2026 - BUILDING").                                                                                            | Agent Stack 블로그 214, 222행, 2분기 발표 자료 528행                                                                                                                  |
| 7. (1-1에 없던 고객) 에이전트에게 일을 맡기는 사람 (Arc Portal)                                     | Arc Portal은 "lets people fund agent wallets, set spend limits, and delegate onchain tasks"라고 소개됩니다 [Circle 글].                                                                                                                                                                                                                                                                           | 일을 맡기는 사람                                                                            | 메인넷 발표문은 이미 쓸 수 있는 창구로 소개합니다.                                                                                                                                          | 메인넷 45행                                                                                                                                                           |

- [제 판단, 확신도 높음] 에이전트 기능이 실제로 출시된 곳은 개발자, 파는 쪽, 개인 쪽(4, 5, 6, 7행)뿐입니다. 기업과 금융기관 쪽(1행)은 아직 예시와 로드맵 단계입니다. 2행과 3행은 이번에 확인한 자료에서 에이전트 이야기를 찾지 못했습니다.
- 표를 채우면서 보니 "에이전트"가 두 가지 뜻으로 쓰이고 있었습니다. 하나는 돈을 쓰는 주체(1, 5, 6, 7행)이고, 다른 하나는 사람을 돕는 개발 도구(4행)입니다. 이 구분은 제가 붙인 것입니다. 다만 메인넷 발표문도 Arc Studio를 "BUILT FOR AGENTS AS ECONOMIC ACTORS" 절(40행)이 아니라 개발 도구를 소개하는 부분(77행)에 두었습니다. 이 구분이 맞는지는 2번(에이전트를 바라보는 관점)에서 자료로 확인했습니다.

위 표의 일곱 고객을 "에이전트"의 뜻과 출시 상태로 나누면 다음과 같습니다. 두 축은 제가 정했고, 숫자는 표의 행 번호입니다.

```text
[한국어판] 그림 14. "에이전트"의 두 뜻과 출시 상태

                     출시됨                                 계획, 예시, 로드맵
  ----------------------------------------------------------------------------------------
  돈을 쓰는 주체     5 에이전트를 만드는 개발자             1 은행, PSP, 기업 (CPN)
                     6 API와 데이터를 파는 쪽 (받는 장치)   5의 돈을 버는 기능 (하반기)
                     7 일을 맡기는 사람 (Arc Portal)        6의 "Agents can earn" (하반기)
  ----------------------------------------------------------------------------------------
  개발을 돕는 도구   4 앱 개발자 (Arc Studio, Skills)       -
                       Arc Studio는 테스트넷에만 배포

  에이전트 이야기를 찾지 못한 행: 2 Managed Payments, 3 StableFX
```

```text
[English] Figure 14. Two meanings of "agent" and release status

                                Released                                 Planned, example or roadmap
  ------------------------------------------------------------------------------------------------------
  Actor that spends money       5 developers building agents             1 banks, PSPs, businesses (CPN)
                                6 API and data sellers (receiving)       5's earning functions (H2)
                                7 people delegating tasks (Arc Portal)   6's "Agents can earn" (H2)
  ------------------------------------------------------------------------------------------------------
  Tool that helps development   4 app developers (Arc Studio, Skills)    -
                                  Arc Studio deploys to testnet only

  Rows where no agent story was found: 2 Managed Payments, 3 StableFX
```

이 그림은 바로 위 두 bullet의 판단을 한 번에 보여 줍니다. 하나는 출시된 곳이 개발자, 파는 쪽, 개인 쪽(4, 5, 6, 7행)이고 Circle 매출과 가까운 기업과 금융기관(1행)은 계획 단계라는 것입니다. 다른 하나는 "에이전트"가 돈을 쓰는 주체와 개발 도구라는 두 뜻으로 쓰인다는 것입니다. 표는 상태 열에 이것을 문장으로 적어서 두 판단이 한눈에 겹쳐 보이지 않습니다.

5행과 6행은 기능의 일부가 출시되었고 일부는 하반기 계획이라 두 칸에 나눠 적었습니다. 2행과 3행은 이번에 확인한 자료에서 에이전트 이야기를 찾지 못한 것이고, 에이전트 기능이 없다는 뜻은 아닙니다.

## 바. 1-5 발표와 실제: 발표한 것과 실제로 낸 것은 어디서 어긋나는가?

| 항목                                   | 어긋나는 점                                                                                                                                                                                                                                                                                                                                                                                                      | 근거                                      |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------- |
| Arc 프라이버시                         | 공시의 설계 다섯 가지에 들어 있지만, 문서에는 "not yet available on Arc"라고 적혀 있습니다.                                                                                                                                                                                                                                                                                                                      | why 307행                                 |
| StableFX                               | 2025년 말 10-K는 "StableFX is currently in beta."라고 적었습니다. 2026년 2분기 10-Q는 StableFX를 "built on Arc"인 환전 엔진이라고만 적고, 10-Q 전체에 beta라는 낱말이 없습니다(`rg -c -i 'beta' <10-Q>`, 일치 0건). 메인넷 보도자료는 StableFX가 "enables 24/7 programmable FX trading"이라고 현재형으로 적습니다. 2026년 자료는 베타라는 말 없이 운영 중인 제품으로 적으므로, 이 행은 어긋남으로 남지 않습니다. | 10-K 511행, 10-Q 1909-1911행, 메인넷 32행 |
| Agent Stack 구성                       | Agent Stack 출시 글(2026-05-11)은 "five core components"를 들고 Circle Skills를 넣습니다. 2분기 10-Q는 "Agent Stack consists of four components"라고 적고 Circle Skills를 넣지 않습니다.                                                                                                                                                                                                                         | Agent Stack 블로그 204행, 10-Q 107-114행  |
| Arc의 세 부문(Payment, Privacy, Agent) | 메인넷 발표에 들어 있지만 아직 향후 계획입니다.                                                                                                                                                                                                                                                                                                                                                                  | survey 1001행                             |
| 에이전트가 돈을 버는 기능              | 하반기 계획으로 발표되었습니다.                                                                                                                                                                                                                                                                                                                                                                                  | survey 1230행                             |
| Agent 관련 제품 전체                   | 지금 쓸 수 있는 것이 10개, 테스트넷 참조 구현만 있는 것이 1개, 설계 중이거나 로드맵에 있는 것이 2개입니다.                                                                                                                                                                                                                                                                                                       | products 238행                            |
| Arc Studio와 CLI                       | 메인넷 발표에 개발 도구로 소개되었지만, 개발 문서는 "Arc Studio deploys to Arc testnet only."라고 적습니다. CLI는 Arc Studio를 명령줄에서 쓰게 하는 얇은 클라이언트이므로 같은 제약을 받습니다.                                                                                                                                                                                                                  | arc-studio-cli 14-17, 24행                |

## 1번의 결과를 다음 질문에서 쓰는 곳

- 4번(Arc를 어떻게 볼 수 있는가)은 1-3과 1-4에서 출발합니다. 4번이 인용한 1-3의 원래 문장은 "Arc에서만 풀리는 고객 문제는 좁다"였고, 2026-10-14에 "Arc에서만 얻는 기능의 범위는 좁다(고객 문제의 무게는 판단하지 않음)"로 고쳤습니다.
- 6번(방향이 맞는가)에서는 1-2의 회사 목표와 제 해석(금리 의존), 1-5의 어긋남을 다룹니다.
- 2번과 3번에서는 Agent Stack의 내용과 마 절의 고객별 에이전트를 다룹니다.

## 한계

- 가 절부터 다 절까지와 바 절은 vault의 2차 문서(survey, why, kit, products)에 기댔습니다. verifier는 그 문서 안의 행과 표지를 대조했고, 그 문서가 인용한 원문(10-K, 10-Q의 행)은 이번에 열지 않았습니다(`checks/q1-verify.txt`의 마지막 줄). 라 절과 마 절은 1차 자료를 직접 대조했습니다(`checks/q1b-verify.txt`). 2026-10-14에 본문에 반영한 다섯 곳의 1차 자료 대조는 checks/q1d-verify.txt에 있습니다. 같은 날 사용자 피드백으로 다시 쓴 가 절, 나 절, 다 절은 1차 자료와 연구 원고를 직접 열었고, 대조 결과는 checks/q1e-verify.txt에 있습니다. 가 절의 두 번째 표(고객 다섯 부류)는 여전히 survey에 기댑니다.
- 나 절 1번의 금리 표는 회사 내부 모델의 계산이고, 유통량이 고정된다는 가정을 깔고 있습니다. 금리가 USDC 수요를 바꾸는 경로는 회사도 계산하지 않았고, 저도 추정하지 않았습니다. 나 절 3번(ARC 토큰)은 2분기 10-Q에 보유분의 회계 처리 문장이 없어, 가격 상승이 손익에 어떻게 나타나는지 모르는 채로 썼습니다.
- 처음 답을 쓸 때 `cb/works/ai-chat/2026-10-05-arc-research-structure/outputs/` 아래의 원고를 [미독]으로 적어 두고도 열지 않았고, survey로 대신했습니다. 2026-10-14에 그중 01(무엇인가), 04(사업 이해), 06(가치와 토큰)을 열어 가 절, 나 절 3번, 다 절에 썼습니다. 세 원고 모두 인용 위치 표에 적은 행과 그 주변만 읽었습니다[열람: 범위]. arc-section-08 계열 파일과 `cb/derived/circle-arc-hub.md`는 여전히 [미독]입니다.
- 다 절 3번의 외부 조사 여덟 건은 발행 기관이 공개한 요약 페이지만 읽었고, 보고서 PDF 본문은 받지 않았습니다. 후보는 웹 검색으로 찾았지만 검색 도구의 요약은 쓰지 않았습니다. 요약 하나가 GENIUS Act의 상원 통과를 2026년으로 잘못 적었기 때문입니다. 받지 못한 자료(SWIFT 2017 조사, PNC 기사)와 결과 수치가 없어 보관하지 않은 자료(msg 2025 조사)는 조사 묶음의 목록에 적었습니다.
- 웹 검색은 두 번 했습니다. 하나는 일반 검색이고, 다른 하나는 circle.com과 arc.io로 범위를 좁힌 검색입니다. 10월 7일 이후에 나온 Arc 경제나 에이전트 관련 1차 자료는 두 번의 검색에서 나오지 않았습니다. 검색 도구가 미국 기준이고 찾기만 하는 검색이었으므로, 이것은 자료가 없다는 뜻이 아니라 두 번의 검색에서 보이지 않았다는 뜻입니다. 근거로 쓴 본문은 모두 vault에 이미 있는 사본입니다. 검색 결과에서 확인한 페이지는 다음과 같습니다.
  - [Circle Launches Arc Mainnet](https://www.circle.com/pressroom/circle-launches-arc-mainnet-an-economic-operating-system-for-the-internet)
  - [Circle Reports Second Quarter 2026 Results](https://www.circle.com/pressroom/circle-reports-second-quarter-2026-results)
  - [Circle Launches AI Infrastructure to Power the Agentic Economy](https://www.circle.com/pressroom/circle-launches-ai-infrastructure-to-power-the-agentic-economy)
  - [Internet Financial System Report](https://www.circle.com/reports/internet-financial-system/arc-and-circle-infrastructure) [미독]. 이 페이지는 `cb/derived/circle-arc-public-material-outline.md`가 이미 참조하고 있습니다.

## 뒤에서 고친 것

이 답을 보낸 뒤 2번부터 6번까지를 쓰면서 원문을 다시 열었고, 다음 다섯 곳이 달라졌습니다. 2026-10-14에 다섯 곳을 모두 위의 본문에 반영했습니다. 여기에는 고친 이유와 근거, 대화에서 보낸 원래 문장을 남깁니다.

1. 1-2의 "회사의 문제"를 6번에서 제 해석으로 낮췄습니다. 10-Q는 새 제품의 목표를 "drive our reserve income"(10-Q 1896행)과 "diversifying our revenue profile"(1896-1897행) 두 가지로 적습니다. 회사의 목표는 금리 의존을 줄이는 것이 아니라 준비금 수익을 키우면서 다변화하는 것입니다. 그래서 6번은 회사의 방향을 이 두 목표로 판정하고, 금리 의존은 제 해석으로 한 줄만 두었습니다(q6-answer.md 나 절, q6-report.md 1번). 3번도 같은 점을 적었습니다(q3-report.md 2번).
   - 반영한 곳: 한 줄 답, 나 절의 첫머리와 마지막 줄, 라 절 4번, "1번의 결과를 다음 질문에서 쓰는 곳"의 6번 줄.
   - 원래 문장: 나 절 첫머리는 "매출이 금리에 묶여 있다는 점입니다."였고, 나 절 마지막 줄은 "그래서 저는 1-1의 제품 확장을 이 의존을 줄이려는 시도로 읽었습니다 [제 판단]."이었으며, 라 절 4번은 "Arc는 아직 금리 의존 문제를 풀지 못했습니다. 1-2에서 본 회사의 문제는 ..."로 시작했습니다.
2. 라 절의 수수료 문장은 3번에서 더 정확하게 고쳤습니다. 원문은 수수료가 검증자에게 가고 Circle이 검증자 무리의 "key participant"라고 말합니다(콜 308행). 그래서 3번은 Circle을 "여러 검증자 가운데 하나로서 나눠 받는 쪽"으로 적었습니다(q3-report.md 7번).
   - 반영한 곳: 라 절 첫머리와 표의 2분기 실적 콜 행.
   - 원래 문장: "Circle은 검증자 가운데 한 곳으로서 그 일부를 받습니다."와 "Circle은 검증자 가운데 한 곳입니다(콜 304-310행)."
3. 바 절의 StableFX 행은 6번에서 닫았습니다. 2025년 10-K는 "StableFX is currently in beta."라고 적고(10-K 511행), 2분기 10-Q에는 beta라는 낱말이 나오지 않으며(`rg -c -i 'beta' <10-Q>`, 일치 0건), 메인넷 보도자료는 현재형으로 적습니다. 그래서 "2026년 자료는 베타라는 말 없이 운영 중인 제품으로 적는다"로 정리했습니다(q6-report.md 3번, q6-answer.md 다 절).
   - 반영한 곳: 바 절의 StableFX 행. 근거를 survey에서 10-K, 10-Q, 메인넷 보도자료로 바꿨습니다.
   - 원래 문장: "2025년 말 10-K에는 "currently in beta"라고 적혀 있고, 베타가 끝났는지는 확인되지 않았습니다." (근거 survey 1189-1190행)
4. 바 절의 Agent Stack 구성 행과 Arc Studio 행은 1차 출처로 바꿨습니다. 구성은 6번에서 Agent Stack 출시 글(다섯 가지, Circle Skills 포함)과 10-Q(네 가지, Circle Skills 없음)를 직접 대조했습니다(q6-report.md 4번). Arc Studio가 테스트넷에만 배포한다는 문장은 3번에서 Arc 개발 문서 `arc-studio-cli.md` 24행으로 바꿨습니다(q3-report.md 6번).
   - 반영한 곳: 바 절의 Agent Stack 구성 행과 Arc Studio 행, 마 절 표의 4행.
   - 원래 문장: Agent Stack 구성 행은 "제품 페이지와 답변은 다섯 가지를 들지만, 10-Q에는 "four components"라고 적혀 있습니다." (근거 survey 1217행)였습니다. Arc Studio 행은 "결과물을 테스트넷에만 배포합니다." (근거 kit 87행)였고, 마 절 4행의 상태 칸은 "다만 Studio는 테스트넷에만 배포합니다." (근거에 kit 87행)였습니다.
5. 마 절의 고객 표는 3번에서 일곱 행으로 넓어졌습니다. 3번은 2번에서 드러난 고객(API와 데이터를 파는 쪽)을 6행으로 더했고, 이 답의 6행(Arc Portal)은 7행이 되었습니다(q3-report.md 1번, q3-answer.md 가 절).
   - 반영한 곳: 마 절의 머리말, 표의 6행과 7행, 표 아래 두 줄의 행 번호, 한 줄 답의 마지막 문장.
   - 원래 문장: 표는 여섯 행이었고, 머리말은 "자료에서 새로 나온 고객 하나를 더했습니다", 한 줄 답은 "에이전트 기능이 실제로 출시된 곳은 개발자와 개인 쪽이고"였습니다.

## 사용자 피드백으로 고친 것

사용자는 2026-10-14와 10-15에 1번에 대해 피드백을 여섯 차례 주었습니다. 차례마다 소절을 두었습니다. 기록이 가리키는 절과 소절의 이름은 그 피드백을 반영할 때의 이름이고, 2026-10-15에 목차를 만들며 바꾼 제목은 12번에 적었습니다.

### 첫 번째 피드백(2026-10-14): 제품 목록, 금리와 토큰, 고객 문제의 전제

사용자는 2026-10-14에 1번에 대해 세 가지 피드백을 주었습니다. 각 피드백의 원문, 고친 곳, 대화에서 보낸 원래 문장을 남깁니다.

1. 1-1 피드백 원문: "보여준 표가 너무 빈약해보임. cb/works/ai-chat/2026-10-05-arc-research-structure/ 에서 이것과 관련된 조사를 했는데 왜 여기의 내용을 전혀 안 읽은 것 같지? Circle이 주도하는 제품들을 다시 리스팅하고 다시 제시"
   - 왜 읽지 않았는가: 처음 답의 한계 절에 그 폴더의 원고를 [미독]으로 적어 두고도 열지 않았고, survey의 표로 대신했습니다.
   - 고친 곳: 가 절에 "1. 제품 목록"을 새로 넣었습니다. 2분기 10-Q의 세 기둥과 제품 목록(10-Q 1863-1869, 1898-1911행)을 기준으로 16개 제품을 나열하고, 연구 원고 01과 04, 제품 페이지를 함께 썼습니다. 처음 보낸 다섯 행 표는 "2. 고객 다섯 부류"로 남겼습니다.
   - 원래 문장(가 절 첫머리): "고객은 금융기관, 기업, 개발자로 나뉘고, 제품마다 겨냥하는 문제가 다릅니다. Circle은 스스로 사업을 세 층(애플리케이션, 디지털 자산과 서비스, Arc와 개발자 인프라)으로 나누고(survey 411행), 이 세 층이 "designed to reinforce one another"라고 설명합니다 [공시] (survey 443행)."
2. 1-2 피드백 원문: "매출이 금리에 묶여있다는 것은 오케이. 금리가 올라가고 내려감에 따라 어떻게 될지도 보여줘야함. 최근에 달러/국채금리/스테이블코인 관련 문서를 만들면서 이 내용 정리했으니 참고할 것 USDC만으로 모든 걸 하려고 한다는 것도 문제가 아냐? 그리고 추가적으로 Arc 토큰이 가치를 크게 갖는다면, 어떨거 같니?"
   - 고친 곳: 나 절의 "제가 읽은 문제" 줄과 근거 bullet을 10-Q 원문으로 바꿨고, 세 소절(금리가 오르고 내리면, USDC 하나로 모든 것을 하려는 것도 문제인가, ARC 토큰의 가치가 크게 오른다면)을 더했습니다. 금리 문서는 `cb/derived/dollar-stablecoin-market-guide.md`(인용 위치 표의 guide)입니다.
   - 원래 문장: "제가 읽은 문제" 줄은 "매출이 금리에 묶여 있다는 점입니다. 회사는 이것을 목표로 적지 않았으므로 제 해석입니다."였습니다(줄의 머리 "제가 읽은 문제 [제 판단]:"과 끝의 "근거는 아래와 같습니다."는 옮기지 않았습니다). 근거 bullet 셋은 survey 459-462행(매출 7.01억 달러, 준비금 수익 95.2%), 498행(유통량 25% 증가, 수익 5% 증가, 수익률 4.1%에서 3.5%), 484, 493행(비용 4.12억 달러, 매출의 59%)에 기댔고, 59%는 survey가 100%에서 마진 41%를 빼서 계산한 값이었습니다.
3. 1-3 피드백 원문: 사용자는 다 절의 마지막 문장을 인용하고 "너가 언급한 이 부분에서. 이 고객의 문제가 매우 핵심적이고 심각한게 아니라는 전제인거잖아? 그걸 어떻게 알 수가 있을까?"라고 물었습니다.
   - 답: 알 수 없었고, 판단하지도 않았습니다. 처음 문장은 기능의 범위를 말하려 했지만, 고객 문제가 가볍다는 뜻으로도 읽히게 썼습니다.
   - 고친 곳: 다 절 첫 문장과 마지막 bullet, 새 소절 "고객의 문제가 핵심적이지 않다는 것을 어떻게 아는가", 한 줄 답, "1번의 결과를 다음 질문에서 쓰는 곳"의 4번 줄. 같은 문장을 인용한 q4-answer.md의 두 곳도 같은 날 고쳤습니다.
   - 원래 문장: 다 절 첫 문장은 "[제 판단, 확신도 중간] Arc에서만 풀리는 고객 문제는 좁습니다."였고, 마지막 bullet은 "따라서 지금 고객이 Arc에서 얻는 것은 USDC로 내는 가스비, 빠른 확정, StableFX의 정산 장소 정도로 보입니다. 나머지는 기존 체인과 같은 조건에서 비교해 봐야 할 후보입니다 [제 판단]."이었습니다. 한 줄 답의 해당 문장은 "Arc에서만 풀리는 고객 문제는 좁습니다(USDC로 내는 가스비, 빠른 확정, StableFX의 정산 장소)."였습니다.

### 두 번째 피드백(2026-10-14): 시각화, 외부 조사, USDC 중심 인프라

같은 날 사용자는 두 번째 피드백 셋을 주었습니다. 원문, 고친 곳, 원래 문장은 다음과 같습니다.

4. 시각화 피드백 원문: 사용자는 다 절의 1번(문제의 무게)과 2번(Arc가 맡는 몫)을 인용하고 "아래 부분을 묶어서 시각화 자료 만들 수 있을 것 같은데?"라고 했습니다.
   - 고친 곳: 다 절 "고객의 문제가 핵심적이지 않다는 것을 어떻게 아는가"의 2번 뒤에 한국어판과 영어판 그림과 그 설명을 넣었습니다. 기존 표와 문장은 그대로 두었습니다.
5. 외부 조사 피드백 원문: 사용자는 다 절의 3번(고객이 얼마나 중요하게 여기는지)과 4번(확인하는 방법)을 인용하고 "아래 부분은 충분히 외부 검색을 통해서도 힌트를 얻을 수 있는 것 같은데? 분명히 연구나 조사 이런게 있을 것 같은데?"라고 했습니다.
   - 고친 곳: 공개 조사 여덟 건을 새 수집 단위로 받고, 다 절 3번을 다시 썼습니다. 다 절의 정리 문장, 한 줄 답, 한계 절도 고쳤습니다. 같은 내용을 옮겨 적은 q4-answer.md의 나 절 첫머리도 같은 날 고쳤습니다.
   - 원래 문장(다 절 3번): "**고객이 이 문제를 얼마나 중요하게 여기는지는 모릅니다.** 원고 04는 "이번 연구는 그 효과를 측정하지 않았다"고 적습니다(04 2327행). Circle의 HIFI 사례 글에 나오는 CPN 체인은 Ethereum, Polygon, Solana이고, Arc 실거래를 검증한 자료는 아닙니다(04 2402행). 반대로 "개별 실거래 자료를 확보하지 못한 것은 실제 사용이 없다는 증거가 아니다"(04 2406행)라는 점도 그대로 적용됩니다."
   - 원래 문장(다 절 정리): "정리하면, 고객의 문제는 무겁고 [확신도 높음], Arc에서만 얻는 기능은 그 문제의 일부 구간에 닿으며 [확신도 중간], 그 구간이 고객에게 얼마나 중요한지는 측정되지 않았습니다."
   - 원래 문장(한 줄 답): "다만 고객의 문제 자체는 무겁고, Arc가 맡는 구간이 고객에게 얼마나 중요한지는 측정되지 않았습니다."
6. USDC 인프라 피드백 원문: 나 절 2번의 첫 소절을 인용한 물음이며, 원문은 나 절 2번의 새 소절 "USDC 중심 인프라라는 해석: 제품과 매출에서 각각 맞는가" 첫 문단에 그대로 옮겼습니다.
   - 고친 곳: 그 소절을 새로 넣었습니다. 기존 문장은 고치지 않았습니다.

### 세 번째 피드백(2026-10-14): 그림 열셋, 다 절 그림, USDC 그림

같은 날 사용자는 세 번째 피드백 셋을 주었습니다.

7. 그림 추가 피드백 원문: "우선 문서 안에 중요 내용들을 선정하고, 그것들을 시각화 자료로 설명하는 내용을 추가할 것"
   - 고친 곳: 그림 열셋을 더했습니다. 한 줄 답 뒤에 이 답 전체의 지도, 가 절 1번 끝에 제품과 Arc의 관계, 나 절 1번 끝에 금리 1%p의 계산, 나 절 2번 소절 끝에 USDC 중심 인프라, 나 절 3번 끝에 ARC 가격과 금리의 비교, 다 절에 지도 표와 그림 A, B, C, 다 절 3번에 기업의 단계별 비율과 도입 조건 막대, 라 절 끝에 Arc가 가져다주는 돈의 시점, 마 절 끝에 "에이전트"의 두 뜻과 출시 상태입니다. 그림마다 한국어판, 영어판, 설명을 붙였고, 그림의 숫자와 이름은 모두 본문이 이미 인용한 자리에서 가져왔습니다(`checks/q1g-claims.txt`).
   - 넣지 않은 곳: 가 절 2번(고객 다섯 부류)과 바 절(발표와 실제의 어긋남)은 표가 이미 항목마다 한 줄로 설명하고 있어서, 그림이 더할 관계가 없다고 보고 넣지 않았습니다.
8. 다 절 그림 피드백 원문: "시각화 내용이 너무 헷갈리는데? 이거 하나 그리지 말고 여러가지로 우선 설명한다고 생각하고 다시 그려봐."
   - 헷갈린 이유(제 진단): 옛 그림은 순서가 있는 경로와 순서가 없는 조건을 한 틀에 넣었고, Arc의 몫을 네 가지 표지(맡는 구간, 없음, 일부, 간접)로 섞어 적었습니다.
   - 고친 곳: 다 절의 그림을 지도 표 하나와 그림 A(시간), B(비용), C(위험과 자금)로 바꿨습니다. 그림마다 구조 종류 하나만 씁니다. 옛 그림과 그 설명은 커밋 f54385abd의 `cb/derived/arc-hackathon-questions-20261014/q1-answer.md` 176-256행에 있고, 옛 그림의 숫자는 새 그림에 모두 남았습니다.
9. USDC 그림 피드백 원문: "아래 내용을 담는 시각화 자료 하나 그려봐"(나 절 2번 소절의 세 의견과 정리를 인용)
   - 고친 곳: 그 소절 끝에 그림 하나를 넣었습니다. 화살표를 세 뜻(돈이 흐름, USDC 쪽으로 이어짐, 확인하지 않음)과 빠져나감으로 나눴고, 확신도가 낮은 USYC의 고리에는 화살표를 긋지 않았습니다.

### 네 번째 피드백(2026-10-15): ARC 가격, StableFX와 외환 비용

2026-10-15에 사용자는 네 번째 피드백을 주었습니다.

10. ARC 가격 피드백 원문: "현재 토큰 가격이 2배로 오른다면? 10배로 오른다면? 이런 것은 고려 안 해도 되는게 맞니?"(나 절 3번의 비교 표를 인용)
   - 제 진단: 비교 표가 0.30달러 한 가격만 적어서, 가격이 오를 때 금액이 얼마나 커지는지를 가렸습니다. 10배에서는 보유분의 값이 연간 준비금 수익의 약 3년 치가 되므로 무시할 수 없습니다. 금리 수입을 대신하기 어렵다는 판단은 유지하지만, 그 근거는 금액이 아니라 한 번 매기는 값이라는 점, 회계 처리를 모른다는 점, 해마다 반복되는 몫 가운데 가격과 함께 커지는 것이 발행분뿐이라는 점입니다.
   - 고친 곳: 한 줄 답의 ARC 문장, 나 절 3번의 첫 문단과 보유분 및 스테이킹 bullet, 비교 표의 두 행을 고쳤고, 가격별 크기 표(1배, 2배, 10배)를 더했습니다.
   - 원래 문장(한 줄 답): "ARC 토큰의 가치가 크게 올라도 해마다 들어오는 금리 수입을 대신하기는 어렵다고 판단합니다."
   - 원래 문장(나 절 3번 첫 문단): "[제 판단, 확신도 낮음] Circle이 가진 토큰의 평가액과 앞으로의 토큰 판매와 스테이킹 수입은 커집니다. 그러나 해마다 들어오는 금리 수입에 대한 의존을 대신하기는 어렵습니다. 근거는 아래와 같습니다."
   - 원래 표의 두 행: 보유분의 조건 칸은 "회계 처리 문장을 찾지 못함", 스테이킹의 조건 칸은 "PoS 전환 뒤에만 생김"이었습니다.
11. StableFX 피드백 원문: "아래에서 1.4% 비용을 Arc를 통해서는 못 한다는 의미인거지? 그런데, Arc를 통해서 StableFX를 사용한다면? 결국 Arc를 통해 외한 비용을 아낀다면? 그러면 계산을 다시 할 수 있는게 아냐? 아닌가? 그건 그냥 StableFX가 해결하는 무언가인가?"(그림 B의 설명을 인용). 이어서 "StableX 관련해서 더 찾아서 너가 말한 '채울 숫자'가 있는지 볼것"[원문 그대로]
   - 제 진단: 그림 B가 1.4%를 "통화를 바꾸는 가격"으로 적어 고정된 값처럼 보이게 했고, StableFX를 거쳐 외환 쪽에 닿는 길을 빠뜨렸습니다. 원고 04의 판단을 따져 보지 않고 옮긴 것이 원인입니다.
   - 고친 곳: 다 절 2번 항목의 지급 비용 bullet, 지도 표의 비용 행, 그림 B와 그 설명을 고쳤고, 그림 B 아래에 "외환 1.4%를 StableFX로 줄인다면" 계산과 판단을 더했습니다. 나 절 2번 소절의 EURC bullet에는 지원 통화가 늘어난 것을 더했습니다. 처음에는 그림 C에도 비용 줄을 더하려 했지만, 그림 B가 같은 내용을 담게 되어 그림 C는 그대로 두었습니다.
   - 원래 문장(그림 B 아래): "비용의 87.1%를 차지하는 외환 가격은 Arc가 바꾸지 않습니다." 그림 안의 줄은 "외환 1.4%: 통화를 바꾸는 가격. Arc의 몫 없음"이었고, 지도 표의 비용 행 Arc의 몫은 "작고, 미측정"이었습니다.
   - 새로 받은 자료: StableFX 외환 비용 자료 묶음(13건). StableFX의 실제 가격, 수수료, 거래량은 찾지 못했습니다.
   - 검증: `checks/q1h-claims.txt`, `checks/q1h-verify.txt`.

### 다섯 번째 피드백(2026-10-15): 목차

12. 목차 피드백 원문: "q1-answer.md(이하 answer.md) 에 목차를 만들어서 내가 캐치하기 쉽게 만들 것. 목차들을 보면서 제대로 된 목차인지 보고, 그렇지 않다면 수정할 것. 그 동안 answer.md 수정이 생겼는데, 이 answer.md를 만드는데에 기반한 하위 문서들을 수정하지 않았다면 수정할 것."[원문 그대로, 줄바꿈 둘은 공백으로 옮김]
   - 제 진단: 제목만 읽어서는 답의 구조와 결론이 보이지 않았습니다.
     - "한 줄 답" 절에 한 줄 답 말고도 소질문의 구분, 표지의 뜻, 전체 지도 그림이 함께 있었습니다.
     - 다 절은 가장 긴 절(커밋 d22adfc36에서 435-766행)인데 소절 제목이 하나뿐이었습니다. 그 제목("고객의 문제가 핵심적이지 않다는 것을 어떻게 아는가")은 피드백의 물음을 옮긴 것이어서, 그 아래의 답(문제는 무겁다)이 보이지 않았습니다.
     - 그 아래의 네 항목은 번호 목록이어서, 그 안의 그림 여섯과 표 셋(하나는 StableFX 계산 표)이 목차에 나오지 않았습니다. StableFX 계산은 굵은 글씨로만 구분되어 있었습니다.
     - 나 절 3번의 가격별 표(2배, 10배)도 제목이 없었습니다.
     - 이 절의 제목 "사용자 피드백으로 고친 것(2026-10-14)"은 10-15의 기록(10번과 11번)을 담고 있어 날짜가 맞지 않았습니다.
   - 고친 곳:
     - 맨 앞에 목차를 더했습니다. 형식은 같은 폴더의 q4-answer.md 목차를 따랐습니다.
     - 절 제목은 물음 앞에 개념 이름을 붙였고(가-바와 1-1부터 1-5까지는 그대로), 소절 제목은 그 소절의 답을 줄인 말로 바꿨습니다.
     - 소절 번호는 가-1, 나-1 꼴로 바꿨지만 번호 값은 그대로이므로, "나 절 3번", "다 절 3번" 같은 기존 참조는 그대로 맞습니다.
     - "한 줄 답"에서 "읽는 법"과 "이 답의 지도"를 떼어 절로 두었습니다.
     - 다 절에서는 소절 제목 하나를 없애고, 그 아래의 번호 항목 넷을 다-1부터 다-4까지의 소절로 올렸으며, 정리 문단에 다-5라는 제목을 붙였습니다. 다-2 아래에는 시간, 비용, StableFX 계산, 위험과 자금의 소절을 두었습니다.
     - 나-3 아래에는 두 표의 소절을 두었습니다.
     - 이 절은 제목에서 날짜를 빼고 차례마다 소절을 두었습니다.
   - 바꾼 문장: 번호 목록의 표지(번호와 굵은 글씨)와 들여쓰기를 없앴고, 문장은 그대로 두었습니다. StableFX 계산 문단의 굵은 글씨 머리("외환 1.4%를 StableFX로 줄인다면: 채울 수 있는 숫자.")는 소절 제목으로 옮기면서 콜론 뒤를 "채울 수 있는 숫자와 비어 있는 칸"으로 바꿨습니다. 소절이 바뀌어 고친 곳은 다섯입니다.
     - 다 절 첫머리의 안내 문장이 없어진 소절 이름 대신 다-1부터 다-4까지를 가리키게 했습니다.
     - 다 절 첫머리에 이 넷이 사용자의 물음에 답한다는 문단을 더했습니다.
     - 그림 넷의 안내에서 "위 1번(문제의 무게)과 2번(Arc가 맡는 몫)"을 다-1과 다-2로, 숫자의 출처 "2번 항목"을 "이 소절 첫머리 bullet"로 바꿨습니다.
     - 지도 표 설명의 "2번 항목의 판단"도 같은 방식으로 바꿨습니다.
     - 맨 위 머리말에 10-15의 두 피드백을 더했습니다.
   - 원래 제목: 커밋 d22adfc36의 이 파일에 있습니다(`git show d22adfc36:cb/derived/arc-hackathon-questions-20261014/q1-answer.md | grep '^#'`).
   - 하위 문서: 이 답을 위해 만들었거나 이 답을 설명하는 문서를 다시 보았습니다. 폴더 README의 1번 설명, StableFX 외환 비용 자료 묶음과 수요 조사 묶음 README의 "쓰이는 곳", 허브의 StableFX 자료 행을 고쳤습니다. 2번부터 7번까지의 답에서는 1번에서 10-14와 10-15에 바뀐 문장을 옮겨 쓴 곳을 찾지 못해 고치지 않았습니다(검색 명령은 `checks/q1i-claims.txt`). 1번의 그림은 다른 답과 달리 `figures/`에 원본 파일이 없고, 그림 요소의 근거 대응은 `checks/q1g-claims.txt`와 `checks/q1h-claims.txt`에 있습니다.
   - 검증: `checks/q1i-claims.txt`, `checks/q1i-verify.txt`.

### 여섯 번째 피드백(2026-10-15): 한 줄 답의 모양

13. 한 줄 답 피드백 원문: 사용자는 2번 답 2-2 절의 한 줄 답(약관과 책임을 다룬 긴 문단, q2-answer.md 189행)을 예로 들어 "이게 어떻게 한줄이라고 표현하지? 의미적으로 한줄이라는게 뭔지 생각해야 하는 것 아냐?"라고 묻고, 그 문단을 문장마다 bullet로 나누고 인용과 숫자를 하위 bullet로 내린 예를 보인 뒤 "위의 내용 참고해서 자기 자신의 문서 리뷰하고 고칠 것"이라고 했습니다.
   - 제 진단: 1번의 한 줄 답도 같았습니다. "니다."로 끝나는 문장 10개, 841자(공백 포함)의 문단 하나여서 한 줄 답이 아니라 본문의 요약이었고, 절마다 다른 결론이 한 문단에 이어져 있어 어느 문장이 어느 절의 결론인지 보이지 않았습니다. 같은 모양(목록이나 대응표여야 할 내용이 문단 하나에 이어진 것)이 다른 곳에도 있었습니다.
   - 고친 곳:
     - 한 줄 답: 맨 앞에 실제 한 문장을 두고, 원래 문단의 문장을 절별(가 절부터 바 절까지) bullet로 나눴습니다. 원래 문단에 없던 두 줄을 더했습니다. 하나는 다 절의 StableFX 경로(10-15에 더한 내용)이고, 다른 하나는 바 절의 결론입니다. 둘 다 본문과 목차에 이미 있는 문장을 옮긴 것입니다.
     - 맨 위 머리말: 고친 순서를 날짜별 목록으로 나눴습니다.
     - 읽는 법: 표지의 뜻을 표로, 절마다 다른 근거의 종류를 목록으로 나눴습니다.
     - 나-2의 USDC 중심 인프라 소절: 세 주장 (1), (2), (3)을 번호 목록으로 나눴습니다.
     - 나-3: 보유분 bullet의 다섯 문장을 하위 bullet로, 가격별 크기 아래의 세 근거 (1), (2), (3)을 번호 목록으로 나눴습니다.
     - 라 절 4번: 회사의 목표로 본 답과 제 해석으로 본 답을 하위 bullet 둘로 나눴습니다.
     - 인용 위치 절의 머리말: 표를 읽을 때 알아 둘 네 가지를 목록으로 나눴습니다.
     - 이 절의 12번: 진단, 고친 곳, 바꾼 문장을 하위 bullet로 나눴습니다.
   - 바꾼 문장: 문장의 내용은 바꾸지 않았습니다. 목록으로 나누면서 이어 주던 말(쉼표로 이은 절, "(1)" 같은 번호)을 문장 끝이나 목록 표지로 바꿨고, 한 줄 답의 첫 문장, 위에 적은 두 줄, 그리고 목록 앞의 안내 문장("다음과 같습니다" 꼴)을 새로 썼습니다.
   - 원래 문단: 커밋 9dbb75b4d의 이 파일에 있습니다(한 줄 답은 51행).
   - 검증: `checks/q1j-claims.txt`, `checks/q1j-verify.txt`.

### 일곱 번째 요청(2026-10-15): 그림 리뷰

14. 2026-10-15에 사용자가 "이후 새 시각화 스킬 이용해서 q*-answer.md 들의 시각화 자료들 리뷰."를 요청했고, 리뷰 보고를 받은 뒤 "모두 진행"이라고 했습니다. 리뷰 전체와 고친 내용은 figures/review-20261015.md에 있습니다.
   - 그림 11(돈을 내는 기업의 단계): 단계 사이의 화살표를 뺐습니다. 단계마다 다른 조사의 값인데 화살표가 같은 응답자가 줄어드는 깔때기처럼 읽히게 했습니다. 마지막 단계의 두 값은 단위(기업 수의 몫, 금액의 몫)를 적었습니다. 원래 설명의 두 문장은 "이 그림은 단계를 내려갈수록 비율이 줄어드는 모양을 보여 주려고 그렸습니다."와 "그림 머리에 적은 대로, 각 단계의 값은 서로 다른 조사에서 왔습니다."였습니다.
   - 그림 4(USDC 중심 인프라): (3)의 "가스를 USDC로만 낸다 -> Arc에서 거래하려면 USDC가 있어야 한다"의 `->`는 범례에 없는 기호여서 "그래서"로 바꿨습니다. 설명의 "돈은 아래쪽 USDC에서 나옵니다."는 그림에서 USDC가 아래에 있지 않아서 "매출의 95.2%는 USDC 유통량에서 나오는 준비금 수익입니다."로 바꿨습니다.
   - 그림 7(다-2의 지도 표): 안내 문장 "그림 넷으로 나눠 그렸습니다. 첫 표는 넷의 지도이고"와 표 제목 "아래 세 그림의 지도"가 서로 맞지 않아서, 둘 다 지도 표와 그림 8, 9, 10으로 적었습니다.
   - 그림 이름: 일곱 답의 그림 이름을 답마다 1부터 매기는 "그림 N"으로 맞췄습니다. 이 답의 그림은 그림 1부터 14까지이고, 그림 A, B, C는 그림 8, 9, 10이 되었습니다. 이 절의 앞 항목들에 남은 옛 이름은 그때의 이름입니다.
   - 나 절의 2분기 매출: "7억 132만 달러"를 3번 답과 같은 "7억 131만 5천 달러"로 바꿨습니다(6번 답 그림 1은 "7억 131만"이었습니다).

## 인용 위치

이 표를 읽을 때 알아 둘 것은 다음과 같습니다.

- 행 번호는 1부터 셉니다(`sed -n` 기준). 인용 안의 " / "는 원문의 줄바꿈입니다.
- litepaper 229-230행의 "onchain Arc Treasury"는 원문에서 "Trea-"와 "sury"로 줄이 나뉘어 있어, 인용 대조 도구는 찾지 못하고 verifier는 글자가 같다고 확인했습니다(`checks/q1b-verify.txt`의 D3).
- 약칭 "콜"은 아래 표의 2분기 애널리스트 콜 파일입니다. 같은 폴더에 있는 다른 사본(`web-circle-q2-2026-earnings-call-transcript.md`)은 행 번호가 다르고, 3번과 6번은 그 사본을 인용했습니다.
- 첫 합본까지의 검증 기록은 다음과 같습니다. 그 뒤의 검증은 "사용자 피드백으로 고친 것"의 각 항목에 있습니다.
  - 첫 답: checks/q1-verify.txt(22건, 어긋남 1건은 행 번호 하나였고 본문에 반영함)
  - 뒤의 답: checks/q1b-verify.txt(30건, 어긋남 0건)
  - 합본 때 새로 쓰거나 바꾼 줄 10개: `cb/derived/arc-hackathon-questions-20261014/checks/q1c-verify.txt`에서 대조했고, 판정 30줄이 모두 확인됨입니다(센 명령은 그 파일 머리에 있습니다).

| 인용한 곳                                                                     | 경로와 행                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| survey (Circle 회사 조사 답)                                                  | `cb/derived/circle-company-survey-answer.md:411, 415, 443, 459-462, 484, 493, 498, 992-997, 1001, 1002, 1125, 1143, 1184, 1186, 1189-1190, 1216, 1217, 1230` (1189-1190, 1217은 뒤에서 고친 것 3, 4의 원래 근거)                                                                                                                                                                                                                                                                                                                                                                   |
| why (Arc를 이해해야 하는 이유)                                                | `cb/works/ai-chat/2026-10-05-arc-research-structure/outputs/arc-section-02-why-understanding.md:211, 305, 307`                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| kit (App Kit과 직접 구현 비교)                                                | `cb/works/ai-chat/2026-10-10-aiagents-hackathon/outputs/arc-app-kit-vs-build-ai-guide.md:87-88`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| products (Circle과 Arc 에이전트 제품 안내)                                    | `cb/works/ai-chat/2026-10-13-circle-arc-agent-products/outputs/circle-arc-agent-products-guide.md:210, 238`                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| 콜 (2분기 애널리스트 콜)                                                      | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-analyst-call-transcript.md:266-292, 285-289, 304-310, 308, 312-313, 312-316, 481-486, 790, 826-836`                                                                                                                                                                                                                                                                                                                                                                                             |
| 10-Q (2026년 2분기)                                                           | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-10q.md:107-114, 1382-1384, 1896-1897, 1909-1911, 1951-1953`                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 10-Q (2026년 2분기, 2026-10-14 추가분)                                        | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-10q.md:126-127, 783-786, 1863-1869, 1885-1911, 1942-1953, 2051-2052, 2059, 2274-2280, 2299-2302, 2673, 2817-2849`                                                                                                                                                                                                                                                                                                                                                                               |
| 1분기 10-Q                                                                    | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q1-2026-10q.md:2744-2745, 2798-2814`                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| guide (달러, 국채금리, 스테이블코인 시장 안내)                                | `cb/derived/dollar-stablecoin-market-guide.md:274, 278`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| 01 (연구 원고, Arc는 무엇인가)                                                | `cb/works/ai-chat/2026-10-05-arc-research-structure/outputs/arc-section-01-what.md:515, 716-727, 739, 745, 749`                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| 04 (연구 원고, 사업 이해)                                                     | `cb/works/ai-chat/2026-10-05-arc-research-structure/outputs/arc-section-04-business.md:1101-1123, 1155, 2327, 2376, 2402, 2406, 2408-2412, 2422, 2428`                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 06 (연구 원고, 가치와 토큰)                                                   | `cb/works/ai-chat/2026-10-05-arc-research-structure/outputs/arc-section-06-value-token.md:492, 1188`                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| FSB 2020, FSB 2023                                                            | `cb/works/web/2026-10-07-enterprise-payment-process-sources/pages/P090420-1.txt:32-33, 46`, `cb/works/web/2026-10-07-enterprise-payment-process-sources/pages/P091023-1.txt:172`                                                                                                                                                                                                                                                                                                                                                                                                   |
| FSB 2025                                                                      | `cb/works/web/2026-10-05-arc-builder-research-checks/pages/revision-fsb-cross-border-2025.md:1447-1448, 2540, 2571`                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| SWIFT                                                                         | `cb/works/web/2026-10-05-arc-builder-research-checks/pages/revision-swift-payment-time-web.md:209, 212-213, 228`                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| BIS 2026                                                                      | `cb/works/web/2026-10-08-enterprise-payment-problem-sources/pages/bis-qr-2026-06-fx-settlement-risk.txt:837, 893, 907`                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 제품 페이지 넷 (cpn-product, stablefx-overview, cpn-managed, refund-protocol) | `cb/works/web/2026-10-05-arc-builder-research-checks/pages/revision-business-cpn-product.md:66-67`, `research-stablefx-overview.md:29, 81`, `research-cpn-managed.md:24-25`, `revision-business-refund-protocol.md:39` (모두 같은 폴더)                                                                                                                                                                                                                                                                                                                                            |
| stablecoin-native-model (Arc 개발 문서)                                       | `cb/works/web/2026-10-07-arc-official-library/pages/en/docs/arc/concepts/stablecoin-native-model.md:12, 92-94, 111-112, 132, 132-137`                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| 조사 묶음 (2026-10-14 받은 공개 조사 여덟 건)                                 | `cb/works/web/2026-10-14-corporate-stablecoin-demand-surveys/pages/` 아래 ey는 `ey-2025-stablecoin-survey.txt:393, 401, 418, 439, 453, 462, 465`, afp는 `afp-2026-liquidity-survey-release.txt:99`, pymnts-waiting은 `pymnts-2026-03-cfo-stablecoins-waiting.txt:23, 41, 44, 46`, pymnts-promise는 `pymnts-2026-03-cfo-stablecoins-promise.txt:20`, deloitte는 `deloitte-2025-cfo-signals-crypto.txt:392`, rapyd는 `rapyd-2023-cross-border-release.txt:91, 93`, fireblocks는 `fireblocks-state-of-stablecoins.txt:187`, fireblocks-pr은 `fireblocks-pr-seekingalpha.txt:126, 128` |
| StableFX 외환 비용 묶음 (2026-10-15 받은 자료) | `cb/works/web/2026-10-15-stablefx-fx-cost-sources/pages/` 아래 StableFX 개요는 `circle-stablefx-overview.md:26, 29`, StableFX 기술 안내서는 `circle-stablefx-technical-guide.md:100, 139-140`, taker 안내는 `circle-stablefx-quickstart-taker.md:82, 95`, StableFX API 명세는 `circle-stablefx-openapi.yaml:821-822`, StableFX 지원 통화는 `circle-stablefx-supported-currencies.md:28-43`, StableFX 2026 릴리스 노트는 `circle-stablefx-release-notes-2026.md:29`, Circle Mint 상환 수수료는 `circle-mint-redemption-structure.txt:41-47, 87`, FSB 방법론은 `fsb-2025-kpi-methodology.txt:367, 399-401`, HBS(Du, Scharfstein, Huang 2026 BIS 발표 슬라이드)는 `du-scharfstein-huang-2026-bis-slides.txt:151, 156, 197, 294, 305, 337, 353, 364, 400, 409` |
| 10-K (2025년)                                                                 | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-fy2025-10k.md:500, 500-501, 510-515, 511`                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| CPN 백서                                                                      | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-cpn-whitepaper.md:442-448, 443`                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 실적 보도자료 (2분기)                                                         | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-earnings-release.md:91-94`                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 토큰 백서                                                                     | `cb/works/web/2026-10-07-arc-official-library/pages/web-arc-token-whitepaper.md:234-235, 327, 374-385, 376, 435-445, 436-437, 438-439`                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| litepaper                                                                     | `cb/works/web/2026-10-07-arc-official-library/pages/web-arc-litepaper.md:229-230, 735-762`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 메인넷 (Circle 메인넷 보도자료)                                               | `cb/works/web/2026-09-20-circle-arc-primary-sources/raw/circle-mainnet-launch.md:32, 40, 42, 45, 46, 77, 86, 87`                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Agent Stack 블로그                                                            | `cb/works/web/2026-10-13-circle-agent-stack-sources/pages/circle-blog-introducing-agent-stack.txt:204, 204-213, 214, 222, 223`                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| MP 글 두 편 (Managed Payments 출시 글)                                        | `cb/works/circle-blog/2026-04-08-blog-simplify-stablecoin-adoption-with-cpn-managed-payments/pages/simplify-stablecoin-adoption-with-cpn-managed-payments.en.md`, `cb/works/circle-blog/2026-05-13-blog-cpn-managed-payments-stablecoin-settlement-made-simple/pages/cpn-managed-payments-stablecoin-settlement-made-simple.en.md` (부재 검색의 대상)                                                                                                                                                                                                                              |
| StableFX 페이지                                                               | `cb/works/web/2026-10-02-stablecoin-onchain-investor/pages/circle-stablefx.txt:266` (부재 검색에서 일치한 메뉴 줄)                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Arc 개발 문서 arc-studio-cli                                                  | `cb/works/web/2026-10-07-arc-official-library/pages/en/docs/ai/arc-studio-cli.md:14-17, 24` (뒤에서 고친 것 4)                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 2분기 발표 자료 (Agent Stack 쪽)                                              | `cb/works/web/2026-09-26-circle-quarterly-reports-sources/pages/web-circle-q2-2026-earnings-presentation.md:528` (뒤에서 고친 것 5)                                                                                                                                                                                                                                                                                                                                                                                                                                                |
