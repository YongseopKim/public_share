# Arc 프로토콜: 거래 처리의 구조와 동작 및 신뢰 조건은 무엇인가

Arc에 서명한 거래를 보내면 어떤 결과를 확인할 수 있으며, 그 결과를 믿으려면 무엇을 전제해야 하는가? 이 원고는 Arc 프로토콜의 작동 조건을 설명한다. 공개 사용과 직접 검증 및 합의 투표, 거래 확정과 실행 성공, 규칙에 따른 처리와 규칙을 바꾸는 권한을 구별한다. 합의와 실행의 구성부터 참여 권한, 거래 처리, 합의 조건과 운영 권한, EVM 실행 환경, Arc의 EVM 차이 및 예정된 선택형 프라이버시를 설명한 뒤 보장 범위를 종합한다. 이 순서는 내가 정했으며, 각 결과를 이해하려면 처리 주체와 규칙 및 그 성립 조건을 함께 알아야 하기 때문에 나눴다.

이 목차는 정해진 분석 틀 하나를 따르지 않았다. 블록체인 프로토콜을 나누어 분석한 대표적인 틀 넷과 대조하면 아래와 같다. 틀은 내가 골랐다. 각각 Bitcoin 연구의 정리, 확장성 논의, 합의 프로토콜의 비교, rollup의 위험 평가라는 서로 다른 목적으로 프로토콜을 나누어 보기 때문에, 함께 대조하면 이 원고가 빠뜨린 곳이 드러난다. 원문은 아래 표의 링크에서 읽을 수 있다.

