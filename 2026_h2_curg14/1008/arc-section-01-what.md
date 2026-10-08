# Arc의 정의, 구성과 관계: Arc는 무엇이며, 무엇으로 이루어지고, 서로 어떻게 연결되는가

Arc는 여러 참여자가 같은 거래 기록과 계약 상태를 확인하고, 정해진 합의 규칙에 따라 그 결과를 확정하는 Layer-1 블록체인이다. Circle은 이 네트워크를 금융 앱과 자산 및 개발 도구가 함께 사용하는 기반으로 설명한다. Arc를 이해하려면 네트워크, 그 위에서 이동하는 자산, 자산을 다루는 제품과 서비스, 서비스를 운영하는 회사 및 금융기관을 함께 보아야 한다.

기준일은 2026-10-05의 수집 자료다.

이 원고는 먼저 Arc가 무엇인지 정의하고, Arc 네트워크와 그 위의 자산, 서비스와 참여자를 구성요소별로 구별한 뒤, 이 구성요소들이 한 업무에서 어떻게 연결되는지 설명한다. 마지막에 설명 범위와 후속 질문을 정리한다. 정의, 구성과 관계로 나눈 이 순서는 회사와 네트워크, 자산의 권리, 참여자의 역할 및 완료 상태를 혼동하지 않도록 내가 구성한 설명 순서다. 각 개념의 세부 조건은 본문에 유지한다.

**섹션 전체의 관계: 구성요소에서 업무 결과까지**

아래 그림은 이 원고에 나오는 구성요소를 세 구역에 나누어 배치했다. 맨 위는 사업과 계약의 주체, 가운데는 체인 밖에서 요청하고 승인하는 이용자 쪽, 맨 아래는 Arc 체인 위의 처리다. 구역 구분과 번호는 한 지급 요청을 따라가도록 내가 정했으며 Circle의 공식 구조도가 아니다.

한국어:

```text
== 사업과 계약 ============================================================
                                    [Circle과 관련 법인]   [발행자와 금융기관]
                                             |                     ^
                                             | (1) 제품 제공       |
== 이용자와 앱: 체인 밖 =====================|=====================|=====
                                             v                     |
 [사용자, 승인 주체] ---(2) 요청---> [제품과 앱] ------------------+
          |                                  ^           (6) 발행, 상환,
          | (3) 승인                         |               현지 지급 요청
          v                                  |
 [지갑과 서명 서비스]                        | (5) 결과 조회
          |                                  |
== Arc 네트워크: 체인 위 ====================|===========================
          | (4) 서명한 거래 제출             |
          v                                  |
 [RPC와 노드] -> [합의와 실행] -> [계정, 잔액, 계약 상태]
```

English:

```text
== Business and contracts ===================================================
                                    [Circle and affiliates]   [Issuers and FIs]
                                             |                        ^
                                             | (1) provide products   |
== Users and apps: offchain =================|========================|=====
                                             v                        |
 [User / authorizer] ---(2) request--> [Products and apps] -----------+
          |                                  ^              (6) issue, redeem,
          | (3) authorize                    |                  local payout
          v                                  |
 [Wallet and signer]                         | (5) read results
          |                                  |
== Arc network: onchain =====================|==============================
          | (4) submit signed tx             |
          v                                  |
 [RPC, nodes] -> [Consensus, execution] -> [Accounts, balances, state]
```

그림은 번호 순서로 읽는다. (1) Circle과 관련 법인은 지갑, 지급 API와 개발 도구 같은 제품을 제공하고, 앱이 그 기능을 조합한다. (2) 사용자가 앱에 원하는 업무를 요청하면 (3) 지갑 유형에 맞는 승인 주체가 승인하고, 지갑과 서명 서비스가 서명을 만든다. (4) 서명한 거래는 RPC와 노드를 거쳐 체인에 들어가고, 허가된 검증자의 합의와 실행을 거쳐 계정, 잔액과 계약 상태를 바꾼다. (5) 앱은 그 결과를 체인에서 다시 읽는다. (6) 현지 통화 지급이나 발행자 상환처럼 체인 거래만으로 끝나지 않는 업무는 앱이나 이용 기관이 발행자 또는 금융기관에 따로 요청한다.

같은 구역에 놓인 것은 같은 쪽에서 처리된다는 뜻이며, 위아래 배치가 소유나 지휘 관계를 뜻하지는 않는다. 지갑의 서명은 체인 밖에서 만들어지고, 체인의 상태는 거래가 처리돼야만 바뀐다. 모든 제품과 업무가 Arc를 사용하는 것은 아니며 (6)은 업무에 따라 필요할 때만 생긴다.

스테이블코인(stablecoin)은 가치 안정화를 목표로 한 토큰 범주이며 가격 유지와 발행자 상환은 각각 조건을 확인해야 한다. 최종성(finality)은 확정된 기록을 되돌릴 수 있는지에 관한 성질이고, 검증자(validator)의 합의 참여는 풀 노드의 독립 검증과 구별한다. 소수 자릿수(decimals)는 원시 정수를 금액으로 읽는 자릿수이며 계산의 정확도를 뜻하는 정밀도(precision)와 다르다.

**목차**

