# Arc에서의 개발: Arc 위에 앱을 만들 때 무엇이 필요하고, 왜 필요하며, 어떻게 준비하는가

이 원고는 Arc 위에 앱을 만들려는 개발자를 위한 안내다. Arc에서 개발한다는 말은 네트워크에 접속하는 일부터 서비스의 승인과 실제 자금 처리까지 서로 다른 일을 포함한다. 그래서 1절(구현 경로)에서 만들 기능이 요구하는 경로를 정하고, 2절(준비물)과 3절(실행 권한)에서 그 경로에 필요한 준비물과 권한을 갖춘 뒤, 4절(정상 실행)과 5절(실패 처리)에서 한 번의 실행과 실패 처리를 따라간다. 각 단위는 개발자에게 필요한 것, 그것이 필요한 이유, 준비하거나 확인하는 방법의 순서로 쓴다. 실험 관측: 표시는 공식 문서의 절차를 옮긴 뒤 2026-10-07에 Arc 테스트넷과 Circle의 테스트넷 키로 실행한 단계에 붙이고, 관측한 결과는 그 절차 바로 다음 문단에 적는다. 잔액, 수수료, 버전과 오류 문구는 실험한 날의 값이다. 미실행 항목: 표시는 절차를 옮겼지만 실행하지 않은 단계에 붙인다. 그런 단계는 문서가 안내하는 방법이며 확인한 결과가 아니다.

2026-10-07에 확인한 공식 영문 자료를 Arc의 설계와 사양 설명의 기준으로 삼는다. [Arc Litepaper](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/Arc%20Litepaper%20-%202025.pdf)와 [Arc Token Whitepaper](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/arc_whitepaper.pdf)의 설계 및 제안, 기술 문서의 이용 조건과 예제를 근거로 설명한다. 문서의 계획과 성능 목표는 그 표현을 유지하고, 기존 실험은 관측 자료로 보존한다.

 제목과 순서는 내가 개발자가 실제로 밟는 순서(경로 선택, 준비, 권한 결정, 실행, 실패 처리)를 기준으로 정했고, 1절(구현 경로)의 세 갈래는 그 절의 그림이 나누는 경로를 따랐다. 검증 실험의 계획과 결과, 제출 조건, 세 답변에서 보류한 내용 같은 리서치 기록은 부록인 6절(검증과 제출)에 둔다.

**개발 전체 개요: 구현 경로에서 실패 처리까지의 순서**

아래 개요는 내가 본문의 순서를 정리한 그림이며 실제 실험 결과가 아니다. 화살표는 앞 단계의 결정이 뒤 단계의 조건이 된다는 의존 관계를 나타낸다. 부록인 6절(검증과 제출)은 앱을 만드는 흐름 밖에 있으므로 점선 아래에 따로 그렸다.

한국어:

```text
[1. 구현 경로: 직접 체인 호출 / Circle 서비스 / 승인 상품]
                         |
                         v
[2. 준비물: 네트워크, 개발 도구, 시험 자금, 서비스 계정, 시험 환경, 기존 계약 점검]
                         |
                         v
[3. 실행 권한: 인증과 서명, 비밀, 지출 한도, 가스 대납, 위험 통제]
                         |
                         v
[4. 정상 실행: 요청 흐름, 체인 실행, 서비스 실행]
                         |
                         | 결과가 기대와 다르거나 확인되지 않으면
                         v
[5. 실패 처리: 실행 상태, 부분 성공, 오류 유형, 조회 장애]

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
[6. 부록: 검증 실험, 재현 기록, 제출 조건, 미확인 사항]
     실험 결과와 남은 [미실행] 단계, 프로그램 요구와의 대조
```

English:

```text
[1. Implementation path: direct chain calls / Circle services / approved products]
                         |
                         v
[2. Preparation: network, tools, test funds, service account, test environment, existing-contract review]
                         |
                         v
[3. Authority: authentication and signing, secrets, spending limits, gas sponsorship, risk controls]
                         |
                         v
[4. Normal run: request flow, chain run, service run]
                         |
                         | if the result differs from the expectation or cannot be confirmed
                         v
[5. Failure handling: execution state, partial success, error types, query failures]

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
[6. Appendix: validation experiments, reproduction records, submission conditions, open items]
     experiment results, the remaining [not run] steps, and the comparison with program requirements
```

요청자의 인증(authentication), 작업 권한 부여(authorization), 거래 서명(signing)은 서로 다른 절차다. 개발자 제어 지갑(developer-controlled wallets)과 사용자 제어 지갑(user-controlled wallets)은 서명 승인 주체를 구별하는 연구 내 표현이다. wallet set은 지갑 묶음이며 그 자체를 독립적인 보안 경계로 보지 않는다. 논스(nonce)는 계정 및 처리 경로의 순서를 다루는 값으로 거래 해시나 업무 식별자와 구별한다.

**목차**