| 틀                                                                                                   | 나누는 방식                                                                                                                                                                                    | 이 원고에서 대응하는 곳                                                                                              | 찾지 못한 것과 적용의 한계                                                                                                |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| [Bonneau 외 2015](https://www.jbonneau.com/doc/BMCNKF15-IEEESP-bitcoin.pdf), Bitcoin 연구의 SoK      | 거래(transactions, 스크립트 포함), 합의 프로토콜(consensus protocol), 통신망(communication network)의 세 요소와 규칙 변경, 익명성(anonymity)                                                   | 1.2(실행 계층), 3절(거래 처리)과 7절(Arc의 EVM 차이), 4절(합의), 1.4(통신망), 5절(운영 권한), 8절(선택형 프라이버시) | 검증자끼리 어떻게 연결되는지는 찾지 못했다(1.4(통신망)).                                                                  |
| [Croman 외 2016](https://www.comp.nus.edu.sg/~prateeks/papers/Bitcoin-scaling.pdf), 확장성 논의      | Network, Consensus, Storage, View, Side의 다섯 plane                                                                                                                                           | 1.4(통신망)와 3.1(거래 접수), 4절(합의), 1.5(데이터 보관), 2.2(공개 풀 노드)와 7.1(잔액 표현), 9.3(외부 완료)        | 아카이브의 운영 주체와 보관 기간은 찾지 못했다(1.5(데이터 보관)).                                                         |
| [Bano 외 2019](https://arxiv.org/pdf/1711.03936), 합의의 SoK                                         | 보안 성질인 일관성(consistency), 거래 검열 저항(transaction censorship resistance), DoS 저항(DoS resistance)과 성능 성질인 처리량(throughput), 확장성(scalability), 지연(latency), 그리고 설계 | 4.3.1(안전성), 4.3.3(거래 포함), 4.3.4(과부하 저항), 9.2.2(성능 근거)                                                | 검증자 노드에 대한 공격 대비는 찾지 못했다(4.3.4(과부하 저항)).                                                           |
| [L2BEAT의 Risk Rosette](https://forum.l2beat.com/t/the-risk-rosette-framework/292), rollup 위험 평가 | 상태 검증(State Validation), 데이터 가용성(Data Availability), 탈출 기간(Exit Window), 시퀀서 실패(Sequencer Failure), 제안자 실패(Proposer Failure)                                           | 2.2(공개 풀 노드), 1.5(데이터 보관), 5절(운영 권한)과 5.4(노드 소프트웨어), 4.3.3(거래 포함), 4.3.2(진행성)          | 데이터 가용성과 탈출 기간은 rollup을 위한 질문이어서, Arc에 맞게 바꾸어 적용했다(1.5(데이터 보관), 5.4(노드 소프트웨어)). |

한 행은 틀 하나이고, 대응하는 곳과 찾지 못한 것은 내가 이 원고와 대조해 판단했다. L2BEAT의 틀은 Ethereum 위의 rollup을 평가하려고 만든 것이어서, Arc 같은 독립 체인에는 질문만 빌려 왔다. 대조해 보면 이 원고의 목차는 층을 나누는 틀보다 "누가 무엇을 결정하고, 그 결과를 믿으려면 무엇을 전제해야 하는가"라는 신뢰 조건의 질문에 가깝다. 다만 통신망, 데이터 보관, 과부하 저항과 규칙 변경 전의 대응 시간은 이 틀들이 묻는 질문이어서, 각각 1.4(통신망), 1.5(데이터 보관), 4.3.4(과부하 저항)와 5.4(노드 소프트웨어)에서 다룬다.

**프로토콜의 구성, 처리와 신뢰 조건**

한국어:

```text
[3. 거래 처리: 접수 / 후보 검사와 실행 / 합의 확정]
    |
    +-- 담당 구성 --> [1. 프로토콜 구성: 합의 계층 / 실행 계층과 EVM / 계층 연결 / 통신망 / 데이터 보관]
    |
    +-- 참여 주체 --> [2. 참여 권한: 제출과 조회 / 직접 검증 / 제안과 투표]
    |
    +-- 확정 절차와 조건 --> [4. 합의: 절차 / 안전성 / 진행성 / 거래 포함 / 과부하 저항]
    |
    +-- 변경 권한 --> [5. 운영 권한: 검증자 집합 / 설정 / 접근 제한 / 노드 소프트웨어]
    |
    +-- 다른 네트워크 --> [6. 비교: 거래 처리 / 합의 / 운영 권한]
    |
    +-- Arc의 차이 --> [7. Arc의 EVM 차이: 잔액 / 수수료 / 이전 로그 / 실행 환경 / 계약 동작]
    |
    +-- 예정 확장 --> [8. 선택형 프라이버시: 필요성 / 비공개 실행 / 키 관리 / 접근 정책]
    |                    실행과 기록 및 조회에 연결하는 설계다.
    |                    현재 제공 기능과 구분한다.
    |
    +-- 결과 해석 --> [9. 프로토콜 보장: 의미 / 성립 조건 / 확인 범위]
                         |
                         +-- 체인 밖의 완료는 별도 --> [외부 완료 조건]
```

English:

```text
[3. Transaction processing: admission / candidate checks and execution / consensus commit]
    |
    +-- components --> [1. Protocol components: consensus layer / execution layer and EVM / layer connection / network / data storage]
    |
    +-- participants --> [2. Participation rights: submit and query / verify / propose and vote]
    |
    +-- commit procedure and assumptions --> [4. Consensus: procedure / safety / liveness / transaction inclusion / DoS resistance]
    |
    +-- change authority --> [5. Operational authority: validator set / configuration / access restrictions / node software]
    |
    +-- other networks --> [6. Comparison: transaction processing / consensus / operational authority]
    |
    +-- Arc differences --> [7. Arc EVM differences: balance / fees / transfer logs / execution environment / contract behavior]
    |
    +-- planned extension --> [8. Opt-in privacy: need / private execution / key management / access policy]
    |                            Designed to connect execution, records and queries.
    |                            Distinguish this from currently available functions.
    |
    +-- interpretation --> [9. Protocol guarantees: meaning / assumptions / verification scope]
                              |
                              +-- completion outside the chain is separate --> [External completion]
```

그림은 3절(거래 처리)의 세 단계를 가운데에 두고, 나머지 절이 그 처리와 어떤 관계인지를 화살표의 이름으로 보인다. 상자 앞의 숫자는 절 번호이고, 상자 안의 낱말은 그 절의 하위 단위다. 연결은 내가 본문의 설명을 종합한 관계이며, 처리 순서, 담당 관계, 성립 조건과 변경 권한을 구분해 보이려고 화살표마다 관계의 이름을 붙였다.

검증자(validator)는 합의에 참여하는 주체이고, 최종성(finality)은 확정된 기록의 되돌림 여부에 관한 성질이다. 진행성(liveness)은 명시한 통신 및 참여 조건에서 합의가 계속 진전하는 성질로 잠정 번역한다. 신뢰 실행 환경(TEE, Trusted Execution Environment)의 실행 환경 증명(attestation)은 신원 인증과 다르다. 가스 사용량(gas used), 가스 단가(gas price), 가스비(gas fee)는 양, 단위당 가격과 지불액을 각각 뜻한다.

**목차**

- [Arc 프로토콜: 거래 처리의 구조와 동작 및 신뢰 조건은 무엇인가](#arc-프로토콜-거래-처리의-구조와-동작-및-신뢰-조건은-무엇인가)
  - [1. 프로토콜 구성: Arc 노드의 두 계층과 노드 사이의 통신망, 기록 보관은 어떻게 이어지는가](#1-프로토콜-구성-arc-노드의-두-계층과-노드-사이의-통신망-기록-보관은-어떻게-이어지는가)
    - [1.1 합의 계층: 거래 기록의 확정을 담당한다](#11-합의-계층-거래-기록의-확정을-담당한다)
    - [1.2 실행 계층: 거래와 계약을 EVM 규칙으로 실행해 상태를 바꾼다](#12-실행-계층-거래와-계약을-evm-규칙으로-실행해-상태를-바꾼다)
    - [1.3 계층 간 연결: 후보 생성과 검증 및 상태 반영을 연결한다](#13-계층-간-연결-후보-생성과-검증-및-상태-반영을-연결한다)
    - [1.4 통신망(network): 노드 사이에서 거래, 블록과 투표가 오가는 경로는 역할마다 다르다](#14-통신망network-노드-사이에서-거래-블록과-투표가-오가는-경로는-역할마다-다르다)
    - [1.5 데이터 보관(storage)과 가용성(data availability): 확정된 기록을 보관하고 내주는 경로](#15-데이터-보관storage과-가용성data-availability-확정된-기록을-보관하고-내주는-경로)
  - [2. 참여 권한: 누가 거래를 제출하고 검증하며 확정하는가](#2-참여-권한-누가-거래를-제출하고-검증하며-확정하는가)
    - [2.1 사용자와 RPC 제공자: 서명한 요청의 제출과 조회를 연결한다](#21-사용자와-rpc-제공자-서명한-요청의-제출과-조회를-연결한다)
    - [2.2 공개 풀 노드: 확정된 기록과 실행 결과를 직접 검증한다](#22-공개-풀-노드-확정된-기록과-실행-결과를-직접-검증한다)
    - [2.3 합의 검증자: 후보 블록의 제안과 투표를 담당한다](#23-합의-검증자-후보-블록의-제안과-투표를-담당한다)
  - [3. 거래 처리: 제출한 거래는 어떤 단계를 거쳐 실행되고 확정되는가](#3-거래-처리-제출한-거래는-어떤-단계를-거쳐-실행되고-확정되는가)
    - [3.1 거래 접수: 제출 요청을 검사하고 대기 거래를 보관한다](#31-거래-접수-제출-요청을-검사하고-대기-거래를-보관한다)
    - [3.2 후보 검증: 거래로 블록 후보를 구성하고 실행 유효성을 검사한다](#32-후보-검증-거래로-블록-후보를-구성하고-실행-유효성을-검사한다)
    - [3.3 거래 확정: 합의 투표를 거쳐 블록과 실행 결과를 기록한다](#33-거래-확정-합의-투표를-거쳐-블록과-실행-결과를-기록한다)
    - [3.4 실패 처리: 접수 거절과 대기 및 확정된 실행 실패를 구별한다](#34-실패-처리-접수-거절과-대기-및-확정된-실행-실패를-구별한다)
  - [4. 합의: 블록을 확정하는 절차는 무엇이며 그 확정은 어떤 조건에서 성립하는가](#4-합의-블록을-확정하는-절차는-무엇이며-그-확정은-어떤-조건에서-성립하는가)
    - [4.1 합의의 발전: 비잔틴 장군 문제에서 Tendermint와 Malachite까지](#41-합의의-발전-비잔틴-장군-문제에서-tendermint와-malachite까지)
    - [4.2 합의 절차: 한 높이의 블록은 propose, prevote와 precommit의 라운드로 정해진다](#42-합의-절차-한-높이의-블록은-propose-prevote와-precommit의-라운드로-정해진다)
    - [4.3 성립 조건: 안전성, 진행성, 거래 포함과 과부하 저항은 서로 다른 전제를 요구한다](#43-성립-조건-안전성-진행성-거래-포함과-과부하-저항은-서로-다른-전제를-요구한다)
      - [4.3.1 안전성: 투표권과 잠금 규칙으로 충돌하는 확정을 방지한다](#431-안전성-투표권과-잠금-규칙으로-충돌하는-확정을-방지한다)
      - [4.3.2 진행성: 충분한 투표권과 메시지 전달을 요구한다](#432-진행성-충분한-투표권과-메시지-전달을-요구한다)
      - [4.3.3 거래 포함: 블록 확정 속도와 개별 거래의 포함 조건을 구별한다](#433-거래-포함-블록-확정-속도와-개별-거래의-포함-조건을-구별한다)
      - [4.3.4 과부하 저항(DoS resistance): 스팸과 과부하를 거래 경로의 여러 자리에서 막는다](#434-과부하-저항dos-resistance-스팸과-과부하를-거래-경로의-여러-자리에서-막는다)
  - [5. 운영 권한: 누가 검증자 집합과 실행 규칙을 변경하는가](#5-운영-권한-누가-검증자-집합과-실행-규칙을-변경하는가)
    - [5.1 검증자 관리: 등록과 활성 상태 및 투표권을 변경한다](#51-검증자-관리-등록과-활성-상태-및-투표권을-변경한다)
    - [5.2 설정 관리: 수수료와 합의 매개변수 및 변경 함수의 정지를 관리한다](#52-설정-관리-수수료와-합의-매개변수-및-변경-함수의-정지를-관리한다)
    - [5.3 접근 제한: 주소와 자산 이전에 적용되는 차단 권한을 구별한다](#53-접근-제한-주소와-자산-이전에-적용되는-차단-권한을-구별한다)
    - [5.4 노드 소프트웨어: 하드포크는 릴리스에 적힌 시각에 활성화되며, 그 공지가 사용자의 대응 시간을 정한다](#54-노드-소프트웨어-하드포크는-릴리스에-적힌-시각에-활성화되며-그-공지가-사용자의-대응-시간을-정한다)
  - [6. 다른 네트워크와의 비교: Bitcoin, Ethereum, Solana, Base와 Arc는 거래 처리, 합의와 운영 권한에서 어떻게 다른가](#6-다른-네트워크와의-비교-bitcoin-ethereum-solana-base와-arc는-거래-처리-합의와-운영-권한에서-어떻게-다른가)
    - [6.1 거래 처리 비교: 다섯 네트워크의 제출, 실행과 실패 기록을 단계별로 대조한다](#61-거래-처리-비교-다섯-네트워크의-제출-실행과-실패-기록을-단계별로-대조한다)
    - [6.2 합의 비교: 다섯 네트워크가 기록을 확정하는 방식과 확정의 의미를 대조한다](#62-합의-비교-다섯-네트워크가-기록을-확정하는-방식과-확정의-의미를-대조한다)
    - [6.3 운영 권한 비교: 다섯 네트워크에서 참여자와 규칙을 바꾸는 주체를 대조한다](#63-운영-권한-비교-다섯-네트워크에서-참여자와-규칙을-바꾸는-주체를-대조한다)
  - [7. Arc의 EVM 차이: EVM 호환은 무엇이 같다는 뜻이며, USDC 기록과 계약 실행은 Ethereum과 어디가 다른가](#7-arc의-evm-차이-evm-호환은-무엇이-같다는-뜻이며-usdc-기록과-계약-실행은-ethereum과-어디가-다른가)
    - [7.1 잔액 표현: 같은 USDC 잔액을 인터페이스별 단위로 읽는다](#71-잔액-표현-같은-usdc-잔액을-인터페이스별-단위로-읽는다)
    - [7.2 수수료 기록: 사용 가스와 가격 및 수취 주소를 연결한다](#72-수수료-기록-사용-가스와-가격-및-수취-주소를-연결한다)
    - [7.3 이전 로그: 자산 이전의 기록과 잔액 변화의 차이를 설명한다](#73-이전-로그-자산-이전의-기록과-잔액-변화의-차이를-설명한다)
    - [7.4 실행 환경: 기존 EVM 도구의 재사용 범위와 차이를 설명한다](#74-실행-환경-기존-evm-도구의-재사용-범위와-차이를-설명한다)
    - [7.5 계약 동작: 명령어와 네이티브 USDC 이전의 제약을 설명한다](#75-계약-동작-명령어와-네이티브-usdc-이전의-제약을-설명한다)
  - [8. 선택형 프라이버시(opt-in privacy): 공개 원장의 거래 내용을 감추는 예정 기능은 왜 필요하며 어떻게 설계되는가](#8-선택형-프라이버시opt-in-privacy-공개-원장의-거래-내용을-감추는-예정-기능은-왜-필요하며-어떻게-설계되는가)
    - [8.1 필요성: 공개 원장에서는 누구나 거래의 내용을 읽을 수 있다](#81-필요성-공개-원장에서는-누구나-거래의-내용을-읽을-수-있다)
    - [8.2 비공개 실행: 공개 접수와 보호된 실행 및 상태 확정을 연결하는 설계다](#82-비공개-실행-공개-접수와-보호된-실행-및-상태-확정을-연결하는-설계다)
    - [8.3 키 관리: 암호화와 실행 환경 인증 및 키 복원의 설계 조건을 설명한다](#83-키-관리-암호화와-실행-환경-인증-및-키-복원의-설계-조건을-설명한다)
    - [8.4 접근 정책: 함수 호출과 상태 조회 및 로그의 공개 범위를 설계한다](#84-접근-정책-함수-호출과-상태-조회-및-로그의-공개-범위를-설계한다)
  - [9. 프로토콜 보장: 처리 결과의 의미와 확인 범위는 어디까지인가](#9-프로토콜-보장-처리-결과의-의미와-확인-범위는-어디까지인가)
    - [9.1 보장의 성립 조건: 앞의 작동 원리와 신뢰 조건을 종합한다](#91-보장의-성립-조건-앞의-작동-원리와-신뢰-조건을-종합한다)
    - [9.2 운영 확인: 설계와 코드 및 성능 자료로 확인한 범위를 구별한다](#92-운영-확인-설계와-코드-및-성능-자료로-확인한-범위를-구별한다)
      - [9.2.1 배포 근거: 문서와 고정 코드 및 초기 설정을 현재 운영과 구별한다](#921-배포-근거-문서와-고정-코드-및-초기-설정을-현재-운영과-구별한다)
      - [9.2.2 성능 근거: 벤치마크의 처리량과 실제 제출 지연을 구별한다](#922-성능-근거-벤치마크의-처리량과-실제-제출-지연을-구별한다)
      - [9.2.3 후속 확인: 남은 운영 질문과 필요한 근거를 구별한다](#923-후속-확인-남은-운영-질문과-필요한-근거를-구별한다)
    - [9.3 외부 완료: 체인 확정과 다른 체인 및 은행의 처리 완료를 구별한다](#93-외부-완료-체인-확정과-다른-체인-및-은행의-처리-완료를-구별한다)

Arc의 설계와 사양은 공식 영문 기술 문서, Litepaper와 Whitepaper를 근거로 설명한다. 공식 자료가 서로 다르게 설명하는 조건은 해당 부분에 함께 적었다. 다른 체인 비교, 법률 자료와 고정 커밋의 코드 관찰도 각각의 출처와 적용 범위를 구별한다.

공식 블로그의 관련 설명은 본문에서 원문 링크로 연결한다. 공식 발표와 설계 설명은 실제 운영을 직접 관측한 근거와 구별한다.

다음 그림은 기업이 USDC를 EURC로 환전한 뒤 공급업체에 지급하는 설명용 예시다. 두 앱은 같은 원장의 잔액을 사용하지만 환전과 지급은 별도 거래이며, 각 거래의 USDC 가스비는 이전 원금과 구분한다. 화살표는 거래 제출, 결과 조회와 계층 사이의 연결을 나타낸다.

```text
 [환전 앱]                              [지급 앱]
  교환 조건 확인과 거래 요청             공급업체와 지급액 확인, 거래 요청
    |              ^                       |              ^
    | 거래 제출    | 결과 조회             | 거래 제출    | 결과 조회
    v              |                       v              |
 ======================== 두 앱이 공유하는 Arc ========================

  [실행 계층]
   거래를 선택하고 실행하여 블록 후보와 상태 변경을 계산
   받은 블록 후보가 실행 규칙에 맞는지도 검사
          |                              ^
          | 후보 데이터와 검사 결과      | 후보 구성과 검사 요청
          v                              |
  [합의 계층]
   블록 후보를 제안하고, 검사 결과를 반영해 검증자들이 투표
   필요한 투표권이 모이면 블록을 확정
          |
          | 확정한 블록을 실행 계층에 전달
          v
  [실행 계층]
   확정한 블록을 정본 체인에 반영하고 상태와 영수증을 보관
          |
          v
  [공통된 원장 상태: 계정 잔액, 컨트랙트 저장값과 거래 결과]

   환전 거래 성공과 확정
     기업 USDC 감소, 기업 EURC 증가
          |
          | 지급 앱이 확정된 잔액과 실행 결과를 조회
          v
   지급 거래 성공과 확정
     기업 EURC 감소, 공급업체 EURC 증가
```

- 위아래의 실행 계층은 같은 계층의 서로 다른 작업을 나타냄
- 후보를 만드는 제안자와 받은 후보를 검사하는 검증자의 작업을 함께 표시한 개념도이며, 모든 노드가 같은 순서로 수행한다는 뜻은 아님
- 실행 결과의 계산과 검사, 합의의 확정 결정, 확정된 상태의 반영이 연결되는 구조임

- 두 앱은 서로 다른 화면과 업무 규칙을 갖지만, 기업의 EURC 잔액은 Arc에 기록된 같은 잔액임
- 같은 원장을 사용해도 환전 결과의 확인, 공급업체 주소와 지급액의 검토 및 실행 승인은 앱에서 처리할 필요가 있음

## 1. 프로토콜 구성: Arc 노드의 두 계층과 노드 사이의 통신망, 기록 보관은 어떻게 이어지는가

**프로토콜 구성의 개요: Arc 검증자 노드의 두 계층과 바깥 연결**

한국어:

```text
[Arc 검증자 노드 하나]
 |
 +-- [합의 계층: Malachite] ................................ 1.1
 |     후보 제안, 투표, 확정 결정
 |     <-- libp2p --> 다른 노드의 합의 계층: 제안 조각, 투표 ... 1.4
 |             |    ^
 |             |    |  Engine API: 후보 구성 / 후보 검사 / 정본 반영 ... 1.3
 |             v    |
 +-- [실행 계층: Reth 기반] ................................ 1.2
       거래 풀, EVM 실행, 상태 보관, 영수증
       <-- devp2p ----> 다른 노드의 실행 계층: 거래 전파 ... 1.4
       <-- JSON-RPC --> 앱과 지갑: 거래 제출, 조회
       <-- 스냅샷 ----- 확정된 기록: 새 노드가 시작하는 지점 ... 1.5
```

English:

```text
[One Arc validator node]
 |
 +-- [Consensus layer: Malachite] ........................... 1.1
 |     proposals, votes, commit decisions
 |     <-- libp2p --> other nodes' consensus layers: proposal parts, votes ... 1.4
 |             |    ^
 |             |    |  Engine API: build candidate / check candidate / apply canonical state ... 1.3
 |             v    |
 +-- [Execution layer: Reth-based] .......................... 1.2
       transaction pool, EVM execution, state storage, receipts
       <-- devp2p ----> other nodes' execution layers: transaction gossip ... 1.4
       <-- JSON-RPC --> apps and wallets: submit transactions, queries
       <-- snapshot --- finalized records: where a new node starts ... 1.5
```

그림은 노드 하나를 가운데에 두고, 이 절이 설명하는 것을 모두 그 노드에 이어 놓은 것이다. 위의 합의 계층과 아래의 실행 계층이 한 노드 안에 함께 있고, 둘 사이의 세로 화살표가 Engine API다. 각 계층에서 바깥으로 나가는 연결은 서로 다르다. 합의 계층은 다른 노드의 합의 계층과 libp2p로 제안과 투표를 주고받고, 실행 계층은 다른 노드와 devp2p로 거래를 주고받으며 앱의 JSON-RPC 요청에 답한다. 새 노드는 처음 블록부터 다시 실행하지 않고 스냅샷에서 시작한다. 오른쪽 번호는 각 부분을 자세히 설명하는 절이다. 1.1은 위 상자, 1.2는 아래 상자, 1.3은 두 상자 사이의 연결을 설명한다. 바깥 연결이 실제로 누구와 이어지는지는 1.4(통신망)에서, 확정된 기록을 누가 보관하고 내주는지는 1.5(데이터 보관)에서 설명한다.

1.1부터 1.5까지는 각각 한 부분만 설명하므로, 읽기 전에 다섯 부분이 노드 하나를 기준으로 어떻게 놓이는지 먼저 보여 주려고 이 그림을 두었다. 노드 안의 구성 요소(거래 풀, 블록 실행기 등)는 1.2의 노드 아키텍처 그림에서 더 자세히 보인다. 근거는 [노드 운영 문서](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/docs/running-an-arc-node.md)의 두 프로세스 설명과 RPC 제공 노드의 연결 설명, [아키텍처 문서](https://github.com/circlefin/arc-node/blob/main/docs/ARCHITECTURE.md)의 계층 그림이다. 스냅샷 줄의 근거는 노드 운영 문서의 스냅샷 설명이다.

이 개요 그림의 제안, 투표와 합의 gossip은 검증자 노드의 역할이다. [Running a node 문서](https://docs.arc.io/arc/concepts/running-a-node.md)가 설명하는 공개 풀 노드도 CL과 EL을 실행하지만 블록을 제안하거나 투표하지 않고 합의 gossip에 참여하지 않는다. 공개 풀 노드는 확정된 블록의 검증자 서명을 확인하고 EVM 거래를 직접 다시 실행하여 자기 상태와 RPC를 제공한다.

공식 글 연결: [Run Your Own Arc Node and Join the Arc Bug Bounty Program](https://www.arc.io/blog/open-sourcing-arc-run-your-own-arc-node-and-bug-bounty-program) (2026-04-09, [공식 원문](https://www.arc.io/blog/open-sourcing-arc-run-your-own-arc-node-and-bug-bounty-program)). 노드 공개 글은 풀 노드와 검증자를 구별하고 Reth 및 Malachite의 역할을 명시한다. 공개 노드 실행이 합의 투표 권한을 부여하는 것은 아니다.

### 1.1 합의 계층: 거래 기록의 확정을 담당한다

Arc의 합의 계층(consensus layer)은 Malachite라는 Tendermint 계열 BFT(Byzantine Fault Tolerance) 구현을 사용한다. BFT는 일부 참여자가 잘못 행동해도 합의하도록 설계한 방식이다. [합의 문서](https://docs.arc.io/arc/concepts/consensus-layer.md)는 허가된 기관 검증자가 참여하는 PoA(Proof of Authority)를 설명한다.

Malachite에 이르기까지 합의 연구가 어떤 문제를 차례로 풀었는지는 4.1(합의의 발전)의 연표에 정리했다. 여기서는 Arc의 합의 계층이 하는 일만 먼저 설명한다.

이 계층이 해결하는 문제는 여러 노드가 서로 다른 시각에 거래와 후보를 받더라도 같은 높이의 정본 블록을 결정하도록 하는 것이다. 높이는 체인에서 블록이 차지하는 위치다. 제안자가 후보를 보내는 것만으로는 정본이 되지 않는다. 검증자들이 후보를 평가하고 합의 규칙에 따라 투표한 뒤 필요한 투표권(voting power)의 결정을 확보해야 한다. 따라서 합의 계층의 결과는 어느 거래 요청을 먼저 받았다는 로컬 기록이 아니라, 어떤 블록을 네트워크의 확정된 기록으로 받아들일지에 대한 결정이다.

같은 합의 계층이라도 노드의 역할에 따라 수행하는 일이 다르다. 검증자 측에서는 제안과 투표 및 확정 결정을 수행한다. 공개 풀 노드 측에서는 [노드 문서](https://docs.arc.io/arc/concepts/running-a-node.md)가 설명하듯 확정된 블록을 가져와 검증자 서명을 검사하고 실행 계층에 전달한다. 같은 소프트웨어 계층을 사용한다는 사실이 같은 합의 권한을 갖는다는 뜻은 아니다.

노드의 종류는 2절(참여 권한) 첫머리의 노드 종류 표에, 역할과 결정 범위는 같은 곳의 다섯 역할 비교 표에 정리했다.

PoA는 이 결정에 참여할 집합을 허가한다는 설명이다. 개별 검증자의 판단을 무조건 받아들이거나 기관 이름만으로 실행 결과가 옳다고 인정한다는 뜻으로 읽어서는 안 된다. 후보의 실행 유효성 검사와 합의 투표 규칙이 함께 작동해야 하며, 허가된 집합을 누가 바꿀 수 있는지는 운영 권한의 별도 질문이다. 뒤에서는 거래 처리로 결정의 구체적인 과정을 설명한 뒤 합의의 성립 조건과 집합 변경 권한을 나누어 검토한다.

PoA는 PoW(작업증명)나 PoS(지분증명)와 같은 층에 있는 말이다. 셋 모두 누가 블록을 만들거나 투표할 자격을 갖고, 그 영향력이 무엇으로 정해지는지를 정하는 방식이다. 블록을 확정하는 합의 알고리즘은 그 위에 따로 있다. Tendermint 사양은 자신이 PoS 체인을 위해 설계되었다고 적는다([Tendermint 사양](https://github.com/circlefin/malachite/blob/72143f6c99a98452b587e1c392bdb80944eb2232/specs/consensus/overview.md) ). Arc는 이 알고리즘을 쓰면서 참여 자격은 PoA로 정한다. 아래 표는 세 방식을 같은 기준으로 비교한 것이다. PoS는 Ethereum의 예치형과 Solana의 위임형이 참여 방식에서 달라 두 행으로 나누었다.

| 방식                          | 참여 자격                                      | 영향력의 크기                                                       | 잘못했을 때 잃는 것                                                                                                                  | 대표 네트워크 |
| ----------------------------- | ---------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ------------- |
| PoW(proof of work, 작업증명)  | 누구나. 정해진 조건의 해시를 찾는 연산을 한다. | 연산 능력. 백서는 "one-CPU-one-vote"라고 적는다.                    | 규칙에 어긋난 블록은 다른 노드가 받아들이지 않으므로 그 블록에 들인 연산이 헛된다.                                                   | Bitcoin       |
| PoS(proof of stake, 지분증명) | 32 ETH를 예치 계약에 넣은 검증자               | 예치한 ETH의 양                                                     | 한 슬롯에 블록을 여럿 제안하거나 모순된 증명을 내면 예치 ETH의 일부에서 전부까지 소각된다.                                           | Ethereum      |
| PoS, 위임형(delegated stake)  | SOL 보유자가 지분을 위임한 검증자              | 위임된 지분의 양. 블록을 만들 리더의 일정도 지분으로 가중해 정한다. | 문서는 잘못 투표하면 지분이 슬래싱에 노출된다고 적지만, 잠금 위반의 처벌은 제안(proposed)으로 적혀 있어 시행 여부를 확인하지 못했다. | Solana        |
| PoA(proof of authority)       | 선정된, 신원이 알려진 기관                     | 관리 계약이 정한 투표권(5.1(검증자 관리))                           | 예치를 깎는 장치는 확인하지 못했다. 합의 문서는 경제적 유인 대신 기관의 책임을 내세운다.                                             | Arc           |

한 행은 참여 자격을 정하는 방식 하나다. PoW 행은 [Bitcoin 백서](https://bitcoin.org/bitcoin.pdf)의 4절(Proof-of-Work)과 5절(Network), Ethereum의 PoS 행은 [ethereum.org의 지분 증명 문서](https://ethereum.org/ko/developers/docs/consensus-mechanisms/pos/), PoA 행은 [합의 문서](https://docs.arc.io/arc/concepts/consensus-layer.md)를 따랐다. 위임형 PoS 행은 Anza 문서의 [지분 위임](https://docs.anza.xyz/consensus/stake-delegation-and-rewards), [리더 교대](https://docs.anza.xyz/consensus/leader-rotation)와 [Tower BFT](https://docs.anza.xyz/implemented-proposals/tower-bft)를 따랐다.

Base는 이 표의 어느 행에도 들어가지 않는다. Base는 블록을 만들 자격을 정하는 경쟁이나 투표 없이 Base가 운영하는 시퀀서 하나가 블록을 만들고, 기록의 최종 보관과 확정은 Ethereum에 맡기는 L2(rollup)다([프로토콜 개요](https://docs.base.org/specifications/base-protocol/overview.md)). 그래서 Base를 PoA로 분류하지 않았고, 이 분류는 내가 정한 것이다. 네트워크들에서 확정이 어떻게 다른지는 6.2(합의 비교)에서 Base까지 넣어 비교한다.

블록은 여러 거래의 순서와 처리 결과를 원장(ledger)에 연결하는 단위다. [시스템 개요](https://docs.arc.io/arc/concepts/system-overview.md)는 Malachite가 거래 순서와 블록 확정을, Reth가 거래 실행과 상태 유지를 맡는다고 설명한다. 설명용으로 서로 다른 거래가 같은 계정의 잔액이나 계약 저장값을 사용한다고 생각하면 순서의 의미를 이해할 수 있다. 앞 거래의 처리로 상태가 달라지면 뒤 거래는 그 상태를 기준으로 처리돼야 하므로, 각 앱이 자기 요청만 따로 계산한 결과를 곧바로 원장의 기록으로 삼을 수는 없다.

한국어:

```text
 같은 계정을 쓰는 두 거래, 시작 잔액 50 USDC

 블록 안의 순서:   거래 1  -->  거래 2
                     |            |
                     v            v
             40 USDC 이전    30 USDC 이전 시도
             잔액 50 -> 10   잔액 10 기준으로 처리 -> 실패

 각 앱이 따로 "50에서 30을 보낸다"고 계산한 결과는 원장의 기록이 될 수 없다.
 순서와 확정: Malachite (합의)      실행과 상태 유지: Reth
```

English:

```text
 Two transactions using the same account, starting balance 50 USDC

 Order in the block:  tx 1  -->  tx 2
                        |          |
                        v          v
             transfer 40 USDC   try to transfer 30 USDC
             balance 50 -> 10   processed against 10 -> fails

 Each app computing "send 30 out of 50" on its own cannot become the ledger record.
 Order and finality: Malachite (consensus)    Execution and state: Reth
```

두 거래가 같은 잔액을 쓰면 순서가 결과를 바꾼다. 거래 1이 먼저 처리되면 잔액이 10 USDC로 줄어 거래 2는 실패한다. 순서를 정하는 일은 합의(Malachite)가, 그 순서대로 상태를 계산하는 일은 실행(Reth)이 맡는다. 그림의 값은 설명용 예시이며, 가스비는 생략했다.

### 1.2 실행 계층: 거래와 계약을 EVM 규칙으로 실행해 상태를 바꾼다

실행 계층(execution layer)은 Reth라는 Ethereum 실행 클라이언트를 기반으로 EVM(Ethereum Virtual Machine) 계약을 실행한다.

**실행 클라이언트는 하나가 아니다.** Ethereum은 하나의 사양을 여러 팀이 서로 다른 언어로 구현하고, 각 노드는 그중 하나를 골라 실행한다. ethereum.org는 이 구현들이 모두 같은 사양을 따르며, 한 클라이언트의 버그가 네트워크 전체를 멈추지 않도록 여러 구현이 고르게 쓰이는 것을 목표로 한다고 설명한다. Reth는 그중 하나이며 Arc는 이것을 가져다 실행 계층을 만들었다. 아래 첫 표는 Ethereum 메인넷의 실행 클라이언트이고, 둘째 표는 다른 네트워크가 어떤 실행 클라이언트를 쓰는지다.

| 클라이언트        | 언어     | 문서가 설명하는 특징                                                                                                                    | Ethereum 메인넷 노드 점유율(2025-10-26) |
| ----------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------- |
| Geth(Go Ethereum) | Go       | 최초 구현 가운데 하나이며 사용자 기반과 도구가 가장 넓다.                                                                               | 41%                                     |
| Nethermind        | C#, .NET | 최적화한 가상 머신, 상태 접근과 운영 기능(모니터링, JSON-RPC 추적)을 내세운다.                                                          | 38%                                     |
| Besu              | Java     | 공개망과 허가형 네트워크를 모두 겨냥한 기업용 클라이언트이며 ConsenSys가 지원한다.                                                      | 16%                                     |
| Erigon            | Go       | Geth의 포크(Turbo-Geth)에서 출발해 속도와 디스크 효율을 위해 다시 설계했다.                                                             | 3%                                      |
| Reth              | Rust     | Paradigm이 만든 모듈형 클라이언트로, 구성 요소를 라이브러리로 가져다 쓸 수 있게 했다. RPC, MEV, 색인처럼 성능이 중요한 용도를 겨냥한다. | 2%                                      |

| 네트워크                     | 실행 클라이언트                                    | 관계                                                                                                                                                                                                   |
| ---------------------------- | -------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Ethereum                     | 위 표의 다섯(그 밖에 ethrex, 개발 중인 EthereumJS) | 같은 사양의 독립 구현을 노드마다 고른다.                                                                                                                                                               |
| Arc                          | Reth                                               | Reth를 기반으로 실행 계층을 만들고 USDC 가스와 사전 컴파일 계약을 더했다(이 절의 노드 그림과 7절(Arc의 EVM 차이)).                                                                                     |
| Base                         | Reth 기반의 base/base                              | OP Stack에서 시작했고, 2026-02-18에 Base 자체 스택(base/base)으로 옮긴다고 발표했다. 업그레이드 목록은 Azul을 Base의 첫 독립 업그레이드로, Beryl에서 Reth V2를 기준 실행 클라이언트로 정했다고 적는다. |
| OP Stack 체인(OP Mainnet 등) | op-reth                                            | op-geth는 2026-05-31에 지원이 끝났고, op-reth가 주 지원 경로다.                                                                                                                                        |
| Arbitrum                     | Nitro(Geth의 핵심을 내장)                          | Geth의 EVM 핵심을 Arbitrum 노드 안에 컴파일해 넣었다.                                                                                                                                                  |
| BNB Smart Chain              | bsc(go-ethereum 포크)                              | go-ethereum을 포크해 개발을 시작했다.                                                                                                                                                                  |
| Polygon PoS                  | Bor(geth 포크)                                     | geth를 포크한 Go 구현이다.                                                                                                                                                                             |
| Solana                       | 해당 없음                                          | EVM을 쓰지 않고 자체 실행 환경을 쓴다(6.1(거래 처리 비교)).                                                                                                                                            |

첫 표의 언어와 특징은 [ethereum.org의 노드와 클라이언트 문서](https://github.com/ethereum/ethereum-org-website/blob/dev/public/content/developers/docs/nodes-and-clients/index.md)를, 점유율은 같은 사이트의 [클라이언트 다양성 문서](https://github.com/ethereum/ethereum-org-website/blob/dev/public/content/developers/docs/nodes-and-clients/client-diversity/index.md)를 따랐다. 이 점유율은 supermajority.info에서 2025-10-26에 얻은 한 시점의 값이다. 같은 문서는 Geth가 노드의 약 85%라고 적는데, 이는 그보다 앞서 쓴 문단으로 보이며 이 원고는 날짜가 적힌 그림의 값을 썼다. Reth의 설명은 [Reth README](https://github.com/paradigmxyz/reth/blob/main/README.md)도 따랐다. 둘째 표는 각 네트워크의 문서를 내가 모은 것이다. Arc는 [시스템 개요](https://docs.arc.io/arc/concepts/system-overview.md), Base는 [프로토콜 개요](https://docs.base.org/specifications/base-protocol/overview.md), [업그레이드 목록](https://docs.base.org/upgrades/overview.md)과 [통합 스택 발표](https://blog.base.dev/next-chapter-for-base-chain-1), OP Stack은 [Optimism의 실행 클라이언트 설정 문서](https://docs.optimism.io/operators/node-operators/configuration/execution-config.md), Arbitrum은 [Nitro README](https://github.com/OffchainLabs/nitro/blob/master/README.md), BNB Smart Chain은 [bsc README](https://github.com/bnb-chain/bsc/blob/master/README.md), Polygon PoS는 [Bor README](https://github.com/0xPolygon/bor/blob/develop/README.md)를 따랐다. 각 네트워크의 노드 가운데 몇 개가 어느 클라이언트를 실행하는지는 Ethereum 외에는 조사하지 않았다.

표에서 보이는 흐름은 두 갈래다. 하나는 Geth를 포크하거나 내장한 네트워크(BNB Smart Chain, Polygon PoS, Arbitrum)이고, 다른 하나는 Reth를 기반으로 삼는 최근의 네트워크(Base, OP Stack, Arc)다. 이 갈래는 내가 표를 읽어 나눈 것이다. 공식 실행 계층 문서는 Reth가 성능, 메모리 안전성과 모듈 확장성을 위해 Rust로 작성됐으며, Arc는 핵심 EVM 실행을 바꾸지 않고 스테이블코인 네이티브 모듈을 추가하기 위해 이 구조를 활용한다고 설명한다. 또 Arc와 Base는 현재 각각 클라이언트 하나에 기대므로, ethereum.org가 말하는 클라이언트 다양성의 보호를 받지 않는다. Reth에 버그가 있으면 Arc의 모든 노드가 같은 버그를 갖는다.

[시스템 개요](https://docs.arc.io/arc/concepts/system-overview.md)는 실행 계층이 계정과 잔액, 계약 및 저장 값을 유지하고 거래를 적용해 상태 루트(state root)를 만든다고 설명한다. 상태는 현재 원장의 내용이며 상태 루트는 그 내용을 요약하는 해시다. 거래는 이 상태에 적용하는 요청이다. 실행 계층은 요청을 규칙대로 처리했을 때 잔액과 계약 저장 값이 어떻게 바뀌는지 계산한다. 합의가 블록을 결정하는 일과 실행이 그 블록의 거래 효과를 계산하는 일은 이처럼 다른 질문에 답한다.

**상태(state)란 무엇인가.** [ethereum.org 용어집](https://ethereum.org/en/glossary/)은 상태를 "A snapshot of all balances and data at a particular point in time on the blockchain"이라고 정의하고, 보통 특정 블록 시점의 상태를 가리킨다고 덧붙인다. [황서](https://ethereum.github.io/yellowpaper/paper.pdf) 4.1(World State)은 더 구체적으로, 상태를 주소마다 그 계정의 상태를 대응시킨 표로 정의한다. 계정 상태에는 잔액, nonce, 계약 코드의 해시와 저장소(storage)가 들어간다. 코드가 없는 계정은 황서의 표현으로 "non-contract" 계정이며, 흔히 외부 소유 계정(EOA, externally owned account)이라고 부른다. 상태 자체는 블록에 저장되지 않고 각 노드가 자기 데이터베이스에 보관한다. 블록에 들어가는 것은 상태를 요약한 값이다. 황서는 상태를 담은 트리 구조의 맨 위 노드가 모든 내부 데이터에 따라 달라지므로, 그 해시를 상태 전체의 식별값으로 쓸 수 있다고 설명한다. 해시는 길이가 제각각인 입력에서 만든 길이가 정해진 지문이다. 블록 헤더의 상태 루트(stateRoot)는 그 블록의 거래를 모두 실행한 뒤 이 트리 맨 위 노드의 해시다. 거래는 기존 계정을 호출하는 메시지 호출(message call)과 코드가 있는 새 계정을 만드는 계약 생성(contract creation)으로 나뉜다.

그래서 두 노드가 같은 블록에 대해 같은 상태 루트를 계산했다면, 상태 전체를 주고받지 않고도 둘이 같은 상태에 도달했다고 확인할 수 있다. 2.2(공개 풀 노드)의 재실행이 확인하는 것이 이것이다.

**실행 계층이 다루는 용어의 관계**

한국어:

```text
[원장]  확정된 블록이 순서대로 이어진 기록
  |
  +-- [블록 n-1] <-- 부모 해시 -- [블록 n]
                                   |
                                   +-- 헤더: 상태 루트 = 거래를 모두 실행한 뒤 상태의 해시
                                   |
                                   +-- 본문: [거래 1] [거래 2] ...
                                                |
                                                | 실행: 상태 전이 함수(EVM)
                                                v
[상태]  주소 -> 계정 상태의 표 (노드의 데이터베이스에 보관)
  |
  +-- [외부 소유 계정]  잔액, nonce, 코드 없음
  |
  +-- [계약 계정]       잔액, nonce, 코드의 해시, 저장소
                          계약 = 코드가 있는 계정
```

English:

```text
[Ledger]  the ordered record of finalized blocks
  |
  +-- [Block n-1] <-- parent hash -- [Block n]
                                       |
                                       +-- header: state root = hash of the state after all transactions run
                                       |
                                       +-- body: [tx 1] [tx 2] ...
                                                    |
                                                    | execution: state transition function (EVM)
                                                    v
[State]  table of address -> account state (kept in each node's database)
  |
  +-- [Externally owned account]  balance, nonce, no code
  |
  +-- [Contract account]          balance, nonce, code hash, storage
                                    contract = an account with code
```

그림의 위쪽은 블록에 기록되는 것이고 아래쪽은 노드가 보관하는 것이다. 원장은 블록의 사슬이고, 블록은 거래의 목록과 상태 루트를 담는다. 거래가 실행되면 아래쪽의 상태가 바뀌고, 바뀐 상태의 해시가 다음 블록 헤더의 상태 루트가 된다. 잔액과 저장값은 상태 안에 있고 블록에는 그 요약만 있다. 계약은 코드가 있는 계정이며, 계약의 데이터는 그 계정의 저장소에 있다. 이 관계는 황서 4.1(World State)과 4.4(The Block)의 정의를 내가 한 그림으로 묶은 것이다. 거래가 상태를 바꾸는 과정 자체는 아래 EVM 설명의 끝에 있는 "EVM의 상태 전이" 그림에서 다시 설명한다.

**EVM은 거래를 받아 상태를 바꾸는 실행 규칙이다.** 실행 계층이 거래와 계약을 실행하는 규칙은 EVM(Ethereum Virtual Machine)이 정한다. 아래에서 EVM의 정의는 Ethereum 실행 계층의 형식 명세인 [황서(yellow paper) Shanghai 판](https://ethereum.github.io/yellowpaper/paper.pdf)을 따른다. 설명한 내용은 끝의 "EVM의 상태 전이" 그림 하나에 모았다.

황서는 2절(The Blockchain Paradigm)에서 Ethereum 전체를 "transaction-based state machine"으로 설명한다. 최초 상태(genesis)에서 출발해 거래를 차례로 실행하면서 현재 상태를 만들고, 그 현재 상태를 정본으로 받아들인다는 뜻이다. 수식으로는 `σt+1 ≡ Υ(σt, T)`이며, 다음 상태는 현재 상태 σt와 거래 T에 상태 전이 함수 Υ를 적용한 결과다. 같은 절은 블록의 순서를 정하는 일을 합의 계층(Ethereum에서는 Beacon Chain)에 맡기고, 황서 자신은 실행 계층만 기술한다고 밝힌다. Arc에서 Malachite가 순서와 확정을, Reth가 실행을 맡는 분담도 같은 경계를 따른다.

EVM은 이 상태 전이 안에서 계약 코드를 실행하는 가상 기계다. 황서 9.1(Basics)에 따르면 EVM은 256비트 워드를 쓰는 스택 기반 구조이고, 스택의 최대 크기는 1024다. 실행 중에만 쓰는 메모리와 상태의 일부로 남는 저장소를 구분한다. 황서가 EVM을 "quasi-Turing-complete"라고 부르는 이유는 모든 계산이 가스라는 한도 안에서만 수행되기 때문이다.

가스(gas)는 계산의 종류마다 정해 둔 비용 단위다(황서 5절(Gas and Payment)). 거래는 gasLimit를 지정하며, 그만큼의 가스를 발신자의 잔액에서 미리 사들이는 방식으로 처리된다. Ethereum은 이 비용을 ETH로 받고 Arc는 네이티브 USDC로 받는다. 이 차이가 7.1(잔액 표현)과 7.2(수수료 기록)의 출발점이다.

실행 결과는 영수증(receipt)으로 남는다. 황서 4.4.1(Transaction Receipt)에 따르면 영수증은 거래 유형, 상태 코드, 블록 안의 누적 가스 사용량, 실행 중 생성된 로그(log)와 그 로그로 만든 블룸 필터의 다섯 항목으로 구성된다. 3.4(실패 처리)의 status 1과 status 0이 이 상태 코드다. 로그는 계약이 실행 중 남기는 기록이며, ERC-20 토큰의 Transfer 이벤트도 로그의 한 종류다. 실행이 예외로 중단되면 그 호출이 만든 상태 변경은 되돌아가지만 사용한 가스는 돌려받지 못한다.

**EVM의 상태 전이**

한국어:

```text
 [현재 상태 σt]                      [거래 T]
  주소 -> 계정 상태                   서명, nonce, 수신 주소 또는 계약 생성,
   - 잔액, nonce                      보낼 값, 호출 데이터, gasLimit
   - 계약 코드, 저장소
           |                               |
           +---------------+---------------+
                           v
              [상태 전이 함수 Υ]
               수신 주소가 계약이면 EVM이 그 코드를 실행한다
               256비트 스택 기계, gasLimit 안에서만 계산한다
                           |
           +---------------+---------------+
           v                               v
 [다음 상태 σt+1]                    [영수증]
  잔액과 저장값이 바뀐다              유형, 상태 코드(1 성공 / 0 실패),
  실패하면 호출의 변경은 되돌린다     누적 가스 사용량, 로그
```

English:

```text
 [Current state σt]                  [Transaction T]
  address -> account state            signature, nonce, recipient or contract creation,
   - balance, nonce                   value, call data, gasLimit
   - contract code, storage
           |                               |
           +---------------+---------------+
                           v
              [State transition function Υ]
               if the recipient is a contract, the EVM runs its code
               256-bit stack machine, computing only within gasLimit
                           |
           +---------------+---------------+
           v                               v
 [Next state σt+1]                   [Receipt]
  balances and storage change         type, status code (1 success / 0 failure),
  on failure, the call's changes      cumulative gas used, logs
  are reverted
```

왼쪽 위의 상태와 오른쪽 위의 거래가 상태 전이 함수에 함께 들어가고, 아래의 다음 상태와 영수증이 함께 나온다. 앱이 확인하는 것은 아래 두 칸이다. 잔액과 저장값은 상태를 조회해 읽고, 성공 여부와 비용 및 로그는 영수증에서 읽는다. 실패한 거래도 가스 사용량은 영수증에 남는다. 그림은 황서의 2절(The Blockchain Paradigm), 4.1(World State), 4.4.1(Transaction Receipt), 5절(Gas and Payment)과 9.1(Basics)을 따랐다.

실행 계층의 역할은 Solidity 계약을 실행하는 데 그치지 않는다. [노드 아키텍처](https://github.com/circlefin/arc-node/blob/main/docs/ARCHITECTURE.md)는 거래 풀(transaction pool), 블록 실행기와 후보 구성 기능 및 Arc의 프리컴파일을 연결한다. 후보를 만들 때는 대기 거래를 선택하고 실행 결과를 포함한 블록 데이터를 구성한다. 받은 후보를 검사할 때는 실행 규칙에 맞는지 판정한다. 확정된 결과를 반영한 뒤에는 잔액과 블록 및 영수증을 조회할 수 있게 한다. 여기서 영수증은 포함된 거래의 실행 결과와 사용 가스 등을 읽는 기록이다.

**노드 아키텍처: 실행 계층 안의 구성 요소**

한국어:

```text
[합의 계층: Malachite]
  블록 제안, 투표 관리
     |                                     ^
     | forkchoiceUpdated, newPayload       | getPayload
     v                                     |
[Engine API 경계: 같은 호스트는 IPC, 분리된 호스트는 HTTP]
     |
     v
[실행 계층: Reth 기반]
  JSON-RPC 제출 --> [거래 풀 검사] --> [거래 풀]
                                          |
                                          v
                                   [후보 구성기] 거래 선택과 순서, 가스 한도
                                          |
                                          v
                                   [블록 실행기] --> [EVM과 프리컴파일] --> [상태 트리]

  Arc 프리컴파일
    0x1800..0000  네이티브 코인 권한: 발행, 소각, 이전
    0x1800..0001  네이티브 코인 제어: 차단 목록
    0x1800..0002  시스템 회계: Fee Manager의 가스 수수료 순환 버퍼
    0x1800..0003  Call From: 일괄 호출과 memo 거래
    0x1800..0004  양자내성 서명(SLH-DSA-SHA2-128s) 검증
```

English:

```text
[Consensus layer: Malachite]
  block proposals, vote keeping
     |                                     ^
     | forkchoiceUpdated, newPayload       | getPayload
     v                                     |
[Engine API boundary: IPC on one host, HTTP across hosts]
     |
     v
[Execution layer: Reth-based]
  JSON-RPC submission --> [Pool validator] --> [Transaction pool]
                                                  |
                                                  v
                                           [Payload builder] selection and ordering, gas limit
                                                  |
                                                  v
                                           [Block executor] --> [EVM and precompiles] --> [State trie]

  Arc precompiles
    0x1800..0000  Native Coin Authority: mint, burn, transfer
    0x1800..0001  Native Coin Control: address blocklist
    0x1800..0002  System Accounting: gas fee ring buffer used by the Fee Manager
    0x1800..0003  Call From: batch calls and memo transactions
    0x1800..0004  Post-quantum signature (SLH-DSA-SHA2-128s) verification
```

그림은 위에서 아래로 합의 계층, 두 계층의 경계, 실행 계층 순서다. 경계를 지나는 세 호출 가운데 합의 계층이 후보를 받아 가는 것이 `getPayload`이고, 받은 후보를 실행 계층에 넘기는 것이 `newPayload`, 정본으로 정한 블록을 알리는 것이 `forkchoiceUpdated`다. 실행 계층 안에서는 제출된 거래가 거래 풀 검사를 거쳐 거래 풀에 들어가고, 후보 구성기가 그중에서 거래를 골라 순서를 정한다. 블록 실행기는 그 거래를 EVM으로 실행하고, Arc가 더한 프리컴파일이 USDC의 발행과 이전, 차단 목록 같은 기능을 처리한다. 실행 결과는 상태 트리에 반영된다.

이 그림은 1절(프로토콜 구성) 첫머리 개요 그림의 실행 계층 상자를 확대한 것이다. 본문이 거래 풀, 블록 실행기, 후보 구성과 프리컴파일을 한 문장으로 연결하므로, 각각이 어디에 놓이고 무엇을 넘기는지를 보이려고 그렸다. 근거는 [아키텍처 문서](https://github.com/circlefin/arc-node/blob/main/docs/ARCHITECTURE.md)의 계층 그림, 프리컴파일 목록, 후보 구성 설명과 데이터 흐름 그림이다. 이 문서는 저장소의 설명 문서이며, 그림은 현재 배포된 노드의 구성을 확인한 것이 아니다.

예를 들어 USDC 이전 요청을 처리하려면 잔액뿐 아니라 가스 비용과 주소 제한 및 이전 규칙도 함께 적용해야 한다. 계약 호출이 실패하면 의도한 계약 상태 변경을 되돌리는 실행 결과가 나올 수 있다. 이 실패를 규칙대로 기록한 블록은 유효할 수 있으므로, 실행 계층이 후보를 유효하다고 판정하는 것과 그 안의 모든 요청이 성공하는 것은 다르다. 실패가 언제 기록되며 어떤 비용이 남는지는 거래 처리와 거래 기록에서 구체화한다. 후보의 유효 판정과 그 안의 거래 하나가 성공하는 것이 어떻게 다른지는 3.3(거래 확정)의 판정과 기록 그림에서 나란히 놓고 비교한다.

Reth 기반이라는 사실도 Ethereum의 모든 실행 의미를 그대로 유지한다는 보장은 아니다. Arc는 네이티브 USDC와 수수료, 이전 제한 등 자체 규칙을 적용한다. 따라서 실행 계층을 이해할 때는 EVM이라는 공통 환경과 Arc가 추가하거나 바꾼 규칙을 함께 보아야 한다. EVM이라는 공통 환경은 이 절 앞쪽의 EVM 설명에서 다루었고, Arc가 바꾼 규칙은 7절(Arc의 EVM 차이)에서 설명한다. Ethereum과 같은 층과 Arc가 바꾼 층은 7절(Arc의 EVM 차이) 첫머리의 층 그림에서 쌓아서 보인다.

[Execution layer의 Reth 설명](https://docs.arc.io/arc/concepts/execution-layer.md)의 원문은 다음과 같다.

> Reth is written in Rust for performance, memory safety, and modular
> extensibility. Arc leverages this architecture to plug in stablecoin-native
> modules without modifying core EVM execution.

같은 문서는 Fee Manager와 CallFrom을 Live로, APS와 Stablecoin Services를 Planned로 구별한다. 프리컴파일의 System Accounting은 Fee Manager가 사용하는 가스 수수료 순환 버퍼(ring buffer)이며, PQ Signature Verify의 서명 방식은 `SLH-DSA-SHA2-128s`다. 이 구분은 문서의 제공 상태와 명세이며 실행 시험 결과는 아니다.

### 1.3 계층 간 연결: 후보 생성과 검증 및 상태 반영을 연결한다

두 계층은 Engine API를 통해 후보 생성과 검증 및 상태 반영을 연결한다. [아키텍처](https://github.com/circlefin/arc-node/blob/main/docs/ARCHITECTURE.md)와 노드 문서는 같은 호스트의 IPC 또는 분리된 프로세스의 HTTP와 JWT 구성을 설명한다. IPC는 로컬 프로세스 사이 통신이며 JWT는 해당 연결의 인증에 쓰는 토큰이다. 공개 앱의 JSON-RPC와 노드 내부 Engine API는 다른 접점이다.

공식 글 연결: [Arc’s Bespoke Consensus Layer Built Using Malachite](https://www.arc.io/blog/arcs-deterministic-finality-the-bespoke-consensus-layer-built-using-malachite) (2025-10-14, [공식 원문](https://www.arc.io/blog/arcs-deterministic-finality-the-bespoke-consensus-layer-built-using-malachite)). Malachite 소개는 합의와 실행의 프로세스 분리 및 Engine API 연결을 설명한다. IPC와 JWT 설정 및 후보 실행 시점의 상세 조건은 기존 기술 문서에서 확인한다.

Engine API는 합의 계층이 실행 계층에 작업을 요청하고 결과를 받는 인터페이스다. 제안자 측에서는 후보 구성을 요청해 블록 데이터를 받는다. 받은 후보의 검사에서는 실행 계층의 유효성 판정을 합의 처리에 전달한다. 확정 결정 이후에는 선택한 블록을 정본 상태로 반영하는 연결이 필요하다. 내가 이 작업을 나눈 이유는 후보를 계산했다는 사실, 후보가 유효하다는 판정과 후보가 확정됐다는 결정이 서로 대체되지 않기 때문이다. 구체적인 검사 범위는 뒤의 고정 Payload 코드 설명을 따른다.

앱이 JSON-RPC로 거래를 보냈다는 사실은 이 내부 작업을 모두 완료했다는 뜻이 아니다. 앱은 제출 응답을 받은 뒤 블록과 영수증 및 계약 결과를 조회한다. 내부적으로는 합의와 실행 사이의 통신이 필요하고, 외부적으로는 조회 노드가 해당 결과를 제공할 수 있어야 한다. 따라서 내부 Engine 연결의 오류, 합의 지연과 공개 RPC의 조회 오류를 같은 장애로 묶으면 원인을 잘못 판단할 수 있다.

따라서 합의를 거래 순서만의 결정으로 축소하거나 실행을 확정 이후 처음 하는 일로 읽으면 부족하다. 뒤의 거래 처리 설명에서는 후보를 만드는 실행, 받은 후보를 검사하는 실행 유효성, 정본 상태 반영과 앱이 읽는 영수증을 따로 설명한다.

**계층 간 연결: 연결 방식, 세 작업과 장애 위치**

한국어:

```text
외부 접점
[앱과 지갑] -- JSON-RPC: 거래 제출과 조회 --> [공개 RPC 주소] --> [RPC 제공 노드의 실행 계층]
                                                   (C) 조회 오류, 노드마다 다른 높이

노드 내부: Engine API
  연결 방식: 같은 호스트면 IPC 소켓, 다른 호스트면 HTTP(포트 8551)와 JWT 인증
  [합의 계층]                                               [실행 계층]
      |-- (1) 후보 구성 요청 ------------------------------->|  거래 풀에서 거래를 고른다
      |<-------------------------- 후보 payload: getPayload -|
      |-- (2) 받은 후보 검사: newPayload ------------------->|  실행 규칙으로 실행해 본다
      |<-------------------------- VALID / INVALID ----------|
      |-- (3) 정본 반영: forkchoiceUpdated ----------------->|  정본 블록과 상태를 정한다
      (A) 연결 오류: 소켓이나 JWT 문제, 한쪽 프로세스의 중단

노드 사이: 합의 망
  [이 노드의 합의 계층] <== libp2p: 제안, 투표 ==> [다른 검증자의 합의 계층]
      (B) 합의 지연: 투표권이 모이지 않거나 메시지가 늦게 도착
```

English:

```text
External interface
[Apps and wallets] -- JSON-RPC: submit and query --> [Public RPC endpoint] --> [RPC provider node's execution layer]
                                                         (C) query errors, nodes at different heights

Inside the node: Engine API
  transport: IPC socket on one host, HTTP (port 8551) with JWT auth across hosts
  [Consensus layer]                                         [Execution layer]
      |-- (1) request a candidate -------------------------->|  selects transactions from the pool
      |<------------------------ candidate payload: getPayload |
      |-- (2) check a received candidate: newPayload ------->|  executes it against the rules
      |<------------------------ VALID / INVALID ------------|
      |-- (3) apply canonical: forkchoiceUpdated ----------->|  sets the canonical block and state
      (A) connection failure: socket or JWT problem, one process down

Between nodes: consensus network
  [This node's consensus layer] <== libp2p: proposals, votes ==> [Other validators' consensus layers]
      (B) consensus delay: not enough voting power, or late messages
```

그림은 이 절의 세 문단을 한 장에 모은 것이다. 위쪽의 외부 접점과 가운데의 노드 내부는 서로 다른 접점이다. 가운데 줄의 연결 방식이 첫 문단의 IPC와 HTTP, JWT이고, (1)에서 (3)이 둘째 문단의 세 작업이며, (A)에서 (C)가 셋째 문단의 장애가 나는 세 위치다. (1)은 그 라운드의 제안자 노드만 하고, (2)는 제안을 받은 검증자가 하며, (3)은 확정 결정 뒤에 한다. 같은 거래가 보이지 않는 증상이라도 (A)는 노드 안의 연결을, (B)는 검증자 사이의 투표를, (C)는 앱이 묻는 RPC 노드를 살펴야 한다.

세 작업을 한 줄의 "요청과 결과"로 그리면 후보를 계산한 것, 후보가 유효하다는 판정과 후보가 정본이 된 것이 하나로 보인다. 이 셋을 나누고, 장애가 어디서 나는지를 같은 그림에 두려고 다시 그렸다. 호출 이름은 [아키텍처 문서](https://github.com/circlefin/arc-node/blob/main/docs/ARCHITECTURE.md)의 계층 그림과 단계 설명, 받은 후보를 `newPayload`로 검사한다는 것은 [고정 Payload 코드](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/crates/malachite-app/src/payload.rs)의 설명을 따랐다. 연결 방식은 [노드 운영 문서](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/docs/running-an-arc-node.md)의 IPC 설명, JWT 설명과 포트 표를 따랐다. 같은 문서는 두 호스트에 나누는 HTTP 방식이 v0.8.0부터 사용 중단(deprecated) 상태이며 v0.9.0에서 제거된다고 적는다. (A)에서 (C)의 구분은 셋째 문단의 분류를 내가 그림에 옮긴 것이다. 이 그림은 호출의 개념적인 순서이며, 코드의 정확한 호출 순서를 확인한 것은 아니다.

공식 개요의 설명 순서는 서로 다르므로 상세 경로와 함께 구별한다. System overview는 합의 계층이 순서를 정하고 확정한 뒤 실행 계층이 처리한다고 쓴다. Execution layer의 생애 설명은 Reth가 거래를 실행하고 상태 루트를 만든 뒤 합의 계층이 확정한다고 쓴다. 위의 후보 생성, 후보 재실행과 정본 반영 구분은 보존한 Engine API와 코드 경로에 근거하며, 두 개요 문장을 하나의 실행 시점으로 합치지 않는다.

[System overview의 계층 순서](https://docs.arc.io/arc/concepts/system-overview.md)의 원문은 다음과 같다.

> The consensus layer orders
> and finalizes, then the execution layer processes and applies state changes.

[Execution layer의 거래 생애](https://docs.arc.io/arc/concepts/execution-layer.md)의 원문은 다음과 같다.

> which the consensus layer then finalizes into an irreversible block.

### 1.4 통신망(network): 노드 사이에서 거래, 블록과 투표가 오가는 경로는 역할마다 다르다

Arc의 노드는 같은 소프트웨어를 실행하지만 설정에 따라 네 종류로 나뉜다. 블록을 제안하고 투표하는 검증자 노드, RPC 제공 노드에 확정된 블록을 내주는 센트리(sentry), 공개 JSON-RPC로 거래를 받고 조회에 답하는 RPC 제공 노드, 확정된 블록을 받아 직접 검증하는 공개 풀 노드다. 각 노드의 운영 주체와 권한은 2절(참여 권한) 첫머리의 표에서 정리한다. 이 절에서는 이 노드들이 실제로 누구와 연결되어 어떤 메시지를 주고받는지 설명한다. 같은 노드 소프트웨어를 쓰더라도 역할에 따라 연결하는 상대와 받는 메시지가 다르다. 이 차이가 4.3.2(진행성)의 메시지 전달 조건이 어느 망에서 성립해야 하는지를 정하고, 2.2(공개 풀 노드)가 무엇을 받아서 검증하는지를 정한다.

Arc 노드의 두 계층은 서로 다른 P2P(peer-to-peer) 통신을 쓴다. 실행 계층은 Reth가 쓰는 devp2p로 거래를 주고받고, 합의 계층은 libp2p로 블록 제안과 투표를 주고받는다. [노드 운영 문서](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/docs/running-an-arc-node.md)는 RPC 제공 노드가 "connect to network sentries via devp2p (EL) and libp2p (CL)"라고 적는다. 센트리(sentry)는 이 문서가 쓰는 이름이다. 다만 문서는 센트리가 어떻게 구성되는지, 검증자와 어떤 관계인지는 설명하지 않는다. 두 망이 어느 노드 사이에 놓이는지는 아래 목록 다음의 그림 하나에 모아 그렸다.

역할마다 연결하는 상대는 다음과 같다.

- **검증자 사이의 합의 메시지:** 블록 제안은 libp2p의 Gossipsub 위에서 128 KiB 크기의 조각으로 나뉘어 스트림으로 퍼진다. [ADR-0002(블록 전파 프로토콜)](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/docs/adr/0002-block-dissemination-protocol.md)의 결정 절과 상수 표가 근거다. 이 ADR의 상태는 Draft이다. 투표는 블록 전체가 아니라 블록의 참조에 대해 이루어진다. [Malachite 소개 글](https://www.arc.io/blog/arcs-deterministic-finality-the-bespoke-consensus-layer-built-using-malachite)은 이를 "run consensus on references to proposed blocks rather than on full block payloads"라고 설명한다. 같은 글은 메시지 재전송을 gossip 계층이 아니라 합의 쪽의 별도 진행성 부속 프로토콜(liveness sub-protocol)이 맡는다고 적는다.
- **공개 풀 노드:** 합의 gossip에 참여하지 않는다([노드 문서](https://docs.arc.io/arc/concepts/running-a-node.md) ). 운영 문서의 기본 설정은 follow 모드이고, "We provide three endpoints from which the node retrieves finalized blocks."라고 적는다. 예시의 세 주소는 Circle, dRPC와 Blockdaemon의 테스트넷 RPC다. follow 노드는 블록을 만들지 않으므로 제출받은 거래를 블록을 만드는 상류 노드로 넘긴다. [거래 전달 문서](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/docs/tx-forwarding.md)가 근거다.
- **RPC 제공 노드:** 온보딩 때 받은 센트리 주소로 직접 연결한다. 운영 문서의 포트 표를 보면, 실행 계층의 P2P 포트 30303은 무허가 노드가 거래를 퍼뜨릴 수 있도록 공개한다. 반면 합의 계층의 P2P 포트 27000은 온보딩 때 받은 피어의 IP만 허용한다. 거래는 신뢰하는 피어에게만 전파하고, 합의 계층은 `--no-consensus`로 합의 gossip을 구독하지 않도록 권장한다.

**역할별 통신 경로: 닫힌 합의 망과 공개 영역**

한국어:

```text
 [닫힌 합의 망: 온보딩한 참여자만 연결한다]
 4.3.2(진행성)의 메시지 전달 조건은 이 안에서 성립해야 한다
 ...................................................................
 :
 :  [허가된 검증자] <== libp2p: 제안 조각(128 KiB), 투표 ==> [허가된 검증자]
 :          :
 :          : ?
 :          :
 :  [네트워크 센트리]
 :..........|.......................................................
            |  합의 계층: libp2p 27000, 온보딩 때 받은 IP만 허용
            |  실행 계층: devp2p
            v
 [공개 영역: 누구나 연결한다]
 -------------------------------------------------------------------
 |
 |  [RPC 제공 노드] -- 공개 JSON-RPC --> [앱과 지갑]
 |       |      |
 |       |      +-- devp2p 30303(공개): 거래 전파 --> [무허가 노드]
 |       |
 |       |  HTTP나 WebSocket: 확정 블록
 |       v
 |  [공개 풀 노드(follow 모드)]
 |     위조된 블록이 오면: 서명 검사로 거부한다
 |     주소가 모두 응답하지 않으면: 새 블록을 받지 못한다
 |     제출받은 거래: 블록을 만드는 상류 노드로 넘긴다
 |     합의 gossip: 받지 않는다
```

English:

```text
 [Closed consensus network: onboarded participants only]
 The message-delivery condition of 4.3.2 (liveness) must hold inside here
 ...................................................................
 :
 :  [Permissioned validator] <== libp2p: proposal parts (128 KiB), votes ==> [Permissioned validator]
 :          :
 :          : ?
 :          :
 :  [Network sentries]
 :..........|.......................................................
            |  consensus layer: libp2p 27000, onboarding-provided IPs only
            |  execution layer: devp2p
            v
 [Public zone: anyone can connect]
 -------------------------------------------------------------------
 |
 |  [RPC provider node] -- public JSON-RPC --> [Apps and wallets]
 |       |      |
 |       |      +-- devp2p 30303 (public): transaction gossip --> [Permissionless nodes]
 |       |
 |       |  HTTP or WebSocket: finalized blocks
 |       v
 |  [Public full node (follow mode)]
 |     forged block arrives: rejected by the signature check
 |     no endpoint answers: receives no new blocks
 |     submitted transactions: forwarded to an upstream node that builds blocks
 |     consensus gossip: not received
```

그림은 위아래 두 구역으로 나뉜다. 점선으로 두른 위 구역은 온보딩한 참여자만 연결하는 닫힌 합의 망이고, 실선 아래 구역은 누구나 연결하는 공개 영역이다. 두 구역의 경계를 지나는 것은 센트리와 RPC 제공 노드 사이의 연결뿐이다. 검증자와 센트리 사이의 물음표 점선은 그 연결을 문서에서 찾지 못했다는 뜻이다. 공개 풀 노드는 공개 영역 안에서 RPC 제공 노드 아래에 있다. 블록을 합의 망에서 받지 않고 RPC 제공자의 공개 주소에서 받기 때문이다.

그림에는 이 구성에서 내가 끌어낸 결론 두 가지도 담았다. 첫째, 위 구역에 적은 대로 4.3.2(진행성)이 요구하는 메시지 전달은 공개 인터넷 전체가 아니라 이 닫힌 망 안에서 성립해야 한다. 공개 노드가 늘어난다고 합의 메시지의 전달이 나아지지는 않는다. 둘째, 공개 풀 노드 상자의 첫 두 줄이다. 공개 풀 노드는 확정 블록을 몇 개의 엔드포인트에서 받는다. 엔드포인트가 위조된 블록을 넘기면 서명 검사가 그 블록을 거부하지만, 엔드포인트가 모두 응답하지 않으면 노드는 새 블록을 받지 못한다. 서명 검사는 위조를 막을 수 있지만 연결이 끊기는 것까지 막지는 못한다.

위 목록의 세 경로는 각각 그림의 한 부분이어서 따로 그리지 않고 이 그림 하나에 합쳤다. 근거는 위 목록의 노드 운영 문서, ADR-0002, 거래 전달 문서와 노드 문서이며, 두 구역으로 나누어 배치한 것은 내가 이 문서들을 종합한 것이다.

확인하지 못한 것도 있다. 검증자끼리 직접 연결하는지, 센트리를 거치는지, 검증자의 IP를 어떻게 감추는지는 찾지 못했다. [아키텍처 문서](https://github.com/circlefin/arc-node/blob/main/docs/ARCHITECTURE.md)는 libp2p로 블록을 주고받는 P2P 동기화를 기본(Default)으로 적고, HTTP로 블록을 받는 RPC 동기화를 경량 풀 노드의 대안으로 적는다. 그런데 운영 문서는 공개 풀 노드에 follow 모드를 안내한다. 두 문서의 차이는 해소하지 못했다.

### 1.5 데이터 보관(storage)과 가용성(data availability): 확정된 기록을 보관하고 내주는 경로

거래가 확정된 뒤에도 그 기록을 누군가 보관하고 내주어야 한다. 그래야 새 노드가 참여하고, 사용자가 과거 거래를 조회하며, 2.2(공개 풀 노드)의 직접 검증이 가능하다. 데이터 가용성은 원래 rollup이 거래 데이터를 다른 체인에 올리는지를 묻는 L2BEAT의 항목이다. Arc는 다른 체인에 데이터를 올리지 않는 독립 체인이므로, 이 절에서는 이 질문을 "확정된 기록을 원하는 사람이 받을 수 있는가"로 바꾸어 쓴다. 바꾼 질문은 나의 정의다. 기록을 내주는 경로는 이 절 끝의 그림에 모았다.

새 노드는 처음 블록부터 다시 실행할 수 없고, 스냅샷(snapshot)에서 시작한다. [노드 운영 문서](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/docs/running-an-arc-node.md)는 "Syncing a new Arc node from genesis is currently not supported."라고 적고, 스냅샷을 snapshots.arc.network에서 받는다고 설명한다. [노드 요구 사항 문서](https://docs.arc.io/arc/references/node-requirements.md)에 따르면 테스트넷 스냅샷은 압축한 크기로 실행 계층 약 68 GB, 합의 계층 약 16 GB다.

스냅샷은 실행 계층의 기록을 얼마나 담는지에 따라 세 가지로 나뉜다. 근거는 [스냅샷 도구 설명](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/crates/snapshots/README.md)에서 이다.

| 프로필          | 담는 것                                      | 문서가 맞는다고 적은 노드 |
| --------------- | -------------------------------------------- | ------------------------- |
| minimal(기본값) | 상태, 모든 블록 헤더와 최근의 짧은 구간      | 검증자와 센트리           |
| full            | 위에 더해 모든 거래, 영수증과 상태 변경 기록 | follow 노드               |
| archive         | 거래 발신자와 색인을 포함한 모든 구성 요소   | 따로 적지 않음            |

한 행은 스냅샷 프로필 하나다. 노드를 실행할 때 `--full`을 주면 실행 계층과 합의 계층 모두 오래된 데이터를 지운다(요구 사항 문서 ). v0.8.0부터는 이 정리 간격이 128블록이다([호환성 변경 기록](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/BREAKING_CHANGES.md) ).

기록을 내주는 쪽은 세 갈래다.

- **직접 운영:** [노드 문서](https://docs.arc.io/arc/concepts/running-a-node.md)는 "Anyone can run an Arc node without permission."이라고 적는다.
- **공개 RPC:** 메인넷의 공개 RPC 제공자 다섯은 2.1(사용자와 RPC 제공자)에서 정리한다. [RPC 주소 문서](https://docs.arc.io/arc/references/rpc-endpoints.md)에 따르면 Circle의 공개 엔드포인트에서 `eth_getLogs`는 한 번에 10,000블록까지만 조회한다. 문서는 이를 약 85분으로 환산한다.
- **확정 증명:** 운영 문서는 확정된 블록과 그 높이의 확정 증명서(`arc_getCertificate`)가 한 번 확정되면 계속 유효하므로 높이별로 캐시해도 된다고 적는다.

**확정된 기록을 받는 경로**

한국어:

```text
 [확정된 기록]
     |
     +-- 스냅샷: snapshots.arc.network ------------> [새 노드의 시작점]
     |      minimal(기본값): 상태, 모든 헤더, 최근 구간 ...... 검증자, 센트리
     |      full:    위에 더해 모든 거래, 영수증, 상태 변경 .. follow 노드
     |      archive: 위에 더해 발신자와 색인 ................ 적지 않음
     |
     +-- 직접 운영하는 노드 ------------------------> 스냅샷 시점 이후의 블록을 직접 재실행
     |
     +-- 공개 RPC: 메인넷 제공자 다섯 -------------> 조회. eth_getLogs는 한 번에 10,000블록까지
     |
     +-- 확정 증명서: arc_getCertificate ----------> 높이별로 캐시해도 된다

 [처음 블록부터 다시 실행]  지원하지 않는다
```

English:

```text
 [Finalized records]
     |
     +-- snapshots: snapshots.arc.network ---------> [starting point of a new node]
     |      minimal (default): state, all headers, recent window .. validators, sentries
     |      full:    adds all txs, receipts, state changes ........ follow nodes
     |      archive: adds senders and indexes ..................... not stated
     |
     +-- self-run node ----------------------------> re-executes blocks after the snapshot point
     |
     +-- public RPC: five mainnet providers -------> queries; eth_getLogs up to 10,000 blocks per call
     |
     +-- finality certificate: arc_getCertificate -> may be cached per height

 [Sync from genesis]  not supported
```

그림은 확정된 기록이 사용자와 노드에게 가는 네 경로를 한 줄씩 놓았다. 맨 위의 스냅샷은 새 노드가 시작하는 지점이며, 세 프로필은 담는 범위가 넓어지는 순서다. 점선 끝은 문서가 그 프로필이 맞는다고 적은 노드다. 아래의 처음 블록부터 다시 실행하는 경로는 지금 막혀 있으므로 따로 떼어 두었다. 이 절의 질문인 "확정된 기록을 원하는 사람이 받을 수 있는가"에 대한 답이 이 네 경로에 달려 있음을 보이려고 그렸다. 값과 이름의 근거는 위의 표와 목록에 적은 출처와 같다.

아래 두 판단은 이 자료에서 내가 끌어낸 것이다. 첫째, 처음 블록부터 다시 실행할 수 없으므로, 2.2(공개 풀 노드)의 "직접 다시 계산"은 스냅샷 시점 이후의 블록에만 적용된다. 스냅샷 이전의 상태가 검증자가 서명한 블록의 상태 루트와 맞는지를 노드가 확인하는지는 이 자료에서 찾지 못했다. 확인하지 않는다면 그 구간은 스냅샷 제공자를 믿는 셈이다. 둘째, 운영 문서는 스냅샷의 보관 기간을 "whatever its retention"이라고만 적는다. 전체 기록을 누가 얼마나 오래 보관하는지, 공개된 아카이브 노드가 있는지는 찾지 못했다. 따라서 과거 기록을 받을 수 있는지는 지금은 Circle과 소수의 RPC 제공자가 계속 운영하는지에 달려 있다.

## 2. 참여 권한: 누가 거래를 제출하고 검증하며 확정하는가

이 절은 거래와 규칙 처리에 참여하는 주체를 두 가지로 나누어 설명한다. 노드(node)는 Arc 노드 소프트웨어를 실행하는 컴퓨터 하나이고, 역할은 거래와 규칙 처리에서 맡는 일이다. 노드와 역할을 나눈 것은 나이며, 같은 소프트웨어를 실행하는 노드가 역할에 따라 전혀 다른 권한을 갖기 때문에 나누었다. 사용자나 관리 계약의 역할 보유자처럼 노드를 실행하지 않는 역할도 있다.

**노드의 종류.** [노드 운영 문서](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/docs/running-an-arc-node.md)는 Arc 노드를 실행 계층과 합의 계층의 두 프로세스로 설명하고, 누구나 허가 없이 노드를 실행할 수 있다고 적는다. 1절(프로토콜 구성)의 두 계층이 노드 하나 안에 함께 있다는 뜻이다. 같은 소프트웨어라도 어떤 설정으로 실행하는지에 따라 연결하는 상대와 하는 일이 달라진다. Arc 자료에 나오는 노드는 아래 네 종류다.

| 노드 종류                 | 운영 주체                                                                                       | 연결하는 상대                                                                                            | 합의 투표                          | 하는 일                                                                         | 근거                                                                                                                                               |
| ------------------------- | ----------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | ---------------------------------- | ------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| 검증자 노드               | 허가된 기관. 합의 문서는 "selected, known institutions with compliance obligations"라고 적는다. | 다른 검증자와 합의 망(libp2p)으로 연결한다. 검증자끼리 직접 연결하는지, 센트리를 거치는지는 찾지 못했다. | 한다                               | 후보 블록의 제안, 검사와 투표                                                   | [합의 문서](https://docs.arc.io/arc/concepts/consensus-layer.md), ADR-0002                                                                         |
| 센트리(sentry)            | 문서에 없다. RPC 제공 노드는 그 주소를 온보딩 때 받는다.                                        | RPC 제공 노드. 검증자와의 관계는 문서에 없다.                                                            | 문서에 없다                        | RPC 제공 노드에 확정된 블록을 내준다.                                           | 노드 운영 문서, [스냅샷 도구 설명](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/crates/snapshots/README.md) |
| RPC 제공 노드             | 온보딩을 거친 RPC 제공자                                                                        | 합의 계층은 센트리에만, 실행 계층은 센트리와 무허가 노드에 연결한다.                                     | 하지 않는다(`--no-consensus` 권장) | 공개 JSON-RPC로 거래를 받고 조회에 답한다. 거래는 신뢰하는 피어에게만 전파한다. | 노드 운영 문서                                                                                                                                     |
| 공개 풀 노드(follow 노드) | 누구나                                                                                          | RPC 제공자의 공개 주소에서 확정 블록을 받는다. 제출받은 거래는 블록을 만드는 상류 노드로 넘긴다.         | 하지 않는다                        | 검증자 서명 검사, 거래 재실행, 자기 RPC 제공                                    | 노드 운영 문서, [거래 전달 문서](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/docs/tx-forwarding.md)        |

한 행은 노드 하나의 실행 방식이다. 운영 문서의 포트 표는 RPC 제공 노드의 공개 포트가 "permissionless nodes"에 열려 있다고 적는다. 온보딩 없이 실행하는 노드를 이렇게 부른 것이며, 공개 풀 노드가 여기에 속한다고 나는 읽었다. 문서가 두 이름이 같다고 적지는 않는다.

이 표로 세 가지 질문에 답할 수 있다.

- **허가된 검증자 집합과 공개 풀 노드는 다른가?** 다르다. 둘 다 같은 Arc 노드 소프트웨어를 실행하지만, 검증자 노드는 관리 계약에 등록된 키로 제안하고 투표한다(5.1(검증자 관리)). 공개 풀 노드는 이미 확정된 블록을 받아 서명을 검사하고 다시 실행할 뿐, 투표하지 않고 합의 gossip도 받지 않는다.
- **RPC 제공자는 노드인가?** RPC 제공자는 조직이고, 그 조직이 운영하는 노드가 RPC 제공 노드다. 앱이 보는 것은 그 노드들 앞에 놓인 공개 주소다. 메인넷의 공개 주소를 내는 다섯 제공자는 2.1(사용자와 RPC 제공자)에서 정리한다. Circle의 주소는 여러 백엔드 노드로 요청을 나누므로, 연달아 보낸 요청이 높이가 조금 다른 노드에서 답을 받을 수 있다([RPC 주소 문서](https://docs.arc.io/arc/references/rpc-endpoints.md) ). 이 다섯 제공자가 각각 운영 문서의 RPC 제공 노드 절차대로 노드를 운영하는지는 확인하지 않았다.
- **RPC 제공자는 허가된 검증자에만 연결하는가?** 문서상 RPC 제공 노드는 검증자가 아니라 센트리에 연결한다. 운영 문서는 RPC 제공 노드가 "should only communicate with sentries"라고 적는다. 센트리가 검증자와 어떻게 연결되는지는 문서에 없다. 이 연결은 1.4(통신망)에서 그림으로 설명했다.

**다섯 역할의 비교.** 아래 표는 거래와 규칙 처리에 참여하는 다섯 역할을 같은 기준으로 비교한다.

| 역할                    | 운영하는 노드                           | 하는 일                                           | 결정할 수 있는 것                         | 그 사실만으로 생기지 않는 권한                                              |
| ----------------------- | --------------------------------------- | ------------------------------------------------- | ----------------------------------------- | --------------------------------------------------------------------------- |
| 사용자와 지갑           | 없어도 된다                             | 계정 키 또는 승인한 방식으로 요청에 서명한다.     | 서명할 요청의 내용                        | 검증자 등록, 자산 발행 및 상품 가입 권한은 별도다.                          |
| RPC 제공자              | RPC 제공 노드                           | 조회와 제출 요청을 받으며 노드의 상태를 반환한다. | 없다. 요청을 전달하고 결과를 돌려준다.    | 응답이 네트워크 전체의 접수와 일정 시간 내 포함을 보장하지 않는다.          |
| 공개 풀 노드의 운영자   | 공개 풀 노드                            | 확정의 서명과 실행 결과를 직접 검사한다.          | 없다. 자기 노드가 받아들일지만 정한다.    | 합의 제안 및 투표에 참여하지 않는다.                                        |
| 허가된 검증자           | 검증자 노드                             | 제안과 후보 검사 및 투표로 블록 확정에 참여한다.  | 어떤 블록을 확정할지                      | 임의로 모든 실행 규칙을 무시하거나 외부 은행 지급을 완료하는 권한은 아니다. |
| 관리 계약의 역할 보유자 | 없어도 된다. 키로 관리 계약을 호출한다. | 맡은 함수에서 집합이나 매개변수를 바꾼다.         | 검증자 집합과 규칙의 변경, 5절(운영 권한) | 역할 이름만으로 실제 기관과 키 보관 방식을 알 수 없다.                      |

한 행은 거래나 규칙 처리에 참여하는 역할 하나다. "하는 일"과 "그 사실만으로 생기지 않는 권한" 열은 원래 2.3(합의 검증자)에 있던 표에서 옮겼고, "운영하는 노드"와 "결정할 수 있는 것" 열을 더했다. 같은 기관이 여러 역할을 맡을 수도 있지만 이번 연구에서 그 실제 대응을 확인하지 않았다. 네트워크 공개성을 상품 승인이나 토큰 정책까지 모두 자유롭다는 뜻으로 확대하지 않는다. 기관 서비스의 접근은 기업 업무와 개발 접근에서 이어 확인한다.

아래 그림은 이 다섯 역할이 거래와 규칙에 어떻게 연결되는지 보여 준다. 세로 방향은 거래 요청이 지나는 경로이고, 각 역할 옆의 "결정"은 그 역할이 결과를 바꿀 수 있는 범위다. 거래가 검증자에게 도달하기까지의 전파 경로(로컬 풀과 재광고)는 3.1(거래 접수)에서 다루며 그림에서는 (2) 하나로 묶었다.

**참여 역할의 연결과 결정 범위**

한국어:

```text
 [사용자와 지갑]                    결정: 서명할 요청의 내용
     |                  ^
     | (1) 서명한 거래   | (5) 영수증과 잔액
     v                  |
 [RPC 제공자]                       결정 없음: 제출을 전달하고 노드의 조회 결과를 돌려준다
     |                  ^
     | (2) 거래 전달     | (4) 노드가 보관한 상태
     v                  |
 [허가된 검증자 집합] --(3) 확정 블록과 서명--> [공개 풀 노드]
  결정: 후보 제안과 투표로 블록 확정               결정 없음: 서명 검사와 거래 재실행
     ^
     | 등록, 활성 상태, 투표권과 설정의 변경
     |
 [관리 계약의 역할 보유자]          결정: 검증자 집합과 규칙의 변경, 5절(운영 권한)

(4)는 검증자 노드와 공개 풀 노드 중 RPC를 제공하는 노드의 응답이다.
```

English:

```text
 [User and wallet]                  decides: the content of the signed request
     |                  ^
     | (1) signed tx     | (5) receipt and balance
     v                  |
 [RPC provider]                     decides nothing: relays submissions, returns node query results
     |                  ^
     | (2) relay tx      | (4) state held by the node
     v                  |
 [Permissioned validator set] --(3) finalized block and signatures--> [Public full node]
  decides: block finality by proposing and voting              decides nothing: checks signatures, re-executes txs
     ^
     | registration, active status, voting power and configuration changes
     |
 [Management contract role holders] decides: changes to the validator set and rules, section 5

(4) is the response of whichever node serves the RPC, validator or public full node.
```

그림의 (1)에서 (5)까지가 거래 하나의 경로이고, 맨 아래의 관리 계약 역할은 거래 경로 밖에서 검증자 집합과 규칙을 바꾼다. 결정 범위가 있는 역할은 사용자, 검증자와 관리 계약의 역할 보유자 셋이며, 각각 요청의 내용, 블록의 확정, 규칙과 집합을 결정한다. RPC 제공자와 공개 풀 노드는 결과를 전달하거나 검사하지만 그 결과를 바꾸지는 않는다. 같은 기관이 여러 역할을 맡을 수 있지만, 기관과 역할의 실제 대응은 확인하지 않았다. 아래 2.1부터 2.3까지는 이 역할을 차례로 설명한다. 역할 사이의 연결과 확정된 기록의 보관은 앞의 1.4(통신망)와 1.5(데이터 보관)에서 설명했다.

**참여 권한의 용어 지도: 역할, 노드와 망**

한국어:

```text
 역할                          운영하는 노드                  연결하는 망과 주고받는 것
 --------------------------    ---------------------------    ----------------------------------------
 [사용자와 지갑] ----------- 노드 없음 -------------------> 공개 RPC 주소: 서명한 거래, 조회
 [RPC 제공자] -------------> [RPC 제공 노드] -------------> 실행 망(devp2p): 거래 전파
                                    |                         합의 계층은 센트리에만 연결
                                    v
                              [센트리] ........................ 운영 주체와 검증자와의 연결: 문서에 없음
                                    :
 [허가된 검증자] ----------> [검증자 노드] ===============> 합의 망(libp2p): 제안 조각, 투표
          ^
          | 등록, 활성 상태, 투표권
 [관리 계약의 역할 보유자] - 노드 없음, 키로 계약 호출 --> [검증자 집합과 설정]
 [공개 풀 노드 운영자] ----> [공개 풀 노드] <------------- RPC 제공자의 공개 주소: 확정 블록
                                                              제출받은 거래는 상류 노드로 넘긴다
```

English:

```text
 Role                          Node it runs                   Network it uses and what moves
 --------------------------    ---------------------------    ----------------------------------------
 [User and wallet] --------- no node ---------------------> public RPC endpoint: signed txs, queries
 [RPC provider] -----------> [RPC provider node] ---------> execution network (devp2p): tx gossip
                                    |                         consensus layer connects only to sentries
                                    v
                              [Sentry] ........................ operator and link to validators: not documented
                                    :
 [Permissioned validator] -> [Validator node] ============> consensus network (libp2p): proposal parts, votes
          ^
          | registration, active status, voting power
 [Management contract role holder] - no node, calls the contract with a key --> [Validator set and configuration]
 [Public full node operator] -> [Public full node] <------ RPC provider's public endpoint: finalized blocks
                                                              submitted txs are forwarded upstream
```

그림은 2절(참여 권한)에 나오는 낱말을 세 열로 나누어 잇는다. 왼쪽은 결정 범위를 갖는 역할, 가운데는 그 역할이 운영하는 노드, 오른쪽은 그 노드가 연결하는 망과 그 망으로 오가는 것이다. 사용자와 관리 계약의 역할 보유자는 노드를 운영하지 않아도 된다. 센트리는 RPC 제공 노드가 연결하는 상대로만 문서에 나오므로 점선으로 이었다. 바로 위의 그림이 거래 하나의 경로를 따라간다면, 이 그림은 같은 이름들이 서로 어떤 관계인지 한눈에 보이려는 것이다. 각 연결의 근거는 이 절 첫머리의 두 표와 1.4(통신망)의 출처와 같다. 열을 역할, 노드와 망으로 나눈 것은 나의 구분이다.

### 2.1 사용자와 RPC 제공자: 서명한 요청의 제출과 조회를 연결한다

사용자의 지갑 서명은 자기 계정의 자산 이전 또는 계약 호출을 요청한다. RPC(Remote Procedure Call)는 원격 노드에 거래 전송이나 상태 조회를 요청하는 인터페이스다. 일반 사용자가 공개 RPC로 거래를 제출할 수 있다는 설명과, 블록을 제안하거나 합의 투표에 참여할 수 있다는 설명은 다르다.

사용자가 결정하는 것은 서명할 요청의 내용이다. 수취 주소와 금액 또는 호출할 계약과 데이터, 계정 순서 및 수수료 조건이 그 내용에 속한다. 서명은 요청의 발신 권한을 확인하는 데 쓰이며, 네트워크가 그 요청을 반드시 포함하거나 실행을 성공시킨다는 약속은 아니다. 다른 사용자가 제출한 거래의 위치나 검증자 집합을 사용자의 서명만으로 결정할 수도 없다.

RPC 제공자는 앱과 노드 사이에서 제출과 조회를 연결한다. RPC 제공자는 공개 RPC 주소를 운영하는 조직이다. 메인넷에서는 Circle, Alchemy, Blockdaemon, dRPC와 QuickNode가 주소를 공개하고([RPC 주소 문서](https://docs.arc.io/arc/references/rpc-endpoints.md) ), Circle의 주소는 API 키 없이 쓸 수 있으며 다른 제공자는 자체 키를 요구할 수 있다. 이 조직들이 운영하는 노드가 2절(참여 권한) 첫머리의 RPC 제공 노드다. 앱이 제삼자 RPC를 이용하면 제출 응답과 조회 결과를 그 제공자에게서 받는다. 자기 노드의 RPC를 이용하면 직접 검증한 상태를 조회할 수 있다는 것이 [노드 문서](https://docs.arc.io/arc/concepts/running-a-node.md)의 설명이다. 어느 방식을 택하든 제출 응답, 블록 포함과 실행 결과를 구분해야 한다. 예를 들어 거래 해시를 받았지만 아직 영수증을 찾지 못했다면, 그 응답만으로 성공이나 실패를 결정할 수 없다.

### 2.2 공개 풀 노드: 확정된 기록과 실행 결과를 직접 검증한다

"노드"는 2절(참여 권한) 첫머리의 네 종류를 모두 가리키는 말이다. 공개 풀 노드는 그 가운데 하나이고, 합의에서 투표하는 노드는 검증자 노드뿐이다. 이 절은 누구나 실행할 수 있는 공개 풀 노드를 설명한다.

[노드 운영 문서](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/docs/running-an-arc-node.md)의 "What Your Node Does" 절을 따라, 공개 풀 노드가 확정된 블록 하나를 받아 처리하는 순서를 정리하면 아래와 같다. 순서를 단계로 나눈 것은 나이며, 각 단계의 규칙을 누가 정하는지와 Ethereum의 노드에서는 어느 소프트웨어가 그 일을 하는지를 함께 적었다.

| 순서 | 공개 풀 노드가 하는 일                       | 담당 계층                        | 그 규칙을 정하는 곳                                                                   | Ethereum의 노드에서는                                                                                                         |
| ---- | -------------------------------------------- | -------------------------------- | ------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| 1    | 확정된 블록을 받는다.                        | 합의 계층                        | Arc 노드 소프트웨어(follow 모드의 받을 주소)                                          | 블록은 P2P 망으로 모든 노드에 퍼진다. Merge 이후 실행 클라이언트는 블록 gossip을 껐으므로 블록을 받는 쪽은 합의 클라이언트다. |
| 2    | 블록에 검증자 집합의 서명이 있는지 확인한다. | 합의 계층                        | Arc의 합의 규칙(Malachite)                                                            | 합의 클라이언트가 지분증명 합의 알고리즘으로 Beacon Chain의 머리에 합의한다.                                                  |
| 3    | 블록의 거래를 차례로 다시 실행한다.          | 실행 계층(Engine API로 넘겨받음) | EVM의 상태 전이 규칙과 Arc의 차이. 1.2(실행 계층)와 7절(Arc의 EVM 차이)에서 설명한다. | 실행 클라이언트가 EVM으로 실행한다.                                                                                           |
| 4    | 실행 결과로 바뀐 상태를 보관한다.            | 실행 계층                        | 노드 소프트웨어의 구현(Reth의 저장 방식)                                              | 실행 클라이언트가 상태를 관리한다.                                                                                            |
| 5    | 로컬 JSON-RPC로 조회와 제출에 답한다.        | 실행 계층                        | Ethereum의 JSON-RPC 형식                                                              | 같은 JSON-RPC 형식이다(7절(Arc의 EVM 차이) 첫머리 호환 표의 노드 인터페이스 행).                                              |

한 행은 블록 하나를 처리하는 한 단계다. Arc 쪽 근거는 노드 운영 문서 이다. Ethereum 쪽 근거는 [ethereum.org 용어집](https://ethereum.org/en/glossary/)이다. 1번 행은 블록이 P2P 망으로 퍼진다는 설명과 Merge 때 실행 클라이언트가 블록 gossip을 껐다는 설명에서 내가 끌어냈다. 용어집은 합의 클라이언트가 거래를 검증하거나 상태 전이를 실행하지 않고 그 일은 실행 클라이언트가 한다고 적고, 실행 클라이언트가 "processing and broadcasting transactions and managing Ethereum's state"를 맡는다고 적는다. 블록을 제안하고 증명하는 일은 합의 클라이언트에 덧붙이는 선택 기능인 검증자 클라이언트가 한다.

이 표에서 EVM이 정하는 것은 3번 단계의 규칙뿐이다. [황서](https://ethereum.github.io/yellowpaper/paper.pdf)는 2절(The Blockchain Paradigm)에서 블록의 순서를 정하는 일은 합의 계층에 맡기고 자신은 실행만 기술한다고 밝힌다(1.2(실행 계층) 참고). 블록을 어디서 받고, 서명을 어떻게 확인하고, 상태를 어떻게 저장하는지는 노드 소프트웨어가 정한다. Ethereum도 같은 구조여서, 노드 하나가 실행 클라이언트와 합의 클라이언트 두 프로그램으로 이루어지고 검증자 기능은 따로 덧붙인다. Arc 노드가 두 계층의 두 프로세스로 이루어지는 것은 이 구조를 따른 것이다. 다른 점은 2번 단계다. Ethereum의 합의 클라이언트는 포크 선택으로 머리를 고르지만, Arc의 공개 풀 노드는 이미 확정된 블록의 서명만 확인한다.

[노드 운영 문서](https://docs.arc.io/arc/concepts/running-a-node.md)는 공개 풀 노드(full node)가 확정 블록의 검증자 서명을 검사하고 거래를 로컬에서 다시 실행하며 자체 RPC를 제공한다고 설명한다. 동시에 제안 및 투표를 하지 않고 합의 gossip에도 참여하지 않는다고 명시한다. gossip은 참여자가 메시지를 서로 전파하는 통신 방식이다. 스스로 결과를 검사하는 능력은 승인된 검증자가 가진 결정권을 대신하지 않는다.

공식 글 연결: [Run Your Own Arc Node and Join the Arc Bug Bounty Program](https://www.arc.io/blog/open-sourcing-arc-run-your-own-arc-node-and-bug-bounty-program) (2026-04-09, [공식 원문](https://www.arc.io/blog/open-sourcing-arc-run-your-own-arc-node-and-bug-bounty-program)). 공개 노드 글은 풀 노드가 합의에 참여하지 않는다고 명시한다. 거래 재실행과 스냅샷 검증의 상세 조건은 기존 노드 문서에서 확인한다.

서명 검사와 재실행은 서로 다른 것을 확인한다. 서명 검사는 검증자 집합의 확정 결정에 관한 기록을 확인한다. 재실행은 블록에 담긴 거래를 규칙대로 적용했을 때 결과를 로컬에서 확인하는 일이다. 이를 통해 노드는 제삼자 RPC가 알려 준 잔액을 그대로 믿는 대신 자신이 검증한 상태를 보관하고 조회할 수 있다.

직접 검증은 운영 책임도 수반한다. 노드가 어떤 버전과 설정을 사용하고 어디까지 동기화했는지 확인해야 자기 조회가 어떤 기록을 나타내는지 알 수 있다. 직접 검사할 수 있다는 능력과 항상 최신 결과를 반환한다는 운영 성질은 다르다. 또한 확정 서명을 검증한다고 검증자가 투표 전 주고받은 모든 메시지를 관측하는 것은 아니다. 공개 풀 노드는 확정 결과를 검사하는 참여자이며 그 결정을 새로 만드는 투표자는 아니다.

한국어:

```text
 방법 1: 받은 숫자를 저장
 [다른 서비스의 RPC] --잔액 응답--> [앱의 기록]
                                     믿는 대상: 그 서비스

 방법 2: 직접 다시 계산
 [확정된 블록] --> [내 풀 노드: 서명 확인, 거래 재실행] --> [내 노드의 상태] --> [로컬 RPC] --> [앱]
                                     믿는 대상: 검증자 서명과 직접 실행한 결과
```

English:

```text
 Method 1: store the number received
 [Another service's RPC] --balance response--> [App records]
                                     trusts: that service

 Method 2: recompute it
 [Finalized blocks] --> [My full node: check signatures, re-execute] --> [My node's state] --> [Local RPC] --> [App]
                                     trusts: validator signatures and its own execution
```

두 방법 모두 앱에 같은 숫자를 줄 수 있지만 믿는 대상이 다르다. 방법 1은 응답을 준 서비스를 믿어야 하고, 방법 2는 확정된 블록의 검증자 서명과 내 노드가 직접 실행한 결과를 믿는다.

### 2.3 합의 검증자: 후보 블록의 제안과 투표를 담당한다

앞의 합의 계층 문서가 설명하는 허가된 검증자는 후보 블록의 제안과 검사 및 투표로 확정에 참여한다. 이 결정권을 다른 네 역할과 비교한 표는 2절(참여 권한) 첫머리의 다섯 역할 비교에 있다.

제안자는 해당 라운드에서 후보를 내는 검증자다. 후보의 거래 목록과 배열은 제안자 측 실행 계층의 선택 및 구성으로 만들어지지만, 그 후보를 정본으로 받아들이는 결정에는 다른 검증자의 검사와 투표가 필요하다. 제안자가 자기 후보를 보냈다는 사실과 필요한 합의 투표권을 확보했다는 사실은 다르다. 제안과 투표가 어떻게 연결되는지는 다음 거래 처리에서 이어 설명한다. 라운드 단위의 자세한 절차는 4.2(합의 절차)에 있다.

현재 PoA(Proof-of-Authority) 구조에서 일반 노드 운영이나 ARC 토큰 보유만으로 합의 투표권을 얻지는 않는다. 검증자의 수입과 비용, 기관의 책임이 참여를 지속하고 올바르게 처리할 유인에 어떻게 연결되는지는 [네트워크 운영 참여자의 경제 조건](arc-section-06-value-token.md)에서 다룬다.

허가된 기관, 지역 분산과 가동 시간 협약은 합의 문서가 제시하는 운영 책임의 설명이다. 이는 투표권과 메시지 전달이라는 프로토콜 조건을 대체하지 않는다. 기관별 실제 키 보관과 가동 상태, 협약의 집행 및 손실 배상은 이 원고에서 확인한 결과가 아니다. 따라서 기관이 운영한다는 사실만으로 실행 성공이나 외부 지급 완료를 보장하는 것으로 해석하지 않는다.

공식 합의 문서는 검증자를 신원이 확인된 기업으로 설명하고, SOC 2 인증으로 감사된 보안과 가용성 기준을 충족하며, 지역을 분산하고, 가동 시간에 관한 서비스 수준 협약(uptime SLAs)을 통해 운영 가용성 요구사항을 준수한다고 제시한다. 이는 문서가 내세운 운영 조건이며 개별 기관의 인증과 현재 투표 참여를 직접 조사한 결과는 아니다.

공식 글 연결: [Arc’s Bespoke Consensus Layer Built Using Malachite](https://www.arc.io/blog/arcs-deterministic-finality-the-bespoke-consensus-layer-built-using-malachite) (2025-10-14, [공식 원문](https://www.arc.io/blog/arcs-deterministic-finality-the-bespoke-consensus-layer-built-using-malachite)). Malachite 소개는 검증자를 심사한 기관에서 선정한다고 설명한다. 개별 기관의 인증, SLA 이행이나 현재 투표 참여를 직접 확인한 자료는 아니다.

[Consensus layer의 검증자 조건](https://docs.arc.io/arc/concepts/consensus-layer.md)의 원문은 다음과 같다.

> **SOC 2 certified** -- Validators meet audited security and availability
> standards.

## 3. 거래 처리: 제출한 거래는 어떤 단계를 거쳐 실행되고 확정되는가

참여 주체를 구별했으므로 이제 요청이 어떤 기록으로 바뀌는지 살펴본다. 접수, 후보 구성과 검증, 합의 확정 및 실행 결과는 서로 다른 단계와 상태다.

아래 그림은 제출에서 확정과 결과 확인까지의 전체 경로다. 이 그림은 ChatGPT의 전체 경로와 Claude의 실행 검사 및 Grok의 실패 구분을 공식 판독에 맞춰 내가 재구성한 것이다. 화살표는 후보와 판정 및 기록의 연결이며 실행이 딱 한 번 발생한다는 뜻이 아니다.

한국어:

```text
[지갑: 요청과 서명]
          |
          v
[RPC 접수 / 로컬 거래 풀] -- 거절 또는 탈락 --> [확정 미관측]
          |
          v
[제안자의 실행 계층: 거래 선택 / 후보 구성]
          |
          v
[받은 후보 검사: 높이와 부모 / 실행 유효성]
          |
          v
[합의: prevote / precommit / 필요한 투표권]
          |
          v
[확정 블록 / 정본 상태 / 영수증]
          |
          +--> [status 1: 성공한 실행]
          +--> [status 0: 실패한 실행과 비용]
```

English:

```text
[Wallet: request and signature]
          |
          v
[RPC admission / local pool] -- reject or drop --> [Finality unobserved]
          |
          v
[Proposer execution layer: selection / candidate construction]
          |
          v
[Received candidate checks: height and parent / execution validity]
          |
          v
[Consensus: prevote / precommit / required voting power]
          |
          v
[Committed block / canonical state / receipt]
          |
          +--> [status 1: successful execution]
          +--> [status 0: failed execution and cost]
```

그림의 RPC 접수와 로컬 거래 풀은 3.1(거래 접수), 제안자의 후보 구성과 받은 후보의 검사는 3.2(후보 검증), 합의 투표와 확정 블록은 3.3(거래 확정), 거절과 탈락 및 status 0은 3.4(실패 처리)에서 설명한다.

### 3.1 거래 접수: 제출 요청을 검사하고 대기 거래를 보관한다

서명된 거래에는 목적 주소와 금액 또는 호출 데이터, 수수료 조건과 nonce가 들어간다. 논스(nonce)는 해당 계정의 거래 순서를 구별하는 값이다. 서명과 잔액 및 순서 등의 접수 조건을 통과하면 노드가 대기 거래를 보관하는 거래 풀(mempool)에 들어갈 수 있다. 로컬 풀은 한 노드의 대기 상태이며 모든 노드가 같은 거래를 같은 시각에 보유한다는 기록이 아니다.

접수와 포함 사이에는 거래가 후보를 구성하는 노드에 전달되고 실제 후보에 선택되는 과정이 남는다. 같은 계정의 앞선 거래가 처리되지 않아 순서가 비어 있거나 수수료 조건이 맞지 않으면, 제출 요청을 받았더라도 바로 포함되지 않을 수 있다. 아래 거래 생애 문서가 설명하는 대기와 탈락이 이 구간에 속한다. 따라서 접수 결과는 다음 상태를 추적할 출발점이지 확정된 지급 기록이 아니다.

이 원고의 출발점인 세 AI 답변 가운데 ChatGPT 답변과 Claude 답변은 읽기 노드의 상위 전달과 재광고, 후보 선택 및 대기 거래의 RPC 비노출을 나누어 설명했다. [변경 기록](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/BREAKING_CHANGES.md)은 v0.7.0에서 대기 거래를 공개하는 옵션이 기본 숨김으로 바뀌었다고 적는다. 이는 공개 원장에 확정된 거래의 기밀성을 제공한다는 뜻이 아니다. 이번에 재광고의 모든 경로와 풀 용량 및 현재 실행 옵션을 검증하지는 않았다.

[거래 생애](https://docs.arc.io/integrate/wallets/transaction-lifecycle.md)는 접수 거절과, nonce 간격이나 낮은 수수료 등으로 대기 거래가 탈락하는 경우를 구별한다. 해시가 있다는 사실은 성공의 증거가 아니며 영수증이 없다는 사실도 대기만의 증거가 아니다. 지갑과 지급 시스템은 제출 기록 및 재조회와 계정 순서를 함께 확인해야 한다.

공식 글 연결: [Arc Wallet Integration Guide: USDC Balances & Fees](https://www.arc.io/blog/supporting-arc-in-wallets-one-balance-usdc-fees-and-complete-history) (2026-09-04, [공식 원문](https://www.arc.io/blog/supporting-arc-in-wallets-one-balance-usdc-fees-and-complete-history)). 지갑 안내도 제출 전 거절, 대기 중 탈락 및 교체와 확정된 실행 실패를 구별한다. 모든 거래의 포함 기한을 보장하는 설명은 아니다.

**제출한 거래가 거치는 상태**

한국어:

```text
 [서명된 거래] -- eth_sendRawTransaction --> [RPC 접수 검사]
                                                 |       |
                                            통과 |       +-- 실패 --> (거절) 오류 응답, 대기 상태에 들어가지 않는다
                                                 v
 [이 노드의 로컬 풀: 대기(pending)]
    다른 노드의 풀과 같다는 보장은 없다
    대기 거래는 RPC로 보이지 않는다(v0.7.0부터 기본 숨김)
      |
      +-- 전파: 신뢰하는 피어에게, follow 노드는 상류 노드로 넘긴다
      |
      +-- nonce 간격이 메워지지 않음 ----------+
      +-- 최저 기본 수수료 20 Gwei 미만 -------+--> (탈락) 체인에 기록이 없고 영수증도 없다
      +-- 높은 부하에서 낮은 가격이 밀려남 ----+
      |
      v
 [제안자의 후보에 선택] --> 3.2, 3.3 --> (확정) 영수증이 생긴다: status 1 또는 status 0
```

English:

```text
 [Signed transaction] -- eth_sendRawTransaction --> [RPC admission checks]
                                                         |       |
                                                    pass |       +-- fail --> (rejected) error response, never pending
                                                         v
 [This node's local pool: pending]
    no guarantee other nodes' pools match
    pending txs are hidden from RPC (default since v0.7.0)
      |
      +-- propagation: to trusted peers; a follow node forwards upstream
      |
      +-- nonce gap never filled ---------------+
      +-- below the 20 Gwei minimum base fee ---+--> (dropped) no onchain record, no receipt
      +-- evicted for low price under load -----+
      |
      v
 [Selected into a proposer's candidate] --> 3.2, 3.3 --> (final) receipt exists: status 1 or status 0
```

그림은 제출한 거래가 끝나는 세 자리를 보인다. 접수 검사에서 바로 거절되는 경우, 로컬 풀에서 대기하다 탈락하는 경우, 후보에 선택되어 확정되는 경우다. 가운데의 로컬 풀 상자가 이 절 첫 문단의 "한 노드의 대기 상태"이고, 상자 안의 둘째 줄이 셋째 문단의 대기 거래 비공개이며, 오른쪽으로 갈라지는 세 줄이 둘째 문단과 넷째 문단의 대기와 탈락이다. 거절과 탈락은 모두 체인에 기록을 남기지 않지만, 거절은 제출할 때 오류로 바로 알 수 있고 탈락은 영수증이 끝내 나타나지 않는 것으로만 알 수 있다. 그래서 넷째 문단은 해시와 영수증만으로 판단하지 말고 계정 순서를 함께 보라고 한다.

이 절의 네 문단은 한 거래가 지나는 같은 경로의 서로 다른 구간을 설명하므로, 문단마다 따로 그리지 않고 경로 하나에 구간을 표시했다. 상태의 이름과 갈래는 [거래 생애 문서](https://docs.arc.io/integrate/wallets/transaction-lifecycle.md)의 상태 그림, 거절 설명과 탈락 설명을 따랐다. 대기 거래의 비공개는 [변경 기록](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/BREAKING_CHANGES.md)를, 전파 상대는 [노드 운영 문서](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/docs/running-an-arc-node.md)과 [거래 전달 문서](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/docs/tx-forwarding.md)를 따랐다.

### 3.2 후보 검증: 거래로 블록 후보를 구성하고 실행 유효성을 검사한다

현재 라운드의 제안자(proposer)는 실행 계층을 통해 거래를 선택하고 후보 블록의 payload를 만든다. payload는 거래 목록과 실행 결과를 담은 블록 데이터다. [고정 Payload 코드](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/crates/malachite-app/src/payload.rs)의 생성 함수는 Engine에 후보 구성을 요청하며, 받은 후보의 검사 함수는 합의 높이와 실행 블록 번호, 바로 이전 블록을 가진 경우 부모 해시의 연결을 확인한 다음 Engine의 판정을 받는다. 동기화 중 이전 블록이 바로 전 높이가 아닌 경우 부모 연결 검사는 이 함수에서 생략되는 조건도 있다.

Engine의 VALID는 후보를 받아들였다는 판정이다. INVALID는 거절 판정이며, SYNCING과 ACCEPTED 또는 내부 통신 오류는 코드가 기대한 확정적인 판정을 확보하지 못한 경우로 처리한다. 판정 미확보 오류를 유효한 후보나 포함된 실패 거래로 바꾸지 않는다. 기존 [받은 제안 코드](https://github.com/circlefin/arc-node/blob/main/crates/malachite-app/src/handlers/received_proposal_part.rs)는 이 판정을 `block.validity`에 기록하고 합의에 전달할 값의 유효성으로 연결한다.

이 열람으로 확인한 것은 선택한 공개 코드의 검사와 전달 경로다. 기존 main 주소 캡처와 새 고정 커밋이 동일 버전인지, 실제 검증자의 바이너리가 이 코드인지 및 모든 정본 반영 경로가 같은지는 확인하지 않았다. 내부 처리 그림은 이 한계를 유지한다.

**후보 구성과 받은 후보의 검사**

한국어:

```text
후보를 만드는 과정: 그 라운드의 제안자
[합의 계층] -- 후보 구성 요청 --> [실행 계층: 거래 선택, 실행, payload 구성]
[합의 계층] <-- payload ----------+
    +-- PROPOSAL로 보낸다

받은 후보를 검사하는 과정: 제안을 받은 검증자
[받은 payload]
    |
    +-- 검사 1: 블록 번호 = 합의 높이 ? ------------------ 아니오 --> INVALID
    |
    +-- 검사 2: 바로 전 높이의 블록을 갖고 있다면
    |           부모 해시 = 그 블록의 해시 ? ------------- 아니오 --> INVALID
    |           바로 전 블록이 없으면(동기화 중) 건너뛴다
    |
    |   검사 1과 2의 INVALID는 실행 계층에 묻지 않고 정한다
    |
    +-- 검사 3: newPayload로 실행 계층에 넘긴다
                   |
                   +-- VALID --------------------------> 유효한 후보로 합의에 전달
                   +-- INVALID, 내부 오류가 아닌 오류 --> 무효로 합의에 전달
                   +-- SYNCING, ACCEPTED, 내부 오류 ---> 판정 없음: 오류로 처리
```

English:

```text
Building a candidate: the round's proposer
[Consensus layer] -- build request --> [Execution layer: select txs, execute, build payload]
[Consensus layer] <-- payload ---------+
    +-- send it as PROPOSAL

Checking a received candidate: a validator that received the proposal
[Received payload]
    |
    +-- check 1: block number = consensus height ? ------- no --> INVALID
    |
    +-- check 2: if the block at the previous height is held,
    |            parent hash = that block's hash ? -------- no --> INVALID
    |            skipped when that block is not held (during sync)
    |
    |   INVALID from checks 1 and 2 is decided without asking the execution layer
    |
    +-- check 3: hand it to the execution layer with newPayload
                   |
                   +-- VALID ---------------------------> passed to consensus as valid
                   +-- INVALID, or a non-internal error -> passed to consensus as invalid
                   +-- SYNCING, ACCEPTED, internal error -> no verdict: treated as an error
```

그림은 위아래 두 과정이다. 위는 그 라운드의 제안자가 실행 계층에 후보를 만들게 하는 과정이고, 아래는 제안을 받은 검증자가 그 후보를 검사하는 과정이다. 아래 과정의 세 검사는 위에서부터 차례로 한다. 검사 1과 검사 2는 payload가 체인의 제자리에 맞는지를 합의 계층이 직접 보는 것이고, 여기서 걸리면 실행 계층은 그 payload를 보지 못한다. 검사 3에서 실행 계층이 돌려주는 답은 세 갈래다. VALID와 INVALID는 판정이지만, SYNCING과 ACCEPTED, 내부 오류는 판정이 아니라 오류로 처리된다. 이 갈래가 둘째 문단이 말하는 "판정 미확보"다.

이 절의 두 문단은 검사의 순서와 판정의 갈래를 문장으로 설명하므로, 두 문단에 따로 그림을 두지 않고 이 자리의 그림 하나에 모았다. 근거는 [고정 Payload 코드](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/crates/malachite-app/src/payload.rs)다. 코드의 `check_payload_binding` 검사, 실행 계층에 문의하기 전의 거절, 실행 판정의 갈래와 합의에 전달하는 무효 판정을 근거로 구성했다. 이 그림은 선택한 고정 커밋의 코드 경로이며, 현재 배포된 검증자의 바이너리가 이 코드인지는 확인하지 않았다.

후보 구성과 후보 검사는 역할도 다르다. 제안자 측의 구성은 무엇을 어떤 순서로 담을지 정하는 작업이다. 받은 후보의 검사는 이미 제시된 값이 현재 높이와 이전 블록 및 실행 규칙에 맞는지 판단하는 작업이다. 검사에 통과했다는 사실은 그 거래 배열이 사용자에게 가장 공정하거나 가장 빠르다는 판정이 아니다. 유효한 후보 안에서도 특정 거래가 빠질 수 있으므로, 실행 유효성과 개별 거래 포함은 별도 질문으로 남는다.

### 3.3 거래 확정: 합의 투표를 거쳐 블록과 실행 결과를 기록한다

검증자들은 제안된 후보에 prevote와 precommit의 두 단계로 투표하고, 필요한 투표권의 precommit을 관측하면 그 높이의 후보를 확정한다. 한 라운드에서 결정하지 못하면 같은 높이에서 다음 라운드를 시도하며, 이것은 이미 확정한 블록을 다시 고르는 과정이 아니다. 단계마다 무엇을 보내는지, 높이와 라운드가 무엇이며 언제 다음 라운드로 넘어가는지, 잠금이 무엇인지는 4.2(합의 절차)의 한 높이의 합의 절차 그림과 함께 설명한다.

앱이 관측하는 영수증은 이런 투표 메시지 자체가 아니라 포함된 거래의 실행 결과다. 합의의 확정 기록과 영수증을 함께 읽어야 포함 여부와 성공 여부를 구분할 수 있다.

공식 글 연결: [Arc Wallet Integration Guide: USDC Balances & Fees](https://www.arc.io/blog/supporting-arc-in-wallets-one-balance-usdc-fees-and-complete-history) (2026-09-04, [공식 원문](https://www.arc.io/blog/supporting-arc-in-wallets-one-balance-usdc-fees-and-complete-history)). 지갑 안내는 영수증의 블록 번호와 실행 status를 함께 읽도록 설명한다. 후보의 내부 INVALID 판정은 기존 사양 및 코드 근거에서 확인한다.

`INVALID` 후보와 `status 0` 거래는 다르다. 전자는 후보 블록의 유효성 판정이고, 후자는 유효하게 확정된 블록 안에서 실패한 거래의 영수증이다. 실패한 호출의 상태 변경을 되돌린 결과와 사용한 가스를 기록하는 블록도 유효할 수 있다. 거래의 확정과 성공을 같은 표시로 합치면 이 차이를 놓친다.

**INVALID 후보와 status 0 거래**

한국어:

```text
 INVALID: 후보 블록 하나에 대한 판정        status 0: 확정된 블록 안의 거래 하나에 대한 기록
 ---------------------------------------    ------------------------------------------------
 [받은 후보 블록]                           [확정된 블록 n]  블록 자체는 유효하다
      |                                       거래 1  status 1  상태 변경이 반영된다
      v                                       거래 2  status 0  상태 변경은 되돌려진다
 검사 결과: INVALID                                             사용한 가스는 낸다
      |                                                         nonce는 소모된다
      +-- 합의에 무효로 전달한다              거래 3  status 1  ...
      +-- 이 후보는 확정되지 않는다
      +-- 체인에 남지 않는다                  체인에 남는다
          노드에 조사용 기록만 남긴다

 누가 보는가: 검증자의 합의 처리            누가 보는가: 앱과 지갑, 영수증으로
```

English:

```text
 INVALID: a verdict on one candidate block  status 0: a record of one tx inside a finalized block
 ---------------------------------------    ------------------------------------------------
 [Received candidate block]                 [Finalized block n]  the block itself is valid
      |                                       tx 1  status 1  state changes applied
      v                                       tx 2  status 0  state changes reverted
 check result: INVALID                                        gas used is paid
      |                                                       nonce is spent
      +-- passed to consensus as invalid      tx 3  status 1  ...
      +-- this candidate is not finalized
      +-- does not stay on the chain          stays on the chain
          the node keeps a forensic record

 Who sees it: validators' consensus         Who sees it: apps and wallets, via receipts
```

왼쪽과 오른쪽은 판정하는 대상이 다르다. 왼쪽의 INVALID는 블록 후보 전체에 대한 검증자의 판정이며, 그 후보는 확정되지 않으므로 앱이 볼 기록이 체인에 생기지 않는다. 오른쪽의 status 0은 유효하게 확정된 블록 안에 있는 거래 하나의 실행 결과다. 그 블록의 다른 거래는 성공할 수 있고, 실패한 거래도 가스와 nonce를 쓴 기록으로 체인에 남는다. 그래서 앱이 status 0을 보았다면 블록이나 합의의 문제가 아니라 그 거래의 실행이 실패한 것이고, 같은 nonce로 다시 보낼 수 없다.

두 낱말이 모두 "실패"로 번역되기 쉬워서, 대상과 남는 기록을 나란히 놓아 구분하려고 그렸다. 왼쪽은 [고정 Payload 코드](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/crates/malachite-app/src/payload.rs)의 무효 판정과 조사용 기록 설명을, 오른쪽은 [거래 생애 문서](https://docs.arc.io/integrate/wallets/transaction-lifecycle.md)의 실행 중 되돌림 설명과 nonce 소모 설명을 따랐다. 1.2(실행 계층)의 USDC 이전 예시 문단이 이 그림을 가리킨다.

### 3.4 실패 처리: 접수 거절과 대기 및 확정된 실행 실패를 구별한다

| 관측한 경로      | 남는 기록과 효과                                                           | 확인할 다음 행동                                                                 |
| ---------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| 제출 시 거절     | RPC 오류가 나고 거래는 대기 상태에 진입하지 않을 수 있다.                  | 제출한 거래와 오류 원인을 확인한다.                                              |
| 대기 또는 탈락   | 제출 기록은 있으나 확정 영수증을 아직 확인하지 못했다.                     | nonce, 잔액과 수수료 및 기존 해시를 재조회한다.                                  |
| 확정된 성공      | status 1과 대상 계약의 결과를 확인할 수 있다.                              | 계약 결과와 지급 대상 및 외부 완료를 이어 확인한다.                              |
| 확정된 실행 실패 | status 0이며 시도한 호출 변경은 되돌아가지만 사용 가스와 nonce가 소비된다. | 실패 원인을 해결한 뒤 새 nonce로 거래를 계획한다. 기존 지급과의 중복을 확인한다. |

한 행은 서로 다른 처리 결과다. [거래 생애의 Runtime revert](https://docs.arc.io/integrate/wallets/transaction-lifecycle.md)는 차단으로 포함된 실패가 "status: 0" 영수증을 남기며 가스를 사용한다고 설명한다. 남은 가스의 반환과 이미 사용한 가스의 비용도 구별한다. 여러 문서의 공통 안내는 같은 차단을 영수증 없이 가스를 소비하는 것으로 적어 상세 설명과 충돌한다. 여기서는 상세 경로를 채택하고 실제 버전별 거래 시험은 남긴다.

같은 문서의 UX 안내는 포함 시 Complete나 Success를 표시하도록 제안한다. 그러나 자체 실패 예외에 따르면 블록 포함만으로 지급 성공을 표시해서는 부족하다. 영수증의 실행 결과와 대상 계약의 효과를 함께 읽어야 한다. 재시도의 구현은 개발 설명, 지급 객체와 거래 교체의 차이는 기업 업무 설명로 이어진다.

공식 글 연결: [Arc Wallet Integration Guide: USDC Balances & Fees](https://www.arc.io/blog/supporting-arc-in-wallets-one-balance-usdc-fees-and-complete-history) (2026-09-04, [공식 원문](https://www.arc.io/blog/supporting-arc-in-wallets-one-balance-usdc-fees-and-complete-history)). 지갑 안내는 온체인 revert를 확정된 실패로 설명한다. 블록 포함만으로 성공을 표시하지 않는 이유이며 가스와 nonce의 효과는 상세 기술 근거를 유지한다.

예를 들어 수취 주소가 제한되어 포함된 이전이 되돌아갔다면, 지급하려던 금액의 이전은 성공하지 않았어도 거래의 실패 기록과 사용한 가스는 남을 수 있다. 반면 접수 전에 거절된 요청을 같은 온체인 실패로 집계하면 실제 비용과 계정 순서를 잘못 해석한다. 영수증을 못 찾은 경우에도 아직 대기 중인지, 풀에서 탈락했는지 또는 조회 경로에 문제가 있는지부터 구분해야 한다. 실패는 화면의 오류 문구보다 어느 단계의 어떤 기록으로 확인했는지가 중요하다.

## 4. 합의: 블록을 확정하는 절차는 무엇이며 그 확정은 어떤 조건에서 성립하는가

앞의 거래 경로가 확정에 도달하려면 합의의 전제가 성립해야 한다. 4.1(합의의 발전)에서 이 전제들이 어디서 왔는지를 보고, 4.2(합의 절차)에서 블록 하나를 정하는 라운드의 단계를 설명한다. 4.3(성립 조건)에서는 그 절차가 성립하는 조건을 충돌하는 확정을 막는 조건, 새 확정을 이어가는 조건, 개별 거래를 포함하는 조건과 스팸과 과부하를 견디는 조건으로 나누어 살펴본다. 다른 네트워크의 합의와 비교하는 일은 6.2(합의 비교)에서 한다.

### 4.1 합의의 발전: 비잔틴 장군 문제에서 Tendermint와 Malachite까지

아래 4.3.1(안전성)부터 4.3.3(거래 포함)까지에서 쓰는 3분의 1, 3분의 2, 부분 동기와 잠금은 Arc가 새로 정한 숫자나 규칙이 아니다. 분산 합의 연구가 40여 년 동안 쌓은 결과이며, Arc는 그 계보의 끝에 있는 Tendermint 계열을 쓴다. 아래 연표는 그 계보 가운데 Arc를 이해하는 데 필요한 항목만 골라 정리한 것이다. 항목을 고른 것은 나이며.

**합의 연구에서 Arc까지의 주요 단계**

한국어:

```text
 1980  Pease, Shostak, Lamport     일부 참여자가 거짓말을 해도 합의할 수 있는가
       "Reaching Agreement..."     -> 전체 n, 고장 m일 때 n >= 3m + 1 이어야 풀린다
         |
 1985  Fischer, Lynch, Paterson    통신 시간에 상한이 전혀 없으면?
       (FLP)                       -> 고장 하나만 있어도 종료를 보장하는 방법은 없다
         |
 1988  Dwork, Lynch, Stockmeyer    상한이 있지만 모르거나, 언젠가부터 성립한다면?
       (DLS, 부분 동기)            -> 이 조건에서 동작하는 합의 프로토콜을 제시한다
         |
 1990  Schneider                   상태 기계 방식: 장애를 견디는 서비스를 복제로 구현하는 일반 방법
         |
 1999  Castro, Liskov (PBFT)       인터넷 같은 비동기 환경에서 쓸 수 있는 비잔틴 장애 허용 복제
         |
 2008  Nakamoto (Bitcoin)          누구나 참여하는 작업증명, 가장 많은 작업이 쌓인 체인
         |                         -> 확정이 아니라 되돌릴 확률이 줄어드는 방식
         |
 2014  Kwon (Tendermint 초안)      채굴 대신 DLS 알고리즘을 블록체인에 적용
         |                         예치한 코인이 투표권, prevote / precommit / commit,
         |                         3분의 2 다수로 확정, 비잔틴 투표권 3분의 1까지 허용
         |
 2019  HotStuff                    DLS, PBFT, Tendermint, Casper를 한 틀로 표현
         |
 2022  Ethereum의 Merge            작업증명에서 지분증명으로 전환 (Ethereum은 다른 계열)
         |
 Arc   Malachite                   CometBFT(Tendermint의 Go 구현) 운영 경험을 반영한
                                   Rust 구현의 Tendermint 엔진
```

English:

```text
 1980  Pease, Shostak, Lamport     Can parties agree when some of them lie?
       "Reaching Agreement..."     -> solvable only if n >= 3m + 1 (n total, m faulty)
         |
 1985  Fischer, Lynch, Paterson    What if message delay has no bound at all?
       (FLP)                       -> no protocol guarantees termination with even one fault
         |
 1988  Dwork, Lynch, Stockmeyer    What if a bound exists but is unknown, or holds from some time on?
       (DLS, partial synchrony)    -> consensus protocols that work under these conditions
         |
 1990  Schneider                   State machine approach: a general method for fault-tolerant replicated services
         |
 1999  Castro, Liskov (PBFT)       Byzantine fault-tolerant replication practical on the Internet
         |
 2008  Nakamoto (Bitcoin)          Open participation by proof of work, the chain with most work
         |                         -> the chance of reversal shrinks rather than finality
         |
 2014  Kwon (Tendermint draft)     DLS adapted to blockchains in place of mining
         |                         bonded coins as voting power, prevote / precommit / commit,
         |                         commit by a 2/3 majority, tolerates up to 1/3 Byzantine power
         |
 2019  HotStuff                    Expresses DLS, PBFT, Tendermint and Casper in one framework
         |
 2022  Ethereum's Merge            From proof of work to proof of stake (a different lineage)
         |
 Arc   Malachite                   A Rust Tendermint engine shaped by operating CometBFT
                                   (the Go implementation of Tendermint)
```

연표의 항목마다 읽은 범위가 다르다. 1980, 1985, 1988, 1990, 2019는 서지와 초록, 1999, 2008, 2014는 본문, 2022는 Circle 공지, Malachite는 Arc 블로그를 읽었다.

1980년의 문제는 서로 메시지만 주고받는 참여자 가운데 일부가 거짓말을 할 때 정상 참여자들이 같은 값에 도달할 수 있는가였다. [Pease, Shostak, Lamport의 초록](https://doi.org/10.1145/322186.322188)은 이 문제가 "n ≥ 3 m + 1"일 때만 풀린다고 밝힌다. 고장 난 참여자가 전체의 3분의 1 미만이어야 한다는 뜻이고, 4.3.1(안전성)의 "결함 투표권 1/3 미만"이 같은 조건이다. 같은 기록에 있는 FLP의 초록은 통신 시간에 상한이 없는 완전 비동기 환경에서는 고장 하나만으로도 종료하지 못할 가능성이 남는다고 증명한다. 그러면 현실의 네트워크에서는 무엇을 가정해야 하는가에 대한 답이 DLS의 부분 동기(partial synchrony)다. 상한이 있지만 미리 알 수 없거나, 상한이 어느 시점부터 성립하는 환경을 가정하면 합의 프로토콜을 만들 수 있다는 결과다. n >= 3m + 1의 산수는 4.3.1(안전성)의 두 정족수의 교집합 그림이 투표권으로 보인다.

[PBFT](https://www.scs.stanford.edu/nyu/03sp/sched/bfs.pdf)는 초록에서 이전 알고리즘이 동기 시스템을 가정했거나 실제로 쓰기에 너무 느렸다고 지적하고, 자신의 알고리즘은 인터넷 같은 비동기 환경에서 동작한다고 설명한다. [Bitcoin 백서](https://bitcoin.org/bitcoin.pdf)는 투표할 참여자를 미리 정하지 않고 누구나 작업증명으로 참여하게 하는 다른 길을 택했다. 그 대가로 투표로 확정하는 단계가 없어지고, 11절(Calculations)이 계산하듯 뒤에 블록이 쌓일수록 되돌릴 확률이 줄어드는 방식이 됐다.

[Tendermint 2014 초안](https://tendermint.com/static/docs/tendermint.pdf)은 두 흐름을 다시 합쳤다. 초안은 채굴 대신 "an existing solution to the Byzantine Generals Problem"을 블록체인에 적용한다고 밝히고, 6.1(On Byzantine Consensus)에서 그 기존 해법이 DLS 논문의 알고리즘이며 네트워크의 부분 동기를 가정한다고 적는다. 참여 자격은 코인을 예치(bond)한 검증자에게 주고, 예치한 양을 투표권으로 삼는다. 투표는 prevote, precommit, commit 세 종류이고, 검증자의 3분의 2 다수가 commit에 서명하면 블록이 확정되며, 비잔틴 투표권을 3분의 1까지 허용한다. 3.3(거래 확정)에서 본 prevote와 precommit, 4.3.1(안전성)의 3분의 2 정족수는 이 초안에서 이어진 구조다. 초안 스스로 "Draft v.0.6 (outdated)"라고 표시하므로, 현재 규칙은 이 원고가 읽은 [Tendermint 사양](https://github.com/circlefin/malachite/blob/72143f6c99a98452b587e1c392bdb80944eb2232/specs/consensus/overview.md)으로 확인한다. 사양이 완전한 증명을 맡기는 2018년 논문(arXiv 1807.04938)은 이번에 열지 않았다.

그 뒤의 연구는 같은 틀을 다듬었다. [HotStuff의 초록](https://arxiv.org/abs/1803.05069v6)은 부분 동기 모델의 리더 기반 프로토콜로서 DLS, PBFT, Tendermint와 Casper를 한 틀로 표현할 수 있다고 설명한다. Ethereum은 2022년 [Merge](https://www.circle.com/blog/how-circle-is-preparing-for-the-ethereum-merge)로 작업증명에서 지분증명(proof of stake)으로 바꾸었는데, 그 합의는 포크 선택과 체크포인트 완결을 결합한 다른 계열이다. 이 차이는 6.2(합의 비교)에서 다룬다. Arc의 [Malachite 소개 글](https://www.arc.io/blog/arcs-deterministic-finality-the-bespoke-consensus-layer-built-using-malachite)은 Malachite를 Informal Systems가 처음 구현한 Rust 기반의 BFT 엔진으로, 가장 널리 쓰이는 Tendermint의 Go 구현인 CometBFT를 유지하며 얻은 경험을 반영했다고 설명한다. 따라서 Arc의 합의는 1980년의 3분의 1 조건, 1988년의 부분 동기, 2014년의 예치 투표권과 3분의 2 확정을 그대로 물려받고, 예치 대신 허가된 검증자 집합을 쓴다는 점에서 달라진다. 집합을 누가 정하는지는 5절(운영 권한)의 질문이다.

**두 흐름의 갈림과 합류**

한국어:

```text
 [1980 Pease, Shostak, Lamport]  일부가 거짓말할 때의 합의: n >= 3m + 1
       |
 [1985 FLP]  통신 지연에 상한이 전혀 없으면 종료를 보장할 수 없다
       |
 [1988 DLS]  부분 동기를 가정하면 합의 프로토콜을 만들 수 있다
       |
       +------------------------------------------+
       |                                          |
 투표로 확정하는 흐름                       누구나 참여하는 흐름
 참여자를 미리 정한다                       참여자를 미리 정하지 않는다
 [1999 PBFT]                                [2008 Bitcoin]
   인터넷 같은 비동기 환경에서 실용적         작업증명, 가장 많은 작업의 체인
       |                                      투표 확정 없음, 되돌릴 확률이 줄어든다
       |                                          |
       |                                          +--> [2022 Ethereum Merge]
       |                                          |      지분증명, 포크 선택과 체크포인트(다른 계열)
       |                                          |
       +-------------------+----------------------+
                           |
 [2014 Tendermint 초안]
   투표로 확정하는 흐름에서: DLS 알고리즘, 3분의 2 확정, 3분의 1까지 허용
   누구나 참여하는 흐름에서: 블록체인, 채굴 대신 코인 예치로 참여 자격과 투표권
                           |
 [Malachite]  CometBFT 운영 경험을 반영한 Rust 구현
                           |
 [Arc]
   물려받은 것: 3분의 1 조건, 부분 동기, 3분의 2 확정, 라운드 절차
   바꾼 것: 예치 대신 허가된 검증자 집합, 집합의 변경은 관리 계약
```

English:

```text
 [1980 Pease, Shostak, Lamport]  agreement when some lie: n >= 3m + 1
       |
 [1985 FLP]  with no bound on message delay, termination cannot be guaranteed
       |
 [1988 DLS]  assuming partial synchrony, consensus protocols can be built
       |
       +------------------------------------------+
       |                                          |
 Deciding by vote                           Open participation
 participants fixed in advance              participants not fixed in advance
 [1999 PBFT]                                [2008 Bitcoin]
   practical in asynchronous settings         proof of work, the chain with most work
   such as the Internet                       no vote to finalize; reversal odds shrink
       |                                          |
       |                                          +--> [2022 Ethereum Merge]
       |                                          |      proof of stake, fork choice and checkpoints (a different lineage)
       |                                          |
       +-------------------+----------------------+
                           |
 [2014 Tendermint draft]
   from deciding by vote: the DLS algorithm, 2/3 commit, tolerates up to 1/3
   from open participation: a blockchain, bonded coins instead of mining for eligibility and voting power
                           |
 [Malachite]  a Rust implementation shaped by operating CometBFT
                           |
 [Arc]
   inherited: the 1/3 condition, partial synchrony, 2/3 commit, the round procedure
   changed: a permissioned validator set instead of bonding; the set is changed by a management contract
```

그림은 위의 연표를 한 줄로 늘어놓지 않고, 1988년 이후 갈라진 두 흐름과 2014년의 합류로 다시 배치한 것이다. 왼쪽은 참여자를 미리 정하고 투표로 확정하는 흐름이고, 오른쪽은 누구나 참여하고 투표 없이 가장 긴 체인을 따르는 흐름이다. Tendermint 초안은 왼쪽에서 확정 방식과 정족수를, 오른쪽에서 블록체인과 경제적 참여 자격을 가져왔다. 맨 아래 Arc 상자는 이 절 마지막 문단의 두 문장, 즉 물려받은 것과 바꾼 것을 그대로 옮겼다.

위의 연표는 시간순이어서 PBFT와 Bitcoin이 같은 줄 위의 앞뒤로 보이고, 둘이 서로 다른 질문에 답했다는 것과 Tendermint가 둘을 합쳤다는 것이 드러나지 않는다. 이 절의 셋째 문단부터 마지막 문단까지가 바로 그 갈림과 합류를 설명하므로, 그 관계를 보이려고 따로 그렸다. 두 흐름의 이름은 내가 붙인 것이다. 각 상자의 근거는 이 절의 문단에 적은 출처와 같고, 예치와 3분의 2, 3분의 1은 [Tendermint 2014 초안](https://tendermint.com/static/docs/tendermint.pdf)을 따랐다.

### 4.2 합의 절차: 한 높이의 블록은 propose, prevote와 precommit의 라운드로 정해진다

2.3(합의 검증자)과 3.3(거래 확정)은 제안과 투표를 결과 위주로 짧게 설명했다. 이 절은 Arc 합의의 바탕인 [Tendermint 사양](https://github.com/circlefin/malachite/blob/72143f6c99a98452b587e1c392bdb80944eb2232/specs/consensus/overview.md)이 블록 하나를 정하는 절차를 단계별로 설명한다. 뒤의 4.3.1(안전성)과 4.3.2(진행성)는 이 절차가 어떤 조건에서 올바르게 작동하는지를 묻는다. 아래 행 번호는 모두 이 사양의 것이다.

**높이와 라운드.** 높이(height)는 합의 한 번이 정하는 블록의 위치다. 한 높이에서 값 하나를 결정하면 그 높이가 끝나고 다음 높이를 시작한다. 한 높이는 0번부터 번호가 붙는 라운드(round)로 진행된다. 성공한 라운드에서는 그 라운드에 제안된 값을 결정하고, 실패한 라운드에서는 결정하지 못한 채 다음 라운드로 넘어간다. 라운드마다 제안자(proposer)가 하나 있고, 높이와 라운드를 넣으면 같은 답을 내는 결정적 함수 `proposer(h, r)`가 그 제안자를 고른다. 한 높이 안에서는 라운드가 바뀌어도 참여하는 집합이 바뀌지 않는다.

**한 라운드의 세 단계.** 라운드는 propose, prevote, precommit의 세 단계로 이루어진다.

- **propose:** 그 라운드의 제안자가 값을 골라 `PROPOSAL` 메시지로 모두에게 보낸다. 나머지 참여자는 제안을 기다릴 시간을 정하는 타임아웃을 건다. Arc에서 이 값은 실행 계층이 구성한 후보 블록이다(3.2(후보 검증)).
- **prevote(예비 투표):** 받은 값을 검사해 받아들이면 그 값의 식별자 `id(v)`에, 거절하면 지지할 값이 없다는 뜻의 `nil`에 `PREVOTE`를 보낸다. 타임아웃 안에 제안을 받지 못해도 거절한다. 3.2(후보 검증)에서 본 Engine의 VALID와 INVALID 판정이 이 검사에 들어간다. 판정을 이 단계에 연결한 것은 내가 3.2의 코드 경로와 사양을 맞추어 본 것이다.
- **precommit(확정 투표):** prevote 단계에서 같은 값에 대한 합의를 관측하면 그 값에, 관측하지 못하면 `nil`에 `PRECOMMIT`을 보낸다. 여기서 합의는 전체 투표권의 3분의 2를 넘는 표를 말한다. 사양은 이 기준을 그 집합 안에서 정상 참여자의 투표권이 결함 참여자의 투표권보다 많은 집합으로 정의한다.

**결정과 다음 라운드.** 어느 라운드든 같은 값에 대한 3분의 2 초과의 `PRECOMMIT`을 관측하면 그 값을 결정하고 높이를 확정한다. 결정한 라운드는 지금 라운드일 수도, 실패했다고 본 지난 라운드일 수도 있다. 서로 다른 값에 대한 `PRECOMMIT`이 섞여 결정하지 못하면 타임아웃을 걸고, 그 시간이 지나면 라운드가 실패한 것으로 보고 다음 라운드를 시작한다. 타임아웃은 라운드가 올라갈수록 길어져야 한다. Arc는 이 타임아웃 값을 ProtocolConfig에서 관리한다([ProtocolConfig 코드](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/contracts/src/protocol-config/ProtocolConfig.sol), 5.2(설정 관리)).

**잠금(lock).** 참여자는 어떤 값에 `PRECOMMIT`을 보내기 직전에 그 값과 라운드를 잠금 값으로 기록한다. 그 뒤로는 잠근 값과 다른 제안에 `nil`로 예비 투표한다. 예외는 하나다. 제안자가 잠긴 라운드보다 나중 라운드에서 그 값에 대해 3분의 2 초과의 prevote가 모였다는 증거(Proof-of-Lock)를 함께 보내면 다른 값도 받아들인다. 잠금은 서로 다른 라운드에서 서로 다른 값을 결정하지 않게 하는 장치이고, 4.3.1(안전성)의 설명이 이 규칙에 기댄다.

**한 높이의 합의 절차**

한국어:

```text
[높이 h 시작]
     |
     v
[라운드 r: propose] -- 제안자가 후보를 보낸다 / 나머지는 타임아웃을 건다
     |
     v
[prevote] -- 후보를 받아들이면 id(v), 거절하거나 늦으면 nil
     |
     v
[precommit] -- prevote에서 3분의 2 초과를 보면 id(v)와 잠금, 아니면 nil
     |
     +-- 같은 값에 3분의 2 초과의 precommit --> [값 결정: 높이 h 확정] --> [높이 h+1 시작]
     |
     +-- 결정하지 못하고 타임아웃 --> [라운드 r+1: 다음 제안자, 더 긴 타임아웃]
                                          |
                                          +--> propose로 돌아간다
```

English:

```text
[Start height h]
     |
     v
[Round r: propose] -- proposer sends a candidate / others start a timeout
     |
     v
[prevote] -- id(v) if the candidate is accepted, nil if rejected or late
     |
     v
[precommit] -- id(v) and lock if prevotes exceed 2/3, otherwise nil
     |
     +-- precommits for one value exceed 2/3 --> [Decide: height h committed] --> [Start height h+1]
     |
     +-- no decision before timeout --> [Round r+1: next proposer, longer timeout]
                                           |
                                           +--> back to propose
```

그림은 사양의 단계 설명을 한 높이의 흐름으로 이은 것이다. 세 단계는 위에서 아래로 진행하고, precommit에서 갈래가 둘로 나뉜다. 왼쪽 위의 갈래는 결정이고, 아래 갈래는 같은 높이에서 다음 라운드를 시도하는 경우다. 높이가 바뀌는 것은 결정했을 때뿐이다. 그래서 라운드가 여러 번 돌더라도 이미 확정한 블록을 다시 고르는 것이 아니다. 그림은 사양의 결정 규칙 가운데 지난 라운드의 precommit으로 결정하는 경우와 잠금의 예외를 생략했다.

### 4.3 성립 조건: 안전성, 진행성, 거래 포함과 과부하 저항은 서로 다른 전제를 요구한다

이 절은 4.2(합의 절차)가 올바르게 작동하는 조건을 네 가지 성질로 나누어 묻는다. 4.3.1(안전성)은 충돌하는 확정이 생기지 않는 조건, 4.3.2(진행성)는 새 확정이 계속 나오는 조건, 4.3.3(거래 포함)은 제출한 거래가 결국 들어가는 조건, 4.3.4(과부하 저항)는 스팸과 과부하 속에서도 처리가 이어지는 조건을 다룬다. 성질마다 필요한 전제가 다르므로 하나가 성립한다고 다른 것이 따라오지 않는다. 아래 표는 네 성질을 나란히 비교한다.

**합의의 성질별 조건 비교**

| 비교할 성질(property)       | 답하려는 질문                             | 살펴볼 조건                                                                             | 이 설명만으로 보장하지 않는 것   |
| --------------------------- | ----------------------------------------- | --------------------------------------------------------------------------------------- | -------------------------------- |
| 안전성(safety)              | 충돌하는 블록이 모두 확정될 수 있는가?    | 결함(faulty) 투표권, 정족수, 잠금 및 투표 규칙                                          | 새 블록이 계속 만들어지는 것     |
| 진행성(liveness)            | 새 확정을 계속 만들 수 있는가?            | 충분한 참여 투표권, 메시지 전달, 라운드와 타임아웃 조건                                 | 모든 제출 거래의 포함            |
| 개별 거래 포함              | 내가 제출한 거래가 포함되는가?            | 접수, 전파, 제안자의 선택, 실행 정책                                                    | 특정 순서나 기한 안의 포함       |
| 과부하 저항(DoS resistance) | 스팸과 과부하 속에서도 처리가 이어지는가? | 노드 RPC의 연결과 요청 제한, 거래 풀의 수수료 하한, 블록 가스 한도, 합의 망의 조각 제한 | 검증자 노드를 겨냥한 공격의 방어 |

안전성과 진행성은 분산 시스템에서 성질(property)을 나누는 표준 이름이며 이 원고가 만든 구분이 아니다. [Lamport의 1977년 논문](https://lamport.azurewebsites.net/pubs/proving.pdf)이 두 이름을 처음 나누어 썼다. 안전성은 "something will not happen", 진행성은 "something must happen"을 말하는 성질이다. [Alpern과 Schneider(1985)](https://decomposition.al/CSE232-2020-10/readings/liveness.pdf)는 이를 각각 "나쁜 일"이 일어나지 않는 성질과 "좋은 일"이 결국 일어나는 성질로 형식화했고, 모든 성질이 안전성과 진행성의 교집합으로 표현된다는 것을 보였다. Arc 합의의 바탕인 [Tendermint 사양](https://github.com/circlefin/malachite/blob/72143f6c99a98452b587e1c392bdb80944eb2232/specs/consensus/overview.md)도 이 구분을 따라, Safety 절의 결론으로 "two correct processes cannot decide different values in a height of consensus"를 제시하고 진행성을 "correct processes eventually decide"로 풀어 쓴다.

앞의 세 성질의 그림은 성질마다 하나씩, 그 성질을 설명하는 단위에 두었다. 안전성은 4.3.1(안전성)의 두 정족수의 교집합, 진행성은 4.3.2(진행성)의 네트워크 분할, 개별 거래 포함은 4.3.3(거래 포함)의 확정은 계속되고 거래 하나만 대기하는 그림이다. 과부하 저항의 장치는 4.3.4(과부하 저항)의 그림이 거래 경로 위에 놓는다.

셋째 행의 개별 거래 포함도 문헌에 있는 성질이다. 다만 합의 알고리즘이 아니라 원장(ledger)의 성질로 정의된다. [Garay, Kiayias, Leonardos의 Bitcoin backbone 논문](https://ilyasergey.net/CS6213/_static/papers/backbone.pdf)은 원장에 필요한 두 성질을 Persistence와 Liveness로 정의한다. Persistence는 거래가 k 블록보다 깊이 들어가면 모든 정직한 참여자의 원장에서 위치가 바뀌지 않는다는 성질이고, Liveness는 "all transactions originating from honest account holders will eventually end up at a depth more than k blocks"라는 성질이다. 같은 문단은 그래서 공격자가 정직한 사용자를 골라 거래를 막을 수 없다고 덧붙인다. [Bano 외의 합의 SoK](https://arxiv.org/pdf/1711.03936)도 Cachin 등의 정의를 빌려, 진행성의 한 조건(validity)을 노드가 보낸 메시지가 결국 합의된 순서에 들어가는 것으로 적고, 보안 평가 항목에 거래 검열 저항(transaction censorship resistance)을 따로 둔다. 따라서 같은 "liveness"라는 말이 합의 알고리즘에서는 "새 결정이 계속 나온다"를, 원장에서는 "내 거래가 결국 들어간다"를 뜻한다. 이 표는 두 뜻을 둘째 행과 셋째 행으로 나눈 것이고, 첫째 행의 안전성은 원장의 Persistence에 대응한다. 행을 이렇게 나눈 것과 각 행의 "살펴볼 조건", "보장하지 않는 것"은 이 원고가 정리한 내용이다.

liveness의 한국어 번역은 정해져 있지 않다.

#### 4.3.1 안전성: 투표권과 잠금 규칙으로 충돌하는 확정을 방지한다

안전성(safety)은 서로 충돌하는 결과를 확정하지 않는 성질이다. 진행성(liveness)은 새 높이의 결정을 계속 만들 수 있는 성질이다. [Tendermint 사양](https://github.com/circlefin/malachite/blob/72143f6c99a98452b587e1c392bdb80944eb2232/specs/consensus/overview.md)의 안전성 설명은 같은 높이의 전체 투표권에서 2/3를 초과하는 precommit, 1/3 미만의 결함 투표권과 잠금 규칙을 함께 사용한다. 잠금은 한 후보를 지지한 정상 참여자가 다른 라운드의 충돌 후보를 임의로 지지하지 않게 하는 규칙이다.

공식 글 연결: [Deterministic Sub-Second Finality on Arc](https://www.arc.io/blog/deterministic-finality-on-arc) (2025-10-09, [공식 원문](https://www.arc.io/blog/deterministic-finality-on-arc)). 최종성 소개는 검증자 집합의 2/3 초과라는 개괄 표현을 쓴다. 위 투표권 기준의 precommit과 결함 비율 및 잠금 규칙은 Tendermint 사양의 근거를 유지하며 이 블로그 표현으로 대체하지 않는다.

전체 투표권을 W, 두 확정 집합의 투표권을 A와 B라고 하자. 두 집합이 각각 2W/3를 초과하면 공통 투표권은 적어도 `A + B - W > 2W/3 + 2W/3 - W = W/3`다. 결함 투표권이 1/3 미만이라는 가정 아래 두 충돌 확정이 모두 존재하려면 이 공통 부분에 있는 정상 참여자의 잠금 및 투표 규칙을 깨는 상황이 필요하다. 이것은 정족수가 중요한 이유를 설명하는 계산이며 사양의 모든 라운드와 잠금 규칙을 증명한 결과는 아니다.

교집합과 위의 전제는 같은 높이에서 서로 충돌하는 확정이 양립할 수 없는 이유를 설명한다. 잠금 규칙은 라운드가 바뀌어도 정상 참여자가 충돌하는 후보로 임의로 지지를 옮기지 않도록 그 관계를 유지한다. 따라서 투표를 많이 모았다는 사실만 떼어 내면 충분하지 않다. 무엇에 투표했는지, 어느 집합의 투표권인지와 정상 참여자가 어떤 규칙을 지켰는지를 함께 유지해야 안전성의 설명이 성립한다.

Claude 답변이 사용한 동일 투표권 11개 예시는 [저장소 초기 설정](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/assets/mainnet/config.json)에서도 읽을 수 있다. 조회한 11개 항목이 각각 투표권 2000, 합계 22000을 가진다. 동일 투표권에서는 `8 > 2 * 11 / 3`이므로 8개가 정족수이며 `3 < 11 / 3`이므로 결함 3개의 투표권은 1/3 미만이다. 초기 설정의 가정에 따른 예시이며 현재 기관 수와 가동 여부의 관측이 아니다.

**두 정족수의 교집합**

한국어:

```text
전체 투표권 W 안의 두 확정 집합

|<--------------- 집합 A --------------->|
+------------------+--------------------+------------------+
| A에만 속한 부분  | A와 B의 공통 부분  | B에만 속한 부분  |
+------------------+--------------------+------------------+
                   |<--------------- 집합 B -------------->|

A > 2W/3, B > 2W/3
공통 투표권 >= A + B - W > W/3

함께 필요한 전제:
- 결함 투표권이 W/3 미만이다.
- 정상 참여자가 잠금 및 투표 규칙을 지킨다.

W, A와 B는 참여자 수가 아니라 투표권이다.
```

English:

```text
Two commit sets within total voting power W

|<---------------- set A ---------------->|
+-------------------+---------------------+-------------------+
| Only in A         | Shared by A and B   | Only in B         |
+-------------------+---------------------+-------------------+
                    |<---------------- set B ---------------->|

A > 2W/3, B > 2W/3
Shared voting power >= A + B - W > W/3

Additional assumptions:
- Faulty voting power is less than W/3.
- Correct participants follow locking and voting rules.

W, A and B denote voting power, not participant counts.
```

그림의 칸 길이는 실제 투표권 비율을 나타내지 않는다. 위 문단에 적은 대로, 이 계산만으로 모든 라운드의 안전성을 증명한 것은 아니다.

#### 4.3.2 진행성: 충분한 투표권과 메시지 전달을 요구한다

합의 문서는 정직하고 온라인인 참여자의 투표권이 2/3를 초과한다는 진행 조건을 설명한다. 사양은 정상 제안자가 같은 유효 후보를 보내고, 제안과 표가 타임아웃 전에 전달되며, 잠금 관계가 맞는 라운드가 결국 만들어진다는 조건을 더 구체화한다. 부분 동기성(partial synchrony)은 어느 시점 이후 통신 지연이 제한된 범위에 들어온다는 모형이다. 증가하는 타임아웃은 이 조건과 연결된다.

아래 그림은 ChatGPT 답변과 Grok 답변의 네트워크 분할 설명을 내가 나눈 것이다. 각 구역의 투표권은 현재 전체 집합을 기준으로 하며, 새로운 집합을 임의로 만들어 2/3를 다시 계산하지 않는다.

한국어:

```text
[같은 검증자 집합에서 네트워크 분할]
                    |
        +-----------+------------+
        |                        |
        v                        v
[어느 쪽도 필요한 표 미확보] [한쪽이 필요한 표 확보]
        |                        |
        v                        v
[새 확정 지연 / 마지막 확정 유지] [그쪽의 진행 조건을 검사]
                                 |
                                 v
                          [다른 쪽은 추후 동기화]
```

English:

```text
[Network partition within the same validator set]
                    |
        +-----------+------------+
        |                        |
        v                        v
[Neither side obtains quorum] [One side obtains quorum]
        |                        |
        v                        v
[New finality delayed / last commit retained] [Check its progress conditions]
                                           |
                                           v
                                   [Other side later synchronizes]
```

필요한 표를 실제로 모으지 못하면 새 결정을 만들 수 없지만 이미 확정한 상태가 사라지는 것은 아니다. 반대로 정직한 온라인 투표권의 충분조건을 입증하지 못했다고 매번 실제 체인이 정지했다고 역추론하지 않는다. 악의적인 참여자도 어떤 라운드에는 표를 줄 수 있다. 실제 진행의 관측과 안전성 및 진행을 보장하는 가정은 다른 질문이다.

메시지 전달이 필요한 이유는 검증자들이 같은 후보와 필요한 표를 관측해야 다음 합의 단계로 넘어갈 수 있기 때문이다. 프로세스가 켜져 있어도 후보나 표가 늦게 도착하면 해당 시도에서 결정에 도달하지 못할 수 있다. 그러므로 가동 상태만 보는 점검과 실제 합의 메시지가 제때 전달되는지 보는 점검은 다르다. 타임아웃과 라운드 변경은 지연 상황에서 다시 시도하는 규칙이며, 통신 조건을 무시한 즉시 확정을 보장하는 장치는 아니다.

Claude 답변이 제시한 시계 편차와 조각 크기는 두 계층의 통신 및 저장 압력과 함께 이 운영 조건을 검사할 후보다. 변경 기록은 서로 다른 버전의 mainnet P2P 식별자가 연결되지 않을 수 있는 변경도 설명한다. 모든 현재 버전과 설정을 관측하지 않았으며 이러한 코드 및 설명을 실제 장애 사례로 바꾸지 않는다.

공식 글 연결: [Arc Testnet Reliability Technical Insights](https://www.arc.io/blog/technical-insights-on-arc-testnet-reliability) (2025-12-18, [공식 원문](https://www.arc.io/blog/technical-insights-on-arc-testnet-reliability)). 테스트넷 안정성 글은 제안 시간 조절에 동기화된 시계라는 추가 가정이 필요했다고 설명한다. 과거 구현 설명이며 현재 메인넷의 같은 설정이나 실제 장애를 관측한 자료는 아니다.

#### 4.3.3 거래 포함: 블록 확정 속도와 개별 거래의 포함 조건을 구별한다

결정적 최종성(deterministic finality)은 가정 아래 확정한 블록을 같은 높이의 다른 블록으로 바꾸지 않는 설명이다. 앱이 확정 이후 추가 블록 개수만큼 기다리는 방식과는 다르다. 그러나 제출한 모든 거래가 즉시 포함된다는 뜻은 아니다. 풀 접수와 전파, 제안자의 선택 및 실행 정책은 그보다 앞에 있다.

순환 제안자는 제안 기회를 여러 검증자에게 돌리는 방식이다. 단일 제안자가 계속 독점하지 않는다는 설명과 모든 거래가 공정한 순서 및 기한 안에 포함된다는 보장은 다르다. 이번 선택 검증에서 모든 강제 포함 및 순서 정책을 확인하지 않았다. [합의 문서의 roadmap](https://docs.arc.io/arc/concepts/consensus-layer.md)이 적은 다중 제안자와 허가형 PoS(Proof of Stake, 지분을 기준으로 투표권을 정하는 합의) 전환은 예정 방향이다. 이를 현재의 검열 방지나 누구나 가능한 검증자 참여로 사용하지 않는다.

새 블록이 계속 확정되고 있는데 특정 거래의 영수증만 관측되지 않는 경우를 생각할 수 있다. 이때 합의 전체의 중단이라고 단정하기보다 해당 거래의 접수와 전파, 계정 순서, 수수료 조건 및 후보 선택을 확인해야 한다. 반대로 특정 거래가 포함됐다는 사실만으로 모든 사용자가 같은 기한과 순서로 처리됐다고 결론 내릴 수도 없다. 이는 앞에서 구분한 합의의 진행과 개별 거래 포함을 실제 조사 질문에 적용한 예시다.

**확정은 계속되고 거래 하나만 대기하는 경우**

한국어:

```text
 시간 ------------------------------------------------------------>
 확정된 블록:   [n] -- [n+1] -- [n+2] -- [n+3] -- [n+4] -- ...    합의는 진행한다(진행성)
                 ^
 내 거래 X:    제출 ..... 대기 ..... 대기 ..... 대기 ..... ?      영수증이 관측되지 않는다

 X가 머무는 자리: 모두 합의 밖이다          확인할 것
   접수와 전파: 제출한 노드의 풀에만 있다      제출한 노드, 전달 경로
   계정 순서: 앞선 nonce가 비어 있다           계정의 다음 nonce
   수수료 조건: 하한 미만이거나 밀려났다       maxFeePerGas와 현재 기본 수수료
   제안자의 선택: 후보에 고르지 않았다         여러 제안자에 걸친 대기 시간
```

English:

```text
 time ------------------------------------------------------------>
 finalized:     [n] -- [n+1] -- [n+2] -- [n+3] -- [n+4] -- ...    consensus proceeds (liveness)
                 ^
 my tx X:      submit ... pending ... pending ... pending ... ?   no receipt observed

 Where X is held: all outside consensus     What to check
   admission and propagation: only in the      the submitting node, the forwarding path
     submitting node's pool
   account order: an earlier nonce is missing  the account's next nonce
   fee conditions: below the floor or evicted  maxFeePerGas and the current base fee
   proposer selection: not picked              waiting time across several proposers
```

위 줄은 블록이 끊기지 않고 확정되는 모습이고, 아래 줄은 같은 시간 동안 거래 X가 한 번도 포함되지 않는 모습이다. 두 줄이 나란히 있다는 것이 이 절의 요점이다. 합의의 진행성은 위 줄을 보장하지만 아래 줄을 보장하지는 않는다. 아래 표는 X가 머무를 수 있는 네 자리와, 그때 확인할 것을 짝지은 것이다. 네 자리 모두 합의 투표보다 앞에 있으므로 블록 확정이 빠르다는 사실로는 X의 포함을 설명할 수 없다.

이 그림은 4절(합의) 첫머리 표의 셋째 행인 개별 거래 포함의 그림이다. 네 자리는 이 절의 첫 문단과 셋째 문단, 그리고 3.1(거래 접수)의 그림에 나오는 대기와 탈락의 갈래를 따랐다. 제안자의 선택에 강제 포함이나 순서 정책이 있는지는 이 절 둘째 문단에 적은 대로 확인하지 않았다.

[Consensus layer의 Roadmap](https://docs.arc.io/arc/concepts/consensus-layer.md)은 다중 제안자 외에 합의를 세 라운드에서 두 라운드로 줄이는 최적화와 허가형 PoS 가능성을 제시한다. 현재 절차가 이미 두 라운드라는 뜻은 아니다. [Litepaper의 MEV(Maximal Extractable Value, 거래 순서를 이용해 얻는 이익) 로드맵](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/Arc%20Litepaper%20-%202025.pdf)은 시장 간 가격을 맞추는 차익거래를 유익한 MEV(constructive MEV)로, 앞뒤에 거래를 끼워 넣는 샌드위치 공격(sandwich attack)과 해로운 선행매매(front-running)를 해로운 MEV(harmful MEV)로 나누고, 암호화된 mempool, 거래 일괄 처리와 다중 제안자를 완화 기법의 로드맵으로 제시한다.

반면 [P2P Payments의 Deterministic ordering](https://docs.arc.io/build/payments.md)은 순서 보장이 front-running을 방지하고 제출 순서대로 지급을 결제한다고 설명한다. 이 구절은 Litepaper의 완화 로드맵보다 강한 표현이다. 위의 개별 거래 포함 조건과 구별하여 공식 자료 사이의 설명 차이로 남긴다.

[P2P Payments의 순서 설명](https://docs.arc.io/build/payments.md)의 원문은 다음과 같다.

> Transaction ordering guarantees prevent front-running and ensure payments
> settle in the order they are submitted.

#### 4.3.4 과부하 저항(DoS resistance): 스팸과 과부하를 거래 경로의 여러 자리에서 막는다

4.3.2(진행성)은 충분한 투표권이 참여하고 메시지가 전달되면 새 확정이 계속 나온다고 설명했다. 그런데 누군가 의도적으로 거래를 쏟아붓거나 노드에 요청을 몰아 보내면, 투표권은 충분해도 처리가 느려지거나 멈출 수 있다. [Bano 외 2019](https://arxiv.org/pdf/1711.03936)는 DoS 저항을 "the system’s resilience to DoS attacks against nodes involved in consensus"로 정의한다. 이 절은 그 질문을 합의 노드에서 거래 풀과 공개 RPC까지 넓혀, Arc 자료에 나오는 장치를 위치별로 모았다. 위치를 이렇게 나눈 것은 나다.

| 위치           | 장치                                                                                                                                                                      | 근거                                                                                                                                                                                                                                                                           |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 거래 수수료    | 최소 기본 수수료 20 Gwei, 최대 20,000 Gwei. 하한보다 낮은 수수료의 거래는 거래 풀에서 버려지고 영수증도 남지 않는다.                                                      | [가스 문서](https://docs.arc.io/arc/references/gas-and-fees.md), [EVM 차이 문서](https://docs.arc.io/arc/references/evm-differences.md), [메인넷 설정](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/assets/mainnet/config.json)         |
| 블록 용량      | 블록 가스 한도 30,000,000                                                                                                                                                 | 메인넷 설정                                                                                                                                                                                                                                                                    |
| 합의 망        | 블록 제안 조각의 동시 스트림을 피어당 64개, 전체 100개로 제한하고 60초가 지나면 버린다. 서명이 잘못된 조각은 조립할 때 거부한다.                                          | [ADR-0002(블록 전파 프로토콜)](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/docs/adr/0002-block-dissemination-protocol.md)                                                                                                              |
| 합의 망의 노출 | RPC 제공 노드의 합의 계층 P2P 포트는 온보딩 때 받은 피어의 IP만 허용한다.                                                                                                 | [노드 운영 문서](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/docs/running-an-arc-node.md),                                                                                                                                             |
| 거래 풀        | 블록 구성 중 오류를 일으킨 거래를 무효 거래 목록에 올려 다시 들어오지 못하게 한다. v0.7.2부터 기본으로 켜져 있고, 목록의 기본 상한은 100,000건이다.                       | [호환성 변경 기록](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/BREAKING_CHANGES.md), [거래 풀 검사 코드](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/crates/execution-txpool/src/validator.rs) |
| 노드의 RPC     | 연결 250개, 연결당 구독 32개, 한 번의 묶음 요청 100건, `eth_call`의 가스 30,000,000이 기본 상한이다.                                                                      | [호환성 변경 기록](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/BREAKING_CHANGES.md)                                                                                                                                                    |
| 공개 RPC       | Circle의 공개 엔드포인트에서 `eth_getLogs`는 한 번에 10,000블록까지 조회한다. 노드 자체는 사용자별 요청 수를 제한하지 않으므로, 운영자가 앞단의 프록시에서 제한해야 한다. | [RPC 주소 문서](https://docs.arc.io/arc/references/rpc-endpoints.md), 노드 운영 문서                                                                                                                                                                                           |

한 행은 장치가 놓인 위치 하나다. 2026-10-07에 메인넷 공개 RPC로 최신 블록을 조회했을 때 기본 수수료는 20,000,000,000 wei(20 Gwei), 블록 가스 한도는 30,000,000이었다. 가스 문서는 수수료 값을 테스트넷 기준이라고 적지만, 메인넷도 같은 하한으로 운영되고 있었다.

수수료 하한은 스팸에 드는 최소 비용을 정한다. Arc의 가스는 USDC로 내므로 1 Gwei는 10^-9 USDC다. 하한 가격으로 블록 하나를 가득 채우려면 30,000,000 × 20 × 10^-9 = 0.6 USDC가 든다. 가스 문서의 블록 간격 약 0.5초를 쓰면 초당 약 1.2 USDC, 시간당 약 4,320 USDC다(1.2 × 3,600). 블록이 계속 차면 기본 수수료가 올라가므로 실제 비용은 이보다 크다. 상한 20,000 Gwei에서는 블록당 30,000,000 × 20,000 × 10^-9 = 600 USDC다. 이 계산은 내가 문서의 숫자로 한 것이며 실제 공격 비용을 측정한 것은 아니다. 다만 상한이 있다는 것은 공격자가 수수료를 끝없이 올려 일반 사용자를 밀어낼 수 없다는 뜻이기도 하고, 반대로 공격자가 내야 할 비용에도 상한이 있다는 뜻이기도 하다.

확인하지 못한 것도 있다. Bano의 정의가 직접 묻는 검증자 노드에 대한 공격에 어떻게 대비하는지, 즉 검증자 앞에 센트리를 두는지와 IP를 어떻게 감추는지는 찾지 못했다(1.4(통신망) 참고). 거래 풀의 크기와 계정당 대기 거래 수의 상한은 Arc가 Reth의 설정을 그대로 쓰는 것까지만 보았고, 메인넷 배포에서 그 값을 바꾸었는지는 열어 보지 않았다. 또한 [ADR-0003(블록 가스 한도 검증)](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/docs/adr/0003-governance-configuration-and-validation.md)은 "A proposer can set any gas limit and all nodes accept it, provided `gas_used <= gas_limit`."라는 공백을 기록한다. 이 ADR은 Draft 상태이고 마지막 수정이 2026-05-12이므로, 지금 코드에서 이 공백이 메워졌는지는 확인하지 않았다. [테스트넷 안정성 글](https://www.arc.io/blog/technical-insights-on-arc-testnet-reliability)은 블록 용량과 P2P 버퍼를 소진시키는 부하 생성기로 사전 시험을 한다고 설명한다. 다만 이것은 시험 방법의 설명이며 방어 장치의 명세는 아니다.

**거래 경로 위의 과부하 저항 장치**

한국어:

```text
 [앱과 공격자의 요청]
      |
      v
 [공개 RPC 앞단] ......... 사용자별 요청 제한은 노드에 없고 운영자의 프록시가 맡는다
      |                     eth_getLogs는 한 번에 10,000블록(Circle 주소)
      v
 [노드의 RPC] ............ 연결 250, 연결당 구독 32, 묶음 요청 100건, eth_call 가스 30,000,000
      |
      v
 [거래 풀] ............... 기본 수수료 하한 20 Gwei 미만은 버린다, 상한 20,000 Gwei
      |                     블록 구성 오류를 낸 거래는 무효 목록에(기본 100,000건)
      v
 [후보 블록] ............. 블록 가스 한도 30,000,000
      |
      v
 [합의 망] ............... 조각 스트림 피어당 64, 전체 100, 60초 뒤 폐기, 잘못된 서명 거부
      |                     RPC 제공 노드의 합의 포트는 온보딩한 IP만 허용
      v
 [검증자 노드] ........... ?
```

English:

```text
 [Requests from apps and attackers]
      |
      v
 [In front of public RPC] .. no per-user rate limit in the node; the operator's proxy does it
      |                       eth_getLogs up to 10,000 blocks per call (Circle endpoint)
      v
 [Node RPC] ................ 250 connections, 32 subscriptions each, batches of 100, eth_call gas 30,000,000
      |
      v
 [Transaction pool] ........ drops txs below the 20 Gwei base-fee floor; cap 20,000 Gwei
      |                       txs that broke block building go on an invalid list (default 100,000)
      v
 [Candidate block] ......... block gas limit 30,000,000
      |
      v
 [Consensus network] ....... part streams: 64 per peer, 100 total, dropped after 60 s; bad signatures rejected
      |                       RPC provider nodes' consensus port admits onboarded IPs only
      v
 [Validator node] .......... ?
```

그림은 요청이 앱에서 검증자 노드까지 가는 경로를 위에서 아래로 놓고, 위 표의 장치를 그 장치가 놓인 자리 옆에 적은 것이다. 위쪽 세 자리는 요청의 수와 크기를 제한하고, 거래 풀과 후보 블록은 스팸 거래 하나하나에 비용을 물리며, 합의 망은 제안 조각이 메모리를 채우지 못하게 한다. 맨 아래 검증자 노드의 물음표는 Bano의 정의가 직접 묻는 자리인데도 장치를 찾지 못했다는 뜻이며, 바로 위 문단의 확인하지 못한 것과 같다.

표는 장치마다 근거를 보여 주지만 장치가 경로의 어디에서 작동하는지는 보여 주지 못한다. 공격이 어느 자리를 넘으면 무엇이 막는지를 위에서 아래로 따라가 보이려고 그렸다. 숫자와 근거는 모두 위 표와 같다.

## 5. 운영 권한: 누가 검증자 집합과 실행 규칙을 변경하는가

앞에서는 주어진 검증자 집합과 규칙 아래에서 합의가 성립하는 조건을 살폈다. 이제 그 집합과 규칙을 누가 바꿀 수 있는지 확인한다.

**운영 권한과 적용 대상**

한국어:

```text
[검증자 관리 권한]
    +-- 등록 / 활성화 / 투표권 변경 --> [검증자 집합]

[설정 변경 권한]
    +-- 수수료 / 가스 / 타임아웃 변경 -> [프로토콜 설정]

[관리 계약의 정지 권한]
    +-- 해당 변경 함수의 정지 / 해제 -> [관리 호출]

[프록시 관리 권한]
    +-- 구현 변경 -------------------> [호출이 전달되는 구현]

[주소 제한 권한]
    +-- 주소 목록 변경 --------------> [접수 및 실행의 제한 정책]

[USDC의 자산 관리 권한]
    +-- 발행 / 소각 / 차단 ----------> [자산 처리 정책]

역할 주소와 실제 기관 및 키 보유자의 대응은 별도 확인 대상이다.
각 권한의 적용 위치와 현재 운영 상태도 별도로 확인한다.
```

English:

```text
[Validator management authority]
    +-- registration / activation / voting power changes --> [Validator set]

[Configuration authority]
    +-- fee / gas / timeout changes ----------------------> [Protocol configuration]

[Management contract pause authority]
    +-- pause / unpause the affected update functions -----> [Management calls]

[Proxy administration authority]
    +-- implementation changes ---------------------------> [Call implementation]

[Address restriction authority]
    +-- address list changes -----------------------------> [Admission and execution restrictions]

[USDC asset management authority]
    +-- mint / burn / block ------------------------------> [Asset processing policy]

Mapping role addresses to institutions and key holders requires separate verification.
The check locations and current operational state of each authority also need verification.
```

그림의 권한을 지금 누가 행사하는지는 아래 단위마다 확인한다. 그 출발점은 백서가 밝힌 초기 구조다. [Arc 백서](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/arc_whitepaper.pdf)는 초기의 결정 구조를 이렇게 제안한다. 프로토콜 규칙과 업그레이드는 "Circle decides with broad input, validators adopt"이고, 검증자 권한은 초기에 체인 밖에서 관리하며 검증자가 합류할 때 공개한다. 백서는 이 구조가 확정되지 않은 예비 안이라고 밝힌다(부근). [테스트넷 안정성 글](https://www.arc.io/blog/technical-insights-on-arc-testnet-reliability)은 "We anticipate many upgrades to come, planned and unplanned"라고 적는다.

### 5.1 검증자 관리: 등록과 활성 상태 및 투표권을 변경한다

[PermissionedValidatorManager](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/contracts/src/validator-manager/PermissionedValidatorManager.sol)는 허가형 검증자의 등록과 관리 계약이다. [ValidatorRegistry](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/contracts/src/validator-manager/ValidatorRegistry.sol)는 등록 정보와 활성 집합 및 투표권을 저장한다. 새 등록에는 기본 투표권 0을 사용한다. 지정 등록자(registerer)가 등록할 수 있으며 담당 controller가 활성화와 제거 및 투표권 변경을 요청한다. controller는 특정 검증자를 관리하도록 배정된 주소다.

ARC 토큰 백서의 초기 거버넌스 구상은 검증자 구성을 Circle이 정하도록 제안한다. 아래 코드는 권한 주소가 수행할 수 있는 기능을 설명하며, 현재 배포 주소의 키를 실제로 누가 보관하고 서명하는지 확인한 결과는 아니다. 검증자 제거와 투표권 변경 기능도 특정 위반에 자동 적용되는 금전적 제재와 구분한다. [백서의 초기 거버넌스](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/arc_whitepaper.pdf)

[controller 코드](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/contracts/src/validator-manager/roles/Controller.sol)는 같은 검증자에 여러 controller를 배정할 수 있고 owner가 배정 및 철회와 한도를 바꾼다고 설명한다. owner는 해당 관리 계약의 소유 권한을 가진 주소다. 한도를 낮춰도 현재 검증자의 투표권이 자동으로 그 이하로 줄어드는 것은 아니다. 이후 변경 호출에서 한도를 검사한다.

한국어:

```text
[관리 계약 owner]
       |
       +-- 역할 부여/철회 --> [등록자] -- 등록 --> [투표권 0의 등록 정보]
       |
       +-- 담당/한도 배정 --> [controller] -- 활성화/투표권 변경 --> [Registry]
       |
       +-- pauser 변경 --> [pauser] -- 변경 함수의 정지/해제 --> [관리 계약]
```

English:

```text
[Management contract owner]
       |
       +-- grant/revoke --> [Registerer] -- register --> [Registration with zero power]
       |
       +-- assign/cap --> [Controller] -- activate/update power --> [Registry]
       |
       +-- replace pauser --> [Pauser] -- pause/unpause updates --> [Manager]
```

이 그림은 읽은 코드의 접근 검사를 재구성한 것으로 실제 기관 및 서명 구조의 지도가 아니다. Active 상태의 검증자도 투표권 0일 수 있다. Registry는 마지막 양수 투표권을 가진 활성 검증자를 제거하거나 0으로 만드는 경우를 제한하지만, 이 검사만으로 충분한 독립 기관과 지리 분산 또는 안전한 정족수가 보장되지는 않는다.

등록, 활성화와 투표권을 나누어 읽어야 하는 이유는 정보의 존재, 집합 소속과 합의의 가중치가 다른 속성이기 때문이다. 등록된 주소의 목록만 세면 실제 결정에 영향을 주는 집합을 잘못 설명할 수 있다. 반대로 양수 투표권을 확인했더라도 그 주소의 노드가 실제로 제안과 투표에 참여하는지는 별도 관측이다. 아래 표는 이 속성들과 운영 관측을 함께 확인하도록 내가 구성한 것이며, 반드시 그 순서대로 상태가 바뀐다는 절차는 아니다.

**검증자의 등록, 활성 상태와 투표권 해석**

| 확인 항목      | 확인하는 질문                    | 그 항목만으로 알 수 없는 것    |
| -------------- | -------------------------------- | ------------------------------ |
| 등록 정보      | 검증자 정보가 등록되어 있는가?   | 활성 상태와 실제 투표권        |
| 활성 상태      | 활성 집합에 속하는가?            | 양수 투표권의 보유             |
| 투표권         | 합의에서 얼마의 가중치를 갖는가? | 실제 온라인 상태와 메시지 전달 |
| 실제 참여 관측 | 제안과 투표에 참여하고 있는가?   | 전체 집합의 독립성과 안전성    |

한국어:

```text
[등록 확인] -------+
[활성 상태 확인] --+-- 함께 읽는다 --> [해당 검증자의 운영 상태 해석]
[투표권 확인] -----+
[실제 참여 관측] --+
```

English:

```text
[Registration check] ------+
[Active status check] -----+-- read together --> [Interpret the validator's operational state]
[Voting power check] ------+
[Observed participation] --+
```

네 항목은 병렬로 확인할 항목이며, 그림은 하나의 필수 진행 순서를 나타내지 않는다.

### 5.2 설정 관리: 수수료와 합의 매개변수 및 변경 함수의 정지를 관리한다

[ProtocolConfig](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/contracts/src/protocol-config/ProtocolConfig.sol)는 수수료와 블록 가스 한도 및 합의 타임아웃 등을 관리한다. [설정 controller](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/contracts/src/protocol-config/roles/Controller.sol)가 변경 함수를 호출하고 owner가 controller를 바꿀 수 있다. 함수는 alpha와 kRate의 상한, 기본 수수료 범위 및 0이 아닌 가스 한도와 타임아웃 등의 조건을 검사한다. 모든 운영 목표를 강제하는 검사가 있는 것은 아니다.

[Pausable](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/contracts/src/common/roles/Pausable.sol)의 pauser는 해당 계약의 paused 값을 바꾸고 owner는 pauser를 교체한다. 관리 계약과 설정 계약의 `whenNotPaused`는 그 변경 함수를 제한한다. 이를 체인 전체의 거래와 합의가 모두 멈추는 버튼이라고 설명하면 대상이 달라진다. 규칙의 변경을 막는 정지와 자산의 이전 또는 블록 생산을 막는 정책을 구별해야 한다.

| 권한이나 규칙                      | 바꾸는 대상                      | 아직 확인할 운영 조건                             |
| ---------------------------------- | -------------------------------- | ------------------------------------------------- |
| 등록자와 담당 controller           | 검증자 정보, 활성 상태와 투표권  | 현재 역할 주소와 한도 및 변경의 적용 시점         |
| 설정 controller                    | 수수료, 가스 및 합의 매개변수    | 현재 값과 클라이언트 검사 및 배포 버전            |
| 관리 계약의 pauser                 | 정지 조건이 붙은 변경 함수       | 실제 paused 상태와 역할 키 및 복구 절차           |
| 프록시 관리자                      | 호출이 전달되는 구현             | 실제 구현 주소, 업그레이드 키와 감사 및 적용 기록 |
| USDC의 상위 발행 및 차단 역할      | 자산 정책과 지정 프리컴파일 호출 | 현재 상위 계약의 권한과 실제 행위 및 소구         |
| 별도 Denylist의 owner와 denylister | 거부 역할과 주소 목록            | 현재 목록, 예외와 검사 위치 및 운영 버전          |

한 행은 관리 대상 하나다. 초기 설정 파일에 proxy admin과 owner 및 controller가 들어 있어도 그 주소를 특정 사람이나 기관으로 해석할 수는 없다. 합의가 유효한 블록을 확정한다는 보장과 앞으로 어떤 규칙 및 집합을 적용하도록 바꿀 수 있는가는 함께 검토해야 한다.

설정 변경의 권한과 변경 결과도 구분해야 한다. 허용된 controller가 함수를 호출할 수 있다는 것은 호출 자격이고, 값의 범위 검사에 통과하는 것은 해당 함수의 조건을 충족한다는 뜻이다. 그 설정이 모든 노드에 언제 적용되고 어떤 운영 성능을 만드는지는 배포와 클라이언트 및 실제 관측의 질문이다. 특히 정지 권한을 평가할 때는 이름보다 정지 조건이 붙은 함수를 먼저 확인해야 한다. 변경을 잠시 막는 권한과 이미 정한 규칙대로 거래를 처리하는 과정은 같은 대상이 아니다.

**관리 계약의 호출은 바로 적용된다.** 수수료 매개변수는 controller 역할의 주소가 함수 하나를 호출해서 바꾼다. [ProtocolConfig 코드](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/contracts/src/protocol-config/ProtocolConfig.sol)의 `updateFeeParams`는 "Only callable by controller when not paused"라는 조건만 확인하고 값을 바로 바꾼다. 계약의 구현 교체도 프록시의 admin 주소가 `upgradeTo`를 직접 호출하는 형태다([프록시 코드](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/contracts/src/proxy/AdminUpgradeableProxy.sol) ). 공개 저장소의 [파일 목록](https://github.com/circlefin/arc-node/tree/6e764023ee6515fe70573e123ed2db912a7207b4) 1,020개에서 이름에 timelock, governor, multisig가 들어간 파일을 찾았으나 없었다(`rg -c -i 'timelock|governor|multisig'`, 결과 0건). 2026-10-07에 메인넷 공개 RPC로 조회한 결과, 세 프록시의 admin 주소와 ProtocolConfig의 owner, controller, pauser 주소에는 모두 계약 코드가 없었다. 따라서 이 주소들 앞에 온체인의 지연 계약은 없다. 다만 각 주소의 키를 체인 밖에서 여러 사람이 나누어 관리하는지는 이 조회로 알 수 없다.

### 5.3 접근 제한: 주소와 자산 이전에 적용되는 차단 권한을 구별한다

[네이티브 권한 코드](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/crates/precompiles/src/native_coin_authority.rs)는 발행과 소각 및 이전의 지정 프리컴파일(precompile)을 제공한다. 프리컴파일은 지정 주소에서 노드가 수행하는 실행 기능이다. 이 본문의 변경 호출은 지정 USDC 계약에서 온 경우만 허용하며 영주소와 차단 및 잔액 등의 조건을 검사한다. 사용자 누구나 이 주소를 호출해 USDC를 발행할 수 있다는 뜻이 아니다. 상위 USDC 계약의 전체 역할과 현재 키 보유자는 이번 선택 열람으로 확인하지 않았다.

[Denylist 계약](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/contracts/src/Denylist.sol)에는 denylister가 주소를 추가 및 해제하고 owner가 그 역할을 부여 및 철회하는 절차가 있다. USDC blocklist와 별도 계약 및 역할이다. 변경 기록의 v0.8.0은 클라이언트의 denylist 검사가 필수가 되었다고 적지만 예외 설정과 현재 버전의 실제 적용은 별도 관측이 필요하다.

체인 합의, 주소 접수와 실행 정책, 자산 이전 정책은 같은 검열 질문 안에서도 대상과 시점이 다르다. 차단 기능이 있다고 모든 거래가 항상 접수 전에 거절되는 것은 아니며, 정상 합의가 있다고 차단된 자산의 이전이 성공하는 것도 아니다. 이 차이는 3.4(실패 처리)의 실패 경로와 7.1(잔액 표현)부터 7.3(이전 로그)까지의 기록 설명에서도 유지한다.

제한을 조사할 때는 누가 요청했는지와 어느 주소가 검사 대상인지도 나누어 보아야 한다. 거래 발신자의 접수 조건과 계약 내부에서 수행하는 자산 이전의 발신자 및 수취인 조건은 같은 검사가 아닐 수 있다. 또한 블록 후보에 포함하지 않는 선택과 포함된 호출이 실행 규칙에 따라 되돌아가는 결과는 서로 다르다. 따라서 접근 제한을 단일한 차단 여부로 요약하기보다 관리 역할, 검사 위치와 남는 기록을 연결해야 한다. 이 연결은 앞의 실패 처리에서 구분한 영수증과 비용의 차이를 설명하는 데 필요하다.

### 5.4 노드 소프트웨어: 하드포크는 릴리스에 적힌 시각에 활성화되며, 그 공지가 사용자의 대응 시간을 정한다

5.1(검증자 관리)부터 5.3(접근 제한)까지는 관리 계약의 역할이 무엇을 바꿀 수 있는지를 설명했다. 이 절은 관리 계약 밖의 변경 경로인 노드 소프트웨어를 본다. 노드 소프트웨어의 변경은 새 버전과 하드포크로 들어오며, 그 활성화 시각을 얼마나 미리 알리는지가 사용자가 원하지 않는 변경에 대응할 수 있는 시간을 정한다. 대응 시간이라는 질문은 L2BEAT의 탈출 기간(Exit Window)에서 빌려 왔다. [L2BEAT의 정의](https://forum.l2beat.com/t/the-risk-rosette-framework/292)는 "The amount of time users have to exit the system in case of unwanted upgrades."이다. L2BEAT은 이 시간이 30일 이상이면 녹색, 7일 이상 30일 미만이면 노란색, 7일 미만이면 빨간색으로 표시한다. Arc는 rollup이 아니므로 "탈출"은 자산을 다른 체인이나 은행으로 옮기거나 사용을 멈추는 것으로 바꾸어 읽었다. 바꾼 해석은 나의 것이다.

**노드 소프트웨어의 하드포크.** 하드포크는 블록 높이가 아니라 정해진 시각에 활성화된다([하드포크 코드](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/crates/execution-config/src/hardforks.rs) ). 새 버전을 낼 때 변경 기록에 그 시각과 필요한 버전을 함께 적는다. 예를 들어 [변경 기록](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/CHANGELOG.md)의 v0.8.0 항목은 "mainnet node operators must use a version supporting Zero7/Zero8 before timestamp `1789052400` (2026-09-10 15:00:00 UTC)"라고 적는다. 릴리스가 공개된 시각([GitHub 릴리스 목록](https://api.github.com/repos/circlefin/arc-node/releases?per_page=30))과 활성화 시각 사이의 간격은 다음과 같다.

| 릴리스 | 릴리스 공개(UTC) | 활성화 대상과 시각(UTC)                | 간격             |
| ------ | ---------------- | -------------------------------------- | ---------------- |
| v0.7.2 | 2026-06-04 15:07 | 테스트넷 Zero7, 2026-06-18 14:00       | 13일 22시간 53분 |
| v0.8.0 | 2026-08-28 11:19 | 테스트넷 Zero8, 2026-09-03 15:00       | 6일 3시간 41분   |
| v0.8.0 | 2026-08-28 11:19 | 메인넷 Zero7과 Zero8, 2026-09-10 15:00 | 13일 3시간 41분  |

한 행은 공지 하나다. 활성화 시각은 변경 기록과 [호환성 변경 기록](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/BREAKING_CHANGES.md)의 유닉스 시각을 `date -u -r`로 바꾸어 확인했다. 간격은 두 시각의 차이를 Python의 datetime으로 계산했다. 이 공지는 노드 운영자에게 업그레이드 기한을 알리는 것이며, 사용자에게 대응 시간을 보장하려고 정한 기간은 아니다. 또한 메인넷의 Zero7과 Zero8 활성화는 공개 메인넷 시작일(2026-09-16)보다 앞서, Arc가 "currently in private mainnet"이라고 적은 기간에 있었다([메인넷 공지](https://www.arc.io/blog/arc-mainnet-goes-live-on-september-16-2026) ). 공지 시각과 버전이 맞지 않으면 노드가 통신망에서 갈라질 수도 있다. 호환성 변경 기록은 v0.7.0 이전의 합의 계층이 메인넷에서 v0.7.0과 연결되지 않는다고 적는다.

아래 판단은 위 사실에서 내가 끌어낸 것이다. 노드 소프트웨어의 변경은 이번 사례에서 활성화 6일에서 14일 전에 공지되었다(위 표의 간격 6일 3시간 41분에서 13일 22시간 53분). 반면 5.2(설정 관리)에서 본 계약 매개변수와 구현 교체는 지연 없이 바로 적용될 수 있는 구조다. 변경이 적용되면 계약은 FeeParamsUpdated 같은 이벤트를 남기므로(ProtocolConfig 코드 , ) 사후에는 알 수 있다. 그러나 사전에 알 수 있는 시간은 코드로 보장되지 않는다. L2BEAT의 기준을 그대로 대면, 계약 변경에 대한 대응 시간은 7일 미만, 즉 빨간색 구간이다. 다만 이 기준은 사용자가 다른 체인으로 자산을 빼낼 수 있는 rollup을 전제로 만든 것이다. 허가형 L1에 이 기준을 그대로 대는 것이 맞는지는 판단을 보류한다. 공지 기간에 관한 Circle의 약속이나 운영 정책 문서는 찾지 못했다.

## 6. 다른 네트워크와의 비교: Bitcoin, Ethereum, Solana, Base와 Arc는 거래 처리, 합의와 운영 권한에서 어떻게 다른가

3절(거래 처리)부터 5절(운영 권한)까지는 Arc 하나를 설명했다. 이 절은 같은 세 질문, 즉 거래를 어떻게 처리하는가, 기록을 어떻게 확정하는가, 참여자와 규칙을 누가 바꾸는가를 Bitcoin, Ethereum, Solana, Base와 Arc의 다섯 네트워크에 나란히 던진다. 각 표의 근거와 기준일은 표 아래의 설명에 적었다.

### 6.1 거래 처리 비교: 다섯 네트워크의 제출, 실행과 실패 기록을 단계별로 대조한다

3.1(거래 접수)부터 3.4(실패 처리)까지 본 Arc의 거래 처리 단계를 Bitcoin, Ethereum, Solana와 Base에 대어 보면 Arc가 어디서 Ethereum을 따르고 어디서 달라지는지가 드러난다. Solana는 EVM을 쓰지 않는 L1이고, Base는 Ethereum 위에서 동작하는 L2(rollup)다. 이 표의 행은 L1을 기준으로 정한 질문이므로, Base 열의 블록 생산과 확정은 시퀀서와 Ethereum에서의 도출로 답했다. 이렇게 대응시킨 것은 나의 해석이다. EVM은 비교 대상에서 별도 열로 두지 않았다. EVM은 네트워크가 아니라 거래를 실행하는 규칙이어서 접수, 합의나 확정 단계가 없고, 아래 표에서는 Ethereum과 Arc의 "실행과 검사" 행에 들어간다. 비교의 행은 이 절의 단계에 맞춰 내가 정했다.

| 단계                   | Bitcoin                                                                                                    | Ethereum                                                                                                                                                   | Arc                                                                                                | Solana                                                                                                                                    | Base(L2)                                                                                                                                                                      |
| ---------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 거래가 바꾸는 것       | 이전 거래의 출력(UTXO)을 입력으로 소비하고 새 출력을 만든다.                                               | 계정의 잔액, nonce와 계약 저장값을 바꾸는 메시지 호출 또는 계약 생성이다.                                                                                  | Ethereum과 같은 계정 모델이며, 값과 가스는 네이티브 USDC다.                                        | 계정의 잔액과 데이터를 바꾼다. 거래는 읽고 쓸 계정을 미리 적고, 담긴 명령(instruction)을 모두 실행하거나 모두 되돌린다. 수수료는 SOL이다. | Ethereum과 같은 계정 모델과 거래 형식이며, 수수료는 ETH다.                                                                                                                    |
| 제출과 대기            | 새 거래를 모든 노드에 전파하고, 각 노드는 확인되지 않은 거래를 mempool에 둔다.                             | JSON-RPC로 실행 클라이언트에 제출하고, 서명과 잔액을 검사한 뒤 로컬 멤풀에 둔다.                                                                           | JSON-RPC로 제출하고, 접수 검사를 통과하면 로컬 거래 풀에 둔다.                                     | RPC 노드에 보내면 RPC 노드가 현재 블록 생산자(리더)에게 전달한다. 검증자는 곧 리더가 될 노드로 거래를 넘긴다.                             | eth_sendRawTransaction으로 노드의 JSON-RPC에 제출하고, 시퀀서(sequencer)가 자기 멤풀에서 가져간다. Ethereum의 계약으로 제출하는 경로도 있다.                                  |
| 블록을 만드는 주체     | 거래를 모아 블록을 만들고 작업증명(proof of work)을 찾는 노드(채굴자)다. 먼저 찾은 노드가 블록을 전파한다. | 슬롯(12초)마다 무작위로 선택된 제안자다. 실행 클라이언트가 멤풀의 거래를 실행 페이로드로 묶는다.                                                           | 라운드마다 정해진 제안자다. 실행 계층에 후보 payload의 구성을 요청한다.                            | 지분으로 가중해 미리 정한 리더 일정에 따라 슬롯마다 리더 하나가 블록을 만든다. 슬롯은 약 400ms다.                                         | Base가 운영하는 활성 시퀀서 하나가 L2 블록을 만들고, 그 사이에 200ms마다 사전 확인 블록(preconfirmation block, Flashblock)을 낸다.                                            |
| 실행과 검사            | 블록의 모든 거래가 유효하고 이미 쓰이지 않았는지 검사한다. EVM은 없다.                                     | 다른 노드가 실행 클라이언트(EVM)로 거래를 다시 실행해 상태 변경이 유효한지 확인한다.                                                                       | 받은 후보를 실행 계층(Reth의 EVM)으로 실행해 VALID 또는 INVALID로 판정한 뒤 투표한다.              | 수신, 서명 검사, 수수료 납부자 검사, 계정 적재, 명령 실행과 기록의 8단계로 처리한다. EVM이 아니라 Solana의 자체 실행 환경이다.            | 검증자 노드가 시퀀서와 별도로 상태 전이를 실행한다. 실행 엔진은 Reth 기반이다.                                                                                                |
| 블록을 받아들이는 방식 | 받아들인 블록 위에 다음 블록을 쌓아 수용을 표시하고, 작업량이 가장 많이 쌓인 체인을 따른다.                | 검증자의 증명(attestation)과 LMD-GHOST 포크 선택(fork choice)으로 체인의 머리를 정하고, 체크포인트 사이에 3분의 2 이상의 투표가 모이면 완결(finalize)한다. | prevote와 precommit에서 전체 투표권의 3분의 2를 넘는 precommit을 모으면 그 높이의 블록을 확정한다. | 분기가 생기면 지분 가중 투표로 하나를 고른다. 지분 66% 이상이 투표하면 confirmed, 그 위에 확인된 블록이 31개 이상 쌓이면 finalized다.     | 시퀀서가 정한 순서가 L2 블록이 되고, 시퀀서가 그 데이터를 Ethereum에 올린다. 노드는 Ethereum에 올라간 데이터에서 정본 체인을 도출한다.                                        |
| 실패한 거래의 기록     | 유효하지 않은 거래가 든 블록은 받아들이지 않는다.                                                          | 실행이 실패해도 블록에 들어갈 수 있으며, 영수증에 상태 코드 0과 사용한 가스가 남는다.                                                                      | Ethereum과 같다. status 0과 사용 가스가 남는다.                                                    | 실행이 실패해도 수수료는 부과되고, 수수료 납부자의 차감만 남기고 나머지 변경은 버린다.                                                    | Ethereum과 같다고 판단한다. 다만 이를 직접 적은 문장은 받은 Base 문서에서 찾지 못했다.                                                                                        |
| 되돌림의 가능성        | 확률로 줄어든다. 뒤에 쌓인 블록이 많을수록 공격자가 따라잡을 확률이 낮다.                                  | 완결 전에는 재구성될 수 있다. 완결까지 평균 약 2.5 에포크(약 15분)가 걸린다.                                                                               | 정족수(quorum)와 잠금(lock) 규칙의 가정 아래, 확정된 높이의 블록을 다른 블록으로 바꾸지 않는다.    | finalized 이전에는 되돌려질 수 있다. 문서는 블록의 약 5%가 finalized에 이르지 못한다고 적는다.                                            | 네 단계로 줄어든다. 약 200ms 뒤 Flashblock, 약 2초 뒤 L2 블록, 약 2분 뒤 Ethereum 게시, 약 20분 뒤 Ethereum 완결이며, 마지막 단계부터는 Ethereum의 완결 블록과 같이 보호된다. |

한 행은 거래 처리의 한 단계이고, 각 칸은 그 네트워크의 자료가 설명하는 방식이다. Bitcoin 열은 [Bitcoin 백서](https://bitcoin.org/bitcoin.pdf)의 5절(Network), 9절(Combining and Splitting Value), 11절(Calculations)과, mempool은 [How Crypto Works 교재의 Bitcoin 장](https://github.com/lawmaster10/howcryptoworksbook/blob/587537b70cc9b065905ad771e06c75c32344d163/Chapters/ch01_bitcoin.md)을 따랐다. Ethereum 열은 [ethereum.org의 지분 증명 문서](https://ethereum.org/ko/developers/docs/consensus-mechanisms/pos/), [황서](https://ethereum.github.io/yellowpaper/paper.pdf)의 4.4.1(Transaction Receipt)과 [Circle의 Ethereum 확인 규칙 글](https://www.circle.com/blog/exploring-confirmation-rules-for-ethereum)을 따랐다. Solana 열은 Solana 공식 문서의 [Transactions](https://solana.com/docs/core/transactions.md), [Fees](https://solana.com/docs/core/fees.md), [거래 확인 문서](https://solana.com/docs/advanced/confirmation.md), [Transaction Pipeline](https://solana.com/docs/core/transactions/transaction-pipeline.md)과 Anza(Solana의 주요 검증자 클라이언트 Agave의 개발사) 문서의 [리더 교대](https://docs.anza.xyz/consensus/leader-rotation), [TPU](https://docs.anza.xyz/validator/tpu), [지분 위임](https://docs.anza.xyz/consensus/stake-delegation-and-rewards), [확인 수준](https://docs.anza.xyz/consensus/commitments)을 따랐다. Base 열은 Base 공식 문서의 [프로토콜 개요](https://docs.base.org/specifications/base-protocol/overview.md)와 [최종성 문서](https://docs.base.org/specifications/transactions/transaction-finality.md)를 따랐다. Base의 실패한 거래 기록은 거래 제출이 Ethereum과 같다는 설명과 실행 엔진이 표준 Ethereum JSON-RPC를 낸다는 설명에서 내가 추론했다. Arc 열은 Circle이 낸 Arc 공식 문서와 공개 저장소의 고정 커밋 코드를 따랐다. 계정 모델과 USDC 가스는 [EVM 차이 문서](https://docs.arc.io/arc/references/evm-differences.md)를, 제출과 대기 및 실패한 거래의 기록은 [거래 생애 문서](https://docs.arc.io/integrate/wallets/transaction-lifecycle.md)를, 블록을 만드는 주체와 받아들이는 방식 및 되돌림은 [합의 문서](https://docs.arc.io/arc/concepts/consensus-layer.md)를, 후보의 실행 검사는 [고정 Payload 코드](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/crates/malachite-app/src/payload.rs)를 각각 근거로 삼았다. 이 원고의 3.1(거래 접수)부터 3.4(실패 처리)까지가 같은 자료를 더 자세히 설명한다. 다섯 열 모두 그 네트워크를 만든 쪽의 1차 자료이며, 독립된 제삼자가 동작을 확인한 기록은 아니다. Solana 열은 2026-10-07 기준 메인넷의 합의인 Tower BFT를 따랐다(6.2(합의 비교) 참고).

표에서 Arc는 거래의 형태, 제출 방식, 실행과 실패 기록에서 Ethereum을 따른다. 계정 모델, JSON-RPC, EVM 실행과 status 0 영수증이 모두 같은 규칙이기 때문이다. 달라지는 곳은 블록을 받아들이는 방식과 되돌림의 가능성이다. Ethereum은 포크 선택으로 체인의 머리를 먼저 정하고 체크포인트 투표로 나중에 완결하므로, 블록이 체인에 붙은 때와 완결된 때 사이에 시간 차이가 있다. Arc는 투표를 마친 블록만 정본으로 붙이므로 그 시간 차이가 없다. Bitcoin은 완결이라는 단계가 따로 없으며, 시간이 지날수록 되돌릴 확률이 줄어드는 방식이다.

Solana와 Base는 Arc와 다른 방향에서 빠르다. Solana는 리더 일정을 미리 정해 두고 RPC 노드가 거래를 곧 블록을 만들 리더에게 바로 보내며, 확정은 지분 투표가 쌓이는 정도에 따라 confirmed와 finalized로 나뉜다. Base는 시퀀서 하나가 순서를 정하므로 200ms 만에 사전 확인을 받지만, 그 사전 확인은 시퀀서의 약속이다. 되돌릴 수 없는 기록이 되려면 Ethereum에 게시되고 Ethereum에서 완결되어야 하므로 약 20분이 걸린다. Arc는 투표를 마친 블록을 한 번에 확정하므로 이런 중간 단계가 없다.

실패한 거래의 기록도 앱의 처리를 바꾼다. Bitcoin에서는 유효하지 않은 거래가 블록에 들어가지 않으므로 "포함됐지만 실패한 거래"라는 상태가 없다. Ethereum, Base와 Arc에서는 그런 상태가 있으므로, 3.4(실패 처리)에서 설명한 대로 포함 여부와 실행 성공을 따로 확인해야 한다. Solana에서도 실패한 거래가 수수료만 내고 기록되므로 같은 확인이 필요하다.

### 6.2 합의 비교: 다섯 네트워크가 기록을 확정하는 방식과 확정의 의미를 대조한다

4.1(합의의 발전)에서 본 두 흐름, 즉 누구나 참여해 확률로 굳어지는 방식과 정해진 투표권으로 확정하는 방식은 지금의 네트워크들에 각각 남아 있다. 아래 표는 4.3.1(안전성)부터 4.3.3(거래 포함)까지의 질문을 다섯 네트워크에 같은 순서로 던진 것이다. EVM은 합의 규칙이 없으므로 이 비교에서 뺐다. Base는 자체 합의 투표가 없는 L2이므로, Base 열은 시퀀서와 Ethereum이 각 질문에 어떻게 답하는지로 채웠으며, 이렇게 대응시킨 것은 나의 해석이다. 행은 내가 정했으며, 질문의 출발점은 안전성, 진행성 및 거래 포함의 보장 범위를 구별하는 것이다.

| 질문               | Bitcoin                                                                      | Ethereum                                                                                                                                                                      | Arc                                                                                        | Solana                                                                                                                                  | Base(L2)                                                                                                                                                                                     |
| ------------------ | ---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 참여 자격과 영향력 | 누구나 작업증명으로 참여하고, 연산 능력이 곧 영향력이다("one-CPU-one-vote"). | 32 ETH를 예치한 검증자가 참여하고, 예치한 ETH가 투표의 무게다.                                                                                                                | 관리 계약이 등록하고 활성화한 허가된 검증자가 참여하고, 설정된 투표권이 무게다.            | 지분을 위임받은 검증자가 참여하고, 위임된 지분이 투표의 무게이자 리더 일정의 가중치다.                                                  | 블록을 만드는 쪽은 Base가 운영하는 시퀀서 하나이며 투표가 없다. 검증자 노드는 상태를 따로 실행하고, 제안자(proposer)나 도전자(challenger)로서 Ethereum에 상태 주장을 내거나 이의를 제기한다. |
| 분기가 생기면      | 작업이 가장 많이 쌓인 체인을 따르며, 나중에 더 긴 체인이 나타나면 옮겨 간다. | 증명이 가장 많이 쌓인 가지를 LMD-GHOST로 고르며, 완결 전의 선택은 바뀔 수 있다.                                                                                               | 한 높이에서 3분의 2를 넘는 precommit을 받은 블록만 확정하므로 확정된 높이에는 분기가 없다. | 리더가 바뀌는 슬롯 경계에서 분기가 생길 수 있고, 지분 가중 투표로 하나만 확정하며 나머지 블록은 버린다.                                 | L2 블록의 순서는 시퀀서 하나가 정한다. Ethereum이 재구성되어도 Base는 보통 재구성되지 않고, 배치 데이터를 다시 올린다.                                                                       |
| 확정의 의미        | 정해진 확정 단계가 없다. 뒤에 쌓인 블록 수만큼 되돌릴 확률이 줄어든다.       | 두 체크포인트 사이에 예치 ETH 3분의 2 이상의 투표가 모이면 완결된다. 평균 약 15분이다.                                                                                        | 투표가 끝난 블록이 곧 확정이다. 4.3.1(안전성)의 가정 아래 다른 블록으로 바뀌지 않는다.     | confirmed(지분 66% 이상의 투표)와 finalized(그 위에 31개 이상의 블록)의 두 단계다. Alpenglow 제안은 지금의 확정 시간을 12.8초로 적는다. | 한 번에 정해지지 않고 네 단계로 굳어진다. 마지막 단계는 그 데이터를 담은 Ethereum 블록의 완결이다.                                                                                           |
| 안전성의 전제      | 정직한 참여자의 연산 능력이 공격자보다 크다.                                 | 악의적인 예치가 전체의 3분의 1 미만이다. 완결을 되돌리려면 예치 ETH의 3분의 1 이상을 잃는다.                                                                                  | 결함 투표권이 전체의 3분의 1 미만이고, 정상 검증자가 잠금 규칙을 지킨다.                   | 받은 문서에서 정족수의 경계 조건은 찾지 못했다. Alpenglow 제안은 지금의 Tower BFT에 보안 증명이 없다고 적는다.                          | 시퀀서를 신뢰하지 않아도 되도록 설계했다. 데이터는 Ethereum에 있고, 검증자가 따로 실행하며, 잘못된 상태 주장에는 증명으로 이의를 제기한다. 마지막 근거는 Ethereum의 안전성이다.              |
| 진행이 멈추는 조건 | 블록 생성은 작업증명을 찾는 한 계속된다.                                     | 예치의 3분의 1이 다수와 다르게 투표하면 완결을 막을 수 있다. 4 에포크 이상 완결되지 못하면 비활동 누수(inactivity leak)가 그 검증자의 예치를 줄여 3분의 2 다수를 되찾게 한다. | 3분의 2를 넘는 투표권이 참여하지 않으면 새 블록의 확정이 멈춘다.                           | 66% 이상의 지분이 투표하지 않으면 confirmed와 finalized에 이르지 못한다고 읽힌다. 이는 확인 수준 표에서 내가 추론한 것이다.             | 시퀀서가 멈추면 L2 블록 생산이 멈춘다. 2026년 6월 25일과 26일에 시퀀서의 버그로 블록 생산이 116분과 20분 동안 멈췄다.                                                                        |

한 행은 합의에 던지는 질문 하나다. Bitcoin 열은 [Bitcoin 백서](https://bitcoin.org/bitcoin.pdf)의 4절(Proof-of-Work), 5절(Network)과 11절(Calculations)을 따랐다. Ethereum 열은 [ethereum.org의 지분 증명 문서](https://ethereum.org/ko/developers/docs/consensus-mechanisms/pos/)와 [Circle의 Ethereum 확인 규칙 글](https://www.circle.com/blog/exploring-confirmation-rules-for-ethereum)을 따랐다. Arc 열은 [합의 문서](https://docs.arc.io/arc/concepts/consensus-layer.md)의 참여 자격, 충돌하는 확정이 불가능하다는 설명, 확정의 의미와 안전성 및 진행성의 조건, 그리고 [Tendermint 사양](https://github.com/circlefin/malachite/blob/72143f6c99a98452b587e1c392bdb80944eb2232/specs/consensus/overview.md)의 결함 투표권 조건과 잠금 규칙을 따랐다. Solana 열은 Anza 문서의 [지분 위임](https://docs.anza.xyz/consensus/stake-delegation-and-rewards), [리더 교대](https://docs.anza.xyz/consensus/leader-rotation), [분기 생성](https://docs.anza.xyz/consensus/fork-generation), [확인 수준](https://docs.anza.xyz/consensus/commitments)과 [Alpenglow 제안(SIMD-0326)](https://github.com/solana-foundation/solana-improvement-documents/blob/main/proposals/0326-alpenglow.md)을 따랐다. Base 열은 [프로토콜 개요](https://docs.base.org/specifications/base-protocol/overview.md)와 [최종성 문서](https://docs.base.org/specifications/transactions/transaction-finality.md), 그리고 [2026년 6월 장애 보고](https://blog.base.dev/postmortem-june-25th-block-production-outage)를 따랐다. Solana의 진행 조건은 확인 수준 표에서 내가 추론한 것이다. 4.3.1(안전성)부터 4.3.3(거래 포함)까지가 같은 자료를 더 자세히 설명한다.

**Solana의 합의는 바뀌는 중이다.** Alpenglow 제안(SIMD-0326)은 PoH와 Tower BFT를 새 합의로 바꾸는 제안이며, 받은 날 상태는 Review다. Solana 개선 제안의 절차 문서(SIMD-0001)는 메인넷 베타에서 켜진 제안만 Activated로 부른다. Anza의 확인 수준 문서는 이미 Alpenglow에서는 confirmed와 finalized가 같은 뜻이 되고 조건이 지분 60% 이상의 finalize 투표 또는 80% 이상의 notarize 투표라고 적는다. 2026년 9월 말의 기사 두 건은 Alpenglow가 9월 하순에 테스트넷에 들어갔지만 메인넷 활성화는 확정되지 않았다고 전한다([Bitzo](https://bitzo.com/2026/09/solana-alpenglow-public-testnet-150ms-finality), [cryptoticker](https://cryptoticker.io/en/solana-alpenglow-mainnet-date-missed/)). 그래서 표의 Solana 열은 지금 메인넷의 Tower BFT를 적었다. 활성화되면 Solana의 확정은 Arc처럼 투표 한 단계로 바뀐다.

표의 핵심은 확정의 의미가 다섯 네트워크에서 모두 다르다는 점이다. Bitcoin의 확인은 확률이고, Ethereum은 체인의 머리를 먼저 고르고 나중에 완결하는 두 단계이며, Solana는 지분 투표가 쌓이는 정도로 confirmed와 finalized를 나누고, Base는 시퀀서의 사전 확인에서 Ethereum 완결까지 네 단계를 거치며, Arc는 투표가 끝나야 블록을 붙이는 한 단계다. 그래서 같은 "확인"이나 "확정"이라는 말도 네트워크마다 다른 대기를 뜻한다. 또 Base는 블록 생산을 시퀀서 하나에 맡기므로, Arc의 "3분의 1 이상이 멈추면 확정이 멈춘다"에 해당하는 조건이 Base에서는 "시퀀서가 멈추면 생산이 멈춘다"가 된다. Arc의 방식은 확정이 빠르고 단순한 대신, 3분의 1 이상의 투표권이 멈추면 새 블록 자체가 확정되지 않는다. 이 성질은 허가된 검증자 집합의 규모와 운영에 직접 의존하므로, 다음 5절(운영 권한)에서 그 집합을 누가 정하는지를 확인한다.

### 6.3 운영 권한 비교: 다섯 네트워크에서 참여자와 규칙을 바꾸는 주체를 대조한다

5절(운영 권한)에서 본 Arc의 권한 가운데 검증자 집합과 설정을 바꾸는 권한은 관리 계약의 역할로 행사되고, 노드 소프트웨어의 변경은 공개 저장소의 릴리스로 들어온다. Bitcoin, Ethereum, Solana와 Base에도 참여자와 규칙이 바뀌는 절차가 있지만, 그 절차를 누가 움직이는지가 다르다. EVM은 운영 절차를 갖지 않으므로 이 비교에서도 뺐다. 행은 이 절의 질문에 맞춰 내가 정했다.

| 질문                      | Bitcoin                                                                                                                                                  | Ethereum                                                                                                                           | Arc                                                                                                                                         | Solana                                                                                                                                                                                                     | Base(L2)                                                                                                                                                                                     |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 합의 참여자가 바뀌는 방식 | 등록 절차가 없다. 노드는 언제든 네트워크를 떠나고 다시 들어올 수 있다.                                                                                   | 예치 계약에 32 ETH를 넣고 활성화 대기열을 거친다. 진입과 퇴장은 에포크마다 정해진 한도 안에서 처리된다.                            | 등록자와 담당 controller 역할이 검증자를 등록하고 활성 상태와 투표권을 바꾼다.                                                              | 지분 보유자가 검증자에게 지분을 위임하고, 지분의 변화는 다음 에포크의 리더 일정부터 반영된다.                                                                                                              | 시퀀서는 Base 하나다. Base는 누구나 검증에 참여할 수 있다고 설명한다.                                                                                                                        |
| 잘못한 참여자에 대한 조치 | 노드는 유효하지 않은 거래가 든 블록을 받아들이지 않는다.                                                                                                 | 한 슬롯에 블록을 여럿 제안하거나 모순된 증명을 내면 슬래싱으로 예치 ETH의 일부에서 전부까지 잃는다. 참여하지 않으면 보상을 놓친다. | 관리 계약으로 검증자를 비활성화하거나 투표권을 바꿀 수 있다. 예치금을 깎는 방식은 이 원고에서 확인하지 않았다.                              | 문서는 잘못 투표한 검증자의 지분이 슬래싱(slashing)에 노출된다고 적지만, 잠금 위반의 처벌은 제안(proposed)으로 적혀 있다. 시행 여부는 확인하지 못했다.                                                     | 잘못된 상태 주장에는 도전자가 ZK 증명으로 이의를 제기하고, 무효가 된 주장으로 증명한 출금은 완료되지 않는다.                                                                                 |
| 프로토콜 규칙의 변경      | BIP로 제안하고 Bitcoin Core에 구현한다. 소프트포크는 채굴자 신호나 사용자 측의 시행일로 활성화하며, 어떤 소프트웨어를 실행할지는 사용자와 기업이 정한다. | EIP로 제안하고, 이전 버전과 호환되지 않는 하드포크를 정해진 블록 높이에서 적용한다. 2022년에는 합의 방식 자체를 바꾸었다.          | 수수료, 가스와 합의 매개변수는 설정 controller가 바꾸고, 프록시 관리자가 호출이 전달되는 구현을 바꾼다. 노드 소프트웨어의 버전 변경도 있다. | SIMD(Solana Improvement Document)로 제안하고 핵심 기여자의 합의로 수락한 뒤, 기능 활성화 프로그램(feature gate)으로 메인넷에서 켠다.                                                                       | Ethereum 위 계약의 업그레이드는 Coinbase의 3-of-6 다중 서명과 Security Council의 8-of-11 다중 서명이 모두 승인해야 한다. 노드 소프트웨어는 Base의 하드포크 릴리스로 바뀌며, 연 6회가 목표다. |
| 주소와 자산의 차단        | 비트코인 자체를 동결하는 장치가 없다.                                                                                                                    | 이 원고는 ETH의 프로토콜 차원 차단을 확인하지 않았다. 발행자가 있는 토큰은 토큰 계약의 규칙으로 차단할 수 있다.                    | USDC의 상위 차단 역할과 별도 Denylist가 있고, 실행 중 발신자와 수취인을 검사한다.                                                           | SOL을 감싼 토큰 계정(native token account)은 동결할 수 없고, SOL을 담은 일반 계정을 동결하는 장치는 받은 문서에서 찾지 못했다. 발행 계정에 동결 권한이 남은 토큰은 그 권한자가 토큰 계정을 동결할 수 있다. | 프로토콜 차원의 차단은 확인하지 않았고, 토큰은 Ethereum과 같이 토큰 계약의 규칙을 따른다. 시퀀서가 거래를 받지 않으면 Ethereum의 계약으로 제출하는 경로가 있다.                              |

한 행은 운영의 질문 하나다. Bitcoin 열은 [Bitcoin 백서](https://bitcoin.org/bitcoin.pdf)의 초록과 5절(Network), [How Crypto Works 교재의 Bitcoin 장](https://github.com/lawmaster10/howcryptoworksbook/blob/587537b70cc9b065905ad771e06c75c32344d163/Chapters/ch01_bitcoin.md)을 따랐다. Ethereum 열은 [ethereum.org의 지분 증명 문서](https://ethereum.org/ko/developers/docs/consensus-mechanisms/pos/), [Circle의 Ethereum 확인 규칙 글](https://www.circle.com/blog/exploring-confirmation-rules-for-ethereum), [ethereum.org 용어집](https://ethereum.org/en/glossary/)의 EIP와 Hard fork 항목, [Circle의 2019년 하드포크 공지](https://www.circle.com/blog/circle-to-support-two-ethereum-hard-forks-temporarily-increasing-minimum-block-confirmations-for-usdc)와 [Merge 공지](https://www.circle.com/blog/how-circle-is-preparing-for-the-ethereum-merge)를 따랐다. Arc 열은 [검증자 관리 계약](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/contracts/src/validator-manager/PermissionedValidatorManager.sol)의 등록, 활성화, 제거와 투표권 변경 함수, [ProtocolConfig 코드](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/contracts/src/protocol-config/ProtocolConfig.sol)의 변경 함수, [프록시 코드](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/contracts/src/proxy/AdminUpgradeableProxy.sol), [Denylist 계약](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/contracts/src/Denylist.sol)과 [EVM 차이 문서](https://docs.arc.io/arc/references/evm-differences.md)의 실행 중 차단 규칙을 따랐다. 예치를 깎는 장치는 이 자료들에서 찾지 못했다. Solana 열은 [리더 교대](https://docs.anza.xyz/consensus/leader-rotation), [Tower BFT](https://docs.anza.xyz/implemented-proposals/tower-bft), [지분 위임](https://docs.anza.xyz/consensus/stake-delegation-and-rewards), [SIMD-0001](https://github.com/solana-foundation/solana-improvement-documents/blob/main/proposals/0001-simd-process.md), [Freeze Account](https://solana.com/docs/tokens/basics/freeze-account.md)을 따랐다. Base 열은 [프로토콜 개요](https://docs.base.org/specifications/base-protocol/overview.md), [Security Council 문서](https://docs.base.org/specifications/security/security-council-for-base.md), [최종성 문서](https://docs.base.org/specifications/transactions/transaction-finality.md)와 [통합 스택 발표](https://blog.base.dev/next-chapter-for-base-chain-1)를 따랐다. 5.1(검증자 관리)부터 5.3(접근 제한)까지가 같은 자료를 더 자세히 설명한다.

다섯 네트워크의 차이는 규칙을 바꾸는 힘이 어디에 있는지에서 가장 크게 드러난다. Bitcoin 교재는 Bitcoin Core가 영향력을 갖는 이유를 "not because it controls Bitcoin, but because the economic majority has chosen to run it"이라고 설명한다. 규칙의 변경은 사용자가 새 소프트웨어를 실행하기로 할 때 성립한다. Ethereum은 EIP와 정해진 높이의 하드포크라는 조율된 절차가 있지만, 그 소프트웨어를 실행하는 쪽은 여전히 노드와 검증자다. Solana도 SIMD로 제안하고 핵심 기여자가 수락한 변경을 기능 활성화 프로그램으로 켜는 절차가 있다. Base는 둘로 나뉜다. Ethereum 위의 계약은 Coinbase와 Security Council의 다중 서명이 모두 승인해야 바뀌고, 노드 소프트웨어는 Base가 내는 하드포크 릴리스로 바뀐다. Arc에서는 검증자 집합과 설정을 바꾸는 권한이 관리 계약의 역할 주소에 있으므로, 변경은 그 역할을 가진 키의 호출로 일어난다.

이 차이는 결함이 아니라 설계의 선택이며, 무엇을 확인해야 하는지를 바꾼다. Bitcoin, Ethereum과 Solana를 평가할 때는 사용자와 검증자가 변경을 받아들이는 과정을 보아야 한다. Base를 평가할 때는 다중 서명의 구성과 시퀀서 운영자를 함께 보아야 한다. Arc를 평가할 때는 5절(운영 권한)의 그림처럼 각 역할 주소를 누가 보유하고, 어떤 키 관리와 절차로 호출하며, 그 변경을 누가 언제 알 수 있는지를 확인해야 한다. 그 확인은 아직 남아 있으며 9.2(운영 확인)에서 정리한다.

## 7. Arc의 EVM 차이: EVM 호환은 무엇이 같다는 뜻이며, USDC 기록과 계약 실행은 Ethereum과 어디가 다른가

Arc의 실행 계층은 EVM을 쓰고, Arc는 기존 EVM 앱을 위한 [호환성 안내](https://www.arc.io/blog/arc-compatibility-guide-for-existing-evm-apps)를 낸다. 이 절은 먼저 "EVM 호환"이 무엇이 같다는 뜻인지를 그 안내로 정리하고, 이어서 Arc가 Ethereum과 달라지는 지점을 모은다. 7.1(잔액 표현)부터 7.3(이전 로그)까지는 거래의 기록을 금액과 비용으로 읽는 방법을, 7.4(실행 환경)와 7.5(계약 동작)는 계약이 전제한 실행 규칙의 차이를 다룬다. EVM이 무엇을 정하는 규칙인지는 1.2(실행 계층)에서 설명했다.

먼저 호환의 범위부터 본다. "EVM 호환"은 한 가지만 같다는 말이 아니다. 아래 표는 Arc의 호환성 안내가 같다고 설명하는 항목을 내가 다섯 층으로 나눈 것이다. 층을 나눈 이유는 어느 층이 같은지에 따라 다시 확인할 범위가 달라지기 때문이다.

| 층                   | 같다는 뜻                                       | Arc 호환성 안내의 설명                                                                              | 같아도 따로 확인할 차이                                      |
| -------------------- | ----------------------------------------------- | --------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| 계약 언어와 실행     | Solidity로 쓴 계약을 컴파일해 EVM에서 실행한다. | "The contracts remain Solidity"                                                                     | 일부 명령어의 반환 값과 블록 정보, 7.4(실행 환경)            |
| 거래와 서명          | 거래 형식과 서명 방식, 주소 형식이 같다.        | EIP-1559 거래, secp256k1 서명과 Ethereum 형식의 주소를 유지한다.                                    | type-3(블롭) 거래를 받지 않는다, 7.4(실행 환경)              |
| 노드 인터페이스      | 같은 JSON-RPC 호출로 제출하고 조회한다.         | JSON-RPC를 계속 사용한다.                                                                           | 같은 호출이 돌려주는 잔액의 단위, 7.1(잔액 표현)             |
| 개발 도구            | 기존 도구로 배포하고 시험한다.                  | Foundry, Hardhat, viem과 ethers를 계속 쓸 수 있다.                                                  | 표준 로컬 EVM이 Arc의 차이를 재현하지 않는다, 7.4(실행 환경) |
| 자산과 이벤트의 의미 | 같지 않다.                                      | "The main compatibility review is the code that assumes Ethereum's native token or event behavior." | 7.1(잔액 표현)부터 7.3(이전 로그)까지와 7.5(계약 동작)       |

한 행은 호환의 한 층이다. 위 네 층은 같다고 안내하는 층이며, 마지막 층은 안내 스스로 검토의 중심이라고 지목한 층이다. 따라서 Arc에서 "EVM 호환"은 기존 계약과 도구를 그대로 가져와 시작할 수 있다는 뜻이고, 그 계약이 네이티브 자산과 이벤트를 Ethereum과 같은 의미로 읽어도 된다는 뜻은 아니다.

**같은 층과 바뀐 층: 호환의 층마다 걸린 차이**

한국어:

```text
 층(위가 앱에 가깝다)          그 층에 걸린 Arc의 차이(아래 차이 표의 번호)
 ---------------------------   ----------------------------------------------------
 [개발 도구]                   표준 로컬 EVM은 아래의 차이를 재현하지 않는다
 [노드 인터페이스]             1 같은 호출이 돌려주는 잔액의 단위
 [거래와 서명]                 6 블롭 거래(type-3)를 받지 않는다
 [계약 언어와 실행]            2, 5, 6, 7 블록 정보와 명령어가 돌려주는 값
                               3, 4, 8, 9, 11 네이티브 값을 보내는 규칙
 ==== 여기까지 같다고 안내한 층, 아래는 검토의 중심 ====================
 [자산과 이벤트의 의미]        1 USDC와 두 인터페이스, 10 차단 목록
                               12 Transfer 로그, 13, 14, 15 수수료
 [블록과 확정]                 16 같은 블록 시각, 17 즉시 확정
```

English:

```text
 Layer (top is closest to apps)  Arc differences on that layer (numbers from the difference table below)
 ---------------------------   ----------------------------------------------------
 [Developer tools]             a standard local EVM does not reproduce the differences below
 [Node interface]              1 the unit of the balance the same call returns
 [Transactions and signatures] 6 blob (type-3) transactions are not accepted
 [Contract language, execution] 2, 5, 6, 7 values returned by block fields and opcodes
                               3, 4, 8, 9, 11 rules for sending native value
 ==== above: layers described as the same; below: the focus of review ====
 [Meaning of assets, events]   1 USDC and its two interfaces, 10 blocklist
                               12 Transfer logs, 13, 14, 15 fees
 [Blocks and finality]         16 equal block timestamps, 17 immediate finality
```

그림은 위 표의 다섯 층을 위에서 아래로 쌓고, 아래 차이 표의 17개 항목을 그 차이가 걸리는 층 옆에 번호로 놓았다. 위 네 층은 Arc가 같다고 안내하는 층이지만, 그 층에도 번호가 붙어 있다. 같은 도구와 같은 호출을 쓰더라도 돌려받는 값이 다를 수 있다는 뜻이다. 두 줄 선 아래의 자산과 이벤트의 층에 번호가 가장 많이 몰려 있으며, 안내가 검토의 중심으로 지목한 층과 같다. 맨 아래 블록과 확정의 층은 호환성 안내의 다섯 층에 없는 층이어서 내가 더했다. 16번과 17번이 어느 층에도 들어가지 않았기 때문이다.

표는 층마다 대표 차이 하나만 적으므로, 아래 차이 표의 17개 항목이 층 사이에 어떻게 나뉘는지는 보여 주지 못한다. 어느 층이 같다는 안내를 받았을 때 그 층에서 무엇을 다시 확인해야 하는지 한눈에 보이려고 그렸다. 차이를 층에 배정한 것은 나의 판단이다. 6번은 거래 형식과 명령어 값에 모두 걸리므로 두 층에 놓았고, 1번은 노드 인터페이스와 자산의 의미에 모두 놓았다.

알아야 할 것은 아래 17개 차이의 표다. 17개 차이가 호환의 어느 층에 걸리는지는 위의 층 그림에 있다.

알아야 할 것은 Arc가 Ethereum과 다른 지점이다. Arc 문서 가운데 차이를 모아 적은 [EVM 차이 문서](https://docs.arc.io/arc/references/evm-differences.md)는 Ethereum의 Osaka 하드포크를 기준으로 비교하며, 차이를 여섯 개의 절로 나누어 적는다. 그 가운데 다섯 절의 표 행과 글머리 항목을 하나씩 세면 17개다. 나머지 SELFDESTRUCT 절의 조건 표는 아래 3번과 4번, 9번 항목을 풀어 쓴 것이어서 따로 세지 않았다. 세는 단위를 이렇게 정한 것은 나다.

| 번호 | 문서의 절                              | 차이                                                                                                                        | 이 원고의 설명                       |
| ---- | -------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| 1    | USDC as the native gas token           | 네이티브 자산이 ETH가 아니라 USDC이며, 소수 18자리의 네이티브 인터페이스와 6자리의 ERC-20 인터페이스가 한 잔액을 함께 쓴다. | 7.1(잔액 표현)                       |
| 2    | Execution and opcode differences       | `PREVRANDAO`가 항상 0을 돌려준다.                                                                                           | 7.4(실행 환경)                       |
| 3    | 같은 절                                | `SELFDESTRUCT`에 네이티브 값의 규칙이 더해지고, 성공하면 `Transfer` 로그를 남긴다.                                          | 7.5(계약 동작)                       |
| 4    | 같은 절                                | 이미 자기파괴된 계정에 값을 보내는 `CALL`이 되돌려진다.                                                                     | 7.5(계약 동작)                       |
| 5    | 같은 절                                | `parentBeaconBlockRoot`가 부모 실행 블록의 해시이고 beacon-roots 계약이 없다.                                               | 7.4(실행 환경)                       |
| 6    | 같은 절                                | 블롭 거래(type-3)를 받지 않고, `BLOBHASH`는 0, `BLOBBASEFEE`는 1이다.                                                       | 7.4(실행 환경)                       |
| 7    | 같은 절                                | withdrawals가 항상 비어 있다.                                                                                               | 7.4(실행 환경)                       |
| 8    | Value transfer rules                   | 영주소로 값을 보내면 되돌려진다. 0액은 성공한다.                                                                            | 7.5(계약 동작)                       |
| 9    | 같은 절                                | 소각이 금지된다. 잔액을 가진 채 자기 자신에게 자기파괴하거나 자기파괴된 계정에 값을 보내면 되돌려진다.                      | 7.5(계약 동작)                       |
| 10   | 같은 절                                | 실행 중에 차단 목록을 검사하며, 차단으로 되돌려진 거래도 가스를 쓴다.                                                       | 3.4(실패 처리), 7.5(계약 동작)       |
| 11   | 같은 절                                | 계약으로 네이티브 값을 보내는 호출이 성공한다는 보장이 없다.                                                                | 7.5(계약 동작)                       |
| 12   | Native USDC Transfer events (EIP-7708) | 네이티브 값이 움직이면 시스템 주소가 ERC-20 형식의 `Transfer` 로그를 남긴다. 가스 차감은 로그를 남기지 않는다.              | 7.3(이전 로그)                       |
| 13   | Fee market and block behavior          | 기본 수수료를 소각하지 않고 블록의 수수료 수취 주소에 준다.                                                                 | 7.2(수수료 기록)                     |
| 14   | 같은 절                                | 다음 블록의 기본 수수료가 부모 헤더의 `extra_data`에 들어 있다.                                                             | 7.2(수수료 기록)                     |
| 15   | 같은 절                                | 최소 기본 수수료는 20 Gwei이고, 그보다 낮은 거래는 오류 없이 거래 풀에서 버려진다.                                          | 4.3.4(과부하 저항), 7.2(수수료 기록) |
| 16   | 같은 절                                | 블록 시각이 줄어들지는 않지만 여러 블록이 같은 시각을 가질 수 있다.                                                         | 7.4(실행 환경)                       |
| 17   | 같은 절                                | 확정이 결정적이고 즉시 이루어진다.                                                                                          | 4.3.1(안전성), 4.3.3(거래 포함)      |

한 행은 문서가 적은 차이 하나다. 같은 문서는 EIP-7702, `CREATE2`와 EIP-2935가 Ethereum과 같게 동작한다고 따로 적는다. 이 문서 밖에도 차이가 있다. [호환성 변경 기록](https://github.com/circlefin/arc-node/blob/6e764023ee6515fe70573e123ed2db912a7207b4/BREAKING_CHANGES.md)은 대기 거래를 RPC에서 기본으로 숨기는 변경(3.1(거래 접수))과 클라이언트의 denylist 검사를 필수로 바꾼 변경(5.3(접근 제한))을 적는다. 8절(선택형 프라이버시)의 예정된 비공개 실행도 아직 제공되지 않는 차이다. 아래 그림은 7.1(잔액 표현)부터 7.3(이전 로그)까지가 다루는 기록의 관계다.

**거래 결과와 기록의 관계**

한국어:

```text
[거래의 실행 결과]
    |
    +-- [잔액 조회: 얼마가 있는가?]
    |       +-- 네이티브 표현
    |       +-- ERC-20 표현
    |           같은 USDC 잔액이며 표현 단위가 다르다.
    |
    +-- [영수증: 실행 결과와 비용은?]
    |       +-- 실행 성공 또는 실패
    |       +-- 사용 가스와 유효 가격
    |
    +-- [이전 로그: 어떤 이전을 기록했는가?]
            +-- 방출 주소 / 로그 위치 / 단위

두 잔액 표현을 별개 자산처럼 합산하지 않는다.
같은 이전을 나타내는 로그를 중복 합산하지 않는다.
이전 로그만으로 가스 차감과 모든 잔액 변화를 설명하지 않는다.
```

English:

```text
[Transaction execution result]
    |
    +-- [Balance query: how much is held?]
    |       +-- native representation
    |       +-- ERC-20 representation
    |           The same USDC balance, expressed in different units.
    |
    +-- [Receipt: execution outcome and cost?]
    |       +-- execution success or failure
    |       +-- gas used and effective price
    |
    +-- [Transfer logs: which transfers are recorded?]
            +-- emitting address / log position / unit

Do not add the two balance representations as separate assets.
Do not double-count logs that represent the same transfer.
Transfer logs alone do not account for gas deductions and all balance changes.
```

실제 개발에서는 계약이 전제한 규칙을 위 사양과 대조하고, 네트워크와 도구를 준비한 뒤 금액 단위, 요청 제출과 결과 확인, 실패 처리 및 검증 실험을 각각 점검해야 한다.

### 7.1 잔액 표현: 같은 USDC 잔액을 인터페이스별 단위로 읽는다

[네이티브 모형](https://docs.arc.io/arc/concepts/stablecoin-native-model.md)은 USDC의 네이티브 인터페이스와 ERC-20 인터페이스가 하나의 잔액을 공유한다고 설명한다. 네이티브 잔액은 소수 18자리, ERC-20 잔액은 소수 6자리 기준이다. 두 값을 별개 자산처럼 더하거나 같은 원시 정수 단위를 가정해서는 안 된다.

두 인터페이스는 같은 잔액을 서로 다른 호출 방식으로 다룬다. 네이티브 방식은 거래의 value와 계약의 `msg.value`, 가스 회계 등에 쓰이고, ERC-20 방식은 토큰의 이전과 승인 및 allowance에 쓰인다. allowance는 다른 주소가 이전할 수 있도록 승인한 한도다. 위 네이티브 모형은 Ethereum에서 ETH를 ERC-20으로 다루는 WETH처럼 별도 토큰으로 바꾸는 단계를 거치지 않는다고 설명한다. 조회나 이전에 어떤 인터페이스를 썼는지가 달라도 기초 잔액은 같은 USDC라는 점을 유지해야 한다.

같은 잔액이 두 정수로 나타나므로, 정수를 읽을 때는 그 값을 얻은 인터페이스와 단위를 함께 알아야 한다. ERC-20 조회는 소수 6자리 아래를 잘라 내므로, 그 조회에서 보이지 않는 소액도 네이티브 표현에는 남아 있다. 다음 계산과 그림은 같은 잔액의 표현 차이를 보여 준다.

공식 글 연결: [Compatibility Guide for EVM Apps on Arc](https://www.arc.io/blog/arc-compatibility-guide-for-existing-evm-apps) (2026-09-10, [공식 원문](https://www.arc.io/blog/arc-compatibility-guide-for-existing-evm-apps)). 호환성 안내는 네이티브 값과 ERC-20 값 사이의 소수 자릿수 변환을 설명한다. 인터페이스 단위 변환과 최종 USDC 표시를 구별하며 아래 계산 및 상세 사양을 유지한다.

| 표현                               | 1 USDC를 나타내는 정수            | 금액으로 읽는 계산                                        |
| ---------------------------------- | --------------------------------- | --------------------------------------------------------- |
| 네이티브 value 또는 잔액           | 10^18                             | 정수 / 10^18 USDC                                         |
| ERC-20 잔액 또는 일반 Transfer 값  | 10^6                              | 정수 / 10^6 USDC                                          |
| 네이티브 정수를 ERC-20 정수로 변환 | 네이티브 정수 / 10^12의 정수 부분 | 18자리와 6자리 사이 소수 자릿수 변환이며 소액을 절사한다. |

예를 들어 네이티브 정수 10^11은 `10^11 / 10^18 = 0.0000001 USDC`다. ERC-20 정수로는 `floor(10^11 / 10^12) = 0`이지만 자산이 사라진 것이 아니다. 아래 그림은 동일 잔액의 표현을 내가 구분한 것이며 자산을 나누거나 옮기는 그림이 아니다.

한국어:

```text
                 [하나의 USDC 잔액]
                        |
              +---------+---------+
              |                   |
              v                   v
[네이티브 정수: 18자리]  [ERC-20 정수: 6자리 / 절사]
              |                   |
       / 10^18로 금액 표시   / 10^6으로 금액 표시
```

English:

```text
                 [One USDC balance]
                        |
              +---------+---------+
              |                   |
              v                   v
[Native integer: 18 decimals] [ERC-20 integer: 6 decimals / truncation]
              |                   |
       Display via / 10^18   Display via / 10^6
```

[EVM 차이](https://docs.arc.io/arc/references/evm-differences.md)의 표시 안내에는 10^12로 나누라는 문구도 있다. 이것을 네이티브 원시 정수의 최종 USDC 금액 표시로 사용하면 단위가 맞지 않는다. 위 표처럼 두 정수 사이의 변환과 사람이 읽는 금액 표시를 구별한다. [가스 문서](https://docs.arc.io/arc/references/gas-and-fees.md)의 native send 예제는 `ethers.parseUnits("1", 6)`을 1 USDC라고 주석 처리하여 자체 18자리 표와 충돌한다. 명시된 단위대로라면 `10^6 / 10^18 = 10^-12 USDC`이며 예제를 그대로 복사하지 않는다.

**네이티브와 ERC-20 비교: 한 행은 두 방식을 비교하는 기준 하나다**

| 기준                     | 네이티브 인터페이스                        | ERC-20 인터페이스                                                                  |
| ------------------------ | ------------------------------------------ | ---------------------------------------------------------------------------------- |
| 무엇인가                 | 체인이 계정에 직접 기록하는 기본 잔액      | 토큰 계약이 따르는 공통 함수 표준                                                  |
| 다른 EVM 체인에서의 USDC | 해당하지 않는다. 기본 잔액은 ETH 등이다.   | USDC 토큰 계약의 저장값                                                            |
| Arc에서의 USDC           | 계정의 기초 잔액                           | 같은 기초 잔액을 `0x3600000000000000000000000000000000000000`에서 읽는다           |
| 소수 자릿수              | 18                                         | 6                                                                                  |
| 주된 용도                | 가스비 회계, 네이티브 송금, `msg.value`    | 앱의 이전, 사용 한도 승인과 조회                                                   |
| 잔액 조회                | `addr.balance`, `eth_getBalance`           | `USDC.balanceOf(addr)`                                                             |
| 사용 한도 승인           | 해당 기능이 없다.                          | `approve`, `allowance`                                                             |
| 이전 로그                | 시스템 발생 주소의 `Transfer`, 소수 18자리 | 시스템 `Transfer`와 ERC-20 계약의 `Transfer`가 함께 남는다. 계약 로그는 소수 6자리 |
| 표시하는 잔액            | 전체 자릿수                                | 10^-6 USDC보다 작은 부분을 버린다.                                                 |

표의 근거는 [네이티브 모델 문서](https://docs.arc.io/arc/concepts/stablecoin-native-model.md)과 [USDC 시스템 이벤트](https://docs.arc.io/arc/references/usdc-system-events.md)다. "사용 한도 승인" 행의 네이티브 칸은 Arc 문서가 승인과 한도를 ERC-20 인터페이스의 용도로만 적은 데서 내가 정리했다.

[Stablecoin-native model의 Wrapping tokens](https://docs.arc.io/arc/concepts/stablecoin-native-model.md)는 별도의 래퍼가 배포되거나 지원되지 않는다고 명시한다. DeFi SDK가 사용하는 EIP-7528 네이티브 자산 표지 주소는 USDC ERC-20 계약 주소의 별칭이 아니다. 네이티브 `value`와 ERC-20 계약 호출을 같은 잔액의 서로 다른 인터페이스로 다루되, 표지 주소에 ERC-20 계약이 있다고 가정하지 않는다.

[Stablecoin-native model의 래퍼 조건](https://docs.arc.io/arc/concepts/stablecoin-native-model.md)의 원문은 다음과 같다.

> No wrapper is deployed or supported.

### 7.2 수수료 기록: 사용 가스와 가격 및 수취 주소를 연결한다

USDC로 가스를 내면 별도 가스 자산을 준비하는 절차와 그 자산 가격의 변동을 줄일 수 있다. 그러나 비용은 사용 가스와 유효 가스 가격에 따라 달라진다. [수수료 설계](https://docs.arc.io/arc/concepts/stable-fee-design.md)는 최근 블록 이용률의 EWMA(Exponentially Weighted Moving Average, 최근 값에 더 큰 가중치를 주는 이동 평균)에 따라 기본 수수료를 조정한다고 설명한다.

공식 글 연결: [How Gas Works on Arc: Delivering Low Transaction Costs](https://www.arc.io/blog/how-gas-works-on-arc) (2025-09-10, [공식 원문](https://www.arc.io/blog/how-gas-works-on-arc)). 가스 소개는 이용률 평활화와 기본 수수료 변화 제한을 설명한다. 고정 요금이나 현재 매개변수를 직접 관측한 근거는 아니다.

문서의 모형에서 현재 이용률을 u, 이전 평활 값을 m, 반응 계수를 a라고 쓰면 새 평활 값은 `a*u + (1-a)*m`이다. a가 작을수록 단발성 부하 변화에 덜 반응한다. 평활 이용률이 목표를 넘으면 가격을 올리고 낮으면 내리되 최소와 최대 범위를 적용한다. 이는 설계 설명이며 저장소 alpha 정수 20을 환산 없이 수식의 a=20으로 넣는 계산이 아니다.

| 읽은 값                                               | 값이 속한 근거                          | 해석할 조건                                                                  |
| ----------------------------------------------------- | --------------------------------------- | ---------------------------------------------------------------------------- |
| 20 Gwei와 20,000 Gwei                                 | 문서의 테스트넷 기본 수수료 하한과 상한 | 현재 모든 네트워크에서 영원히 고정된 값이 아니다.                            |
| alpha 20, kRate 200, inverseElasticityMultiplier 5000 | 고정 커밋의 mainnet 초기 설정           | 원래 정수 필드를 유지한다. 척도와 구현을 읽지 않고 변화율을 계산하지 않는다. |
| 30,000,000 gas와 목표 500 ms                          | 같은 초기 설정 및 문서의 용량 설명      | 현재 블록의 실제 값과 달라질 수 있다.                                        |
| 약 0.001 USD의 ERC-20 이전                            | 수수료 문서의 정상 조건 설계 목표       | 모든 호출의 정액 요금이나 최악 지연 보장이 아니다.                           |

가스 50,000을 사용하고 팁이 없다고 가정하면 기본 가격 20 Gwei일 때 `50,000 * 20 * 10^9 / 10^18 = 0.001 USDC`, 20,000 Gwei일 때 `50,000 * 20,000 * 10^9 / 10^18 = 1 USDC`다. 가스 50,000은 Claude 답변이 정한 예시 입력이며 실제로 측정한 ERC-20 비용이 아니다. 실제 거래는 영수증의 사용 가스와 유효 가격을 읽고 승인 및 실패와 재시도의 비용도 포함해야 한다.

공식 가스 문서는 다음 블록의 기본 수수료를 부모 블록 헤더의 `extra_data`에 8바이트 big-endian 값으로 게시한다고 명시한다. 수취 주소(fee recipient)의 실제 설정과 기관별 사후 배분은 별도 운영 확인 대상이다. 이번에는 해당 모든 구현을 재검증하지 않았다. 수수료 문서의 sequencer라는 단어도 별도 중앙 순서 결정자의 존재를 입증하지 않는다. 이 연구에서는 합의 문서의 순환 제안자와 상세 실행 경로를 기준으로 설명하고 용어 차이를 남긴다.

수수료를 읽을 때 내가 구분하는 것은 표시 통화, 가격 조정과 개별 거래 비용이다. 표시 통화가 USDC라는 사실은 별도 가스 자산을 보유해야 하는 문제를 줄인다. 평활 가격 조정은 최근 이용률에 따라 기본 가격이 변하는 방법을 설명한다. 영수증의 사용 가스와 유효 가격은 실제 포함된 거래가 소비한 비용을 설명한다. 이 구분이 필요한 이유는 가격 변화를 완화하더라도 계약이 더 많은 가스를 사용하거나 실패 후 재시도하면 총비용이 달라질 수 있기 때문이다. 설계 목표 금액을 모든 업무의 정액 비용으로 사용하지 않는다.

수수료 설계는 기본 수수료를 소각하지 않고 기본 및 우선순위 수수료를 블록의 beneficiary에 적립한다고 설명한다. beneficiary는 블록의 수수료 수취 주소다. 변경 기록은 validator 모드에서 `--suggested-fee-recipient`를 요구한다. 이 규칙과 특정 기관의 소유권 및 사후 배분은 다른 주장이다. 특정 기관의 매출이나 토큰 보유자 수익으로 곧바로 옮기지 않는다. 익스플로러의 Burnt Fees 표시는 ChatGPT 답변의 관찰 및 추정으로 보존하며 이번에 해당 UI의 의미를 확인하지 않았다.

**수수료 가격 조정과 거래 비용**

한국어:

```text
기본 가격의 조정
[현재 이용률] ---+
                 +--> [평활 이용률] --> [목표와 비교]
[이전 평활 값] --+                           |
                                            v
                                    [기본 가격 조정]
                                    최소와 최대 범위 적용

개별 거래의 비용
[거래가 사용한 가스] -+
                      +--> [거래 비용]
[유효 가스 가격] -----+
    ^
    +-- 기본 가격과 거래의 수수료 조건을 함께 읽는다.

수수료 적립
[기본 수수료와 우선순위 수수료] --> [블록의 수수료 수취 주소]

수취 주소를 실제 기관의 매출이나 사후 배분과 동일시하지 않는다.
가격 조정의 설계와 실제 영수증의 비용을 구분한다.
```

English:

```text
Base price adjustment
[Current utilization] -----+
                           +--> [Smoothed utilization] --> [Compare with target]
[Previous smoothed value] -+                                      |
                                                                 v
                                                        [Adjust base price]
                                                        Apply minimum and maximum bounds

Individual transaction cost
[Gas used by the transaction] --+
                                +--> [Transaction cost]
[Effective gas price] ----------+
    ^
    +-- read the base price together with the transaction's fee terms.

Fee crediting
[Base and priority fees] --> [Block fee recipient address]

Do not equate the recipient address with institutional revenue or later distributions.
Distinguish the price adjustment design from costs in actual receipts.
```

[Gas and fees의 다음 블록 가격](https://docs.arc.io/arc/references/gas-and-fees.md)의 원문은 다음과 같다.

> Arc publishes the next block's base fee in the parent header's `extra_data`
> field as an 8-byte big-endian value,

하한 미달 거래에 관한 공식 문서의 설명은 다르다. Gas and fees는 `maxFeePerGas`가 20 Gwei 미만이면 거래가 대기 상태에 남거나 수수료 오류로 실패할 수 있다고 설명한다. EVM differences는 mempool에서 조용히 제거되며 오류 영수증을 만들지 않고 블록에 나타나지 않는다고 설명한다. 이 차이는 실제 제출 시험으로 해소하지 않았다.

수수료의 흐름도 판본과 설계를 구별한다. docs는 기본 수수료와 우선 수수료가 모두 블록 beneficiary에 지급되고 소각되지 않는다고 설명한다. 2025년 Litepaper는 출시 시 수수료를 Arc Treasury로 보내는 계획을 제시했다. 2026년 Token Whitepaper의 수수료를 ARC로 전환하여 배분하고 소각하는 구조는 제안된 경제 설계다. 현재 실행 규칙 하나로 합쳐 쓰지 않는다.

### 7.3 이전 로그: 자산 이전의 기록과 잔액 변화의 차이를 설명한다

[USDC 이벤트](https://docs.arc.io/arc/references/usdc-system-events.md)는 현재 네이티브 Transfer의 시스템 방출 주소와 ERC-20 방출 주소 및 각각의 18자리와 6자리 값을 구별한다. 일반 ERC-20 이전에서 두 로그가 같은 이전을 나타낼 수 있으므로 두 인터페이스를 합산하면 중복된다. 체인과 거래 해시, 방출 주소 및 로그 위치와 단위를 함께 기록해야 한다.

공식 글 연결: [Compatibility Guide for EVM Apps on Arc](https://www.arc.io/blog/arc-compatibility-guide-for-existing-evm-apps) (2026-09-10, [공식 원문](https://www.arc.io/blog/arc-compatibility-guide-for-existing-evm-apps)). 호환성 글도 같은 이전을 한 번만 기록하고 두 인터페이스의 로그를 중복 적립하지 않도록 설명한다. 0금액과 자기 이전 등의 예외는 상세 사양에서 확인한다.

같은 문서는 가스 차감과 블록 보상이 Transfer 로그를 만들지 않는다고 설명한다. 공식 USDC system events 문서는 0액 이전과 자기 자신으로의 이전(`from == to`)이 네이티브 시스템 Transfer 로그를 생성하지 않는다고 명시한다. 보존한 native authority 코드의 관찰도 이 조건에 대응한다. 따라서 모든 호출이 항상 두 로그를 남긴다고 일반화하지 않는다. 로그를 모으는 일과 잔액의 모든 변화를 대사하는 일은 다르다.

잔액은 특정 시점에 얼마를 보유하는지에 답하고, 로그는 실행 중 어떤 사건을 기록했는지에 답한다. 영수증은 해당 거래의 실행 상태와 비용을 읽는 별도 기록이다. 이전 로그의 금액을 모으는 것만으로 시작 잔액에서 종료 잔액까지의 모든 변화를 설명하려 하면 로그로 나타나지 않는 비용을 놓칠 수 있다. 또한 같은 이전이 여러 인터페이스의 로그로 기록되면 금액을 중복 합산할 수 있다. 따라서 잔액의 변화, 거래 비용과 이전 사건을 서로 대응시키되 동일한 기록이라고 취급하지 않는다.

과거 테스트넷의 NativeCoinTransferred 등은 현행 Transfer 형식과 구별한다. [공식 실행 계층 문서](https://docs.arc.io/arc/concepts/execution-layer.md)는 Memo(메타데이터를 붙이는 계약), Multicall3From(원 발신자를 유지하는 일괄 호출 계약)과 CallFrom(원 발신자를 보존하는 프리컴파일)의 관계를 설명한다. 실제 계약 및 호출 경로와 적용 버전을 확인한 것으로 쓰지 않는다. 로그 및 영수증의 개발 절차는 개발 설명, 지급 의무와 외부 기록의 대사는 기업 업무 설명에서 이어 설명한다.

USDC 시스템 이벤트 사양은 과거 테스트넷에서 `NativeCoinTransferred` 등의 이벤트를 사용했지만 활성화 이후에는 이를 발생시키지 않으며, 메인넷은 처음부터 시스템 `Transfer`를 사용했다고 설명한다. 과거 로그를 현재 사양의 예시로 옮기지 않는다. 이 구별은 문서의 시점 설명이며 실제 과거 블록을 조회한 결과는 아니다. [이벤트 사양의 과거 구역](https://docs.arc.io/arc/references/usdc-system-events.md).

**잔액 변화와 이전 로그의 대응**

| 동작 또는 관측                | 잔액과의 관계                              | 로그를 읽을 때 주의할 점                                  | 적용 근거와 범위                                                                    |
| ----------------------------- | ------------------------------------------ | --------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| 일반 ERC-20 이전              | 발신자와 수취인의 잔액이 변한다.           | 네이티브 로그와 ERC-20 로그가 같은 이전을 나타낼 수 있다. | 위 USDC 이벤트 문서의 현행 형식 설명이며 실제 거래 시험은 아니다.                   |
| 가스 차감                     | 거래 비용이 잔액에 반영된다.               | Transfer 로그만으로 비용을 집계하지 않는다.               | 위 이벤트 문서의 로그 생략 설명이다.                                                |
| 블록 보상                     | 수취 주소에 금액이 적립될 수 있다.         | 이전 로그와 별도로 잔액 및 비용 기록을 확인한다.          | 위 이벤트 문서와 수수료 설계의 설명이며 실제 기관의 배분은 미확인이다.              |
| 0액 또는 자기 자신으로의 이전 | 일반 이전과 같은 효과로 단순화하지 않는다. | 네이티브 로그의 생략 조건을 확인한다.                     | 공식 USDC system events의 생략 조건과 고정 코드의 관찰이며 실제 거래 시험은 아니다. |
| 과거 형식의 이벤트            | 당시 버전의 기록으로 해석한다.             | 현행 이벤트와 이름 및 단위를 일괄 적용하지 않는다.        | 과거 테스트넷 형식과 현행 설명의 구분이며 개별 과거 거래의 재검증은 아니다.         |

[USDC system events](https://docs.arc.io/arc/references/usdc-system-events.md)의 현재 명세에서는 네이티브 시스템 Transfer의 방출 주소가 `0xffffFFFfFFffffffffffffffFfFFFfffFFFfFFfE`이고 값의 단위는 소수 18자리다. ERC-20 Transfer의 방출 주소는 `0x3600000000000000000000000000000000000000`이고 소수 6자리다. 시스템 Transfer는 거래의 다른 로그보다 먼저 방출된다. 발행은 `Transfer(0x0, recipient, amount)`, 소각은 `Transfer(from, 0x0, amount)`로 표시하며, 권한 있는 프리컴파일의 발행 및 소각을 일반 영주소 송금과 구별한다. 가스비는 영수증의 `gasUsed * effectiveGasPrice`로 읽고 블록 보상 귀속은 `block.miner`로 읽는다.

[USDC system events의 로그 생략 규칙](https://docs.arc.io/arc/references/usdc-system-events.md)의 원문은 다음과 같다.

> * Zero-value transfers emit no log.
> * Self-transfers (`from == to`) emit no log.

Memo와 Multicall3From은 공식 문서에도 설명돼 있다. CallFrom을 통해 하위 호출에서 원래 EOA의 `msg.sender`를 유지한다. Memo는 메타데이터와 호출 결과를 연결하며 `BeforeMemo`, 하위 호출 로그, `Memo` 순서로 이벤트를 남긴다. 하위 호출이 실패하면 전체 거래를 `MemoFailed`로 되돌린다. Multicall3From은 하위 호출의 `allowFailure`가 false이면 전체 일괄 호출을 되돌리며 true이면 해당 호출의 실패를 허용할 수 있다. 직접 EOA 호출을 전제로 하고 스마트 계약 계정이나 ERC-4337 경로를 같은 방식으로 지원하지 않으며, CallFrom은 네이티브 값을 전달하지 않는다.

[Batched transactions의 발신자 보존](https://docs.arc.io/arc/concepts/batched-transactions.md)의 원문은 다음과 같다.

> it preserves the
> original externally owned account (EOA) wallet as `msg.sender` for each target
> call.

[Transaction memos의 호출 조건과 이벤트 순서](https://docs.arc.io/arc/concepts/transaction-memos.md)를 함께 읽어야 한다. 메타데이터를 남기는 기능은 외부 회계 업무를 자동 완료하는 기능과 구별한다.

로그 순서에 관한 두 공식 설명도 구별해야 한다. USDC system events는 네이티브 Transfer가 거래의 다른 로그보다 먼저 나온다고 적고, Transaction memos는 BeforeMemo 뒤에 대상 계약의 이벤트가 나온다고 설명한다. 이를 모든 Memo 경로의 네이티브 시스템 로그 순서로 일반화하지 않는다. Memo 문서의 예시는 대상 USDC 계약의 ERC-20 Transfer를 포함하며, 정확한 전체 영수증 순서는 실제 호출 경로에 맞춰 확인해야 한다.

### 7.4 실행 환경: 기존 EVM 도구의 재사용 범위와 차이를 설명한다

잔액과 비용 및 로그의 의미를 이해했더라도 계약이 전제한 실행 규칙까지 같은지는 별도로 확인해야 한다. 7.4(실행 환경)와 7.5(계약 동작)는 계약 기능과 자산 이전에 관한 Arc의 사양을 설명한다.

EVM 호환은 기존 계약과 도구를 활용하는 출발점이다. 그러나 [EVM 차이 문서](https://docs.arc.io/arc/references/evm-differences.md)는 Osaka 기준에서 실제 실행 의미가 달라지는 항목을 열거한다. 계약이 컴파일되고 배포됐다는 확인만으로 금액과 이벤트, 난수 및 네이티브 전송의 모든 가정이 맞는 것은 아니다.

공식 글 연결: [Compatibility Guide for EVM Apps on Arc](https://www.arc.io/blog/arc-compatibility-guide-for-existing-evm-apps) (2026-09-10, [공식 원문](https://www.arc.io/blog/arc-compatibility-guide-for-existing-evm-apps)). 호환성 글은 일반 로컬 EVM 시험으로 Arc 고유의 동작을 재현하지 못하는 범위를 설명한다. 컴파일과 배포 성공을 모든 실행 가정의 검증으로 확대하지 않는다.

여기서 재사용할 수 있는 것과 다시 검토해야 하는 것을 나누면 호환성의 의미가 분명해진다. EVM과 Solidity라는 공통 환경은 기존 코드와 도구를 활용할 출발점을 제공한다. 그러나 그 코드가 읽는 블록 정보와 명령어의 반환 값, 네이티브 자산 및 이벤트의 의미는 Arc의 사양을 따라야 한다. 같은 함수를 호출할 수 있다는 사실과 그 결과를 같은 방식으로 해석해도 된다는 사실은 별개다.

예를 들어 계약이 블록의 난수 관련 값을 추첨의 입력으로 사용하거나 시각이 반드시 증가한다고 가정하면, 아래 표의 반환 값과 시각 조건이 업무 로직에 직접 영향을 준다. 자산을 보관하는 계약에서는 네이티브 잔액과 ERC-20 잔액이 서로 다른 자산이라는 가정부터 검토해야 한다. 이는 모든 계약이 수정되어야 한다는 결론이 아니라, 계약이 실제로 사용하는 기능을 확인해 그 기능의 가정과 사양을 대조해야 한다는 뜻이다.

| 계약이 사용한 가정                             | 읽은 Arc 사양                                                                 | 검토할 영향                                                            |
| ---------------------------------------------- | ----------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| PREVRANDAO로 난수를 만든다.                    | 항상 0을 반환한다.                                                            | 별도의 난수 제공 방식과 신뢰 조건을 정해야 한다.                       |
| 블롭 거래와 관련 정보를 쓴다.                  | type-3 거래를 받지 않으며 BLOBHASH는 0, BLOBBASEFEE는 1이다.                  | 블롭 지원을 전제한 배포와 데이터 경로를 바꿔야 한다.                   |
| beacon-root 계약을 조회한다.                   | parentBeaconBlockRoot는 부모 실행 블록 해시이고 해당 beacon-root 계약은 없다. | 이 조회를 원래 oracle이나 난수의 근거로 사용하지 않는다.               |
| withdrawals 또는 초 단위 시각을 사용한다.      | withdrawals는 비어 있으며 여러 블록의 시각이 같을 수 있다.                    | 블록 순서와 거래 위치를 함께 사용하며 시각만으로 순서를 구하지 않는다. |
| CREATE2, EIP-7702와 과거 블록 해시를 사용한다. | 이 항목들과 EIP-2935는 Ethereum의 동작을 유지한다는 설명이다.                 | 모든 기능이 다르다고 뭉뚱그리지 않고 사용 항목을 실제 대조한다.        |
| 표준 anvil에서만 시험한다.                     | 표준 로컬 EVM은 Arc의 예외를 재현하지 못한다고 안내한다.                      | Arc Foundry의 시험 환경 및 실제 RPC와의 대응을 확인한다.               |

한 행은 계약의 실행 가정 하나다. 세 AI 답변이 제시한 차이와 공식 상세 사양을 함께 정리했다. 표는 실제 장애가 발생했다는 기록이 아니며, 어떤 가정이 Arc에서 달라지는지 보여 준다.

[EVM differences](https://docs.arc.io/arc/references/evm-differences.md)는 EIP-4788 beacon-roots 계약을 생략하여 해당 조회가 빈 값 `0x`를 반환한다고 설명한다. EIP-2935의 과거 블록 해시 계약은 배포되어 작동하며, `CREATE2`에는 EIP-7610의 잔존 저장소(residual-storage) 동작도 포함한다. 블록 시각은 제안자 시계의 초 단위 값이므로 1초 미만 블록들이 같은 timestamp를 가질 수 있다. 시각은 감소하지 않지만 매 블록 엄격히 증가하지 않으므로 순서를 구분할 때 블록 번호를 사용하라는 설명이다.

### 7.5 계약 동작: 명령어와 네이티브 USDC 이전의 제약을 설명한다

먼저 일반적인 자산 이전의 제약을 살펴보아야 SELFDESTRUCT의 차이도 이해할 수 있다. 앞의 [EVM 차이 문서](https://docs.arc.io/arc/references/evm-differences.md)는 네이티브 USDC를 값과 함께 영주소로 보내는 동작과, 이미 자기파괴된 계정에 값을 보내는 동작 등을 제한한다. 발신자나 수취인의 차단 조건도 실행 중 적용한다. 충분한 잔액은 이전의 필요 조건일 수 있지만 이 주소와 정책 조건을 대신하지 않는다.

공식 글 연결: [Compatibility Guide for EVM Apps on Arc](https://www.arc.io/blog/arc-compatibility-guide-for-existing-evm-apps) (2026-09-10, [공식 원문](https://www.arc.io/blog/arc-compatibility-guide-for-existing-evm-apps)). 호환성 글은 잔액이 충분해도 네이티브 값 이전이 성공하는 것은 아니라고 설명한다. SELFDESTRUCT와 차단 정책의 세부 조건은 상세 사양을 유지한다.

이 제약은 계약이 다른 주소로 값을 전달할 때도 중요하다. 사용자가 계약을 호출하는 요청 자체는 처리할 수 있어도, 그 계약이 실행 중 수행한 네이티브 이전은 제한 조건 때문에 실패할 수 있다. 따라서 계약 호출을 분석할 때는 최초 수취 주소만 보지 말고 실제 이전이 일어나는 대상과 결과도 보아야 한다. 문서는 영주소로의 0액 호출과 금액이 있는 이전을 구별하므로 모든 영주소 호출이 같은 결과라고 일반화하지 않는다.

Arc는 EIP-6780에 따른 SELFDESTRUCT를 설명한다. 같은 거래에서 생성된 계약에 한정해 계정을 완전히 삭제하는 조건과, 계약이 보유한 네이티브 USDC를 수혜자에게 옮기는 일은 다르다. USDC가 네이티브 잔액이므로 다른 체인의 ERC-20 잔액에는 없던 이동 의미가 생긴다.

상세 문서는 잔액을 가진 계약이 자기 자신이나 영주소로 보내거나 이미 자기파괴된 계정에 값을 보내는 경우, 차단된 발신자 또는 수취인에게 이전하는 경우 등의 실패를 설명한다. 잔액 0의 SELFDESTRUCT와 0액으로 영주소에 보내는 호출은 금액이 있는 경우와 다르다. 충분한 잔액만 확인해도 전송이 항상 성공하는 것이 아니다.

SELFDESTRUCT를 별도로 보는 이유는 계약의 수명과 자산 보관 방식이 함께 영향을 받기 때문이다. 일반적인 ERC-20 USDC 잔액은 토큰 계약 안의 기록이지만, Arc의 USDC는 해당 계정의 네이티브 잔액이기도 하다. 따라서 계약 종료에 사용한 명령어가 보유 USDC의 이전을 일으킬 수 있다. 문서는 잔액을 이동시키는 성공한 자기파괴가 시스템의 Transfer 로그를 남긴다고 설명한다. 삭제의 효과와 자산 이전의 허용 조건, 그 이전의 기록을 함께 읽어야 계약 종료의 결과를 정확히 설명할 수 있다.

예를 들어 계약이 보관한 USDC를 종료 시 전달하도록 설계했다면 "종료가 허용되는가", "실제로 삭제되는가", "수혜자에게 값을 옮길 수 있는가"를 각각 검토해야 한다. 이는 내가 사양의 조건을 연결한 검토 사례이며 실제 실행은 하지 않았다.

**계약 삭제와 자산 이전의 검토**

한국어:

```text
[SELFDESTRUCT 호출]
    |
    +-- [계정 삭제 조건]
    |       +-- 계약 생성 시점과 삭제 규칙을 확인한다.
    |       +-- 삭제 효과를 해석한다.
    |
    +-- [USDC 이전 조건]
            +-- 잔액 / 수혜자 / 차단 및 주소 조건을 확인한다.
            +-- 이전의 허용과 실패를 해석한다.
```

English:

```text
[SELFDESTRUCT call]
    |
    +-- [Account deletion conditions]
    |       +-- check contract creation timing and deletion rules.
    |       +-- interpret the deletion effect.
    |
    +-- [USDC transfer conditions]
            +-- check balance, beneficiary, blocking and address conditions.
            +-- interpret transfer permission and failure.
```

호출의 효과는 두 검토 결과를 함께 읽어 판단한다. 그림은 두 효과가 독립적으로 확정된다는 실행 순서도가 아니며, 실제 실행 결과는 적용 버전의 시험으로 확인한다.

공식 [EVM differences의 SELFDESTRUCT](https://docs.arc.io/arc/references/evm-differences.md)는 같은 거래 안에서 앞서 자기파괴한 주소로 이후 0이 아닌 값을 보내는 호출의 경우를 구체적으로 든다. Ethereum과 달리 Arc는 이를 금지된 소각으로 처리하여 되돌린다는 설명이다. 문서의 SELFDESTRUCT 표는 차단된 source 또는 beneficiary에서는 되돌린다는 행과 잔액이 0이면 any beneficiary에서 성공한다는 행을 함께 제시한다. 두 조건이 동시에 성립할 때의 우선순위는 이 표만으로 정하지 않는다.

## 8. 선택형 프라이버시(opt-in privacy): 공개 원장의 거래 내용을 감추는 예정 기능은 왜 필요하며 어떻게 설계되는가

앞의 설명은 누구나 읽을 수 있는 공개 EVM의 실행을 다뤘다. [프라이버시 문서](https://docs.arc.io/arc/concepts/opt-in-privacy.md)는 거래의 내용을 공개 원장에서 감추는 기능을 선택형 프라이버시(opt-in privacy)라고 부르고, 그 실행 환경을 APS(Arc Privacy Sector)라고 부른다. 이 기능은 아직 제공되지 않는다. 문서는 "Privacy features are on the roadmap and not yet available on Arc."라고 적는다. 8.1은 이 기능이 왜 필요한지를, 8.2부터 8.4까지는 그 설계를 설명한다. 설계의 설명은 현재 제공되는 기능이 아니라 예정된 설계로 읽는다.

공식 글 연결: [Opt-In Privacy on Arc for Real-World Onchain Finance](https://www.arc.io/blog/privacy-with-control-how-arc-can-unlock-onchain-finance) (2026-06-10, [공식 원문](https://www.arc.io/blog/privacy-with-control-how-arc-can-unlock-onchain-finance)). 프라이버시 소개는 선택형 기밀 기능을 미래 기능으로 설명한다. 현재 제공 조건은 기존 docs와 메인넷 발표를 함께 확인한다.

### 8.1 필요성: 공개 원장에서는 누구나 거래의 내용을 읽을 수 있다

지금의 Arc는 공개 원장이다. 2.1(사용자와 RPC 제공자)에서 본 Circle의 공개 RPC 주소는 키 없이 누구의 요청이든 받는다([RPC 주소 문서](https://docs.arc.io/arc/references/rpc-endpoints.md) ). 그 주소로 블록, 거래, 영수증과 잔액을 조회할 수 있다. USDC가 움직이면 보낸 주소, 받은 주소와 금액을 담은 `Transfer` 로그가 남는다([USDC 시스템 이벤트](https://docs.arc.io/arc/references/usdc-system-events.md), 7.3(이전 로그)). 따라서 어떤 회사의 주소를 알면 누구나 그 회사가 언제 누구에게 얼마를 보냈는지 읽을 수 있다. 이 문단의 결론은 이 자료들에서 내가 끌어낸 것이다.

Arc 자료는 이 공개성이 기업의 사용을 막는 이유가 된다고 적는다.

- [자금 관리 글](https://www.arc.io/blog/how-arc-supports-treasury-management-arc-blueprints)은 감추어야 할 정보의 예로 "vendor relationships, internal transfer amounts, and entity activity"를 든다. 거래처, 법인 사이 이전 금액과 법인의 활동이다.
- [자본시장 결제 글](https://www.arc.io/blog/how-arc-supports-capital-markets-settlement-arc-blueprints)은 기업 팀이 블록체인을 쓰지 못하는 구조적인 이유 가운데 하나로 "privacy controls that are either insufficient or bolt-on"을 든다.
- 프라이버시 문서는 감출지 말지를 앱이 정한다고 적는다. 원문은 "applications choose when business or regulatory requirements warrant keeping data off the public ledger"이다.

감추는 것만으로는 부족하다. 같은 자본시장 결제 글은 감사인이나 규제 기관처럼 권한을 받은 쪽은 거래를 볼 수 있어야 한다고 적고, 그 방법으로 선택적 공개(selective disclosure)와 열람 키(view-key)를 든다. 정리하면 이 기능이 풀려는 문제는 두 가지다. 하나는 공개 관측자에게 거래의 내용을 감추는 것이고, 다른 하나는 권한을 증명한 쪽에는 그 내용을 보여 주는 것이다. 두 문제로 나눈 것은 나다. 8.2(비공개 실행)와 8.3(키 관리)이 앞의 문제를, 8.4(접근 정책)가 뒤의 문제를 다룬다.

### 8.2 비공개 실행: 공개 접수와 보호된 실행 및 상태 확정을 연결하는 설계다

[Opt-in privacy](https://docs.arc.io/arc/concepts/opt-in-privacy.md)는 APS(Arc Privacy Sector)를 공개 EVM과 함께 작동하는 Solidity 계약의 기밀 실행 환경으로 정의한다. 하나의 블록체인에 공개 상태를 위한 Arc와 비공개 상태를 위한 APS라는 두 실행 환경을 두며, 두 상태 루트를 각 블록에서 함께 commit하여 같은 합의 라운드에서 진행하도록 설계한다. 프라이버시는 앱이 업무나 규제상 요구에 따라 선택하며, 문서는 아직 제공되지 않은 로드맵 기능이라고 명시한다.

공식 글 연결: [Opt-In Privacy on Arc for Real-World Onchain Finance](https://www.arc.io/blog/privacy-with-control-how-arc-can-unlock-onchain-finance) (2026-06-10, [공식 원문](https://www.arc.io/blog/privacy-with-control-how-arc-can-unlock-onchain-finance)). 프라이버시 소개는 기밀 실행과 허가된 정보 접근의 목표를 설명한다. 두 상태 루트와 암호화 및 이전 절차의 상세 조건은 기존 설계 문서에서 확인한다.

[Opt-in privacy의 제공 상태](https://docs.arc.io/arc/concepts/opt-in-privacy.md)의 원문은 다음과 같다.

> Privacy features are on the roadmap and not yet available on Arc.

설계에서는 표준 EVM 거래를 APS 공개키로 암호화해 지정 프리컴파일의 calldata(호출 입력 데이터)로 제출한다. 공개 원장에는 암호문과 접수 확인 및 미리 정한 가스 비용이 보이고, 비공개 실행의 반환 값과 로그는 공개하지 않는다. 검증자의 TEE(Trusted Execution Environment) 안에서 복호화 및 검증과 실행을 처리한다. TEE는 호스트와 구분된 보호 실행 환경이며 해당 환경의 enclave를 엔클레이브라고 부른다.

공개 및 비공개 상태 루트는 같은 블록에서 같은 합의로 확정하도록 설계한다. 상태 루트는 상태를 요약하는 해시다. 문서의 두 환경 사이 자산 이동도 같은 블록 안에서 통제된 프리컴파일로 연결하며 다른 체인의 비동기 bridge(체인 사이의 자산이나 메시지를 이전하는 연결)와 구별한다. 확정 이후 엔클레이브 안의 light client(확정 기록을 검사하는 간단한 클라이언트)가 commit certificate를 검사한 뒤 권한을 증명한 요청자에게 상태 조회를 허용한다. commit certificate는 확정에 참여한 서명을 검증하는 기록이다.

공개 접수와 비공개 결과를 나눈 설계에서는 공개 원장의 접수 확인만으로 요청자가 실행 결과 전체를 읽을 수 있는 것은 아니다. 공개 관측자는 암호문을 포함한 접수 기록을 보고, 권한을 증명한 요청자는 별도 조회 경로로 결과를 얻는다는 설명이다. 같은 블록에서 상태를 확정하도록 설계했다는 사실과 모든 정보를 같은 방식으로 조회할 수 있다는 사실도 다르다. 이 차이를 유지해야 암호화된 거래가 있다는 설명을 모든 메타데이터와 기록이 사라진다는 설명으로 확대하지 않을 수 있다.

한국어:

```text
[사용자 거래] -- APS 공개키로 암호화 --> [공개 원장: 암호문 / 접수 기록]
                                             |
                                             v
                                [증명을 확인한 엔클레이브: 복호화 / 실행]
                                             |
                                             v
                                [공개 및 비공개 상태 루트의 공동 확정]
                                             |
                                    확정 기록 검사 / 조회 권한 증명
                                             v
                                        [허용된 조회자]
```

English:

```text
[User transaction] -- encrypt with APS public key --> [Public ledger: ciphertext / acknowledgement]
                                                             |
                                                             v
                                              [Attested enclave: decryption / execution]
                                                             |
                                                             v
                                              [Joint commitment of public and private roots]
                                                             |
                                                Commit check / authorization proof
                                                             v
                                                       [Permitted viewer]
```

이 그림은 ChatGPT 답변의 APS 그림과 상세 사양을 함께 읽고 재구성한 예정 설계다. 공개 접수와 메타데이터, 비공개 실행 내용과 권한 조회를 나누며 모든 흔적이 사라진다고 설명하지 않는다. 현재 배포 및 실제 기밀 보장은 확인하지 않았다.

[Privacy Whitepaper의 Private Transaction Lifecycle](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/Whitepapers/Arc_Privacy_Sector%20%285%29.pdf)은 엔클레이브가 없는 노드와 엔클레이브가 있는 노드를 나눈다. 전자는 공개 부분을 실행하고 암호화된 비공개 상태 루트를 불투명한 값으로 다루며 비공개 상태를 검증하지 않는다. 후자는 복호화, 서명 검증과 실행을 다시 수행하고 계산한 비공개 상태 루트를 제안된 헤더와 비교한다. 이 설계에서 합의 검증자는 모두 엔클레이브를 실행해야 한다. 확정 뒤 RPC 조회에는 거래 해시와 원래 거래를 서명한 키로 증명하는 권한이 필요하다. 암호화된 실행 결과를 받으려면 제출할 때 임시 공개키(ephemeral public key)를 인수로 넣어야 한다. 백서는 이를 넣지 않으면 비공개 EVM(pEVM)이 결과를 반환하지 않는다고 설명한다.

공개 및 비공개 자산 연결의 구체적인 시점은 docs의 요약과 백서의 상세 설명을 함께 읽어야 한다. docs는 두 환경의 controlled precompile을 같은 블록 안의 원자적 조합으로 설명한다. 백서의 shield는 공개 자산의 소각 또는 잠금과 비공개 mirror 발행을 같은 블록 N에서 처리한다. unshield는 비공개 mirror를 블록 N에서 소각하고 N의 확정 뒤 블록 N+1에서 공개 자산을 발행하거나 잠금을 푼다고 설명한다. 백서는 미확정 상태를 호스트가 재정렬하거나 재실행하여 다른 비공개 거래 정보를 얻는 것을 막기 위한 구분이라고 설명한다.

[Privacy Whitepaper의 shield와 unshield 설명](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/Whitepapers/Arc_Privacy_Sector%20%285%29.pdf)의 원문은 다음과 같다.

> Unshielding burns the Private ERC20 in block N, and mint-or-unlocks public ERC20 value in block N+1 to ensure block N is finalized.

### 8.3 키 관리: 암호화와 실행 환경 인증 및 키 복원의 설계 조건을 설명한다

공식 설계는 암호화와 엔클레이브의 보호 실행을 함께 사용한다. X-Wing KEM(Key Encapsulation Mechanism, 키를 설정하는 암호기법)은 X25519와 ML-KEM-768을 결합하며 HKDF-SHA256과 AES-256-GCM을 사용한다. 상태에는 AES-256-GCM-SIV, 상태 루트에는 AES-256-GCM을 사용하고 노드 간 통신은 TLS 1.3의 X25519MLKEM768 혼합 키 교환을 설명한다. 알고리즘 이름을 확인한 사실만으로 실제 구현 전체의 안전성을 입증한 것은 아니다.

실행 환경 증명(attestation)은 엔클레이브가 허용된 실행 환경이라는 점을 확인하는 절차다. 설계의 단일 MSK(master secret key)는 파생 암호키의 원천이며 Shamir 임계 비밀 분할(threshold secret sharing)로 검증자 사이에 나눈다. 허용된 수의 조각이 모여야 복원하는 방식이다. 문서는 증명을 확인한 엔클레이브 안에서만 MSK를 복원하고 호스트에는 공개하지 않는다고 설명한다.

각 검증자 조직의 KMS(Key Management Service)는 어떤 엔클레이브에 키를 제공할지 정하는 attestation 정책을 갖는다. seed node(재시작 시 키 복원을 돕는 노드)의 복원 및 검증자 변경 시 키 교체 설명도 있다. 따라서 키 관리가 전혀 문서화되지 않았다는 결론은 사용하지 않는다. 남는 질문은 실제 복원 임계값과 정책 관리자, 키 교체 및 복원 운영 설정, 하드웨어와 구현의 감사 및 장애 대응이다.

암호화와 실행 환경 증명은 서로 다른 보호 대상을 가진다. 암호화는 허가 없이 내용을 읽지 못하도록 하고, 실행 환경 증명은 키를 제공받을 환경이 정책에서 허용한 대상인지 확인한다. 키를 복원하는 조건도 함께 필요하므로 암호 알고리즘이 있다는 사실만으로 하드웨어와 정책 운영에 대한 질문이 사라지지는 않는다. 반대로 보호 하드웨어를 사용한다고 입력과 상태를 암호화할 필요가 없어지는 것도 아니다.

위 [프라이버시 설계](https://docs.arc.io/arc/concepts/opt-in-privacy.md)는 거래 복호화와 계약 상태 및 상태 루트의 암호키를 MSK에서 파생한다고 설명한다. 따라서 단일한 비밀의 파생 관계와 여러 조직에 조각을 분산하는 관계를 함께 읽어야 한다. 분할은 비밀을 어느 한 호스트에 그대로 노출하는 방식과 다르지만, 그 자체만으로 조직의 독립성이나 정책 관리의 안전성을 입증하지 않는다. 장애 뒤 복원이 가능해야 한다는 가용성의 질문과 허가된 환경에서만 복원해야 한다는 기밀성의 질문도 함께 남는다.

**키 제공과 보호 실행의 관계**

한국어:

```text
예정 설계
[검증자 조직의 키 관리 정책]
    |
    +-- 허용할 실행 환경을 판단 --> [실행 환경 증명]
                                         |
                                         v
                              [증명을 확인한 보호 실행 환경]
                                         ^
                                         |
[임계 비밀 분할의 키 조각] ---------------+
    허용 조건에 따라 보호 환경 내부에서 복원
                                         |
                                         v
                               [복호화와 보호된 실행]
                                         |
                                         v
                                 [보호된 상태와 결과]

운영 확인: 복원 임계값 / 정책 관리자 / 키 교체 / 재시작과 복구 절차
```

English:

```text
Planned design
[Validator organization's key management policy]
    |
    +-- assess permitted execution environments --> [Execution environment attestation]
                                                               |
                                                               v
                                                  [Attested protected environment]
                                                               ^
                                                               |
[Threshold secret shares] -------------------------------------+
    Reconstruct inside the protected environment under permitted conditions.
                                                               |
                                                               v
                                                [Decryption and protected execution]
                                                               |
                                                               v
                                                    [Protected state and results]

Operational checks: recovery threshold / policy administrators / key rotation / restart and recovery
```

그림은 예정 설계의 관계이며, 현재 운영 배치를 확인한 그림은 아니다.

[Privacy Whitepaper의 Network Setup과 Key Generation](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/Whitepapers/Arc_Privacy_Sector%20%285%29.pdf)은 설계의 복원 임계값을 `TRecon = 2t + 1`로 둔다. `N`은 검증자 수이며 Byzantine 검증자 수의 상한 `t`는 `t < N/3`를 만족한다는 가정이다. 이 수식은 설계의 값이며 실제 운영 집합과 키 조각의 배치를 확인한 것은 아니다. dealer 엔클레이브가 초기 MSK와 Shamir 조각을 만들고, 각 조직의 독립 KMS를 통해 암호화한 조각을 게시한다. seed 엔클레이브는 허용된 조각을 복원하여 인증된 TLS로 승인된 pEVM 엔클레이브에 MSK를 제공한다.

키 교체에는 거래 암호화의 네트워크 공개키, 블록별 상태 루트 키와 저장 키가 함께 바뀐다. 이전 키로 암호화하여 이전 epoch에 포함되지 못한 거래는 새 키로 다시 제출해야 한다. 이전 snapshot과 write-ahead log를 읽는 키는 보존 기간이 끝나기 전까지 유지한다는 설계다. 백서는 정직한 엔클레이브에서 비밀을 추출하거나 코드를 변조할 수 없다고 가정하며, timing, traffic analysis와 access pattern 같은 측면 경로 공격(side-channel attacks)은 이 논문의 범위에서 다루지 않는다고 명시한다. 이 범위를 암호화만으로 모든 관측 위험이 사라진다는 보장으로 확대하지 않는다.

[Privacy Whitepaper의 위협 모형](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/Whitepapers/Arc_Privacy_Sector%20%285%29.pdf)의 원문은 다음과 같다.

> We do not address sidechannel attacks (timing, traffic analysis, access patterns) in this paper.

### 8.4 접근 정책: 함수 호출과 상태 조회 및 로그의 공개 범위를 설계한다

문서는 계약의 함수와 저장 위치를 기본적으로 외부에서 접근하지 못하게 하는 default-deny를 설명한다. 외부 공개는 함수 정책과 계약 간 신뢰 및 실행 시 가시성 검사로 정한다. 아래 표는 해당 문서의 정책 이름을 사용하며 내가 비교할 대상을 붙였다.

| 문서의 정책 또는 기능     | 허용 또는 제한하는 대상                 | 설명에서 유지할 조건                                               |
| ------------------------- | --------------------------------------- | ------------------------------------------------------------------ |
| Open                      | 열어 둔 함수의 호출                     | 같은 계약의 모든 잔액과 저장 값이 자동으로 공개된다는 뜻이 아니다. |
| Restricted                | 명시적인 권한을 가진 호출자             | 실제 grant와 권한 확인 및 조회 경로가 필요하다.                    |
| Locked                    | 호출을 무조건 revert한다.               | 실패 결과와 공개 메타데이터의 범위도 구별한다.                     |
| addTrustee와 trust domain | 지정 계약의 내부 정보 접근              | 단방향이며 철회할 수 있다. 상호 신뢰를 자동으로 가정하지 않는다.   |
| runtime visibility        | CALL 및 DELEGATECALL에서 의도한 진입점  | Solidity 가시성을 실제 실행에 적용한다는 예정 설명이다.            |
| 로그와 외부 정보          | 기본 로그 비활성, 명시적 공개 및 마스킹 | 누구에게 어떤 이벤트를 열지와 정해진 가스 보고를 함께 확인한다.    |

문서는 표준 ERC-20 bytecode를 APS에 두고 transfer는 Open, balanceOf는 허가된 계약에만 열도록 설정하는 예시도 제공한다. 이는 기존 업무 로직을 활용하면서 공개 인터페이스를 다시 정하는 설계다. 코드를 옮기는 작업과 접근 정책을 정하는 작업은 별도다.

이 예시에서 누구나 이전 함수를 호출할 수 있다는 설정과 누구나 잔액을 읽을 수 있다는 설정은 다르다. 또한 어느 계약에 내부 정보를 읽을 신뢰를 부여했다고 그 계약과 상호 신뢰가 자동으로 생기는 것은 아니다. 따라서 접근 정책은 하나의 공개 여부가 아니라 함수 호출, 상태 조회, 계약 간 접근과 로그 공개를 각각 설정하는 문제다. 공개 EVM에서 함수와 이벤트를 다루던 앱을 그대로 옮기기 전에 이 경로들의 정책이 업무에 필요한 조회와 기록을 허용하는지 확인해야 한다. 이는 예정 설계에 대한 검토 기준이며 실제 배포나 시험 결과는 아니다.

법적 요구에 따른 공개 가능성과 기술적으로 자동 부여된 규제기관 열람권도 다르다. 이번 선택 자료로 모든 감사인 또는 기관의 실제 키와 접근 경로를 확인하지 않았다. 정책이 허용하는 공개 범위와 사업의 규정 준수 판단을 같은 보장으로 쓰지 않는다.

공식 글 연결: [Opt-In Privacy on Arc for Real-World Onchain Finance](https://www.arc.io/blog/privacy-with-control-how-arc-can-unlock-onchain-finance) (2026-06-10, [공식 원문](https://www.arc.io/blog/privacy-with-control-how-arc-can-unlock-onchain-finance)). 프라이버시 소개는 승인받은 감사인 등의 접근을 설계 방향으로 설명한다. 모든 기관에 자동 열람권이 있거나 실제 접근 키를 확인했다는 뜻은 아니다.

**정보 종류별 접근 범위: 예정 설계**

| 정보 또는 행동   | 예정 설계에서 구분할 접근 조건                    | 자동으로 따라오지 않는 권한       |
| ---------------- | ------------------------------------------------- | --------------------------------- |
| 함수 호출        | 함수 정책에 따라 허용하거나 제한한다.             | 모든 상태와 잔액의 조회           |
| 계약 내부 상태   | 조회 권한과 계약 간 신뢰를 확인한다.              | 다른 계약의 내부 정보 접근        |
| 비공개 실행 결과 | 보호 실행과 반환 및 조회 경로를 확인한다.         | 공개 원장에서 결과 전체를 읽는 것 |
| 로그             | 명시적 공개와 마스킹 정책을 확인한다.             | 모든 실행 로그의 공개             |
| 공개 접수 정보   | 암호문과 접수 기록 및 공개 메타데이터를 구분한다. | 비공개 입력과 내부 상태의 복호화  |
| 감사 목적의 열람 | 실제 권한 부여와 접근 경로를 확인한다.            | 감사인이나 규제기관의 자동 열람권 |

[Opt-in privacy의 Contract isolation](https://docs.arc.io/arc/concepts/opt-in-privacy.md)은 활성 신뢰 관계가 없으면 `EXTCODESIZE`, `EXTCODEHASH`와 `BALANCE` 같은 외부 관측 명령이 0을 반환한다고 설명한다. 외부로 노출되는 revert 사유는 정제하고, 이벤트는 명시적 프리컴파일로 허용하며, 외부 관측자에게 보이는 가스는 constant-time으로 보고한다는 설계다. [Privacy Whitepaper의 Constant-time gas](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/Whitepapers/Arc_Privacy_Sector%20%285%29.pdf)는 이를 호출별로 정해진 외부 가스 값으로 풀이한다. 내부에서는 실제 가스를 측정하며 계약에 설정한 허용량을 넘으면 거래가 되돌아간다. 기본 격리와 외부 표시 방식의 설명을 모든 측면 경로 공격에 대한 증명으로 바꾸지 않는다.

## 9. 프로토콜 보장: 처리 결과의 의미와 확인 범위는 어디까지인가

앞의 설명을 종합하면 프로토콜이 처리하는 결과와 그 결과를 믿기 위한 조건을 구별할 수 있다. 먼저 보장의 성립 조건을 정리하고, 자료로 확인한 범위와 남은 운영 질문을 대조한 뒤 체인 밖의 완료 조건을 살펴본다.

### 9.1 보장의 성립 조건: 앞의 작동 원리와 신뢰 조건을 종합한다

이번 설명으로 말할 수 있는 것은 거래와 상태를 정해진 규칙으로 검사하고, 투표권과 잠금 및 메시지 전달 조건에 따라 유효한 블록을 확정하며, 앱이 확정과 실행 결과를 따로 관측한다는 관계다. 공개 풀 노드의 직접 검증은 그 결과를 검사하는 수단이며, 합의 집합과 규칙의 변경 권한은 별도로 존재한다. 수수료와 자산의 단위 및 로그와 EVM 예외는 앱의 정확한 회계와 실행을 위한 조건이다.

이 상위 답은 내가 자료를 연결한 종합 판단이다. 확신도는 중간이다. 문서와 선택 코드의 관계는 확인했지만 현재 집합과 키 보유자, 실제 바이너리와 계약 및 운영 성능을 함께 확인하지 않았기 때문이다. 예정 APS도 기밀 실행의 설명을 제공하지만 현재 배포와 실제 운영 보장은 미확인이다. 체인의 확정만으로 외부 자산의 상환, 은행 수취와 사업의 적합성을 결론 내리지 않는다.

프로토콜의 보장은 이 조건들을 연결해서 읽어야 한다. 실행 규칙에 맞는 후보인지 검사하고 합의 조건 아래 확정하는 과정은 블록의 정본성을 설명한다. 영수증과 계약 결과는 그 안의 특정 요청이 어떻게 처리됐는지 설명한다. 관리 권한은 앞으로 적용할 집합과 규칙을 바꿀 수 있는 조건을 설명한다. 직접 검증을 선택해도 허가된 합의와 규칙 변경의 권한까지 없어지는 것은 아니며, 예정된 선택형 프라이버시를 추가해도 외부 업무의 완료를 대신하지 않는다. 아래 표는 이 종합을 대상별로 다시 나눈 것이다.

**처리 결과와 보장 조건의 대조**

| 결론의 대상       | 설명할 수 있는 관계                                   | 함께 유지할 조건                    | 운영에서 추가로 확인할 것               |
| ----------------- | ----------------------------------------------------- | ----------------------------------- | --------------------------------------- |
| 블록 확정         | 합의 규칙에 따라 후보를 확정한다.                     | 투표권, 잠금과 메시지 전달 조건     | 실제 검증자 집합, 버전과 가동 상태      |
| 거래 성공         | 확정과 실행 성공을 구분한다.                          | 영수증과 대상 계약의 효과           | 실제 거래 및 계약 결과                  |
| 직접 검증         | 공개 풀 노드가 기록과 실행 결과를 검사한다.           | 합의 투표권과 구분한다.             | 운영 노드의 설정과 동기화 상태          |
| 규칙의 유지       | 주어진 규칙 아래에서 거래를 처리한다.                 | 규칙을 변경하는 권한이 존재한다.    | 현재 역할, 구현과 변경 이력             |
| 선택형 프라이버시 | 예정 설계가 암호화, 보호 실행과 접근 정책을 연결한다. | 현재 제공 기능으로 간주하지 않는다. | 실제 제공 시점, 구현과 운영 설정        |
| 외부 완료         | 체인 확정 뒤에도 별도 처리가 남을 수 있다.            | 경로별 담당 주체와 완료 조건        | 다른 체인, 지급망 또는 업무의 완료 기록 |

[Post-quantum security 문서](https://docs.arc.io/arc/concepts/post-quantum-security.md)는 서명 위조와 지금 수집하여 나중에 복호화하는 공격(harvest-now, decrypt-later)을 서로 다른 위험으로 설명한다. 현재 제공된다고 적은 `SLH-DSA-SHA2-128s` 검증은 계약이 calldata의 메시지, 공개키와 서명을 검증하여 상태 변경을 승인하는 앱 계층 기능이다. 서명자가 Arc 계정을 보유하지 않아도 사용할 수 있다는 설명이며, 지갑의 네이티브 거래 서명이 이미 양자내성 방식이라는 뜻은 아니다. 네이티브 거래 서명은 향후 EIP-8141 frame transactions가 확정되면 구현할 가능성으로 적는다.

[Post-quantum security의 네이티브 서명 계획](https://docs.arc.io/arc/concepts/post-quantum-security.md)의 원문은 다음과 같다.

> Post-quantum transaction signing is a future milestone and will likely
> implement EIP-8141 frame transactions once the EIP is finalized.

공식 로드맵은 지갑 서명 검증 및 향후 거래 서명을 In progress, 프라이버시 보호를 Near-term, 체인 밖 TLS와 암호화 기반 시설을 Mid-term, 검증자 서명을 Long-term으로 구별한다. APS 암호화, 앱의 서명 검증과 합의 검증자의 인증을 하나의 현재 양자내성 보장으로 합치지 않는다.

공식 글 연결: [Arc’s Post-Quantum Roadmap for Blockchain Security](https://www.arc.io/blog/arcs-quantum-resistant-design-and-roadmap-why-it-matters) (2026-04-02, [공식 원문](https://www.arc.io/blog/arcs-quantum-resistant-design-and-roadmap-why-it-matters)). 양자내성 로드맵 글은 검증자 인증의 변경에 성능 시험과 도구 준비가 필요하다고 설명한다. 출시 전 계획을 현재 모든 계층의 양자내성 보장으로 읽지 않는다.

[Circle Post-Quantum Whitepaper의 Quantum Ready Now와 Account Security](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/quantum_paper.pdf)는 당분간 네이티브 거래 서명을 ECDSA로 유지하는 이유로 서명 크기와 검증 비용, Falcon의 표준화 및 하드웨어 지갑 지원을 제시한다. ERC-4337 계정에서는 `validateUserOp`가 양자내성 서명을 검증하고 bundler는 전환기에 ECDSA를 계속 사용할 수 있다고 설명한다. hash-and-rotate, 두 키의 파생, 양자내성 공개키 등록과 frame transactions도 전환 방법으로 논의한다. 이들은 백서의 방법 제안이며 현재 지갑에서 모두 제공된다는 뜻은 아니다.

### 9.2 운영 확인: 설계와 코드 및 성능 자료로 확인한 범위를 구별한다

확인 범위는 자료의 종류와 버전, 성능 수치의 조건 및 남은 운영 질문을 함께 보아야 정할 수 있다.

#### 9.2.1 배포 근거: 문서와 고정 코드 및 초기 설정을 현재 운영과 구별한다

ChatGPT 답변과 Claude 답변이 근거로 든 최신 릴리스, 오래된 README와 변경된 mainnet 발표는 같은 시점과 같은 대상을 보고한 자료가 아니다. 새 코드 캡처는 arc-node 커밋 `6e764023ee6515fe70573e123ed2db912a7207b4`, Malachite 커밋 `72143f6c99a98452b587e1c392bdb80944eb2232`에 고정했다. 커밋 고정은 같은 소스를 재검토할 수 있게 하지만 운영 바이너리와 일치함을 입증하지 않는다.

| 자료의 종류           | 지금 설명할 수 있는 것                | 같은 것으로 올리지 않는 것                       |
| --------------------- | ------------------------------------- | ------------------------------------------------ |
| 기능 문서와 roadmap   | 제공자의 현재 또는 예정 설명          | 실제 모든 모듈의 제공과 계약 실행                |
| 고정된 공개 코드      | 특정 버전의 규칙과 접근 검사          | 현재 모든 검증자의 바이너리와 배포 구현          |
| 초기 설정             | 저장된 초기 주소와 투표권 및 매개변수 | 현재 Registry, 실제 법인과 역할 키 및 가동률     |
| 변경 기록의 버전 제목 | 버전 사이의 운영 차이                 | 최신 태그의 조회와 현재 운영 버전                |
| 발표 및 RPC 관측      | 발표 내용과 조회 시점의 응답          | 같은 시점의 전체 기능과 서비스 승인 및 계약 권리 |

한 행은 서로 다른 증거 역할이다. Grok 답변이 지적한 Chain ID의 문서 충돌과 세 답변이 적은 mainnet 상태는 공식 자료의 발표와 RPC 및 프로그램 기준일을 함께 대조한다. 조회 가능한 체인과 특정 기관 서비스의 승인 여부를 혼동하지 않는다.

예를 들어 공개 코드에서 관리 함수의 호출 조건을 확인했다면 특정 버전이 어떤 권한 검사를 정의하는지 설명할 수 있다. 이를 현재 운영의 설명으로 연결하려면 실제 배포된 구현과 그 역할 주소 및 적용 버전을 추가로 맞춰야 한다. 초기 설정에 주소가 들어 있다는 사실만으로 현재 키 보유자까지 알 수는 없다. 설명을 더 상세히 쓰는 것과 근거의 적용 범위가 더 넓어지는 것은 다르므로, 이 보완에서도 보존된 문서와 코드의 설명을 새로운 운영 관측으로 올리지 않는다.

#### 9.2.2 성능 근거: 벤치마크의 처리량과 실제 제출 지연을 구별한다

TPS(Transactions Per Second)는 초당 거래 처리량이며, 블록 간격과 사용자의 제출부터 확정까지 걸린 시간은 다른 값이다. [합의 문서](https://docs.arc.io/arc/concepts/consensus-layer.md)의 3,000+ TPS는 20개 검증자, 10,000+ TPS는 4개 검증자 조건이며 350 ms 미만 확정은 benchmark 조건이다. 이를 현재 운영에서 모든 거래에 적용되는 상한으로 합치지 않는다.

공식 글 연결: [Deterministic Sub-Second Finality on Arc](https://www.arc.io/blog/deterministic-finality-on-arc) (2025-10-09, [공식 원문](https://www.arc.io/blog/deterministic-finality-on-arc)). 최종성 소개도 검증자 구성에 따른 벤치마크 결과를 제시한다. 내부 시험 조건과 EVM 실행 비용의 범위를 유지하며 현재 모든 거래의 지연 상한으로 쓰지 않는다.

Claude와 ChatGPT의 답변에는 범위가 다른 수치도 제시되어 있다. Claude의 780 ms는 100개 검증자와 1 MB 블록의 엔진 초기 실험, 약 0.48초와 가동률 100%는 테스트넷의 특정 분기 보고, 약 506 ms는 개시일의 제3자 서술로 구분돼 있다. ChatGPT의 짧은 익스플로러 평균도 표본과 조회 시점을 가진 값이다. 이번 단계에서 이 수치들의 출처와 측정 방법을 모두 재검증하지 않았으므로 각각 보고된 종류와 미확인을 유지한다.

가스 한도 30,000,000과 블록 간격 0.5초가 실제 적용되고 모든 블록을 같은 거래로 가득 채운다고 가정하면 `30,000,000 / 0.5 = 60,000,000 gas/s`다. 거래당 21,000 gas라는 예시라면 `60,000,000 / 21,000 = 약 2,857 거래/s`, 거래당 50,000 gas를 가정하면 `60,000,000 / 50,000 = 1,200 거래/s`다. 이는 가스 예산의 조건부 계산이며 실제 블록 생성과 합의, 전파 및 저장의 용량을 측정한 최대 처리량이 아니다.

이 계산과 3,000+ TPS 표가 다르다고 공식 수치가 반드시 틀렸다고 결론 내리지 않는다. 거래 종류, 가스 한도와 시간, 빈 블록 및 실험에서 포함한 구간이 같은지 먼저 확인해야 한다. 초기 설정과 실제 블록 및 합의 벤치마크를 구별하는 이유다. 가스 한도를 200,000,000까지 바꿀 수 있다는 Claude 답변의 주장도 이번에 그 전체 클라이언트 제한을 확인하지 않았으며 실제 현재 용량으로 채택하지 않는다.

측정값이 답하는 질문도 구분해야 한다. 블록 간격은 연속한 블록 사이의 시간이고, 제출부터 확정까지의 지연은 접수와 대기 및 포함을 거치는 개별 거래의 시간이다. 처리량은 명시한 구간에 처리한 거래의 양을 설명한다. 블록이 짧은 간격으로 만들어져도 특정 거래가 오래 대기할 수 있고, 많은 단순 거래를 처리하는 실험 결과가 복잡한 계약 호출의 용량과 같지는 않을 수 있다. 따라서 성능을 비교할 때는 수치보다 먼저 처리한 대상과 측정 구간을 맞춰야 한다.

감사 및 바운티의 언급은 전체 보안 감사 보고서나 모든 운영 오류의 보장이 아니다. Claude 답변이 적은 코드 공개일과, 감사 보고서를 찾지 못했다는 설명은 조사 후보로 남긴다. 해당 보고서를 열지 않은 상태에서 감사가 없거나 안전성이 입증됐다고 쓰지 않는다.

**성능 지표의 측정 대상과 구간**

한국어:

```text
사용자 거래의 관측 경로
[제출] ------ [접수와 대기] ------ [블록 포함] ------ [확정]
   |                                                  |
   +-------- 제출부터 확정까지 관측한 지연 ------------+

블록의 관측 경로
[블록 A] ---------------------- [블록 B]
   |                               |
   +------ 블록 간격의 관측 --------+

처리량의 측정
[명시한 측정 구간]
    +-- 그 구간에 처리한 거래 수 / 구간의 길이

비교 조건:
거래 종류 / 검증자 구성 / 부하 / 측정 시작과 종료 / 버전

벤치마크의 확정 시간은 해당 실험의 측정 정의를 확인한 뒤 표시한다.
선 길이는 실제 소요 시간을 나타내지 않으며 평균과 상한도 구분한다.
```

English:

```text
Observed transaction path
[Submission] -- [Admission and waiting] -- [Block inclusion] -- [Commit]
      |                                                          |
      +---------- observed submission-to-commit latency ----------+

Observed block path
[Block A] ---------------------- [Block B]
    |                               |
    +----- observed block interval -+

Throughput measurement
[Specified measurement interval]
    +-- transactions processed in the interval / interval duration

Comparison conditions:
Transaction type / validator configuration / load / measurement endpoints / version

Label benchmark finality time only after checking the experiment's measurement definition.
Line lengths do not represent elapsed time; distinguish averages from upper bounds.
```

Litepaper의 합의 벤치마크에는 실행 비용에 관한 조건이 있다. 아래 각주는 확정 지연 수치가 EVM 실행의 추가 비용을 포함하지 않으며 합의에 초점을 맞춘 벤치마크라고 명시한다. docs의 optimistic responsiveness는 네트워크가 허용하는 속도로 블록을 만들고 인위적인 지연이나 추가 timeout을 두지 않는다는 설명이다. 이를 거래 제출부터 실행과 확정까지의 모든 지연 상한으로 바꾸지 않는다.

[Litepaper의 합의 벤치마크 각주](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/Arc%20Litepaper%20-%202025.pdf)의 원문은 다음과 같다.

> It is also important to note that this latency does not yet account for the additional overhead of EVM execution as the benchmarks were focused on consensus.

#### 9.2.3 후속 확인: 남은 운영 질문과 필요한 근거를 구별한다

| 세 답변에서 제시한 기여 또는 남은 질문                                                                | 추가로 확인할 대상                                                                                                                     | 이 원고에서 유지한 경계                                                             |
| ----------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| 정상 및 실패 지급, RFI(Request for Information, 추가 자료 요청)와 은행 및 기관 자격                   | 기관별 지급, 반환 절차와 책임                                                                                                          | 체인 확정 이후에도 별도 업무가 남는다.                                              |
| Memo, Multicall3From와 CallFrom, 이벤트 및 단위, Arc Foundry 시험                                     | 공식 호출 조건과 실제 구현 대조                                                                                                        | AI 답변이 설명한 기능과 직접 시험한 결과를 구별한다.                                |
| 수수료 주소와 기관 수익, Grok 답변이 보고한 USYC 상품의 자격과 100,000 USD 조건, ARC 발행과 개인 배분 | 상품별 가입 및 투자 조건과 토큰의 배분 권리를 확인한다. USYC는 펀드 지분을 나타내는 토큰이다.                                          | 네트워크 이용과 자산 및 토큰 권리는 별개다. 이 원고의 최소 금액 검증 결과가 아니다. |
| Chain ID와 발표 기준일, 코드 및 모듈 상태                                                             | 공식 설정, 발표와 같은 시점의 RPC 응답 대조                                                                                            | 초기 설정 및 공개 코드만으로 현재 배포를 판정하지 않는다.                           |
| 풀 재광고 및 용량, 조각 크기와 시계, fee recipient 검사와 extra_data, 최대 가스 설정                  | 고정된 관련 코드와 운영 옵션 및 현재 계약을 이어 읽는다.                                                                               | 이번에 모든 경로와 숫자를 검증한 것으로 쓰지 않는다.                                |
| 감사 보고서와 SLA(Service Level Agreement, 운영 수준의 계약) 집행, 지역 및 키 구조                    | 실제 보고서와 기관 및 운영 관측을 확보한다. 계약의 언급은 [합의 문서](https://docs.arc.io/arc/concepts/consensus-layer.md)에서 읽었다. | 검색 실패를 부재로 바꾸지 않는다.                                                   |
| APS 복원 임계값과 정책 관리자, 키 교체 및 조회와 감사                                                 | 실제 제공 시점과 설계 구현 및 운영 절차를 대조한다.                                                                                    | 예정된 암호화와 하드웨어 및 정책을 현재 보장으로 바꾸지 않는다.                     |

한 행은 다음 설명에 필요한 기여 또는 관측 하나다. 각 기여는 확인 범위와 미확인 조건을 구별해 읽어야 한다.

### 9.3 외부 완료: 체인 확정과 다른 체인 및 은행의 처리 완료를 구별한다

Chain finality와 외부 메시지 증명, 다른 체인의 발행 또는 이전, API 지급 상태와 은행 입금 및 주문 이행은 다른 종료점이다. 아래 그림은 ChatGPT의 외부 경로와 Grok의 업무 경계를 내가 다시 연결한 것이다. 모든 상품이 이 정확한 순서와 같은 서비스를 사용한다는 뜻은 아니다.

한국어:

```text
[Arc의 확정된 상태]
       |
       +-- 다른 체인 경로 --> [증명/전달] --> [목적 체인의 처리와 확정]
       |
       +-- 기관 지급 경로 --> [상품의 상태] --> [현지 지급망 / 고객 수취]
       |
       +-- 상거래 경로 ----> [계약/업무 확인] --> [상품 또는 서비스 이행]
```

English:

```text
[Finalized Arc state]
       |
       +-- cross-chain path --> [Proof/delivery] --> [Destination execution and finality]
       |
       +-- institutional path --> [Product state] --> [Local rail / customer receipt]
       |
       +-- commerce path ----> [Contract/business check] --> [Goods or service fulfillment]
```

어느 외부 API의 장애나 지급 지연을 관측했다고 Arc 블록 생산의 중단까지 확인한 것은 아니다. 반대로 Arc가 계속 확정해도 외부 경로와 고객 수취가 정상이라는 뜻은 아니다.

예를 들어 Arc에서 지급에 관련된 계약 호출이 성공했더라도, 그 기록을 받아 외부 업무를 진행하는 주체가 다음 처리를 완료했는지는 별도 기록으로 확인해야 한다. 체인 쪽에서는 확정된 블록과 영수증 및 계약 효과를 확인하고, 외부 쪽에서는 해당 지급이나 주문의 상태와 실제 수취를 확인한다. 이는 모든 서비스가 같은 경로를 쓴다는 주장이 아니라, 완료라고 부르려는 대상에 맞는 근거를 찾아야 한다는 원칙이다. 프로토콜의 빠른 확정은 그 구간의 결과이며 업무 전체의 종료 조건은 별도로 남는다.