- [Arc의 정의, 구성과 관계: Arc는 무엇이며, 무엇으로 이루어지고, 서로 어떻게 연결되는가](#arc의-정의-구성과-관계-arc는-무엇이며-무엇으로-이루어지고-서로-어떻게-연결되는가)
  - [1. 정의: Arc는 무엇이며, 이 원고는 어디까지를 함께 설명하는가](#1-정의-arc는-무엇이며-이-원고는-어디까지를-함께-설명하는가)
    - [1.1 Layer-1 네트워크: Arc는 어떤 블록체인인가](#11-layer-1-네트워크-arc는-어떤-블록체인인가)
    - [1.2 Economic OS: Circle은 Arc를 어떤 기반으로 제시하는가](#12-economic-os-circle은-arc를-어떤-기반으로-제시하는가)
  - [2. 구성: Arc 네트워크와 그 위의 자산, 서비스와 참여자는 각각 무엇을 맡는가](#2-구성-arc-네트워크와-그-위의-자산-서비스와-참여자는-각각-무엇을-맡는가)
    - [2.1 네트워크: 거래를 처리하는 규칙과 그 처리를 맡는 주체는 무엇인가](#21-네트워크-거래를-처리하는-규칙과-그-처리를-맡는-주체는-무엇인가)
      - [2.1.1 실행 규칙과 원장: Arc는 거래를 어떤 규칙으로 실행하고 그 결과를 어디에 기록하는가](#211-실행-규칙과-원장-arc는-거래를-어떤-규칙으로-실행하고-그-결과를-어디에-기록하는가)
      - [2.1.2 노드와 검증자: 거래 처리, 상태 검증과 합의는 누가 맡는가](#212-노드와-검증자-거래-처리-상태-검증과-합의는-누가-맡는가)
    - [2.2 자산과 기록: 무엇을 보유하며, 그 권리와 수량은 어디에 어떻게 기록되는가](#22-자산과-기록-무엇을-보유하며-그-권리와-수량은-어디에-어떻게-기록되는가)
      - [2.2.1 자산의 유형: 지급 자산, 투자 상품, 네트워크 토큰과 회사 주식은 어떻게 다른가](#221-자산의-유형-지급-자산-투자-상품-네트워크-토큰과-회사-주식은-어떻게-다른가)
      - [2.2.2 계정과 주소: 잔액과 계약 상태는 어디에 귀속되는가](#222-계정과-주소-잔액과-계약-상태는-어디에-귀속되는가)
      - [2.2.3 잔액과 인터페이스: Arc는 USDC 잔액 하나를 네이티브와 ERC-20 두 방식으로 어떻게 다루는가](#223-잔액과-인터페이스-arc는-usdc-잔액-하나를-네이티브와-erc-20-두-방식으로-어떻게-다루는가)
      - [2.2.4 기록의 위치: 체인별 상태와 수탁 서비스의 장부는 어떻게 다른가](#224-기록의-위치-체인별-상태와-수탁-서비스의-장부는-어떻게-다른가)
    - [2.3 제품과 서비스: Circle의 제품은 어떤 일을 처리하고, 승인 권한은 누가 통제하는가](#23-제품과-서비스-circle의-제품은-어떤-일을-처리하고-승인-권한은-누가-통제하는가)
      - [2.3.1 제품과 앱: 제공되는 기능은 사용자 업무에 어떻게 연결되는가](#231-제품과-앱-제공되는-기능은-사용자-업무에-어떻게-연결되는가)
      - [2.3.2 지갑과 서명 서비스: 자산 이전을 승인하는 권한은 누가 통제하는가](#232-지갑과-서명-서비스-자산-이전을-승인하는-권한은-누가-통제하는가)
    - [2.4 회사와 기관: 사업, 발행과 금융서비스의 주체는 어떻게 나뉘는가](#24-회사와-기관-사업-발행과-금융서비스의-주체는-어떻게-나뉘는가)
      - [2.4.1 회사와 법인: 사업과 계약의 주체는 어떻게 구분되는가](#241-회사와-법인-사업과-계약의-주체는-어떻게-구분되는가)
      - [2.4.2 발행자와 금융기관: 자산의 발행, 상환과 금융서비스는 누가 맡는가](#242-발행자와-금융기관-자산의-발행-상환과-금융서비스는-누가-맡는가)
    - [2.5 사용자와 개발자: 거래 의도와 앱의 업무 규칙은 누가 정하는가](#25-사용자와-개발자-거래-의도와-앱의-업무-규칙은-누가-정하는가)
  - [3. 관계: 구성요소들은 한 업무에서 서로 어떻게 연결되는가](#3-관계-구성요소들은-한-업무에서-서로-어떻게-연결되는가)
    - [3.1 역할 분담: 누가 무엇을 제공하고 요청하며 처리하는가](#31-역할-분담-누가-무엇을-제공하고-요청하며-처리하는가)
    - [3.2 거래 처리: 승인한 요청은 어떻게 기록된 결과가 되는가](#32-거래-처리-승인한-요청은-어떻게-기록된-결과가-되는가)
      - [3.2.1 승인과 제출: 거래 요청은 어떤 권한으로 네트워크에 전달되는가](#321-승인과-제출-거래-요청은-어떤-권한으로-네트워크에-전달되는가)
      - [3.2.2 실행과 확정: 거래는 상태를 어떻게 바꾸고 그 결과는 어떻게 확정되는가](#322-실행과-확정-거래는-상태를-어떻게-바꾸고-그-결과는-어떻게-확정되는가)
      - [3.2.3 결과 확인: 접수, 실행 성공과 확정은 어떻게 구별하는가](#323-결과-확인-접수-실행-성공과-확정은-어떻게-구별하는가)
    - [3.3 업무 결과: 여러 주체와 서비스의 처리는 어떤 결과로 이어지는가](#33-업무-결과-여러-주체와-서비스의-처리는-어떤-결과로-이어지는가)
      - [3.3.1 자산 이전: 출발지의 자산은 어떻게 목적지에서 사용할 수 있게 되는가](#331-자산-이전-출발지의-자산은-어떻게-목적지에서-사용할-수-있게-되는가)
      - [3.3.2 자산 교환: 견적과 승인은 어떻게 서로 다른 자산의 교환으로 이어지는가](#332-자산-교환-견적과-승인은-어떻게-서로-다른-자산의-교환으로-이어지는가)
      - [3.3.3 지급과 수취: 정산은 어떻게 최종 수취인의 지급 결과로 이어지는가](#333-지급과-수취-정산은-어떻게-최종-수취인의-지급-결과로-이어지는가)
  - [4. 설명 범위: 공통 개념으로 설명할 수 있는 것과 추가 확인할 것은 무엇인가](#4-설명-범위-공통-개념으로-설명할-수-있는-것과-추가-확인할-것은-무엇인가)
    - [4.1 제공 상태: 개념과 설계 설명은 현재 이용 가능성과 어떻게 구별되는가](#41-제공-상태-개념과-설계-설명은-현재-이용-가능성과-어떻게-구별되는가)
    - [4.2 후속 질문: 필요성, 기술, 업무와 개발 분석에서 어떤 조건을 더 확인해야 하는가](#42-후속-질문-필요성-기술-업무와-개발-분석에서-어떤-조건을-더-확인해야-하는가)

Arc의 설계와 사양은 공식 영문 기술 문서, Litepaper와 Whitepaper를 근거로 설명한다. 공식 자료가 서로 다르게 설명하는 조건은 해당 부분에 함께 적었다. 다른 체인 비교, 법률 자료와 고정 커밋의 코드 관찰도 각각의 출처와 적용 범위를 구별한다.

공식 블로그의 관련 설명은 본문에서 원문 링크로 연결한다. 공식 발표와 설계 설명은 실제 운영을 직접 관측한 근거와 구별한다.

## 1. 정의: Arc는 무엇이며, 이 원고는 어디까지를 함께 설명하는가

Arc는 두 층위에서 설명할 수 있다. 하나는 Arc를 자체 합의로 거래 기록을 확정하는 Layer-1 네트워크로 보는 설명이고(1.1), 다른 하나는 Circle이 백서에서 제시한 Economic OS, 곧 핵심 인프라부터 앱까지 걸친 구성이다(1.2). 이 원고에서 "Arc"는 네트워크를 가리킨다. 그 위에서 이동하는 자산, 네트워크를 이용하는 제품과 서비스, 이를 운영하는 회사와 기관, 그리고 사용자와 개발자는 2절(구성)에서 네트워크와 함께 구성요소로 다루고, 이들의 연결은 3절(관계)에서 설명한다. 이 범위 구분은 원고 본문이 Arc를 네트워크의 이름으로 쓰는 용법에 맞춰 내가 정했다.

### 1.1 Layer-1 네트워크: Arc는 어떤 블록체인인가

Arc는 스테이블코인 금융과 자산 토큰화(tokenization)를 위해 설계한 EVM 호환 Layer-1 블록체인이다. Litepaper는 USDC 가스, 결정적 최종성(deterministic finality)과 로드맵에 포함된 선택형 프라이버시(opt-in privacy)를 핵심 설계로 제시한다. Token Whitepaper는 Arc를 경제 활동의 공유 인프라로 설계한 공개된 개방형 네트워크라고 설명한다.

공식 글 연결: [Introducing Arc: An Open Layer-1 Blockchain Purpose-Built for Stablecoin Finance](https://www.circle.com/blog/introducing-arc-an-open-layer-1-blockchain-purpose-built-for-stablecoin-finance) (2025-08-12, [공식 원문](https://www.circle.com/blog/introducing-arc-an-open-layer-1-blockchain-purpose-built-for-stablecoin-finance)). Circle의 최초 소개는 EVM 호환성과 스테이블코인 금융을 위한 설계를 설명한다. 당시의 출시 계획과 현재 운영 상태는 구별한다.

[Token Whitepaper의 Arc 정의](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/arc_whitepaper.pdf)의 원문은 다음과 같다.

> a public, open Layer–1 blockchain network purpose-built as shared infrastructure for economic activity.

Layer-1은 다른 체인의 확정에 전적으로 의존하지 않고 자체 합의로 기본 거래 기록을 확정하는 네트워크를 뜻한다. Arc의 실행 환경은 EVM(Ethereum Virtual Machine, 이더리움 가상머신)과 호환된다. Solidity로 작성한 계약과 익숙한 EVM 도구를 사용할 수 있다는 뜻이지만, 가스 자산, USDC의 내부 처리와 모든 운영 조건이 Ethereum과 같다는 뜻은 아니다.

### 1.2 Economic OS: Circle은 Arc를 어떤 기반으로 제시하는가

회사 발표의 Economic OS라는 표현은 금융 앱, 자산과 시장이 같은 기반 위에서 작동하도록 만들겠다는 제품 비전이다. 이 표현을 보고 은행 지급, 자산 상환, 기밀 거래와 에이전트 기능이 모두 현재 제공된다고 판단하면 실제 지원 범위가 달라진다. 메인넷 발표도 기밀 기능을 개발 중으로 표시한다. 제품 비전과 개별 기능의 지원 상태를 나누어 읽어야 한다. [메인넷 발표](https://www.circle.com/pressroom/circle-launches-arc-mainnet-an-economic-operating-system-for-the-internet)

공식 글 연결: [Introducing the ARC whitepaper.](https://www.arc.io/blog/introducing-the-arc-token-whitepaper) (2026-05-11, [공식 원문](https://www.arc.io/blog/introducing-the-arc-token-whitepaper)). 백서 소개는 자산과 앱 및 시장이 공통 기반에서 작동한다는 제품 비전을 설명한다. 백서의 전체 구조와 기능별 제공 조건은 기존 백서 근거에서 확인한다.

공식 글 연결: [Arc Mainnet Is Here: The Economic OS for the Internet Is Now Live](https://www.arc.io/blog/arc-economic-os-internet) (2026-09-16, [공식 원문](https://www.arc.io/blog/arc-economic-os-internet)). 메인넷 출시 글도 프라이버시를 다음 개발 과제로 설명한다. 네트워크 출시와 기밀 기능의 제공을 같은 사건으로 읽지 않는다.

[Token Whitepaper의 Economic OS 설명](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/arc_whitepaper.pdf)은 핵심 인프라(core infrastructure), 프로토콜 서비스(protocol services), 개발 키트(developer kits)와 앱(applications)을 Arc의 구조로 열거한다. CCTP 체인 간 이전, 프로그래머블 지갑, 환전(FX) 인프라와 Circle Mint 및 CPN 연동은 Arc를 더 넓은 금융과 가상자산 생태계에 연결한다. 아래 그림은 이 문장의 네 구성을 옮긴 것이며, 아래에서 위로 쌓는 배치는 내가 정했다. 같은 백서의 Figure 2는 자산과 프로토콜을 별도 층으로 두므로 아래 그림과 구별한다.

한국어:

```text
                 [Economic OS: Circle이 백서에서 제시한 Arc의 목표]
                                     |
          +--------------------------+---------------------------+
          |                                                      |
 백서가 말하는 Arc의 구성                           Arc를 외부와 잇는 플랫폼과 서비스
 +----------------------------------+              +---------------------------------+
 | 앱 (applications)                |              | CCTP 체인 간 이전               |
 | 개발 키트 (developer kits)       |              | 프로그래머블 지갑               |
 | 프로토콜 서비스                  | <----------> | 환전(FX) 인프라                 |
 | 핵심 인프라 (core infrastructure)|              | Circle Mint, CPN 연동           |
 +----------------------------------+              +---------------------------------+
   백서가 내세운 특징: 결정적 결제, 설정 가능한 프라이버시, 스테이블코인 단위의 수수료
```

English:

```text
                 [Economic OS: Arc's goal as stated in Circle's whitepaper]
                                     |
          +--------------------------+---------------------------+
          |                                                      |
 Arc's architecture per whitepaper                Platforms and services linking Arc
 +----------------------------------+              +---------------------------------+
 | Applications                     |              | Crosschain transfers via CCTP   |
 | Developer kits                   |              | Programmable wallets            |
 | Protocol services                | <----------> | FX infrastructure               |
 | Core infrastructure              |              | Circle Mint and CPN integration |
 +----------------------------------+              +---------------------------------+
   Stated features: deterministic settlement, configurable privacy, stablecoin-native fees
```

운영체제(OS)의 비유는 백서가 직접 전개한다. 모바일 OS 이전에도 전화와 문자 및 제조사가 만든 앱은 작동했지만, 기기별로 호환되지 않는 플랫폼에 개발자가 각각 맞춰야 했다. iOS와 Android는 전화기를 대체한 것이 아니라 개발자가 세계적인 공통 플랫폼을 사용하도록 했다. 클라우드도 각 회사가 서버, 통신망과 저장소를 따로 마련하던 중복 작업을 공유 인프라로 바꿨다는 설명이다. 백서는 이와 같은 공통 기반을 금융에 제공하려는 목표를 Economic OS라고 부른다.

[Token Whitepaper의 OS 논지](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/arc_whitepaper.pdf)의 원문은 다음과 같다.

> iOS and Android did not replace the phone.

백서 Figure 2는 이 목표를 아래 다섯 층으로 표현한다. 이 분류와 이름은 백서의 것이며, 표는 그 내용을 옮겼다.

| 백서의 층            | 백서가 제시한 구성                                   |
| -------------------- | ---------------------------------------------------- |
| Applications         | DeFi 프로토콜, 지급, 지갑과 에이전트                 |
| Developer kits       | 수익 상품, 거래, 차입과 대출, bridge 및 에이전트 SDK |
| Protocol services    | 체인 간 이전, 지갑, FX와 지급망                      |
| Assets and protocols | USDC, 스테이블코인, 토큰화 자산과 ARC                |
| Arc core             | 최종성, 스테이블코인 가스, 프라이버시, 검증자와 합의 |

ARC는 이 모든 층을 가로지르는 조정 자산(coordination asset)으로 제안된다. 이와 별도로 백서는 Arc 네트워크를 실행 환경, 스테이블코인을 거래 수단, ARC를 네트워크 보안과 경제 규칙 및 활동 가치 배분을 조정하는 수단으로 설명한다. ARC의 구체적인 경제 설계는 가치와 토큰 설명에서 다룬다.

개발 키트와 앱 프레임워크는 Skills와 CLI를 통해 제공하여 개발자가 기초 인프라를 처음부터 만들지 않고 대출, 거래, 지급과 에이전트 서비스를 배포하도록 한다는 목표다. 백서의 고지에 따라 이러한 구성은 제안된 설계이며, 모든 기능이 현재 제공된다는 뜻은 아니다.

## 2. 구성: Arc 네트워크와 그 위의 자산, 서비스와 참여자는 각각 무엇을 맡는가

Arc를 이해하는 데 필요한 구성요소는 다섯이다. 네트워크는 거래를 실행하고 그 결과를 원장에 기록한다. 자산과 기록은 보유하는 대상과 그 수량이 기록되는 곳이다. 제품과 서비스는 네트워크의 기능을 사용자가 이용하는 업무에 연결한다. 회사와 기관은 사업, 발행과 금융서비스의 계약 주체이고, 사용자와 개발자는 거래의 의도와 앱의 업무 규칙을 정한다. 이 절은 각 구성요소가 무엇을 맡는지 구별하고, 그것을 운영하거나 통제하는 주체도 해당 구성요소 안에서 함께 설명한다.

### 2.1 네트워크: 거래를 처리하는 규칙과 그 처리를 맡는 주체는 무엇인가

네트워크는 거래를 실행하고 기록하는 규칙과 원장(2.1.1), 그리고 그 규칙에 따라 거래를 전달하고 검증하며 합의하는 노드와 검증자(2.1.2)로 나누어 본다.

#### 2.1.1 실행 규칙과 원장: Arc는 거래를 어떤 규칙으로 실행하고 그 결과를 어디에 기록하는가

Arc에서 Malachite는 합의를, Reth를 바탕으로 한 실행 구성은 계약 실행과 상태 변경을 담당한다. 합의는 어떤 블록을 받아들일지 참여자들이 결정하는 과정이고, 실행은 거래와 계약이 기존 상태를 어떻게 바꾸는지 계산하는 과정이다. 계정 잔액, 계약 저장값과 거래 결과가 같은 규칙에 따라 확인돼야 한다. 공개 문서에서 설명하는 구조이며, 이 리서치에서 노드를 직접 실행해 측정한 결과는 아니다. [시스템 개요](https://docs.arc.io/arc/concepts/system-overview.md), [합의 설명](https://docs.arc.io/arc/concepts/consensus-layer.md)

공식 글 연결: [Arc’s Bespoke Consensus Layer Built Using Malachite](https://www.arc.io/blog/arcs-deterministic-finality-the-bespoke-consensus-layer-built-using-malachite) (2025-10-14, [공식 원문](https://www.arc.io/blog/arcs-deterministic-finality-the-bespoke-consensus-layer-built-using-malachite)). 합의와 실행을 별도 프로세스로 나누고 Engine API로 연결한다는 공식 설계 설명이다. 이 연결은 노드를 직접 실행한 검증 결과를 뜻하지 않는다.

원장에 기록되는 상태를 이해하려면 앱 화면의 숫자와 네트워크가 관리하는 상태를 구별해야 한다. 앱은 사용자가 보기 쉬운 잔액이나 거래 내역을 표시하지만, 체인에서는 계정의 잔액, 계약의 저장값과 거래 결과가 정해진 규칙에 따라 관리된다. 앱이 전송 버튼을 눌렀다는 기록을 남겼다고 그 자체로 수취인의 체인 잔액이 바뀌는 것은 아니다. 상태를 바꾸려면 거래가 처리돼야 하고, 앱은 그 결과를 다시 읽어 화면에 반영해야 한다.

이렇게 같은 실행 규칙과 하나의 원장을 쓰면 서로 다른 앱이 같은 체인 상태를 기준으로 기능을 연결할 수 있다. 다만 같은 네트워크를 이용한다는 사실은 앱들이 같은 업무 규칙이나 법률상 책임을 가진다는 뜻이 아니다. 네트워크는 모든 거래에 같은 처리 규칙을 적용하고, 개별 계약과 서비스는 그 위에서 어떤 업무를 수행할지 정한다. 이 구별은 2.3(제품과 서비스)에서 제품과 앱의 관계를 이해하는 기준이 된다.

한국어:

```text
 같은 네트워크를 쓰는 두 앱: 공유하는 것과 공유하지 않는 것

 [앱 A]                                 [앱 B]
  화면: 원장 상태를 읽어 보여 준다       화면: 원장 상태를 읽어 보여 준다
  업무 규칙과 법률상 책임: A의 것        업무 규칙과 법률상 책임: B의 것
    |              ^                       |              ^
    | 거래 제출    | 결과 조회             | 거래 제출    | 결과 조회
    v              |                       v              |
 ======================== 여기부터 두 앱이 공유한다 ========================
  Arc 네트워크: 모든 거래에 같은 처리 규칙을 적용한다
    합의 (Malachite)   어떤 블록을 받아들일지 정한다
    실행 (Reth 기반)   거래와 계약이 상태를 어떻게 바꾸는지 계산한다
                       |
                       v
  [하나의 원장 상태]   계정 잔액 | 계약 저장값 | 거래 결과
```

English:

```text
 Two apps on the same network: what they share and what they do not

 [App A]                                    [App B]
  screen: reads and shows the ledger state   screen: reads and shows the ledger state
  business rules and legal liability: A's    business rules and legal liability: B's
    |              ^                           |              ^
    | submit tx    | read results              | submit tx    | read results
    v              |                           v              |
 ========================== shared by both apps from here ==========================
  Arc network: the same processing rules for every transaction
    consensus (Malachite)    decides which block is accepted
    execution (Reth-based)   computes how transactions and contracts change state
                            |
                            v
  [One ledger state]   account balances | contract storage | transaction results
```

그림은 위에서 아래로 읽는다. 위의 두 앱은 각자의 화면, 업무 규칙과 법률상 책임을 가진다. 두 앱은 거래를 네트워크에 제출하고, 그 결과를 원장 상태에서 읽어 화면에 보여 준다. 이중선(=====) 아래는 두 앱이 공유하는 부분이다. 네트워크는 모든 거래에 같은 규칙을 적용한다. 합의(Malachite)는 어떤 블록을 받아들일지 정하고, 실행(Reth 기반)은 그 블록의 거래와 계약이 계정 잔액, 계약 저장값과 거래 결과를 어떻게 바꾸는지 계산한다. 그 결과가 하나의 원장 상태에 남으므로, 한 앱이 만든 결과를 다른 앱도 같은 기준으로 확인할 수 있다. 반면 화면에 보이는 숫자, 어떤 거래를 허용할지와 누가 책임질지는 공유되지 않는다.

[System overview의 계층 분리](https://docs.arc.io/arc/concepts/system-overview.md)의 원문은 다음과 같다.

> Arc separates consensus from execution

#### 2.1.2 노드와 검증자: 거래 처리, 상태 검증과 합의는 누가 맡는가

RPC 제공자와 노드는 조회 및 거래 제출을 처리한다. 풀 노드는 블록과 거래의 상태를 검증하고, 허가된 검증자는 합의에서 제안 및 투표를 수행한다. 요청 접수, 독립적인 검증과 합의 참여는 같은 역할이 아니다.

한국어:

```text
 일반적인 블록체인의 역할 구분 (참여 조건은 체인마다 다르다)

 [앱] --조회, 거래 제출--> [RPC 제공자] --> [풀 노드]
                                             - 블록과 검증자 서명 확인
                                             - 거래 재실행, 상태 보유
                                                   ^
                                                   | 확정된 블록
                                                   |
                                             [검증자 집합]
                                             - 블록 제안과 투표 (합의)

 RPC 응답 제공, 독립적인 상태 확인, 블록 합의는 서로 다른 역할이다.
```

English:

```text
 Typical blockchain roles (participation rules differ by chain)

 [App] --query, submit tx--> [RPC provider] --> [Full node]
                                                 - checks blocks and validator signatures
                                                 - re-executes transactions, keeps state
                                                       ^
                                                       | finalized blocks
                                                       |
                                                 [Validator set]
                                                 - proposes and votes on blocks (consensus)

 Serving RPC, independently checking state and agreeing on blocks are distinct roles.
```

그림은 특정 체인이 아니라 블록체인 일반의 역할 구분이다. 앱이 조회와 제출을 보내는 접점인 RPC 제공자, 블록과 상태를 직접 다시 확인하는 풀 노드, 블록을 제안하고 투표하는 검증자는 서로 다른 역할이다. 누가 검증자가 될 수 있는지는 체인마다 다르며, 이 리서치는 다른 체인의 검증자 선정 방식을 조사하지 않았다.

[공식 노드 문서](https://docs.arc.io/arc/concepts/running-a-node.md)는 거래 재실행과 독립 상태 검증을 명시한다. 원본 중 풀 노드가 서명만 확인한다고 축약한 설명은 보완했다. Arc의 일반 노드 실행과 허가된 검증자의 합의 참여는 다른 접근 조건이다. 창립 검증자 명단은 단계별 참여 계획을 포함한 발표이며 기관별 현재 실제 투표 여부를 이 원고에서 확인한 것은 아니다.

공식 글 연결: [Run Your Own Arc Node and Join the Arc Bug Bounty Program](https://www.arc.io/blog/open-sourcing-arc-run-your-own-arc-node-and-bug-bounty-program) (2026-04-09, [공식 원문](https://www.arc.io/blog/open-sourcing-arc-run-your-own-arc-node-and-bug-bounty-program)). 공개 노드는 검증자가 아니며 합의에 참여하지 않는다는 공식 고지다. 이 글은 테스트넷 시기의 설명이므로 기관별 현재 메인넷 투표 여부를 입증하지 않는다.

한국어:

```text
 Arc의 경우 (공식 노드 문서 기준)

 누구나 허가 없이 운영                       허가된 검증자만 참여
 [Arc 풀 노드]                               [허가된 검증자 집합]
  - 검증자 서명 확인                          - 블록 제안과 투표
  - 거래를 로컬에서 재실행                    - 창립 검증자 명단은 단계별 참여 계획
  - 자체 상태 유지, 로컬 JSON-RPC 제공          (기관별 현재 투표 여부는 미확인)
          ^                                             |
          +--------------- 확정된 블록 -----------------+

 풀 노드를 운영해도 합의 투표 권한은 생기지 않는다.
```

English:

```text
 The Arc case (per the official node docs)

 Anyone, without permission                  Permissioned validators only
 [Arc full node]                             [Permissioned validator set]
  - checks validator signatures               - proposes and votes on blocks
  - re-executes transactions locally          - founding list is a phased rollout plan
  - keeps own state, local JSON-RPC             (current voting per institution unverified)
          ^                                             |
          +--------------- finalized blocks ------------+

 Running a full node does not grant consensus voting rights.
```

Arc에서는 두 역할의 참여 조건이 뚜렷이 나뉜다. [노드 문서](https://docs.arc.io/arc/concepts/running-a-node.md)은 "Anyone can run an Arc node without permission."라고 적고, 같은 문서는 Arc 노드가 검증자가 아닌 풀 노드이며 블록 제안과 투표는 허가된 검증자만 한다고 설명한다. 왼쪽의 풀 노드는 누구나 운영해 블록을 직접 확인할 수 있고, 오른쪽의 합의 참여는 허가가 필요하다.

검증자는 합의에 참여해 제안과 투표를 처리한다. 풀 노드를 운영한다고 이 투표 권한까지 생기는 것은 아니다. 따라서 개발자는 노드를 통해 무엇을 직접 확인할지와 합의에 누가 참여할지를 별도로 이해해야 한다. 노드가 거래와 상태를 검증해도 발행자의 준비금이나 금융기관의 고객 지급까지 체인 밖 자료 없이 검증하는 것은 아니다. 그러한 자산 및 금융서비스 처리를 담당하는 주체는 2.4.2(발행자와 금융기관)에서 설명한다.

한국어:

```text
 풀 노드로 검증할 수 있는 것          |  체인 밖 자료가 필요한 것
                                      |
  - 블록의 검증자 서명                 |   - 발행자의 준비금
  - 거래의 실행 결과                   |   - 금융기관의 고객 지급
  - 계정 잔액과 계약 저장값            |   - 은행 계좌의 입금
                                      |
        체인 기록                      |   체인 밖 업무 (2.4.2 발행자와 금융기관)
```

English:

```text
 What a full node can verify          |  What needs offchain evidence
                                      |
  - validator signatures on blocks    |   - the issuer's reserves
  - transaction execution results     |   - a financial institution's payout
  - balances and contract storage     |   - deposits into bank accounts
                                      |
        onchain records               |   offchain work (2.4.2 issuers and institutions)
```

왼쪽은 체인에 기록된 내용이라 풀 노드가 직접 확인할 수 있고, 오른쪽은 체인 밖의 장부와 업무라 별도 자료가 필요하다. 오른쪽 업무를 맡는 주체가 2.4.2의 발행자와 금융기관이다.

### 2.2 자산과 기록: 무엇을 보유하며, 그 권리와 수량은 어디에 어떻게 기록되는가

네트워크가 거래를 처리하는 규칙과 주체를 보았으므로 이제 그 처리의 대상인 자산과 잔액을 살펴본다. 같은 토큰이라는 형식을 사용해도 지급 자산, 투자 상품, 네트워크 참여 수단과 회사 지분은 서로 다른 권리를 나타낸다.

보유 대상의 권리, 잔액이 귀속되는 계정, 수량의 표현 방식과 기록의 위치를 차례로 구별한다. 같은 자산의 여러 표현과 서로 다른 장부의 잔액을 구분하는 것이 이 절의 중심 질문이다.

**자산과 기록의 구별: 한 행은 하나의 개념과 확인 질문이다**

| 개념        | 답해야 하는 질문                        | 구별해야 하는 관계                                               |
| ----------- | --------------------------------------- | ---------------------------------------------------------------- |
| 자산        | 무엇을 보유하며 어떤 권리가 따르는가?   | 토큰 형식이 같아도 권리는 다를 수 있습니다.                      |
| 계정과 주소 | 잔액과 계약 상태는 어디에 귀속되는가?   | 주소는 식별자이고, 지갑은 관리와 조회 및 승인을 위한 도구입니다. |
| 잔액        | 해당 기록에서 얼마나 보유하는가?        | 수량만으로 상환 자격이나 투자 권리를 설명할 수 없습니다.         |
| 인터페이스  | 그 수량을 어떻게 조회하고 처리하는가?   | 다른 인터페이스가 같은 기초 잔액을 가리킬 수 있습니다.           |
| 기록 위치   | 어느 체인이나 서비스 장부에 기록되는가? | 같은 주소나 자산 이름만으로 별도 장부가 합쳐지지는 않습니다.     |

#### 2.2.1 자산의 유형: 지급 자산, 투자 상품, 네트워크 토큰과 회사 주식은 어떻게 다른가

자산은 경제적으로 보유하는 대상이고, 토큰은 그 대상을 블록체인에서 표현하고 처리하는 형식이다. 잔액은 특정 상태에서 그 단위를 얼마나 보유하는지 나타낸다. USDC는 지급에 사용하는 자산이면서 토큰으로 표현된다. 토큰 자체와 그 토큰의 보유 수량은 구별해야 한다.

다음 그림은 원본의 자산별 도식과 펀드 및 권리 설명을 연결해 내가 재구성했다. 화살표는 이름이 가리키는 경제적 대상과 기능을 뜻한다. 모든 상품의 법률상 권리를 확정한 그림은 아니다.

한국어:

```text
[USDC / EURC] --> [달러 / 유로 기준 지급 자산과 상환 조건]
[USYC]        --> [펀드 지분과 투자 자격]
[cirBTC]      --> [BTC 연계 토큰: 담보와 상환 조건은 확인 대상]
[ARC]         --> [네트워크 참여 및 경제 기능의 설계]
[CRCL]        --> [Circle 상장회사의 주식]
```

English:

```text
[USDC / EURC] --> [USD / EUR payment assets and redemption conditions]
[USYC]        --> [Fund shares and investor eligibility]
[cirBTC]      --> [BTC-linked token: collateral and redemption need checking]
[ARC]         --> [Design for network participation and economic functions]
[CRCL]        --> [Shares in the listed Circle company]
```

USDC의 고정 지급 단위와 USYC의 펀드 지분은 다르다. USYC 문서는 Hashnote International Short Duration Yield Fund의 온체인 표현이며, 펀드가 주로 미국 국채를 담보로 한 역환매조건부거래(reverse repo)에 투자한다고 설명한다. 투자자가 얻는 펀드 지분의 권리와 지급용 스테이블코인의 상환 조건을 같게 설명하면 안 된다. USYC는 미국인(U.S. Persons)에 해당하지 않는 법인을 대상으로 하며 추가 자격 제한이 있다. 테스트넷에서 비슷한 토큰을 사용해 봤다는 사실은 실제 펀드 투자 자격을 얻었다는 뜻이 아니다. [USYC 상품 문서](https://developers.circle.com/tokenized/usyc/overview.md)

비EEA USDC 약관에서 발행자에게 직접 상환하려면 자격을 갖추고 정상 상태의 Circle Mint 계정이 있어야 한다. 주소 사이의 USDC 이전은 자격을 갖추고 계정을 등록한다는 조건 아래 직접 상환 권리와 연결된다. 같은 약관은 준비금에서 발생하는 이자를 USDC 보유자의 수익으로 보장하지 않으며, 제3자 거래 가격이 항상 달러와 같다고 보장하지도 않는다. EEA에는 별도 문서가 적용된다. 여기서는 해당 약관의 적용 범위를 설명하며 모든 지역의 직접 상환 절차를 확정하지 않는다. [USDC 약관의 적용 범위, 상환 및 위험 조항](https://www.circle.com/legal/usdc-terms)

ARC는 현재 USDC 가스와 다른 대상이다. 공식 메인넷 발표는 초기 민트를 기술적 단계로 설명하면서 공개 출시를 약속한 것은 아니라고 적는다. 백서 안내도 미출시 상태와 기능 변경 가능성을 명시한다. Token Whitepaper는 ARC가 Circle이나 다른 주체에 대한 지분, 채무, 배당권, 수익 배분권, 청산권, 소유권 또는 그 밖의 청구권을 나타내지 않는다고 명시한다. 이 리서치에서는 민트 거래와 공개 이전 기능을 직접 조회하지 않았다. [출시 발표](https://www.circle.com/pressroom/circle-launches-arc-mainnet-an-economic-operating-system-for-the-internet), [ARC 안내의 권리 고지](https://www.arc.io/arc-token-whitepaper)

공식 글 연결: [Introducing the ARC whitepaper.](https://www.arc.io/blog/introducing-the-arc-token-whitepaper) (2026-05-11, [공식 원문](https://www.arc.io/blog/introducing-the-arc-token-whitepaper)). 백서 소개의 당시 고지는 ARC 미출시와 기능 변경 가능성을 명시한다. 이후의 초기 민트 발표와 같은 시점의 상태로 합치지 않는다.

공식 Borrow 문서는 cirBTC를 담보로 제공하여 USDC를 빌리고 상환 후 담보를 회수하는 용례를 설명한다. cirBTC의 실제 BTC 보관과 발행 및 상환 구조는 이 기능 설명만으로 확인되지 않는다. 상품 계약과 보관 및 상환의 세부를 이번 공통 개념에서 검증한 결과로 쓰지 않는다. 자산의 네트워크 배포, 직접 발행 및 상환 자격과 투자 자격은 각각 다른 질문이다.

자산의 이름을 이해했다면 보유, 사용과 상환을 나누어 질문할 수 있다. 주소에 토큰 잔액이 있다는 것은 체인에서 그 수량을 확인할 수 있다는 뜻이다. 그 자산을 어떤 계약에 사용할 수 있는지, 발행자에게 직접 상환할 수 있는지, 투자 상품의 권리를 행사할 수 있는지는 별도의 지원 조건과 자격에 따른다. 앞의 USDC와 USYC 사례가 이 차이를 보여 준다.

따라서 자산 비교의 기준은 토큰이라는 형식만이 아니다. 지급에 사용할 단위를 보유하는지, 투자 상품의 지분을 보유하는지, 네트워크 기능에 관한 설계상 대상인지, 회사 주식인지부터 구별해야 한다. 이 구별을 유지해야 뒤에서 잔액을 설명할 때에도 수량의 존재를 수익이나 상환 권리의 보장으로 바꾸지 않게 된다.

[Token Whitepaper의 권리 고지](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/arc_whitepaper.pdf)의 원문은 다음과 같다.

> ARC does not represent any equity, debt, dividend right, revenue share, liquidation right, ownership interest, or other claim on Circle or any other person,

Earn의 vault share도 USYC의 펀드 지분과 구별한다. [Earn 문서](https://docs.arc.io/app-kit/earn.md)에서 사용자는 USDC 또는 EURC를 대출 프로토콜의 vault에 예치하고 지분을 받는다. 기반 프로토콜이 수익을 만들면 지분의 자산 환산 가치가 늘어나고, 나갈 때 지분을 상환하여 자산을 회수한다는 설명이다. USDC 자체의 보유 이자나 USYC 펀드의 권리와 같은 대상이 아니다.

#### 2.2.2 계정과 주소: 잔액과 계약 상태는 어디에 귀속되는가

계정은 잔액과 계약 상태가 귀속되는 대상이고, 주소는 그 계정을 식별하는 값이다. 지갑은 키를 관리하고 거래를 승인하거나 잔액을 조회하는 도구 및 서비스다. 지갑 화면에 숫자가 보인다는 것만으로 자산의 위치와 권리가 모두 설명되지는 않는다. 개인이 키를 통제하는 온체인 계정인지, 서비스가 관리하는 계정인지, 거래소 내부 장부인지 확인해야 한다.

이 구별은 다음에 설명할 잔액 조회의 기준이 된다. 앱이 수량을 읽을 때에는 어떤 계정의 어떤 기록을 읽는지 알아야 하며, 조회 도구인 지갑과 기록 대상인 계정을 같은 것으로 취급하면 안 된다.

**계정과 지갑의 관계: 기록 대상과 조회 및 승인 경로**

한국어:

```text
[주소: 계정을 식별하는 값]
             |
             v
[특정 체인의 계정과 상태]
  - 잔액
  - 계약 저장값
             ^
             | 조회 / 거래 결과 반영
             |
        [지갑과 앱]
         /       \
        v         v
  [잔액 조회]  [승인과 서명]
                   |
                   v
              [거래 제출]

승인 주체는 지갑 유형에 따라 다르다.
수탁 서비스의 내부 장부는 위 온체인 계정과 구별한다.
```

English:

```text
[Address: identifies an account]
                |
                v
[Account and state on a specific chain]
  - Balance
  - Contract storage
                ^
                | queries / transaction results reflected
                |
         [Wallet and app]
          /            \
         v              v
 [Balance query]  [Authorization and signing]
                         |
                         v
                [Transaction submission]

The authorizing party depends on the wallet type.
A custodial service's internal ledger is distinct from this onchain account.
```

주소는 자산을 담는 지갑 프로그램의 이름이 아니라 체인에서 계정을 식별하는 값이다. 같은 계정의 잔액을 여러 지갑 화면이나 조회 도구에서 읽을 수 있어도, 화면을 하나 더 열었다고 자산이 하나 더 생기지는 않는다. 반대로 지갑 앱에 접근할 수 있다는 사실만으로 그 계정의 거래를 승인할 권한이 있다는 뜻도 아니다. 조회와 상태 변경 권한을 따로 보아야 한다.

앞 도식에서 지갑과 앱의 연결은 조회하거나 거래를 요청하는 경로다. 계정의 상태는 네트워크가 거래를 처리한 결과로 바뀌며, 지갑 화면이 직접 수정하는 것이 아니다. 승인 주체와 서명 방법은 뒤의 참여자 절에서 설명하고, 체인이나 수탁 장부를 바꾸어 조회하는 경우는 기록의 위치 절에서 구별한다.

**다른 체인에서도 같은 관계인가**

주소가 계정을 식별하고, 계정에 잔액과 계약 저장값이 귀속되며, 지갑이 조회하고 서명한다는 위 구조는 Arc만의 것이 아니다. Arc는 EVM의 계정 구조를 따르므로 Ethereum과 다른 EVM 체인에서도 같은 관계가 성립한다. 달라지는 것은 어떤 자산이 계정의 기본 잔액으로 기록되는가다. [EVM 차이 문서](https://docs.arc.io/arc/references/evm-differences.md)은 Arc에서는 계약이 가진 USDC가 "its native balance, held in the account"인 반면, 다른 체인에서는 계약의 ERC-20 USDC 잔액이 "lives in the token contract"라고 비교한다. [네이티브 모델 문서](https://docs.arc.io/arc/concepts/stablecoin-native-model.md)도 대부분의 EVM 체인에서는 ETH 같은 변동성 토큰이 기본 자산이라고 적는다.

공식 글 연결: [USDC for Every Action on Arc: What EVM Developers Need to Know](https://www.arc.io/blog/usdc-for-every-action-how-arc-simplifies-building-onchain) (2026-08-28, [공식 원문](https://www.arc.io/blog/usdc-for-every-action-how-arc-simplifies-building-onchain)). USDC의 값이 네이티브 계정 모델에 있고 ERC-20은 같은 잔액의 인터페이스라는 설명이다. 다른 체인의 계정 모델 비교는 기존 기술 문서의 근거를 유지한다.

**Arc와 다른 EVM 체인의 계정 비교: 한 행은 비교하는 기준 하나다**

| 기준                             | Arc                                                       | Ethereum 등 다른 EVM 체인  |
| -------------------------------- | --------------------------------------------------------- | -------------------------- |
| 주소, 계정과 지갑의 관계         | 위 그림과 같다.                                           | 위 그림과 같다.            |
| 계정의 기본 잔액이 나타내는 자산 | USDC                                                      | ETH 등 각 체인의 기본 토큰 |
| 가스비를 내는 자산               | USDC                                                      | 각 체인의 기본 토큰        |
| USDC 잔액이 기록되는 곳          | 계정의 기본 잔액. ERC-20 인터페이스도 같은 잔액을 읽는다. | USDC 토큰 계약의 저장값    |

이 차이 때문에 같은 지갑 화면에 USDC 잔액이 보여도, Arc에서는 계정 자체의 잔액을 읽고 다른 EVM 체인에서는 토큰 계약에 주소별로 기록된 값을 읽는다. 다음 절은 Arc에서 이 두 방식이 하나의 USDC 잔액에 함께 적용될 때 생기는 결과를 설명한다. Bitcoin이나 Solana처럼 EVM이 아닌 체인은 계정과 잔액을 기록하는 방식 자체가 다르지만, 이 절은 EVM 체인과의 차이에 집중하므로 여기서 비교하지 않는다.

#### 2.2.3 잔액과 인터페이스: Arc는 USDC 잔액 하나를 네이티브와 ERC-20 두 방식으로 어떻게 다루는가

앞 절의 비교처럼 다른 EVM 체인에서는 기본 토큰과 USDC가 서로 다른 방식으로 기록된다. Arc에서는 USDC 하나가 두 방식으로 모두 다뤄진다. 이 절은 먼저 두 방식을 정의한 뒤, Arc에서 두 방식이 같은 잔액을 공유할 때 생기는 결과를 설명한다.

**두 방식의 정의**

네이티브 자산은 체인이 계정마다 직접 기록하는 기본 잔액이다. 거래의 가스비가 이 잔액에서 차감되고, 거래와 함께 값을 보내는 `msg.value`도 이 잔액을 옮긴다. 별도 계약을 거치지 않고 체인의 실행 규칙이 직접 처리한다.

ERC-20은 토큰 계약이 따르는 공통 함수 표준이다. 토큰 계약은 주소별 잔액을 자기 저장값에 기록하고, 앱은 `balanceOf`로 잔액을 조회하고 `transfer`로 이전한다. 다른 계약이 대신 쓸 수 있는 한도는 `approve`로 승인하고 `allowance`로 조회한다. 함수 이름과 동작이 같으므로 지갑과 계약은 서로 다른 토큰을 같은 방식으로 다룰 수 있다. 이 설명은 Arc 문서가 다루는 함수의 범위로 한정했으며, 표준 원문(EIP-20)은 이번 리서치에서 보존하지 않았다.

다른 EVM 체인에서는 두 방식이 서로 다른 자산에 쓰인다. ETH 같은 기본 토큰은 네이티브 방식으로 기록되고, USDC는 ERC-20 토큰 계약에 기록된다. 기본 토큰을 ERC-20 함수로 다루려면 WETH 같은 포장 계약에 맡기고 별도 토큰을 받아야 한다. [네이티브 모델 문서](https://docs.arc.io/arc/concepts/stablecoin-native-model.md)는 Arc의 USDC는 처음부터 ERC-20 인터페이스를 갖추고 있어 이 포장 단계가 없고, 포장 계약도 배포하거나 지원하지 않는다고 설명한다.

Arc에서는 이 두 인터페이스가 같은 기초 잔액을 가리킨다. 네이티브 인터페이스는 가스와 `msg.value`를 통한 값 전송에 사용하고, ERC-20은 `transfer`, `approve`, `allowance`처럼 앱이 익숙하게 사용하는 호출에 사용한다. 별도 포장 토큰을 만들어 잔액을 옮기는 과정이 아니다. [Two interfaces, one balance](https://docs.arc.io/arc/concepts/stablecoin-native-model.md)

공식 글 연결: [Building with USDC on Arc: Two Interfaces for One Token](https://www.arc.io/blog/building-with-usdc-on-arc-one-token-two-interfaces) (2025-11-17, [공식 원문](https://www.arc.io/blog/building-with-usdc-on-arc-one-token-two-interfaces)). 두 인터페이스가 같은 기초 자산을 가리킨다는 개발자 안내다. 별도 잔액처럼 합산하지 않는 이유를 설명하며, 승인과 지급 완료의 구별은 기존 기술 문서에서 확인한다.

다음 그림의 분기는 같은 기초 잔액을 다루는 방법이다. 두 곳에 독립적으로 돈이 생긴다는 뜻이 아니다.

한국어:

```text
                  [Arc USDC의 기초 잔액]
                    /              \
                   v                v
       [네이티브: 소수 18자리]    [ERC-20: 소수 6자리]
       [가스 / msg.value]        [transfer / approve / allowance]
                    \              /
                     v            v
                  [같은 잔액에 반영]
```

English:

```text
                   [Underlying Arc USDC balance]
                     /                  \
                    v                    v
          [Native: 18 decimals]      [ERC-20: 6 decimals]
          [Gas / msg.value]         [transfer / approve / allowance]
                     \                  /
                      v                v
                  [Changes affect the same balance]
```

가스비를 지급하면 ERC-20으로 조회하는 잔액에도 그 변화가 반영된다. 반대로 ERC-20으로 자산을 전송하면 네이티브 가스 지급에 사용할 수 있는 잔액도 달라진다. 따라서 전액을 지급 자산으로 예약하면서 가스 비용을 같은 잔액에서 낼 수 있다고 생각하면 자금이 부족할 수 있다.

지급 설계에서는 지급할 수량과 실행에 필요한 가스 비용을 같은 기초 잔액 안에서 함께 고려해야 한다. 또한 계약에 사용 한도를 부여한 상태와 실제 자산을 이전한 상태를 별도로 관리해야 한다. 승인 기록만 보고 지급 완료로 표시하거나, 네이티브와 ERC-20 조회값을 서로 다른 자산으로 더하면 업무 기록이 체인의 상태와 어긋날 수 있다. 이는 앞의 잔액 및 인터페이스 사양에서 도출한 설계상의 주의점이며 특정 앱을 시험한 결과는 아니다.

[Stablecoin-native model의 인터페이스 정의](https://docs.arc.io/arc/concepts/stablecoin-native-model.md)의 원문은 다음과 같다.

> Two interfaces, one balance

#### 2.2.4 기록의 위치: 체인별 상태와 수탁 서비스의 장부는 어떻게 다른가

Arc 내부의 두 인터페이스가 같은 잔액을 본다는 설명은 서로 다른 체인이나 수탁 서비스까지 적용되지 않는다. 이 경계를 구별해야 지갑의 표시 금액과 실제로 지급할 수 있는 자산을 혼동하지 않는다.

한 개인이 같은 키에서 얻은 주소를 여러 EVM 체인에 사용할 수 있다. 하지만 같은 주소 문자열이 서로 다른 체인의 계정 상태를 하나로 합치지는 않는다. 잔액, 계약 배포, 논스(nonce)와 가스 조건은 체인마다 다를 수 있다. 네트워크를 바꾸어 지갑 화면을 조회하면 다른 상태를 읽는 것이다.

아래 그림의 위쪽 연결은 동일한 식별자를 여러 체인에서 사용하는 관계이고, 아래쪽 화살표는 별도 전송 절차다. 같은 주소를 쓴다는 이유로 아래 전송이 이미 수행됐다고 볼 수 없다.

한국어:

```text
                     [같은 주소 문자열]
                       /           \
                      v             v
              [Ethereum 계정]      [Arc 계정]
              [별도 잔액과 상태]   [별도 잔액과 상태]

     [출발 체인 USDC] -- 체인 간 전송 절차 --> [목적지 체인 USDC]
```

English:

```text
                     [Same address string]
                       /              \
                      v                v
             [Ethereum account]     [Arc account]
             [Separate state]       [Separate state]

        [Source-chain USDC] -- crosschain transfer --> [Destination-chain USDC]
```

이 그림은 AI 답변의 잔액 및 인터페이스 설명을 바탕으로 내가 구성했다. Arc 내부 인터페이스의 공유 잔액과 체인 간 자산 이동을 구별하기 위한 그림이다.

Gateway는 이 차이를 이용자가 다루기 쉽게 하는 별도 기능을 제공한다. 지원 출발 체인의 Gateway Wallet 계약에 USDC를 예치해 통합 잔액을 성립시키고, 승인과 서비스 절차에 따라 목적지 체인에서 사용할 수 있도록 한다. 지갑의 모든 체인 잔액이 예치 없이 자동으로 합쳐지는 것은 아니다. Gateway의 빠른 목적지 이용 설명은 잔액이 먼저 성립했다는 조건을 가진다. 문서는 비수탁 구조와 7일의 신뢰 없는 출금(trustless withdrawal) 경로를 설명하지만, 그 기간을 모든 정상 전송의 처리 시간으로 읽으면 안 된다. [Gateway 개요의 조건](https://developers.circle.com/gateway.md)

거래소의 USDC 잔액은 또 다른 관계다. 거래소 내부 장부에 표시한 고객 잔액과 특정 개인 주소의 온체인 잔액은 같다고 보장되지 않는다. 사용자는 서비스의 출금 절차를 통해 자신의 주소로 받을 수 있는지 확인해야 한다. 개발자가 승인하는 Circle Wallets의 온체인 계정도 거래소 내부 장부와 자동으로 같은 유형이 되지는 않는다. 서명 통제와 계약상 청구 관계를 각각 읽어야 한다.

정리하면 잔액을 확인할 때에는 자산 이름과 주소에 더해 어떤 체인 또는 서비스 장부를 읽었는지 알아야 한다. 같은 주소의 다른 체인 잔액은 별도 상태이고, 같은 체인의 다른 인터페이스가 같은 기초 잔액을 읽는 경우는 별도 자산이 아니다. 수탁 서비스의 고객 잔액은 다시 서비스의 장부와 출금 조건을 함께 보아야 한다. 이 구별을 한 뒤에야 그 기록을 누가 통제하고 어떤 승인으로 바꾸는지 질문할 수 있다.

[Unified Balance 문서](https://docs.arc.io/app-kit/unified-balance.md)는 이 SDK 기능이 Gateway 위에 구축되어 여러 체인의 예치와 사용을 처리한다고 설명한다. 통합 잔액은 출발 체인의 자금을 먼저 예치하여 성립한다. SDK가 여러 체인의 기존 지갑 잔액을 예치 없이 하나의 온체인 잔액으로 합치는 것은 아니다.

공식 글 연결: [Unified Balance Kit: Rethinking Multichain Architecture](https://www.arc.io/blog/unified-balance-kit-rethinking-payment-and-treasury-app-architectures) (2026-06-10, [공식 원문](https://www.arc.io/blog/unified-balance-kit-rethinking-payment-and-treasury-app-architectures)). Unified Balance 소개는 예치와 가용 USDC 잔액을 연결해 설명한다. 출금 대기 기간과 자산 통제 조건은 Gateway의 상세 문서에서 확인한다.

### 2.3 제품과 서비스: Circle의 제품은 어떤 일을 처리하고, 승인 권한은 누가 통제하는가

제품과 서비스는 각 제품이 처리하는 일(2.3.1)과, 그중 자산 이전을 승인하는 권한을 누가 통제하는지(2.3.2)로 나누어 본다.

#### 2.3.1 제품과 앱: 제공되는 기능은 사용자 업무에 어떻게 연결되는가

지갑, 지급 API와 개발 도구를 사용한 앱이 모두 Arc에서만 작동하는 것은 아니다. 한 앱이 Circle Wallets로 서명하고, 다른 체인에서 USDC를 전송하며, 은행의 지급 경로를 사용할 수도 있다. 따라서 제품 이름만으로 실행 체인이나 계약 상대방을 정할 수 없다. Arc에서 실행하는 제3자 앱을 사용했다는 사실도 Circle이 만든 앱이라는 증거가 아니다.

네트워크와 자산을 구별했다면, 다음으로 각 제품이 어떤 일을 처리하는지 구별할 수 있다. 제품 이름을 나열하는 대신 거래 실행, 서명, 자산의 발행과 이동, 결제 및 앱 개발의 역할로 연결한다.

공식 글 연결: [Build and scale faster with Arc App Kits](https://www.arc.io/blog/app-kits-a-suite-of-sdks-to-build-onchain) (2026-04-10, [공식 원문](https://www.arc.io/blog/app-kits-a-suite-of-sdks-to-build-onchain)). 초기 App Kits 글은 Bridge, Swap과 Send를 소개한다. 이후 추가된 기능까지 당시의 지원 목록으로 설명하지 않는다.

아래 표의 한 행은 처리하는 일과 그에 연결되는 제품 하나다. 역할 구분은 내가 여러 답변과 공식 상품 문서를 함께 읽어 구성했다. 실제 지원 체인, 계정 승인과 요금은 이용하려는 경로에서 다시 확인해야 한다.

마지막 열은 보존한 공식 자료의 법적 고지나 공시에서 제공 또는 운영 법인을 확인한 결과다. "고지 없음"은 해당 제품의 보존 문서에서 제공 법인을 밝힌 문장을 찾지 못했다는 뜻이며 법인이 없다는 뜻이 아니다. 법인 사이의 소유 관계는 2.4.1(회사와 법인)의 법인 관계도에서 구별한다.

| 처리하는 일                                  | 제품 또는 구성                      | 무엇을 확인해야 하는가                                                                  | 제공 또는 운영 법인 (수집 자료의 고지)                                                                                                           |
| -------------------------------------------- | ----------------------------------- | --------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| 거래와 계약 실행, 상태 및 블록 확정          | Arc                                 | 네트워크, 가스 자산과 계약의 규칙을 확인한다.                                           | 메인넷: Arc Network Services LLC가 출시, 허가된 검증자 집합이 운영. 테스트넷: Circle Technology Services, LLC                                    |
| 서명 승인과 거래 제출                        | Circle Wallets                      | 지갑 유형, 승인 주체, 키 관리와 제출 후 상태를 확인한다.                                | Circle Technology Services, LLC                                                                                                                  |
| 법정화폐와 스테이블코인의 발행 및 상환       | Circle Mint                         | 계정 자격, 지역과 상품별 계약을 확인한다.                                               | 비EEA USDC: Circle Internet Financial, LLC. EEA: Circle Internet Financial Europe SAS. Bermuda의 Mint 계정: Circle International Bermuda Limited |
| 체인 간 소각 및 발행                         | CCTP(Cross-Chain Transfer Protocol) | 출발 및 목적지 지원, 증명과 전달, 전송 유형의 조건을 확인한다.                          | 고지 없음                                                                                                                                        |
| 예치한 USDC를 지원 체인에서 사용할 통합 잔액 | Gateway                             | 잔액이 성립하는 예치 조건과 출금 경로를 확인한다.                                       | 고지 없음                                                                                                                                        |
| USDC 담보와 파트너 스테이블코인의 연결       | xReserve                            | 모델에서 얻은 개념 후보다. 담보 계약과 파트너 토큰의 발행 및 상환 책임을 확인해야 한다. | 고지 없음 (보존한 제품 문서 없음)                                                                                                                |
| 환전 견적과 온체인 자산 교환 결제            | StableFX                            | 기관 승인, 견적 수락과 계약의 조건부 보관(escrow)을 확인한다.                           | Circle Technology Services, LLC                                                                                                                  |
| 지급의 접수, 전환, 이동과 결제               | CPN(Circle Payments Network)        | 상품, 운영 방식과 기관별 지급 상태를 확인한다.                                          | Circle Technology Services, LLC가 운영                                                                                                           |
| 앱 기능을 조합하고 구현하는 도구             | App Kits, Studio, Portal            | SDK, 생성 코드와 실제 실행하는 제품을 구별한다.                                         | 고지 없음                                                                                                                                        |
| 에이전트의 지갑과 지급 기능                  | Agent Stack                         | 지갑 정책, 지원 네트워크와 지급 방식을 각각 확인한다.                                   | 고지 없음                                                                                                                                        |

법인 열의 출처: [메인넷 발표](https://www.circle.com/pressroom/circle-launches-arc-mainnet-an-economic-operating-system-for-the-internet), [ARC 백서](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/arc_whitepaper.pdf), [개발자 지원금 공고](https://www.circle.com/grant), [CPN 상품 설명](https://www.circle.com/cpn), [USDC 약관](https://www.circle.com/legal/usdc-terms), [10-K](https://www.sec.gov/Archives/edgar/data/1876042/000187604226000062/crcl-20251231.htm). 고지는 위 자료의 제공자 및 운영자 설명에서 확인했다.

[CPN 개요](https://developers.circle.com/cpn.md), [Gateway 개요](https://developers.circle.com/gateway.md), [StableFX 개요](https://developers.circle.com/stablefx.md)가 제품별 기능을 설명한다. 공식 Bridge 문서는 CCTP의 소각(burn), 증명(attestation)과 발행(mint)을 SDK가 처리한다고 설명한다. 이 설명으로 기본 이전 흐름을 연결할 수 있다. xReserve의 담보와 파트너 토큰의 권리 구조는 이 문서의 확인 범위와 구별한다.

예를 들어 앱 개발 도구가 USDC 지급 화면을 생성해도 거래를 승인할 지갑, 실행 체인과 수취 주소가 필요하다. API가 견적을 반환해도 결제 자산이 이전됐다는 뜻은 아니다. 이처럼 사용자가 보는 기능 하나가 여러 제품과 주체의 처리를 거쳐 완성된다.

앱 하나가 여러 기능을 조합하는 모습을 설명용 지급 사례로 생각해 볼 수 있다. 사용자는 앱에서 수취인과 지급 대상을 정하고, 앱은 지갑 서비스를 통해 승인을 받아 거래를 제출한다. Arc에서 실행하는 경로라면 네트워크가 거래를 처리하고, 앱은 그 결과를 조회해 지급 내역을 갱신한다. 목적지 체인이 다르면 자산 이전 기능이, 최종 수취 통화가 다르면 교환이나 금융기관의 지급 기능이 추가될 수 있다. 이들은 필요한 조건에 따라 선택하는 기능이며 모든 지급에 반드시 등장하는 순서가 아니다.

이 사례에서 제품은 서명, 이전이나 교환 같은 기능을 제공하고, 앱은 그 기능을 사용자의 업무로 구성한다. 따라서 제품이 제공하는 API를 호출할 수 있는지와 사용자가 원하는 업무를 끝낼 수 있는지는 서로 다른 질문이다. 이후에는 제품 이름보다 처리 대상 자산, 실행 환경, 승인 주체와 완료 결과를 함께 확인해야 한다.

[App Kits 문서](https://docs.arc.io/app-kit.md)는 체인마다 저수준 프로토콜 연동을 따로 조합하지 않고 여러 체인의 지급과 유동성 흐름을 구성하는 SDK 모음이라고 정의한다. App Kit SDK는 아래 기능을 하나의 인터페이스로 제공하고, Send를 제외한 기능은 개별 Kit로도 설치할 수 있다고 설명한다. 이 분류는 공식 문서의 것이다.

| 공식 기능                                                         | 처리하는 일과 기반 기능                                                                      |
| ----------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| [Send](https://docs.arc.io/app-kit/send.md)                       | 같은 체인의 지갑 사이에서 토큰을 이전한다. 발신자의 adapter로 서명하고 제출한다.             |
| [Bridge](https://docs.arc.io/app-kit/bridge.md)                   | CCTP의 소각, 증명과 발행을 처리하여 USDC와 EURC를 체인 사이에서 이전한다.                    |
| [Swap](https://docs.arc.io/app-kit/swap.md)                       | 같은 체인 또는 체인 사이에서 토큰을 교환한다. Arc의 지원 자산은 USDC, EURC와 cirBTC다.       |
| [Unified Balance](https://docs.arc.io/app-kit/unified-balance.md) | Gateway 기반으로 여러 체인의 USDC 예치와 통합 잔액 사용을 처리한다.                          |
| [Onramp](https://docs.arc.io/app-kit/onramp.md)                   | 법정화폐로 Arc의 USDC 또는 EURC를 사는 위젯이다. KYC, 지급 처리와 목적지 지갑 전달을 다룬다. |
| [Earn](https://docs.arc.io/app-kit/earn.md)                       | 지원 대출 프로토콜의 USDC와 EURC vault를 찾고 예치 지분과 자산의 환산을 처리한다.            |
| [Borrow](https://docs.arc.io/app-kit/borrow.md)                   | Arc에서 cirBTC 담보로 USDC를 차입하고 상환하여 담보를 회수한다.                              |

[App Kits의 기능 목록](https://docs.arc.io/app-kit.md)의 원문은 다음과 같다.

> capability (Send, Bridge, Swap, Unified Balance, Onramp, Earn, and Borrow)

Borrow 문서는 담보 제공과 USDC 수령을 하나의 원자적 거래(atomic transaction)로 설명하고, 대출의 건전성(loan health) 변화와 청산 위험을 webhook으로 관측할 수 있다고 설명한다. Earn의 비수탁(non-custodial) 구조는 예치한 자산이 vault 계약에 있고 연동 개발자가 vault를 선택한다는 뜻이다. Onramp는 지갑 adapter를 요구하지 않으며 구매와 목적지 전달을 위젯이 처리한다. 모든 SDK 기능이 같은 서명 경로를 사용한다는 뜻은 아니다.

[Agentic Economy 문서](https://docs.arc.io/build/agentic-economy.md)는 ERC-8004를 에이전트 신원 등록, 평판 구축과 자격 증명 검증에, ERC-8183을 작업 생성, USDC 에스크로 자금 조달, 결과물 제출, 평가와 결제에 연결한다. 에이전트의 지갑과 API 이용료 지급만으로 범위를 줄이지 않는다. 표준의 역할을 공식 문서가 설명하는 범위이며, 표준 자체와 모든 배포 계약을 이번에 시험한 것은 아니다.

[Agentic Economy의 작업 계약 설명](https://docs.arc.io/build/agentic-economy.md)의 원문은 다음과 같다.

> full job lifecycle: creation, escrow funding, deliverable submission,
> evaluation, and USDC settlement.

#### 2.3.2 지갑과 서명 서비스: 자산 이전을 승인하는 권한은 누가 통제하는가

사용자와 앱의 의도를 실제 거래 승인으로 연결하는 경로는 지갑 유형에 따라 다르다.

Circle Wallets에서도 요청과 승인을 구별한다. 개발자 제어 지갑은 백엔드가 거래 승인 비밀값(entity secret)으로 승인하며 MPC(Multi-Party Computation, 다자간 연산) 방식으로 서명을 처리한다. 사용자 제어 지갑과 모듈형 지갑은 사용자가 승인한다. [서명과 승인 문서](https://developers.circle.com/wallets/signing-and-authorization-models.md)

한국어:

```text
 [앱 백엔드] --API 키--> [Circle Wallets API]      (1) 요청 인증: 이 서비스를 호출할 수 있는가?
                                 |
                                 v                  (2) 거래 승인: 이 이전을 허용하는가?
           +---------------------+----------------------+
           v                                            v
 개발자 제어 지갑                            사용자 제어 지갑, 모듈형 지갑
 [백엔드가 승인 비밀값으로 승인]             [사용자가 승인]
           |                                            |
           v                                            v
 [MPC 방식으로 서명 생성]                    [서명 생성]
```

English:

```text
 [App backend] --API key--> [Circle Wallets API]   (1) request auth: may it call the service?
                                 |
                                 v                  (2) approval: is this transfer allowed?
           +---------------------+----------------------+
           v                                            v
 Developer-controlled wallet                 User-controlled or modular wallet
 [Backend approves with entity secret]       [User approves]
           |                                            |
           v                                            v
 [Signature produced by MPC]                 [Signature produced]
```

그림의 두 질문에는 따로 답해야 한다. API 키는 (1)에 답하고, 지갑 유형에 따른 승인 주체가 (2)에 답한다. 개발자 제어 지갑에서는 승인 비밀값을 가진 백엔드가 승인하고 MPC 방식으로 서명을 만들며, 사용자 제어 지갑과 모듈형 지갑에서는 사용자가 승인한다.

**요청과 승인의 구별: 한 행은 서로 구별해서 확인할 질문이다**

| 구분      | 확인하는 질문                                 | 그 확인만으로 확정되지 않는 것                                |
| --------- | --------------------------------------------- | ------------------------------------------------------------- |
| 요청 인증 | 이 요청자가 서비스를 호출할 수 있는가?        | 자산 이전이 승인됐는지는 별도입니다.                          |
| 거래 승인 | 해당 지갑의 승인 주체가 이 거래를 허용했는가? | 서명 생성과 제출 결과는 별도입니다.                           |
| 서명      | 거래에 필요한 서명이 생성됐는가?              | 네트워크 접수와 실행 성공은 별도입니다.                       |
| 결과 확인 | 제출된 거래가 어떻게 처리됐는가?              | 금융서비스의 최종 지급 결과는 추가 확인이 필요할 수 있습니다. |

요청 인증은 호출자가 서비스를 사용할 수 있는지 확인하는 과정이고, 거래 승인은 해당 지갑의 승인 주체가 서명을 허용하는 과정이다. 서명은 그 승인 경로에 따라 거래에 필요한 암호학적 결과를 만드는 처리다. 마지막으로 서명한 거래를 네트워크에 전달해야 실제 체인 처리가 시작될 수 있다. 앞 표는 이 차이를 비교하며, 어떤 확인이 다음 결과까지 보장하는지 혼동하지 않도록 한다.

[Unified Balance의 지갑 모델](https://docs.arc.io/app-kit/unified-balance.md)은 예치자와 사용 서명자가 다른 사례를 설명한다. Circle Wallets의 스마트 계약 계정(SCA)과 Privy 서버 지갑은 자신의 Unified Balance 사용을 직접 서명할 수 없는 모델에 포함된다. delegate 흐름에서는 지갑이 예치자로 남고 권한을 받은 EOA가 사용을 서명한다. 따라서 예치한 주소와 해당 기능의 서명자를 자동으로 같은 주체로 가정하지 않는다.

### 2.4 회사와 기관: 사업, 발행과 금융서비스의 주체는 어떻게 나뉘는가

회사와 기관은 Circle의 회사와 법인(2.4.1)과, 자산을 발행하고 상환하거나 고객에게 지급하는 발행자와 금융기관(2.4.2)으로 나누어 본다.

#### 2.4.1 회사와 법인: 사업과 계약의 주체는 어떻게 구분되는가

Circle이라는 이름은 회사와 관련 사업을 가리킬 때 사용된다. 상장회사인 Circle Internet Group, Inc., 네트워크 출시 주체인 Arc Network Services LLC, 자산 발행 및 금융서비스 계약의 주체는 역할이 다르다. Arc 출시 발표는 네트워크를 허가된 검증자 집합이 운영하며 출시 법인은 소프트웨어 서비스를 제공한다고 고지한다. 제3자 앱은 다시 그 앱의 운영자가 기능과 계약을 관리한다.

법인명도 상품 및 지역에 따라 확인해야 한다. 비EEA USDC 약관은 Circle Internet Financial, LLC를 발행자로 설명하고, Circle Internet Financial Europe SAS가 이중 발행자가 됐다고 안내한다. Singapore 고객은 별도 대체 조항을 가진다. USYC 상품 문서는 Circle International Bermuda Limited와 Cayman Islands의 펀드 구조를 설명한다. 이 이름들을 모두 하나의 계약 상대방으로 합치지 않는다. [USDC 약관](https://www.circle.com/legal/usdc-terms), [USYC 설명](https://developers.circle.com/tokenized/usyc/overview.md)

Claude가 제시한 자세한 법인 지도와 Grok가 남긴 법인 간 계약의 확인 한계는 함께 유지했다. StableFX를 CTS(Circle Technology Services, LLC)가 제공한다는 고지는 [개발자 지원금 공고](https://www.circle.com/grant)에서 확인했지만, 그 고지만으로 해당 법인의 계약상 비수탁 지위까지 확정하지 않는다. 법인별 계약은 기업 결제 설명에서 더 확인할 질문이다.

공식 글 연결: [How Arc Supports Onchain FX 24/7](https://www.arc.io/blog/how-arc-can-support-247-onchain-fx) (2025-12-15, [공식 원문](https://www.arc.io/blog/how-arc-can-support-247-onchain-fx)). StableFX 고지는 CTS가 사용자를 대신해 디지털 자산을 수령하거나 전송하지 않는다고 명시한다. 제공자가 공개한 역할 설명을 보완한 것이며 개별 계약의 법률상 지위를 판정한 것은 아니다.

같은 사용자 화면에서도 계약의 대상은 나뉠 수 있다. 예를 들어 제3자 앱에서 USDC를 보내는 경우, 앱 운영자는 화면과 업무 기능을 제공하고, 지갑 서비스는 승인과 서명에 관여하며, 네트워크는 거래를 처리한다. 자산의 상환 조건은 다시 발행자의 약관에 따른다. 이 사례는 앞에서 구별한 역할을 연결한 설명용 상황이며 특정 앱의 실제 계약 구조를 확인한 결과는 아니다.

따라서 회사 이름을 확인한 뒤에는 그 회사가 이번 관계에서 어떤 역할로 등장하는지 물어야 한다. 소프트웨어를 제공하는 법인, 자산을 발행하는 법인과 고객의 지급 요청을 처리하는 기관을 구별해야 서비스 장애, 상환 요청과 지급 지연을 각각 어느 관계에서 검토할지 정할 수 있다. 법인 목록만 외우는 것보다 상품, 지역과 처리 업무를 법인에 연결하는 것이 중요하다.

**법인 관계도: 누가 누구를 소유하고, 누가 어떤 역할로 등장하는가**

앞에서 나온 법인들이 모두 상장회사 Circle Internet Group 아래에 있는지는 수집 자료로 답할 수 있는 범위가 둘로 나뉜다. Circle Internet Group의 2025 회계연도 10-K는 USDC, EURC와 USYC를 발행하는 법인들을 회사 자신 또는 해외 자회사로 적는다. 반면 Wallets, StableFX와 CPN을 제공하는 Circle Technology Services, LLC와 Arc 메인넷을 출시한 Arc Network Services LLC는 보존한 10-K 본문에서 이름을 찾지 못했다. 두 법인의 이름은 Circle 제품 문서와 공고의 법적 고지에 나온다. 아래 그림은 이 차이를 실선과 점선으로 구별해 내가 그렸다.

한국어:

```text
[Circle Internet Group, Inc.]  NYSE: CRCL 상장회사, 10-K를 제출한 법인
  |
  |  실선: 10-K가 회사 자신 또는 자회사로 적은 법인
  +-- Circle Internet Financial, LLC ....... 비EEA USDC 발행, NY BitLicense
  +-- Circle Internet Financial Europe SAS . EEA의 USDC, EURC 발행 (해외 자회사)
  +-- Circle International Bermuda Limited . USYC 발행, Bermuda의 Mint 계정 (해외 자회사)
  +-- Circle Internet Singapore Pte Ltd. ... Singapore 결제 서비스 (해외 자회사)
  +-- Hashnote (2025-01 지분 100% 인수) ..... 계열사를 통해 펀드를 운용
                     :
                     : 운용 관계 (소유 아님)
                     v
           [SDYF: Cayman 펀드, USYC는 이 펀드 지분의 온체인 표현]

  점선: 10-K 캡처에서 이름을 찾지 못한 법인, 소유 관계 미확인
  :.. Circle Technology Services, LLC ...... Wallets, StableFX 제공, CPN 운영, Arc 테스트넷 제공
  :.. Arc Network Services LLC ............. Arc 메인넷 출시 주체
```

English:

```text
[Circle Internet Group, Inc.]  NYSE: CRCL listed company, the 10-K filer
  |
  |  solid: named in the 10-K as the company itself or a subsidiary
  +-- Circle Internet Financial, LLC ....... non-EEA USDC issuer, NY BitLicense
  +-- Circle Internet Financial Europe SAS . EEA USDC and EURC issuer (foreign subsidiary)
  +-- Circle International Bermuda Limited . USYC issuer, Bermuda Mint accounts (foreign subsidiary)
  +-- Circle Internet Singapore Pte Ltd. ... Singapore payment services (foreign subsidiary)
  +-- Hashnote (100% acquired, 2025-01) .... manages the fund through affiliates
                     :
                     : manages (not owns)
                     v
           [SDYF: Cayman fund; USYC is the onchain form of its shares]

  dotted: not found in the captured 10-K; ownership unconfirmed
  :.. Circle Technology Services, LLC ...... provides Wallets, StableFX; operates CPN; offers Arc testnet
  :.. Arc Network Services LLC ............. launched Arc mainnet
```

실선 쪽부터 읽는다. 10-K는 미국 규제를 설명하면서 Circle Internet Financial, LLC가 뉴욕주의 가상자산 면허(BitLicense)를 보유한다고 적고, 해외 규제 문단에서는 회사의 "foreign subsidiaries"에 적용되는 규제를 설명하며 Bermuda, France와 Singapore 법인을 차례로 든다. 같은 문서는 2025년 1월 Hashnote의 지분 100%를 인수했다고 적는다. 출처: [10-K](https://www.sec.gov/Archives/edgar/data/1876042/000187604226000062/crcl-20251231.htm). 따라서 이 법인들에 대해서는 상장회사 Circle Internet Group이 맨 위에 있다고 말할 수 있다. 상장회사 자체의 소유자는 주주이며, 그림은 회사 아래의 관계만 다룬다.

SDYF는 실선 아래에 두지 않았다. 10-K는 Hashnote가 계열사를 통해 이 펀드를 운용한다고 적을 뿐 펀드를 자회사로 적지 않는다. USYC의 발행자 표기도 자료마다 다르다. 10-K의 규제 설명과 [USYC 상품 문서](https://developers.circle.com/tokenized/usyc/overview.md)은 Circle International Bermuda Limited가 USYC를 발행한다고 적고(10-K:3275), 10-K의 인수 설명은 SDYF를 "the issuer of USYC"라고 적는다(10-K:4642). 펀드 지분의 발행과 그 지분을 나타내는 토큰의 발행을 각각 가리킨 것으로 보이지만, 이 해석은 내 추론이며 계약 문서로 확인하지 않았다.

점선 쪽 두 법인은 Circle 상표의 문서에서 각 제품의 제공자로 고지된다. Circle Wallets와 StableFX는 Circle Technology Services, LLC가 제공하고([개발자 지원금 공고](https://www.circle.com/grant)), 같은 법인이 CPN을 운영하며([CPN 상품 설명](https://www.circle.com/cpn)) Arc 테스트넷도 제공한다([ARC 백서](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/arc_whitepaper.pdf)). Arc 메인넷은 Arc Network Services LLC가 출시하고 허가된 검증자 집합이 운영한다([메인넷 발표](https://www.circle.com/pressroom/circle-launches-arc-mainnet-an-economic-operating-system-for-the-internet)). 이 고지는 역할을 알려 줄 뿐 소유 관계를 밝히지 않는다. 10-K의 첨부 목록에는 자회사 목록(Exhibit 21.1)이 있으나(10-K:9434) 그 내용은 보존하지 않았으므로, 두 법인이 Circle Internet Group의 자회사인지는 그 첨부를 확인해야 확정할 수 있다.

#### 2.4.2 발행자와 금융기관: 자산의 발행, 상환과 금융서비스는 누가 맡는가

자산 발행자와 금융기관은 상품의 발행 및 상환, 고객 심사와 지급을 처리한다. 앞의 노드와 검증자가 체인의 상태를 확인하는 역할과는 구별된다. 블록이 확정돼도 발행자에게 직접 상환할 자격이나 금융기관의 고객 지급이 자동으로 성립하는 것은 아니다.

한국어:

```text
            체인의 처리                              발행자와 금융기관의 처리
 누가     노드와 검증자                            자산 발행자, 금융기관
 무엇을   거래 기록과 상태를 확정                  발행, 상환, 고객 심사, 지급
 결과     체인의 잔액 변화                         상환 자격, 고객의 실제 수령
               |                                               ^
               +----- 블록 확정으로 자동 성립하지 않음 ----X---+
```

English:

```text
            Chain processing                         Issuer and institution processing
 Who      nodes and validators                     issuers, financial institutions
 What     finalize records and state               issue, redeem, screen, pay out
 Result   balance changes onchain                  redemption rights, actual receipt
               |                                               ^
               +----- not created by block finality --------X--+
```

왼쪽 처리가 끝나도 오른쪽 결과는 자동으로 생기지 않는다. 블록이 확정되면 체인의 잔액은 바뀌지만, 발행자에게 직접 상환할 자격이나 고객의 실제 수령은 발행자와 금융기관의 처리로 따로 성립한다. 아래쪽 연결선의 X는 이 자동 연결이 없다는 표시다.

이 역할의 계약 주체는 2.4.1 회사와 법인에서, 상품별 권리와 자격은 2.2.1 자산의 유형에서 설명했다. 따라서 발행자와 금융기관의 역할을 판단할 때에는 해당 상품과 지역의 계약을 함께 보아야 한다. 뒤의 업무 결과 절에서는 이러한 처리가 체인 거래와 어떻게 연결되는지 살펴본다.

여기서 토큰 발행은 해당 자산을 나타내는 토큰 수량을 생성하는 처리이고, 이전은 이미 존재하는 토큰을 계정 사이에서 이동시키는 처리이며, 상환은 발행자와의 조건에 따라 토큰을 반환하고 약속된 대가를 받는 관계다. 따라서 사용자가 다른 주소에서 USDC를 받았다는 사실과 발행자에게 직접 상환할 자격을 갖췄다는 사실을 구별해야 한다. 앞의 자산 유형 절에서 설명한 Circle Mint 계정과 상품별 자격이 이 구별에 필요하다.

USDC를 예로 들면 이용자는 자격과 계정 조건을 갖춘 뒤 Circle의 서비스를 통해 USD를 USDC로 전환하거나 USDC를 USD로 상환하는 관계를 맺는다. [비EEA USDC 약관](https://www.circle.com/legal/usdc-terms)은 이 서비스를 정상 상태의 Circle Mint 계정과 연결한다. 주소 사이의 토큰 전송은 그와 다른 체인 처리다. 네트워크는 전송의 실행 및 확정을 담당하고, 직접 발행이나 상환 서비스의 계정 자격과 처리는 발행자와의 관계에서 확인한다. 이 설명은 해당 약관의 적용 범위 안에서 서비스를 구별하며 다른 지역의 절차를 대신하지 않는다.

한국어:

```text
            체인 밖: 발행자와의 관계                       |  체인 위: Arc
                                                           |
 [Mint 계정 이용자] --USD 입금--> [Circle] --USDC 발행-----+--> [이용자의 주소]
 [Mint 계정 이용자] <--USD 지급-- [Circle] <--USDC 반환----+--- [이용자의 주소]
                                                           |
                                                           |    [주소 A] --USDC 이전--> [주소 B]
 조건: 정상 상태의 Circle Mint 계정 (비EEA 약관)           |    조건: 체인의 거래 규칙
```

English:

```text
            Offchain: relationship with the issuer         |  Onchain: Arc
                                                           |
 [Mint account user] --USD in--> [Circle] --issue USDC-----+--> [User's address]
 [Mint account user] <--USD out-- [Circle] <--return USDC--+--- [User's address]
                                                           |
                                                           |    [Address A] --USDC transfer--> [Address B]
 Condition: Circle Mint account in good standing (non-EEA) |    Condition: chain transaction rules
```

세로선 왼쪽은 이용자와 발행자의 관계이고, 오른쪽은 체인 위의 처리다. 위 두 줄의 발행과 상환은 Circle Mint 계정을 통해 USD와 USDC를 바꾸는 관계이고, 아래 줄의 주소 간 이전은 발행자를 거치지 않는 체인 거래다.

금융기관이 처리하는 지급은 또 다른 업무다. 예를 들어 현지 통화를 받을 수취인이 있는 지급에서는 체인의 결제 거래에 더해 수취 기관의 송금 처리가 필요할 수 있다. [CPN 상품 개요](https://developers.circle.com/cpn.md)는 온체인 USDC 결제 뒤 지급 파트너가 현지 통화를 전달하는 Fiat Payouts를 설명한다. 체인의 수취 주소와 최종 고객의 은행 계좌는 이 업무에서 서로 다른 대상을 가리킨다.

한국어:

```text
 [송금 기관] --USDC 결제--> [수취 기관의 체인 주소]        체인 위: 결제 거래
                                    |
                                    | 수취 기관이 현지 통화로 송금
                                    v
                         [최종 고객의 은행 계좌]          체인 밖: 법정화폐 지급

 체인 주소와 은행 계좌는 서로 다른 대상이며 결과도 따로 확인한다.
```

English:

```text
 [Sending institution] --USDC settlement--> [Receiving institution's address]   onchain: settlement
                                                     |
                                                     | receiving institution sends local currency
                                                     v
                                       [End customer's bank account]           offchain: fiat payout

 The chain address and the bank account are different targets, checked separately.
```

수취 기관의 체인 주소로 USDC가 결제되는 것과 최종 고객의 은행 계좌에 현지 통화가 들어오는 것은 다른 결과다. 앞의 것은 체인에서, 뒤의 것은 수취 기관의 송금 기록과 고객의 수령으로 확인한다.

서비스를 누가 운영하는지도 상품에 따라 나뉜다. 같은 CPN 개요의 self-managed에서는 이용 기관이 보관, 지급과 준수 업무를 운영하고, managed에서는 Circle이 라이선스, 보관, 준수, 자금 관리와 결제를 처리한다고 설명한다. 이 제품 분류는 개별 기관의 계약과 승인 상태를 대신하지 않는다. 공통 개념 단계에서는 자산 발행, 상환, 결제와 고객 지급이 누구의 처리인지 구별하고, 구체적인 책임은 해당 상품 및 계약에서 확인한다.

[Onramp 문서](https://docs.arc.io/app-kit/onramp.md)의 법정화폐 구매 위젯은 Mint 계정의 직접 발행 및 상환과 별도 경로다. 서버가 사용자와 목적지 지갑에 대한 session을 만들고 위젯이 구매 및 전달을 처리한다. 결제수단과 국가에 따라 지원 범위가 다르며 일부 수단은 KYB를 요구한다. 문서는 직불카드, Apple Pay, Google Pay와 제한된 국가의 은행 이체를 설명하고 신용카드는 지원하지 않는다고 명시한다. 구매 위젯의 접근 가능성을 Mint의 직접 상환 자격으로 바꾸지 않는다.

### 2.5 사용자와 개발자: 거래 의도와 앱의 업무 규칙은 누가 정하는가

사용자 또는 승인 주체는 거래 의도와 사용 권한을 승인하고, 앱 및 계약 개발자는 거래를 조립하며 계약의 업무 규칙을 구현한다. 사용자가 승인했다는 사실만으로 계약이 그 의도를 올바르게 구현했다고 확인할 수는 없다. 또한 앱의 제출 요청이 성공한 것과 지급이 성공한 것은 구별해야 한다. 이 절은 3.1(역할 분담)의 역할 표에서 사용자와 개발자에 해당하는 두 행을 자세히 설명한다.

한국어:

```text
  [사용자 또는 승인 주체]                 [앱과 계약 개발자]
            |                                      |
            | 원하는 결과를 정하고 승인            | 요청과 업무 규칙을 구현
            +-----------------+--------------------+
                              v
                       [실행되는 거래]

  구별할 것 1: 사용자가 승인했다  !=  계약이 의도대로 구현됐다
  구별할 것 2: 앱의 제출이 성공했다  !=  지급이 성공했다
```

English:

```text
  [User or authorizing party]             [App and contract developer]
            |                                      |
            | decides and approves the outcome     | implements requests and rules
            +-----------------+--------------------+
                              v
                    [Transaction executed]

  Distinction 1: user approved          !=  contract implements the intent
  Distinction 2: app submission worked  !=  payment succeeded
```

두 참여자는 서로 다른 것을 정한다. 사용자는 원하는 결과를 정하고 승인하며, 개발자는 그 결과를 요청과 계약 규칙으로 구현한다. 그림 아래의 두 구별은 한쪽의 확인이 다른 쪽의 결과까지 보장하지 않는다는 뜻이다.

거래 의도는 사용자가 달성하려는 업무다. 예를 들어 사용자가 특정 수취인에게 자산을 보내려 한다면, 앱은 그 의도를 실행 체인, 보내는 계정, 수취 주소, 자산과 처리 방식으로 구체화해야 한다. 단순한 자산 이전인지 계약 호출인지에 따라 요청 내용도 달라진다. 사용자의 문장과 네트워크가 처리할 거래는 같은 형식이 아니므로, 앱이 그 사이의 변환을 담당한다.

개발자는 화면과 백엔드뿐 아니라 계약이 집행할 업무 규칙도 정한다. 설명용 예산 앱이라면 누가 지급을 요청할 수 있는지, 누구의 승인을 받아야 하는지, 계약이 어떤 조건에서 자산을 이전하는지를 구현해야 한다. 이러한 업무 규칙은 앱의 설계 예시이며 Arc가 모든 앱에 제공하는 공통 지급 정책은 아니다. 네트워크가 계약을 정해진 방식으로 실행한다고 해서 개발자가 작성한 규칙이 사용자의 의도와 일치한다고 보장되지는 않는다.

한국어:

```text
 [설명용 예산 계약: 개발자가 정한 규칙]
   누가 지급을 요청할 수 있는가    -> 등록된 직원
   누구의 승인이 필요한가          -> 재무 담당자
   언제 자산을 이전하는가          -> 승인 완료 그리고 한도 이내
        |
        v
 [Arc: 계약 코드를 정해진 방식대로 실행]
        |
        v
 규칙이 사용자의 의도와 맞는지는 Arc가 보장하지 않는다 (개발자가 설계할 몫)
```

English:

```text
 [Illustrative budget contract: rules set by the developer]
   who may request a payment       -> registered staff
   whose approval is required      -> finance officer
   when assets move                -> approved and within the limit
        |
        v
 [Arc: executes the contract code as written]
        |
        v
 Arc does not guarantee the rules match the user's intent (the developer's design)
```

세 규칙은 개발자가 계약에 넣은 설명용 예시다. Arc는 계약 코드를 쓰인 대로 실행할 뿐, 그 규칙이 사용자의 의도와 맞는지 판단하지 않는다.

사용자의 앱 내 확인과 실제 지갑의 거래 승인을 구별하는 것도 이 책임 범위에 속한다. [공식 서명 문서](https://developers.circle.com/wallets/signing-and-authorization-models.md)는 거래를 요청하는 주체와 서명을 승인하는 주체를 따로 설명한다. 개발자 제어 지갑에서는 사용자가 앱에 요청했더라도 백엔드가 지갑의 승인 경로를 처리하며, 사용자 제어 지갑에서는 사용자의 인증과 승인이 서명에 필요하다. 따라서 화면의 버튼 이름만으로 누가 자산 이전 권한을 행사했는지 판단할 수 없다.

한국어:

```text
                 [사용자가 앱에서 "보내기"를 누름]
                                |
            +-------------------+--------------------+
            v                                        v
   개발자 제어 지갑                          사용자 제어 지갑
   [앱 백엔드]                               [사용자 본인]
      | 지갑의 승인 경로를 처리                 | 인증하고 직접 승인
      v                                        v
   [서명 생성]                               [서명 생성]

   같은 버튼이라도 자산 이전 권한을 행사한 주체가 다르다.
```

English:

```text
                 [User taps "Send" in the app]
                                |
            +-------------------+--------------------+
            v                                        v
   Developer-controlled wallet               User-controlled wallet
   [App backend]                             [The user]
      | handles the wallet's approval          | authenticates and approves
      v                                        v
   [Signature created]                       [Signature created]

   Same button, different party exercising the transfer authority.
```

사용자의 화면 조작이 같아도 두 지갑의 승인 경로는 다르다. 개발자 제어 지갑에서는 백엔드가 지갑의 승인을 처리하고, 사용자 제어 지갑에서는 사용자 본인의 인증과 승인이 있어야 서명이 만들어진다.

이 절에서 사용자와 개발자의 역할을 나누는 이유는 거래의 출발점을 명확히 하기 위해서다. 사용자는 원하는 결과를 정하고, 개발자는 그 결과를 요청과 업무 규칙으로 구현한다. 2.3.2(지갑과 서명 서비스)에서 본 지갑과 서명 서비스는 그 요청을 해당 계정의 승인 경로에 연결한다.

## 3. 관계: 구성요소들은 한 업무에서 서로 어떻게 연결되는가

구성요소를 하나씩 구별했다면, 다음 질문은 이들이 한 업무에서 어떻게 연결되는가다. 3.1(역할 분담)은 회사, 네트워크, 제품과 앱의 제공 관계와 참여자별 역할을 비교하고, 3.2(거래 처리)는 한 거래가 승인에서 결과 확인까지 이어지는 단계를, 3.3(업무 결과)은 여러 처리가 모여 이루는 이전, 교환과 지급의 결과를 설명한다. 첫머리의 섹션 전체 관계 그림은 이 연결을 한 지급의 순서로 요약한 것이다.

### 3.1 역할 분담: 누가 무엇을 제공하고 요청하며 처리하는가

아래 그림은 회사, 네트워크, 제품과 앱 네 가지만 남긴 관계다. 구체적인 법인 이름과 소유 관계는 2.4.1(회사와 법인)에서 따로 그린다. 화살표는 출시, 제공, 기능 조합과 거래 요청의 관계이며 지분 소유나 법률상 책임을 나타내지 않는다. 이 구분은 서로 다른 문서의 역할을 연결하기 위해 내가 정했다.

한국어:

```text
               [회사와 관련 법인]
                |              |
                | (a)          | (b)
                v              v
         [Arc 네트워크]    [제품: 지갑, 지급 API, 개발 도구]
                ^                 |
                | (d)             | (c)
                |                 v
                +---------- [앱: Circle 앱 / 제3자 앱] --(e)--> [다른 체인, 금융기관]

(a) 출시, 소프트웨어 제공   (b) 만들어 제공   (c) 앱이 기능을 골라 조합
(d) 거래 제출, 계약 호출    (e) Arc를 거치지 않는 경로
```

English:

```text
           [Company and affiliates]
                |              |
                | (a)          | (b)
                v              v
         [Arc network]     [Products: wallets, payment APIs, dev tools]
                ^                 |
                | (d)             | (c)
                |                 v
                +---------- [Apps: Circle / third-party] --(e)--> [Other chains, institutions]

(a) launch, software services   (b) build and provide   (c) apps select and combine functions
(d) submit transactions, call contracts                  (e) routes that do not use Arc
```

회사와 관련 법인은 네트워크를 출시하고 소프트웨어를 제공하며(a), 지갑, 지급 API와 개발 도구 같은 제품을 만든다(b). 앱은 그 제품 가운데 필요한 기능을 골라 사용자의 업무로 조합하고(c), Arc에서 실행하는 경로라면 거래를 제출하거나 계약을 호출한다(d). 같은 앱이 다른 체인이나 금융기관의 경로를 쓸 수도 있다(e). 네트워크와 제품을 따로 그린 이유는 제품을 쓴다는 사실만으로 실행 체인이 Arc로 정해지지 않기 때문이다.

거래에는 의도, 승인, 제출, 실행과 결과 확인의 역할이 있다. 아래 표의 한 행은 책임을 구별해야 하는 참여자 하나다. 이 표는 문서들의 역할을 연결한 나의 설명이며 계약상 손실 책임을 확정한 표는 아니다.

| 참여자                  | 처리하는 일                                            | 그 역할만으로 확인되지 않는 것                         |
| ----------------------- | ------------------------------------------------------ | ------------------------------------------------------ |
| 사용자 또는 승인 주체   | 거래 의도와 사용 권한을 승인한다.                      | 계약이 의도한 대로 구현됐는지는 별도다.                |
| 앱 및 계약 개발자       | 거래를 조립하고 계약의 업무 규칙을 구현한다.           | 제출 성공이 지급 성공을 뜻하지 않는다.                 |
| 지갑과 서명 서비스      | 승인 경로에 따라 서명을 만든다.                        | 모든 지갑이 같은 주체의 승인으로 작동하지 않는다.      |
| RPC 제공자 및 노드      | 조회와 거래 제출을 처리한다.                           | 접수 응답만으로 블록 포함과 성공은 확인되지 않는다.    |
| 허가된 검증자           | 합의에서 제안 및 투표를 수행한다.                      | 자산의 준비금과 법정화폐 상환을 직접 보장하지 않는다.  |
| 풀 노드                 | 블록의 서명을 확인하고 거래를 로컬 EVM에서 재실행한다. | 일반 노드를 운영한다고 합의 투표 권한을 얻지는 않는다. |
| 자산 발행자 및 금융기관 | 상품의 발행 및 상환, 고객 심사와 지급을 처리한다.      | 그 역할을 체인의 블록 확정으로 대체할 수 없다.         |

이렇게 참여자를 구별하면 한 지급에 필요한 설명을 연결할 수 있다. 앱은 의도를 요청으로 만들고, 지갑은 승인 경로에 따라 서명하며, 노드와 검증자는 체인 거래를 처리하고 확인한다. 발행자와 금융기관은 상품의 상환 또는 고객 지급처럼 체인 거래만으로 끝나지 않는 업무를 맡는다. 다음 절에서는 먼저 이 중 한 체인 거래가 어떻게 처리되는지 살펴본다.

### 3.2 거래 처리: 승인한 요청은 어떻게 기록된 결과가 되는가

앞 절에서 처리 주체를 구별했으므로, 이제 한 거래가 승인 및 제출에서 실행과 확정을 거쳐 결과 확인으로 이어지는 과정을 설명한다. 같은 참여자라도 단계마다 처리하거나 확인하는 내용이 다르다.

다음 그림은 한 거래의 큰 흐름을 체인 밖과 체인 위로 나누어 그렸다. 세로선이 두 구역의 경계이고 번호는 처리 순서다. 가운데의 실행 검사와 합의 투표는 여러 호출을 묶어 표시했으며, 세부 구현 순서나 동일 시점의 처리를 확정하지 않는다.

한국어:

```text
 체인 밖                               |  Arc 체인 위
                                       |
 [사용자 또는 승인 주체]               |
         | (1) 의도와 권한             |
         v                             |
 [앱, 지갑: 서명]                      |
         | (2) 서명한 거래 제출 -------+--> [RPC와 노드: 접수 검사]
         |                             |               | (3)
         |                             |               v
         |                             |      [실행 검사, 합의 투표]
         |                             |               | (4)
         |                             |               v
         |                             |      [확정된 블록과 상태]
         |                             |               |
         v                             |               |
 [앱: 결과 확인] <--(5) 영수증, 성공 여부, 잔액 조회---+
```

English:

```text
 Offchain                              |  On the Arc chain
                                       |
 [User or authorizing party]           |
         | (1) intent and permission   |
         v                             |
 [App, wallet: signing]                |
         | (2) submit signed tx -------+--> [RPC and nodes: admission checks]
         |                             |               | (3)
         |                             |               v
         |                             |      [Execution checks, consensus votes]
         |                             |               | (4)
         |                             |               v
         |                             |      [Finalized block and state]
         |                             |               |
         v                             |               |
 [App: check results] <--(5) receipt, success, balance-+
```

(1) 사용자 또는 승인 주체가 의도와 권한을 정하면 앱과 지갑이 서명을 만들고, (2) 경계를 넘어 RPC와 노드에 거래를 제출한다. 노드는 접수 검사를 거쳐 (3) 실행 검사와 합의 투표로 넘기고, (4) 블록이 확정되면 상태가 바뀐다. (5) 앱은 다시 경계를 넘어 영수증, 성공 여부와 잔액을 조회한다. 3.2.1은 (1)-(2)를, 3.2.2는 (3)-(4)를, 3.2.3은 (5)를 설명한다. 앱 쪽 왼쪽 세로선은 앱이 제출 뒤에도 같은 거래를 추적한다는 뜻이다.

#### 3.2.1 승인과 제출: 거래 요청은 어떤 권한으로 네트워크에 전달되는가

사용자 또는 승인 주체가 의도와 권한을 정하면 앱과 지갑은 승인 경로에 따라 거래를 구성하고 서명한 요청을 RPC와 노드에 전달한다. 요청 인증과 자산 이전의 승인은 앞에서 설명한 서로 다른 단계다. 제출을 접수했다는 응답은 그 뒤의 실행 성공이나 블록 확정을 보장하지 않는다.

#### 3.2.2 실행과 확정: 거래는 상태를 어떻게 바꾸고 그 결과는 어떻게 확정되는가

실행은 거래와 계약이 기존 잔액과 저장값을 어떻게 바꾸는지 계산하는 과정이고, 합의는 어떤 블록을 받아들일지 결정하는 과정이다. 앞 그림의 가운데는 검사, 실행과 합의의 관계를 묶어 보여 주므로, 이를 세부 구현의 고정된 실행 순서로 읽으면 안 된다.

또한 블록에 포함된 거래가 확정됐다는 뜻과 계약의 의도한 상태 변경이 성공했다는 뜻은 다르다. 실패한 실행도 그 거래가 실패했다는 결과로 확정될 수 있다. 따라서 확정은 체인의 기록에 관한 질문이고, 성공은 실행 결과에 관한 질문이다. 다음 절에서 앱이 두 질문의 답을 어떻게 나누어 확인해야 하는지 설명한다.

공식 글 연결: [Arc Wallet Integration Guide: USDC Balances & Fees](https://www.arc.io/blog/supporting-arc-in-wallets-one-balance-usdc-fees-and-complete-history) (2026-09-04, [공식 원문](https://www.arc.io/blog/supporting-arc-in-wallets-one-balance-usdc-fees-and-complete-history)). 지갑 안내는 온체인 revert를 확정된 실패로 구별한다. 확정 여부와 계약 실행의 성공 여부를 나누어 읽는 근거다.

한국어:

```text
                  |  확정 전                    |  확정 후
 -----------------+-----------------------------+--------------------------------------
 실행 성공        |  결과가 아직 정해지지 않음  |  의도한 상태 변경이 기록됨
 실행 실패        |  결과가 아직 정해지지 않음  |  실패했다는 결과가 기록됨, 상태 변경 없음

 확정은 기록에 관한 질문이고, 성공은 실행 결과에 관한 질문이다.
```

English:

```text
                  |  Not yet final              |  Final
 -----------------+-----------------------------+--------------------------------------
 Execution worked |  outcome not yet settled    |  intended state change is recorded
 Execution failed |  outcome not yet settled    |  the failure is recorded, no state change

 Finality is about the record; success is about the execution result.
```

가로축은 기록이 확정됐는지를, 세로축은 실행이 성공했는지를 묻는다. 오른쪽 아래 칸처럼 실행에 실패한 거래도 확정될 수 있으므로, 앱은 두 질문의 답을 따로 확인해야 한다.

#### 3.2.3 결과 확인: 접수, 실행 성공과 확정은 어떻게 구별하는가

영수증을 확인할 때에는 확정과 실행 성공을 나누어야 한다. 블록에 포함됐지만 계약 실행이 실패한 거래도 확정될 수 있다. 제출 전에 거절된 거래, 아직 대기 중인 거래와 실행 실패는 또 다르다. 공식 거래 수명주기 문서는 이 상태들을 나눈다. [거래 수명주기](https://docs.arc.io/integrate/wallets/transaction-lifecycle.md)

공식 글 연결: [Arc Wallet Integration Guide: USDC Balances & Fees](https://www.arc.io/blog/supporting-arc-in-wallets-one-balance-usdc-fees-and-complete-history) (2026-09-04, [공식 원문](https://www.arc.io/blog/supporting-arc-in-wallets-one-balance-usdc-fees-and-complete-history)). 지갑 안내는 영수증의 블록 번호와 실행 status를 나누어 확인하도록 설명한다. 이 결과만으로 금융기관의 최종 고객 지급을 확인할 수는 없다.

예를 들어 설명용 지급 앱에서 서명과 제출이 끝났어도 계약 실행에 실패했다면 지급 완료로 표시할 수 없다. 블록 포함과 확정, 실행 성공 여부, 기대한 잔액과 계약 상태는 서로 다른 질문이며 하나의 완료 표시가 모두를 대신하지 않는다.

따라서 앱은 접수 응답에 더해 영수증의 실행 성공 여부와 확정된 상태를 확인하고, 사용자가 기대한 잔액 변화와 대조해야 한다. 체인의 거래 결과를 확인한 뒤에도 체인 간 이전이나 금융기관 지급처럼 별도 처리가 남아 있을 수 있다. 다음 절에서는 그 업무 결과를 구별한다.

### 3.3 업무 결과: 여러 주체와 서비스의 처리는 어떤 결과로 이어지는가

사용자가 원하는 결과는 목적지에서 자산을 쓰거나, 다른 자산으로 교환하거나, 최종 수취인이 지급을 받는 것일 수 있다. 아래 세 사례는 서로 다른 결과를 설명하며, 모든 업무가 이전, 교환과 은행 지급을 순서대로 거친다는 뜻은 아니다. 각 사례에서 한 거래의 성공과 전체 업무의 완료를 구별한다.

**업무별 완료 조건: 한 행은 사용자가 원하는 업무 결과다**

| 업무        | 사용자가 원하는 결과                      | 중간 처리만으로 부족한 이유                                         | 최종적으로 확인할 것                                   |
| ----------- | ----------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------ |
| 자산 이전   | 목적지에서 자산을 사용할 수 있습니다.     | 출발지 처리가 끝나도 증명, 전달이나 목적지 처리가 남을 수 있습니다. | 목적지의 사용 가능한 잔액을 확인합니다.                |
| 자산 교환   | 조건에 따라 서로 다른 자산이 교환됩니다.  | 견적과 수락만으로 실제 결제가 끝나지는 않습니다.                    | 교환 조건과 양쪽 자산이 인도된 결과를 확인합니다.      |
| 지급과 수취 | 약속한 자산이나 통화를 수취인이 받습니다. | 결제 거래 완료와 기관 지급 및 실제 수령은 구별해야 합니다.          | 해당 상품이 약속한 지급 결과와 수령 상태를 확인합니다. |

#### 3.3.1 자산 이전: 출발지의 자산은 어떻게 목적지에서 사용할 수 있게 되는가

한 체인의 거래를 승인하고 결과를 확인하는 방법만으로 체인 간 이전의 완료를 설명할 수는 없다. 출발 체인과 목적지 체인 사이에는 별도의 메시지 증명과 전달이 필요하다.

CCTP 설명에서 사용자가 보는 전송 하나는 출발 체인의 소각, 메시지 증명, 전달과 목적지의 발행을 연결한다. 소각은 출발 체인의 해당 잔액을 줄이는 처리이고, 증명은 메시지가 요구하는 확인 조건을 충족했음을 전달하며, 목적지 발행은 그 메시지를 검사하고 목적지의 잔액을 생성하는 처리다.

다음 그림의 소각, 증명과 발행 흐름은 [공식 Bridge 문서](https://docs.arc.io/app-kit/bridge.md)에 대응한다. SDK는 이 CCTP 흐름을 조합한다. Iris와 전달 서비스까지 나눈 그림의 배치는 기존 모델 설명을 연결해 내가 구성했다. 화살표는 앞 처리의 결과가 다음 처리의 입력이라는 뜻이다. 전송 유형별 확인 조건과 지연 수치를 이 그림에서 확정하지 않는다.

한국어:

```text
[출발 체인: 소각과 전송 유형의 확인 조건]
                     |
                     v
          [Iris: 메시지 증명 서비스]
                     |
                     v
        [사용자 / 앱 / 전달 서비스]
                     |
                     v
 [목적지: 증명 검사, 발행 실행과 결과 확정]
                     |
                     v
       [목적지의 사용 가능한 잔액]
```

English:

```text
[Source chain: burn and transfer-type confirmation rules]
                         |
                         v
              [Iris: attestation service]
                         |
                         v
             [User / app / relay service]
                         |
                         v
 [Destination: verify, execute mint and finalize result]
                         |
                         v
             [Usable destination balance]
```

출발 체인의 소각이 확인됐다고 목적지 잔액이 이미 사용할 수 있는 상태는 아니다. 증명 대기, 전달 실패나 목적지 실행 실패가 있다면 어느 단계까지 완료됐는지 확인해야 한다. 단순히 출발 거래를 다시 보내면 같은 사용자 의도의 새로운 이전을 만들 수 있으므로 재시도도 처리 단계와 메시지 상태에 맞춰 설계해야 한다. 이는 모델 설명의 과정을 연결해 도출한 개발상 질문이며 이 리서치에서 실제 전송을 실행한 결과는 아니다.

빠른 전송과 표준 전송의 확인 조건을 하나로 합치지 않는다. Arc 내부의 확정 시간, 출발 체인의 확인 대기와 체인 간 이동 전체 시간은 서로 다른 측정이다. 세부 지원과 증명 조건은 프로토콜 및 개발 부분에서 확인한다.

이 과정에서 앱이 추적해야 하는 대상도 단계마다 바뀐다. 출발지에서는 소각 거래를, 중간에서는 그 처리에 연결된 메시지와 증명을, 목적지에서는 발행 거래와 사용 가능한 잔액을 확인한다. 같은 사용자 의도에 속한다는 이유로 모두 하나의 체인 거래가 되는 것은 아니다. 따라서 이전 완료를 설명할 때에는 어느 단계의 기록을 확인했고 어떤 처리가 남았는지 함께 표시해야 한다.

#### 3.3.2 자산 교환: 견적과 승인은 어떻게 서로 다른 자산의 교환으로 이어지는가

체인 간 이전이 같은 자산의 처리 위치를 연결한다면, 환전은 서로 다른 자산을 교환하는 조건까지 다룬다. StableFX에서는 거래 조건을 정하는 정보 전달과 실제 자산을 교환하는 결제를 구별해야 한다.

StableFX는 기관이 스테이블코인 간 환전 견적을 요청하고 거래를 수락한 뒤 온체인으로 결제하는 제품이다. 공식 문서는 RFQ(Request-for-Quote, 견적 요청) 모델에서 체인 밖의 견적 및 수락과 Arc 계약의 결제를 연결한다. 계약 escrow는 자산을 조건부로 보관하고 PvP(Payment-versus-Payment, 양쪽 지급의 조건부 교환)로 두 지급이 함께 처리되도록 설계한다. 실제 API 요청과 기관 승인은 이 리서치에서 시험하지 않았다. [StableFX 개요](https://developers.circle.com/stablefx.md)

공식 글 연결: [How Arc Supports Onchain FX 24/7](https://www.arc.io/blog/how-arc-can-support-247-onchain-fx) (2025-12-15, [공식 원문](https://www.arc.io/blog/how-arc-can-support-247-onchain-fx)). StableFX 소개는 체인 밖 RFQ와 온체인 결제를 연결한다. 기관 승인이나 실제 결제 성공을 직접 관측한 자료는 아니다.

다음 그림은 정보 전달과 자산 이동을 별도 연결로 표시한다. 원본의 체인 밖 제품 분류와 계약 결제 설명을 함께 반영해 내가 재구성했다.

한국어:

```text
[기관] -- 견적 요청과 수락 --> [StableFX API / 유동성 제공자]
   |
   +-- 자산과 이전 승인 --> [Arc의 결제 계약] <-- 자산과 승인 -- [상대방]
                                  |
                                  v
                       [조건을 충족한 양쪽 자산 교환]
```

English:

```text
[Institution] -- request / accept quote --> [StableFX API / liquidity provider]
      |
      +-- assets and authorization --> [Arc settlement contract] <-- assets / approval -- [Counterparty]
                                                  |
                                                  v
                                [Both assets exchanged when conditions hold]
```

API는 정보와 처리 요청을 전달하고, 계약은 자산 인도 규칙을 집행한다. 그러므로 StableFX를 체인 밖 기능으로만 묶으면 온체인 결제가 빠진다. 반대로 환전 결제가 Arc에서 확정됐다고 고객 은행 계좌의 입금까지 끝났다고 볼 수도 없다. 앱이 어느 자산을 최종 결과로 약속했는지에 따라 추가 처리가 필요하다. 이용 기관의 승인과 API 키, 지원 자산 및 계약 책임은 각각 확인해야 한다.

교환에서 정보와 자산을 구별하는 이유는 견적이 경제적 조건을 제시할 뿐 그 자체로 잔액을 바꾸지는 않기 때문이다. 기관은 견적과 수락 내용을 결제에 필요한 승인 및 자산과 연결해야 하고, 계약은 정해진 조건 아래 교환을 처리한다. 조건부 교환이라는 설계 목적만으로 이용 기관의 자격, 자금 준비와 실제 결제 성공까지 확인된 것으로 볼 수는 없다. 따라서 앱은 견적을 받음, 조건을 수락함과 자산 교환이 완료됨을 구별해야 한다.

[공식 Swap 문서](https://docs.arc.io/app-kit/swap.md)는 SDK의 같은 체인 교환과 체인 간 교환을 별도로 제공한다. Arc의 지원 자산은 USDC, EURC와 cirBTC이고, mainnet 제공을 기본으로 하되 Arc testnet을 예외로 표시한다. 다른 체인의 지원 토큰 목록을 Arc 목록으로 옮기지 않는다. [Stablecoin FX 문서](https://docs.arc.io/build/stablecoin-fx.md)는 온체인 교환 가격과 설정 가능한 슬리피지 허용치(slippage tolerance)를 설명한다. 이 SDK 교환과 기관용 StableFX의 RFQ 및 PvP 결제를 같은 제품으로 합치지 않는다.

#### 3.3.3 지급과 수취: 정산은 어떻게 최종 수취인의 지급 결과로 이어지는가

환전이나 결제 자산의 이동이 끝나도 사용자가 요청한 지급 업무는 계속될 수 있다. 최종 수취인이 현지 통화로 받아야 하는 경우에는 금융기관이 처리하는 지급과 실제 수령을 따로 확인한다.

CPN은 글로벌 지급을 접수, 전환, 이동 및 결제하도록 제공하는 네트워크와 상품 묶음이다. 공식 상품 개요는 self-managed와 managed를 나눈다. 앞은 이용 기관이 스테이블코인의 보관, 지급과 준수 업무를 운영하고 Circle이 API와 경로를 제공하는 방식이다. 뒤는 Circle이 라이선스, 보관, 준수, 자금 관리와 결제를 처리한다고 설명하는 방식이다. 이 상품 설명이 이용자의 개별 계약과 승인 상태를 대신하지는 않는다. [CPN 운영 방식](https://developers.circle.com/cpn.md)

Fiat Payouts는 온체인 USDC 결제와 현지 법정화폐 지급을 연결한다. Stablecoin Payments는 제3자 지갑으로 스테이블코인을 보내거나 받는 상품이므로 모든 CPN 상품에 은행 지급이 이어지는 것은 아니다. 아래 그림은 Fiat Payouts형 경로를 설명하기 위한 일부 사례다. 정보 전달과 결제 자산의 이동을 나누며 마지막에 고객 수령 확인을 둔다.

한국어:

```text
[고객의 지급 요청]
        |
        v
[송금 기관: 고객 확인과 자금]
        |
        +-- 지급 정보 --> [CPN 조정] --> [수취 기관]
        |
        +-- 결제 자산 --> [선택한 체인의 결제] --> [수취 기관]
                                                     |
                                                     v
                                          [현지 법정화폐 송금]
                                                     |
                                                     v
                                               [고객 수령 확인]
```

English:

```text
[Customer payment request]
        |
        v
[Sending institution: customer checks and funds]
        |
        +-- payment data --> [CPN coordination] --> [Receiving institution]
        |
        +-- settlement asset --> [Selected-chain settlement] --> [Receiving institution]
                                                                        |
                                                                        v
                                                               [Local fiat transfer]
                                                                        |
                                                                        v
                                                              [Customer receipt check]
```

체인은 결제 거래를 확정하고, 수취 기관은 해당 상품의 법정화폐 지급을 처리한다. 공식 상태 문서의 Transaction `COMPLETED`는 온체인 거래 확인을 뜻한다. Payment `COMPLETED`는 수취 기관이 법정화폐 송금을 완료했다는 뜻이며, 전송 방식에 따라 수취인이 아직 받지 않았을 수도 있다고 명시한다. 따라서 앱은 자신이 표시하는 완료의 뜻을 정의하고 사용자에게 약속한 최종 결과와 대조해야 한다. [CPN 상태 사양](https://developers.circle.com/cpn/concepts/payments/component-states-and-workflows.md)

이 사례는 Grok의 기관별 지급 설명에 ChatGPT의 정보 및 자산 구분을 적용해 발전시킨 것이다. CPN과 Arc의 통합 발표를 모든 CPN 지급이 Arc에서 결제됐다는 운영 관측으로 바꾸지 않는다. 법정화폐 지급과 환불, 기관의 지연 및 추가 정보 요청은 기업 결제 설명에서 더 설명한다.

고객 화면의 완료 표시는 이 서로 다른 결과 가운데 무엇을 뜻하는지 분명해야 한다. 온체인 결제 완료를 보여 주는 화면과 최종 수취를 약속하는 화면은 확인할 상태가 다르다. 정보 요청이나 기관의 지급 지연이 남았다면 체인 거래가 확정됐다는 사실은 유지하면서 업무의 미완료 상태도 설명해야 한다. 이는 결제 기록을 취소됐다고 바꾸거나, 반대로 체인 거래의 성공만으로 고객 수령을 단정하는 오류를 피하기 위한 구별이다.

## 4. 설명 범위: 공통 개념으로 설명할 수 있는 것과 추가 확인할 것은 무엇인가

구성요소부터 업무 결과까지의 관계를 이해해도 모든 기능의 현재 제공 상태나 이용 자격이 확인되는 것은 아니다. 마지막으로 개념 설명이 허용하는 범위를 구별하고, 이후 원고에서 확인할 질문을 연결한다.

### 4.1 제공 상태: 개념과 설계 설명은 현재 이용 가능성과 어떻게 구별되는가

출시 발표는 회사가 어떤 제품을 출시했다고 주장하는지 알려 준다. 기술 문서는 기능과 지원 조건을 설명한다. 공개 코드는 특정 구현 경로를 보여 주며, RPC 응답은 특정 시각에 요청한 조회 결과다. 이 증거들을 같은 강도로 합치지 않는다. 예를 들어 메인넷 출시 발표로 모든 파트너의 실제 운영이나 고객 이용이 입증되지는 않는다.

이번 공식 발표의 검증자 표기는 "Worldpay (now Global Payments)."다. 이 표기는 모델 답변의 이름 차이를 설명하지만, phased rollout이라는 조건을 함께 읽어야 한다. 기관별 현재 투표 참여 여부는 직접 관측하지 않았다. 기밀 기능은 네트워크 전체 제공을 위한 개발 중으로 표시했고, ARC는 초기 민트와 공개 출시를 구별했다. [해당 발표](https://www.circle.com/pressroom/circle-launches-arc-mainnet-an-economic-operating-system-for-the-internet)

따라서 제품을 검토할 때에는 실행 체인, 이동 자산, 승인 주체, 완료 상태와 이용 자격을 각각 물어야 한다. 네트워크 접속이 가능하다는 답은 금융서비스 승인이나 투자 상품 자격의 답이 아니다. Agent Wallets 정책과 App Kits의 지원 환경도 제품별로 확인해야 한다.

**질문별 확인 자료: 한 행은 확인하려는 질문과 그에 필요한 자료다**

| 확인하려는 질문                            | 확인에 사용할 자료     | 추가로 구별할 조건                     |
| ------------------------------------------ | ---------------------- | -------------------------------------- |
| 어떤 기능과 구조를 설명하는가?             | 제품 문서와 기술 문서  | 문서의 버전과 적용 환경을 확인합니다.  |
| 어떤 출시나 도입을 발표했는가?             | 공식 발표              | 단계별 도입과 실제 운영을 구별합니다.  |
| 구현에서 어떤 처리를 수행하는가?           | 해당 버전의 코드       | 배포된 버전과 일치하는지 확인합니다.   |
| 특정 환경에서 실제로 어떤 결과가 나왔는가? | 조회 응답과 실행 기록  | 관측 시각과 확인 범위를 기록합니다.    |
| 누가 어떤 조건으로 이용할 수 있는가?       | 약관, 계약과 승인 조건 | 상품, 지역과 이용자 자격을 구별합니다. |

앞 표는 자료의 우열을 일괄적으로 정한 것이 아니라 질문과 확인 자료를 연결한 나의 정리다. 약관은 이용 자격이나 계약 조건을 확인할 때 필요하고, 기술 문서는 처리 방식과 지원 환경을 확인할 때 필요하다. 실제 이용 가능성을 판단하려면 문서의 환경 및 기준일을 맞춘 뒤 관측이나 승인 상태를 추가로 확인해야 한다. 한 종류의 자료가 다른 질문의 답까지 대신하지 않도록 하는 것이 이 절의 기준이다.

이번 개정에서 연결한 공식 자료의 기준은 2026-10-07 보존 라이브러리다. 2025년 Litepaper의 출시 설계와 2026년 Token Whitepaper의 제안된 ARC 경제 구조, docs의 Live 및 Planned 기능 표시는 서로 다른 시점과 책임을 설명한다. 특히 docs는 Fee Manager와 CallFrom을 Live로, APS와 Stablecoin Services를 Planned로 구별하며 네이티브 양자내성 거래 서명도 향후 단계로 남긴다. 이 판본들을 하나의 현재 제공 상태로 합치지 않는다.

### 4.2 후속 질문: 필요성, 기술, 업무와 개발 분석에서 어떤 조건을 더 확인해야 하는가

유용한 원본 내용을 없애는 대신 이 원고에서 소개한 범위와 이후 목적지를 구별한다. 표의 한 행은 다른 부분에서 심화할 설명 하나다. 아직 확인할 세부와 필요한 자료를 함께 기록한다.

| 원본 설명과 위치                                   | 공통 원고에서 반영한 내용                                                                                                                                                           | 이어 확인할 부분                                              |
| -------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| ChatGPT, Claude, Grok의 정의, 회사와 제품          | 기술 정의, 사업 비전, 법인과 제품의 기능을 함께 설명했다.                                                                                                                           | 필요성에서 별도 네트워크가 필요한 업무와 대안을 비교한다.     |
| ChatGPT, Claude, Grok의 자산과 잔액                | 권리, 계정과 지갑, 공유 잔액, 체인별 상태 및 수탁 장부를 설명했다.                                                                                                                  | 가치와 토큰에서 수익 및 권리의 조건을 심화한다.               |
| Claude의 소수 자릿수, 이벤트, 차단과 자기파괴 조건 | 단위와 중복 이벤트 및 실패의 구별을 설명했다.                                                                                                                                       | 프로토콜과 개발에서 세부 구현을 확인한다.                     |
| ChatGPT, Claude, Grok의 자산 및 정보 이동          | 내부 거래, 체인 간 이전, 환전과 기관 지급을 별도 과정으로 그렸다.                                                                                                                   | 기업 결제에서 실패, 대사와 환불을 심화한다.                   |
| Claude, Grok의 활동 지표, AMP와 계획               | 회사 발표 및 계획과 실제 관측을 구별했다. Grok 답변이 소개한 AMP(Arc Multi-Proposer Protocol, 여러 제안자를 두어 거래 포함과 순서를 다루려는 구상)의 구현은 여기서 확정하지 않았다. | 현재 상태와 프로토콜에서 날짜, 모집단과 제공 상태를 확인한다. |
| Claude의 Agent Wallets 지원 표와 출처 목록         | 기능별 환경 확인이 필요함을 설명했다.                                                                                                                                               | 개발에서 메인넷과 테스트넷 정책 및 서비스 지원을 대조한다.    |

실제 상환과 기관 계약, 고객 수령, 노드 운영과 거래 제출, ARC의 공개 이전 및 스테이킹, CCTP의 전송 유형별 증명 조건은 이 원고에서 시험하지 않았다. 그 한계를 유지하면서도 개념과 관계는 충분히 설명할 수 있다. 이후 부분은 이 공통 설명에서 정의한 대상과 완료 상태를 사용해 필요성, 기술 보장, 업무와 접근 조건을 더 구체화한다.