- [Arc에서의 개발: Arc 위에 앱을 만들 때 무엇이 필요하고, 왜 필요하며, 어떻게 준비하는가](#arc에서의-개발-arc-위에-앱을-만들-때-무엇이-필요하고-왜-필요하며-어떻게-준비하는가)
  - [1. 구현 경로: 만들 기능이 직접 체인 호출, Circle 서비스, 승인 상품 중 어느 경로를 요구하는가](#1-구현-경로-만들-기능이-직접-체인-호출-circle-서비스-승인-상품-중-어느-경로를-요구하는가)
    - [1.1 직접 체인 호출: RPC와 자기 지갑으로 계약을 배포하고 USDC를 보낸다](#11-직접-체인-호출-rpc와-자기-지갑으로-계약을-배포하고-usdc를-보낸다)
    - [1.2 Circle 서비스: App Kit와 지갑 API는 기능마다 키 조건이 다르다](#12-circle-서비스-app-kit와-지갑-api는-기능마다-키-조건이-다르다)
    - [1.3 승인 상품: 일부 서비스와 자산은 계정 심사나 기관 자격을 받아야 쓸 수 있다](#13-승인-상품-일부-서비스와-자산은-계정-심사나-기관-자격을-받아야-쓸-수-있다)
  - [2. 준비물: 첫 요청을 보내기 전에 무엇을 갖추고 서로 맞춰야 하는가](#2-준비물-첫-요청을-보내기-전에-무엇을-갖추고-서로-맞춰야-하는가)
    - [2.1 네트워크: 앱, 지갑과 계약이 같은 체인을 가리키도록 chain ID와 RPC 주소를 맞춘다](#21-네트워크-앱-지갑과-계약이-같은-체인을-가리키도록-chain-id와-rpc-주소를-맞춘다)
    - [2.2 개발 도구: Arc Foundry와 App Kit를 설치하고 실제로 쓴 버전을 기록한다](#22-개발-도구-arc-foundry와-app-kit를-설치하고-실제로-쓴-버전을-기록한다)
    - [2.3 시험 자금: 테스트넷 USDC를 받고 가스와 전송 금액의 단위를 맞춘다](#23-시험-자금-테스트넷-usdc를-받고-가스와-전송-금액의-단위를-맞춘다)
    - [2.4 서비스 계정: Circle 서비스를 쓰려면 API 키를 발급받고 환경별로 나눈다](#24-서비스-계정-circle-서비스를-쓰려면-api-키를-발급받고-환경별로-나눈다)
    - [2.5 시험 환경: 계약 논리, Arc fork, 공개 체인과 서비스를 따로 시험한다](#25-시험-환경-계약-논리-arc-fork-공개-체인과-서비스를-따로-시험한다)
    - [2.6 기존 계약 점검: Ethereum에서 쓰던 계약을 Arc에 올리기 전에 계약이 쓰는 기능의 가정을 Arc의 차이와 대조한다](#26-기존-계약-점검-ethereum에서-쓰던-계약을-arc에-올리기-전에-계약이-쓰는-기능의-가정을-arc의-차이와-대조한다)
  - [3. 실행 권한: 누가 요청을 인증하고 거래에 서명하며, 자산 지출을 어디에서 제한하는가](#3-실행-권한-누가-요청을-인증하고-거래에-서명하며-자산-지출을-어디에서-제한하는가)
    - [3.1 승인 주체: 서비스 요청의 인증과 거래 서명은 서로 다른 자격증명이 맡는다](#31-승인-주체-서비스-요청의-인증과-거래-서명은-서로-다른-자격증명이-맡는다)
    - [3.2 비밀 관리: entity secret과 요청 암호문, 복구 파일을 보관하고 교체한다](#32-비밀-관리-entity-secret과-요청-암호문-복구-파일을-보관하고-교체한다)
    - [3.3 지출 한도: 앱, 서명자, 계약과 allowance는 자산 이동을 서로 다른 자리에서 막는다](#33-지출-한도-앱-서명자-계약과-allowance는-자산-이동을-서로-다른-자리에서-막는다)
    - [3.4 가스 대납: Gas Station 정책은 수수료 부담자를 바꿀 뿐 지출 한도가 아니다](#34-가스-대납-gas-station-정책은-수수료-부담자를-바꿀-뿐-지출-한도가-아니다)
    - [3.5 위험 통제: 서비스의 위험 심사와 USDC 계약의 주소 차단은 다른 경로에서 일어난다](#35-위험-통제-서비스의-위험-심사와-usdc-계약의-주소-차단은-다른-경로에서-일어난다)
  - [4. 정상 실행: 요청을 승인하고 제출한 뒤 그 결과를 업무 기록과 어떻게 대조하는가](#4-정상-실행-요청을-승인하고-제출한-뒤-그-결과를-업무-기록과-어떻게-대조하는가)
    - [4.1 요청 흐름: 사용자의 의도를 거래로 만들고 처리 식별자와 결과를 연결한다](#41-요청-흐름-사용자의-의도를-거래로-만들고-처리-식별자와-결과를-연결한다)
    - [4.2 체인 실행: Counter 계약을 배포하고 호출하며 USDC를 보낸 결과를 확인한다](#42-체인-실행-counter-계약을-배포하고-호출하며-usdc를-보낸-결과를-확인한다)
    - [4.3 서비스 실행: Onramp 세션을 만들고 브라우저 표시와 서버의 결과를 대조한다](#43-서비스-실행-onramp-세션을-만들고-브라우저-표시와-서버의-결과를-대조한다)
  - [5. 실패 처리: 실행 상태를 어떻게 판별하고, 완료된 효과를 보존한 채 남은 작업을 어디서부터 재개하는가](#5-실패-처리-실행-상태를-어떻게-판별하고-완료된-효과를-보존한-채-남은-작업을-어디서부터-재개하는가)
    - [5.1 실행 상태: 제출 거절, 실행 실패와 결과 미확인은 다음 행동이 다르다](#51-실행-상태-제출-거절-실행-실패와-결과-미확인은-다음-행동이-다르다)
    - [5.2 부분 성공: 여러 단계로 된 작업은 완료된 단계를 보존하고 남은 단계를 재개한다](#52-부분-성공-여러-단계로-된-작업은-완료된-단계를-보존하고-남은-단계를-재개한다)
    - [5.3 오류 유형: 오류가 난 단계와 이미 생긴 효과에 따라 재조회, 수정, 재개를 고른다](#53-오류-유형-오류가-난-단계와-이미-생긴-효과에-따라-재조회-수정-재개를-고른다)
    - [5.4 조회 장애: 결과를 읽지 못했을 때는 새 거래가 아니라 조회 경로를 복구한다](#54-조회-장애-결과를-읽지-못했을-때는-새-거래가-아니라-조회-경로를-복구한다)
  - [6. 검증과 제출(부록): 이 안내를 실험으로 어디까지 확인했고, 프로그램 요구와는 어떻게 대조하는가](#6-검증과-제출부록-이-안내를-실험으로-어디까지-확인했고-프로그램-요구와는-어떻게-대조하는가)
    - [6.1 검증 실험: 실험마다 답할 질문을 정하고, 실행한 실험의 결과를 적는다](#61-검증-실험-실험마다-답할-질문을-정하고-실행한-실험의-결과를-적는다)
    - [6.2 재현 기록: 실험 결과를 다른 사람이 다시 확인할 수 있는 자료로 남긴다](#62-재현-기록-실험-결과를-다른-사람이-다시-확인할-수-있는-자료로-남긴다)
    - [6.3 제출 조건: 프로그램이 요구하는 환경과 결과물을 구현의 준비 상태와 대조한다](#63-제출-조건-프로그램이-요구하는-환경과-결과물을-구현의-준비-상태와-대조한다)
    - [6.4 미확인 사항: 확정하지 않은 기여와 남은 질문을 확인할 곳에 연결한다](#64-미확인-사항-확정하지-않은-기여와-남은-질문을-확인할-곳에-연결한다)

공식 블로그의 관련 설명은 본문에서 원문 링크로 연결한다. 공식 발표와 설계 설명은 실제 운영을 직접 관측한 근거와 구별한다.

## 1. 구현 경로: 만들 기능이 직접 체인 호출, Circle 서비스, 승인 상품 중 어느 경로를 요구하는가

개발자가 가장 먼저 정할 것은 구현 경로다. 구현 경로는 앱이 어떤 인터페이스를 통해 작업을 요청하고, 누가 그 요청을 승인하며, 어디에서 실제 결과를 만드는지를 뜻한다. 경로를 먼저 정해야 하는 이유는 경로에 따라 승인과 결과 확인의 책임, 그리고 갖춰야 할 준비물이 달라지기 때문이다. 직접 체인 호출에서는 개발자가 노드 연결과 필요한 서명 및 전송이나 계약 호출을 구성한다. Circle 서비스를 이용하면 선택한 서비스의 인증 조건과 작업 객체를 함께 다루며, 체인 거래가 연결된다면 그 결과도 추적해야 한다. 서비스가 개입한다고 체인의 결과 확인이 불필요해지는 것은 아니다. 승인 상품은 이 두 경로에 계정 심사나 기관 자격이라는 이용 조건이 더해진 경우다. 정하는 방법은 만들 작업(전송, 체인 간 이전, 자산 구매 등)을 먼저 적고, 아래 그림의 세 갈래 가운데 그 작업이 요구하는 갈래를 고르는 것이다. 갈래마다 필요한 것은 1.1-1.3에서 설명한다.

이 조건들을 계정 등록을 차례로 통과하는 한 줄의 과정으로 보면 필요하지 않은 승인을 먼저 기다리거나, 공개 접속만으로 기관 상품도 이용할 수 있다고 오해할 수 있다. 아래는 ChatGPT 답변의 세 접근 계층과 Claude 답변의 네 단계(계정 없이 쓰는 기능, 자금, 계정과 키, 심사와 승인) 설명을 내가 기능의 의존 관계로 바꾼 그림이다.

한국어:

```text
                    [선택 기능과 제출 환경]
                               |
        +----------------------+-----------------------+
        |                      |                       |
        v                      v                       v
 [직접 EVM 경로]         [서비스 API 경로]        [제한된 자산/상품]
 RPC와 개발 도구         계정과 기능별 키         허용 목록과 기관 자격
 서명자와 자산/가스       승인 주체와 복구         실제 허용된 작업
        |                      |                       |
        +----------------------+-----------------------+
                               v
                    [정상/실패의 효과와 기록]
```

English:

```text
                 [Chosen function and submission environment]
                                      |
          +---------------------------+-------------------------+
          |                           |                         |
          v                           v                         v
  [Direct EVM path]           [Service API path]       [Restricted asset/product]
  RPC and development tools   Account and scoped keys  Allowlist and eligibility
  Signer and asset/gas        Authority and recovery   Permitted operations
          |                           |                         |
          +---------------------------+-------------------------+
                                      v
                         [Normal/failure effects and records]
```

화살표는 선택 기능이 요구하는 조건과 그 결과의 연결이며 모든 사용자가 모든 가지를 거친다는 뜻은 아니다. 예를 들어 자체 지갑의 USDC 전송과 Onramp 위젯, 기관 외환은 접근 조건이 다르다. 공개 계약 주소를 찾았더라도 호출 권한과 상품 자격 또는 실제 잔액은 별도로 확인한다. 기본 공개 RPC와 서버 서비스 인증은 [RPC 문서](https://docs.arc.io/arc/references/rpc-endpoints.md) 및 [키 문서](https://developers.circle.com/api-reference/keys.md)에서 구별한다.

예를 들어 사용자의 기존 지갑에서 USDC를 보내려는 앱이라면 서명할 지갑과 전송 인터페이스, 대상 체인과 잔액 및 가스를 먼저 연결한다. 개발자 제어 지갑 서비스를 사용하려면 여기에 서버의 서비스 인증과 민감한 작업 승인 및 서비스 객체 추적을 추가한다. 법정화폐로 자산을 구매하도록 만들려는 앱은 아래 Onramp 사례처럼 세션과 지급 수단 및 결과 통지를 다룬다. 이처럼 작업을 먼저 정해야 필요한 구성 요소를 고를 수 있다. 경로를 선택한 결과는 기능 이름뿐 아니라 승인 주체, 실행 대상과 완료 근거까지 포함해야 한다.

### 1.1 직접 체인 호출: RPC와 자기 지갑으로 계약을 배포하고 USDC를 보낸다

RPC(Remote Procedure Call)는 원격 노드에 조회나 거래 제출을 요청하는 인터페이스다. EVM(Ethereum Virtual Machine)은 계약을 실행하는 가상 머신이며 아래 직접 경로의 실행 대상이다. 공개 RPC로 체인 식별자와 블록을 읽는 데에는 자기 지갑의 서명이 필요하지 않다. 자신의 EOA(Externally Owned Account, 개인 키로 서명하는 계정)에서 자산을 보내려면 해당 체인의 잔액과 서명 수단 및 가스가 필요하다. Circle의 지갑 API나 승인 대상 상품을 사용하는 일에는 별도의 인증과 이용 조건이 붙는다.

직접 체인 호출 경로에서 개발자에게 필요한 것은 세 가지다. 체인에 요청을 보낼 RPC 주소, 거래에 서명할 지갑, 그리고 가스를 낼 USDC다. Arc에서는 가스도 USDC로 내므로, 테스트넷에서 거래를 보내려면 먼저 테스트넷 USDC를 받아야 한다([계약 주소 안내](https://docs.arc.io/arc/references/contract-addresses.md)의 USDC 절). 공식 [배포 안내](https://docs.arc.io/build/deploy-on-arc.md)는 이 경로를 시작하는 조건으로 Arc Foundry와 Git의 설치를 든다(공식 영문판의 Prerequisites 절). RPC 주소는 2.1(네트워크), 도구 설치는 2.2(개발 도구), 테스트넷 USDC는 2.3(시험 자금)에서 준비하고, 계약을 배포하고 USDC를 보내는 실행은 4.2(체인 실행)에서 설명한다.

[RPC endpoints](https://docs.arc.io/arc/references/rpc-endpoints.md)는 기본 Circle 메인넷 RPC가 익명 요청과 브라우저의 교차 출처 요청(CORS)을 허용하며 API 키나 자격증명을 요구하지 않는다고 설명한다. 제삼자 제공자는 자체 키를 요구할 수 있으므로 제공자별 조건을 확인한다. 이는 공식 연결 사양이며 이번 작업에서 메인넷 접속을 새로 시험한 결과는 아니다.

### 1.2 Circle 서비스: App Kit와 지갑 API는 기능마다 키 조건이 다르다

Circle 서비스 경로를 고른 개발자에게 필요한 것은 쓰려는 기능이 선택한 체인, 자산과 지갑에서 지원되는지, 그리고 그 기능이 어떤 키를 요구하는지에 대한 정보다. 패키지에 함수가 있다는 사실만으로는 선택한 환경에서 그 작업을 수행할 수 있다고 말할 수 없기 때문이다. 확인하는 방법은 앱의 요구를 먼저 전송, 체인 간 이전이나 자산 구매 같은 작업으로 정하고, 그 작업의 체인과 자산 및 지갑을 지원 문서와 대조하는 것이다. 지원 함수가 반환한 목록은 이 대조의 입력이며 계정 승인, 자금과 정상 실행의 증거를 대신하지 않는다. 아래 기능별 표는 이름이 다른 기능을 같은 설치 및 인증 절차로 처리하지 않도록 돕는다. 키를 발급받는 방법은 2.4(서비스 계정)에서 설명한다.

SDK(Software Development Kit)는 개발용 라이브러리와 인터페이스를 묶은 도구다. 공식 설치 안내는 App Kit SDK를 설치하면 Send, Bridge, Swap, Unified Balance, Onramp, Earn과 Borrow를 하나의 패키지에서 사용할 수 있다고 설명한다. Onramp와 Borrow의 통합자 수수료 설정에는 Circle API 키가 필요하다. Swap, Earn과 Borrow에서 API 키는 선택 사항이며, 키를 사용하면 이용 한도가 높아진다. Send는 자산 전송, Bridge는 체인 사이 이전, Swap은 교환, Unified Balance는 여러 체인의 USDC를 연결하는 기능이다. Onramp는 법정화폐로 자산을 구매하는 연결이고 Earn과 Borrow는 수익 및 담보 대출 기능이다. 실제 자산과 금융 조건은 선택 상품에서 확인한다.

[설치 문서](https://docs.arc.io/app-kit/tutorials/installation.md)는 통합 패키지 또는 개별 kit와 Viem 및 Ethers, Solana와 Circle Wallets 어댑터를 설명한다. 어댑터(adapter)는 SDK의 요청을 사용하는 지갑 및 체인의 인터페이스에 연결하는 구성 요소다. Circle Wallets 어댑터는 서버에서 사용한다. Solana 브리지에서는 EVM 어댑터도 필요하다고 안내하므로 한 패키지를 설치했다는 사실만으로 양쪽 지갑 구성이 끝나지는 않는다.

한 행은 선택 작업의 확인 조건이다. 이 표는 [지원 문서](https://docs.arc.io/app-kit/references/supported-blockchains.md)와 설치 안내를 함께 읽은 것이며 모든 계정에서 직접 실행했다는 뜻은 아니다.

| 작업            | 문서에서 확인할 범위                                                                                | 키와 실행 조건                                                                                                                                           |
| --------------- | --------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Send            | 선택 체인과 토큰, 지갑 및 전송 인터페이스를 정한다.                                                 | 직접 지갑의 서명과 서비스 지갑의 인증을 구별한다.                                                                                                        |
| Bridge          | 출발과 목적 체인, 토큰과 양쪽 어댑터 및 증명 경로를 확인한다.                                       | 공개 프로토콜 사용과 서비스 지갑의 키 및 가스를 구별한다.                                                                                                |
| Swap            | 체인과 자산의 지원을 확인한다. 문서는 메인넷 중심이며 Arc Testnet 예외를 둔다.                      | 키 없이 공동 이용 한도를 쓰거나 환경별 API 키를 사용한다. 전체 온보딩이 메인넷 Swap의 보편적 필수 조건은 아니다.                                         |
| Unified Balance | USDC의 출발 및 목적 체인과 forwarder 지원을 확인한다. forwarder는 연결 실행을 중계하는 구성 요소다. | 어떤 지갑이 자산 이동을 승인하며 어느 체인의 잔액과 가스를 쓰는지 확인한다.                                                                              |
| Onramp          | 지급 수단과 지역, 사용자 및 목적 지갑, sandbox 또는 production을 정한다.                            | 서버 API 키가 필수이며 일부 수단에는 KYB(Know Your Business, 기업 신원과 자격 확인)와 referrerDomain이 필요하다. 지갑 어댑터는 필요하지 않다고 안내한다. |
| Earn            | 선택 자산과 상품 및 환경의 조건을 확인한다.                                                         | 설치 문서는 API 키를 선택 사항으로 설명하며 키가 있으면 더 높은 이용 한도를 제공한다.                                                                    |
| Borrow          | 담보 자산과 대출 및 체인과 상품 조건을 확인한다.                                                    | API 키는 선택 사항이지만 통합자 수수료(integrator fee)를 설정하려면 필요하다고 안내한다.                                                                 |

지원 조회 함수도 구별한다. 통합 App Kit의 `getSupportedChains`에는 작업 유형을 지정할 수 있다. 독립 Bridge Kit의 `chainType`과 `isTestnet` 및 forwarder 필터를 그 함수에 그대로 넣는 것은 다른 인터페이스다. Onramp Kit와 Borrow Kit에는 그 메서드가 없으며 Borrow는 `BorrowChain` 열거형을 안내한다. 설치한 버전의 실제 서명과 반환값을 읽고 사용한다.

지원 자산도 기능마다 다르다. [지원 블록체인과 토큰](https://docs.arc.io/app-kit/references/supported-blockchains.md)은 Send에 지원 토큰의 별칭이나 계약 주소를 사용할 수 있다고 설명한다. Bridge는 USDC, EURC, WETH, cirBTC와 CCTPx(추가 자산까지 지원하는 Circle의 체인 간 이전 프로토콜)에 등록된 제삼자 자산, Arc의 Swap은 USDC, EURC와 cirBTC를 나열한다. Unified Balance는 USDC만, Onramp와 Earn은 USDC 및 EURC, Borrow는 담보 자산으로 cirBTC를 지원한다고 적는다. 토큰 별칭은 대소문자를 구분하지 않지만 체인 식별자와 기능별 열거형은 대소문자를 구분한다. 예를 들어 테스트넷 식별자는 `Arc_Testnet`이다. 별칭이 목록에 있다는 사실만으로 모든 체인과 기능에서 그 자산을 지원한다고 해석하지 않는다.

기능을 조합하는 앱에서는 각 작업의 결과가 다음 작업의 입력 조건을 충족하는지도 확인한다. 예를 들어 체인 간 이전 뒤 자산을 전송하려면 출발 체인의 처리가 끝났다는 사실뿐 아니라 목적 체인에서 사용할 잔액과 서명 및 가스가 준비됐는지 확인해야 한다. 같은 패키지에 두 기능이 있다는 사실만으로 이 연결이 검증되지는 않는다. 이 의존 관계는 정상 처리의 결과 확인과 부분 성공 뒤의 복구를 함께 설계해야 하는 이유다.

### 1.3 승인 상품: 일부 서비스와 자산은 계정 심사나 기관 자격을 받아야 쓸 수 있다

일부 서비스와 자산은 기술적으로 요청을 만들 수 있어도, 해당 계정이나 사용자가 그 작업을 허용받아야 쓸 수 있다. 이런 상품을 쓰려는 개발자에게는 접속 설정과 별도로 이용 자격이 필요하다. 예를 들어 계약 주소를 알고 잔액을 조회할 수 있어도 그 자산의 구독이나 상환을 할 자격까지 확보한 것은 아니다. 자격 심사에 시간이 걸리는 상품이 있고 승인 전에는 시험할 수 있는 범위가 좁아지므로, 개발 일정을 잡기 전에 확인해야 한다. 방법은 상품 문서에서 대상 고객과 신청 조건을 확인하고, 구현 계획에 신청할 계정, 승인 대상 기능과 실제로 허용받은 작업을 기록하는 것이다. 아래 사례는 이런 차이가 개발 일정과 시험 범위에 영향을 주는 경우다.

Compliance Engine은 거래와 주소의 위험을 심사하는 서비스다. [개요](https://developers.circle.com/wallets/compliance-engine.md)는 테스트넷과 메인넷 모두 적격 고객에게만 제공한다고 설명한다. API 키를 만들고 테스트넷을 선택하는 일만으로 서비스 접근이 완료되지 않는다.

공식 문서는 USYC를 단기 미국 국채를 기초로 하는 토큰화 머니마켓 펀드의 지분을 나타내는 수익형 토큰으로 설명한다. 일반 지갑의 공개 전송과 USYC의 구독 및 상환 자격은 구분한다. [계약 주소 안내](https://docs.arc.io/arc/references/contract-addresses.md)는 미국 밖의 기관만 USYC를 이용할 수 있고 자격 제한과 최소 100,000달러 투자 조건이 있다고 적는다. 테스트넷에서는 시험 USDC를 받은 뒤 Circle Support에 지갑 주소와 함께 허용 목록 등록을 요청하고, 승인 후 Teller 계약이나 USYC Portal로 USDC를 예치해 시험 USYC를 받는다. 등록 요청은 통상 24-48시간에 처리한다고 안내한다. 이는 문서의 조건과 통상 소요이며 사용자 승인이나 처리 기한의 확약은 아니다. 기관 외환 StableFX와 금융기관 지급 CPN의 승인 및 자금 조건도 기업 업무 설명에서 따로 다룬다.

경로를 정했다면 그 경로에 필요한 준비물을 갖추고, 같은 실행을 반복할 수 있도록 환경을 고정해야 한다. 네트워크 설정과 도구 및 자산 단위가 달라지면 성공과 실패의 기록도 다른 뜻을 갖는다. 2절(준비물)은 그 준비를 차례로 설명한다.

## 2. 준비물: 첫 요청을 보내기 전에 무엇을 갖추고 서로 맞춰야 하는가

1절(구현 경로)에서 경로를 골랐다면, 첫 요청을 보내기 전에 갖춰야 할 것은 다섯 가지다. 연결할 네트워크, 개발 도구, 가스와 시험 전송에 쓸 테스트넷 USDC, Circle 서비스를 쓴다면 API 키, 그리고 결과를 확인할 시험 환경이다. 이들을 먼저 맞춰야 하는 이유는 하나라도 서로 어긋나면 같은 실행의 결과가 다른 뜻을 갖기 때문이다. 예를 들어 앱과 지갑이 다른 체인을 가리키면 다른 환경을 조회하거나 실행하고, 금액 단위가 어긋나면 의도한 금액과 실행 금액이 달라진다. 아래 대조표는 항목마다 서로 맞출 대상과 확인 자료를 적었고, 2.1-2.5는 같은 순서로 준비 방법을 설명한다. 직접 체인 호출만 쓴다면 2.4(서비스 계정)는 건너뛰어도 된다. Ethereum에서 쓰던 계약을 Arc에 올린다면 2.6(기존 계약 점검)에서 그 계약이 쓰는 기능의 가정도 확인한다.

**준비물 대조표: 한 행은 서로 맞춰야 할 준비 항목이다.**

| 항목        | 서로 맞출 대상                             | 확인 자료                       | 불일치가 미치는 영향                                                           |
| ----------- | ------------------------------------------ | ------------------------------- | ------------------------------------------------------------------------------ |
| 네트워크    | 앱 접속 대상, 지갑의 서명 대상과 계약 주소 | 체인 식별자와 주소              | 다른 환경을 조회하거나 실행한다.                                               |
| 개발 도구   | 코드, 설치 버전과 연결 구성                | 커밋과 lockfile, 실제 버전      | 예제와 실제 인터페이스가 달라진다.                                             |
| 시험 자금   | 입력 정수, 호출 인터페이스와 화면 표시     | 단위와 변환 규칙                | 의도한 금액과 실행 금액이 달라진다.                                            |
| 서비스 계정 | API 키의 환경과 요청할 환경                | 키의 종류(테스트넷 또는 메인넷) | 키가 없으면 요청이 실패하고, 다른 환경의 키로는 의도한 환경을 시험하지 못한다. |
| 시험 환경   | 검증 질문과 시험 대상                      | 시험 환경과 실행 조건           | 결과를 적용할 수 있는 범위를 잘못 판단한다.                                    |

### 2.1 네트워크: 앱, 지갑과 계약이 같은 체인을 가리키도록 chain ID와 RPC 주소를 맞춘다

개발자에게 필요한 것은 앱이 조회하는 체인, 지갑이 서명하는 체인과 계약이 배포된 체인이 모두 같다는 확인이다. 셋이 어긋나면 다른 환경의 상태를 읽거나 다른 환경에 거래를 보내게 된다. 방법은 연결할 네트워크의 chain ID와 RPC 주소를 공식 연결 문서에서 확인해 앱과 지갑 설정에 넣고, 실제 RPC에서 읽은 chain ID를 그 값과 대조하는 것이다. 개발 환경에서 동작한 결과를 제출 환경으로 옮길 때에는 주소를 복사하는 것보다 그 주소의 코드와 자산 및 접근 조건을 다시 확인하는 것이 중요하다. 나는 이 원고에서 환경 전환을 설정 변경과 해당 환경의 재검증을 함께 수행하는 작업으로 다룬다. 아래 연결 설정과 공고 조건은 각각 실제 접속 대상과 사용할 환경을 확인하는 기준이다.

[연결 문서](https://docs.arc.io/arc/references/connect-to-arc.md)는 Arc 메인넷의 chain ID를 5042, 테스트넷을 5042002로 적고 각각 `https://rpc.mainnet.arc.io`와 `https://rpc.testnet.arc.io`를 안내한다. 같은 주소라도 환경별 자산과 상태를 확인한다. 앱의 실제 RPC에서 `eth_chainId`를 읽고 지갑의 서명 대상 및 계약 주소와 맞춘다. 일부 자산 및 계약의 주소가 같다는 사실에서 모든 주소가 같다고 추론하지 않는다.

[RPC endpoints](https://docs.arc.io/arc/references/rpc-endpoints.md)는 Circle의 기본 메인넷과 테스트넷에 HTTP 및 WebSocket 주소를 모두 나열한다. 메인넷은 `https://rpc.mainnet.arc.io`와 `wss://rpc.mainnet.arc.io`, 테스트넷은 `https://rpc.testnet.arc.io`와 `wss://rpc.testnet.arc.io`다. 이 표의 주소 안내와 실제 접속 및 구독 성공은 구분한다. 구 도메인이나 다른 공급자로 바꿀 때에는 읽기 및 구독과 제출의 지원, 키와 이용 한도 및 오류를 해당 제공자에서 다시 확인한다.

제출 환경을 메인넷의 동의어로 쓰지 않는다. 테스트넷을 허용하는 프로그램도 있고 메인넷의 작동 결과물을 요구하는 프로그램도 있으므로 먼저 선택 공고가 평가할 대상을 확인한다. 접수, 제출과 선정 및 지급 조건을 기술 접근의 순서로 바꾸지 않는다.

### 2.2 개발 도구: Arc Foundry와 App Kit를 설치하고 실제로 쓴 버전을 기록한다

경로에 따라 필요한 개발 도구가 다르다. 직접 체인 호출에는 Solidity, Foundry, Hardhat, Viem과 ethers.js 같은 표준 Ethereum 도구를 사용할 수 있다. [EVM differences](https://docs.arc.io/arc/references/evm-differences.md)는 대부분의 기존 계약을 변경 없이 배포할 수 있다고 설명한다. Arc의 프리컴파일과 실행 차이를 로컬에서 재현하려면 Arc Foundry를 사용한다. Circle 서비스를 쓰려면 선택한 기능에 맞는 App Kit와 어댑터가 필요하며, 사용자 지갑을 화면에 연결하려면 지갑 연결 설정도 필요하다. 설치만큼 중요한 것은 실제로 쓴 버전의 기록이다. 같은 기능 이름을 사용해도 실제 설치 버전이나 어댑터가 다르면 입력과 반환값을 다시 확인해야 하므로, 재현하려면 패키지 이름뿐 아니라 호출한 인터페이스, 사용한 어댑터와 지갑 연결 설정이 함께 있어야 한다. 따라서 아래 설치 절차, 실제 설치 상태의 기록과 인터페이스 대조를 하나의 준비 과정으로 묶는다.

Arc Foundry는 Arc의 프리컴파일(precompile, 지정 주소에서 노드가 처리하는 기능)과 프로토콜 차이를 반영한 Foundry 도구다. [설치 안내](https://docs.arc.io/arc/tutorials/install-arc-foundry.md)는 플랫폼에 맞는 릴리스와 `arc-forge`, `arc-cast` 및 `arc-anvil`의 버전 확인을 설명한다. 이 설치 절차는 2026-10-07 실험에서 실행했고, 결과는 아래 절차 다음 문단에 적었다.

실험 관측: Arc Foundry는 [설치 안내](https://docs.arc.io/arc/tutorials/install-arc-foundry.md)에 따라 릴리스 페이지에서 플랫폼에 맞는 압축 파일을 내려받는다. 미리 빌드된 바이너리는 Linux(x86_64, arm64), Apple Silicon macOS와 WSL을 쓰는 Windows용이 있고, Intel Mac은 소스에서 빌드한다. 압축을 풀어 `forge`, `cast`, `anvil`을 `PATH`에 있는 디렉터리로 옮기면서 `arc-forge`, `arc-cast`, `arc-anvil`로 이름을 바꾸고, `arc-forge --version`으로 설치를 확인한다(공식 영문판의 Steps 절). 실험 관측: App Kit는 [설치 안내](https://docs.arc.io/app-kit/tutorials/installation.md)에 따라 모든 기능이 든 `@circle-fin/app-kit`를 설치하거나 필요한 kit만 따로 설치한 뒤, 사용할 지갑에 맞는 어댑터(Viem, Ethers, Solana 또는 서버 전용 Circle Wallets)를 함께 설치한다(공식 영문판의 패키지 및 어댑터 설치 절).

2026-10-07 실험에서는 Apple Silicon macOS에서 두 설치를 실행했다. Arc Foundry는 릴리스 v0.8.0-2의 압축 파일을 내려받아 릴리스에 함께 올라온 `.sha256` 값과 대조했고, 시스템의 `PATH`를 바꾸지 않으려고 문서의 `~/.local/bin` 대신 별도 디렉터리에 두었다. 세 도구는 모두 버전 `1.7.1-dev`와 커밋 `d497beea`를 보고했다. App Kit는 Node v22.20.0에서 `npm install --ignore-scripts --save-exact`로 `@circle-fin/app-kit`, `@circle-fin/adapter-ethers-v6`와 `ethers`를 설치했고, lockfile에 적힌 버전은 각각 1.16.0, 1.12.1과 6.17.0이었다. `--ignore-scripts` 때문에 의존 패키지 세 곳의 설치 스크립트는 실행되지 않았지만 설치는 끝났다. `npm audit`은 하위 의존성의 문제 28건(low 8, moderate 11, high 9)을 보고했다. App Kit의 Send 기능은 실행하지 않았다. 아래 문단이 말하는 버전 기록은 이 실험에서 이런 형태로 남겼다.

"최신 버전"이라는 표현은 실행한 버전을 재현하지 못한다. 결과에는 저장소 커밋과 lockfile, 실제 설치한 SDK 및 어댑터와 Node, Solidity compiler 및 Arc Foundry의 버전을 남긴다. 문서의 버전 표와 package.json의 범위는 실제 설치 결과와 다르다. 예를 들어 `^1.15.1`은 특정 설치 버전 하나를 뜻하지 않는다.

ChatGPT 답변은 arc-fintech와 arc-commerce의 서로 다른 의존 버전을 보고했다. 이 리서치에서 두 저장소의 현행 파일과 설치 결과를 직접 검증하지 않았으므로 그 수치를 표준 실행 환경으로 채택하지 않는다. 그 세부 값은 6.4(미확인 사항)의 보류 표에 남긴다. 현재 Onramp quickstart가 요구하는 Node v22+와 다른 지갑 quickstart의 전제도 선택한 예제별로 확인해야 한다.

지갑 연결 도구도 이름이 비슷하다고 합치지 않는다. Reown AppKit은 사용자 지갑 연결을 구성하는 도구이며 Circle의 Arc App Kit는 위 결제 기능을 묶는 SDK다. 연결 문서는 viem의 `arc`와 `arcTestnet`, ConnectKit 및 WalletConnect와 Reown의 설정 예제를 설명한다. Reown 예제는 `defineChain`을 `@reown/appkit/networks`에서 가져와 `caipNetworkId`와 `chainNamespace`를 포함하도록 안내한다. 문서의 안내를 읽은 것이며 UI를 실행한 결과는 아니다.

[Connect to Arc](https://docs.arc.io/arc/references/connect-to-arc.md)는 ConnectKit 설정에 Arc 외에 `mainnet`도 포함해 ENS 조회가 올바른 Ethereum RPC를 사용하도록 안내한다. Arc 체인만 설정하면 ENS 조회가 CORS를 차단하는 RPC로 향할 수 있다. Arc Testnet은 WalletConnect의 사전 등록 체인 목록에 없으므로 첫 연결에서 `wallet_addEthereumChain`을 호출해 추가하도록 안내한다. 이는 문서의 설정 지침이며 이번에 지갑 UI를 실행한 결과는 아니다.

AI 도구를 이용하는 개발 경로도 있다. [Arc Studio](https://docs.arc.io/ai/arc-studio.md)는 자연어로 스마트 계약과 프런트엔드를 만들고 배포 및 미리보기를 제공하는 개발 환경이다. 공식 문서는 생성한 프로젝트를 GitHub로 내보낼 수 있다고 설명한다. 배포 대상은 Arc 테스트넷이며 메인넷 배포 결과로 해석하지 않는다.

공식 글 연결: [Arc Studio: Build Onchain Apps and Agents With AI in Minutes](https://www.arc.io/blog/introducing-arc-studio-the-onchain-coding-agent) (2026-09-17, [공식 원문](https://www.arc.io/blog/introducing-arc-studio-the-onchain-coding-agent)). Studio 소개의 고지는 도구가 사용자를 대신해 메인넷 배포, 서명, 자금 공급이나 거래 제출을 하지 않는다고 명시한다. 코드를 내보내 자기 자격증명으로 운영하는 경우와 구별한다.

미실행 항목: [Arc Studio CLI](https://docs.arc.io/ai/arc-studio-cli.md)는 Node.js 20 이상을 요구한다. `npm install -g @circle-fin/arc-studio-cli`로 설치하고 `arc-studio login`으로 브라우저 device-link 인증을 한 뒤, `arc-studio whoami`로 계정을 확인한다. 프롬프트와 파일을 서버에 보내면 에이전트, 모델 추론, 계약 처리와 sandbox는 서버에서 실행되고 CLI는 배포 주소, 변경 내용과 미리보기를 받는다. `arc-studio run ... --output json`의 결과는 `status`, `deployments`, `fileDiffs`, `previewUrl` 등을 포함한다. 문서는 이 결과를 검증된 사실로 취급하지 말고 주소와 변경 내용을 확인하도록 안내한다. `arc-studio pull`은 로컬에서 수정한 파일을 건너뛰며, 인증 토큰은 macOS Keychain 또는 다른 플랫폼의 권한이 제한된 자격증명 파일에 보관한다. 설치와 인증 및 서버 실행은 이번에 수행하지 않았다.

미실행 항목: [Circle Skills](https://docs.arc.io/ai/skills.md)는 `circlefin/skills`의 공개 스킬을 AI 개발 도구에 설치하는 방법을 안내한다. `npx skills add circlefin/skills`로 설치할 수 있고, 체인 설정, 지갑, USDC, CCTP와 계약 개발 등을 다룬다. [Arc MCP server](https://docs.arc.io/ai/mcp.md)는 인증 없이 `https://docs.arc.io/mcp`에 접속해 문서 Search와 Get page를 제공한다. Claude Code의 문서 예제는 `claude mcp add --transport http arc-docs https://docs.arc.io/mcp`다. MCP는 관련 문서 검색과 전체 페이지 조회를 제공하는 도구이며 거래 배포의 실행 결과를 제공하는 도구가 아니다. 이 설치 및 연결 명령은 안내로만 기록했다.

### 2.3 시험 자금: 테스트넷 USDC를 받고 가스와 전송 금액의 단위를 맞춘다

실험 관측: 가스와 시험 전송에 쓸 테스트넷 USDC는 Circle Faucet에서 받는다. [배포 안내](https://docs.arc.io/build/deploy-on-arc.md)는 Faucet에서 Arc Testnet을 고르고 지갑 주소를 넣어 테스트넷 USDC를 요청하라고 안내하며, Arc는 가스를 USDC로 내므로 이 잔액이 배포 수수료를 충당한다고 설명한다(공식 영문판의 Fund your wallet 절). 테스트넷 USDC는 시험용이며 운영 환경에서 쓸 수 없다(같은 절의 테스트넷 자금 조건). 2026-10-07 실험에서는 Faucet에 한 번 요청해 20 USDC를 받았다. 요청 간격은 한 번만 요청했으므로 확인하지 못했고, Grok 답변이 옮긴 Faucet 화면의 문구(2시간마다 20 USDC)는 6.4(미확인 사항)의 보류 표에 있다. 자금을 받은 다음에는 금액의 단위를 맞춘다. Arc의 USDC는 같은 잔액을 두 가지 소수 자릿수로 표현하므로, 단위를 맞추지 않으면 의도한 금액과 실행 금액이 달라진다.

Arc의 네이티브 USDC와 ERC-20 USDC는 같은 잔액을 서로 다른 소수 자릿수로 표현한다. 네이티브 `value`와 `eth_getBalance`는 18자리, ERC-20 인터페이스는 6자리 소수를 사용한다. 두 잔액을 합산하거나 화면에 별도 자산으로 표시하지 않는다. [계약 주소의 USDC 설명](https://docs.arc.io/arc/references/contract-addresses.md)에 따르면 ERC-20 인터페이스는 같은 native 잔액에 대해 `transfer`, `approve`와 `transferFrom`을 제공하므로 WETH 방식의 래핑이나 별도 wrapped USDC 주소가 필요하지 않다. 지갑이 가스 자산을 ETH로 잘못 표시하는 경우도 있다는 연결 문서의 고지는 실제 자산과 화면 표기를 구별하게 한다.

공식 글 연결: [Compatibility Guide for EVM Apps on Arc](https://www.arc.io/blog/arc-compatibility-guide-for-existing-evm-apps) (2026-09-10, [공식 원문](https://www.arc.io/blog/arc-compatibility-guide-for-existing-evm-apps)). 호환성 안내는 두 조회 결과를 합산하면 같은 USDC를 이중 계산한다고 설명한다. 지갑 표시의 기준과 앱의 ERC-20 호출은 사용 목적을 나누어 읽는다.

두 표현은 같은 기초 잔액을 나타낸다. 소수 18자리의 네이티브 잔액을 10^12로 나누고 소수점 아래를 버리면 소수 6자리의 ERC-20 조회값이 된다. 따라서 ERC-20 조회에 보이지 않는 소액도 네이티브 잔액에는 남을 수 있다. 개발자는 입력할 정수, 같은 블록의 비교와 문서 예제의 단위를 함께 확인해야 한다. [EVM differences, USDC 단위](https://docs.arc.io/arc/references/evm-differences.md)

2026-10-07 실험에서 같은 블록(65952222)의 두 표현을 읽었다. 시험 지갑의 `eth_getBalance`는 20000000000000000000이었고, USDC 계약 `0x3600...0000`의 `balanceOf`는 20000000, `decimals()`는 6이었다. 18자리로 읽어도 6자리로 읽어도 20 USDC이며, floor(20000000000000000000 / 10^12) = 20000000으로 위 변환 규칙과 맞았다.

시험에서는 같은 주소와 같은 블록을 사용한다. 서로 다른 시점의 잔액을 비교하면 그 사이의 가스 및 전송을 단위 차이로 잘못 설명할 수 있다. 네이티브 전송의 1 USDC는 10^18 정수, ERC-20 전송은 10^6 정수를 입력한다. 기존 [가스 문서](https://docs.arc.io/arc/references/gas-and-fees.md)의 native send 예제에 적힌 `parseUnits("1", 6)`은 18자리 규칙에서 10^6 / 10^18 = 10^-12 USDC이므로 주석의 1 USDC와 맞지 않는다. 문서의 코드도 단위와 대조해야 한다. 2026-10-07 실험에서 이 예제는 실제로 10^-12 USDC를 보냈다(4.2(체인 실행)).

### 2.4 서비스 계정: Circle 서비스를 쓰려면 API 키를 발급받고 환경별로 나눈다

Circle 서비스(지갑 API, Onramp와 App Kit의 일부 기능 등)를 쓰려면 API 키가 필요하다. [키 문서](https://developers.circle.com/api-reference/keys.md)는 API 키가 Circle API의 권한 있는 작업에 접근하는 데 쓰이며, Circle 서비스에 보내는 REST API 요청에 필요하고 키가 없으면 요청이 실패한다고 설명한다. 어떤 기능이 키를 요구하는지는 1.2(Circle 서비스)의 표에 있다. 실험 관측: 키는 Circle Console에서 발급하고 관리하며, 발급할 때 표시된 그대로 복사한다. 키는 클라이언트 코드나 공개 저장소에 넣지 않는다. 요청에는 `authorization: Bearer <API_KEY>` 헤더를 넣고, 테스트넷 키(예시가 `TEST_API_KEY:`로 시작한다)와 메인넷 키(`LIVE_API_KEY:`)를 따로 쓴다. 설정을 확인하려면 문서의 `curl` 예제로 지갑 목록(`GET https://api.circle.com/v1/w3s/wallets`)을 조회한다. 성공하면 `wallets` 배열을 받고, 인증 형식이 틀리면 401 오류를 받는다. 키의 종류와 역할은 3.1(승인 주체)에서 설명한다. 개발자 제어 지갑을 쓴다면 entity secret도 등록해야 하지만, 등록 절차 자체는 캡처한 문서에 없다. [entity secret 문서](https://developers.circle.com/wallets/dev-controlled/entity-secret-management.md)는 등록하면 복구 파일이 생긴다고만 적으므로 이 단계는 빈칸으로 두고, entity secret의 보관은 3.2(비밀 관리)에서 설명한다.

2026-10-07 실험에서는 Circle Console의 테스트넷 모드에서 Standard 키를 만들었고, 키는 문서의 예시처럼 `TEST_API_KEY:`로 시작했다. 이 키로 보낸 문서의 확인 명령(지갑 목록 조회)은 HTTP 200과 빈 목록 `{"data":{"wallets":[]}}`를 받았다. 형식은 맞지만 발급받지 않은 가짜 키로 보낸 같은 요청은 HTTP 401과 "Invalid credentials."를 받았다. 문서가 401을 예로 든 경우는 인증 형식이 틀린 요청이므로, 이 응답과는 입력 조건이 다르다.

### 2.5 시험 환경: 계약 논리, Arc fork, 공개 체인과 서비스를 따로 시험한다

개발자에게 필요한 것은 확인하려는 질문에 맞는 시험 환경이다. 시험 환경에 따라 확인할 수 있는 질문이 달라지기 때문이다. 계약의 입력 검사와 상태 변경을 확인하는 질문에는 계약 논리의 시험이 필요하고, Arc의 자산 표현과 차단 동작을 확인하는 질문에는 그 차이를 반영하는 환경이 필요하다. 공개 RPC를 통한 제출과 서비스의 승인 및 완료를 확인하려면 해당 외부 경로의 관측이 추가로 필요하다. 앞의 시험이 뒤의 시험을 자동으로 포함하지 않으므로, 질문마다 시험 환경을 고르고 결과를 기록할 때 사용 환경과 적용 가능한 결론을 함께 적는다. Arc Foundry의 설치는 2.2(개발 도구)에서 다뤘고, 아래는 그 도구로 Arc의 상태를 재현하는 방법이다.

[문제 재현 안내](https://docs.arc.io/arc/tutorials/troubleshoot-with-arc-foundry.md)는 포함된 거래의 `arc-cast run`, 고정 블록의 fork 및 `arc-forge test`를 설명한다. fork는 외부 체인 상태의 특정 시점을 가져와 로컬에서 시험하는 방식이다. 표준 Anvil의 일반 계약 시험이 Arc의 네이티브 USDC와 차단 동작까지 재현하는 것은 아니라고 안내한다.

따라서 일반 계약 논리, Arc fork의 상태, 공개 체인의 포함과 확정 및 서비스의 승인과 완료를 별도 시험으로 기록한다. fork에서 계정을 대신 사용해 통과한 시험은 공개 체인의 실제 서명 권한을 확보했다는 뜻이 아니다. 문서에 인쇄된 PASS와 가스 사용량도 이번 관측값이 아니다. 기존 계약을 Arc에 올린다면, 시험 환경을 정한 다음 2.6(기존 계약 점검)에서 그 계약의 가정을 확인한다.

### 2.6 기존 계약 점검: Ethereum에서 쓰던 계약을 Arc에 올리기 전에 계약이 쓰는 기능의 가정을 Arc의 차이와 대조한다

Ethereum에서 쓰던 계약을 Arc에 올리려면, 그 계약이 쓰는 기능마다 기능이 전제한 동작이 Arc에서도 같은지 먼저 확인해야 한다. Arc의 호환성 안내는 기존 계약과 도구를 그대로 쓸 수 있다고 설명하지만, 네이티브 자산, 일부 명령어의 반환 값과 블록 정보, 수수료와 이벤트의 동작은 Ethereum과 다르기 때문이다. [EVM differences](https://docs.arc.io/arc/references/evm-differences.md)는 네이티브 USDC, 실행 명령어, 자산 이전, 로그와 수수료의 차이를 설명한다. 이 차이를 기존 계약 전체에 일괄 적용하지 않고, 계약이 실제로 쓰는 기능마다 가정과 사양을 대조한다. 아래 그림이 그 점검 순서다.

공식 글 연결: [Compatibility Guide for EVM Apps on Arc](https://www.arc.io/blog/arc-compatibility-guide-for-existing-evm-apps) (2026-09-10, [공식 원문](https://www.arc.io/blog/arc-compatibility-guide-for-existing-evm-apps)). 호환성 글도 네이티브 자산과 이벤트를 Ethereum처럼 가정하는 코드를 점검 대상으로 제시한다. 개별 명령어와 이벤트 예외는 상세 사양의 조건을 유지한다.

**계약의 실행 가정을 검토하는 순서**

한국어:

```text
[사용한 도구와 배포 환경 확인]
 어떤 도구를 재사용할 수 있는가?
    |
    v
[계약이 사용한 기능 확인]
 명령어 / 거래 유형 / 시각 / 난수 관련 가정은?
    |
    v
[금액과 기록의 해석 확인]
 네이티브 값 / ERC-20 값 / 영수증 / 로그를 어떻게 읽는가?
    |
    v
[자산 이전과 실패 조건 확인]
 대상 주소와 자산 정책에 따라 무엇이 실패할 수 있는가?
    |
    v
[시험 환경의 대응 확인]
 시험 환경이 Arc의 차이를 실제로 재현하는가?
    |
    v
[사용한 기능별로 결과 기록]
 확인한 동작과 아직 시험하지 않은 동작을 구분한다.
```

English:

```text
[Check tools and deployment environment]
 Which tools can be reused?
    |
    v
[Check the features used by the contract]
 What assumptions involve opcodes, transaction types, time and randomness?
    |
    v
[Check interpretation of amounts and records]
 How are native values, ERC-20 values, receipts and logs read?
    |
    v
[Check asset transfer and failure conditions]
 What can fail because of destination addresses and asset policies?
    |
    v
[Check test environment correspondence]
 Does the test environment actually reproduce Arc's differences?
    |
    v
[Record results for each feature used]
 Distinguish checked behavior from behavior not yet tested.
```

그림의 순서는 공식 EVM 차이를 내가 연결한 검토 순서이며 프로토콜의 실행 순서는 아니다. 금액 단위와 수수료 및 로그, 실행 환경과 계약 동작을 [EVM differences](https://docs.arc.io/arc/references/evm-differences.md)와 대조한다. 시험 환경에서 Arc 고유 동작을 재현하는 방법은 이 문서의 2.5(시험 환경)에서 설명한다.

공식 [Port a contract to Arc](https://docs.arc.io/arc/tutorials/porting-contracts-to-arc.md)는 대부분의 Ethereum 계약이 변경 없이 배포되고 실행되지만, native 가스 자산이 USDC이고 native 및 ERC-20 USDC가 같은 자산이라는 점에서 주의할 경우가 생긴다고 설명한다. 아래 표는 그 안내의 점검 항목을 기존 그림의 단계에 연결한 것이다. 아직 해당 계약들을 실행 시험한 결과는 아니다.

| 공식 점검 항목     | 기존 계약에서 확인할 내용                                                                                                                                                                                                        |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 잔액과 소수 자릿수 | `balanceOf`와 `address.balance`를 비교하거나 합치는 위치를 찾고 6자리와 18자리의 단위를 변환한다. ERC-20 조회는 소수 부분을 절삭하므로 0이라고 native 잔액도 0인 것은 아니다.                                                    |
| native value 전송  | native 전송과 value를 전달하는 경로를 찾는다. 잔액이 충분해도 영 주소, 차단 주소나 금지된 burn 때문에 revert할 수 있다.                                                                                                          |
| 승인과 sweep       | `USDC.approve`는 `transferFrom`만 제한한다. 같은 계약이 native USDC를 보내는 경로까지 allowance가 제한하지 않는다. native 잔액의 sweep도 사용자의 ERC-20 USDC 잔액을 이동시킨다.                                                 |
| DEX, AMM과 router  | 별도 WUSDC를 만들지 않고 USDC ERC-20 주소를 사용한다. WETH식 `deposit()`과 `withdraw()` 경로를 대조하고 `msg.value`의 18자리와 ERC-20의 6자리를 구분한다. native 자산 sentinel을 USDC ERC-20 주소와 같은 값으로 취급하지 않는다. |
| SELFDESTRUCT       | 계약의 native USDC가 수익자에게 이동한다. 자기 자신과 영 주소, 차단되거나 이미 self-destruct된 주소로 보내는 금지 조건을 확인한다.                                                                                               |
| 난수와 실행 환경   | `PREVRANDAO`는 0을 반환하므로 VRF나 난수 oracle로 대체한다. Arc Foundry의 `arc-anvil --network arc`와 `arc-forge test`를 사용하고, fork 전환이나 실제 거래 순서는 테스트넷에서 확인한다.                                         |
| revert 경로        | 문서의 테스트용 차단 주소를 사용해 native 전송과 SELFDESTRUCT 수익자의 실패를 처리하는지 확인한다.                                                                                                                               |

구체적인 opcode와 블록 정보의 차이는 [EVM differences](https://docs.arc.io/arc/references/evm-differences.md)를 함께 대조한다. 해당 문서는 Arc의 기준을 Osaka hard fork로 설명하며 EIP-7702, EIP-7708과 블록 시각 등의 조건을 구분한다. 위 점검표는 사용한 기능에 적용하며, 쓰지 않는 기능의 차이를 계약 전체의 결함으로 확대하지 않는다.

점검 결과는 기능별로 남기는 편이 정확하다. 계약이 난수 관련 명령어를 쓰지 않는다면 해당 차이만으로 그 계약에 문제가 있다고 판단하지 않는다. 반면 자산 이전이나 잔액 계산을 사용한다면 호출이 성공하는지뿐 아니라 단위, 비용과 반환 결과까지 맞는지 확인해야 한다. 표준 로컬 시험을 통과했다는 결과도 그 환경이 Arc의 차이를 재현하는지 확인한 뒤 해석해야 한다. 점검을 마쳤다면 누가 요청을 승인하고 어떤 행동을 제한하는지 구성한다.

## 3. 실행 권한: 누가 요청을 인증하고 거래에 서명하며, 자산 지출을 어디에서 제한하는가

준비를 마쳤다면 다음으로 정할 것은 실행 권한이다. 누가 서비스에 요청할 수 있는지, 누가 거래에 서명하는지, 그리고 자산 지출을 어디에서 제한하는지다. 이것을 먼저 정해야 하는 이유는 권한이 곧 누가 어떤 자산을 움직일 수 있는지를 정하기 때문이다. 요청을 보낼 수 있다는 사실과 자산을 지출할 수 있다는 사실은 다르고, 한 통제가 거절해도 다른 경로로 같은 자산이 움직일 수 있다. 아래 관계도는 요청 경로별 통제 지점과 관리 항목을 보여 준다. 3.1(승인 주체)과 3.2(비밀 관리)는 인증과 서명의 자격증명을, 3.3(지출 한도)과 3.4(가스 대납)는 자산과 수수료의 한도를, 3.5(위험 통제)는 서비스와 체인의 차단을 다룬다.

**권한 관계도: 요청 경로별 통제 지점과 관리 항목**

상단은 선택 경로의 통제 지점이며 하단은 해당 지점에 적용할 관리 항목이다. 서비스 내부에서 체인을 호출하는 구체적인 연결은 선택 서비스별로 확인한다.

한국어:

```text
[앱: 입력과 자체 정책]
          |
          +----------------------------+
          |                            |
          v                            v
[서명자: 거래 승인]           [서비스: 인증과 작업 승인]
          |                            |
          v                            v
[체인: 계약 권한과 실행 조건]  [서비스의 실제 처리 경로]
          |                            |
          +-------------+--------------+
                        |
                        v
                  [대상 작업의 효과]

[비밀 관리] ------> 해당 서명/인증/승인 구성
[가스 대납 정책] -> 해당 실행의 수수료 부담
[위험 통제] ------> 적용되는 서비스 또는 체인 처리
```

English:

```text
[App: input and application policy]
                 |
                 +-----------------------------+
                 |                             |
                 v                             v
[Signer: transaction approval] [Service: authentication and authorization]
                 |                             |
                 v                             v
[Chain: permissions and conditions] [Actual service processing path]
                 |                             |
                 +--------------+--------------+
                                |
                                v
                      [Effects of the target operation]

[Secret management] ---> Relevant signing/authentication/authorization
[Gas sponsorship] -----> Fee payment for the relevant execution
[Risk controls] -------> Applicable service or chain processing
```

### 3.1 승인 주체: 서비스 요청의 인증과 거래 서명은 서로 다른 자격증명이 맡는다

개발자는 서비스에 요청을 보낼 수 있는 계정과 자산 이동을 승인하는 주체를 따로 정해야 한다. 요청 인증은 서비스가 호출자를 식별하는 관계이고 거래 서명은 특정 거래를 승인하는 관계라서, 같은 서버가 두 역할을 수행하더라도 자격증명의 용도와 허용 범위가 다르기 때문이다. 정하는 방법은 사용할 지갑 모형(직접 EOA, 개발자 제어, 사용자 제어, 모듈형)을 고르고, 그 모형에서 어느 단계에 사용자 승인이 필요한지, 서버가 어떤 작업을 대신 승인할 수 있는지, 승인에 실패하면 어디에서 멈추는지를 적는 것이다. 아래 문단은 지갑 모형별 서명 주체와 키의 종류, 그리고 각 자격증명을 둘 위치를 설명한다.

직접 EOA에서는 서명자가 개인 키로 거래를 승인한다. [Circle의 승인 모형](https://developers.circle.com/wallets/signing-and-authorization-models.md)은 개발자 제어, 사용자 제어와 모듈형 지갑을 구별한다. 개발자 제어 지갑은 서버의 승인, 사용자 제어 지갑은 사용자의 승인, 모듈형 지갑은 선택한 계약과 passkey 및 복구 구성을 확인한다. MPC(Multi-Party Computation)는 여러 참여자가 비밀 정보를 나누어 연산하는 기술이며, 승인 API와 실제 서명 구조 및 복구가 같은 권한은 아니다.

서버 API key는 서비스 요청을 인증한다. client key는 웹 도메인이나 모바일 앱에 결합된 클라이언트용 자격증명이다. 기존 kit key는 legacy로 새 생성이 불가능하고 기존 키는 계속 작동한다고 [키 문서](https://developers.circle.com/api-reference/keys.md)가 안내한다. 신규 API 키는 테스트와 운영 환경을 분리한다. 모든 SDK 인증값을 하나의 공개 키 또는 하나의 서버 비밀로 분류하지 않는다.

서버 개인 키와 API 비밀 및 entity secret을 브라우저 번들, 저장소와 일반 로그에 넣지 않는다. 사용자 자신의 브라우저 지갑 서명과 도메인에 결합된 클라이언트 SDK 키는 사용하는 모형의 조건에서 다룬다. 직접 서명자, 비밀 관리 서비스나 HSM(Hardware Security Module, 키를 보호하는 하드웨어)의 선택은 보관 위치와 승인 권한 및 복구 요구를 함께 정해야 한다.

[Post-quantum security](https://docs.arc.io/arc/concepts/post-quantum-security.md)는 Arc 메인넷에서 `SLH-DSA-SHA2-128s` 서명 검증을 지원한다고 설명하면서 native 지갑의 거래 서명은 미래의 단계로 구분한다. 계약은 메시지, 공개 키와 서명을 calldata로 받아 검증하고 상태 변경의 승인 조건으로 사용할 수 있다. 이 문서의 검증 기능을 기존 EOA 거래 서명이 이미 양자내성(post-quantum) 방식으로 바뀌었다는 뜻으로 쓰지 않는다. 이번 작업에서는 해당 검증을 실행하지 않았다.

### 3.2 비밀 관리: entity secret과 요청 암호문, 복구 파일을 보관하고 교체한다

개발자 제어 지갑을 쓰는 개발자에게는 API 키 외에 entity secret이 필요하다. [entity secret 문서](https://developers.circle.com/wallets/dev-controlled/entity-secret-management.md)는 API 키가 요청을 인증하고 entity secret은 그 요청이 수행하는 지갑 작업을 승인한다고 구별한다. Circle은 이 비밀의 사본을 보관하지 않으므로, 복구 파일 없이 잃으면 지갑과 자금에 영구히 접근할 수 없다. 미실행 항목: 관리 방법은 세 가지다. 비밀은 비밀 관리 서비스, HSM이나 암호화된 비밀번호 관리자에 보관하고 저장소, 설정 파일과 로그에 넣지 않는다. 등록할 때 한 번만 내려받을 수 있는 복구 파일을 바로 저장해 비밀과 다른 곳에 둔다. 비밀은 정기적으로 교체하고(문서의 예는 180일마다), 교체나 재설정 뒤에는 새 복구 파일로 덮어쓴다. 아래 관계도와 문단은 비밀, 요청 암호문과 복구 파일의 관계를 설명한다.

**비밀 관리 관계도: 개발자 제어 지갑의 승인과 복구**

화살표는 생성, 요청 전달과 복구의 관계이며 자산 이동이 아니다. 복구 파일의 교체와 무효화 조건은 아래 본문에 따른다.

한국어:

```text
[API key] ------------------------------> [서비스 요청 인증]

[entity secret] --+
                  |
                  v
           [요청별 암호화] -> [새 요청 암호문] -> [민감한 작업 승인 요청]
                  ^
                  |
       [Circle의 공개 RSA 키]

[별도 보관한 복구 파일] -> [분실 후 재설정] -> [새 entity secret]
```

English:

```text
[API key] ------------------------------> [Service request authentication]

[Entity secret] --+
                  |
                  v
          [Encrypt per request] -> [Fresh ciphertext] -> [Sensitive-operation approval request]
                  ^
                  |
       [Circle's public RSA key]

[Separately stored recovery file] -> [Reset after loss] -> [New entity secret]
```

entity secret은 개발자 제어 지갑의 민감한 작업을 승인하는 개발자 보유 비밀값이다. [공식 문서](https://developers.circle.com/wallets/dev-controlled/entity-secret-management.md)는 계정 범위의 32바이트 비밀이며 API key의 인증과 구별한다고 설명한다. 32바이트를 16진수로 적으면 32 * 2 = 64자리이므로 Claude 답변의 길이 표기(64자)는 모순이 아니다.

`entitySecretCiphertext`는 그 비밀을 Circle의 공개 RSA 키로 암호화하여 요청에 넣는 값이다. 문서는 매 요청 새 암호문을 만들고 재사용을 거절하며 SDK가 재암호화를 처리한다고 설명한다. 직접 API를 호출한다면 그 책임을 구현해야 한다. 같은 암호문을 다시 보내는 일과 이미 제출한 자산 거래의 효과를 확인하여 재시도하는 일은 다르다.

복구 파일은 비밀을 잃었을 때 재설정하는 별도 자격증명이다. 문서는 별도 비밀번호가 없는 파일 자체의 권한, 비밀 교체 및 재설정 뒤 이전 파일의 무효화를 설명한다. 비밀과 복구 파일의 분리 보관 및 갱신 절차가 필요하다. `.env`에 비밀을 넣고 `.gitignore`에 등록하는 일만으로 회복과 키 교체가 제공되지는 않는다. 비밀 교체 후 진행 중 요청도 새 승인 정보로 처리해야 한다. wallet set을 여러 개 만들더라도 같은 계정 비밀을 공유한다는 문서의 설명을 보안 경계가 분리됐다는 주장으로 바꾸지 않는다.

### 3.3 지출 한도: 앱, 서명자, 계약과 allowance는 자산 이동을 서로 다른 자리에서 막는다

자산을 움직이는 앱을 만드는 개발자에게는 지출 한도가 필요하다. 다만 지출 한도는 금액 하나를 적는 설정이 아니라 어떤 요청을 어느 주체가 차단할 수 있는지 정하는 통제다. 아래 표처럼 같은 자산 이동에도 앱, 서명자와 계약 등 서로 다른 통제가 적용될 수 있고, 한 통제가 거절해도 다른 경로로 같은 자산을 이동할 수 있다면 그 통제를 전체 지출의 상한이라고 설명할 수 없기 때문이다. 정하는 방법은 보호할 자산과 허용 작업, 검사 위치 및 정책을 변경할 권한을 함께 적고, 표의 각 통제에 우회할 수 있는 경로가 있는지 확인하는 것이다.

공식 글 연결: [Unified Balance Kit: Safeguards and Recovery for spend()](https://www.arc.io/blog/unified-balance-kit-production-safeguards-and-recovery-patterns-for-spend) (2026-06-19, [공식 원문](https://www.arc.io/blog/unified-balance-kit-production-safeguards-and-recovery-patterns-for-spend)). Unified Balance의 SCA(스마트 계약 계정) 지출 사례는 예치된 자금을 지출할 때 각 체인에서 서명을 맡을 EOA(외부 소유 계정)가 필요하다고 설명한다. 지출마다 위임 관계가 ready인지 확인하는 구현 사례이며, 앱의 지출 상한 전체를 보장하는 설명은 아니다.

모델에게 예산을 지키라고 지시하는 것과 실제 자산 이동을 막는 권한 검사는 다르다. 한 행은 내가 ChatGPT 답변의 지출 한도 설명을 보호 대상에 따라 구별한 통제 하나다. 대안들을 미리 제외하기 위한 표가 아니라 구현에서 적용 경로를 확인하기 위한 표다.

| 통제                | 제한하는 대상                            | 추가 확인할 경로                                                                               |
| ------------------- | ---------------------------------------- | ---------------------------------------------------------------------------------------------- |
| 앱의 최대 금액      | 해당 앱에 들어온 요청                    | 직접 RPC 서명과 다른 앱 또는 API로 우회할 수 있는지 확인한다.                                  |
| 서명자의 승인 정책  | 그 서명자가 승인하는 작업                | 정책 변경 권한과 예외 서명 또는 다른 키를 확인한다.                                            |
| 계약의 권한 및 예산 | 해당 계약을 통한 자산 이동               | 관리자 변경과 직접 호출 및 다른 계약과 전송 경로를 확인한다.                                   |
| ERC-20 allowance    | 지정 계약이 사용할 수 있는 자산의 승인량 | 이미 사용한 양과 새 승인, 다른 spender를 확인한다. spender는 자산을 사용할 권한을 받은 주소다. |
| 지갑 잔액           | 현재 그 주소가 보유한 자산               | 자금 보충 및 다른 주소를 통한 실행을 확인한다. 잔액은 기간별 정책과 다르다.                    |
| 가스 대납 정책      | 대납자가 부담할 비용                     | 자기 가스와 다른 대납 및 첫 거래 예외를 확인한다.                                              |

[Agent Wallet의 지출 정책](https://developers.circle.com/agent-stack/agent-wallets/wallet-operations/custom-policies.md)은 메인넷 지갑에서만 지원되며 정책 변경에 이메일 OTP(One-Time Password, 일회용 인증코드)를 요구한다고 설명한다. 전송 한도와 수취인 및 계약의 허용 또는 차단 목록을 확인한다. 이 지출 정책을 테스트넷에 그대로 시연할 수 있다고 가정하지 않는다. 테스트넷의 한도 시험은 앱, 서명자와 계약 등 선택한 집행 경로에서 설계할 수 있다. 자체 계약만 유일한 방법이라는 Claude 답변의 추론은 채택하지 않는다.

설명용 상황으로 앱이 입력 금액을 제한하지만 연결된 서명자가 다른 요청도 승인할 수 있다고 가정하자. 이 경우 앱 화면에서 초과 입력이 거절된 결과는 그 화면의 검사만 확인한다. 전체 지출 통제를 검증하려면 화면을 거치지 않는 요청도 같은 승인 정책의 검사를 받는지 살펴봐야 한다. 정책 변경 권한을 가진 주체가 한도를 바꾸는 상황도 별도 시험 대상이다. 이 예시는 실제 취약점을 관측한 결과가 아니라 표의 적용 경로와 변경 권한을 확인할 시험 설계다.

`approve`는 실제 송금이 아니다. 특정 계약이 사용할 수 있는 한도를 승인하는 동작이며, 계약이 그 권한으로 실제 이전을 수행할 때 자산이 이동한다. 예산 앱에서는 사용자에게 받은 승인, 계약에 부여한 한도와 실제 지급액을 따로 표시해야 한다. 이것은 ERC-20 승인과 잔액의 관계를 설명하기 위해 내가 만든 구현 사례다.

[계약 이식 안내의 승인과 sweep](https://docs.arc.io/arc/tutorials/porting-contracts-to-arc.md)는 `USDC.approve`가 `transferFrom` 호출만 제한한다고 명시한다. 계약이 native USDC를 전송하는 함수도 제공한다면 그 함수는 allowance와 별도로 같은 잔액을 움직인다. 따라서 ERC-20 승인만으로 모든 전송 경로가 제한된다고 설명하지 않는다.

[계약 주소 안내의 StableFX와 Permit2](https://docs.arc.io/arc/references/contract-addresses.md)는 Permit2를 서명 기반 토큰 승인의 공통 계약으로 설명하고 StableFX에 필요하다고 적는다. 문서의 메인넷 및 테스트넷 주소는 `0x000000000022D473030F116dDEE9F6B43aC78BA3`다. StableFX가 지갑의 USDC를 이전하도록 먼저 Permit2에 USDC allowance를 부여해야 한다. 이 사전 승인은 실제 이전과 구분하며, 이번 실험에서는 Permit2 승인과 StableFX 실행을 수행하지 않았다.

### 3.4 가스 대납: Gas Station 정책은 수수료 부담자를 바꿀 뿐 지출 한도가 아니다

사용자가 가스를 직접 내지 않고 앱을 쓰게 하려면 가스 대납이 필요하다. 가스 대납은 사용자가 하려는 작업과 그 실행 비용을 부담하는 주체를 분리한다. 그래서 앱에서는 자산을 얼마나 보낼 수 있는지와 그 거래의 수수료를 누가 내는지를 별도 조건으로 확인해야 한다. 구현할 때에는 대납이 거절된 상황에서 거래 자체가 불가능한지, 자기 가스를 사용해 계속할 수 있는지와 사용자에게 추가 승인이 필요한지를 정해 둔다. 실제 행동은 선택한 지갑과 구현에 따라 정하며 자동으로 다른 비용 부담 경로로 바뀐다고 가정하지 않는다.

Gas Station은 정책 범위에서 사용자의 가스를 대신 부담하는 서비스다. [정책 문서](https://developers.circle.com/wallets/gas-station/policy-management.md)는 메인넷에서 네트워크별 활성 기본 정책을 설정하고 일일 지출 및 거래별 지출과 작업 수 또는 주소를 구성한다고 안내한다. 한도를 비워 두면 적용되지 않는다고 설명한다.

정책 초과로 대납이 거절돼도 송신인이 자기 가스를 부담하면 거래할 수 있다. 따라서 정책의 비활성화도 자산 이전의 전면 중단과 같지 않다. 문서에는 첫 SCA(Smart Contract Account, 계약으로 구현된 계정) 거래에 거래별 금액 한도를 적용하지 않는 예외와, 그 검사에서 논스(nonce, 거래 순번)를 잠그지 않아 여러 고비용 호출이 통과할 수 있다는 고지가 있다. 대납 한도를 엄격한 자산 지출 경계라고 설명하지 않는다.

Claude 답변이 제시한 50 USDC는 문서의 Arc Testnet 행에서 일일 대납 한도로 확인된다. 일일 정책은 UTC 0시에 재설정한다고 안내한다. 이는 테스트 대납이며 운영 예산과 faucet의 수령량은 별개다. 실제 정책 집행을 이번에 설정하거나 관측하지 않았다.

### 3.5 위험 통제: 서비스의 위험 심사와 USDC 계약의 주소 차단은 다른 경로에서 일어난다

위험 심사나 주소 차단을 다루는 앱의 개발자에게 필요한 것은 심사하는 대상과 조치를 집행하는 위치의 구분이다. 서비스가 요청이나 주소를 심사한 결과와 체인이 특정 자산 이동을 차단한 결과는 서로 다른 처리 경로에서 발생하기 때문이다. 따라서 앱은 심사 결과, 적용된 조치와 실제 제출 및 실행 상태를 각각 연결해서 기록해야 한다. 아래 서비스 시험과 자산 차단 시험은 이 차이를 보여주는 사례이며, 한 사례의 승인이나 거절로 다른 경로의 결과까지 판단하지 않는다.

Compliance Engine은 서비스 정책의 심사와 REVIEW, FREEZE_WALLET 및 DENY 같은 조치를 설명한다. REVIEW는 검토 요청, FREEZE_WALLET은 해당 지갑의 동결 조치, DENY는 해당 요청의 거절을 나타내는 문서 용어다. 위험 등급과 조치, inbound와 outbound 및 주소 심사 결과를 함께 읽는다. [시험 안내](https://developers.circle.com/wallets/compliance-engine/tx-screening-testing.md)에는 high 위험에도 APPROVED 예제가 있다.

Sanctions 시험의 정확한 주소 접미사는 `999999999999`다. ChatGPT 답변의 `9999`를 모든 환경의 거절 규칙으로 사용하지 않는다. 시험은 기본 규칙의 존재에 의존하며 예제의 체인은 MATIC이다. 같은 fixture가 현재 Arc에서 지원 및 집행되는지는 별도 확인한다. fixture는 예상 결과를 유도하도록 정한 시험용 입력이다.

[계약 주소 안내의 Transaction extensions](https://docs.arc.io/arc/references/contract-addresses.md)는 오프체인 차단 목록이나 USDC 이전 감시를 운영한다면 Memo와 Multicall3From도 감시 대상에 포함하도록 안내한다. 두 계약은 CallFrom을 통해 원래 EOA를 `msg.sender`로 유지하므로, 계약을 인식하지 못하는 감시 경로에서 차단 집행을 우회하지 않도록 해야 한다. 이 오프체인 감시 조건은 native 전송의 runtime 차단과 구분한다.

Arc USDC의 차단 주소를 이용한 실행 시험은 서비스의 위험 심사와 별개다. [계약 주소 안내](https://docs.arc.io/arc/references/contract-addresses.md)의 Test addresses for restricted transfer behavior 절은 테스트용 `0x70997970C51812dc3A010C7d01b50e0d17dc79C8`을 차단 주소로 적는다. 실제 상태와 실행 실패는 해당 블록 및 환경에서 확인한다. 차단 상태, 사전 simulation의 거절과 포함된 실패를 동일 사건으로 합치지 않는다. 권한과 통제를 정했다면 정상 요청이 어떤 결과를 만드는지 추적할 수 있어야 한다.

## 4. 정상 실행: 요청을 승인하고 제출한 뒤 그 결과를 업무 기록과 어떻게 대조하는가

준비와 권한을 갖췄다면 첫 실행을 해 본다. 첫 실행이 보여야 할 것은 승인한 요청, 그 요청의 처리 식별자, 그리고 실제로 생긴 효과의 연결이다. 성공 메시지 하나만으로는 의도한 효과가 생겼는지, 결과를 나중에 다시 찾을 수 있는지 알 수 없기 때문이다. 아래 시퀀스는 승인, 제출과 결과 확인의 공통 흐름이다. 4.1(요청 흐름)은 이 흐름을 경로와 상관없이 설명하고, 4.2(체인 실행)는 직접 체인 호출로 계약을 배포하고 USDC를 보내는 경우를, 4.3(서비스 실행)은 Circle 서비스인 Onramp를 쓰는 경우를 따라간다.

**정상 처리 시퀀스: 승인, 제출과 결과 확인**

시간은 위에서 아래로 흐르며 가로 화살표는 요청과 응답을 나타낸다. 승인 담당은 선택 경로의 서명자 또는 인증과 권한 검사 구성이다. 서명자가 직접 제출하는 구현에서는 제출의 출발 주체를 그 서명자로 맞춘다.

한국어:

```text
앱                       승인 담당                  체인/서비스
 |                           |                           |
 |--- 승인할 작업 ----------->|                           |
 |<-- 승인 결과 --------------|                           |
 |                           |                           |
 |--- 승인된 요청의 제출 -------------------------------->|
 |<-- 거래 해시 또는 서비스 객체 식별자 ------------------|
 |                           |                           |
 |  [업무 식별자와 처리 식별자를 연결해서 기록]            |
 |                           |                           |
 |--- 기존 작업의 결과 조회 ----------------------------->|
 |<-- 영수증, 대상 상태 또는 서비스 처리 상태 ------------|
 |                           |                           |
 |  [실제 효과와 의도한 업무 결과를 대조]                  |
```

English:

```text
App                      Approval handler          Chain/service
 |                              |                        |
 |--- Operation to approve ---->|                        |
 |<-- Approval result ----------|                        |
 |                              |                        |
 |--- Submit approved request -------------------------->|
 |<-- Transaction hash or service object ID -------------|
 |                              |                        |
 |  [Link business ID with processing IDs]               |
 |                              |                        |
 |--- Query the existing operation --------------------->|
 |<-- Receipt, target state or service status -----------|
 |                              |                        |
 |  [Reconcile actual effects with the intended outcome] |
```

### 4.1 요청 흐름: 사용자의 의도를 거래로 만들고 처리 식별자와 결과를 연결한다

개발자가 어느 경로를 쓰든 구현해야 하는 것은 요청 흐름이다. 요청 흐름은 사용자의 의도를 외부에서 실행할 수 있는 작업으로 바꾸고, 그 결과를 다시 같은 업무에 연결하는 과정이다. 체인과 서비스의 개별 상태 이름은 다를 수 있지만, 앱이 어떤 요청을 추적하고 있는지와 무엇을 완료로 판단하는지는 명확해야 하기 때문이다. 방법은 요청의 목적과 승인 대상을 정하고, 외부 처리 식별자를 내부 업무 식별자와 연결해 기록한 뒤, 그 식별자로 실제 효과를 조회하는 것이다. 이 절은 이 연결을 경로와 상관없는 공통 설명으로 삼는다.

정상 실행의 최소 단위는 성공 메시지 하나보다 길다. 의도한 작업, 권한 검사와 서명, 제출 식별자와 실제 상태 변화를 연결해야 한다. 아래는 ChatGPT 답변의 전체 구현 그림과 Claude 답변의 영수증 설명을 내가 앱 및 서명자와 외부 처리의 경계로 재구성한 그림이다. 연결은 요청과 증거의 흐름이며 모두 자산 이동을 뜻하지 않는다.

한국어:

```text
[사용자의 의도]
       |
       v
[앱: 환경/입력/정책 확인] -> [서명자: 승인과 서명]
       |                              |
       |                              v
       |                       [체인 또는 서비스 제출]
       |                              |
       |                              v
       +--------------------> [해시와 객체 ID 기록]
                                      |
                    +-----------------+----------------+
                    |                                  |
                    v                                  v
          [영수증과 대상 상태]               [서비스의 상태/webhook]
                    |                                  |
                    +-----------------+----------------+
                                      v
                        [업무 결과 대사와 남은 단계]
```

English:

```text
[User intention]
       |
       v
[App: environment/input/policy] -> [Signer: authorize and sign]
       |                                     |
       |                                     v
       |                            [Submit to chain or service]
       |                                     |
       |                                     v
       +--------------------------> [Record hash and object IDs]
                                             |
                         +-------------------+----------------+
                         |                                    |
                         v                                    v
                [Receipt and target state]          [Service state/webhook]
                         |                                    |
                         +-------------------+----------------+
                                             v
                           [Reconcile outcome and remaining steps]
```

앱은 승인할 작업과 환경을 정하고, 서명자는 그 요청의 권한을 검사한다. 체인의 해시와 서비스 ID 및 내부 업무 ID를 연결하면 요청 응답 이후의 결과를 조회할 수 있다. 직접 계약 호출에는 서비스 가지가 필요하지 않을 수 있다. Onramp와 지급 서비스 또는 브리지에는 별도 완료 대상이 있다. 체인 확정과 외부 은행 입금까지 같은 완료로 합치지 않는 이유는 기업 업무 설명에 설명했다.

요청 처리의 첫 단계에서 앱은 사용자의 의도를 네트워크가 처리할 거래 항목으로 구체화한다. 다음 그림은 설명용 지급 하나를 예로 들어 그 항목을 보여 준다.

한국어:

```text
 사용자의 의도: "A에게 100 USDC를 보내고 싶다"
        |
        | 앱이 거래 내용으로 구체화
        v
 +----------------+-------------------------------+
 | 실행 체인      | Arc                           |
 | 보내는 계정    | 사용자의 주소                 |
 | 수취 주소      | A의 주소                      |
 | 자산과 수량    | USDC 100                      |
 | 처리 방식      | 단순 자산 이전 또는 계약 호출 |
 +----------------+-------------------------------+
        |
        v
 [네트워크가 처리할 거래]          값은 설명용 예시다.
```

English:

```text
 User's intent: "I want to send 100 USDC to A"
        |
        | the app turns it into transaction fields
        v
 +-----------------+---------------------------------+
 | Chain           | Arc                             |
 | Sending account | the user's address              |
 | Recipient       | A's address                     |
 | Asset, amount   | USDC 100                        |
 | Method          | plain transfer or contract call |
 +-----------------+---------------------------------+
        |
        v
 [Transaction the network processes]   Values are illustrative.
```

왼쪽 칸은 네트워크가 거래를 처리하려면 필요한 항목이고, 오른쪽 칸은 설명용 값이다. 처리 방식이 계약 호출이라면 수취 주소 대신 대상 계약과 호출 내용이 들어간다.

같은 사용자의 앱 내 요청이라도 지갑 유형에 따라 권한 관계가 달라진다. 개발자 제어 지갑에서는 백엔드의 승인 관리가 중요하고, 사용자 제어 또는 모듈형 지갑에서는 사용자의 승인 참여가 중요하다. [공식 문서](https://developers.circle.com/wallets/signing-and-authorization-models.md)는 지원 체인에서 Circle이 전송을 처리하는 경로와 서명 API를 이용해 자체 노드로 제출하는 경로도 구별한다. 따라서 지갑 서비스를 선택할 때에는 누가 요청하고 승인하는지뿐 아니라 서명 뒤 누가 제출하며 결과를 어디서 확인할지도 정해야 한다.

한국어:

```text
                           [서명된 거래]
                                 |
            +--------------------+---------------------+
            v                                          v
 경로 A: Circle이 제출                       경로 B: 서명 API로 서명만 받음
 [Circle Wallets] --> [지원 체인]            [앱] --> [자체 노드나 RPC] --> [체인]
 결과 확인: API 응답과 이후 상태 통지        결과 확인: 제출 응답과 거래 조회
```

English:

```text
                        [Signed transaction]
                                 |
            +--------------------+---------------------+
            v                                          v
 Route A: Circle submits                     Route B: signing API only
 [Circle Wallets] --> [supported chain]      [App] --> [own node or RPC] --> [chain]
 check: API response, later status events    check: submission response, tx lookup
```

서명을 얻은 뒤의 경로는 두 갈래다. 경로 A에서는 Circle이 지원 체인으로 거래를 보내므로 앱은 API 응답과 이후 상태 통지로 결과를 확인한다. 경로 B에서는 앱이 서명만 받고 자체 노드나 RPC로 제출하므로 제출 응답과 거래 조회를 직접 연결해야 한다.

### 4.2 체인 실행: Counter 계약을 배포하고 호출하며 USDC를 보낸 결과를 확인한다

직접 체인 호출 경로에서 첫 실행은 계약을 배포하고 호출하는 일과 USDC를 보내는 일이다. 개발자는 실행 전에 대상 계약과 함수, 입력 및 전송 금액을 정하고, 제출 후에는 그 거래의 영수증과 관련 상태를 연결해 승인한 거래가 어떤 실행 결과와 상태 변화를 만들었는지 확인한다. 계약 내부의 상태 변경과 자산 이동은 확인할 대상이 다르므로 성공 영수증 하나로 모든 효과를 설명하지 않는다. 아래에서는 먼저 공식 배포 안내의 Counter 절차로 계약 상태의 변화를 확인하고, 이어서 USDC 전송 절차로 잔액과 가스 및 로그의 관계를 확인한다.

계약 상태를 확인할 때에는 시작 상태와 의도한 변경을 먼저 정한다. 조회 함수가 값을 반환하는 것과 상태를 변경하는 거래가 실행되는 것은 다른 작업이다. 제출한 거래를 추적할 식별자가 확보되면 해당 거래의 결과와 변경 대상의 상태를 대조한다. 여러 거래가 같은 상태에 영향을 주는 상황에서는 최종 값만으로 특정 요청의 효과를 단정하기 어려우므로 해당 블록과 거래 및 관련 기록을 함께 확인해야 한다. 이 원고의 단순 계약 예제도 그런 확인 구조의 일부다.

Counter는 저장된 숫자를 조회하고 증가시키는 단순 계약 예제다. [배포 안내](https://docs.arc.io/build/deploy-on-arc.md)는 프로젝트의 계약과 시험 및 배포 스크립트, Arc 환경의 시험과 테스트 자금 및 `--broadcast` 배포, 검증과 호출을 설명한다. compiler 버전과 생성자 인자 및 실제 네트워크를 맞추어 소스 검증을 수행한다. explorer의 소스 공개는 구현의 보안 감사와 다르다.

실험 관측: [배포 안내](https://docs.arc.io/build/deploy-on-arc.md)의 Counter 절차는 다음 순서다. (1) `arc-forge init hello-arc`로 프로젝트를 만들면 `src/Counter.sol`, 시험 파일과 배포 스크립트가 생기고, 생성된 `.gitignore`가 `.env`를 제외한다(Initialize a project 절). (2) `.env`에 `ARC_TESTNET_RPC_URL="https://rpc.testnet.arc.io"`를 넣고 `source .env`로 불러온다(Configure the RPC connection 절). (3) 배포 전에 `arc-forge test --network arc`로 Arc 실행 환경에서 시험한다. 문서는 이 옵션이 일반 EVM 시뮬레이터가 놓치는 Arc 고유의 문제를 잡는다고 설명한다(Test the contract 절). (4) `arc-cast wallet new`로 지갑을 만들거나 기존 개발 지갑을 쓰고, 개인 키를 `.env`의 `PRIVATE_KEY`에 넣는다(Set up your wallet 절). (5) Faucet에서 테스트넷 USDC를 받는다(Fund your wallet 절, 2.3(시험 자금)). (6) `arc-forge create src/Counter.sol:Counter --rpc-url $ARC_TESTNET_RPC_URL --private-key $PRIVATE_KEY --broadcast`로 배포하고, 출력의 `Deployed to` 주소를 `.env`의 `COUNTER_ADDRESS`에 저장한다(Deploy the contract 절). (7) `arc-forge verify-contract`에 `--chain-id 5042002 --verifier blockscout --verifier-url https://explorer.testnet.arc.io/api/`를 주어 소스를 검증한다. 생성자 인자가 있으면 `arc-cast abi-encode`로 인코딩해 `--constructor-args`로 넘긴다(Verify the contract on Arc Testnet Explorer 절). (8) `arc-cast call $COUNTER_ADDRESS "number()(uint256)"`로 값을 읽고, `arc-cast send $COUNTER_ADDRESS "increment()"`로 증가시킨 뒤 다시 읽는다. 문서는 처음 0, 증가 뒤 1을 예상 결과로 제시한다(Interact with your contract 절).

2026-10-07 실험에서 이 순서대로 실행했다. (3)단계의 `arc-forge test --network arc`는 시험 2개를 통과했고, 이때 solc 0.8.37이 자동으로 내려받아졌다. (6)단계의 배포는 가스 156,813을 25 Gwei에 써서 수수료가 156,813 x 25 Gwei = 0.003920325 USDC였다. (8)단계에서 `number()`는 0이었고, `increment()`(가스 43,482, 43,482 x 25 Gwei = 0.00108705 USDC) 뒤 1이 되어 문서의 예상과 같았다. (7)단계의 소스 검증은 제출에 `OK`를 받았지만 결과가 "Fail - Unable to verify"였다. 탐색기의 `GET /api/v2/smart-contracts/verification/config`가 돌려준 컴파일러 목록에서 가장 새 판은 0.8.36이었고 0.8.37은 없었다. 그래서 `--use 0.8.36`으로 다시 배포하고 `--compiler-version 0.8.36`으로 검증하자 "Pass - Verified"였다. 탐색기가 실패 이유를 직접 밝힌 것은 아니므로, 원인이 컴파일러 버전이라는 판단은 이 대조에 근거한다. 따라서 소스를 검증할 계약은 배포 전에 탐색기의 컴파일러 목록을 확인하고, 그 목록에 있는 버전으로 컴파일러를 고정한다. 세 거래의 영수증에는 로그가 하나도 없었다. 수수료를 USDC로 냈지만 수수료 지급은 Transfer 로그를 남기지 않았다.

Counter가 처음 0인 문서 예제에서는 조회로 0을 확인하고 increment를 보낸 뒤 영수증과 상태 1을 확인한다. 이것은 문서에서 제시한 예상이다. 실제 시험에서는 배포 주소와 코드 및 시작 상태를 직접 확인하고 그 상태에서 어떤 변화가 일어났는지 기록한다. 영수증의 성공만 보고 모든 비즈니스 동작까지 검증됐다고 쓰지 않는다.

실험 관측: USDC를 네이티브 전송으로 보내는 예제는 [가스 문서](https://docs.arc.io/arc/references/gas-and-fees.md)에 있다. 문서는 ethers의 `JsonRpcProvider("https://rpc.testnet.arc.io")`와 개인 키 지갑으로 `sendTransaction`을 호출하면서 `maxFeePerGas`를 최소 20 Gwei로 두라고 안내하고, 이 하한보다 낮게 제출한 거래는 무기한 대기하거나 실패할 수 있다고 적는다. `maxPriorityFeePerGas`는 0 Gwei도 받지만 사용량이 많을 때는 1 Gwei 정도의 작은 tip이 포함을 앞당길 수 있다고 설명한다(Submitting transactions 절). 다만 이 예제의 `value: ethers.parseUnits("1", 6)`은 2.3(시험 자금)에서 설명한 18자리 규칙에서 1 USDC가 아니라 10^-12 USDC이므로, 1 USDC를 보내려면 네이티브 전송의 단위인 10^18 정수를 넣어야 한다. 새로 보관한 공식 자료에는 App Kit의 Send와 ERC-20 전송에 메모를 붙이거나 여러 전송을 묶는 예제가 있다. 아래에서 문서의 절차를 옮기되 아직 실행하지 않은 단계로 구분한다.

2026-10-07 실험에서 이 예제대로 `maxFeePerGas`를 20 Gwei로 두고 시험 지갑 사이에 두 번 보냈다. ethers가 자동으로 넣은 `maxPriorityFeePerGas`는 5 Gwei였지만 블록의 기본 수수료가 20 Gwei여서 실제 가격은 20 Gwei였다. 0.01 USDC를 뜻하는 10^16을 보낸 첫 전송은 수취 지갑의 네이티브 잔액을 10^16, ERC-20 잔액을 10000 늘렸다. 문서 예제의 `parseUnits("1", 6)`을 그대로 쓴 둘째 전송은 1,000,000을 보냈고, 수취 지갑의 네이티브 잔액은 1,000,000(10^-12 USDC) 늘었지만 ERC-20 잔액은 변하지 않았다. 두 전송의 수수료는 모두 21,000 x 20 Gwei = 0.00042 USDC였고, 송신 지갑의 감소에서 보낸 금액과 수수료를 빼면 차이가 0이었다. 로그는 두 전송에서 각각 하나였으며, 시스템 주소 `0xffffFFFfFFffffffffffffffFfFFFfffFFFfFFfE`가 18자리 정수 금액으로 방출했다. 같은 실험에서 Faucet의 ERC-20 `transfer`는 그 시스템 주소와 USDC 계약이 하나씩 방출한 로그 두 개를 남겼다.

USDC 전송에서는 요청의 인터페이스와 금액, 수취인 전후 잔액과 가스 및 이벤트를 대조한다. 송신인 잔액 감소에는 이전 금액과 가스가 함께 들어갈 수 있으므로 전액을 지급액으로 세지 않는다. 네이티브 및 ERC-20 로그가 같은 이동을 표현하는 경우 방출 주소와 단위를 읽고 중복 집계하지 않는다. 두 로그가 모든 거래에서 반드시 같은 수로 발생한다고 가정하지 않는다.

전송 시험을 구체화하면 먼저 송신인과 수취인, 사용할 인터페이스 및 사람이 의도한 금액과 요청 정수를 기록한다. 제출 후에는 거래 해시를 업무 식별자에 연결하고 영수증과 대상 블록을 확인한다. 잔액 조회의 인터페이스와 블록 기준을 명시한 뒤 전후 변화, 실제 비용 부담자와 가스 및 관련 로그를 대조한다. 시험 중 다른 전송이 같은 주소의 잔액에 영향을 주었다면 그 변화를 함께 분리해야 한다. 이런 기록이 있어야 잘못된 단위, 수수료를 포함한 잔액 감소와 실제 지급액을 구별할 수 있다.

설명용 예산 계약을 예로 들면 실행은 단순히 전송 버튼이 눌렸는지 확인하는 과정이 아니다. 계약에 승인 주체와 허용된 지급 조건이 구현돼 있다면, 호출을 받은 계약은 그 조건을 검사하고 충족한 경우 자산 이전과 업무 상태 갱신을 수행한다. 조건이 맞지 않아 실행이 실패하면 앱은 그 요청을 성공한 지급으로 취급할 수 없다. 이 사례는 계약 실행의 의미를 설명하기 위한 것이며 특정 예산 계약을 배포하거나 시험한 결과는 아니다.

한국어:

```text
 [호출: 30 USDC 지급 요청]
            |
            v
 [설명용 예산 계약: 조건 검사]
   - 정해진 승인 주체가 승인했는가?
   - 남은 한도 안인가?
            |
     +------+-------+
     v              v
  [충족]         [불충족]
     |              |
     v              v
 [자산 이전과     [실행 실패]
  업무 상태 갱신]   앱은 이 요청을 성공한 지급으로 표시할 수 없다
```

English:

```text
 [Call: request a 30 USDC payment]
            |
            v
 [Illustrative budget contract: check conditions]
   - did the designated approver approve?
   - is it within the remaining limit?
            |
     +------+-------+
     v              v
  [Met]          [Not met]
     |              |
     v              v
 [Move assets and [Execution fails]
  update records]   the app cannot show this as a successful payment
```

계약은 호출을 받으면 먼저 조건을 검사한다. 조건을 충족한 경우에만 자산 이전과 업무 상태 갱신이 일어나고, 그렇지 않으면 실행이 실패한다. 실패한 실행은 지급 기록으로 쓸 수 없다.

미실행 항목: [Send tokens on the same blockchain](https://docs.arc.io/app-kit/quickstarts/send-tokens-same-chain.md)는 브라우저의 연결 지갑과 서버의 Circle Wallets 지갑을 두 경로로 안내한다. 브라우저에서는 EIP-6963 provider를 찾고 `eth_requestAccounts`로 연결한 다음 `createViemAdapterFromProvider({ provider })`를 만든다. 서버에서는 API 키와 entity secret으로 `createCircleWalletsAdapter`를 만든다. 서버 키는 클라이언트에 넣지 않는다. 어댑터와 지갑을 준비한 뒤 같은 체인의 전송을 추정하고 보낸다.

아래는 공식 브라우저 예제의 전송 입력과 호출 부분이다. 지갑 연결과 어댑터 설정을 마친 뒤 사용하는 부분이며 독립 실행 스크립트는 아니다. `RECIPIENT_ADDRESS`를 실제 수취 주소로 바꾸고 수취인과 금액을 확인한다.

```typescript
import { AppKit, type SendParams } from "@circle-fin/app-kit";

const kit = new AppKit();
const sendParams: SendParams = {
  from: { adapter, chain: "Arc_Testnet" },
  to: "RECIPIENT_ADDRESS",
  amount: "1.00",
  token: "USDC",
};
const estimate = await kit.estimateSend(sendParams);
const result = await kit.send(sendParams);
```

문서는 반환된 거래 해시를 탐색기에서 확인하고 수취인과 금액을 대조하도록 안내한다. 예제에 인쇄된 결과는 이번 실행 결과가 아니다. App Kit 설치 실험만으로 Send의 정상 실행을 확인했다고 쓰지 않는다.

미실행 항목: [Send USDC with a transaction memo](https://docs.arc.io/arc/tutorials/send-usdc-with-transaction-memo.md)는 거래에 송장이나 주문 참조 같은 메타데이터를 붙이는 방법을 안내한다. [Transaction memos](https://docs.arc.io/arc/concepts/transaction-memos.md)의 Memo 계약은 `0x5294E9927c3306DcBaDb03fe70b92e01cCede505`이며 CallFrom 프리컴파일을 통해 대상 호출에서 원래 EOA를 `msg.sender`로 유지한다. USDC 전송자는 Memo 계약이 아니라 서명한 지갑으로 보인다. 호출은 EOA가 직접 해야 하며 Circle 지갑도 EOA 구성일 때 지원한다. ERC-4337, Circle SCA와 Safe 같은 계약 지갑은 직접 호출자로 지원하지 않는다.

튜토리얼은 다음 순서로 구현한다. (1) 테스트넷 지갑과 USDC, 선택한 Viem, ethers 또는 web3.py 환경을 준비한다. (2) USDC의 `transfer(recipient, 1_000_000)`에 해당하는 calldata를 만들고, `keccak256`으로 calldata hash와 `bytes32` memoId를 준비한다. 금액은 ERC-20의 6자리 단위로 1 USDC다. (3) `eth_getCode`로 Memo 주소의 배포 코드를 확인한다. `0x`라면 중단한다. (4) `memo(target, data, memoId, memoData)`를 호출해 영수증을 기다리고 성공 상태를 확인한다. (5) `BeforeMemo`, 대상 계약의 전송 이벤트와 `Memo` 이벤트를 해독해 sender, target, callDataHash, memoId와 메모 바이트가 보낸 값과 맞는지 확인한다. (6) 영수증의 블록에서 indexed memoId로 Memo 로그를 다시 찾는다. memoId는 앱이 정의하는 조회 식별자이며 같은 호출을 정확하게 복원하려면 원래 calldata도 보관한다.

성공한 Memo 호출의 기록 순서는 `BeforeMemo` 다음에 대상 계약 이벤트, 마지막에 `Memo`다. 중첩 메모에서는 시작 시점에 `BeforeMemo`가 나오고 종료 이벤트는 안쪽 메모부터 바깥쪽으로 나온다. 하위 호출이 revert하면 바깥 거래도 revert하고 메모 인덱스의 증가도 되돌아가며, 하위 반환 데이터는 `MemoFailed(bytes)`로 감싸진다. 메모 인덱스를 변경하므로 `STATICCALL`로 실행할 수 없고 Memo에 대한 `DELEGATECALL`도 CallFrom 권한을 갖지 못한다. EOA가 CallFrom을 직접 호출하면 `unauthorized caller`로 revert하므로 Memo의 공개 진입점을 사용한다. 이 기록을 원고의 업무 식별자와 연결하되, 이번에 메모 전송이나 조회를 실행한 것으로 표시하지 않는다.

미실행 항목: [Send batch USDC transfers](https://docs.arc.io/arc/tutorials/batch-usdc-transfers.md)는 여러 USDC 전송을 한 거래에 묶는 방법을 안내한다. [Batched transactions](https://docs.arc.io/arc/concepts/batched-transactions.md)의 Multicall3From 주소는 `0x522fAf9A91c41c443c66765030741e4AaCe147D0`이며 `aggregate3`의 각 하위 호출을 CallFrom으로 실행해 원래 EOA를 유지한다. 일반 Multicall3의 읽기 집계와 같은 기능으로 취급하지 않는다.

튜토리얼은 (1) 각 수취인과 ERC-20의 6자리 전송 금액으로 `transfer` calldata를 만들고, (2) `eth_getCode`로 Multicall3From의 코드를 확인하며, (3) `{ target, allowFailure: false, callData }` 배열을 구성해 사전 시뮬레이션하고 `aggregate3`를 제출한 뒤, (4) 성공 영수증의 USDC 계약 로그에서 각 `Transfer`의 `from`이 원래 지갑이고 `to`와 `value`가 각 요청과 맞는지 확인한다. 이 계약에는 batch 전용 이벤트가 없으므로 대상 계약의 이벤트를 읽는다. native 시스템 emitter와 ERC-20 계약이 같은 이동을 기록할 때에는 단위와 방출 주소를 구분한다.

모든 하위 호출이 성공해야 한다면 `allowFailure: false`를 사용한다. 한 하위 호출이 실패하면 전체 묶음이 revert한다. `true`는 앱이 실패한 하위 호출을 명시적으로 처리할 때만 사용한다. CallFrom은 value를 전달하지 않으므로 `aggregate3Value`와 native value 전달 패턴은 지원하지 않는다. 중간 계약을 거치는 호출도 원래 발신자 보존 조건에 어긋나면 거절된다. 실패 정책은 5.2(부분 성공)에서 여러 체인의 복구와 구분한다.

[Agentic Economy](https://docs.arc.io/build/agentic-economy.md)는 ERC-8004를 에이전트의 온체인 신원, 평판과 자격 검증에, ERC-8183을 작업 생성, USDC escrow 입금, 결과물 제출, 평가와 정산에 연결한다. [공식 계약 주소](https://docs.arc.io/arc/references/contract-addresses.md)는 ERC-8004의 registry와 ERC-8183의 테스트넷 참조 구현을 나열한다. 이는 에이전트 작업을 구현할 때 사용할 문서와 배포 주소의 설명이며, 이번 실험에서 에이전트 등록이나 작업 정산을 실행했다는 뜻은 아니다.

공식 글 연결: [Using Arc with ERC-8183 to Run an Agentic Economic Flow](https://www.arc.io/blog/running-an-agentic-economic-flow-on-arc-with-erc-8183) (2026-04-07, [공식 원문](https://www.arc.io/blog/running-an-agentic-economic-flow-on-arc-with-erc-8183)). ERC-8183 예제는 결과물 전체 대신 이를 나타내는 bytes32 값(commitment)을 체인에 기록한다고 설명한다. 예제의 주소와 호출 설명을 확보한 것과 코드 전체 및 실제 배포를 직접 검증한 것은 구별한다.

따라서 체인 처리의 완료를 설명하는 기록에는 승인한 입력, 실행 결과와 그 요청이 만든 대상 효과가 함께 있어야 한다. 단순 계약 시험은 상태 변경의 확인 방법을 보여주고 전송 시험은 자산 및 비용의 확인 방법을 보여준다. 서비스가 체인 거래를 생성하는 경로에서도 필요한 효과를 확인하되, 그 거래의 성공을 서비스 전체의 완료로 확대하지 않는다. 다음 절은 체인 밖에서도 계속되는 서비스 처리를 다룬다.

### 4.3 서비스 실행: Onramp 세션을 만들고 브라우저 표시와 서버의 결과를 대조한다

Circle 서비스 경로에서 첫 실행은 앱이 외부 서비스에 작업을 요청하고 그 서비스가 관리하는 객체와 결과를 추적하는 일이다. 이때 개발자가 정해야 할 것은 누가 요청할 수 있는지, 무엇을 처리 객체로 추적하는지, 어떤 상태와 실제 효과를 완료의 근거로 삼는지다. 서비스가 요청을 접수했다는 응답과 서비스가 맡은 작업이 끝났다는 사실이 다르기 때문이다. 이 절의 구체적인 사례는 Onramp의 세션 생성과 입금이며, 다른 서비스에도 같은 세션이나 입금 단계가 있다고 가정하지 않는다. 나는 아래 Onramp 절차를 위 질문에 답하는 사례로 배치했다.

Onramp 사례에서는 브라우저가 사용자에게 입력과 진행 상태를 보여주고, 앱 서버가 요청 권한과 업무 기록을 관리하며, 외부 서비스가 해당 작업을 처리한다. 브라우저가 표시한 성공과 서버가 확인한 처리 상태를 같은 사건으로 합치면 화면 종료나 통지 누락을 실제 실패로 잘못 해석할 수 있다. 반대로 요청 접수 응답만으로 최종 입금까지 완료됐다고 판단할 수도 있다. 그래서 앱의 업무 식별자와 서비스 객체 및 목적 지갑을 연결하고, 완료 기준에 해당하는 결과를 서버에서 대조하는 구성이 필요하다.

**Onramp 시퀀스: 브라우저 표시와 서버의 결과 대조**

화살표는 요청과 사건 전달이다. webhook 전달과 브라우저 이벤트의 도착 순서는 고정하지 않으며, 브라우저 알림 없이도 서버에서 결과를 확인할 수 있어야 한다.

한국어:

```text
브라우저                 앱 서버                  Onramp 서비스
   |                        |                           |
   |--- 세션 요청 --------->|                           |
   |                        | [사용자와 목적 지갑의 권한 확인]
   |                        |--- 세션 생성 ------------>|
   |                        |<-- 세션 정보 -------------|
   |<-- 위젯용 세션 정보 ---|                           |
   |--- 위젯의 구매 절차 ------------------------------>|
   |                        |                           |
   | [독립 통지: 아래 두 사건의 도착 순서는 고정되지 않음] |
   |<-- 화면 이벤트 -----------------------------------|
   |                        |<-- 서버 webhook ----------|
   |                        |--- 처리 상태 조회 -------->|
   |                        |<-- 최종 상태 -------------|
   |                        |                           |
   |                        | [요청/목적 지갑/결과 대조] |
```

English:

```text
Browser                  App server                Onramp service
   |                        |                           |
   |--- Request session --->|                           |
   |                        | [Check user/target-wallet authorization]
   |                        |--- Create session ------->|
   |                        |<-- Session details -------|
   |<-- Widget session -----|                           |
   |--- Widget purchase flow -------------------------->|
   |                        |                           |
   | [Independent notifications: no fixed arrival order] |
   |<-- UI event ---------------------------------------|
   |                        |<-- Server webhook --------|
   |                        |--- Query processing state>|
   |                        |<-- Final state -----------|
   |                        |                           |
   |                        | [Reconcile request/wallet/result]
```

실험 관측: [위젯 quickstart](https://docs.arc.io/app-kit/quickstarts/onramp-embed-widget.md)의 절차는 여섯 단계다. 시작 조건은 Node.js v22 이상, 서버 route와 브라우저 페이지가 있는 웹 앱, App Kit 설치, Circle Console의 API 키, 사용자가 받을 Arc 지갑 주소다(Prerequisites 절). (1) 서버 환경 변수에 `CIRCLE_API_KEY`를 넣고 클라이언트 코드에는 넣지 않는다(Set your environment variables 절). (2) 서버에 `createAppServerKit`과 `createSessionRouteHandler`로 session route를 만든다. 직불카드, Apple Pay와 Google Pay를 쓰려면 `referrerDomain`이 필요하고, 이 route는 인증을 하지 않으므로 배포 전에 `authorize` 콜백을 더한다(Expose a session route on your server 절). (3) 페이지에 높이가 0이 아닌 컨테이너를 DOM에 붙여 둔다(Add a container element to your page 절). (4) 브라우저에서 `kit.onramp.fetchSession`으로 2단계의 route에 `appUserId`와 `destinationAddress`를 보내 세션을 받고, `kit.onramp.mountIframe`으로 위젯을 붙이며, 화면을 떠날 때 `widget.close()`를 호출한다(Mint a session and mount the widget 절). (5) CSP를 쓰는 사이트는 `frame-src https://onramp.arc.io`와 `connect-src https://onramp.arc.io https://api.circle.com`을 허용한다(Allow the widget origin in your Content Security Policy 절). (6) 미실행 항목: 서버에 webhook 수신기를 두고 최종 입금 상태를 webhook 이벤트로 대조한다(Set up a webhook receiver 절). 아래 문단은 이 단계마다 확인할 조건을 설명한다.

2026-10-07 실험에서는 1-4단계를 Next.js 16.4.0 앱으로 옮겨 로컬에서 실행했다. 문서의 기본값(운영 위젯 `https://onramp.arc.io`)으로는 session route가 HTTP 200으로 세션을 받았지만, 위젯 자리에는 깨진 페이지 아이콘만 표시됐다. 운영 위젯의 응답 헤더에 있는 CSP가 `frame-ancestors https:`여서 로컬의 HTTP 페이지 안에는 붙지 않기 때문이다. quickstart는 이 조건을 단계 안에 적지 않고 5단계에서 [hosting requirements 문서](https://docs.arc.io/app-kit/references/onramp-hosting-requirements.md)를 가리키며, 그 문서는 운영 위젯의 CSP가 `localhost`를 막으므로 로컬 개발에는 sandbox를 쓰라고 안내한다. 그 문서대로 서버의 `baseUrl`을 `https://api-test.circle.com`으로, 서버와 클라이언트의 `widgetBaseUrl`을 `https://onramp-sandbox.arc.io`로 바꾸고, 페이지를 `127.0.0.1`이 아니라 `localhost`로 열자 위젯이 표시됐다. sandbox 위젯의 CSP는 `frame-ancestors https: http://localhost:*`다. sandbox를 쓰는 사이트가 CSP를 보낸다면 5단계의 주소 대신 `https://onramp-sandbox.arc.io`와 `https://api-test.circle.com`을 허용한다(같은 문서). 구매는 시도하지 않았고, 6단계의 webhook은 공개 수신 주소가 필요해 실행하지 않았다. 설치한 `@circle-fin/onramp-kit`의 타입 선언 주석은 "No public sandbox exists today"라고 적지만, 위 문서와 실제 sandbox 응답은 이 주석과 다르다.

[Onramp 개요](https://docs.arc.io/app-kit/onramp.md)는 서버가 특정 사용자와 목적 지갑의 세션을 만들고 브라우저가 위젯을 붙이는 절차를 설명한다. 세션 유효 기간은 30분이며 그 안에 모든 은행 입금이 완료된다는 뜻은 아니다. 위젯이 신원 확인과 지불 및 결제를 처리한다는 소개와 개발자가 기록해야 할 사용자 및 목적 지갑과 결과를 구별한다.

Onramp는 서버 API 키가 필요하다. [hosting requirements 문서](https://docs.arc.io/app-kit/references/onramp-hosting-requirements.md)는 키가 환경에 묶여 있어 sandbox 키는 production에서, production 키는 sandbox에서 동작하지 않는다고 적는다. 그런데 2026-10-07 실험에서는 같은 테스트넷 키로 두 주소(`api.circle.com`, `api-test.circle.com`)에 세션을 직접 요청했을 때 둘 다 201과 세션 토큰을 받았다. 이 관측은 세션 발급 단계에 한정되며, 결제나 입금 단계에서 환경을 구분하는지는 확인하지 않았다. 그러므로 키는 문서대로 환경마다 따로 쓴다. 직불카드와 Apple Pay 및 Google Pay를 활성화하려면 KYB(Know Your Business, 기업 신원과 자격 확인)와 `referrerDomain`을 요구한다. 은행 이체는 별도 지역 및 통화 조건을 확인하며 신용카드는 지원하지 않는다고 안내한다. 세계 여러 국가라는 문구에서 한국 사용자에게 허용된다고 추론하지 않는다.

[위젯 quickstart](https://docs.arc.io/app-kit/quickstarts/onramp-embed-widget.md)의 기본 session route는 사용자 인증을 하지 않는다. 배포에는 `authorize`를 추가해야 한다. 사용자와 목적 지갑을 실제 권한에 연결하는 검사는 내가 그 절차에서 도출한 구현 제안이다. ChatGPT 답변이 말한 서버 키 보호뿐 아니라 누가 세션을 만들 수 있는지도 정해야 한다.

위젯은 DOM에 연결된 높이가 있는 컨테이너에 붙이고 종료 시 controller를 정리한다. CSP(Content Security Policy, 브라우저가 허용할 자원 출처 정책)와 위젯 및 API origin도 맞춘다. 브라우저의 `DEPOSIT_SETTLED`는 화면 알림이며 탭을 닫으면 성공한 입금의 이벤트를 받지 못할 수 있다고 문서가 명시한다. 서버 webhook과 최종 상태를 대사해야 한다. webhook은 서비스가 서버에 사건을 전달하는 호출이다. 이 처리의 중복 방지와 누락 복구는 실제 앱에서 따로 확인한다.

구현 제안으로는 세션 생성 요청과 반환된 식별자, 연결한 사용자와 목적 지갑 및 이후 확인한 결과를 같은 업무 기록에서 추적하도록 한다. 통지를 받았다는 사실과 그 통지를 업무에 반영했다는 사실도 구별한다. 같은 결과를 반복 전달받거나 조회로 다시 발견했을 때 업무를 중복 완료하지 않는지, 통지를 받지 못했을 때 결과를 찾아 반영할 수 있는지가 후속 시험의 질문이다. 이 질문은 아래 실패 처리와 검증 실험으로 이어진다.

[Onramp hosting requirements](https://docs.arc.io/app-kit/references/onramp-hosting-requirements.md)는 sandbox가 실제 자금을 움직이지 않으며, 입금 이벤트로 `settlementExpected: false`가 포함된 `DEPOSIT_SUBMITTED`만 발생한다고 설명한다. `DEPOSIT_SETTLED`는 SDK에 정의돼 있지만 sandbox에서는 발생하지 않는다. 시험 입금의 확인은 설정한 체인의 탐색기에서 목적 지갑의 USDC 잔액을 확인하도록 안내한다. 은행 이체의 시험 입금 버튼으로 보내는 자금은 Ethereum의 목적 지갑에만 도착한다고 적으므로 Arc 테스트넷의 일반 결제 성공으로 확대하지 않는다.

[Handle lifecycle events](https://docs.arc.io/app-kit/tutorials/onramp/handle-lifecycle-events.md)는 위젯이 `postMessage`로 보낸 이벤트를 구독하는 방법을 안내한다. 세션 만료는 `onSessionExpired`에서 새 세션을 만든 뒤 기존 `widget.close()`를 호출하고 다시 표시할 수 있다. 세션은 생성 후 30분 동안 유효하다. 브라우저 이벤트는 화면 갱신에 사용하고, 최종 입금 상태는 서버의 webhook으로 대사한다. 사용자가 창을 닫아 `DEPOSIT_SETTLED`를 받지 못해도 입금이 완료될 수 있다. 이번 실험에서는 실제 입금, 이벤트 정산과 webhook 대사를 수행하지 않았다.

정상 실행의 기록을 정하면 오류를 만났을 때 마지막으로 확인한 효과에서 복구를 시작할 수 있다.

## 5. 실패 처리: 실행 상태를 어떻게 판별하고, 완료된 효과를 보존한 채 남은 작업을 어디서부터 재개하는가

실행이 기대대로 끝나지 않았을 때 개발자에게 필요한 것은 이미 가진 식별자와 이미 생긴 효과의 기록이다. 결과를 확인하지 못한 요청을 실패로 보고 새로 보내면, 원래 요청도 실행되어 같은 지급이 두 번 일어날 수 있기 때문이다. 그래서 실패 처리는 새 요청보다 기존 작업의 조회에서 시작한다. 아래 흐름도는 그 판단 순서이고, 5.1(실행 상태)은 상태의 구분을, 5.2(부분 성공)는 여러 단계 작업의 재개를, 5.3(오류 유형)은 오류별 다음 행동을, 5.4(조회 장애)는 결과를 읽지 못한 경우를 다룬다.

**실패 판단 흐름도: 기존 상태와 효과에서 다음 행동을 정한다**

화살표는 판단과 다음 조회 또는 처리다. 재조회 후에도 불명확하면 미확인 상태를 유지하며, 남은 작업의 조건 확인을 즉시 재실행으로 해석하지 않는다.

한국어:

```text
[오류 또는 결과 미확인]
           |
           v
[기존 식별자와 실행 단계 확인]
           |
           v
[실제 처리 상태와 효과를 확인할 수 있는가?]
           |
     +-----+--------------------+
     |                          |
   아니오                       예
     |                          |
     v                          v
[조회 조건과 장애 확인]    [어디까지 완료되었는가?]
     |                          |
     v                +---------+---------+
[기존 작업 재조회]     |                   |
                      v                   v
                [목표 효과 완료]    [남은 작업이 있음]
                      |                   |
                      v                   v
                [업무 기록 대조]    [완료 효과 보존]
                                          |
                                          v
                              [실패 원인과 재개 조건 확인]
```

English:

```text
[Error or unobserved result]
             |
             v
[Check existing IDs and execution stage]
             |
             v
[Can processing state and effects be established?]
             |
       +-----+---------------------+
       |                           |
       No                         Yes
       |                           |
       v                           v
[Query setup/errors]       [What has already completed?]
       |                           |
       v                 +---------+---------+
[Requery existing work]   |                   |
                         v                   v
                 [Target effect done]  [Work remains]
                         |                   |
                         v                   v
                  [Reconcile records] [Preserve completed effects]
                                             |
                                             v
                              [Check cause and resumption conditions]
```

### 5.1 실행 상태: 제출 거절, 실행 실패와 결과 미확인은 다음 행동이 다르다

실패를 처리하려면 먼저 요청이 지금 어떤 실행 상태인지 알아야 한다. 상태에 따라 다음 행동이 달라지기 때문이다. 요청이 실행 전에 거절됐다면 입력과 권한 등의 원인을 수정할 수 있다. 이미 실행된 실패라면 그 실행이 남긴 비용과 순번 및 대상 효과를 확인해야 한다. 결과를 확인하지 못했다면 실패를 확정하기보다 기존 작업을 추적해야 한다. 상태를 판별하는 방법은 아래 문단과 그림이 설명한다. 이 구분은 이 원고에서 체인 요청의 관측을 정리한 것이며 서비스의 개별 상태 이름을 대체하지 않는다.

공식 글 연결: [Unified Balance Kit: Pending & Funds-in-Motion States](https://www.arc.io/blog/unified-balance-kit-designing-for-pending-and-funds-in-motion-states) (2026-06-12, [공식 원문](https://www.arc.io/blog/unified-balance-kit-designing-for-pending-and-funds-in-motion-states)). Unified Balance 글은 아직 가용해지는 중인 잔액과 전송 중인 자금을 나누어 표시한다. 앱 잔액 상태의 사례이며 노드의 거래 상태 정의를 대체하지 않는다.

잘못된 입력과 권한, 잔액 또는 수수료 조건으로 제출 전에 거절된 요청과 체인에 포함된 실행 실패는 다르다. 사전 호출이나 가스 추정의 revert도 실제 서명 거래가 포함된 사건은 아니다. 포함된 status 0 영수증은 실행 실패이며 nonce와 가스의 효과를 읽어야 한다.

영수증이 없으면 미관측 상태다. 거래가 대기 중일 수도 있고 제출 거절과 탈락, 공급자의 조회 장애 또는 잘못된 체인 및 해시일 수도 있다. [Transaction Lifecycle](https://docs.arc.io/integrate/wallets/transaction-lifecycle.md)는 거래가 mempool에 있는 pending 상태이거나 committed block에 포함된 final 상태라고 설명하며 중간 confirming 상태와 누적 확인 수를 사용하지 않는다고 적는다. 이 체인 상태 모델만으로 앱의 모든 미관측 상태를 분류하지는 않는다. 타임아웃에서 새 nonce로 같은 지급을 보내면 원래 요청도 실행되어 중복 지급이 될 수 있다.

EOA 거래에서는 기존 해시와 계정의 논스(nonce, 거래 순번), 해당 블록의 대상 효과를 함께 읽는다. 이미 포함된 실패의 nonce 소비와 아직 대기 중인 거래를 같은 nonce로 교체하는 작업은 다른 상황이다. 계약 지갑의 UserOperation(ERC-4337에서 서명하고 제출하는 사용자 작업)과 서비스 거래 객체를 EOA 순번 하나로 일반화하지 않는다. [AA 소개](https://docs.arc.io/arc/tools/account-abstraction.md)는 여러 bundler(사용자 작업을 거래로 묶는 처리자)와 paymaster(가스를 지원하는 구성 요소)를 소개한다. 소개 목록은 해당 계정의 실제 접근과 가용성 검증이 아니다.

**거래 결과의 확인: 앱이 구별할 상태와 질문**

한국어:

```text
[거래 제출]
     |
     +-- 접수 전 거절
     |
     +-- 접수
           |
           +-- 아직 결과 미확인 / 대기
           |
           +-- 블록 포함과 확정 여부 확인
                         |
                         v
                  [실행 결과 확인]
                    /         \
                   v           v
              [실행 성공]  [실행 실패]
                   |
                   v
        [기대한 잔액과 계약 상태 대조]
                   |
                   v
        [업무에 필요한 추가 처리 확인]

범위: 앱의 확인 관점이며, 노드 내부의 처리 순서를 나타내지 않는다.
확정된 거래도 실행에 실패할 수 있다.
```

English:

```text
[Transaction submission]
          |
          +-- Rejected before acceptance
          |
          +-- Accepted
                |
                +-- Result unknown / pending
                |
                +-- Check block inclusion and finality
                                  |
                                  v
                         [Check execution result]
                             /             \
                            v               v
                     [Succeeded]        [Failed]
                            |
                            v
               [Compare expected balance and contract state]
                            |
                            v
               [Check further processing required by the task]

Scope: app checks, not the internal processing order of nodes.
A finalized transaction can have failed execution.
```

[거래 수명주기의 Runtime revert](https://docs.arc.io/integrate/wallets/transaction-lifecycle.md)는 차단 검사가 실행 중 실패한 거래도 블록에 포함되고 `status: 0` 영수증을 남기며, 가스를 소비하지만 시도한 상태 변경은 revert한다고 설명한다. 거래는 final에 도달했지만 성공한 것은 아니다. 소비한 nonce는 사용됐으므로 이 경우의 재실행은 새 거래와 새 nonce를 요구한다. mempool에서 탈락하거나 대기 중인 거래를 같은 nonce로 교체하는 상황과 구분한다.

앞 그림의 첫 분기에서 접수 전 거절은 네트워크에 받아들여지지 않은 경우이고, 접수 후 결과 미확인은 아직 앱이 처리 결과를 확인하지 못한 경우다. 조회 응답을 얻지 못했다는 사실만으로 거래가 실행되지 않았다고 결론 내릴 수는 없다. 앱의 관측 상태와 체인의 실제 처리 상태를 구별해야 중복 제출을 방지할 수 있다. 거래 수명주기 문서가 설명하는 대기 및 거래 풀에서 제거되는 경우도 이 구별 안에서 확인해야 한다.

### 5.2 부분 성공: 여러 단계로 된 작업은 완료된 단계를 보존하고 남은 단계를 재개한다

체인 간 이전처럼 여러 단계로 된 작업에서는 일부 단계의 효과는 확인됐지만 최종 목표의 달성은 확인되지 않는 상황이 생긴다. 여기에는 실제로 남은 작업이 있는 상황과 마지막 결과를 아직 조회하지 못한 상황이 포함된다. 이런 작업을 구현하는 개발자에게는 업무 전체의 목적과 단계별 완료 근거를 함께 보존하는 기록이 필요하다. 그 기록이 없으면 이미 끝난 단계를 놓치거나 다시 실행하게 되기 때문이다. 복구 방법은 이미 완료된 작업은 유지하고, 결과가 미확인인 단계는 먼저 조회하며, 미완료가 확인된 단계는 재개 조건을 점검하는 것이다. 아래 브리지 사례는 이 원칙을 자산 소각과 목적 체인 발행에 적용한 것이다.

[Bridge 복구 안내](https://docs.arc.io/app-kit/references/bridge-error-recovery.md)는 approve, burn, fetchAttestation와 mint를 나눈다. 아래는 USDC의 burn-and-mint 경로를 설명한다. approve는 자산 사용 승인, burn은 출발 체인의 소각, attestation은 소각 사건의 증명, mint는 목적 체인의 발행이다. 다른 자산의 포장 및 잠금 경로에도 같은 소각 단계가 있다고 일반화하지 않는다. 중간 장애에서 요청 전체가 미실행됐다고 보면 이미 소각된 자산을 놓친다.

한국어:

```text
[approve 완료] -> [burn 완료] -> [증명 확보] -> [mint 결과 미관측]
                                                     |
                                                     v
                                         [목적 체인 효과 재조회]
                                                     |
                          +--------------------------+----------------+
                          |                                           |
                          v                                           v
                     [이미 완료: 대사]                   [미완료 확인: 남은 단계 재개]
```

English:

```text
[approve done] -> [burn done] -> [attestation obtained] -> [mint result unobserved]
                                                              |
                                                              v
                                                   [Requery destination effects]
                                                              |
                                +-----------------------------+----------------+
                                |                                              |
                                v                                              v
                         [Already done: reconcile]                 [Confirmed incomplete: resume]
```

이 그림은 ChatGPT 답변의 mint 실패와 재개 설명에 효과 재조회를 추가했다. 화살표는 처리 순서와 다음 판단이며 mint 타임아웃을 확정된 실패로 쓰지 않는다. `BridgeResult`와 단계별 이름, 상태 및 거래 해시와 오류를 보존하고 같은 from 및 to 구성으로 재개한다. 조회한 결과에서 완료됐으면 대사하고, 미완료가 확인되면 남은 단계의 조건을 수정한다.

미실행 항목: [Bridge 오류 복구](https://docs.arc.io/app-kit/references/bridge-error-recovery.md)는 입력 검증, 설정과 인증 같은 hard error는 예외를 던지고, 실행 중 발생한 soft error는 복구에 필요한 거래 정보를 반환한다고 설명한다. `BridgeResult`의 `state`, 각 단계의 이름과 상태, `txHash`와 오류를 저장한 뒤 실패한 결과에 `kit.retry(result, { from: sourceAdapter, to: destinationAdapter })`를 사용할 수 있다. 복구 전에는 어느 단계가 완료됐는지 확인한다. 이 예제는 어댑터 설정을 마친 상태에서 사용하는 복구 코드이며 모든 경우에 재시도가 성공한다는 실험 결과가 아니다.

[Unified Balance deposits의 복구](https://docs.arc.io/app-kit/references/unified-balance-error-recovery.md)는 다른 규칙을 둔다. FAST 입금의 `PENDING`은 출발 거래를 제출했다는 뜻이며 burn 성공을 확인한 결과는 아니다. 성공 영수증으로 burn을 확인한 뒤에는 같은 입금을 다시 제출하지 않고 기존 입금을 감시한다. `DONE` 결과의 txHash는 목적 relay 거래이고 `PENDING` 및 `FAILED`의 txHash는 출발 burn 거래다. 대체된 거래라면 성공 상태만 보지 말고 원래 burn과 계약 주소 및 calldata나 burn 이벤트가 맞는지도 확인한다.

공식 글 연결: [Unified Balance Kit: Safeguards and Recovery for spend()](https://www.arc.io/blog/unified-balance-kit-production-safeguards-and-recovery-patterns-for-spend) (2026-06-19, [공식 원문](https://www.arc.io/blog/unified-balance-kit-production-safeguards-and-recovery-patterns-for-spend)). spend 복구 글은 일부 목적 mint 실패의 재시도 경로를 설명한다. 앞의 deposit 복구와 다른 경로이며, deposit에 공개 retry가 없다는 기존 조건을 바꾸지 않는다.

FAST 입금의 burn이 성공했다면 IRIS에서 `forwardState`와 `forwardTxHash`로 목적 입금을 확인한다. attestation을 나타내는 최상위 `status`만으로 forwarding 완료를 판단하지 않는다. 목적 relay가 실패하면 먼저 수취인의 Unified Balance를 확인하고 출발 해시와 환경 및 금액을 Circle Support에 전달한다. 문서는 이미 발생한 burn에 대한 공개 retry 메서드를 제공하지 않는다고 명시한다. Bridge의 `retry()`에 Unified Balance 입금 결과를 넘기거나 새 `deposit()` 및 `depositFor()`를 복구 요청으로 보내지 않는다. STANDARD 같은 체인 입금은 구조화된 오류를 던지며 FAST의 progress 상태를 반환하지 않는다.

4.2(체인 실행)의 일괄 호출은 한 거래 안의 실패 정책이다. Multicall3From에서 `allowFailure: false`인 하위 호출이 실패하면 전체 거래가 revert한다. `allowFailure: true`를 선택한 경우에는 각 `Result.success`와 반환 데이터를 처리해야 하며 상위 거래의 성공만으로 모든 전송이 성공했다고 쓰지 않는다. 이는 CCTP에서 이미 완료된 burn을 보존하고 목적 체인의 남은 단계를 재개하는 경우와 다른 범위다.

잘못된 adapter를 생성자나 입력 검사에서 거절하면 burn 후의 부분 성공 시험이 아니다. 목적 체인의 가스와 RPC 또는 실제 실패 단계를 통제하고 어디까지 완료됐는지 확인해야 한다. SDK의 `retry`와 상태 보존 설명은 복구 절차의 근거이며 모든 장애에서 중복 없이 성공한다는 실제 검증은 아니다.

### 5.3 오류 유형: 오류가 난 단계와 이미 생긴 효과에 따라 재조회, 수정, 재개를 고른다

오류를 받았을 때 개발자에게 필요한 것은 오류 유형과 실제 실행 상태를 함께 읽는 방법이다. 오류 유형은 원인을 설명하는 정보일 뿐이어서, 같은 오류 이름이라도 이미 생긴 효과에 따라 다음 행동이 달라지기 때문이다. 나는 이 원고에서 오류가 난 위치, 그 전에 만들어진 식별자와 효과 및 원인을 수정할 수 있는 주체를 함께 확인하는 방식을 제안한다. 위치는 앱의 입력 검사, 인증과 승인, 외부 제출, 실행 또는 결과 조회 등으로 기록한다. 이 위치 구분은 설명을 위한 것이며 여러 SDK의 오류 코드를 하나의 공식 분류로 바꾸는 규칙은 아니다.

예를 들어 권한 오류는 필요한 자격이나 승인을 수정할 주체를 찾아야 하고, 이용 한도 오류는 요청 빈도와 해당 서비스의 정책을 확인해야 한다. 타임아웃은 기존 요청이 실행됐는지부터 조회해야 하며, 실행 중 발생한 실패는 그 실행의 효과와 원인을 확인해야 한다. 같은 오류 이름이라도 어느 단계에서 발생했는지에 따라 재조회, 원인 수정이나 남은 작업 재개가 달라진다. 따라서 오류 코드만으로 같은 업무를 새 요청으로 보내는 분기를 만들지 않는다.

같은 네트워크 오류를 만난 상황도 나누어 볼 수 있다. 전송 전에 체인 식별자를 읽다가 실패했다면 우선 접속 설정과 조회를 복구한다. 전송 요청을 보낸 뒤 응답을 받지 못했다면 기존 요청의 식별자와 대상 효과를 추적한다. 브리지의 출발 체인 소각을 확인한 뒤 목적 체인의 결과를 읽지 못했다면 완료된 소각을 보존하고 목적 체인의 상태를 조회한다. 오류 이름은 같아도 이미 발생한 효과가 달라 다음 행동도 달라지는 설명용 사례다.

현재 [Onramp 오류 문서](https://docs.arc.io/app-kit/references/onramp-error-handling.md)는 App Kit의 `KitError`를 설명한다. 이 표의 한 행은 해당 문서의 type와 개발자가 검토할 다음 행동이며 모든 SDK 및 RPC의 공통 오류 체계가 아니다.

| KitError type | 문서의 기본 HTTP 대응 | 다음 행동과 유지할 기록                                                                                                |
| ------------- | --------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| INPUT         | 400                   | 입력과 자격 및 환경을 수정한다. 재요청 전에 기존 객체나 작업이 만들어졌는지 확인한다.                                  |
| RATE_LIMIT    | 429                   | 이용 한도와 백오프(backoff, 재요청 사이의 대기 시간을 조정하는 방식)를 확인한다. 같은 업무의 요청과 식별자를 보존한다. |
| NETWORK       | 504                   | 연결 및 타임아웃을 확인하고 기존 작업의 상태를 먼저 읽는다.                                                            |
| SERVICE       | 502                   | 제공자 응답과 권한 및 서비스 상태를 확인한다. 실제 객체와 효과를 함께 기록한다.                                        |
| RPC           | 502                   | 조회 오류와 체인 제출 및 실행 오류를 구별한다.                                                                         |
| UNKNOWN       | 500                   | 원인을 추가 확인하고 효과가 미관측인 요청을 임의로 새 지급으로 만들지 않는다.                                          |

type와 `recoverability`의 RETRYABLE, RESUMABLE 및 FATAL을 제어 흐름에 사용하도록 안내한다. 각각 재시도, 남은 단계 재개와 원인 수정 없이 계속할 수 없는 오류를 구별하는 문서 용어다. name과 code는 정확한 일치 및 기록에 사용하며, 진단 메시지를 사용자에게 그대로 노출하기 전에 검토한다. 예를 들어 키 오류 1907, origin 불일치 1910, 브라우저 환경 부재 1914 및 session route 거절 8923은 원인이 다르다.

[Gas and fees의 Common errors](https://docs.arc.io/arc/references/gas-and-fees.md)는 `transaction underpriced`일 때 `maxFeePerGas`가 최소 20 Gwei보다 낮은지 확인하고, `intrinsic gas too low`일 때 단순 전송은 최소 21,000 gas, 계약 호출은 `eth_estimateGas`로 확인하도록 안내한다. `insufficient funds for gas * price + value`는 USDC가 전송액과 가스를 함께 충당하지 못하는 경우다. 문서의 상한 계산은 `value + maxFeePerGas x gasLimit`이며 native USDC의 단위로 계산한다. 제출 결과가 불명확하다면 이 오류 분류만으로 같은 지급을 새로 보내지 않고 기존 거래를 조회한다.

route는 POST 이외에 405, JSON 해석 실패에 400, authorize가 false이면 401도 반환한다. widget의 `INITIALIZATION_ERROR`는 런타임 이벤트이며 함수 throw와 별도다. 일반 로그에는 단계와 환경 및 업무 ID, 오류 타입과 코드, 이미 관측한 효과 및 다음 행동을 남긴다. 비밀 키와 복구 파일 또는 전체 인증 헤더는 기록하지 않는다.

### 5.4 조회 장애: 결과를 읽지 못했을 때는 새 거래가 아니라 조회 경로를 복구한다

조회 장애는 앱이 외부 상태를 읽지 못하는 문제이며, 그것만으로 기존 거래의 실행 여부를 알 수는 없다. 그래서 조회가 실패했을 때 개발자가 할 일은 새 거래를 보내는 것이 아니라 조회 경로를 복구하는 것이다. 방법은 조회 중인 네트워크와 식별자, 요청 범위와 제공자 응답을 먼저 확인하고, 조회 조건을 수정하거나 기존 작업을 다시 읽는 행동과 새 거래를 승인해 제출하는 행동을 구분해서 기록하는 것이다. 아래 범위 및 높이 오류는 조회 경로를 복구해야 하는 사례이고, 뒤의 문서 충돌은 실행 결과를 판단할 근거를 더 확인해야 하는 사례다.

[RPC 문서](https://docs.arc.io/arc/references/rpc-endpoints.md)는 `eth_getLogs`에 10,000블록 범위 한도와 초과 오류 -32012, 9,999블록 이하의 분할 조회를 안내한다. 최신 높이 부근의 -32014는 부하 분산된 서로 다른 노드의 높이 차이일 수 있다고 설명한다. 읽기 요청의 백오프와 범위 분할이 계약 또는 지급을 다시 실행하라는 뜻은 아니다.

[EVM differences](https://docs.arc.io/arc/references/evm-differences.md)는 20 Gwei보다 낮은 `maxFeePerGas`를 가진 거래가 mempool에서 조용히 탈락하고 오류 영수증도 블록 기록도 남지 않는다고 설명한다. [Gas and fees](https://docs.arc.io/arc/references/gas-and-fees.md)는 같은 하한 아래의 거래가 무기한 대기하거나 실패할 수 있다고 적고 common errors에는 `transaction underpriced`를 제시한다. [Transaction Lifecycle](https://docs.arc.io/integrate/wallets/transaction-lifecycle.md)는 포함된 runtime revert가 `status: 0` 영수증을 남긴다고 명시한다. 문서의 이 설명들을 모두 같은 노드 응답으로 통일하지 않는다. 실제 RPC와 클라이언트 및 버전에서 사전 거절, 탈락과 포함된 실패를 별도로 시험해야 한다. 이번 작업은 이 응답을 새로 실행해 확인하지 않았다.

## 6. 검증과 제출(부록): 이 안내를 실험으로 어디까지 확인했고, 프로그램 요구와는 어떻게 대조하는가

이 절은 부록이다. 앱을 만드는 개발자에게 필요한 내용은 1절(구현 경로)에서 5절(실패 처리)까지이고, 이 절은 이 리서치가 안내를 실험으로 확인하고 프로그램 제출을 준비하는 데 쓰는 기록을 모은다. 6.1(검증 실험)의 실험표는 실험마다 답할 질문과 2026-10-07에 실행한 실험의 결과, 아직 실행하지 않은 실험을 함께 적는다. 6.2(재현 기록)는 그 결과를 남길 형식, 6.3(제출 조건)은 프로그램 요구와의 대조, 6.4(미확인 사항)는 아직 확인하지 못한 기능과 추가 검증이 필요한 질문이다.

**검증 관계도: 질문과 예상, 관측에서 결론까지**

화살표는 검증 설계와 해석의 의존 관계다. 실제 관측이 없는 실험은 아래 실험표처럼 미실행으로 남긴다.

한국어:

```text
                    [검증할 질문]
                          |
                          v
                 [필요한 환경과 권한]
                          |
                          v
                   [실험과 관측 방법]
                          |
             +------------+------------+
             |                         |
             v                         v
       [근거에 따른 예상]       [실제 응답과 대상 효과]
             |                         |
             +------------+------------+
                          |
                          v
                 [일치와 차이의 설명]
                          |
                          v
             [근거가 뒷받침하는 결론과 한계]
```

English:

```text
                  [Validation question]
                            |
                            v
              [Required environment and authority]
                            |
                            v
              [Experiment and observation method]
                            |
               +------------+------------+
               |                         |
               v                         v
      [Supported expectation]   [Actual response and effects]
               |                         |
               +------------+------------+
                            |
                            v
              [Explain agreements and differences]
                            |
                            v
              [Supported conclusion and its limits]
```

### 6.1 검증 실험: 실험마다 답할 질문을 정하고, 실행한 실험의 결과를 적는다

검증 실험은 구현의 어떤 설명을 확인하려는지 먼저 정하고, 그 설명에 필요한 입력과 관측을 연결하는 작업이다. 정상 전송의 실험이라면 의도한 자산 이동과 비용을 확인하고, 실패 복구의 실험이라면 장애가 발생한 단계와 이미 완료된 효과 및 재개 결과를 확인해야 한다. 성공 화면이 나타났다는 관측만으로 두 질문에 모두 답할 수는 없다. 아래 실험표는 앞에서 구분한 환경, 권한과 결과 및 복구를 각각 확인할 질문으로 바꾼 것이다.

아래는 세 답변의 실험안을 내가 질문별로 연결한 계획이다. 한 행은 다른 설명을 검증할 실험 하나다. 순서는 필요한 환경과 권한 및 의존 조건을 갖추는 기준이며 예상 가치가 낮다고 입력을 제외하지 않는다. 2026-10-07 실험은 앞의 네 행과 서비스 API 행의 일부를 실행했고, 그 결과를 오른쪽 열에 적었다. 나머지 행은 아직 실행하지 않았다.

| 질문과 실험                                             | 예상 근거와 기록할 실제 자료                                                                            | 현재 범위 및 결론의 한계                                                                                                                                                                                                                                                    |
| ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| RPC가 의도한 체인인가?                                  | chain ID, 공급자와 UTC 시각, 최신 블록과 조회 오류를 보존한다.                                          | 기존 읽기 응답은 2026-10-05 UTC의 관측이다. 2026-10-07 실험에서는 `https://rpc.testnet.arc.io`의 chain ID가 5042002로 연결 문서의 값과 같았다. 어느 관측도 모든 API 지원과 거래 성공을 입증하지 않는다.                                                                     |
| 두 정수 인터페이스가 같은 잔액인가?                     | 같은 주소와 블록의 네이티브 및 ERC-20 잔액을 기록하고 소수 및 절삭을 비교한다.                          | 실행했다(2026-10-07). 블록 65952222에서 네이티브 20000000000000000000과 ERC-20 20000000(`decimals()` 6)이 같은 20 USDC였다. 한 지갑과 한 블록의 관측이며, 다른 시점의 잔액을 단위 검증에 쓰지 않는다.                                                                       |
| Counter의 의도한 함수가 상태를 바꾸는가?                | 코드 및 compiler, 주소와 시작 상태, 서명 요청과 해시 및 영수증과 종료 상태를 기록한다.                  | 실행했다(2026-10-07). `increment()` 뒤 `number()`가 0에서 1이 되었고, 소스 검증은 solc 0.8.37에서 실패하고 0.8.36에서 통과했다. 단순 계약의 성공은 외부 서비스와 업무 성공을 입증하지 않는다.                                                                               |
| USDC 이전과 가스 및 로그가 맞는가?                      | 인터페이스와 정수 금액, 같은 블록 기준의 전후 상태와 가스 및 방출 주소를 대조한다.                      | 실행했다(2026-10-07). 네이티브 전송 두 건에서 수취인의 변화, 수수료와 송신인의 감소가 맞았고, 문서 예제의 `parseUnits("1", 6)`은 10^-12 USDC를 보냈다. 로그는 네이티브 전송에서 하나, Faucet의 ERC-20 `transfer`에서 둘이었다. 로그 두 개를 지급 두 번으로 합산하지 않는다. |
| 로컬 revert와 접수 거절 및 포함된 실패는 어떻게 다른가? | 통제된 시험 계약과 사전 호출, 가스 추정 및 실제 제출의 오류와 영수증, 가스와 nonce를 나눈다.            | 미실행이다. simulation의 실패를 실제 자산 효과로 쓰지 않는다.                                                                                                                                                                                                               |
| 수수료와 차단 및 로그 범위의 경계는 무엇인가?           | 선택 제공자에서 최저 수수료와 차단된 주소, 조회 범위 초과의 응답과 상태를 각각 기록한다.                | 미실행이다. chain과 서비스 심사 및 RPC 읽기 오류를 합치지 않는다.                                                                                                                                                                                                           |
| 한도는 어디에서 실제로 집행되는가?                      | 앱, 서명자와 계약 및 대납의 허용과 초과, 권한 변경 및 우회 요청을 비교한다.                             | 미실행이다. Agent Wallet 지출 정책의 테스트넷 미지원과 대납의 첫 거래 예외를 유지한다.                                                                                                                                                                                      |
| bridge의 부분 성공 뒤 무엇을 재개하는가?                | burn 전후와 증명 및 mint 단계에 장애를 넣고 출발과 목적 거래, 저장 결과와 재개 및 중복 효과를 확인한다. | 미실행이다. adapter 사전 거절만으로 부분 성공을 검증했다고 쓰지 않는다.                                                                                                                                                                                                     |
| 선택 API의 인증 및 실패와 완료를 추적하는가?            | 자격을 확보한 뒤 키 및 입력 오류, 서비스 ID와 webhook 및 최종 상태, 반복 처리와 누락의 효과를 기록한다. | 일부 실행했다(2026-10-07). API 키의 인증 성공과 가짜 키의 401, Onramp 세션 발급과 sandbox 위젯 표시를 확인했다. 입력 오류, 서비스 ID와 webhook 및 최종 상태는 실행하지 않았고, Compliance의 승인 조건도 확인하지 않았다.                                                    |
| 제출 환경에서 같은 구현을 재현하는가?                   | 실제 환경과 주소 및 키, 자산과 서명 모형, 라이브 링크 및 저장소와 공고 조건을 다시 대조한다.            | 미실행이다. chain ID만 바꾸어 서명된 거래를 그대로 보낸다는 실험을 채택하지 않는다.                                                                                                                                                                                         |

Grok의 메인넷 실험은 같은 바이너리와 서명된 거래를 구별해야 한다. 같은 계약 bytecode를 다른 네트워크에서 새로 서명해 배포하는 것과 잘못된 chain ID로 서명한 거래를 전송하는 것은 다르다. 후자의 서명 도메인 시험은 통제된 로컬 환경에서 정하고, 올바른 서명의 잔액 부족 및 권한 오류와 합치지 않는다. 이번 리서치의 목표는 그 실험을 설계하는 것이며 메인넷 거래를 전송하는 일이 아니다.

실패 복구의 실험에서는 장애를 넣을 위치와 실제 도달한 단계를 먼저 확인해야 한다. 예를 들어 목적 체인의 결과 조회 장애를 시험하려고 했는데 입력 검사에서 요청이 거절됐다면 원래 질문에 답한 것이 아니다. 정상 경로에서 필요한 식별자와 상태를 확보한 뒤 통제된 장애 조건을 적용하고, 기존 효과를 보존하는지와 남은 단계의 결과를 비교한다. 예상과 다르다면 실제로 시험한 범위를 기록하고 원래 질문은 미확인으로 남긴다. 모든 실패 조건을 임의로 성공 또는 실패 한 칸에 합치지 않는다.

### 6.2 재현 기록: 실험 결과를 다른 사람이 다시 확인할 수 있는 자료로 남긴다

재현 기록은 다른 사람이 같은 조건에서 같은 질문을 다시 확인할 수 있도록 만드는 자료다. 환경 정보는 시험 대상을 고정하고, 입력과 예상은 확인하려던 내용을 설명하며, 원문 응답과 대상 효과는 실제로 관측한 내용을 보여준다. 복구 기록은 최초 요청과 이후 행동이 같은 업무의 어느 단계에 해당하는지를 연결한다. 이 관계가 있어야 정상 결과만 반복한 것인지, 실제 장애 이후 남은 작업을 복구한 것인지 구분할 수 있다.

한 장의 성공 화면보다 환경과 입력, 실제 결과 및 복구의 연결이 중요하다. 아래는 ChatGPT 답변의 실행 증거 묶음 그림을 내가 재현에 필요한 관계로 바꾼 것이다. 예시 파일과 기록은 다음 구현에서 만들 자료이며 현재 모두 생성돼 있다는 뜻은 아니다.

한국어:

```text
[환경 기록: 커밋/lockfile/실제 버전/체인/주소/시각]
                             |
                +------------+-------------+
                |                          |
                v                          v
       [정상 요청과 예상]           [실패 조건과 예상]
                |                          |
                v                          v
       [응답/영수증/실제 효과]       [오류/기존 효과/남은 단계]
                |                          |
                +------------+-------------+
                             v
                 [예상과 관측의 대조 및 재개 기록]
                             |
                             v
                 [같은 조건에서 재현할 절차와 한계]
```

English:

```text
[Environment: commit/lockfile/resolved versions/chain/addresses/time]
                                  |
                   +--------------+---------------+
                   |                              |
                   v                              v
          [Normal request and expectation] [Failure condition and expectation]
                   |                              |
                   v                              v
          [Response/receipt/actual effects] [Error/prior effects/remaining steps]
                   |                              |
                   +--------------+---------------+
                                  v
                     [Compare expectation/observation and recovery]
                                  |
                                  v
                      [Reproduction under the same conditions and limits]
```

환경 기록은 어떤 코드와 노드 및 자산을 대상으로 했는지 정한다. 정상과 실패의 예상은 문서에서 가져오되 실제 응답 및 대상 효과와 다른 칸에 둔다. 재개 자료에는 완료 단계를 유지하고 남은 작업을 어떻게 처리했는지 적는다. 그림의 화살표는 기록의 의존 관계이며 자동으로 만들어지는 SDK의 증거 폴더를 뜻하지 않는다.

실행 결과에는 원문 응답과 transaction 또는 UserOperation 및 서비스 ID, 대상 상태와 로그 및 화면과 시각을 연결한다. 읽기 요청은 실행 명령과 응답으로 확인할 수 있지만 서명과 비밀은 그대로 출력하지 않는다. 검증 실패도 삭제하지 않고 문서의 기대와 실제 응답이 어떻게 달랐는지 남긴다. 이런 자료가 있어야 프로그램 평가와 연구의 후속 판단에서 같은 구현을 다시 확인할 수 있다.

### 6.3 제출 조건: 프로그램이 요구하는 환경과 결과물을 구현의 준비 상태와 대조한다

**제출 요구 대조표: 한 행은 선택 공고에서 확인할 요구 종류다.**

| 요구 종류   | 공고에서 확인할 내용       | 구현에서 대조할 자료           | 부족하면 보완할 대상 |
| ----------- | -------------------------- | ------------------------------ | -------------------- |
| 실행 환경   | 네트워크와 자산            | 실제 실행 환경과 주소          | 배포와 설정          |
| 기능과 결과 | 요구한 사용 사례           | 정상 처리와 복구의 근거        | 구현과 검증          |
| 접근 자격   | 계정과 참가 승인           | 실제 확보한 권한               | 신청과 승인          |
| 제출물      | 저장소와 실행 링크, 설명   | 제출 가능한 결과물과 재현 절차 | 제출 자료            |
| 이용 증거   | 사용자 또는 실제 사용 요구 | 해당 요구에 맞는 기록          | 이용과 관측 자료     |

제출 준비는 앞에서 검증한 기술 결과를 선택 공고의 요구와 연결하는 과정이다. 구현이 동작한다는 증거와 참가 자격을 충족했다는 증거는 역할이 다르다. 나는 요구별로 대응하는 자료를 연결하고, 준비 상태를 설명할 때 구현 보완과 시험 보완 및 신청이나 제출물 준비를 구별하도록 제안한다. 예를 들어 필요한 라이브 링크가 없다면 계약 시험의 성공으로 그 요구를 충족했다고 대신 설명할 수 없다.

정상과 실패의 증거를 만들더라도 참가 조건은 별도로 충족해야 한다. 요구한 네트워크와 자산, 접근 계정과 제출물, 라이브 링크 및 공개 저장소, 실제 사용자 또는 사용 증거와 제출 및 지급 조건을 해당 공고에서 확인한다. 기능별 접근 조건과 공고의 기준일 및 요구 사항을 구현의 실제 준비 상태와 대조한다.

메인넷이 필요한 프로그램이면 실제 자금과 키 및 승인, 주소와 비용 및 회복 경로를 그 환경에서 확보해야 한다. 테스트넷을 허용하더라도 실제 이용이나 제출물의 다른 조건이 없어지는 것은 아니다. 공개 RPC로 시작할 수 있다는 사실과 기관 가입 및 프로그램의 선정, 지급과 개인 토큰 배분은 다른 조건이다.

[Arc Litepaper의 Applications와 법률 조건](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/Arc%20Litepaper%20-%202025.pdf)은 개발 사용 사례와 상품별 조건을 설명한다. [Arc Token Whitepaper의 Platform Access Programs](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/arc_whitepaper.pdf)는 플랫폼 접근, 수수료 혜택과 생태계 프로그램을 제안 설계의 예시로 제시하며 확정된 권리나 참가 자격을 부여하지 않는다. 따라서 paper의 사용 사례와 프로그램 예시를 현재 공고의 선정, 보상이나 개인 토큰 자격으로 대신 쓰지 않는다.

### 6.4 미확인 사항: 확정하지 않은 기여와 남은 질문을 확인할 곳에 연결한다

미확인 사항은 현재 설명의 적용 범위를 정하고 다음에 필요한 조사를 구체화한다. 아래 표는 구현에 필요한 설치와 계정 조건, 프로그램의 보상과 개인 자격을 구별해 확인할 자료를 제시한다. 모든 항목을 이 개발 안내에서 결론 내린 것은 아니다.

한 행은 현재 사실로 확정하지 않은 기능이나 질문 하나다. 미확인 상태가 해당 기능의 부재를 뜻하지는 않는다.

| 확인할 기능 또는 질문                                                                                                             | 확인 범위와 추가 조사                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ChatGPT 답변의 arc-fintech 의존 `app-kit ^1.15.0`, `developer-controlled-wallets ^10.3.1`, `viem ^2.41.2`                         | ChatGPT 답변의 저장소 열람 자기 보고다. 현행 커밋과 lockfile 및 실제 설치를 후속 구현에서 확인한다.                                                                                                                                                                                                                                                                                                                                                                                   |
| 같은 범위의 arc-commerce `app-kit ^1.15.1`, `developer-controlled-wallets ^10.8.0`, `viem ^2.56.5`, `wagmi ^3.7.7` 및 Node `>=22` | 현재의 공통 실행 버전으로 채택하지 않는다. 선택 저장소와 설치 기록에서 확인한다.                                                                                                                                                                                                                                                                                                                                                                                                      |
| Grok의 chain ID와 블록 높이 및 읽기 관측 보고                                                                                     | 같은 반환 자료의 자기 보고로 유지한다. 기존 별도 RPC 관측 자료와 조회 시각이 다르므로 숫자를 일치시키거나 같은 관측으로 세지 않는다.                                                                                                                                                                                                                                                                                                                                                  |
| Grok 답변의 faucet 주소 및 체인당 2시간마다 20 USDC, Claude 답변의 agent 지갑 최대 5개                                            | Grok 답변과 Claude 답변이 옮긴 문구와 적용 범위다. 2026-10-07 실험에서 Faucet에 한 번 요청해 20 USDC를 받아 금액은 Grok 답변의 문구와 맞았다. 요청 간격과 agent 지갑의 최대 수는 확인하지 않았으며, 자금과 접근을 준비할 때 해당 문서 및 계정에서 확인한다.                                                                                                                                                                                                                           |
| Grok 답변의 CCTP 방법 문서는 테스트넷만 대상으로 한다는 설명                                                                      | 메인넷 계약 주소의 게재와 샘플의 실행 대상이 같지 않다는 확인 질문으로 보존한다. 선택 구현에서 그 방법 문서와 현재 배포 및 실제 지원을 대조한다.                                                                                                                                                                                                                                                                                                                                      |
| Arc Studio와 ERC-8183, APS와 샘플 연결                                                                                            | [Arc Studio](https://docs.arc.io/ai/arc-studio.md)와 [Agentic Economy](https://docs.arc.io/build/agentic-economy.md)의 문서 설명은 확인해 2.2(개발 도구)와 4.2(체인 실행)에 반영했다. [Opt-in privacy](https://docs.arc.io/arc/concepts/opt-in-privacy.md)는 APS(Arc Privacy Sector, 공개 EVM과 함께 실행하는 Solidity 기밀 실행 환경)를 설명하면서 프라이버시 기능은 로드맵에 있으며 아직 이용할 수 없다고 명시한다. Studio 사용, ERC-8183 실행과 APS 배포는 이번에 시험하지 않았다. |
| 회사 참여와 프로그램 및 보상, 개인 토큰 자격                                                                                      | 발표와 실제 실행 및 선정과 지급을 구별한다. 해당 프로그램의 공고와 약관, 선정 통지 및 지급 기록을 확인해야 한다.                                                                                                                                                                                                                                                                                                                                                                      |
| Memo(추가 기록을 붙이는 계약), Multicall3From(원래 발신자를 유지하는 일괄 호출 계약)과 CallFrom(지정한 호출자로 실행하는 기능)    | [Transaction memos](https://docs.arc.io/arc/concepts/transaction-memos.md)와 [Batched transactions](https://docs.arc.io/arc/concepts/batched-transactions.md)의 호출 조건과 공식 튜토리얼을 확인해 4.2(체인 실행)에 반영했다. 문서의 계약 주소, 원래 EOA 보존, 로그와 단위 및 실패 조건은 설명할 수 있으나 2026-10-07 실험은 이 기능들을 다루지 않았다. 선택 구현의 실제 호출, 영수증 대조와 실패 시험은 미실행으로 남는다.                                                           |
| Permit2 권한                                                                                                                      | [Contract addresses](https://docs.arc.io/arc/references/contract-addresses.md)의 Permit2 주소와 StableFX를 위한 선행 USDC allowance 조건을 확인해 3.3(지출 한도)에 반영했다. 문서의 계약 설명은 AI 답변의 자기 보고에만 의존하지 않는다. 이번 실험에서는 Permit2를 다루지 않았으므로 선택 서명의 권한과 실제 허용량 및 실행 결과는 후속 시험 대상이다.                                                                                                                                |

이 안내가 지금 개발자에게 말할 수 있는 것은 만들 기능에 따라 경로를 고르고, 그 경로에 맞는 준비물과 권한을 갖추고, 실행 결과를 기록하고, 기존 효과를 조회해 다음 행동을 정하는 방법이다. 실험 관측:을 붙인 절차는 2026-10-07 테스트넷에서 한 번 실행해 동작을 확인한 것이며 운영 환경의 결과가 아니다. 미실행 항목:으로 남은 절차와 실제 운영 가능성, 오류 후 회복은 선택 계정과 배포 및 시험의 근거를 더 요구한다. 접근과 재현 조건의 확인을 모든 기능의 성공 또는 사용자 자격으로 올리지 않는다. 6.1(검증 실험)에 남은 실패, 한도와 부분 성공의 실험을 수행하면 그 결과도 같은 방식으로 본문에 적고, 정상과 실패의 자료를 다음 구현과 참가 판단의 입력으로 남긴다.
