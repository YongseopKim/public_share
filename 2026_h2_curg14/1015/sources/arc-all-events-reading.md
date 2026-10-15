---
date: 2026-10-08
type: analysis
tags: [blockchain, business, stablecoin, AI]
status: review
reading_mode: reconstruction
language: ko
source_role_map: cb/works/web/2026-10-08-arc-events-complete/outputs/source-roles.md
unresolved: cb/works/web/2026-10-08-arc-events-complete/outputs/unresolved.md
reconstruction_review: cb/works/web/2026-10-08-arc-events-complete/outputs/final-review.md
source:
  - cb/works/web/2026-10-08-arc-events-complete/README.md
  - cb/works/web/2026-10-08-arc-events-complete/capture-manifest.json
  - cb/works/web/2026-10-08-arc-events-complete/linked-manifest.json
analysis_runs:
  - date: 2026-10-08
    tool: codex
    model: gpt-6
    model_class: deep-reasoning
    reasoning: unknown
    scope: "웹아카이브 모집단 대조, 관찰 원문 확인, 모든 행사 재구성과 기존 문서 수정; 외부 사실 판독 미실행"
  - date: 2026-10-08
    tool: codex-subagent
    model: gpt-6.1-sol
    model_class: general
    reasoning: medium
    scope: "배정된 공고와 연결자료 전체 또는 명시된 행 범위 관찰; 판단과 durable 문서 편집 미실행"
---

# Arc 공개 이벤트 전체 정리

추가로 받은 Microgrants, ETHGlobal Mumbai, Pragma Cannes와 Pragma Mumbai 저장 화면의 제출 질문 및 전체 FAQ는 웹아카이브 보완 정리에 있다. 행사 목록의 이전 날짜와 주최자 화면의 날짜를 따로 보존했다.

이해 전용 실행 - 판독 미실행. 이 문서는 사용자가 저장한 Arc House 이벤트 화면에 나온 모든 카드의 상세 내용을 정리한다. 행사 본문뿐 아니라 공개 일정, 발표자, 세션, 참가 안내와 연결된 주최자 자료를 함께 읽었다. 기술 성능과 실제 개최, 개인의 최종 참가 자격은 공고의 설명과 구분한다.

기존 문서는 일부 해커톤과 지원 프로그램을 골라 읽은 자료였다. 그 자료를 전체 참여 기회의 지도처럼 안내했던 설명은 철회한다. 여기서는 국가, 개인의 제품 유무, 참가 가치로 공고를 먼저 제외하지 않았다. 같은 이름의 다른 회차와 같은 행사에 대한 별도 공고도 남겼다.

## 목록을 읽는 방법

아래 번호는 저장 화면의 카드 순서다. 번호별 정리에는 목적, 다루는 내용, 참가 조건과 지원, 공개 세션 및 확인할 차이를 담았다. 연결된 원문에는 요약에서 반복하지 않은 면책 문구와 전체 메타데이터도 남아 있다. 목록의 시작일은 공개 데이터의 `startedAt`을 UTC 기준으로 표시한 값이며 신청 마감이 아니다. 행사별 본문에 있는 제출 마감과 지역 시간 표기는 따로 읽어야 한다.

모집단 대조는 `python3 cb/works/web/2026-10-08-arc-events-complete/outputs/run/verify_capture.py`, 실제 열람 행과 인용 대조는 `python3 cb/works/web/2026-10-08-arc-events-complete/outputs/run/verify_observations.py`로 수행한다. 결과와 현재 문서의 행사 포함 여부는 검사 기록에 있다. 이 숫자는 행사 상세 페이지의 수이며 독립된 프로그램의 수가 아니다.

## 개발 참여 기회가 어떻게 다른가

다음은 활동 목적을 비교하려고 내가 만든 구분이다. 공고 자체가 전체 행사를 이 방식으로 분류한 것은 아니다. 경쟁, 개발 실습, 기술 질문, 결과 발표와 지역 교류라는 활동이 각 본문에 명시되어 있어 이 기준으로 비교했다.

| 활동 | 공고에서 볼 수 있는 사례 | 개발자가 확인할 것 |
|---|---|---|
| 해커톤과 상금 경쟁 | Lepton, Tameion, Encode, LabLab, ETHGlobal, OpenClaw USDC, Agentic Economy Prize가 있다. | 각 회차의 주제, 실제 제출물, 사용하는 체인과 도구, 시연 및 사용 실적, 상금 심사와 등록 조건을 확인한다. |
| 보조금과 성장 지원 | Microgrants와 Acceleration Season 공고, Programmable Money의 후속 액셀러레이터 안내가 있다. | 이미 배포한 결과물이 필요한지, 기존 사업이 대상인지, 이전 대회 선발팀만 이어지는 지원인지 구분한다. |
| 교육, 실습과 기술 상담 | Programmable Money Bootcamp, Blockradar 워크숍, Technical Office Hours, App Kit 및 Agent Stack 실습이 있다. | 다루는 도구와 예제, 노트북 및 계정 준비, 구체적인 기술 질문의 사전 제출 여부를 확인한다. |
| 개발 결과와 제품 소개 | Builder Spotlight, Agentic Demo Day, Agora 발표, Show & Tell, 공개 소스 자료 안내가 있다. | 다른 팀의 제품, 구현 방법, 다시보기와 코드 자료, 자신의 결과물 발표 및 피드백 기회를 확인한다. |
| 지역 교류와 함께 개발하기 | Vietnam, Bangladesh, Brasil, Argentina, Nigeria, Turkey 등의 모임과 Build Club이 있다. | 개최 도시, 언어, 온라인 참여 방식, 프로젝트를 가져오는 조건과 지역 커뮤니티 대상 표현을 확인한다. |
| 컨퍼런스와 생태계 발표 | Sui Basecamp, Circle House, Pragma, 메인넷 출시 방송과 파트너 대화가 있다. | 강연과 개발 실습 중 무엇을 제공하는지, 입장권과 별도 등록 및 초대 조건을 확인한다. |

개인 제품이 아직 구체화되지 않았다는 이유로 해커톤과 Microgrants만 남길 근거는 없다. 위 교육, 기술 상담과 제품 발표에도 아이디어를 이해하고 구현 방법을 익히는 활동이 명시되어 있다. 이는 활동 내용을 비교한 설명이며 참가 우선순위를 확정한 것은 아니다.

## 헷갈렸던 프로그램의 관계

| 이름 | 공고가 설명하는 것 | 다른 페이지와의 관계 |
|---|---|---|
| Lepton과 Tameion | Canteen 해커톤 시리즈의 서로 다른 회차다. 주최자 자료는 제품 제안, 실제 사용과 에이전트 판단, 제출물을 설명한다. | 두 행사 모두 저장 화면에 카드가 있다. Tameion의 현재 Arc 설명은 비어 있어 주최자 자료를 별도로 읽었다. Arc 일정과 주최자 일정의 차이는 덮어쓰지 않았다. |
| Arc Microgrants | Arc 메인넷에 이미 배포한 작은 결과물을 제출하는 보조금 공고다. | 해커톤 후속 개발도 허용하지만 이미 Circle 또는 Arc가 자금을 지원한 작업은 제외한다고 적는다. 두 공고의 구체적인 중복 수혜 판단까지 확정한 것은 아니다. |
| Arc Acceleration Season | 라틴아메리카 핀테크와 AI 스타트업이 실제 통합을 개발하고 출시하는 온라인 프로그램이다. | 국적 하나로 자격을 판정할 수는 없다. 본문은 대상 사업과 지역을 명시하며 시민권이나 한국인 일반 배제 규칙 전체를 제시하지 않는다. |
| Programmable Money Bootcamp, Hackathon, Demo Day | 교육, 제품 개발 경쟁, 개발 결과 발표라는 서로 다른 공고가 있다. | 해커톤 본문이 상위 팀의 후속 액셀러레이터를 설명하고 Demo Day도 그 다음 과정으로 이어진다고 적는다. 새로운 독립 공개 모집과 같다고 볼 수는 없다. |
| Circle Developer Grants 소개 행사 | 보조금 취지, 평가, 신청 절차와 기술 및 홍보 지원을 설명하는 방송이다. | 이 행사 티켓이나 등록은 보조금 신청 및 선정과 다르다. 실제 프로그램 안내와 신청 양식을 구분한다. |
| ETHGlobal, LabLab, Encode 행사 | 주최자와 Circle 또는 Arc의 후원 및 개발 지원이 결합한 행사들이다. | 전체 대회 상금과 Arc 상금, 본행사와 킥오프 및 현장 구성, 수상자 발표를 서로 구별한다. |

## 자주 나오는 용어

| 원어 | 이 문서에서 읽는 뜻 |
|---|---|
| Office Hours | 개발 상담이나 커뮤니티 질의응답 시간이다. Technical Office Hours에는 구체적인 기술 질문과 등록 승인을 요구하는 회차가 있다. |
| Builder Spotlight, Demo Day, Show & Tell | 개발자가 만든 제품이나 결과물을 소개하고 시연하는 행사다. 각각을 새 해커톤 모집으로 읽지 않는다. |
| Build Club | 참가자가 함께 개발하고 진행 상황을 공유하는 모임이다. |
| RFB, Requests for Builders | Canteen 주최자가 제시한 개발 문제와 제품 아이디어다. Lepton과 Tameion 자료는 이를 경쟁 트랙이라고 하지 않는다. |
| bounty | 정해진 개발 과제를 수행하고 심사받는 보상 과제다. 전체 대회 상금과 별개인 후원 과제일 수 있다. |
| traction | 실제 이용자, 사용 사업체, 실행한 거래 등 제품 사용의 증거다. 목업이나 합성 데이터와 구분하는 공고가 있다. |
| App Kit, Gateway, CCTP, Agent Stack | 공고에서 다루는 Arc와 Circle 개발 도구의 고유 이름이다. App Kit는 결제와 자금 이동을 구성하는 SDK, Gateway는 체인 간 통합 USDC 잔액, CCTP는 체인 간 USDC 이동, Agent Stack은 에이전트 지갑과 거래를 위한 도구 묶음으로 소개된다. |
| nanopayments | 사용량이나 요청 한 번처럼 작은 단위로 수행하는 초소액 결제다. 특정 행사에서는 Circle Nanopayments 제품을 가리킨다. |
| EVM, DeFi, CLI, SDK | 각각 Ethereum Virtual Machine, 탈중앙 금융(Decentralized Finance), 명령줄 인터페이스(Command-Line Interface), 소프트웨어 개발 도구 묶음(Software Development Kit)을 가리킨다. |
| DevRel | Developer Relations의 약칭이며 개발자 관계 및 기술 지원 팀을 가리킨다. |

## 전체 이벤트 찾아보기

| 순서 | 공고 원문과 상세 정리 | 시작일(UTC) | 페이지 표시 형식 |
|---|---|---|---|
| 001 | Sui Basecamp 2026 / [정리](#행사-001) | 2026-10-07 | In-Person |
| 002 | Circle House @ TOKEN2049 Singapore 🇸🇬 / [정리](#행사-002) | 2026-10-07 | In-Person |
| 003 | Tameion Agents Hackathon / [정리](#행사-003) | 2026-09-27 | Livestream |
| 004 | Arc Acceleration Season / [정리](#행사-004) | 2026-09-22 | Livestream |
| 005 | Arc Microgrants / [정리](#행사-005) | 2026-09-16 | Livestream |
| 006 | Vietnam Office Hours \| Regional Updates & Live Demos / [정리](#행사-006) | 2026-10-08 | Webinar |
| 007 | Bangladesh Office Hours \| Regional Updates & Live Demos / [정리](#행사-007) | 2026-10-08 | Webinar |
| 008 | Da Nang \| Community Meetup \| New Location Kickoff / [정리](#행사-008) | 2026-10-11 | In-Person |
| 009 | Arc Community Co-working / [정리](#행사-009) | 2026-10-12 | In-Person |
| 010 | VNU-HCM \| Campus Meetup \| From Campus to Mainnet: An Giang University / [정리](#행사-010) | 2026-10-17 | In-Person |
| 011 | Encode London Hackathon and Conference / [정리](#행사-011) | 2026-10-23 | In-Person |
| 012 | Arc Demos & Meetup / [정리](#행사-012) | 2026-10-26 | In-Person |
| 013 | Pragma Mumbai / [정리](#행사-013) | 2026-11-05 | In-Person |
| 014 | ETHGlobal Mumbai / [정리](#행사-014) | 2026-11-05 | In-Person |
| 015 | EthGlobal Mumbai / [정리](#행사-015) | 2026-11-05 | In-Person |
| 016 | Pragma Mumbai / [정리](#행사-016) | 2026-11-06 | In-Person |
| 017 | Hyperliquid Community Event 2026 - Builder / [정리](#행사-017) | 2026-10-05 | In-Person |
| 018 | Vietnam Office Hours \| Regional Updates & Live Demos / [정리](#행사-018) | 2026-10-02 | Webinar |
| 019 | Member Check-In \| Regional Updates & Live Demos / [정리](#행사-019) | 2026-10-01 | Meeting |
| 020 | Technical Office Hours / [정리](#행사-020) | 2026-10-01 | Webinar |
| 021 | Dev Days Cafe / [정리](#행사-021) | 2026-09-29 | In-Person |
| 022 | How 1Shot Is Building Embedded Wallets on Arc with Onramp Kit and USDC / [정리](#행사-022) | 2026-09-29 | Livestream |
| 023 | Arc Demos & Meetup / [정리](#행사-023) | 2026-09-28 | In-Person |
| 024 | Bangladesh Build Club \| Explore Arc Studio \| Let's Build on Arc / [정리](#행사-024) | 2026-09-28 | Webinar |
| 025 | Uyo \| Community Meetup \| Agentic Economy on Arc / [정리](#행사-025) | 2026-09-26 | In-Person |
| 026 | Agent Builder Meetup - Orion Tekmer / [정리](#행사-026) | 2026-09-26 | In-Person |
| 027 | The Agentic Economy Prize / [정리](#행사-027) | 2026-05-19 | Livestream |
| 028 | Bangladesh Office Hours \| Regional Updates & Live Demos / [정리](#행사-028) | 2026-09-24 | Webinar |
| 029 | Vietnam Office Hours \| Regional Updates & Live Demos / [정리](#행사-029) | 2026-09-24 | Webinar |
| 030 | Vietnam Office Hours \| Mainnet Celebration , Regional Updates & Live Demos / [정리](#행사-030) | 2026-09-18 | Webinar |
| 031 | AI Infra Summit: Machine Payments Demo / [정리](#행사-031) | 2026-09-15 | In-Person |
| 032 | Building on Arc: A Technical Workshop with Blockradar / [정리](#행사-032) | 2026-09-17 | In-Person |
| 033 | Member Check-In \| Mainnet Celebration , Regional Updates & Live Demos / [정리](#행사-033) | 2026-09-17 | Meeting |
| 034 | Technical Office Hours / [정리](#행사-034) | 2026-09-17 | Webinar |
| 035 | Arc Mainnet launch livestream / [정리](#행사-035) | 2026-09-16 | Livestream |
| 036 | EthOnline 2026 / [정리](#행사-036) | 2026-09-04 | Livestream |
| 037 | Discord Office Hours / [정리](#행사-037) | 2026-09-15 | Livestream |
| 038 | Hanoi \| Campus Meetup \| From Campus to Mainnet II : Phuong Dong University / [정리](#행사-038) | 2026-09-15 | In-Person |
| 039 | Bangladesh Build Club \| Let's Build on Arc / [정리](#행사-039) | 2026-09-14 | Webinar |
| 040 | Vietnam Office Hours \| Regional Updates & Live Demos / [정리](#행사-040) | 2026-09-11 | Webinar |
| 041 | Bangladesh Office Hours \| Regional Updates & Live Demos / [정리](#행사-041) | 2026-09-10 | Webinar |
| 042 | Arc x Aave: Bringing Lending Infrastructure to Arc / [정리](#행사-042) | 2026-09-10 | Livestream |
| 043 | Arc x Wirex: From Crypto Cards to Stablecoin Infrastructure / [정리](#행사-043) | 2026-09-09 | Livestream |
| 044 | Discord Office Hours / [정리](#행사-044) | 2026-09-08 | Livestream |
| 045 | Encode Programmable Money on Arc Demo Day / [정리](#행사-045) | 2026-09-08 | Livestream |
| 046 | Ha Noi \| Community Meetup: Road to Arc Mainnet - Stablecoin Finance & AI Applications 101 / [정리](#행사-046) | 2026-09-06 | In-Person |
| 047 | Buenos Aires \| Arc Builder Circle: Building with Lo-Fi Pomodor & arc_fajores 🍪 / [정리](#행사-047) | 2026-09-05 | In-Person |
| 048 | Lagos \| Community Meetup \| Circle Agent Stack / [정리](#행사-048) | 2026-09-05 | In-Person |
| 049 | Vietnam Office Hours \| Regional Updates & Live Demos / [정리](#행사-049) | 2026-09-04 | Webinar |
| 050 | Member Check-In \| Regional Updates & Live Demos / [정리](#행사-050) | 2026-09-03 | Meeting |
| 051 | Arc x Morpho: Midnight and Fixed-Rate Lending Onchain / [정리](#행사-051) | 2026-09-03 | Livestream |
| 052 | Technical Office Hours / [정리](#행사-052) | 2026-09-03 | Webinar |
| 053 | Discord Office Hours / [정리](#행사-053) | 2026-09-01 | Livestream |
| 054 | Bangladesh Build Club \| Let's Build on Arc / [정리](#행사-054) | 2026-08-31 | Webinar |
| 055 | Uyo \| Community Meetup \| Building Your First Stablecoin Payment Flow / [정리](#행사-055) | 2026-08-29 | In-Person |
| 056 | Abuja \| Community Meetup \| Kickoff / [정리](#행사-056) | 2026-08-29 | In-Person |
| 057 | Vietnam Office Hours \| Regional Updates & Live Demos / [정리](#행사-057) | 2026-08-28 | Webinar |
| 058 | Building the Agentic Economy with Fireblocks, Circle & Blockrun / [정리](#행사-058) | 2026-08-27 | In-Person |
| 059 | Bangladesh Office Hours \| Regional Updates & Live Demos / [정리](#행사-059) | 2026-08-27 | Webinar |
| 060 | Arc x Chainlink: Data and Interoperability for Financial Applications / [정리](#행사-060) | 2026-08-27 | Livestream |
| 061 | Discord Office Hours / [정리](#행사-061) | 2026-08-25 | Livestream |
| 062 | Hackathon: Programmable Money / [정리](#행사-062) | 2026-07-13 | Livestream |
| 063 | Ankara: Community Meetup / [정리](#행사-063) | 2026-08-22 | In-Person |
| 064 | Enugu Community Meetup \| Nsukka Build Club / [정리](#행사-064) | 2026-08-22 | In-Person |
| 065 | Member Check-In \| Regional Updates & Live Demos / [정리](#행사-065) | 2026-08-20 | Meeting |
| 066 | Vietnam Office Hours \| Regional Updates & Live Demos / [정리](#행사-066) | 2026-08-20 | Webinar |
| 067 | Technical Office Hours / [정리](#행사-067) | 2026-08-20 | Webinar |
| 068 | Discord Office Hours / [정리](#행사-068) | 2026-08-18 | Livestream |
| 069 | Arc Coworking & Demos / [정리](#행사-069) | 2026-08-17 | In-Person |
| 070 | HCMC \| Community Meetup & New Location Kickoff: The Stablecoin Movement / [정리](#행사-070) | 2026-08-16 | In-Person |
| 071 | Buenos Aires \| Arc Builder Circle: Building with Lo-Fi & arc_fajores 🍪 / [정리](#행사-071) | 2026-08-15 | In-Person |
| 072 | HCMC \| Campus Meetup \| University Tour Kickoff: Van Lang University / [정리](#행사-072) | 2026-08-15 | In-Person |
| 073 | Bangladesh Office Hours \| Regional Updates & Live Demos / [정리](#행사-073) | 2026-08-13 | Webinar |
| 074 | Vietnam Office Hours \| Regional Updates & Live Demos / [정리](#행사-074) | 2026-08-13 | Webinar |
| 075 | Discord Office Hours / [정리](#행사-075) | 2026-08-11 | Livestream |
| 076 | Circle: From Demo to Deployed - Building a Paying Agent Live / [정리](#행사-076) | 2026-08-10 | Livestream |
| 077 | Hackathon: The Stablecoins Commerce Stack Challenge / [정리](#행사-077) | 2026-04-14 | Hybrid |
| 078 | Region Updates: Brasil Roundtable Discussion / [정리](#행사-078) | 2026-08-07 | Meeting |
| 079 | Buenos Aires \| Dev3Pack - Robotics Developer Meetup & Machine Economy 101 / [정리](#행사-079) | 2026-08-07 | In-Person |
| 080 | Vietnam Office Hours \| Regional Updates & Live Demos / [정리](#행사-080) | 2026-08-06 | Webinar |
| 081 | Member Check-In \| Regional Updates & Live Demos / [정리](#행사-081) | 2026-08-04 | Meeting |
| 082 | Ilorin \| Community Meetup \| Building Your First Stablecoin Payment Flow / [정리](#행사-082) | 2026-08-01 | In-Person |
| 083 | Rio \| Builders Sunset Meetup \| Region Event Mixer / [정리](#행사-083) | 2026-07-31 | In-Person |
| 084 | Vietnam Office Hours \| Regional Updates & Live Demos / [정리](#행사-084) | 2026-07-30 | Webinar |
| 085 | Agent Builder Meetup / [정리](#행사-085) | 2026-07-30 | In-Person |
| 086 | Agentic Economy Meetup: How AI Agents Pay With AgentCash and USDC / [정리](#행사-086) | 2026-07-29 | In-Person |
| 087 | Arc Builder Spotlight: AIsa - Agentic APIs and Nanopayments / [정리](#행사-087) | 2026-07-29 | Livestream |
| 088 | The Agentic Economy: Payments, Agents, & Privacy / [정리](#행사-088) | 2026-07-29 | In-Person |
| 089 | Arc Discord Office Hours / [정리](#행사-089) | 2026-07-28 | Livestream |
| 090 | Region Kickoff: Bangladesh Roundtable Discussion / [정리](#행사-090) | 2026-07-28 | Meeting |
| 091 | Buenos Aires \| Community Breakfast Meetup \| Stablecoins in Argentina / [정리](#행사-091) | 2026-07-25 | In-Person |
| 092 | Lagos \| Community Meetup \| Stablecoin Breakfast / [정리](#행사-092) | 2026-07-25 | In-Person |
| 093 | Enugu \| Community Meetup \| New Location Kickoff / [정리](#행사-093) | 2026-07-25 | In-Person |
| 094 | Arc Builder Spotlight: Pulsar - Consumer Stablecoin Money on Arc / [정리](#행사-094) | 2026-07-24 | Livestream |
| 095 | Vietnam Office Hours \| Regional Updates & Live Demos / [정리](#행사-095) | 2026-07-23 | Meeting |
| 096 | Lisbon \| Community Meetup \| Builder Afterwork / [정리](#행사-096) | 2026-07-22 | In-Person |
| 097 | Arc Discord Office Hours / [정리](#행사-097) | 2026-07-21 | Livestream |
| 098 | Building on Arc: Open-Source Resources from the Canteen x Arc Hackathon Series / [정리](#행사-098) | 2026-07-16 | Livestream |
| 099 | Arc Discord Office Hours / [정리](#행사-099) | 2026-07-14 | Livestream |
| 100 | Programmable Money on Arc Bootcamp / [정리](#행사-100) | 2026-06-22 | Livestream |
| 101 | Arc x Canteen: Agora Hackathon Builder Spotlight / [정리](#행사-101) | 2026-07-09 | Livestream |
| 102 | Arc Discord Office Hours / [정리](#행사-102) | 2026-07-07 | Livestream |
| 103 | Builder Breakfast Meetup: How USDC & EURC Are Redefining Payments / [정리](#행사-103) | 2026-07-06 | In-Person |
| 104 | AI Engineer World's Fair / [정리](#행사-104) | 2026-06-29 | In-Person |
| 105 | İstanbul \| Arc Community Meetup with e2vc / [정리](#행사-105) | 2026-07-01 | In-Person |
| 106 | Arc Discord Office Hours / [정리](#행사-106) | 2026-06-30 | Livestream |
| 107 | Hackathon: Lepton Agents / [정리](#행사-107) | 2026-06-15 | Hybrid |
| 108 | Lagos \| Community Meetup \| Region Kickoff Mixer / [정리](#행사-108) | 2026-06-26 | In-Person |
| 109 | Region Kickoff: Brasil Roundtable Discussion / [정리](#행사-109) | 2026-06-26 | Meeting |
| 110 | Privacy on Arc: What Builders Should Know / [정리](#행사-110) | 2026-06-25 | Livestream |
| 111 | Teresina \| Community Meetup \| Builder Kickoff / [정리](#행사-111) | 2026-06-23 | In-Person |
| 112 | Arc Discord Office Hours / [정리](#행사-112) | 2026-06-23 | Livestream |
| 113 | Rio \| Community Meetup \| Region Kickoff Mixer / [정리](#행사-113) | 2026-06-22 | In-Person |
| 114 | Arc Discord Office Hours / [정리](#행사-114) | 2026-06-16 | Livestream |
| 115 | Hackathon: ETHGlobal New York 2026 / [정리](#행사-115) | 2026-06-12 | In-Person |
| 116 | The Bored Room / [정리](#행사-116) | 2026-06-09 | Livestream |
| 117 | Arc Discord Office Hours / [정리](#행사-117) | 2026-06-09 | Livestream |
| 118 | Arc Discord Office Hours / [정리](#행사-118) | 2026-06-02 | Livestream |
| 119 | Agentic Demo Day: AI Projects Built on Arc / [정리](#행사-119) | 2026-05-28 | Livestream |
| 120 | Arc Builder Spotlight: TLAY - Machine-to-Machine Nanopayments on Arc / [정리](#행사-120) | 2026-05-27 | Livestream |
| 121 | Arc Discord Office Hours / [정리](#행사-121) | 2026-05-26 | Livestream |
| 122 | Circle Developer Grants: Building on Arc and the Circle Developer Platform / [정리](#행사-122) | 2026-05-22 | Livestream |
| 123 | Arc Builder Spotlight: Tower Exchange - Native Stablecoin DEX Aggregation on Arc / [정리](#행사-123) | 2026-05-21 | Livestream |
| 124 | Builder Spotlight: Synthra - Spot, Concentrated Liquidity, and Perpetual Markets on Arc / [정리](#행사-124) | 2026-05-20 | Livestream |
| 125 | Arc Discord Office Hours / [정리](#행사-125) | 2026-05-19 | Livestream |
| 126 | Arc Discord Office Hours / [정리](#행사-126) | 2026-05-12 | Livestream |
| 127 | Arc Enterprise & DeFi Hackathon Spotlight: Chariot - Crosschain Collateral Lending Protocol on Arc / [정리](#행사-127) | 2026-05-07 | Livestream |
| 128 | Setting Up Your Full Agentic Stack With Circle: Consensus 2026 Workshop / [정리](#행사-128) | 2026-05-06 | In-Person |
| 129 | AWS + Circle Present: Agentic Nanopayments at Consensus 2026 / [정리](#행사-129) | 2026-05-05 | In-Person |
| 130 | How To Set Up Stablecoin Wallet & Dashboard for Your Business With Circle / [정리](#행사-130) | 2026-05-05 | In-Person |
| 131 | Arc Discord Office Hours / [정리](#행사-131) | 2026-05-05 | Livestream |
| 132 | ArcShop with Elton: Unified Balance Kit for Crosschain USDC Flows / [정리](#행사-132) | 2026-05-01 | Livestream |
| 133 | Arc Enterprise & DeFi Hackathon Spotlight: Crumb - Gasless USDC Nanopayments and settlement on Arc / [정리](#행사-133) | 2026-04-29 | Livestream |
| 134 | ArcShop with HJ: Understanding Gateway - Building Chain Agnostic Apps with Gateway & Circle Wallets / [정리](#행사-134) | 2026-04-28 | Livestream |
| 135 | Agentic Economy on Arc Hackathon / [정리](#행사-135) | 2026-04-20 | Hybrid |
| 136 | Agentic Economy on Arc Hackathon (IRL component) / [정리](#행사-136) | 2026-04-25 | In-Person |
| 137 | Arc Discord Office Hours / [정리](#행사-137) | 2026-04-21 | Livestream |
| 138 | Arc Enterprise & DeFi Hackathon Spotlight: Blink Nanopayment Insurance / [정리](#행사-138) | 2026-04-20 | Livestream |
| 139 | App Kits Developer Office Hours: Bridge, Swap, Send, and Monetization / [정리](#행사-139) | 2026-04-17 | Livestream |
| 140 | Building the Agentic Economy on Arc: VibeCard / [정리](#행사-140) | 2026-04-15 | Livestream |
| 141 | Arc Discord Office Hours / [정리](#행사-141) | 2026-04-14 | Livestream |
| 142 | Arc House Office Hours / [정리](#행사-142) | 2026-04-07 | Webinar |
| 143 | ETHGlobal Cannes Hackathon / [정리](#행사-143) | 2026-04-03 | In-Person |
| 144 | Introducing Arc House and Architects / [정리](#행사-144) | 2026-04-02 | Livestream |
| 145 | ETHGlobal Pragma / [정리](#행사-145) | 2026-04-02 | In-Person |
| 146 | Building an Agentic Economy on Arc with RSoft Agentic Bank / [정리](#행사-146) | 2026-04-01 | Livestream |
| 147 | Arc Discord Office Hours / [정리](#행사-147) | 2026-03-31 | Livestream |
| 148 | Arc Community Spotlight: Social Payments with USDC Powered by XyloNet & PayX / [정리](#행사-148) | 2026-03-26 | Livestream |
| 149 | Agentic Economy on Arc Hackathon Kickoff Stream / [정리](#행사-149) | 2026-03-25 | Livestream |
| 150 | Arc Discord Office Hours / [정리](#행사-150) | 2026-03-24 | Livestream |
| 151 | USDC OpenClaw Hackathon Winner Spotlight: ClawRouter by BlockRunAI / [정리](#행사-151) | 2026-03-19 | Livestream |
| 152 | Arc Discord Office Hours / [정리](#행사-152) | 2026-03-17 | Livestream |
| 153 | Build with Circle Nanopayments: Agentic Payments, Usage‑Based Billing, and Streaming Value / [정리](#행사-153) | 2026-03-12 | Livestream |
| 154 | Arc Discord Architecture Review (Design Clinic) / [정리](#행사-154) | 2026-03-11 | Livestream |
| 155 | Arc Discord Office Hours / [정리](#행사-155) | 2026-03-10 | Livestream |
| 156 | Arc Discord Show and Tell (Lightning Demos) / [정리](#행사-156) | 2026-03-05 | Livestream |
| 157 | Arc Discord Office Hours / [정리](#행사-157) | 2026-03-03 | Livestream |
| 158 | Arc x Encode Enterprise & DeFi Hackathon / [정리](#행사-158) | 2026-02-27 | In-Person |
| 159 | Arc Discord Office Hours / [정리](#행사-159) | 2026-02-24 | Livestream |
| 160 | Arc Side Quest at ETHDenver / [정리](#행사-160) | 2026-02-19 | In-Person |
| 161 | Arc Meetup London - Presented by Encode Club / [정리](#행사-161) | 2026-02-12 | In-Person |
| 162 | ETHGlobal Hack Money DeFi Hackathon / [정리](#행사-162) | 2026-01-30 | Livestream |
| 163 | OpenClaw USDC Hackathon on Moltbooks / [정리](#행사-163) | 2026-02-04 | Hybrid |
| 164 | Day One Architect: Para / [정리](#행사-164) | 2026-02-05 | Livestream |
| 165 | Agentic Commerce on Arc Hackathon Hosted by LabLab.ai / [정리](#행사-165) | 2026-01-09 | Hybrid |
| 166 | Arc Meetup San Francisco - Presented by Thirdweb / [정리](#행사-166) | 2026-01-16 | In-Person |
| 167 | Technical Insights on Arc Testnet Reliability / [정리](#행사-167) | 2025-12-19 | Livestream |
| 168 | Crosschain Payments with CCTP Fast Transfer / [정리](#행사-168) | 2025-12-15 | Livestream |
| 169 | Day One Architect: Hinkal / [정리](#행사-169) | 2025-12-12 | Livestream |
| 170 | Arcshop; Gateway with Blockradar / [정리](#행사-170) | 2025-12-11 | Livestream |
| 171 | Event Replay: Arcshop- Introducing Bridge Kit / [정리](#행사-171) | 2025-12-10 | Livestream |
| 172 | Day One Architect: Crossmint / [정리](#행사-172) | 2025-12-05 | Livestream |
| 173 | Trustless USDC Agents on Arc / [정리](#행사-173) | 2025-12-03 | Livestream |
| 174 | Arc Studio: Buenos Aires / [정리](#행사-174) | 2025-11-19 | In-Person |
| 175 | Encode x Arc DeFi Hackathon / [정리](#행사-175) | 2025-11-14 | In-Person |
| 176 | Day One Architect Highlight: Blockradar / [정리](#행사-176) | 2025-11-13 | Webinar |
| 177 | Welcome to the Arc Community Hub / [정리](#행사-177) | 2025-11-04 | Webinar |
| 178 | ArcTalk: Finality You Can Count On / [정리](#행사-178) | 2025-10-30 | Livestream |

## 행사별 내용

### 행사 001

> Sui Basecamp 2026 [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/sui-basecamp-2026-qiop8e2sdd)

페이지 일정 필드(UTC)는 2026-10-07T13:00:00.573Z부터 2026-10-08T21:00:00.573Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Marina Bay Sands / Singapore [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- AI 에이전트 금융에 필요한 기반을 논의합니다. lines:7-7

- 즉시 정산, 자율 결제, 비공개 거래, 안정적인 디지털 달러, 양자 컴퓨터 이후의 보안과 이동 가능한 메모리를 주제로 제시합니다. lines:9-9

- HJ Chen이 참여하는 AI 중심 개발자 워크숍입니다. lines:10-10

- 15:30-16:30의 Agent-Ready USDC 세션은 CCTP를 활용한 개발을 다룹니다. lines:12-12

- 대면 장소는 Singapore의 Marina Bay Sands입니다. lines:32-35

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> HJ Chen / Senior Manager, Developer Relations and Ecosystem Marketing / Circle [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://www.sui.io/basecamp#overview / 한국어 정리

### 행사 002

> Circle House @ TOKEN2049 Singapore 🇸🇬 [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/circle-house-token2049-singapore-n4m035ioej)

페이지 일정 필드(UTC)는 2026-10-07T01:30:00.366Z부터 2026-10-08T09:30:00.366Z까지이며 표시 시간대는 Asia/Singapore이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Marina Bay Sands / Level 3 / Singapore [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Arc, USDC와 온체인 금융의 미래를 중심으로 이틀간 진행하며 개발자와 AI 에이전트 경제에 관심 있는 사람이 Circle 팀과 만나도록 안내합니다. lines:12-12

- Circle 팀의 Arc 및 USDC 실시간 데모와 Circle 인프라를 활용하는 생태계 파트너 세션이 있습니다. lines:16-17

- Circle Challenge를 완료하면 Chelsea FC x USDC by Circle 상품을 받을 수 있고 웰니스 음료를 제공합니다. lines:18-19

- Level 3 입장에는 TOKEN2049 패스가 필요하지 않지만 모든 참가자는 Luma 등록 후 QR 코드 티켓을 받아 체크인해야 합니다. lines:23-23

- 등록 한 건은 한 사람의 단일 입장에만 유효하며 QR 코드 티켓은 양도할 수 없고 입구에서 스캔합니다. lines:25-25

- Level 3에 올라가기 전 Level 1에서 필수 보안 및 가방 검색을 받으므로 추가 시간을 확보하도록 안내합니다. lines:27-27

- 10월 7일 10:30-11:30에는 Elton의 Agent Stack, 13:00-14:00에는 HJ의 App Kit 세션을 진행합니다. lines:30-32

- 10월 8일 10:30-11:30에는 HJ의 App Kit, 16:00-17:00에는 Elton의 Agent Stack 세션을 진행합니다. lines:34-36

- 본문의 운영 시간은 10월 7-8일 매일 09:30-17:00 SGT이며 장소는 Marina Bay Sands Level 3입니다. lines:7-8

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Elton Tay / DevRel Lead, APAC / Circle [원문 그대로]

> HJ Chen / Senior Manager, Developer Relations and Ecosystem Marketing / Circle [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문은 lines:7에 종료 17:00 SGT를 표기하지만 endedAt은 lines:44의 2026-10-08T09:30:00.366Z입니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/circlehouse2026 / 한국어 정리

### 행사 003

> Tameion Agents Hackathon [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/tameion-agents-hackathon-jb1w9clwx7)

페이지 일정 필드(UTC)는 2026-09-27T04:00:00.534Z부터 2026-10-10T04:00:00.534Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

현재 공개 이벤트 객체의 설명 본문은 비어 있다. 아래 일정과 티켓 값으로 세부 과제나 제출 요건을 추정하지 않았다. 주최자 안내는 연결자료 정리에 별도로 기록했다.

- 공개 태그에는 Hackathon, AI Hackathon, AI, Agent Stack과 Agentic Economy가 있습니다. lines:63-79

- 이전 판본의 registrationUrl은 null이고 topics는 빈 배열입니다. lines:101-102

- 공개 메타데이터는 시작 2026-09-27T04:00:00.534Z, 종료 2026-10-10T04:00:00.534Z, 시간대 America/New_York를 기록합니다. lines:14-16

- 공개 티켓은 Free Ticket이며 표시 가격은 0입니다. lines:52-52

- 온라인 여부는 true이고 초대 전용 여부는 false입니다. lines:19-21

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 현재 설명은 lines:7에 [No description]이며 이전 판본의 Description도 lines:128-130에 본문이 비어 있습니다. 제목과 태그만으로 상금, 제출 요건이나 세부 과제를 설명할 수 없습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://tameion.thecanteenapp.com/ / 한국어 정리
- https://luma.com/ivroypr5 / 한국어 정리
- https://forms.gle/BBWrdfuircrKiG2i6 / 한국어 정리

### 행사 004

> Arc Acceleration Season [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-acceleration-season-vanemu91dk)

페이지 일정 필드(UTC)는 2026-09-22T04:00:00.268Z부터 2026-10-24T04:00:00.268Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 결제, 외환, 신용과 토큰화 자산을 온체인 금융 사례로 제시합니다. lines:7-7

- 중남미 핀테크와 AI 스타트업을 위한 6주 온라인 프로그램이며 지원 마감은 9월 22일입니다. lines:9-9

- 통합 범위를 정하고 개발하여 출시한 뒤 투자자와 생태계 관계자 앞에서 Demo Day 발표를 합니다. 실적 있는 실제 사업들이 무대에 참여한다고 설명합니다. lines:15-17

- Arc와 Circle 팀이 직접 지원하며 첫 주에는 기술팀 상담, 사업 목표와 통합 범위 설정, 팀 소개를 진행합니다. lines:17-21

- 2-3주차에는 App Kits, Gateway와 StableFX로 테스트넷 프로토타입을 개발하고 주간 기술 상담 및 비동기 지원을 받습니다. lines:23-23

- 4-5주차에는 메인넷에 배포하고 성능, 비용과 예외 상황을 점검하며 첫 고객과 시장 진입 방안을 구체화합니다. lines:25-25

- 6주차에는 발표와 데모를 다듬어 온라인 Demo Day에서 출시 결과와 성장 계획을 보여 줍니다. lines:27-27

- Airtable 양식으로 지원하도록 안내합니다. lines:29-29

- 공개 메타데이터는 시작 2026-09-22T04:00:00.268Z, 종료 2026-10-24T04:00:00.268Z, 시간대 America/New_York를 기록합니다. lines:36-38

- 공개 티켓은 Free Ticket이며 표시 가격은 0입니다. lines:75-75

- 온라인 여부는 true이고 초대 전용 여부는 false입니다. lines:41-43

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문은 6주 프로그램이라고 하지만 메타데이터는 lines:36-37에 시작 2026-09-22와 종료 2026-10-24를 기록합니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://airtable.com/appGGpgjSlDjntK7k/pagAoXwWYkoVVGbuB/form / 한국어 정리
- https://t.co/o7A0HNYx5J / 한국어 정리

### 행사 005

> Arc Microgrants [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-microgrants-f8tijfjhyq)

페이지 일정 필드(UTC)는 2026-09-16T13:00:00.321Z부터 2026-10-15T03:59:00.321Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 라이브 방송이 아니라 보조금 프로그램이며 Register를 눌러 신청하도록 안내합니다. lines:7-7

- 총 10,000 USDC에서 500 USDC씩 20건을 지원하며 메인넷의 작동하는 초기 제작물을 대상으로 합니다. lines:11-11

- 신청 전에 메인넷에 배포되어 작동해야 하고 사전 약정이나 후속 보고는 없다고 설명합니다. 배포와 거래에는 가스비를 낼 소량의 USDC가 필요합니다. lines:17-19

- 작은 앱, 개념 증명, 프로토타입, 데모, 해커톤 후속 개발, 실험적 인프라와 초기 기술 실험을 지원합니다. lines:23-23

- 이용 실적, 회사, 발표 자료와 로드맵은 필요하지 않으며 작동하는 제작물이 필요합니다. lines:25-25

- 개인 개발자, 학생 팀, 해커톤 팀, 첫 창업자, 초기 인프라 개발자와 Arc 사용 사례를 개발하는 기술 팀을 대상으로 하며 깊은 암호화폐 경험은 필요하지 않습니다. lines:29-31

- 지분 희석 없는 500 USDC, 기술 지도, 개발 상담, 커뮤니티 노출, 소개와 Circle Grant Program 등 후속 지원 경로를 제공합니다. lines:35-45

- 메인넷 배포 후 실서비스와 저장소 링크를 제출하고 완전성 및 적합성 검토를 받습니다. 최종 후보는 점수화하여 묶음으로 결정하고 선정 후 지급을 위한 검증을 거칩니다. lines:49-59

- 접수는 2026-10-14 23:59 ET에 끝나며 순차 검토하고 모든 결정은 10월 21일까지 발표한다고 안내합니다. lines:61-61

- 열 수 있는 메인넷 배포 링크, 공개 저장소, 기능과 Arc 사용 목적의 짧은 설명, GitHub 또는 X 또는 Farcaster의 공개 프로필이 필요합니다. lines:65-71

- 디자인 목업, 슬라이드, 테스트넷만 사용하는 결과물, Arc 요소 없는 프로젝트와 Circle 또는 Arc가 이미 지원한 작업은 제외합니다. lines:73-73

- Arc 관련성, 기술적 신뢰성, 제작 품질과 후속 개발 가능성을 평가하며 이용 실적보다 가능성을 중시합니다. 더 진행된 프로젝트도 제출하면 알맞은 프로그램으로 안내합니다. lines:77-81

- 전 세계 개인과 팀을 대상으로 하지만 제재와 제한 관할 지역 심사를 적용합니다. 가명 신청은 가능하고 조건부 선정 후 수령자만 비공개 검증을 받습니다. 프로젝트마다 한 번 신청하며 서로 다른 프로젝트는 복수 신청할 수 있습니다. lines:85-89

- 신청 시점에 메인넷에서 작동해야 하며 해커톤 프로젝트도 가능합니다. 자신의 작업이거나 제출 권리가 있어야 하고 Arc USDC를 받을 지갑이 필요합니다. lines:91-97

- 소유권을 유지하며 지분 제공, 지식재산 이전과 독점 조건은 없습니다. 일정과 지급 건수는 조정될 수 있습니다. lines:99-101

- 면책 안내: 운영 주체, 규제 승인 부재, 네트워크 위험과 기능 변경 가능성에 관한 부분은 면책 문구입니다. lines:121-121

- 공개 메타데이터는 시작 2026-09-16T13:00:00.321Z, 종료 2026-10-15T03:59:00.321Z, 시간대 America/New_York를 기록합니다. lines:128-130

- 공개 티켓은 Free Ticket이며 표시 가격은 0입니다. lines:167-167

- 온라인 여부는 true이고 초대 전용 여부는 false입니다. lines:133-135

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- [연결 주소](https://dorahacks.io/hackathon/arc-microgrants)는 이번 요청에서 HTTP 403로 본문을 확보하지 못했다.

### 행사 006

> Vietnam Office Hours | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/vietnam-office-hours-or-regional-updates-and-live-demos-tpptiqh1f5)

페이지 일정 필드(UTC)는 2026-10-08T14:15:55.000Z부터 2026-10-08T15:15:55.000Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 베트남 지역 모임 회원들이 매주 지역 개발자들과 만나고 Arc 개발 소식을 공유하는 토론입니다. lines:7-7

- 기술적 피드백을 교환하고 생태계 기회를 논의하며 지역 개발자 커뮤니티를 강화합니다. lines:7-7

- 공개 메타데이터는 시작 2026-10-08T14:15:55.000Z, 종료 2026-10-08T15:15:55.000Z, 시간대 Asia/Saigon를 기록합니다. lines:14-16

- 공개 티켓은 Free Ticket이며 표시 가격은 0입니다. lines:105-105

- 온라인 여부는 true이고 초대 전용 여부는 false입니다. lines:19-21

- 발표자 목록은 Lecter  Vu의 직함을 Founder, 소속을 Vitael로 기록합니다. lines:33-35

- 발표자 목록은 Teddy Dinh의 직함을 Moderator, 소속을 Architect로 기록합니다. lines:43-45

- 발표자 목록은 Anh Dang의 직함을 Founder, 소속을 Amonix로 기록합니다. lines:53-55

- 발표자 목록은 Bao Bao의 직함을 Founder, 소속을 Myarbiter로 기록합니다. lines:63-65

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Lecter  Vu / Founder / Vitael [원문 그대로]

> Teddy Dinh / Moderator / Architect [원문 그대로]

> Anh Dang / Founder / Amonix [원문 그대로]

> Bao Bao / Founder / Myarbiter [원문 그대로]

### 행사 007

> Bangladesh Office Hours | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/bangledesh/events/bangladesh-office-hours-or-regional-updates-and-live-demos-llm482j4on)

페이지 일정 필드(UTC)는 2026-10-08T15:00:27.000Z부터 2026-10-08T15:59:27.000Z까지이며 표시 시간대는 Asia/Dhaka이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 방글라데시 지역 모임 회원을 위한 격주 커뮤니티 토론입니다. lines:11-11

- 지역 개발자와 만나고 Arc 개발 프로젝트 소식을 공유하며 기술 의견을 교환합니다. lines:11-11

- 생태계 기회와 혜택을 논의하고 지역 개발자 커뮤니티를 강화합니다. lines:11-11

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Sukanto Das / Co-Founder / Ababil Pay [원문 그대로]

> Motaleb Hossain / BD / Achswap [원문 그대로]

> Shah  Jahan / Creator & Founder / ArcFlow Finance [원문 그대로]

> Yasin Ahmed / Builder & Founder / Accordpay [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- startedAt은 lines:18에 10월 8일이고 days 구간은 lines:90-91에 10월 6-7일로 기록되어 있습니다.

### 행사 008

> Da Nang | Community Meetup | New Location Kickoff [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/da-nang-or-community-meetup-or-new-location-kickoff-gzmlbfuzcd)

페이지 일정 필드(UTC)는 2026-10-11T02:00:00.499Z부터 2026-10-11T05:00:39.175Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> 10 Tran Quy Cap Street, Thach Thang Ward, Hai Chau District, Da Nang, Vietnam / 10 Tran Quy Cap Street, Thach Thang Ward, Hai Chau District, Da Nang, Vietnam / Da Nang  / Hai Chau / Việt Nam [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Arc Vietnam이 다낭으로 활동 범위를 넓히며 첫 지역 모임을 개최합니다. lines:7-8

- 지역 개발자, 창업자와 웹3에 관심 있는 사람들이 만나 배우고 Arc 개발 가능성을 탐구합니다. lines:8-8

- 메인넷 출시 이후 실제 제품의 개발과 배포를 강조합니다. lines:10-10

- Arc 생태계, 개발자 기회와 베트남 커뮤니티의 작업 내용을 공유하고 차세대 Arc 앱 개발에 관심 있는 사람들과 교류합니다. lines:12-12

- 기존 웹3 개발자, Arc 입문자와 새로운 개발 생태계를 찾는 사람 모두를 대상으로 합니다. lines:14-14

- 대면 주소는 다낭 Hai Chau District의 10 Tran Quy Cap Street입니다. lines:34-35

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Kien Trinh / Founder / HushCash [원문 그대로]

### 행사 009

> Arc Community Co-working [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-community-co-working-4701o1wgy4)

페이지 일정 필드(UTC)는 2026-10-12T08:00:00.321Z부터 2026-10-12T17:00:43.665Z까지이며 표시 시간대는 Europe/London이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Encode hub / london / uk [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 런던의 개발자, 창업자와 운영 담당자가 Encode Hub Shoreditch에서 함께 작업하고 다른 참가자를 만나는 모임입니다. lines:7-7

- 공동 작업, 대화, 소개와 피드백을 중심으로 진행합니다. lines:9-9

- 결제, 스테이블코인, 프로그래밍 가능한 자금과 금융 인프라를 탐구하는 사람들에게 초점을 맞춥니다. lines:9-9

- 등록은 Luma 페이지로 연결합니다. lines:24-24

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문 lines:7-9는 저녁 모임이라고 설명하지만 startedAt은 lines:16에 2026-10-12T08:00:00.321Z로 기록되어 있습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- [연결 주소](https://luma.com/encode-6tv5)는 이번 요청에서 HTTP 403로 본문을 확보하지 못했다.

### 행사 010

> VNU-HCM | Campus Meetup | From Campus to Mainnet: An Giang University [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/vnu-hcm-or-campus-meetup-or-from-campus-to-mainnet-an-giang-university-lyzskvagac)

페이지 일정 필드(UTC)는 2026-10-17T02:00:00.817Z부터 2026-10-17T05:00:37.887Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> 18 Ung Van Khiem Street, Long Xuyen, An Giang, Vietnam / 18 Ung Van Khiem Street, Long Xuyen, An Giang, Vietnam / An Giang / Long Xuyen / Việt Nam [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- An Giang University는 Long Xuyen에 있으며 Vietnam National University Ho Chi Minh City 소속 공립 대학이라고 소개합니다. lines:7-7

- 학생들이 캠퍼스에서 온체인 개발을 시작하도록 돕는 모임입니다. lines:9-9

- Arc, 스테이블코인 인프라, 온체인 앱과 생태계 개발 기회를 소개합니다. lines:9-9

- 기초를 배우고 메인넷에서 개발 및 배포할 수 있는 결과물을 탐구합니다. lines:9-9

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Tran Hoan / Builder  / Blockhay [원문 그대로]

### 행사 011

> Encode London Hackathon and Conference [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/encode-london-hackathon-and-conference-znntsye2lf)

페이지 일정 필드(UTC)는 2026-10-23T09:00:00.131Z부터 2026-10-23T21:59:02.181Z까지이며 표시 시간대는 Europe/London이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Encode hub / london / UK [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 개발자, 창업자, 연구자, 학생과 혁신가를 위한 AI 및 웹3 행사입니다. lines:7-7

- 해커톤과 강연 및 토론의 두 가지 프로그램을 함께 운영합니다. lines:7-7

- 팀이 AI 및 웹3 주제로 3일간 프로젝트를 개발하고 심사위원에게 결과물을 보여 줍니다. lines:13-13

- 개발 과제, 상금과 멘토링을 제공한다고 예고합니다. lines:13-13

- 토요일 컨퍼런스에서는 AI 및 웹3의 최신 동향, 강연, 기술 설명과 개발자, 연구자 및 업계 관계자 대화를 진행합니다. lines:19-21

- 기술 및 창작 부문의 주제는 AI, 암호화폐와 탈중앙화 시스템의 새로운 아이디어를 탐구하도록 설계하며 추후 공개합니다. lines:25-25

- 개막, 워크숍, 컨퍼런스, 심사와 폐막 일정 및 파트너, 상금과 심사위원은 추후 공개합니다. lines:29-33

- 장소는 Shoreditch의 AI 및 웹3 개발 커뮤니티 공간 Encode Hub입니다. lines:35-37

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문 lines:13은 3일 행사로 설명하지만 startedAt과 endedAt은 lines:44-45에 모두 10월 23일로 기록합니다. 세부 주제, 상금 부문과 일정은 추후 공개 상태입니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- http://hub.encode.club/?utm_source=luma / 한국어 정리
- https://luma.com/encode-london-2026 / 한국어 정리

### 행사 012

> Arc Demos & Meetup [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-demos-and-meetup-jqvzbx8dts)

페이지 일정 필드(UTC)는 2026-10-26T18:30:00.567Z부터 2026-10-26T20:00:02.312Z까지이며 표시 시간대는 Europe/London이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Encode Hub / London / UK [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 개발 진척과 유망 팀을 소개하며 실제 결과물을 보여 주는 마무리 커뮤니티 모임입니다. lines:7-7

- 짧은 데모와 대화를 통해 개발 결과, 이용 실적과 커뮤니티의 개발자를 살펴봅니다. lines:9-9

- 결제, 프로그래밍 가능한 자금, 스테이블코인과 금융 인프라에 관심 있는 참가자를 대상으로 합니다. lines:9-9

- 장소는 Shoreditch의 Encode Hub입니다. lines:7-7

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- [연결 주소](https://luma.com/encode-dfpo)는 이번 요청에서 HTTP 403로 본문을 확보하지 못했다.

### 행사 013

> Pragma Mumbai [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/pragma-mumbai-ost0nlf8ti)

페이지 일정 필드(UTC)는 2026-11-05T05:00:00.974Z부터 2026-11-06T04:53:30.361Z까지이며 표시 시간대는 Etc/GMT+5이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Grand Hyatt Mumbai  / Bandra Kurla Complex, Siddharath Nagar, Vakola, Vicinity, Mumbai, Maharashtra 400055, India / Mumbai / India [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 웹3 개발자와 관계자를 위한 정상급 모임으로 소개합니다. lines:7-7

- 소수의 창업자와 개발자가 웹3의 미래를 논의하고 과거를 돌아봅니다. lines:11-11

- 병렬 세션 없이 초청 참가자, 주요 창업자, 선별한 콘텐츠, 초보자 친화적 구성과 소규모 대화를 제시합니다. lines:13-23

- 본문은 초대 전용이라고 안내합니다. lines:15-15

- 대면 장소는 India Mumbai의 Grand Hyatt Mumbai입니다. lines:43-46

- 공개 메타데이터에서는 행사와 전체 티켓의 초대 전용 여부를 모두 false로 기록합니다. lines:36-37

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문 lines:15는 Invite only이지만 메타데이터 lines:36-37과 티켓 lines:71은 초대 전용 false입니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- [연결 주소](https://ethglobal.com/events/pragma-mumbai)는 이번 요청에서 HTTP 403로 본문을 확보하지 못했다.

### 행사 014

> ETHGlobal Mumbai [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/ethglobal-mumbai-g23qyrr90e)

페이지 일정 필드(UTC)는 2026-11-05T15:00:00.759Z부터 2026-11-07T21:00:00.759Z까지이며 표시 시간대는 Etc/GMT+5이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Grand Hyatt Mumbai / Bandra Kurla Complex, Siddharath Nagar, Vakola, Vicinity, / Mumbai / India [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 웹3 기술 실험과 관심 있는 아이디어 개발, 암호화폐 학습, 인맥 확대와 업계 관계자 및 동료와의 만남을 제공합니다. lines:9-9

- 본문은 참가자 800명 이상, 프로토콜 11개 이상과 워크숍 29개 이상을 표기합니다. lines:11-11

- Arc 상금으로 15,000달러를 제공합니다. lines:13-15

- Arc와 Circle의 wallets, interops, App Kit 및 Circle Agent Stack을 활용하는 스테이블코인 기반 앱을 찾습니다. lines:17-17

- 팀과 함께 구현하고 직접 지원을 받으며 제품 피드백을 공유하고 상금 경쟁에 참여하도록 안내합니다. lines:19-19

- 본문의 표시 주소는 ETHGlobal Mumbai 행사이고 링크 대상은 Arc 상금 페이지입니다. lines:23-23

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 별도 EthGlobal Mumbai 공고와 프로토콜 수, 상금 범위 및 날짜 메타데이터가 다릅니다. 여기의 15,000달러는 lines:13-15의 Arc 상금입니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- [연결 주소](https://ethglobal.com/events/mumbai/)는 이번 요청에서 HTTP 403로 본문을 확보하지 못했다.
- https://ethglobal.com/events/mumbai/prizes/arc / 한국어 정리

### 행사 015

> EthGlobal Mumbai [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/ethglobal-mumbai-7xzcvfr4l8)

페이지 일정 필드(UTC)는 2026-11-05T20:00:00.430Z부터 2026-11-07T20:00:00.430Z까지이며 표시 시간대는 Indian/Mauritius이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Mumbai / India [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 웹3 기술 실험과 아이디어 개발, 암호화폐 학습, 인맥 확대 및 동료와의 만남을 제공합니다. lines:9-9

- 본문은 참가자 800명 이상, 프로토콜 10개 이상과 워크숍 29개 이상을 표기합니다. lines:11-11

- 전체 상금으로 175,000달러를 표기합니다. lines:13-13

- ETHGlobal Mumbai 행사 페이지에서 등록하도록 안내합니다. lines:15-15

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 이 공고의 175,000달러는 전체 상금이며 별도 공고의 Arc 상금 15,000달러와 구분합니다. 시간대는 lines:24에 Indian/Mauritius입니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- [연결 주소](https://ethglobal.com/events/mumbai)는 이번 요청에서 HTTP 403로 본문을 확보하지 못했다.

### 행사 016

> Pragma Mumbai [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/pragma-mumbai-xl8b4685vz)

페이지 일정 필드(UTC)는 2026-11-06T14:00:00.644Z부터 2026-11-06T22:00:33.446Z까지이며 표시 시간대는 Etc/GMT+5이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Grand Hayat Mumbai / Mumbai / India [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 웹3 개발자와 관계자를 위한 모임입니다. lines:7-7

- 소수의 창업자와 개발자가 웹3 미래와 과거를 논의합니다. lines:11-11

- ETHGlobal Pragma Mumbai 등록 페이지로 연결합니다. lines:26-26

- 장소는 Mumbai의 Grand Hayat Mumbai로 표기합니다. lines:31-34

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문 lines:9는 11월 4일을 안내하지만 startedAt과 endedAt은 lines:18-19에 11월 6일로 기록합니다. 별도 Pragma Mumbai 공고는 11월 5일을 안내합니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- [연결 주소](https://ethglobal.com/events/pragma-mumbai)는 이번 요청에서 HTTP 403로 본문을 확보하지 못했다.

### 행사 017

> Hyperliquid Community Event 2026 - Builder [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/hyperliquid-community-event-2026-builder-wqtmdlh1bt)

페이지 일정 필드(UTC)는 2026-10-05T09:00:00.639Z부터 2026-10-05T14:00:16.955Z까지이며 표시 시간대는 Asia/Singapore이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Singapore [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Hyperliquid가 Singapore에서 2026 커뮤니티 행사를 개최합니다. lines:7-7

- Circle 개발자 부스에서 Circle 제품과 Hyperliquid로 개발할 수 있는 결과물을 보여 줍니다. lines:7-7

- 참가하려면 RSVP하도록 안내합니다. lines:9-9

- 메타데이터의 등록은 HL2026Builders Luma 페이지로 연결합니다. lines:24-24

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문 lines:7은 시작 17:30 SGT이며 startedAt은 lines:16에 2026-10-05T09:00:00.639Z입니다. 본문은 HL2026Community, 등록 필드는 HL2026Builders로 연결합니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/HL2026Builders / 한국어 정리
- https://luma.com/HL2026Community / 한국어 정리

### 행사 018

> Vietnam Office Hours | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/vietnam-office-hours-or-regional-updates-and-live-demos-oso17xqshy)

페이지 일정 필드(UTC)는 2026-10-02T14:00:26.000Z부터 2026-10-02T15:00:56.000Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 베트남 지역 모임 회원을 위한 주간 커뮤니티 토론입니다. lines:7-7

- 지역 개발자와 연결하고 Arc 개발 소식을 공유하며 기술 피드백을 교환합니다. lines:7-7

- 생태계 기회를 논의하고 지역 개발자 커뮤니티를 강화합니다. lines:7-7

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Lecter  Vu / Founder / Vitael [원문 그대로]

> Teddy Dinh / Moderator / Architect [원문 그대로]

> Toan  Nhu / Founder / Mermail [원문 그대로]

> Trung Duc / Founder / Arenaiss  [원문 그대로]

### 행사 019

> Member Check-In | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/bangledesh/events/member-check-in-or-regional-updates-and-live-demos-di85d7uhnz)

페이지 일정 필드(UTC)는 2026-10-01T16:00:08.000Z부터 2026-10-01T17:00:31.000Z까지이며 표시 시간대는 Asia/Dhaka이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=True`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 방글라데시 지역 모임 회원을 위한 상호 참여형 진행 점검 모임입니다. lines:7-7

- Arc 개발 결과의 실시간 데모를 공유하고 실제 통합을 보여 줍니다. lines:7-7

- 기술 의견을 교환하고 지역의 실제 문제와 기회를 논의합니다. lines:7-7

- 티켓의 isFull은 true이며 대기 명단 기능은 false로 기록합니다. lines:77-82

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Sukanto Das / Co-Founder / Ababil Pay [원문 그대로]

> Motaleb Hossain / BD / Achswap [원문 그대로]

수집 시점의 공개 이벤트 데이터에서 만석으로 표시되어 있다.

### 행사 020

> Technical Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/technical-office-hours-1mysbdiytw)

페이지 일정 필드(UTC)는 2026-10-01T15:00:00.206Z부터 2026-10-01T16:00:36.690Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=True`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=True`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Elton이 Arc 메인넷의 신규 개발 도구에 관한 기술 상담을 진행합니다. lines:7-9

- App Kit와 신규 Onramp Kit, Earn Kit 및 Borrow Kit의 기능, 상호 관계와 실제 연결 방법을 설명합니다. lines:11-11

- 미리 읽을 수 있도록 세 도구의 문서 링크를 제공합니다. lines:13-19

- 도구 연결을 시작하여 문제가 생긴 개발자에게 질문을 가져오도록 안내합니다. lines:21-21

- 행사 초대 전용은 false지만 전체 티켓 초대 전용은 true로 기록합니다. lines:34-35

- 개별 Free Ticket도 초대 전용 true로 기록합니다. lines:59-59

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 행사 초대 전용 false와 전체 및 개별 티켓 초대 전용 true가 함께 기록되어 있습니다. lines:34-35,59를 구분합니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://docs.arc.io/app-kit/borrow / 한국어 정리
- https://docs.arc.io/app-kit/earn / 한국어 정리
- https://docs.arc.io/app-kit/onramp / 한국어 정리

### 행사 021

> Dev Days Cafe [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/dev-days-cafe-gwpqopd61a)

페이지 일정 필드(UTC)는 2026-09-29T17:00:00.426Z부터 2026-09-30T01:00:18.325Z까지이며 표시 시간대는 America/Los_Angeles이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Fort Maison / San Francisco / CA / USA [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Solana, Circle과 MoonPay 등이 9월 29일 Fort Mason의 Radhaus에서 개발자 카페를 진행합니다. lines:7-7

- 종일 커피, 공동 작업, 기념품, 데모와 해피아워를 제공합니다. lines:9-9

- 10시에 문을 열고 10-11시에 간단한 아침, 12-14시에 점심, 16-18시에 해피아워를 제공합니다. lines:13-19

- 공간이 제한되어 있어 참가 등록을 요구합니다. lines:21-21

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문 lines:7의 장소는 Fort Mason의 Radhaus이며 주소 필드는 lines:41에 Fort Maison으로 표기합니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/dev-day-cafe / 한국어 정리

### 행사 022

> How 1Shot Is Building Embedded Wallets on Arc with Onramp Kit and USDC [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/how-1shot-is-building-embedded-wallets-on-arc-with-onramp-kit-and-usdc-yum5f4rui6)

페이지 일정 필드(UTC)는 2026-09-29T00:00:00.783Z부터 2026-09-29T01:00:02.644Z까지이며 표시 시간대는 Asia/Singapore이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Elton Tay와 1Shot API 공동 창업자 및 CEO Todd Chapman이 Arc 내장 지갑 개발을 기술적으로 논의합니다. lines:7-7

- 1Shot의 Arc와 Onramp Kit 선택 이유, 법정통화에서 USDC로 자금을 넣는 경로의 설계, 통합 과정과 후속 개발 가능성을 다룹니다. lines:7-7

- Todd가 개발자 연결 과정부터 사용자 자금 입금까지 전체 과정을 보여 주고 기존 프로젝트에 지갑을 추가하는 방법을 시연합니다. lines:9-9

- 커뮤니티 질문을 받습니다. lines:9-9

- 면책 안내: 뒤의 법률 안내는 기능 변경 가능성과 보장 및 투자 조언 부재에 관한 면책 문구입니다. lines:17-17

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Elton Tay / DevRel Lead, APAC / Circle [원문 그대로]

> Todd  Chapman / Co-Founder and CEO / 1Shot [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 023

> Arc Demos & Meetup [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-demos-and-meetup-cupbm50egv)

페이지 일정 필드(UTC)는 2026-09-28T17:30:00.258Z부터 2026-09-28T19:00:00.258Z까지이며 표시 시간대는 Europe/London이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Encode hub / London / UK [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 짧은 데모, 프로젝트 소개와 개발자 대화를 진행합니다. lines:7-7

- 결제, 스테이블코인, 프로그래밍 가능한 자금과 온체인 금융 개발자를 대상으로 합니다. lines:7-7

- 실제 제품과 초기 아이디어를 살펴보고 Arc 생태계 개발자와 만납니다. lines:7-7

- 제작 중인 결과물의 피드백과 실제 개발 진척을 볼 기회를 제공합니다. lines:9-9

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/gnk0ygk0 / 한국어 정리

### 행사 024

> Bangladesh Build Club | Explore Arc Studio | Let’s Build on Arc [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/bangledesh/events/bangladesh-build-club-or-explore-arc-studio-or-lets-build-on-arc-1iekpndspt)

페이지 일정 필드(UTC)는 2026-09-28T15:00:12.000Z부터 2026-09-28T16:00:34.000Z까지이며 표시 시간대는 Asia/Dhaka이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 방글라데시 개발자들이 Arc 실제 프로젝트를 함께 만드는 모임입니다. lines:11-11

- 아이디어부터 코딩, 테스트와 배포까지 직접 작업합니다. lines:11-11

- 실시간으로 개발하면서 문제를 공유하고 서로 돕습니다. lines:11-11

- 함께 배우고 실제 결과물을 만들어 출시하는 것을 목표로 합니다. lines:11-11

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Sukanto Das / Co-Founder / Ababil Pay [원문 그대로]

> Motaleb Hossain / BD / Achswap [원문 그대로]

### 행사 025

> Uyo | Community Meetup | Agentic Economy on Arc [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/nigeria/events/uyo-or-community-meetup-or-agentic-economy-on-arc-slkh723jna)

페이지 일정 필드(UTC)는 2026-09-26T10:00:00.598Z부터 2026-09-26T15:00:07.273Z까지이며 표시 시간대는 Africa/Lagos이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Teckcocoon, 155, ikot Ekpene Road / Uyo / Akwa Ibom / Nigeria [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Arc를 Circle이 만든 실제 금융용 스테이블코인 기반 L1으로 소개합니다. lines:7-7

- Arc 개발자들이 실시간 개발, 데모와 대화를 하고 에이전트를 배포합니다. lines:9-9

- 제품을 개발하는 창업자, 투자자와 개발자 중 AI 에이전트, 스테이블코인과 Arc 통합에 관심 있는 사람을 대상으로 합니다. lines:11-11

- 인맥 교류와 Arc 에이전트 배포 실습을 제공합니다. lines:13-13

- 장소는 Uyo Akwa Ibom State의 Teckcocoon, 155 ikot Ekpene Road입니다. lines:15-15

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Blessing Ubi / Co-founder / Oink AI [원문 그대로]

> Fredrick Omoke / Founder / Arcle [원문 그대로]

> Godswill Okure / Founder / InfinitePay [원문 그대로]

> Frank Michael / Co-Founder / Tella [원문 그대로]

> Adenugba Oreofe / Community Builder / Digi Finance [원문 그대로]

> David Amodu / Regional Lead / Hibachi [원문 그대로]

> Akintola Covenant / Co-Founder / Tradersixx [원문 그대로]

### 행사 026

> Agent Builder Meetup - Orion Tekmer [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/turkey/events/agent-builder-meetup-orion-tekmer-62e6g019z6)

페이지 일정 필드(UTC)는 2026-09-26T11:00:00.124Z부터 2026-09-26T15:00:00.124Z까지이며 표시 시간대는 Europe/Istanbul이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Ankara / Türkiye [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=True`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=True`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Ankara에서 Orion Tekmer와 함께 Circle Agent Stack 개발을 중심으로 기술 모임을 개최합니다. lines:7-7

- 작업 추론, 다른 서비스와의 조율 및 자율 실행을 수행하는 AI 에이전트와 Agent Stack 작업 절차 설계를 탐구합니다. lines:9-9

- Arc와 Agent Stack 발표, 실시간 데모와 인맥 교류를 진행합니다. lines:13-17

- Orion Tekmer는 Ankara의 기술개발센터로 예비 창업 보육과 창업 보육을 통해 기업가와 기술 사업을 지원한다고 소개합니다. lines:21-21

- Orion Tekmer 소개는 사업 개발, 자금 조달, 경영, 교육과 멘토링 및 항공, 방위와 AI 분야를 제시합니다. 이는 주최 기관 소개입니다. lines:21-21

- 행사 초대 전용은 false지만 전체 티켓 초대 전용은 true로 기록합니다. lines:34-35

- 개별 Free Ticket도 초대 전용 true로 기록합니다. lines:88-88

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 행사 초대 전용 false와 전체 및 개별 티켓 초대 전용 true가 함께 기록되어 있습니다. lines:34-35,88을 구분합니다.

### 행사 027

> The Agentic Economy Prize [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/the-agentic-economy-prize-aignfyumkq)

페이지 일정 필드(UTC)는 2026-05-19T04:00:00.598Z부터 2026-09-25T04:00:00.598Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Circle이 Build with Gemini XPRIZE 내부에 제공하는 추가 상금 50,000달러이며 한 팀이 수상합니다. lines:7-9

- 실제 사업에서 AI 에이전트의 자율 송금과 수취가 작동함을 가장 잘 보여 주는 스타트업 팀에 수여합니다. lines:9-9

- 자금을 보유하고 필요한 서비스를 구매하며 다른 에이전트와 정산하는 개념을 실제 작동하는 결과물로 구현하도록 장려합니다. lines:13-19

- 이미 Build with Gemini XPRIZE에 등록한 팀은 부문과 관계없이 참여 가능하며 별도 신청 없이 제출 양식에서 추가 상금 참가를 선택합니다. 기존 부문에는 영향을 주지 않습니다. lines:23-23

- 본 대회 규칙을 따르며 프로젝트를 Google Cloud Platform에서 운영해야 합니다. lines:25-25

- Circle Agent Stack으로 AI 에이전트가 자율적으로 송금하거나 수취하도록 구현해야 합니다. lines:29-29

- 통합을 확인할 수 있는 공개 GitHub 저장소 링크를 제출합니다. lines:31-31

- 실제 검증 가능한 USDC 거래를 적어도 한 번 실행하는 제품 데모 영상을 제출합니다. lines:33-33

- 에이전트의 Circle 지갑 주소와 거래 증명을 위한 클릭 가능한 블록 탐색기 주소를 제출하며 예시로 Basescan과 Arbiscan을 제시합니다. lines:35-35

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://www.geminixprize.com/agentic-payments / 한국어 정리

### 행사 028

> Bangladesh Office Hours | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/bangledesh/events/bangladesh-office-hours-or-regional-updates-and-live-demos-y74av7711m)

페이지 일정 필드(UTC)는 2026-09-24T15:00:00.379Z부터 2026-09-24T16:00:31.732Z까지이며 표시 시간대는 Asia/Dhaka이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 방글라데시 지역 모임 회원을 위한 격주 토론입니다. lines:11-11

- 지역 개발자와 만나 Arc 프로젝트 소식을 공유하고 기술 의견을 교환합니다. lines:11-11

- 생태계 기회와 혜택을 논의하며 지역 개발자 커뮤니티를 강화합니다. lines:11-11

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Sukanto Das / Co-Founder / Ababil Pay [원문 그대로]

> Motaleb Hossain / BD / Achswap [원문 그대로]

> Md Raju Ahmed / EVM AND SVM DEV  / www.rajuice.xyz [원문 그대로]

> Rifat  Ahmed / Builder / Architect Pay [원문 그대로]

### 행사 029

> Vietnam Office Hours | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/vietnam-office-hours-or-regional-updates-and-live-demos-g047etzsra)

페이지 일정 필드(UTC)는 2026-09-24T14:00:00.589Z부터 2026-09-24T15:05:14.639Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 베트남 지역 지부 회원을 대상으로 합니다. lines:7-7

- 매주 커뮤니티 토론을 열고 지역 개발자들과 교류합니다. lines:7-7

- Arc에서 개발 중인 프로젝트의 진행 상황을 공유합니다. lines:7-7

- 기술 의견을 교환합니다. lines:7-7

- 생태계의 기회를 논의합니다. lines:7-7

- 지역 개발자 커뮤니티를 강화하는 것을 목표로 합니다. lines:7-7

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Lecter  Vu / Founder / Vitael [원문 그대로]

> Teddy Dinh / Moderator / Architect [원문 그대로]

> Rot Nguyen / Founder / Shiny [원문 그대로]

> Hoang Long / Founder / Taptipfun [원문 그대로]

### 행사 030

> Vietnam Office Hours | Mainnet Celebration , Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/vietnam-office-hours-or-mainnet-celebration-regional-updates-and-live-demos-734p9cohah)

페이지 일정 필드(UTC)는 2026-09-18T14:00:00.199Z부터 2026-09-18T15:15:10.173Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 베트남 지역 지부 회원을 대상으로 합니다. lines:7-7

- 매주 커뮤니티 토론을 열고 지역 개발자들과 교류합니다. lines:7-7

- Arc에서 개발 중인 프로젝트의 진행 상황을 공유합니다. lines:7-7

- 기술 의견을 교환합니다. lines:7-7

- 생태계의 기회를 논의합니다. lines:7-7

- 지역 개발자 커뮤니티를 강화하는 것을 목표로 합니다. lines:7-7

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Lecter  Vu / Founder / Vitael [원문 그대로]

> Teddy Dinh / Moderator / Architect [원문 그대로]

> Quoc Vuong / Founder / DASS & Hushcash [원문 그대로]

> Long  DC / Founder  / prizee.xyz [원문 그대로]

> Ngô Thu Phương / Founder  / Arklake [원문 그대로]

### 행사 031

> AI Infra Summit: Machine Payments Demo [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/ai-infra-summit-machine-payments-demo-pf7lukm5xs)

페이지 일정 필드(UTC)는 2026-09-15T16:00:00.348Z부터 2026-09-18T01:00:00.348Z까지이며 표시 시간대는 America/Los_Angeles이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Santa Clara Convention Center / Santa Clara / CA / USA [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 공고는 AI 인프라의 여러 계층에 속한 참가자들이 한자리에 모이는 행사라고 설명합니다. lines:7-7

- Architect @tlay_io가 기계의 자율 거래를 시연합니다. lines:9-9

- 연결된 장치가 필요한 전력이나 연산 자원을 USDC로 자율 구매하고 Arc에서 실시간 검증하는 사례를 보여 줍니다. lines:9-9

- AI Infra Summit 웹사이트에서 상세 정보를 확인하도록 안내합니다. lines:12-12

- 장소는 미국 Santa Clara Convention Center로 기재되어 있습니다. lines:32-35

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://www.ai-infra-summit.com/ / 한국어 정리

### 행사 032

> Building on Arc: A Technical Workshop with Blockradar [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/building-on-arc-a-technical-workshop-with-blockradar-8srcljr7p4)

페이지 일정 필드(UTC)는 2026-09-17T22:30:00.050Z부터 2026-09-18T00:30:11.022Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Encode Hub / London / UK [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Blockradar와 Encode가 Arc 기반 핀테크와 결제 애플리케이션 개발자를 위한 실습 워크숍을 엽니다. lines:7-7

- Blockradar 공동 창업자이자 CEO인 Abdulfatai Suleiman이 코드를 함께 작성하며 Arc 핀테크 애플리케이션을 구현하는 과정을 진행합니다. lines:9-9

- 지갑 생성, 스테이블코인과 법정화폐의 송수신, 거래 모니터링, 웹훅 사용을 연결하여 작동하는 결제 과정을 만듭니다. lines:11-11

- 구성 요소를 서로 다른 핀테크 사례에 적용하는 방법을 살펴보고 진행 중에 질문에 답합니다. lines:11-11

- 노트북과 자신의 프로젝트, 현재 막힌 문제를 가져오도록 안내합니다. lines:13-13

- 작동하는 코드와 Blockradar를 통한 Arc 개발에 대한 이해를 얻고 세션 후에 팀의 직접적인 도움을 받을 시간이 마련됩니다. lines:13-13

- 런던 Arc 커뮤니티를 위한 반복적인 기술 워크숍, 시연과 공동 작업 프로그램에 속합니다. lines:15-15

- 핀테크, 결제, 스테이블코인 앱을 개발 중이거나 개발하려는 개발자, 창업자와 기술 팀을 대상으로 합니다. lines:17-17

- 아이디어를 시험하는 해커톤 참가자부터 제품 출시를 준비하는 팀까지 포함합니다. lines:17-17

- Encode가 Arc, Circle과 Blockradar의 협력으로 주최합니다. lines:19-19

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문 15행과 장소 39-42행은 런던을 가리키지만 28행의 timezone은 America/New_York로 기재되어 있습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/encode-lwek / 한국어 정리

### 행사 033

> Member Check-In | Mainnet Celebration , Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/bangledesh/events/member-check-in-or-mainnet-celebration-regional-updates-and-live-demos-yi5amcqf08)

페이지 일정 필드(UTC)는 2026-09-17T16:00:00.884Z부터 2026-09-17T17:00:45.641Z까지이며 표시 시간대는 Asia/Dhaka이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=True`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 방글라데시 지역 지부 회원을 위한 상호작용형 진행 상황 공유 모임입니다. lines:10-10

- Arc에서 개발하는 결과물의 실시간 시연을 공유합니다. lines:10-10

- 진행 중인 통합 사례를 보여 주고 기술 의견을 교환합니다. lines:10-10

- 지역에서 실제로 겪는 문제와 기회를 논의합니다. lines:10-10

- 공개 티켓에는 정원이 찼다고 표시되어 있습니다. lines:80-80

- 공개 티켓에는 대기자 명단을 제공하지 않는다고 표시되어 있습니다. lines:85-85

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Sukanto Das / Co-Founder / Ababil Pay [원문 그대로]

> Motaleb Hossain / BD / Achswap [원문 그대로]

수집 시점의 공개 이벤트 데이터에서 만석으로 표시되어 있다.

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 17-18행의 행사 날짜는 9월 17일이지만 days의 69-70행은 9월 14-15일로 기재되어 있습니다.

### 행사 034

> Technical Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/technical-office-hours-rpku8fcswc)

페이지 일정 필드(UTC)는 2026-09-17T15:00:00.126Z부터 2026-09-17T16:00:48.472Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=True`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=True`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 공고는 Arc 메인넷 공개 다음 날의 기술 질의응답 행사라고 설명합니다. lines:7-7

- 개발자 관계 팀의 Blessing이 진행합니다. lines:9-9

- Arc 메인넷에서 공개된 기능을 공유합니다. lines:11-11

- 필요할 때 추론을 구매하는 에이전트를 실시간으로 구현합니다. lines:11-11

- 사전 준비를 원하는 참가자에게 Arc Network 문서를 읽도록 안내합니다. lines:13-15

- 특히 해당 주에 메인넷에 배포하는 참가자에게 질문을 가져오도록 안내합니다. lines:19-19

- 티켓에는 초대가 필요하다고 표시되어 있습니다. lines:57-57

- 사전 준비 자료로 거래 확정(deterministic finality) 문서를 안내합니다. lines:17-17

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 32행 이벤트 isInvitationOnly는 false이지만 33행 모든 티켓 초대 표시는 true이고 57행 티켓 isInvitationOnly도 true입니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://docs.arc.io/arc-chain / 한국어 정리
- https://docs.arc.io/arc/concepts/deterministic-finality / 한국어 정리

### 행사 035

> Arc Mainnet launch livestream [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-mainnet-launch-livestream)

페이지 일정 필드(UTC)는 2026-09-16T15:30:00.181Z부터 2026-09-16T22:45:00.000Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Event [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 9월 16일 메인넷 출시를 뉴욕에서 생중계하며 출시일부터 제공하는 기능과 향후 기관 금융, 글로벌 자금 이동, 상시 시장 및 AI 에이전트 경제 활동을 소개합니다. lines:7-13

- Arc 테스트넷 개발자와 향후 가능한 일을 살펴보는 사람 모두 어디서나 시청하도록 안내합니다. lines:13-13

- ET 11:30-13:30 개발자 사전 방송에는 개발자 대화, 제품 데모, 파트너 소개와 커뮤니티 참여가 포함됩니다. lines:17-17

- ET 13:30-14:00은 대기 방송이며 14:00-15:45에는 기조연설, 파트너 대화, 제품 데모와 향후 계획을 방송합니다. lines:19-21

- 공개 의제에는 금융 시스템에 Arc가 필요한 이유에 관한 세션이 있으며 발표자로 Jeremy Allaire를 기록합니다. lines:269-298

- 공개 의제에는 Arc 플랫폼 소개에 관한 세션이 있으며 발표자로 Nikhil Chandhok를 기록합니다. lines:302-331

- 공개 의제에는 기관의 신뢰와 개방형 혁신에 관한 세션이 있으며 발표자로 Robert Mitchnick, Stani Kulechov, Michael Winnike, Kash Razzaghi를 기록합니다. lines:335-397

- 공개 의제에는 국경을 넘는 자금에 관한 세션이 있으며 발표자로 Sebastian Serrano, Merlin Egalite, Masashi Okuyama, Erika Peterson, Matt Stafford를 기록합니다. lines:401-474

- 공개 의제에는 시장 활성화에 관한 세션이 있으며 발표자로 Ben Morris, Hayden Adams를 기록합니다. lines:478-518

- 공개 의제에는 현재 제공 기능에 관한 세션이 있으며 발표자로 Gagan Mac, Sanket Jain를 기록합니다. lines:522-562

- 공개 의제에는 경제 활동 주체로서의 에이전트 지원에 관한 세션이 있으며 발표자로 Gagan Mac, Hao Min를 기록합니다. lines:566-606

- 공개 의제에는 지금 추진하는 이유에 관한 세션이 있으며 발표자로 Jeremy Allaire, Chris Dixon를 기록합니다. lines:610-650

- 공개 의제에는 IF ARC >> Then Possible에 관한 세션이 있으며 발표자로 Heath Tarbert를 기록합니다. lines:654-683

- 공개 메타데이터는 시작 2026-09-16T15:30:00.181Z, 종료 2026-09-16T22:45:00.000Z, 시간대 America/New_York를 기록합니다. lines:28-30

- 공개 티켓은 Free Event이며 표시 가격은 0입니다. lines:709-709

- 온라인 여부는 true이고 초대 전용 여부는 false입니다. lines:33-35

- 발표자 목록은 Jeremy Allaire의 직함을 Co-Founder, Chief Executive Officer & Chairman, 소속을 Circle로 기록합니다. lines:47-49

- 발표자 목록은 Heath Tarbert의 직함을 President, 소속을 Circle로 기록합니다. lines:57-59

- 발표자 목록은 Nikhil Chandhok의 직함을 Chief Product & Technology Officer, 소속을 Circle로 기록합니다. lines:67-69

- 발표자 목록은 Kash Razzaghi의 직함을 Chief Commercial Officer, 소속을 Circle로 기록합니다. lines:77-79

- 발표자 목록은 Chris Dixon의 직함을 Founder & Managing Partner, 소속을 a16z crypto로 기록합니다. lines:87-89

- 발표자 목록은 Robert Mitchnick의 직함을 Global Head of Digital Assets, 소속을 BlackRock로 기록합니다. lines:97-99

- 발표자 목록은 Stani Kulechov의 직함을 Founder & CEO, 소속을 Aave Labs로 기록합니다. lines:107-109

- 발표자 목록은 Michael Winnike의 직함을 Head of Strategy for Clearing & Market Solutions, 소속을 DTCC로 기록합니다. lines:117-119

- 발표자 목록은 Sebastian  Serrano의 직함을 Ripio, 소속을 CEO & Co-Founder로 기록합니다. lines:127-129

- 발표자 목록은 Merlin Egalite의 직함을 Co-Founder, 소속을 Morpho로 기록합니다. lines:137-139

- 발표자 목록은 Masashi Okuyama의 직함을 Member of the Board of Directors, CEO of SBI, 소속을 SBI Holdings, Inc로 기록합니다. lines:147-149

- 발표자 목록은 Hayden Adams의 직함을 Founder and CEO, 소속을 Uniswap로 기록합니다. lines:157-159

- 발표자 목록은 Gagan Mac의 직함을 VP, Product & Engineering, 소속을 Circle로 기록합니다. lines:167-169

- 발표자 목록은 Hao Min의 직함을 VP, Agentic Products, 소속을 Circle로 기록합니다. lines:177-179

- 발표자 목록은 Matt Stafford의 직함을 VP, Business Development, 소속을 Circle로 기록합니다. lines:187-189

- 발표자 목록은 Erika Peterson의 직함을 VP, Business Development, 소속을 Circle로 기록합니다. lines:197-199

- 발표자 목록은 Ben Morris의 직함을 VP, Business Development, 소속을 Circle로 기록합니다. lines:207-209

- 발표자 목록은 Sanket Jain의 직함을 Senior Principal Product Manager, 소속을 Circle로 기록합니다. lines:217-219

- 발표자 목록은 Sam Sealey의 직함을 Director, Community, 소속을 Circle로 기록합니다. lines:227-229

- 발표자 목록은 Tim Baker의 직함을 Community Manager, 소속을 Circle로 기록합니다. lines:237-239

- 발표자 목록은 Bobbilee Hartman의 직함을 Principle PM, Developer Program, 소속을 Circle로 기록합니다. lines:247-249

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Jeremy Allaire / Co-Founder, Chief Executive Officer & Chairman / Circle [원문 그대로]

> Heath Tarbert / President / Circle [원문 그대로]

> Nikhil Chandhok / Chief Product & Technology Officer / Circle [원문 그대로]

> Kash Razzaghi / Chief Commercial Officer  / Circle [원문 그대로]

> Chris Dixon / Founder & Managing Partner / a16z crypto [원문 그대로]

> Robert Mitchnick / Global Head of Digital Assets / BlackRock [원문 그대로]

> Stani Kulechov / Founder & CEO / Aave Labs [원문 그대로]

> Michael Winnike / Head of Strategy for Clearing & Market Solutions / DTCC [원문 그대로]

> Sebastian  Serrano / Ripio / CEO & Co-Founder [원문 그대로]

> Merlin Egalite / Co-Founder / Morpho [원문 그대로]

> Masashi Okuyama / Member of the Board of Directors, CEO of SBI  / SBI Holdings, Inc [원문 그대로]

> Hayden Adams / Founder and CEO / Uniswap [원문 그대로]

> Gagan Mac / VP, Product & Engineering / Circle [원문 그대로]

> Hao Min / VP, Agentic Products / Circle [원문 그대로]

> Matt Stafford / VP, Business Development / Circle [원문 그대로]

> Erika Peterson / VP, Business Development / Circle [원문 그대로]

> Ben Morris / VP, Business Development / Circle [원문 그대로]

> Sanket Jain / Senior Principal Product Manager / Circle [원문 그대로]

> Sam Sealey / Director, Community  / Circle [원문 그대로]

> Tim Baker / Community Manager / Circle [원문 그대로]

> Bobbilee Hartman / Principle PM, Developer Program / Circle [원문 그대로]

공개 세션은 다음과 같다. 제목과 설명은 원문 표기를 유지하며 시각은 각 세션의 UTC 데이터다.

> Why the Financial System Needs Arc [원문 그대로]

세션 시각: `2026-09-16T18:00:00.000Z` - `2026-09-16T18:10:00.000Z`.

> Why the Financial System Needs Arc [원문 그대로]

> 발표자: Jeremy Allaire / Co-Founder, Chief Executive Officer & Chairman / Circle [원문 그대로]

> Introducing the Arc Platform [원문 그대로]

세션 시각: `2026-09-16T18:00:00.000Z` - `2026-09-16T18:20:00.000Z`.

> 발표자: Nikhil Chandhok / Chief Product & Technology Officer / Circle [원문 그대로]

> Institutional Trust Meets Open Innovation [원문 그대로]

세션 시각: `2026-09-16T18:20:00.000Z` - `2026-09-16T18:30:00.000Z`.

> 발표자: Robert Mitchnick / Global Head of Digital Assets / BlackRock [원문 그대로]

> 발표자: Stani Kulechov / Founder & CEO / Aave Labs [원문 그대로]

> 발표자: Michael Winnike / Head of Strategy for Clearing & Market Solutions / DTCC [원문 그대로]

> 발표자: Kash Razzaghi / Chief Commercial Officer  / Circle [원문 그대로]

> Money Without Borders [원문 그대로]

세션 시각: `2026-09-16T18:30:00.000Z` - `2026-09-16T18:45:00.000Z`.

> 발표자: Sebastian  Serrano / Ripio / CEO & Co-Founder [원문 그대로]

> 발표자: Merlin Egalite / Co-Founder / Morpho [원문 그대로]

> 발표자: Masashi Okuyama / Member of the Board of Directors, CEO of SBI  / SBI Holdings, Inc [원문 그대로]

> 발표자: Erika Peterson / VP, Business Development / Circle [원문 그대로]

> 발표자: Matt Stafford / VP, Business Development / Circle [원문 그대로]

> Markets Come to Life  [원문 그대로]

세션 시각: `2026-09-16T18:45:00.000Z` - `2026-09-16T19:00:00.000Z`.

> 발표자: Ben Morris / VP, Business Development / Circle [원문 그대로]

> 발표자: Hayden Adams / Founder and CEO / Uniswap [원문 그대로]

> What's Live [원문 그대로]

세션 시각: `2026-09-16T19:00:00.000Z` - `2026-09-16T19:10:00.000Z`.

> 발표자: Gagan Mac / VP, Product & Engineering / Circle [원문 그대로]

> 발표자: Sanket Jain / Senior Principal Product Manager / Circle [원문 그대로]

> What's Next: Enabling Agents as Economic Actors [원문 그대로]

세션 시각: `2026-09-16T19:10:00.000Z` - `2026-09-16T19:20:00.000Z`.

> 발표자: Gagan Mac / VP, Product & Engineering / Circle [원문 그대로]

> 발표자: Hao Min / VP, Agentic Products / Circle [원문 그대로]

> Why Now [원문 그대로]

세션 시각: `2026-09-16T19:20:00.000Z` - `2026-09-16T19:40:00.000Z`.

> 발표자: Jeremy Allaire / Co-Founder, Chief Executive Officer & Chairman / Circle [원문 그대로]

> 발표자: Chris Dixon / Founder & Managing Partner / a16z crypto [원문 그대로]

> IF ARC >> Then Possible [원문 그대로]

세션 시각: `2026-09-16T19:40:00.000Z` - `2026-09-16T19:45:00.000Z`.

> 발표자: Heath Tarbert / President / Circle [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문의 ET 본무대 종료는 lines:21의 15:45이나 전체 이벤트 endedAt은 lines:29의 2026-09-16T22:45:00.000Z입니다. 첫 기조연설과 다음 발표는 lines:271,304에 동일 시작 시각을 기록합니다.
- Sebastian Serrano의 title과 company 값은 lines:128-129에서 서로 바뀐 형태이고 Merlin Egalite의 slug는 lines:136에서 paul-frambot입니다.

### 행사 036

> EthOnline 2026 [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/arc-hackathons/events/ethonline-2026-8p0t6v1eux)

페이지 일정 필드(UTC)는 2026-09-04T04:00:00.994Z부터 2026-09-16T04:00:00.994Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Arc가 ETHGlobal Online에 참여한다고 안내합니다. lines:7-7

- Arc와 Circle 도구를 활용한 스테이블코인 중심 앱을 모집하며 지갑, 상호운용성, App Kit와 Agent Stack을 예로 듭니다. lines:9-9

- 공고는 상금 총액이 10,000달러이며 두 부분으로 나뉜다고 설명합니다. lines:11-11

- 9월 16일까지 제출하면 테스트넷 상금 5,000달러에 도전할 수 있다고 안내합니다. lines:13-13

- 9월 30일까지 앱을 Arc 메인넷에 배포하면 나머지 상금 5,000달러에 도전할 수 있다고 안내합니다. lines:13-13

- 실무 지원을 받으며 우수 제출물을 놓고 경쟁한다고 안내합니다. lines:15-15

- ETHGlobal 행사 페이지에서 참가 신청을 하도록 안내합니다. lines:17-17

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- http://ethglobal.com/events/ethonline2026 / 한국어 정리
- https://ethglobal.com/events/ethonline2026 / 한국어 정리
- https://ethglobal.com/events/ethonline2026/prizes/arc / 한국어 정리

### 행사 037

> Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/discord-office-hours-hq6qlpbc68)

페이지 일정 필드(UTC)는 2026-09-15T17:00:00.814Z부터 2026-09-15T17:45:07.577Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord에서만 진행하는 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계의 개발자들이 편하게 만나는 행사입니다. lines:7-7

- 질문을 하고 해당 주의 Arc 최신 소식을 이야기합니다. lines:7-7

- 본문의 Discord 이벤트 링크로 알림을 설정하도록 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 알림 링크는 이 배치에 있는 서로 다른 날짜의 Discord Office Hours 공고에서 동일합니다. 링크의 실제 행사 날짜는 확인하지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 038

> Hanoi | Campus Meetup | From Campus to Mainnet II : Phuong Dong University [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/hanoi-or-campus-meetup-or-from-campus-to-mainnet-ii-phuong-dong-university-enys896x4d)

페이지 일정 필드(UTC)는 2026-09-15T07:00:52.183Z부터 2026-09-15T09:30:52.158Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> No. 171 Trung Kinh Street, Yen Hoa Ward, Cau Giay District, Hanoi, Vietnam. / Ha Noi / Cau Giay / Việt Nam [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 학생, 개발자와 블록체인, 핀테크, 스테이블코인, AI에 관심 있는 사람을 대상으로 합니다. lines:7-7

- Arc의 비전과 메인넷 전환을 살펴보는 행사입니다. lines:9-9

- 스테이블코인 인프라가 실물 금융 애플리케이션을 지원하는 방법과 AI를 온체인 결제에 결합할 가능성을 다룹니다. lines:9-9

- Arc 소개, 발표자와 개발자의 경험 공유, 제품의 실시간 시연이 포함됩니다. lines:11-11

- 학생이 생태계를 배우고 개발과 기여를 시작할 기회를 제공합니다. lines:11-11

- 기술, 금융과 경영 분야의 학생뿐 아니라 Web3를 처음 알아보는 사람도 언급합니다. lines:13-13

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Xuan Hai / Founder / Heypayna [원문 그대로]

### 행사 039

> Bangladesh Build Club | Let’s Build on Arc [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/bangledesh/events/bangladesh-build-club-or-lets-build-on-arc-qrizir2s7e)

페이지 일정 필드(UTC)는 2026-09-14T15:00:00.135Z부터 2026-09-14T16:00:17.966Z까지이며 표시 시간대는 Asia/Dhaka이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 방글라데시 개발자들이 함께 Arc 기반 실제 프로젝트를 만드는 모임입니다. lines:11-11

- 아이디어 구상부터 코딩, 테스트와 배포까지 실습합니다. lines:11-11

- 실시간으로 개발하며 문제를 공유하고 서로 돕습니다. lines:11-11

- 함께 배우고 실제 결과물을 만들어 배포하는 것을 목표로 합니다. lines:11-11

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Sukanto Das / Co-Founder / Ababil Pay [원문 그대로]

> Motaleb Hossain / BD / Achswap [원문 그대로]

### 행사 040

> Vietnam Office Hours | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/vietnam-office-hours-or-regional-updates-and-live-demos-eqm4lprlnq)

페이지 일정 필드(UTC)는 2026-09-11T14:00:00.442Z부터 2026-09-11T15:01:53.386Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 베트남 지역 지부 회원을 대상으로 합니다. lines:7-7

- 매주 커뮤니티 토론을 열고 지역 개발자들과 교류합니다. lines:7-7

- Arc에서 개발 중인 프로젝트의 진행 상황을 공유합니다. lines:7-7

- 기술 의견을 교환합니다. lines:7-7

- 생태계의 기회를 논의합니다. lines:7-7

- 지역 개발자 커뮤니티를 강화하는 것을 목표로 합니다. lines:7-7

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Lecter  Vu / Founder / Vitael [원문 그대로]

> Teddy Dinh / Moderator / Architect [원문 그대로]

> Hieu Nguyen / Founder / EZWallet  [원문 그대로]

> Vu Tang / Founder & Winner Hackathon / KERYX [원문 그대로]

> Still Ho / Founder / Luckpot [원문 그대로]

### 행사 041

> Bangladesh Office Hours | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/bangledesh/events/bangladesh-office-hours-or-regional-updates-and-live-demos-bo94gdvq63)

페이지 일정 필드(UTC)는 2026-09-10T15:00:00.326Z부터 2026-09-10T16:00:18.115Z까지이며 표시 시간대는 Asia/Dhaka이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 방글라데시 지역 지부 회원을 대상으로 합니다. lines:11-11

- 격주로 커뮤니티 토론을 열고 지역 개발자들과 교류합니다. lines:11-11

- Arc에서 개발 중인 프로젝트의 진행 상황을 공유합니다. lines:11-11

- 기술 의견을 교환합니다. lines:11-11

- 생태계의 기회를 논의합니다. lines:11-11

- 발표자 Adnan Taher의 소개에는 마켓플레이스용 스테이블코인 결제 게이트웨이 Druto와 참여 프로젝트 Chronpay가 모두 Arc 테스트넷에서 개발되고 있다고 적혀 있습니다. lines:62-62

- 지역 개발자 커뮤니티를 강화하는 것을 목표로 합니다. lines:11-11

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Sukanto Das / Co-Founder / Ababil Pay [원문 그대로]

> Motaleb Hossain / BD / Achswap [원문 그대로]

> Adnan Taher / Builder and Founder / Druto [원문 그대로]

> Nahian Nahin / Front-End Engineer / Ababil Pay [원문 그대로]

### 행사 042

> Arc x Aave: Bringing Lending Infrastructure to Arc [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-x-aave-bringing-lending-infrastructure-to-arc-2oqj4v3cab)

페이지 일정 필드(UTC)는 2026-09-10T14:00:00.844Z부터 2026-09-10T15:00:33.121Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 개발자를 대상으로 Arc에 도입되는 Aave V4를 이야기합니다. lines:7-7

- 스테이블코인 중심의 대출과 차입이 개발자에게 어떤 의미가 있는지 다룹니다. lines:7-7

- 온체인 유동성 인프라와 Arc 출시 자산인 USDC, EURC와 cirBTC를 다룹니다. lines:7-7

- 실습형 기술 설명 후 커뮤니티 질문을 받습니다. lines:7-7

- 면책 안내: 면책문구는 CTS가 소프트웨어 제공자이며 규제 금융 서비스나 자문 서비스를 제공하지 않는다고 설명합니다. lines:11-11

- 면책 안내: 면책문구는 이용자가 제공하는 서비스의 인허가와 관련 법률 준수 책임을 이용자에게 둡니다. lines:11-11

- 면책 안내: 면책문구는 Arc가 뉴욕주 금융서비스국의 검토나 승인을 받지 않았다고 설명합니다. lines:13-13

- 면책 안내: 면책문구는 제품 기능이 변경, 지연되거나 취소될 수 있다고 설명합니다. lines:15-15

- 면책 안내: 면책문구는 USDC를 Circle의 규제 대상 계열사가 발행하며 인허가 목록을 외부 링크에서 확인할 수 있다고 설명합니다. lines:17-17

- 면책 안내: 면책문구는 이 자료가 약정, 보증이나 투자 자문을 구성하지 않는다고 설명합니다. lines:15-15

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 043

> Arc x Wirex: From Crypto Cards to Stablecoin Infrastructure [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-x-wirex-from-crypto-cards-to-stablecoin-infrastructure-kgxt21prbr)

페이지 일정 필드(UTC)는 2026-09-09T14:00:00.923Z부터 2026-09-09T15:00:50.081Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 공고는 Wirex가 암호화폐 카드에서 소비자와 기업용 스테이블코인 및 온체인 제품으로 확장한 과정을 소개합니다. lines:7-7

- Wirex 공동 창업자이자 그룹 CEO인 Pavel Matveev와 Sam Sealey가 대화합니다. lines:7-7

- Wirex의 역사, 스테이블코인이 인프라의 기반이 된 과정, 카드 이후의 확장과 Arc와의 접점을 논의합니다. lines:7-7

- 온체인 인프라가 기존 카드 결제 인프라와 함께 작동하는 방법에 대한 Wirex의 관점을 다룹니다. lines:7-7

- 면책 안내: 면책문구는 CTS가 소프트웨어 제공자이며 규제 금융 서비스나 자문 서비스를 제공하지 않는다고 설명합니다. lines:11-11

- 면책 안내: 면책문구는 이용자가 제공하는 서비스의 인허가와 관련 법률 준수 책임을 이용자에게 둡니다. lines:11-11

- 면책 안내: 면책문구는 Arc가 뉴욕주 금융서비스국의 검토나 승인을 받지 않았다고 설명합니다. lines:13-13

- 면책 안내: 면책문구는 제품 기능이 변경, 지연되거나 취소될 수 있다고 설명합니다. lines:15-15

- 면책 안내: 면책문구는 USDC를 Circle의 규제 대상 계열사가 발행하며 인허가 목록을 외부 링크에서 확인할 수 있다고 설명합니다. lines:17-17

- 면책 안내: 면책문구는 이 자료가 약정, 보증이나 투자 자문을 구성하지 않는다고 설명합니다. lines:15-15

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 044

> Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/discord-office-hours-d9tobs934u)

페이지 일정 필드(UTC)는 2026-09-08T17:00:00.062Z부터 2026-09-08T17:45:09.681Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord에서만 진행하는 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계의 개발자들이 편하게 만나는 행사입니다. lines:7-7

- 질문을 하고 해당 주의 Arc 최신 소식을 이야기합니다. lines:7-7

- 본문의 Discord 이벤트 링크로 알림을 설정하도록 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 알림 링크는 이 배치에 있는 서로 다른 날짜의 Discord Office Hours 공고에서 동일합니다. 링크의 실제 행사 날짜는 확인하지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 045

> Encode Programmable Money on Arc Demo Day [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/encode-programmable-money-on-arc-demo-day-h4y846b1vb)

페이지 일정 필드(UTC)는 2026-09-08T15:00:00.596Z부터 2026-09-08T16:00:13.115Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 해커톤 우승자들이 자신의 해결책을 시연합니다. lines:7-7

- 공고는 예정된 Arc Accelerator로 이어지는 과정을 시작한다고 설명합니다. lines:7-7

- Circle의 Blessing Adesiji가 발표자로 기재되어 있습니다. lines:33-35

- Circle의 Jenna Teeman이 발표자로 기재되어 있습니다. lines:43-45

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Blessing Adesiji / Developer Relations Manager, EMEA / Circle [원문 그대로]

> Jenna Teeman / Principle Program Manager, Developer Marketing  / Circle [원문 그대로]

### 행사 046

> Ha Noi | Community Meetup: Road to Arc Mainnet — Stablecoin Finance & AI Applications 101 [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/ha-noi-or-community-meetup-road-to-arc-mainnet-stablecoin-finance-and-ai-applications-101-5lj392uqbw)

페이지 일정 필드(UTC)는 2026-09-06T02:00:00.756Z부터 2026-09-06T05:00:27.801Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> D2 Giảng Võ- Ba Đình - Hà Nội / Ha Noi / Ba Dinh / Việt Nam [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 개발자, 학생, 창업자와 Web3 관심자를 위한 개발자 중심 모임입니다. lines:9-9

- Arc와 스테이블코인 및 프로그래밍 가능한 돈(programmable money)을 위한 인프라, 메인넷 이전의 개발 기회를 다룹니다. lines:11-11

- 복잡한 정보 처리부터 기존 스마트 계약이 다루기 어려운 의사결정 지원까지 AI의 온체인 활용을 간략히 살펴봅니다. lines:13-13

- Rise In을 무료 학습, 실제 프로젝트 개발, 부트캠프와 해커톤 등의 기회에 접근할 수 있는 Web3 개발자 커뮤니티로 소개합니다. lines:15-15

- 생태계 정보 공유, 개발자 토론, 질의응답과 베트남 개발자 커뮤니티와의 교류를 진행합니다. lines:17-17

- Web3에서 이미 개발하는 사람과 처음 시작하는 사람을 모두 언급합니다. lines:19-19

- GenLayer와 Rise In이 베트남 개발자 커뮤니티의 연결, 지원과 기회 확대를 위해 행사를 지원합니다. lines:21-21

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Lily Hoang / Founder / Fundline.xyz [원문 그대로]

> Lv Manh / Founder / Flowmint [원문 그대로]

> J Elias / Co-Founder / Vitael.xyz [원문 그대로]

> Panchu Vijay Pal / Co-Founder / Xylonet [원문 그대로]

### 행사 047

> Buenos Aires | Arc Builder Circle: Building with Lo-Fi Pomodor & arc_fajores 🍪 [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/argentina/events/buenos-aires-or-arc-builder-circle-building-with-lo-fi-pomodor-and-arc_fajores-cpczmqww0n)

페이지 일정 필드(UTC)는 2026-09-05T17:00:00.542Z부터 2026-09-05T22:00:00.542Z까지이며 표시 시간대는 America/Argentina/Buenos_Aires이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Malabia 806, C1414 Cdad. Autónoma de Buenos Aires / Cafe Nomada | CoWorkingCo / Buenos Aires / CABA / Argentina [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 부에노스아이레스에서 격주로 열리는 개발 모임이며 결과물을 배포하고 지역 Arc 커뮤니티를 만나는 것을 안내합니다. lines:19-19

- 참가자는 자신의 프로젝트를 가져와 포모도로(Pomodoro) 방식으로 집중 작업하고 작업 사이에 진행 상황을 공유합니다. lines:21-21

- 필터 커피와 arc_fajores를 제공합니다. lines:21-21

- 모임에서 가장 많이 진행한 참가자에게 100 USDC를 지급한다고 안내합니다. lines:23-23

- 다음 모임에서는 그 사이의 2주 동안 가장 많이 진행한 참가자에게 100 USDC를 지급한다고 안내합니다. lines:23-23

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Tomás Cordero / Indie Hacker / Founder / BuFi [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 30-31행의 행사 날짜는 9월 5일이지만 days의 81-82행은 8월 19-20일로 기재되어 있습니다.
- 23행은 가장 많이 진행한 참가자에게 상금을 준다고 안내하지만 진행 정도를 판정하는 기준은 이 공고에서 구체적으로 설명하지 않습니다.

### 행사 048

> Lagos | Community Meetup | Circle Agent Stack [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/nigeria/events/lagos-or-community-meetup-or-circle-agent-stack-mom19hel5d)

페이지 일정 필드(UTC)는 2026-09-05T11:00:00.005Z부터 2026-09-05T15:30:00.005Z까지이며 표시 시간대는 Africa/Lagos이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Cafe One, 3, Kudirat Abiola Way, / Oregun / Lagos / Nigeria [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 공고는 Arc를 Circle이 만든 실물 금융용 스테이블코인 중심 레이어 1로 소개합니다. lines:7-7

- 지역 개발자들이 실시간 개발과 시연, 대화를 진행하고 Arc에 에이전트를 배포합니다. lines:9-9

- 제품을 만드는 창업자, 투자자와 개발자 중 AI 에이전트, 스테이블코인과 Arc의 통합에 관심 있는 사람을 언급합니다. lines:11-11

- 장소는 라고스의 Cafe One, 3, Kudirat Abiola Way, Oregun으로 안내합니다. lines:13-13

- 네트워킹과 Arc에서 에이전트를 배포하는 실습을 혜택으로 안내합니다. lines:15-15

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Ridwan  Jokanola (Ade) / Blockchain developer  / Arcade [원문 그대로]

> Oluwagbemiga Gbangbola / Software Developer / Web3bridge [원문 그대로]

> Oodo Malachi / Co-founder / Hanka Virality [원문 그대로]

> Ikechukwu Christian / Co-founder / Cofluence [원문 그대로]

> Akintola Covenant / Co-Founder / Tradersixx [원문 그대로]

> Akinjide Jaiyeola / Founder  / CivicVault [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 22-23행의 행사 날짜는 9월 5일이지만 days의 123-124행은 8월 14-15일로 기재되어 있습니다.

### 행사 049

> Vietnam Office Hours | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/vietnam-office-hours-or-regional-updates-and-live-demos-hsn9mt6hhp)

페이지 일정 필드(UTC)는 2026-09-04T14:00:00.667Z부터 2026-09-04T15:00:01.386Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 베트남 지역 지부 회원을 대상으로 합니다. lines:7-7

- 매주 커뮤니티 토론을 열고 지역 개발자들과 교류합니다. lines:7-7

- Arc에서 개발 중인 프로젝트의 진행 상황을 공유합니다. lines:7-7

- 기술 의견을 교환합니다. lines:7-7

- 생태계의 기회를 논의합니다. lines:7-7

- 지역 개발자 커뮤니티를 강화하는 것을 목표로 합니다. lines:7-7

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Lecter  Vu / Founder / Vitael [원문 그대로]

> Teddy Dinh / Moderator / Architect [원문 그대로]

> Lily Hoang / Founder / Fundline.xyz [원문 그대로]

> J Elias / Co-Founder / Vitael.xyz [원문 그대로]

> Miley Nguyen / Founder / Lootclaim [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 14-15행의 행사 날짜는 9월 4일이지만 days의 96-97행은 9월 2-3일로 기재되어 있습니다.

### 행사 050

> Member Check-In | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/bangledesh/events/member-check-in-or-regional-updates-and-live-demos-n0m4ich770)

페이지 일정 필드(UTC)는 2026-09-03T15:00:00.154Z부터 2026-09-03T15:59:48.871Z까지이며 표시 시간대는 Asia/Dhaka이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=True`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 방글라데시 지역 지부 회원을 위한 상호작용형 진행 상황 공유 모임입니다. lines:7-7

- Arc에서 만드는 결과물의 실시간 시연을 공유합니다. lines:7-7

- 진행 중인 통합 사례를 보여 주고 기술 의견을 교환합니다. lines:7-7

- 지역에서 실제로 겪는 문제와 기회를 논의합니다. lines:7-7

- 공개 티켓에는 정원이 찼다고 표시되어 있습니다. lines:77-77

- 공개 티켓에는 대기자 명단을 제공하지 않는다고 표시되어 있습니다. lines:82-82

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Sukanto Das / Co-Founder / Ababil Pay [원문 그대로]

> Motaleb Hossain / BD / Achswap [원문 그대로]

수집 시점의 공개 이벤트 데이터에서 만석으로 표시되어 있다.

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 14-15행의 행사 날짜는 9월 3일이지만 days의 66-67행은 8월 2-3일로 기재되어 있습니다.

### 행사 051

> Arc x Morpho: Midnight and Fixed-Rate Lending Onchain [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-x-morpho-midnight-and-fixed-rate-lending-onchain-xfkhlf407j)

페이지 일정 필드(UTC)는 2026-09-03T14:00:00.326Z부터 2026-09-03T15:00:28.715Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Midnight를 서로 분리되고 변경되지 않는 시장을 바탕으로 한 비수탁 고정금리, 고정기간 대출 프로토콜로 소개합니다. lines:7-7

- Morpho 공동 창업자 "Merlin Egalité"[원문 그대로]가 Morpho가 Midnight를 만든 이유를 설명합니다. lines:7-7

- 고정 만기, 담보와 제안(offers)의 작동 방식, 온체인 신용 상품을 설계할 때 고려할 사항을 다룹니다. lines:7-7

- 이러한 구상이 Arc 개발자에게 가질 수 있는 의미를 논의합니다. lines:7-7

- 대화 후 실시간 질의응답을 진행합니다. lines:7-7

- 면책 안내: 면책문구는 CTS가 소프트웨어 제공자이며 규제 금융 서비스나 자문 서비스를 제공하지 않는다고 설명합니다. lines:11-11

- 면책 안내: 면책문구는 이용자가 제공하는 서비스의 인허가와 관련 법률 준수 책임을 이용자에게 둡니다. lines:11-11

- 면책 안내: 면책문구는 Arc가 뉴욕주 금융서비스국의 검토나 승인을 받지 않았다고 설명합니다. lines:13-13

- 면책 안내: 면책문구는 제품 기능이 변경, 지연되거나 취소될 수 있다고 설명합니다. lines:15-15

- 면책 안내: 면책문구는 USDC를 Circle의 규제 대상 계열사가 발행하며 인허가 목록을 외부 링크에서 확인할 수 있다고 설명합니다. lines:17-17

- 면책 안내: 면책문구는 이 자료가 약정, 보증이나 투자 자문을 구성하지 않는다고 설명합니다. lines:15-15

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 052

> Technical Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/technical-office-hours-wyeu64jawb)

페이지 일정 필드(UTC)는 2026-09-03T12:00:00.981Z부터 2026-09-03T13:00:37.134Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=True`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=True`, `isFull=True`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Arc의 지갑과 계정 추상화(account abstraction)를 다룹니다. lines:7-7

- 개발자 관계 팀의 HJ가 진행합니다. lines:9-9

- 가스가 이미 USDC인 Arc에서 계정 추상화가 작동하는 방식과 지갑 제공자들의 현재 Arc 지원 상태를 공유합니다. lines:11-11

- 사전 준비를 원하는 참가자에게 Supporting Arc in Wallets와 계정 추상화 문서를 읽도록 안내합니다. lines:13-17

- 초대 요청 시 행사 관심사 입력란에 구체적인 Arc 기술 질문이나 막힌 문제를 적어야 하며 기술 질문이 없으면 승인되지 않을 수 있다고 안내합니다. lines:21-21

- 공개 티켓에는 정원이 찼다고 표시되어 있습니다. lines:58-58

- 공개 티켓에는 초대가 필요하다고 표시되어 있습니다. lines:59-59

- 공개 티켓에는 대기자 명단을 제공하지 않는다고 표시되어 있습니다. lines:63-63

수집 시점의 공개 이벤트 데이터에서 만석으로 표시되어 있다.

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 34행 이벤트 isInvitationOnly는 false이지만 35행 모든 티켓 초대 표시는 true이고 59행 티켓 isInvitationOnly도 true입니다.
- 15행 Supporting Arc in Wallets에는 본문에서 링크가 연결되어 있지 않습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://docs.arc.io/arc/tools/account-abstraction / 한국어 정리

### 행사 053

> Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/discord-office-hours-xu6aw0wx51)

페이지 일정 필드(UTC)는 2026-09-01T17:00:00.541Z부터 2026-09-01T17:45:52.432Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord에서만 진행하는 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계의 개발자들이 편하게 만나는 행사입니다. lines:7-7

- 질문을 하고 해당 주의 Arc 최신 소식을 이야기합니다. lines:7-7

- 본문의 Discord 이벤트 링크로 알림을 설정하도록 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 알림 링크는 이 배치에 있는 서로 다른 날짜의 Discord Office Hours 공고에서 동일합니다. 링크의 실제 행사 날짜는 확인하지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 054

> Bangladesh Build Club | Let’s Build on Arc [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/bangledesh/events/bangladesh-build-club-or-lets-build-on-arc-agnqffre60)

페이지 일정 필드(UTC)는 2026-08-31T15:00:00.806Z부터 2026-08-31T15:59:49.390Z까지이며 표시 시간대는 Asia/Dhaka이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

> test [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 방글라데시 개발자들이 Arc에서 실제 프로젝트를 함께 개발하는 모임입니다. lines:7-7

- 아이디어부터 코딩, 테스트, 배포까지 직접 실습합니다. lines:7-7

- 참가자들이 실시간으로 개발하며 문제를 공유하고 서로 돕습니다. lines:7-7

- 함께 배우고 실제 결과물을 개발하여 출시하는 것이 목표입니다. lines:7-7

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Sukanto Das / Co-Founder / Ababil Pay [원문 그대로]

> Motaleb Hossain / BD / Achswap [원문 그대로]

### 행사 055

> Uyo | Community Meetup | Building Your First Stablecoin Payment Flow [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/nigeria/events/uyo-or-community-meetup-or-building-your-first-stablecoin-payment-flow-qucn8i7jux)

페이지 일정 필드(UTC)는 2026-08-29T11:00:00.556Z부터 2026-08-29T15:00:17.382Z까지이며 표시 시간대는 Africa/Lagos이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Teckcocoon, 155, ikot Ekpene Road / Uyo / Akwa Ibom / Nigeria [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Uyo에서 처음 열리는 Arc 모임이며 Arc Testnet의 첫 스테이블코인 결제 흐름 개발을 돕습니다. lines:9-9

- 실시간으로 작동하는 스테이블코인 결제 흐름을 개발하고 배포합니다. lines:11-11

- 1초 미만의 거래 확정(deterministic finality)과 USDC로 표시되는 예측 가능한 가스 비용을 다룹니다. lines:11-11

- 핀테크 엔지니어와 개발자가 대상으로 언급됩니다. lines:11-11

- 코딩할 준비를 하고 참여하라고 안내합니다. lines:11-11

- Arc Testnet에서 작동하는 결제 프로토타입을 갖고 돌아가는 것을 제시합니다. lines:11-11

- 현장 장소는 Uyo의 Teckcocoon입니다. lines:13-13

### 행사 056

> Abuja | Community Meetup | Kickoff [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/nigeria/events/abuja-or-community-meetup-or-kickoff-508fmxpjzr)

페이지 일정 필드(UTC)는 2026-08-29T10:00:00.658Z부터 2026-08-29T14:30:00.658Z까지이며 표시 시간대는 Africa/Lagos이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Cafe One, 1st Floor, Sterling Bank Plaza, Mohammadu Buhari Way / Central Business District / Abuja / Nigeria [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Arc에서 제품을 개발하는 지역 개발자들이 실시간 개발, 데모, 대화와 교류에 참여합니다. lines:9-9

- 기존 제품에 스테이블코인을 통합하는 데 관심이 있는 창업자, 투자자, 제품 개발자가 대상으로 언급됩니다. lines:11-11

- 참가 혜택으로 교류와 Arc 제품 배포 실습을 제시합니다. lines:15-15

- 현장 장소는 Abuja의 Cafe One입니다. lines:13-13

- 연사 소개에서 UnitFlow Finance를 Arc 기반의 모듈형 스테이블코인 DeFi 프로토콜로 설명합니다. lines:65-65

- 해당 연사 소개에는 DEX, 대출, 예측 시장, 수익 농사와 국경 간 결제가 포함됩니다. lines:65-65

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Ashley Olika / Co Founder, CEO  / Owego [원문 그대로]

> Christopher)  Ekom (BTCmoney / Software Engineer / UnitFlow.Finance [원문 그대로]

> Paul Winner / Co-founder / BugBountyAi [원문 그대로]

### 행사 057

> Vietnam Office Hours | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/vietnam-office-hours-or-regional-updates-and-live-demos-defq9cs8wr)

페이지 일정 필드(UTC)는 2026-08-28T14:00:00.195Z부터 2026-08-28T15:00:22.208Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 베트남 지역 모임 구성원을 위한 주간 커뮤니티 토론입니다. lines:7-7

- 지역 개발자들이 서로 연결되고 커뮤니티를 강화하는 것을 목표로 합니다. lines:7-7

- Arc에서 개발 중인 프로젝트의 소식을 공유합니다. lines:7-7

- 기술 피드백을 교환하고 생태계 기회를 논의합니다. lines:7-7

- 연사 명단에 Vitael의 Lecter Vu가 기재되어 있습니다. lines:33-35

- 연사 명단에 Architect의 Teddy Dinh가 기재되어 있습니다. lines:43-45

- 연사 명단에 Sabi의 Bong Pink가 기재되어 있습니다. lines:53-55

- 연사 명단에 Railflow의 Long Le가 기재되어 있습니다. lines:63-65

- 연사 명단에 FluxAgent의 Nguyen Duc Trong가 기재되어 있습니다. lines:73-75

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Lecter  Vu / Founder / Vitael [원문 그대로]

> Teddy Dinh / Moderator / Architect [원문 그대로]

> Bong Pink / Founder / Sabi [원문 그대로]

> Long Le / Founder / Railflow [원문 그대로]

> Nguyen Duc  Trong / Founder / FluxAgent [원문 그대로]

### 행사 058

> Building the Agentic Economy with Fireblocks, Circle & Blockrun [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/building-the-agentic-economy-with-fireblocks-circle-and-blockrun-ufqf4memf0)

페이지 일정 필드(UTC)는 2026-08-27T22:00:00.216Z부터 2026-08-28T00:30:56.433Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> 5 Pennsylvania Plaza / New york / New York / USA [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- AI 에이전트의 서비스 탐색, API 호출과 실시간 결제를 다룹니다. lines:7-7

- 에이전트가 사람, 기업과 다른 소프트웨어를 대신하여 기능을 이용하고 거래하는 방식을 다룹니다. lines:9-9

- API와 서비스 제공자의 공개와 수익화, 양쪽을 연결하는 Circle Agent Stack을 다룹니다. lines:9-9

- 스타트업과 기업의 창업자, 운영자와 개발자가 대상으로 언급됩니다. lines:9-9

- Circle, Fireblocks, Dynamic과 Blockrun이 Fireblocks 본사에서 개최합니다. lines:11-11

- 체크인 때 피자와 음료를 제공합니다. lines:15-15

- 짧은 패널과 실시간 데모 뒤에 자유 교류 시간이 있습니다. lines:17-19

- Luma 등록 링크가 기재되어 있습니다. lines:34-34

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/lon7mu2d / 한국어 정리

### 행사 059

> Bangladesh Office Hours | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/bangledesh/events/bangladesh-office-hours-or-regional-updates-and-live-demos-5kcm3hhrwc)

페이지 일정 필드(UTC)는 2026-08-27T15:00:00.914Z부터 2026-08-27T15:59:31.529Z까지이며 표시 시간대는 Asia/Dhaka이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 방글라데시 지역 모임 구성원을 위한 격주 커뮤니티 토론입니다. lines:7-7

- 지역 개발자와 연결하고 Arc에서 개발 중인 프로젝트의 진행 상황을 공유합니다. lines:7-7

- 기술 피드백을 교환하고 생태계 기회를 논의합니다. lines:7-7

- 지역 개발자 커뮤니티를 강화하는 것이 목적입니다. lines:7-7

- 연사 소개에는 Arc Testnet에서 dapp을 개발 중인 Abu Tusher의 경험이 기재되어 있습니다. lines:58-58

- 연사 소개에는 BuildOrbit 창업자 Sahmed Zayan의 AI 자동화와 작업 시스템 학습이 기재되어 있습니다. lines:68-68

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Sukanto Das / Co-Founder / Ababil Pay [원문 그대로]

> Motaleb Hossain / BD / Achswap [원문 그대로]

> Abu Tusher / Builder & Founder  / ArcGrade [원문 그대로]

> Sahmed Zayan / Founder  / BuildOrbit [원문 그대로]

### 행사 060

> Arc x Chainlink: Data and Interoperability for Financial Applications [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-x-chainlink-data-and-interoperability-for-financial-applications-vjvv5i9n9c)

페이지 일정 필드(UTC)는 2026-08-27T14:00:00.481Z부터 2026-08-27T15:00:31.071Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 금융 애플리케이션에 필요한 시장 데이터와 체인 간 연결을 다룹니다. lines:7-7

- Chainlink와 Arc가 Arc 개발자의 인프라 구성에서 Chainlink의 역할을 설명합니다. lines:7-7

- Data Streams, Data Feeds, CCIP와 시작할 때의 실무 고려 사항을 다룹니다. lines:7-7

- 금융 애플리케이션 활용 사례와 실시간 커뮤니티 질의응답을 포함합니다. lines:7-7

- 개발자를 위한 실시간 방송과 세션입니다. lines:7-7

- 다시보기 URL이 기재되어 있습니다. lines:32-32

- 면책 안내: CTS는 소프트웨어 제공자이며 규제 대상 금융 또는 자문 서비스를 제공하지 않는다고 명시합니다. lines:11-11

- 면책 안내: 서비스 제공자가 필요한 허가와 법 준수를 책임진다고 명시합니다. lines:11-11

- 면책 안내: 뉴욕주 금융서비스국이 Arc를 검토하거나 승인하지 않았다고 명시합니다. lines:13-13

- 면책 안내: 제품 기능은 변경, 지연 또는 취소될 수 있고 보증이나 투자 조언을 구성하지 않는다는 면책문구가 있습니다. lines:15-15

- 면책 안내: USDC는 규제 대상 Circle 계열사가 발행하며 규제 인가 목록 링크를 제공합니다. lines:17-17

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.io/home/videos/arc-x-chainlink-data-and-interoperability-for-financial-applications-2026-08-27 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 061

> Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/discord-office-hours-zlmcyav6ym)

페이지 일정 필드(UTC)는 2026-08-25T17:00:00.895Z부터 2026-08-25T17:45:20.756Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord 전용 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계 개발자가 함께하는 비공식 모임입니다. lines:7-7

- 질문하고 그 주의 최신 Arc 소식을 논의합니다. lines:7-7

- Discord 이벤트 링크에서 알림을 받을 수 있다고 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행과 24행의 Discord 이벤트 URL은 다른 일시의 공고에서도 동일합니다. 해당 Discord 이벤트의 실제 대상 일시는 열지 않아 확인하지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 062

> Hackathon: Programmable Money [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/hackathon-programmable-money-74llz8htis)

페이지 일정 필드(UTC)는 2026-07-13T07:00:00.999Z부터 2026-08-22T23:00:00.999Z까지이며 표시 시간대는 Europe/London이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 앞선 부트캠프의 도구로 Arc 실제 제품을 만들며 아이디어에서 작동하는 프로토타입까지 4주를 제공합니다. lines:9-11

- 상위 팀은 8주 액셀러레이터에서 창업자와 전문가의 주간 워크숍, 진도와 목표를 점검하는 일대일 상담, 동료 개발자의 지원을 받습니다. lines:13-13

- Arc 배포 프로토타입, Wallets, Contracts, CCTP, Gateway, Paymaster와 Nanopayments의 명확한 활용, 실제 사용 사례와 제품화 경로를 요구하며 복잡성보다 구현 품질을 중시합니다. lines:17-23

- 작동하는 프런트엔드와 백엔드의 MVP, 핵심 기능과 Circle 도구 활용을 담은 3분 발표 및 데모 영상, 코드 저장소 링크를 제출합니다. lines:27-31

- 메타데이터에 DeFi와 Agentic Economy의 개발 부문이 있습니다. lines:52-79

- Launch event는 2026-07-13T16:00:00.000Z부터 16:30:00.000Z까지입니다. lines:158-161

- 프로젝트 생성, 팀 추가와 아이디어 공유는 2026-07-13T16:31:00.000Z부터 22:59:00.000Z까지입니다. lines:179-182

- 중간 제출에는 저장소와 발표 링크가 필요하며 2026-07-18T23:00:00.000Z부터 2026-07-19T22:59:00.000Z까지입니다. lines:200-203

- Keep Building은 2026-07-26이며 이 주에는 제출할 것이 없다고 표시합니다. lines:221-224

- 최종 제출은 2026-08-01T23:00:00.000Z부터 2026-08-02T22:59:00.000Z까지입니다. lines:242-245

- 데모 전 기술 점검은 2026-08-13T14:00:00.000Z부터 16:30:00.000Z까지입니다. lines:263-266

- Demo Day는 2026-08-20T16:00:00.000Z부터 17:00:00.000Z까지입니다. lines:284-287

- 공개 메타데이터는 시작 2026-07-13T07:00:00.999Z, 종료 2026-08-22T23:00:00.999Z, 시간대 Europe/London를 기록합니다. lines:40-42

- 공개 티켓은 Free Ticket이며 표시 가격은 0입니다. lines:357-357

- 온라인 여부는 true이고 초대 전용 여부는 false입니다. lines:45-47

- 발표자 목록은 Corey Cooper의 직함을 Senior Manager, Developer Relations and Ecosystem Marketing, 소속을 Circle로 기록합니다. lines:87-89

- 발표자 목록은 Jenna Teeman의 직함을 Principle Program Manager, Developer Marketing, 소속을 Circle로 기록합니다. lines:97-99

- 발표자 목록은 Anthony Kelani의 직함을 Director of Ecosystem Growth, 소속을 Circle로 기록합니다. lines:107-109

- 발표자 목록은 Blessing Adesiji의 직함을 Developer Relations Manager, EMEA, 소속을 Circle로 기록합니다. lines:117-119

- 발표자 목록은 Sam Sealey의 직함을 Director, Community, 소속을 Circle로 기록합니다. lines:127-129

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Corey Cooper / Senior Manager, Developer Relations and Ecosystem Marketing / Circle [원문 그대로]

> Jenna Teeman / Principle Program Manager, Developer Marketing  / Circle [원문 그대로]

> Anthony Kelani / Director of Ecosystem Growth  / Circle [원문 그대로]

> Blessing Adesiji / Developer Relations Manager, EMEA / Circle [원문 그대로]

> Sam Sealey / Director, Community  / Circle [원문 그대로]

공개 세션은 다음과 같다. 제목과 설명은 원문 표기를 유지하며 시각은 각 세션의 UTC 데이터다.

> Launch event [원문 그대로]

세션 시각: `2026-07-13T16:00:00.000Z` - `2026-07-13T16:30:00.000Z`.

> Milestone Deadline: Create Your Project, Add Your Team, Share Your Idea [원문 그대로]

세션 시각: `2026-07-13T16:31:00.000Z` - `2026-07-13T22:59:00.000Z`.

> Milestone Deadline: Mid-Hackathon Check Point [원문 그대로]

세션 시각: `2026-07-18T23:00:00.000Z` - `2026-07-19T22:59:00.000Z`.

> Submit your mid-hackathon milestone! You'll need your repo and presentation links. [원문 그대로]

> Keep Building [원문 그대로]

세션 시각: `2026-07-26T19:30:00.000Z` - `2026-07-26T22:59:00.000Z`.

> Nothing due this week [원문 그대로]

> Milestone Deadline: Final Submissions [원문 그대로]

세션 시각: `2026-08-01T23:00:00.000Z` - `2026-08-02T22:59:00.000Z`.

> Submit your final project! [원문 그대로]

> Pre-demo day tech check [원문 그대로]

세션 시각: `2026-08-13T14:00:00.000Z` - `2026-08-13T16:30:00.000Z`.

> Demo Day [원문 그대로]

세션 시각: `2026-08-20T16:00:00.000Z` - `2026-08-20T17:00:00.000Z`.

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문 개발 기간은 4주지만 전체 이벤트 메타데이터와 기술 점검 및 Demo Day는 더 넓은 기간을 기록합니다. lines:11,40-41,263-287을 구분합니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://www.encodeclub.com/programmes/arc-hackathon?scheduleTab=319 / 한국어 정리

### 행사 063

> Ankara: Community Meetup [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/turkey/events/ankara-community-meetup-cf5a024sn2)

페이지 일정 필드(UTC)는 2026-08-22T13:00:00.992Z부터 2026-08-22T15:00:00.992Z까지이며 표시 시간대는 Turkey이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Ground Zero coffee, Çiğdem, 1552. Sk. 1/7, 06530 Çankaya/Ankara [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Ankara에서 처음 열리는 Arc 현장 모임입니다. lines:9-9

- Arc 커뮤니티가 커뮤니티를 위해 주최하는 행사입니다. lines:11-11

- 창업자, 개발자, 프로토콜 설계자, 기관 개발자와 AI 개발자를 모읍니다. lines:11-11

- 이미 Arc에서 개발하는 사람과 스테이블코인 인프라 및 AI 에이전트에 관심만 있는 사람도 대상으로 언급합니다. lines:11-11

- 대화, 새로운 인맥과 지역 Arc 커뮤니티의 출발을 제시합니다. lines:13-13

- 장소는 Ground Zero coffee입니다. lines:19-19

- 주최자는 Veli Uysal입니다. lines:21-21

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://share.google/LC1ynGmtLjLoduh2B / 한국어 정리
- https://www.linkedin.com/in/veliuysal/ / 한국어 정리

### 행사 064

> Enugu Community Meetup | Nsukka Build Club [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/nigeria/events/enugu-community-meetup-or-nsukka-build-club-om3yk9xhhq)

페이지 일정 필드(UTC)는 2026-08-22T11:00:38.356Z부터 2026-08-22T15:00:00.000Z까지이며 표시 시간대는 Africa/Lagos이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> The Block Hive (Opp. UNN Main Gate & Beside MTN Office), Nsukka, Enugu State / https://maps.app.goo.gl/GFm1Aw9UbCtoEM387?g_st=ic / Nsukka / Enugu / Nigeria [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Web3 스타트업, 개발자, 창업자와 제품 팀을 위한 개발자 중심 행사입니다. lines:9-9

- 개발자와 Arc 생태계를 연결하고 현재 개발 내용을 살펴봅니다. lines:11-11

- Arc의 스테이블코인 인프라로 개발, 통합과 확장을 할 기회를 탐색합니다. lines:11-11

- Nsukka의 The Block Hive에서 열리며 UNN 정문 맞은편, MTN 사무소 옆으로 안내합니다. lines:13-15

- 연사 소개에는 Arc 기반 UnitFlow Finance와 DEX, 대출, 예측 시장, 수익 농사, 국경 간 결제의 개발 경험이 기재되어 있습니다. lines:87-87

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Kevin Chibuoyim / Founder / The Block Hive [원문 그대로]

> Panchu Vijay Pal / Co-Founder / Xylonet [원문 그대로]

> James Chukwu / Game Designer  / VeritySports [원문 그대로]

> Christopher)  Ekom (BTCmoney / Software Engineer / UnitFlow.Finance [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://maps.app.goo.gl/GFm1Aw9UbCtoEM387?g_st=ic / 한국어 정리

### 행사 065

> Member Check-In | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/bangledesh/events/member-check-in-or-regional-updates-and-live-demos-rzslz3bjbt)

페이지 일정 필드(UTC)는 2026-08-20T15:00:00.225Z부터 2026-08-20T15:59:54.638Z까지이며 표시 시간대는 Asia/Dhaka이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=True`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 방글라데시 지역 모임 구성원을 위한 상호작용형 체크인입니다. lines:7-7

- Arc에서 개발한 내용을 실시간 데모로 공유하고 활성 통합을 보여 줍니다. lines:7-7

- 기술 피드백을 교환합니다. lines:7-7

- 지역의 실제 과제와 기회를 논의합니다. lines:7-7

- 무료 티켓은 만석으로 표시되어 있습니다. lines:77-77

- 대기 명단은 제공되지 않는 것으로 표시되어 있습니다. lines:82-82

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Sukanto Das / Co-Founder / Ababil Pay [원문 그대로]

> Motaleb Hossain / BD / Achswap [원문 그대로]

수집 시점의 공개 이벤트 데이터에서 만석으로 표시되어 있다.

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 14행의 시작 일시는 2026-08-20T15:00:00.225Z인데 66행 days.startAt은 2026-08-20T18:00:00.000Z로 그보다 늦습니다. 어떤 필드가 운영 일정을 나타내는지는 본문에 설명되어 있지 않습니다.

### 행사 066

> Vietnam Office Hours | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/vietnam-office-hours-or-regional-updates-and-live-demos-jnpwdd6aod)

페이지 일정 필드(UTC)는 2026-08-20T14:00:00.627Z부터 2026-08-20T15:00:15.556Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 베트남 지역 모임 구성원을 위한 주간 커뮤니티 토론입니다. lines:7-7

- 지역 개발자들이 서로 연결되고 커뮤니티를 강화하는 것을 목표로 합니다. lines:7-7

- Arc에서 개발 중인 프로젝트의 소식을 공유합니다. lines:7-7

- 기술 피드백을 교환하고 생태계 기회를 논의합니다. lines:7-7

- 연사 명단에 Vitael의 Lecter Vu가 기재되어 있습니다. lines:33-35

- 연사 명단에 Architect의 Teddy Dinh가 기재되어 있습니다. lines:43-45

- 연사 명단에 HushCash의 Kien Trinh가 기재되어 있습니다. lines:53-55

- 연사 명단에 Papercut의 Davey Cao가 기재되어 있습니다. lines:63-65

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Lecter  Vu / Founder / Vitael [원문 그대로]

> Teddy Dinh / Moderator / Architect [원문 그대로]

> Kien Trinh / Founder / HushCash [원문 그대로]

> Davey Cao / Founder / Papercut [원문 그대로]

### 행사 067

> Technical Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/technical-office-hours-zs4bml6imf)

페이지 일정 필드(UTC)는 2026-08-20T12:00:00.710Z부터 2026-08-20T13:00:30.010Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=True`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=True`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- DevRel 팀의 Elton이 세션을 진행합니다. lines:9-9

- Arc와 기존 EVM 체인의 차이점과 동일한 점을 다룹니다. lines:11-11

- 미리 문서를 읽어도 좋다고 안내합니다. lines:13-13

- 사전 자료로 EVM differences 문서를 제공합니다. lines:15-15

- 사전 자료로 USDC의 두 인터페이스를 다룬 One token, two interfaces 글을 제공합니다. lines:17-17

- 초대 요청 양식의 관심 사항 칸에 구체적인 Arc 기술 질문 또는 장애물을 입력하도록 요구합니다. lines:21-21

- 기술 질문이 없는 요청은 승인되지 않을 수 있다고 명시합니다. lines:21-21

- 모든 티켓이 초대 전용으로 표시되어 있습니다. lines:35-35

- 다시보기 URL이 기재되어 있습니다. lines:36-36

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 34행 isInvitationOnly는 false지만 35행 isAllTicketOptionsInvitationOnly와 60행 티켓 isInvitationOnly는 true입니다. 21행 본문은 기술 질문을 기재한 초대 요청을 요구합니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://circle-com.wistia.com/medias/nomviw7ykk / 한국어 정리
- https://docs.arc.io/arc/references/evm-differences / 한국어 정리
- https://www.arc.io/blog/building-with-usdc-on-arc-one-token-two-interfaces / 한국어 정리

### 행사 068

> Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/discord-office-hours-kfv9mhukea)

페이지 일정 필드(UTC)는 2026-08-18T17:00:00.536Z부터 2026-08-18T17:45:15.637Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord 전용 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계 개발자가 함께하는 비공식 모임입니다. lines:7-7

- 질문하고 그 주의 최신 Arc 소식을 논의합니다. lines:7-7

- Discord 이벤트 링크에서 알림을 받을 수 있다고 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행과 24행의 Discord 이벤트 URL은 다른 일시의 공고에서도 동일합니다. 해당 Discord 이벤트의 실제 대상 일시는 열지 않아 확인하지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 069

> Arc Coworking & Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-coworking-and-demos-yki7vrukh2)

페이지 일정 필드(UTC)는 2026-08-17T17:30:00.919Z부터 2026-08-17T19:00:00.919Z까지이며 표시 시간대는 Europe/London이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Encode Hub, 41 Pitfield St, London N1 6DA, UK / London / UK [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 개발 진척, 짧은 데모와 대화를 중심으로 하는 커뮤니티 저녁 행사입니다. lines:7-7

- 프로그래밍 가능한 돈, 결제, 스테이블코인과 온체인 금융 분야를 다룹니다. lines:7-7

- Encode가 Arc 및 Circle과 협력하여 주최합니다. lines:9-9

- 소수의 팀, 창업자와 개발자가 짧게 발표한 뒤 토론과 교류를 진행합니다. lines:9-9

- 정기적으로 결과물을 보여 주고 피드백을 받으며 협업자를 만나는 자리를 목표로 합니다. lines:11-11

- 개발자, 스타트업 팀, 창업자, 운영자와 커뮤니티 구성원을 대상으로 합니다. lines:13-13

- Encode Hub의 런던 주소가 기재되어 있습니다. lines:33-33

- Luma 등록 링크가 기재되어 있습니다. lines:28-28

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/bbjn8d61 / 한국어 정리

### 행사 070

> HCMC | Community Meetup & New Location Kickoff: The Stablecoin Movement [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/hcmc-or-community-meetup-and-new-location-kickoff-the-stablecoin-movement-1s1r2ck6sm)

페이지 일정 필드(UTC)는 2026-08-16T02:05:00.166Z부터 2026-08-16T05:00:44.935Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> G Floor, Home Hotel - 158 Nguyen Dinh Chinh str - Phu Nhuan Ward - Ho Chi Minh City / Ho Chi Minh City / Phu Nhuan Ward / Viet Nam [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 스테이블코인이 세계 결제, 저축과 투자를 바꾸는 방식을 논의합니다. lines:7-7

- 스테이블코인이 차세대 금융 애플리케이션의 기반이 되는 이유를 논의합니다. lines:7-7

- Arc가 이러한 변화를 뒷받침하는 인프라를 개발하는 방식을 논의합니다. lines:7-7

- 베트남의 개발자와 이용자에게 생기는 기회를 다룹니다. lines:7-7

- 장소는 호찌민 Home Hotel의 G Floor로 기재되어 있습니다. lines:26-26

### 행사 071

> Buenos Aires | Arc Builder Circle: Building with Lo-Fi & arc_fajores 🍪 [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/argentina/events/buenos-aires-or-arc-builder-circle-building-with-lo-fi-and-arc_fajores-gbuspnbdjf)

페이지 일정 필드(UTC)는 2026-08-15T17:00:00.478Z부터 2026-08-15T22:00:00.478Z까지이며 표시 시간대는 America/Argentina/Buenos_Aires이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Malabia 806, C1414 Cdad. Autónoma de Buenos Aires / Café Nómada Villa Crespo / Buenos Aires / Argentina [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 부에노스아이레스에서 격주로 열리는 개발 모임입니다. lines:19-19

- 참가 개발자는 자신의 프로젝트를 가져옵니다. lines:21-21

- Pomodoro 작업 시간을 반복하고 라운드 사이에 진행 상황을 공유합니다. lines:21-21

- 필터 커피와 arc_fajores 간식을 제공합니다. lines:21-21

- 당일 가장 많이 진척한 참가자에게 100 USDC를 제공합니다. lines:23-23

- 2주 뒤 재모임에서는 그 기간 동안 가장 많이 진척한 참가자에게 100 USDC를 제공합니다. lines:23-23

- 장소는 "Café Nómada Villa Crespo"[원문 그대로]로 기재되어 있습니다. lines:41-41

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Tomás Cordero / Indie Hacker / Founder / BuFi [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 30행 startedAt은 2026-08-15T17:00:00.478Z지만 81-82행 days는 2026-08-05T03:00:00.000Z부터 2026-08-06T02:59:59.999Z까지로 기재되어 있습니다. 23행의 most progress 평가 기준은 본문에 구체화되어 있지 않습니다.

### 행사 072

> HCMC | Campus Meetup | University Tour Kickoff: Van Lang University [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/hcmc-or-campus-meetup-or-university-tour-kickoff-van-lang-university-lsr80gscp9)

페이지 일정 필드(UTC)는 2026-08-15T03:00:00.634Z부터 2026-08-15T05:00:00.502Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> 69/68 Dang Thuy Tram Street, An Nhon Ward, Ho Chi Minh City, Vietnam / Ho Chi Minh City / An Nhon Ward / Việt Nam [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 베트남 전역의 대학생에게 스테이블코인, 온체인 금융과 Arc 애플리케이션 개발을 소개하는 교육 프로그램입니다. lines:9-9

- 캠퍼스 모임, 워크숍과 교류 세션으로 블록체인 기초와 개발 기회를 제공합니다. lines:11-11

- Van Lang University 행사가 2026년 전국 대학 행사 시리즈를 시작합니다. lines:13-13

- 베트남 대학생 학습 및 경쟁 프로그램 UniHackfest와 협력합니다. lines:15-15

- UniHackfest는 시장 통찰과 AI 기반 제품 사고를 데모 가능한 Web3 제품 개발로 연결합니다. lines:15-15

- Arc의 스테이블코인과 온체인 금융 비전을 배웁니다. lines:21-21

- Arc 개발 도구, 문서와 기술 자료로 개발을 시작하는 방식을 탐색합니다. lines:25-25

- Arc에서 개발 중인 프로젝트와 애플리케이션의 실시간 데모를 봅니다. lines:27-27

- 베트남 Web3의 개발자, 창업자와 학생을 만나고 생태계 기회를 배웁니다. lines:29-29

- 호찌민의 행사장 주소가 기재되어 있습니다. lines:50-50

### 행사 073

> Bangladesh Office Hours | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/bangledesh/events/bangladesh-office-hours-or-regional-updates-and-live-demos-nco9ehcls0)

페이지 일정 필드(UTC)는 2026-08-13T15:00:00.220Z부터 2026-08-13T15:59:33.433Z까지이며 표시 시간대는 Asia/Dhaka이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 방글라데시 지역 모임 구성원을 위한 격주 커뮤니티 토론입니다. lines:7-7

- 지역 개발자와 연결하고 Arc에서 개발 중인 프로젝트의 진행 상황을 공유합니다. lines:7-7

- 기술 피드백을 교환하고 생태계 기회를 논의합니다. lines:7-7

- 지역 개발자 커뮤니티를 강화하는 것이 목적입니다. lines:7-7

- 연사 명단에는 Achswap의 블록체인 개발자 Asif Iqbal이 포함됩니다. lines:53-55

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Sukanto Das / Co-Founder / Ababil Pay [원문 그대로]

> Motaleb Hossain / BD / Achswap [원문 그대로]

> Asif Iqbal / Blockchain Developer / Achswap [원문 그대로]

### 행사 074

> Vietnam Office Hours | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/vietnam-office-hours-or-regional-updates-and-live-demos-bkcyxswfuy)

페이지 일정 필드(UTC)는 2026-08-13T14:00:00.195Z부터 2026-08-13T15:00:34.171Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 베트남 지역 모임 구성원을 위한 주간 커뮤니티 토론입니다. lines:7-7

- 지역 개발자들이 서로 연결되고 커뮤니티를 강화하는 것을 목표로 합니다. lines:7-7

- Arc에서 개발 중인 프로젝트의 소식을 공유합니다. lines:7-7

- 기술 피드백을 교환하고 생태계 기회를 논의합니다. lines:7-7

- 연사 명단에 Vitael의 Lecter Vu가 기재되어 있습니다. lines:33-35

- 연사 명단에 Architect의 Teddy Dinh가 기재되어 있습니다. lines:43-45

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Lecter  Vu / Founder / Vitael [원문 그대로]

> Teddy Dinh / Moderator / Architect [원문 그대로]

### 행사 075

> Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/discord-office-hours-auknpvyjrh)

페이지 일정 필드(UTC)는 2026-08-11T17:00:00.507Z부터 2026-08-11T17:45:32.519Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord 전용 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계 개발자가 함께하는 비공식 모임입니다. lines:7-7

- 질문하고 그 주의 최신 Arc 소식을 논의합니다. lines:7-7

- Discord 이벤트 링크에서 알림을 받을 수 있다고 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행과 24행의 Discord 이벤트 URL은 다른 일시의 공고에서도 동일합니다. 해당 Discord 이벤트의 실제 대상 일시는 열지 않아 확인하지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 076

> Circle: From Demo to Deployed — Building a Paying Agent Live [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/circle-from-demo-to-deployed-building-a-paying-agent-live-mjab6tyudf)

페이지 일정 필드(UTC)는 2026-08-10T18:00:00.958Z부터 2026-08-10T18:30:00.958Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 사람이 결제 버튼을 눌러야 멈춰 있는 에이전트가 스스로 결제하도록 개발하는 세션입니다. lines:7-7

- Harshal Bhangale과 Danny Organ이 Steve 자율 에이전트 실험에서 실제 돈과 시장을 다룬 경험을 소개합니다. lines:11-11

- Circle CLI와 Marketplace를 Claude 또는 Cursor와 사용하여 에이전트의 지갑, 지출 규칙과 배포를 실시간으로 개발합니다. lines:13-13

- 지출 상한, 서비스별 한도, 허용 목록과 제한된 세션 시간을 다룹니다. lines:25-25

- 결제를 부가 기능으로 다룰 때의 실수를 다룹니다. lines:27-27

- 자신의 프로젝트에서 재현할 수 있는 참고 구현을 제공한다고 안내합니다. lines:33-33

- 50,000달러 Agentic Economy Prize는 Build with Gemini XPRIZE 참가자만을 대상으로 합니다. lines:39-39

- AI 에이전트의 자율 결제가 사업의 핵심인 스타트업 팀을 시상 대상으로 제시합니다. lines:39-39

- 정해진 규칙 안에서 에이전트가 실제로 지급하거나 받는 거래를 보여 주어야 합니다. lines:39-39

- 거래는 실환경 또는 운영 환경으로의 경로가 명확한 테스트넷에서 실행되어야 합니다. lines:39-39

- 참가 자격이 있는 사람은 Build with Gemini XPRIZE 제출 때 별도 상금 경쟁에 참여를 선택할 수 있습니다. lines:45-45

- 면책 안내: 이 상은 Circle이 독립적으로 자금을 제공하고 운영하며 심사합니다. lines:45-45

- 면책 안내: XPRIZE와 Devpost는 해당 상의 제출물 평가에 관여하지 않습니다. lines:45-45

- 전체 규칙과 심사 기준은 Circle이 발표할 예정이라고 명시합니다. lines:45-45

- 에이전트 간, 에이전트와 서비스 간, 에이전트와 판매자 간 돈 거래를 개발하는 사람을 대상으로 합니다. lines:43-43

- 개발자가 흔히 선택하는 첫 활용 사례를 주말 동안 연결하는 방법을 다룹니다. lines:23-23

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 45행은 전체 규칙과 심사 기준을 Circle이 발표할 예정이라고 명시합니다. 공고 자체만으로 전체 대회 자격과 심사 기준을 확인할 수는 없습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/moonshots-o2dg / 한국어 정리
- https://www.geminixprize.com/agentic-payments / 한국어 정리
- https://www.geminixprize.com/agentic-payments?utm_source=luma / 한국어 정리
- https://youtube.com/live/wRBhdq4Ubz8?feature=share&utm_source=luma / 한국어 정리

### 행사 077

> Hackathon: The Stablecoins Commerce Stack Challenge [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/hackathon-the-stablecoins-commerce-stack-challenge-ozc0ih6kba)

페이지 일정 필드(UTC)는 2026-04-14T04:00:00.153Z부터 2026-08-09T04:00:00.153Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Dubai / UAE [원문 그대로]

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Hybrid`로 표시되어 있다.

- Ignyte가 주관하고 Circle과 Arc가 기술 후원하는 3개월 온라인 프로그램으로 소개합니다. lines:7-7

- 개발자들이 스테이블코인으로 지역의 주요 기회를 탐색하는 프로그램입니다. lines:7-7

- 국경 간 결제와 송금을 다룹니다. lines:9-9

- 중소기업 금융과 무역 절차를 다룹니다. lines:11-11

- 토큰화 자산과 법규를 준수하는 DeFi를 다룹니다. lines:13-13

- 에이전트 경제를 다룹니다. lines:15-15

- Arc에서 Circle 개발 플랫폼을 사용하는 후원 현상금 기회에 경쟁할 수 있습니다. lines:17-17

- Ignyte의 상세 정보 및 등록 링크를 제공합니다. lines:19-19

- 구조화 정보는 참가 방식을 Hybrid로 표시합니다. lines:30-30

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 7행은 3-month virtual program이라고 설명하지만 26-27행의 시작과 종료는 2026-04-14T04:00:00.153Z와 2026-08-09T04:00:00.153Z이며 30행과 81행은 Hybrid입니다. 프로그램 기간과 실제 참가 방식의 차이는 이 공고만으로 해결할 수 없습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://app.ignyte.ae/public/challenges/4B436318-C737-F111-9A49-6045BD14D400 / 한국어 정리

### 행사 078

> Region Updates: Brasil Roundtable Discussion [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/brazil/events/region-updates-brasil-roundtable-discussion-zdgy060y8h)

페이지 일정 필드(UTC)는 2026-08-07T22:00:00.000Z부터 2026-08-08T00:00:00.000Z까지이며 표시 시간대는 America/Sao_Paulo이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 브라질 지역 Arc 구성원의 주간 토론입니다. lines:7-7

- 현재 개발하는 내용과 개발을 생각 중인 내용을 공유합니다. lines:7-7

- 지역의 스테이블코인 활용 사례를 논의합니다. lines:7-7

- 지역 기회와 장애물을 드러내어 논의합니다. lines:7-7

- 연사 명단에 Parabuilders의 Thiago Monteiro가 포함됩니다. lines:33-35

- 연사 명단에 Transfero의 Douglas Miranda가 포함됩니다. lines:43-45

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Thiago Monteiro / Developer Relations / Parabuilders [원문 그대로]

> Douglas Miranda / Growth Manager / Transfero [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 14-15행 행사는 2026-08-07T22:00:00.000Z부터 2026-08-08T00:00:00.000Z까지이나 66-67행 days는 2026-08-06T03:00:00.000Z부터 2026-08-07T02:59:59.999Z까지입니다.

### 행사 079

> Buenos Aires | Dev3Pack — Robotics Developer Meetup & Machine Economy 101 [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/argentina/events/buenos-aires-or-dev3pack-robotics-developer-meetup-and-machine-economy-101-ghe4au9xmq)

페이지 일정 필드(UTC)는 2026-08-07T20:00:00.645Z부터 2026-08-07T23:13:03.445Z까지이며 표시 시간대는 America/Buenos_Aires이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Dorrego 2133, Palermo / HUERTA Dorrego / Cdad. Autónoma de Buenos Aires / CABA / Argentina [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Dev3pack과 Arc Argentina가 AI Whisperers 및 Women in Robotics와 함께 하드웨어, AI와 기계 간 결제에 관한 3시간 실습을 제공합니다. lines:111-117

- 17:00-17:40에는 체크인, 커뮤니티 만남, 작업 환경 설정과 주최 커뮤니티 소개가 있습니다. lines:121-129

- 17:40-18:00에 "Tomás Cordero"[원문 그대로]가 기계와 AI 에이전트 사이의 초소액 결제(nanopayments)와 Circle Gateway를 통한 자율 자금 이동을 소개합니다. lines:131-135

- 18:00-19:00에 Stewart가 ESP32 실습으로 마이크로컨트롤러 개념, Arduino 및 컴퓨터와의 비교, 개발 환경, 기본 프로그래밍, LED 제어와 물리 부품 상호작용을 다룹니다. lines:137-155

- 19:00-20:00에 Iri가 전자공학 기초, 부품과 회로 제작, 입출력과 센서 및 구동기, Arduino 생태계와 하드웨어 및 소프트웨어 연결을 가르칩니다. lines:157-171

- 로봇공학, 자동화, IoT와 기계 경제에 참여하는 장치를 계속 탐구할 기초를 갖추도록 설명합니다. lines:173-173

- 노트북은 필수이며 컴퓨터에 맞는 USB-C 또는 USB-A 케이블과 미리 가입한 Circle Console 계정이 필요합니다. lines:177-185

- 활동 중 ESP32 보드를 빌려 줍니다. lines:189-189

- 하드웨어에 관심 있는 개발자, 학생, 제작자와 로봇공학, 전자공학, IoT, AI 및 기계 간 결제에 관심 있는 초보자를 대상으로 합니다. 로봇공학이나 웹3 경험은 필요하지 않으며 기본 프로그래밍 지식이면 충분합니다. lines:193-203

- 모든 참가자가 하드웨어 실습을 할 수 있도록 정원을 제한합니다. lines:205-205

- 공식 참가자 명단은 Dev3Pack의 Luma 행사 페이지에서 관리합니다. lines:207-209

- 대면 장소는 Argentina Buenos Aires의 HUERTA Dorrego, Dorrego 2133, Palermo입니다. lines:228-232

- 공개 메타데이터는 시작 2026-08-07T20:00:00.645Z, 종료 2026-08-07T23:13:03.445Z, 시간대 America/Buenos_Aires를 기록합니다. lines:216-218

- 공개 티켓은 Free Ticket이며 표시 가격은 0입니다. lines:287-287

- 온라인 여부는 false이고 초대 전용 여부는 false입니다. lines:221-223

- 발표자 목록은 "Tomás Cordero"[원문 그대로]의 직함을 Indie Hacker / Founder, 소속을 BuFi로 기록합니다. lines:245-247

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Tomás Cordero / Indie Hacker / Founder / BuFi [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- [연결 주소](https://console.circle.com/signup)는 이번 요청에서 HTTP 403로 본문을 확보하지 못했다.
- https://luma.com/z17lxw31 / 한국어 정리
- https://luma.com/z17lxw31?tk=8lFSEy / 한국어 정리

### 행사 080

> Vietnam Office Hours | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/vietnam-office-hours-or-regional-updates-and-live-demos-jzsafxlgzs)

페이지 일정 필드(UTC)는 2026-08-06T14:00:00.082Z부터 2026-08-06T15:00:09.877Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 베트남 지역 모임 회원을 위한 주간 커뮤니티 토론입니다. lines:7-7

- 지역 개발자와 연결하고 Arc 개발 소식을 공유하며 기술 피드백을 교환합니다. lines:7-7

- 생태계 기회를 논의하고 지역 개발자 커뮤니티를 강화합니다. lines:7-7

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Lecter  Vu / Founder / Vitael [원문 그대로]

> Teddy Dinh / Moderator / Architect [원문 그대로]

### 행사 081

> Member Check-In | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/bangledesh/events/member-check-in-or-regional-updates-and-live-demos-tff0ezznsk)

페이지 일정 필드(UTC)는 2026-08-04T15:00:00.061Z부터 2026-08-04T15:59:00.061Z까지이며 표시 시간대는 Asia/Dhaka이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=True`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 방글라데시 지역 모임 회원을 위한 상호 참여형 진행 점검입니다. lines:7-7

- Arc에서 개발하는 결과물의 실시간 데모와 실제 통합을 보여 줍니다. lines:7-7

- 기술 의견을 교환하며 지역의 실제 문제와 기회를 논의합니다. lines:7-7

- 티켓의 isFull은 true이며 대기 명단 기능은 false입니다. lines:86-91

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Sukanto Das / Co-Founder / Ababil Pay [원문 그대로]

> Motaleb Hossain / BD / Achswap [원문 그대로]

수집 시점의 공개 이벤트 데이터에서 만석으로 표시되어 있다.

### 행사 082

> Ilorin | Community Meetup | Building Your First Stablecoin Payment Flow [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/nigeria/events/ilorin-or-community-meetup-or-building-your-first-stablecoin-payment-flow-lo0v5r2lrj)

페이지 일정 필드(UTC)는 2026-08-01T10:00:00.532Z부터 2026-08-01T15:00:18.215Z까지이며 표시 시간대는 Africa/Lagos이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Ilorin Innovation Hub, 9a Ahmadu Bello Way, GRA / Ilorin / Kwara State / Nigeria [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Ilorin의 첫 Arc 모임에서 개발자의 첫 스테이블코인 결제 흐름 구현을 돕습니다. lines:9-9

- Arc 테스트넷에서 작동하는 스테이블코인 결제 흐름을 개발하고 배포합니다. lines:11-11

- 1초 미만의 거래 확정(deterministic finality)과 예측 가능한 USDC 표시 가스비를 활용하는 방법을 배웁니다. lines:11-11

- 핀테크 엔지니어와 개발자가 코딩과 교류를 준비하고 테스트넷에서 작동하는 결제 프로토타입을 가져가도록 안내합니다. lines:11-11

- 장소는 Ilorin Innovation Hub, 9a Ahmadu Bello Way, GRA입니다. lines:13-13

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Jerry Ojumah / Ecosystem Builder / Onboard [원문 그대로]

> Ridwan  Jokanola (Ade) / Blockchain developer  / Arcade [원문 그대로]

> Paul  Adesina / Co Founder / AfriFleet [원문 그대로]

> Ibrahim AbdulGanniy Temitope / Co-founder / Tella [원문 그대로]

> Treasure Bamigboye / Co-founder / Telianza [원문 그대로]

### 행사 083

> Rio | Builders Sunset Meetup | Region Event Mixer [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/brazil/events/rio-or-builders-sunset-meetup-or-region-event-mixer-34r8rzeg8s)

페이지 일정 필드(UTC)는 2026-07-31T20:00:00.559Z부터 2026-07-31T23:00:20.132Z까지이며 표시 시간대는 Brazil/East이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Terraças de Camboinhas / Niterói / Rio de Janeiro / Brazil [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Rio de Janeiro에서 월례 Arc Brasil 공식 모임을 통해 브라질 지부를 출범하고 개발자, 창업자, 교육자와 핀테크 관계자를 글로벌 생태계와 연결합니다. lines:7-7

- 본문은 브라질의 Pix, BRZ를 포함한 스테이블코인 확산과 실물 자산 토큰화 및 온체인 금융 관심을 기회로 제시합니다. BRZ의 중앙은행 인정은 공고의 주장입니다. lines:9-9

- 활동하는 브라질 개발자 그룹, 지역 개발자의 Arc 인지도와 활용, 후속 워크숍 및 해커톤 참가자 연결과 다른 도시로의 확장을 기대합니다. lines:19-19

- 스테이블코인 가스, 1초 미만 최종 확정과 선택형 거래 비공개 기능을 소개하고 초기 프로젝트 대화 및 정기 커뮤니티 활동을 추진합니다. lines:23-23

- 17:00-17:30에는 공동 작업과 도착 후 개발자 만남 및 프로젝트 대화를 진행합니다. lines:27-27

- 17:30-18:00에는 Arc 비전과 브라질 지부를 소개하며 포르투갈어 자막 영상을 상영합니다. lines:29-29

- 18:30-19:30에는 브라질과 중남미 개발자 대상 스테이블코인, 실물 자산, 금융 접근성과 국가 간 결제를 다루고 참가자의 실제 다음 행동을 설명합니다. lines:31-31

- 19:30-20:00에는 바비큐를 곁들인 해피아워와 교류 및 협업 탐색을 진행합니다. lines:33-33

- 본문 장소는 Rio Crypto Hub, "Terraças de Camboinhas"[원문 그대로]의 casa 16으로 표기합니다. lines:17-17

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Douglas Miranda / Growth Manager / Transfero [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문 lines:15는 7월 25일이며 startedAt은 lines:40에 7월 31일로 기록합니다. days는 lines:91-92에 7월 25-26일입니다.

### 행사 084

> Vietnam Office Hours | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/vietnam-office-hours-or-regional-updates-and-live-demos-svf9qisq75)

페이지 일정 필드(UTC)는 2026-07-30T14:00:00.000Z부터 2026-07-30T15:00:00.000Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 베트남 지역 모임 회원을 위한 주간 커뮤니티 토론입니다. lines:7-7

- 지역 개발자와 연결하고 Arc 개발 소식을 공유하며 기술 피드백을 교환합니다. lines:7-7

- 생태계 기회를 논의하고 지역 개발자 커뮤니티를 강화합니다. lines:7-7

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Lecter  Vu / Founder / Vitael [원문 그대로]

> Teddy Dinh / Moderator / Architect [원문 그대로]

### 행사 085

> Agent Builder Meetup [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/singapore/events/agent-builder-meetup)

페이지 일정 필드(UTC)는 2026-07-30T10:00:00.590Z부터 2026-07-30T13:00:00.590Z까지이며 표시 시간대는 Singapore이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Singapore [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=True`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> GA ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=True`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Singapore에서 Aisa와 함께 Circle Agent Stack 기술 개발 모임을 진행합니다. lines:7-7

- Circle CLI, Agent Wallets, Agent Marketplace와 Gateway 기반 Agent Nanopayments로 API, 데이터, 도구와 컴퓨팅 서비스를 찾고 결제하는 작업 절차를 설명합니다. lines:9-9

- 에이전트가 작업 중 서비스를 구매하는 방식과 개발자가 API, 데이터, 도구 및 컴퓨팅을 검색 및 구매할 수 있게 제공하는 방식을 모두 다룹니다. lines:11-11

- Circle Agent Stack이 Aisa 서비스에 실시간으로 결제하는 데모를 진행합니다. lines:11-11

- Circle Agent Stack 발표, Aisa 발표, 통합 실시간 데모와 교류를 진행합니다. lines:15-21

- Aisa는 하나의 API 키로 실시간 데이터, 웹 검색, SaaS와 LLM 등에 접근하는 서비스를 개발한다고 소개합니다. lines:23-23

- Aisa 소개는 동작할 때만 과금하고 구독과 특정 공급자에 묶이는 조건이 없다고 설명합니다. lines:23-23

- 티켓 설명은 초대 전용과 승인 조건, 제한된 좌석, 양도 금지 및 영어 진행을 명시합니다. lines:152-152

- 사전 등록 양식은 거주 도시 응답을 필수로 요구합니다. lines:174-176

- 사전 등록 양식은 참가 이유 응답을 필수로 요구합니다. lines:183-185

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Elton Tay / DevRel Lead, APAC / Circle [원문 그대로]

> HJ Chen / Senior Manager, Developer Relations and Ecosystem Marketing / Circle [원문 그대로]

사전 등록 질문은 다음과 같다. 필수 여부는 질문마다 따로 기록한다.

> What city do you live in? [원문 그대로]

필수 응답이다.

> Why do you want to attend this event? [원문 그대로]

필수 응답이다.

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 행사 초대 전용은 lines:36에 false지만 전체 및 개별 티켓은 lines:37,156에 true이고 승인 조건도 있습니다. 행사 시작은 lines:30에 7월 30일이나 days는 lines:144-145에 6월 17-18일입니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://aisa.one/?utm_source=luma / 한국어 정리
- https://luma.com/circle-3abs / 한국어 정리

### 행사 086

> Agentic Economy Meetup: How AI Agents Pay With AgentCash and USDC [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/agentic-economy-meetup-how-ai-agents-pay-with-agentcash-and-usdc-hgonxt7u6g)

페이지 일정 필드(UTC)는 2026-07-29T22:30:00.642Z부터 2026-07-30T00:30:18.452Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> 300 Kent Ave / Brooklyn / NY / USA [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Merit Systems와 Circle이 AI 에이전트 경제와 USDC 결제에 관한 저녁 모임을 개최합니다. lines:7-7

- 기업이 AI 에이전트에 판매할 준비 방법, 지갑과 USDC를 이용한 에이전트 거래, 새로운 결제 프로토콜 및 도구를 설명합니다. lines:9-9

- 양 팀의 짧은 발표 뒤 피자, 음료와 개발자 교류 및 데모가 있습니다. lines:11-11

- AgentCash 개발사 Merit Systems와 Circle 생태계 및 보조금 팀이 참여합니다. lines:15-17

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/r248b9dv / 한국어 정리

### 행사 087

> Arc Builder Spotlight: AIsa - Agentic APIs and Nanopayments [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-builder-spotlight-aisa-agentic-apis-and-nanopayments-cze00axjlj)

페이지 일정 필드(UTC)는 2026-07-29T14:00:00.444Z부터 2026-07-29T15:00:00.444Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- AIsa는 모델, 데이터 API, 검색 도구와 스테이블코인 결제를 하나의 개발 경험으로 제공하는 AI 에이전트용 통합 API 서비스를 개발합니다. lines:7-7

- Haonan이 AIsa 개발 내용과 Arc 생태계에서의 역할 및 x402와 Nanopayments 통합을 설명합니다. lines:9-9

- API 자원을 호출할 때마다 결제하는 접근 방식을 설명합니다. lines:9-9

- Circle Gateway 기반 Nanopayments로 소프트웨어, API와 에이전트가 USDC 거래를 지속하는 작업 절차를 설명합니다. lines:9-9

- 면책 안내: 뒤의 법률 안내는 기능 변경과 보장 및 투자 조언 부재에 관한 면책 문구입니다. lines:17-17

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- startedAt은 lines:26에 7월 29일이나 days는 lines:45-46에 6월 18-19일입니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 088

> The Agentic Economy: Payments, Agents, & Privacy [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/the-agentic-economy-payments-agents-and-privacy-frelkh4589)

페이지 일정 필드(UTC)는 2026-07-29T00:30:00.786Z부터 2026-07-29T03:30:15.150Z까지이며 표시 시간대는 America/Los_Angeles이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Stanford / CA / 94305 [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Circle, Pantera Capital과 Stanford Open Lab이 AI 에이전트, 결제 인프라와 거래 비공개 기술에 관한 모임을 진행합니다. lines:7-9

- 17:30에 입장하며 결제, 거래 비공개 기술과 투자 분야의 짧은 강연 및 데모를 진행합니다. lines:11-11

- Circle의 Abinesh Sarvepalli와 Mira Belenkiy가 Arc Privacy 데모와 짧은 강연을 진행합니다. lines:13-13

- Circle의 Duc Le가 Arc Agentic Payment Lane을 소개합니다. lines:15-15

- Circle Quantum Roadmap을 소개합니다. lines:17-17

- Pantera Capital의 Jay Yu가 AI 에이전트 경제 투자 관점을 발표합니다. lines:19-19

- Visa의 Michael Yang이 Agentic CLI를 소개합니다. lines:21-21

- Blockrun의 Vicky Fu가 Blockrun Agent Stack을 소개합니다. lines:23-23

- 음식과 음료를 제공하고 창업자, 개발자와 투자자 등과 교류합니다. lines:25-25

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 주소 필드는 lines:47에 빈 문자열이고 country 값은 lines:50에 94305로 기록합니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/sgs5pubk / 한국어 정리

### 행사 089

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-0rd2chey7t)

페이지 일정 필드(UTC)는 2026-07-28T17:00:00.964Z부터 2026-07-28T17:45:59.156Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord 전용 상담에서 Arc 커뮤니티팀과 생태계 개발자들이 만나 질문하고 그 주의 Arc 최신 소식을 논의합니다. lines:7-7

- Discord 이벤트 링크를 눌러 알림을 받도록 안내합니다. lines:9-9

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 090

> Region Kickoff: Bangladesh Roundtable Discussion [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/bangledesh/events/region-kickoff-bangladesh-roundtable-discussion-mmxbs3qikh)

페이지 일정 필드(UTC)는 2026-07-28T15:00:00.409Z부터 2026-07-28T16:00:01.438Z까지이며 표시 시간대는 Asia/Dhaka이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Arc 방글라데시 커뮤니티 회원들이 서로 소개하는 초기 토론입니다. lines:7-7

- 현재 개발 내용과 앞으로 작업할 계획을 공유합니다. lines:7-7

- 지역 스테이블코인 활용과 방글라데시의 기회 및 문제를 논의합니다. lines:7-7

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Sukanto Das / Co-Founder / Ababil Pay [원문 그대로]

> Motaleb Hossain / BD / Achswap [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- startedAt은 lines:14에 7월 28일이나 days는 lines:66-67에 7월 26-27일입니다.

### 행사 091

> Buenos Aires | Community Breakfast Meetup | Stablecoins in Argentina [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/argentina/events/buenos-aires-or-community-breakfast-meetup-or-stablecoins-in-argentina-vv56olvx5l)

페이지 일정 필드(UTC)는 2026-07-25T12:00:00.044Z부터 2026-07-25T16:00:00.044Z까지이며 표시 시간대는 America/Argentina/Buenos_Aires이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Av. Dorrego 2133, Palermo Hollywood. Entre Palermo y Colegiales. / Huerta Dorrego / Buenos Aires / Argentina [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Palermo Hollywood에서 Arc Builder Circle Argentina의 공식 출범을 알리고 현지 창업자 및 개발자와 스테이블코인 개발을 논의합니다. lines:11-11

- 첫날부터 참가자가 대화에 참여하는 원형 토론 방식을 제시합니다. lines:13-13

- Arc가 무엇이며 어디에 쓰이고 아르헨티나 생태계에 왜 중요한지 소개합니다. lines:19-19

- Crecimiento, Dev3pack 등의 참가자와 암호화폐 커뮤니티의 역할을 논의합니다. lines:21-21

- Paisanos의 Bel과 배포, 커뮤니티 및 시장 진입에 관한 마케팅과 제품 개발을 논의합니다. lines:23-23

- Ripio 팀의 경험으로 핀테크 개발을 설명합니다. lines:25-25

- 스테이블코인 개발자, 암호화폐 창업자, 원격 팀, Arc 개발자와 AI 및 블록체인에 관심 있는 사람을 대상으로 합니다. lines:27-27

- 7월 25일 09:00-10:00에는 아침 식사와 교류를 하고 10시부터 강연 및 토론을 진행합니다. lines:29-29

- 장소는 Huerta Dorrego, Av. Dorrego 2133의 Palermo Hollywood입니다. lines:31-31

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Lara Oses / Content Creator | Desencryptada / Dev3Pack || SheFi [원문 그대로]

> Santi Juarros / LatAm Partner Marketing · Circle / Circle [원문 그대로]

> Juampi Hernández / Developer Growth || Content Creator / Builder [원문 그대로]

> Santi Cristóbal / Director / Crecimiento [원문 그대로]

> Fermín Rodríguez / Head of Product / Ripio [원문 그대로]

> Federico Goldberg / CEO / Manteca [원문 그대로]

> Belén González / CMO / Paisanos [원문 그대로]

> Yulia Yanochkina / Senior Data Analyst & Data Engineer | Automation & AI-Driven Work / Dev3pack || BetterCollective [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문 lines:15에 이미지가 연결되어 있지만 이 입력은 이미지 URL만 포함합니다. 이미지 자체는 열지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://d2xo500swnpgl1.cloudfront.net/uploads/arc/some-file-068bf979-82b5-4967-b7d6-6f0474a30c99-1784825404672.jpeg / 한국어 정리

### 행사 092

> Lagos | Community Meetup | Stablecoin Breakfast [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/nigeria/events/lagos-or-community-meetup-or-stablecoin-breakfast-7v6x9odlyr)

페이지 일정 필드(UTC)는 2026-07-25T11:00:00.817Z부터 2026-07-25T15:00:57.149Z까지이며 표시 시간대는 Africa/Lagos이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Cafe One, 3, Kudirat Abiola Way, Oregun / Lagos / Nigeria [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Lagos의 첫 스테이블코인 조찬 모임에서 Arc 개발자가 실시간 개발, 데모와 대화를 진행합니다. lines:9-9

- 제품을 개발하는 창업자, 투자자와 개발자 중 스테이블코인 및 Arc와 시작 방법에 관심 있는 사람을 대상으로 합니다. lines:11-11

- 교류와 Arc 테스트넷 배포 실습 및 무료 아침 식사를 제공합니다. lines:15-15

- 장소는 Cafe One, 3 Kudirat Abiola Way, Oregun, Lagos입니다. lines:13-13

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Jerry Ojumah / Ecosystem Builder / Onboard [원문 그대로]

> Ridwan  Jokanola (Ade) / Blockchain developer  / Arcade [원문 그대로]

> Elijah Kolawole / Chief Technology Officer / ImportaPay [원문 그대로]

> Olamide Kuforiji / Treasury Operations Associate / Quidax [원문 그대로]

### 행사 093

> Enugu | Community Meetup | New Location Kickoff [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/nigeria/events/enugu-or-community-meetup-or-new-location-kickoff-71bk552gvc)

페이지 일정 필드(UTC)는 2026-07-25T11:00:00.523Z부터 2026-07-25T15:00:00.523Z까지이며 표시 시간대는 Africa/Lagos이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Blockchain Hub Africa, 1 Temple Ave / Enugu / Enugu / Nigeria [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Blockchain Hub Africa에서 Enugu의 첫 Arc 커뮤니티 모임을 개최합니다. lines:7-7

- 스테이블코인이 결제, 저축과 디지털 금융을 바꾸는 방식을 탐구합니다. lines:9-9

- 차세대 금융 앱을 위한 Arc 인프라와 나이지리아에 대한 의미를 설명합니다. lines:9-9

- 장소는 1 Temple Ave의 Blockchain Hub Africa이며 First Bank Headquarters 뒤의 3rd Inventory 표지와 old park에서 자동차로 6분이라는 길 안내를 제공합니다. lines:11-15

- 발표자 소개는 UnitFlow Finance가 Arc의 모듈형 스테이블코인 DeFi 프로토콜이며 DEX, 대출, 예측 시장, 수익 농사와 국가 간 결제를 포함한다고 설명합니다. lines:85-85

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Carbz XBT / BD/CoFounder / ForgeLabs/XyloNet [원문 그대로]

> Chisom  Edwin (CryptoMama) / Licensed MedLab scientist at Federal University of Calabar / Federal University of Calabar  [원문 그대로]

> Emmanuella Okpala / Marketer / Zynta [원문 그대로]

> Christopher)  Ekom (BTCmoney / Software Engineer / UnitFlow.Finance [원문 그대로]

> James Chukwu / Game Designer  / VeritySports [원문 그대로]

> Kevin Chibuoyim / Founder / The Block Hive [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- UnitFlow의 기능은 행사 의제가 아닌 발표자 소개 lines:85의 내용입니다. 해당 소개를 행사 실습으로 해석하지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://maps.app.goo.gl/jyM91yxS2MudX8qb9?g_st=ac / 한국어 정리
- https://maps.app.goo.gl/jyM91yxS2MudX8qb9?g_st=ac / 한국어 정리

### 행사 094

> Arc Builder Spotlight: Pulsar - Consumer Stablecoin Money on Arc [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-builder-spotlight-pulsar-consumer-stablecoin-money-on-arc-qab35uffl6)

페이지 일정 필드(UTC)는 2026-07-24T14:00:00.939Z부터 2026-07-24T15:00:11.641Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Pulsar는 달러, 유로와 파운드 스테이블코인을 한곳에 보유하고 통화를 전환하며 잔액으로 지출하는 소비자 금융 앱입니다. lines:7-7

- Pulsar Money 공동 창업자 및 CEO Alex Radu가 Sam과 제품, Arc 선택 이유와 스테이블코인 기반 개인 금융 관점을 설명합니다. lines:7-7

- Pulsar 앱을 실시간으로 보여 줍니다. lines:7-7

- 소비자 결제, 다중 통화 스테이블코인 계좌와 Arc 금융 앱에 관심 있는 사람을 대상으로 합니다. lines:7-7

- 면책 안내: 뒤의 법률 안내는 기능 변경과 보장 및 투자 조언 부재에 관한 면책 문구입니다. lines:15-15

- 메타데이터에 다시보기 링크가 있습니다. lines:32-32

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- startedAt은 lines:24에 7월 24일이며 days는 lines:44-45에 7월 29-30일입니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.io/home/videos/event-replay-arc-builder-spotlight-pulsar-consumer-stablecoin-money-on-arc-2026-07-24 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 095

> Vietnam Office Hours | Regional Updates & Live Demos [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/vietnam/events/vietnam-office-hours-or-regional-updates-and-live-demos-arl3fl7nx5)

페이지 일정 필드(UTC)는 2026-07-23T14:00:00.514Z부터 2026-07-23T15:00:21.884Z까지이며 표시 시간대는 Asia/Saigon이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=True`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 베트남 지역 모임 회원을 위한 주간 커뮤니티 토론입니다. lines:7-7

- 지역 개발자와 연결하고 Arc 개발 소식을 공유하며 기술 피드백을 교환합니다. lines:7-7

- 생태계 기회를 논의하고 지역 개발자 커뮤니티를 강화합니다. lines:7-7

- 티켓의 isFull은 true이고 대기 명단 기능은 false입니다. lines:86-91

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Lecter  Vu / Founder / Vitael [원문 그대로]

> Teddy Dinh / Moderator / Architect [원문 그대로]

수집 시점의 공개 이벤트 데이터에서 만석으로 표시되어 있다.

### 행사 096

> Lisbon | Community Meetup | Builder Afterwork [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/portugal/events/lisbon-or-community-meetup-or-builder-afterwork-wl85rhfd6c)

페이지 일정 필드(UTC)는 2026-07-22T16:00:00.374Z부터 2026-07-22T19:00:38.396Z까지이며 표시 시간대는 Portugal이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Avenida Duque de Loulé nº24A, 1050-090 / Lisboa / Portugal [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Onchain Lisbon Week 동안 Lunar Strategy 창업자 Tim Haldorsson과 Shann Holmberg가 저녁 모임을 진행합니다. lines:11-11

- Arc 개발자가 발표, 실시간 데모와 교류에 참여하며 간식과 음료를 제공합니다. lines:13-13

- 17시에 입장하며 18시에 Tim Haldorsson의 발표와 데모를 시작합니다. lines:17-19

- Arc 커뮤니티 개발자 한 명이 개발 중인 결과물을 보여 줍니다. lines:21-21

- Lunar 또는 Turtle의 Nick이 Arc 네오뱅크를 시연합니다. lines:23-23

- 간식, 음료와 자유로운 교류를 진행하고 21시에 종료한다고 안내합니다. lines:25-27

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Tim  Haldorsson / Founder / Lunar Strategy & Espressio AI [원문 그대로]

> Shann Holmberg / Founder / Lunar Strategy & Espressio [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문 lines:27은 21시 종료를 안내하지만 endedAt은 lines:35의 2026-07-22T19:00:38.396Z입니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/arclisbon / 한국어 정리
- https://maps.app.goo.gl/76UFDcZQM9GJkbkL7 / 한국어 정리

### 행사 097

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-mv1esefz2v)

페이지 일정 필드(UTC)는 2026-07-21T17:00:00.841Z부터 2026-07-21T17:45:52.002Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord 전용 상담에서 Arc 커뮤니티팀과 생태계 개발자들이 만나 질문하고 그 주의 Arc 최신 소식을 논의합니다. lines:7-7

- Discord 이벤트 링크를 눌러 알림을 받도록 안내합니다. lines:9-9

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 098

> Building on Arc: Open-Source Resources from the Canteen x Arc Hackathon Series [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/building-on-arc-open-source-resources-from-the-canteen-x-arc-hackathon-series-4rowmvmpot)

페이지 일정 필드(UTC)는 2026-07-16T14:00:00.224Z부터 2026-07-16T15:00:58.881Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Circle과 Canteen이 해커톤 시리즈에서 다른 개발자들이 만든 공개 소스 코드를 발견하도록 돕는 방송입니다. lines:7-7

- Arc Open Source Showcase와 프로젝트 페이지, 저장소 및 태그를 살펴보는 방법을 설명합니다. lines:9-9

- 후속 Arc 개발의 참고 자료로 재사용 가능한 앱, 기본 기능, 코드와 사용 사례를 소개합니다. lines:9-9

- 어떤 자료가 있고 자기 프로젝트와 관련된 예제를 어떻게 평가할지 이해하도록 돕습니다. lines:11-11

- 면책 안내: 뒤의 법률 안내는 기능 변경과 보장 및 투자 조언 부재에 관한 면책 문구입니다. lines:19-19

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 099

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-lk2qyepocc)

페이지 일정 필드(UTC)는 2026-07-14T17:00:00.133Z부터 2026-07-14T17:45:40.657Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord 전용 상담에서 Arc 커뮤니티팀과 생태계 개발자들이 만나 질문하고 그 주의 Arc 최신 소식을 논의합니다. lines:7-7

- Discord 이벤트 링크를 눌러 알림을 받도록 안내합니다. lines:9-9

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 100

> Programmable Money on Arc Bootcamp [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/programmable-money-on-arc-bootcamp-mvixsdscmu)

페이지 일정 필드(UTC)는 2026-06-22T07:00:00.825Z부터 2026-07-12T23:00:00.825Z까지이며 표시 시간대는 Europe/London이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 스테이블코인과 이를 기본으로 설계한 Arc L1에 관해 배우는 부트캠프입니다. lines:9-9

- USDC 가스 토큰, 1초 미만 정산, CCTP와 Gateway의 체인 간 전송, StableFX 외환과 지갑, 계약, 결제, 메시징 도구를 소개합니다. lines:15-23

- 프로그래밍 가능한 자금 흐름 설계, CCTP와 Gateway를 통한 체인 간 결제 조율, StableFX 다중 통화 정산과 Circle 도구를 통한 서비스용 금융 앱 개발을 배웁니다. lines:29-35

- CCTP의 체인 간 결제 흐름, Circle Contracts 스마트 계약, Circle Wallets 앱과 StableFX 다중 통화 결제 또는 자금 관리 흐름을 직접 만듭니다. lines:39-45

- 스테이블코인을 이해하고 개발을 시작하려는 개발자를 대상으로 하며 과정 전체가 비동기 방식입니다. lines:49-49

- 추가 안내와 등록은 Encode Club 부트캠프 페이지로 연결합니다. lines:51-51

- 공개 메타데이터는 시작 2026-06-22T07:00:00.825Z, 종료 2026-07-12T23:00:00.825Z, 시간대 Europe/London를 기록합니다. lines:58-60

- 공개 티켓은 Free Ticket이며 표시 가격은 0입니다. lines:169-169

- 온라인 여부는 true이고 초대 전용 여부는 false입니다. lines:63-65

- 발표자 목록은 Corey Cooper의 직함을 Senior Manager, Developer Relations and Ecosystem Marketing, 소속을 Circle로 기록합니다. lines:78-80

- 발표자 목록은 Jenna Teeman의 직함을 Principle Program Manager, Developer Marketing, 소속을 Circle로 기록합니다. lines:88-90

- 발표자 목록은 Anthony Kelani의 직함을 Director of Ecosystem Growth, 소속을 Circle로 기록합니다. lines:98-100

- 발표자 목록은 Blessing Adesiji의 직함을 Developer Relations Manager, EMEA, 소속을 Circle로 기록합니다. lines:108-110

- 발표자 목록은 Sam Sealey의 직함을 Director, Community, 소속을 Circle로 기록합니다. lines:118-120

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Corey Cooper / Senior Manager, Developer Relations and Ecosystem Marketing / Circle [원문 그대로]

> Jenna Teeman / Principle Program Manager, Developer Marketing  / Circle [원문 그대로]

> Anthony Kelani / Director of Ecosystem Growth  / Circle [원문 그대로]

> Blessing Adesiji / Developer Relations Manager, EMEA / Circle [원문 그대로]

> Sam Sealey / Director, Community  / Circle [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://www.encodeclub.com/programmes/arc-bootcamp?scheduleTab=298&scheduleTag=299 / 한국어 정리

### 행사 101

> Arc x Canteen: Agora Hackathon Builder Spotlight [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-x-canteen-agora-hackathon-builder-spotlight-00mi9xlatf)

페이지 일정 필드(UTC)는 2026-07-09T14:00:00.845Z부터 2026-07-09T15:00:22.695Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Agora 해커톤은 Arc에서 USDC로 정산하며 거래, 투자, 창작과 시장 상호작용을 수행하는 AI 에이전트를 탐구했습니다. 수상 팀들이 결과물과 접근 방식을 소개합니다. lines:7-7

- 각 팀의 짧은 시연 후 Circle, Arc와 Canteen이 여러 팀과 배운 점 및 후속 개발 계획을 논의합니다. lines:9-9

- 데모, 사용 사례와 공개 소스 예제에서 재사용 가능한 교훈을 다른 개발자에게 제공합니다. lines:9-9

- 면책 안내: 소프트웨어 제공자, 사용자 책임, 규제 승인 부재와 기능 변경에 관한 부분은 면책 문구입니다. lines:17-17

- 공개 메타데이터에 다시보기 링크가 있습니다. lines:34-34

- 공개 메타데이터는 시작 2026-07-09T14:00:00.845Z, 종료 2026-07-09T15:00:22.695Z, 시간대 America/New_York를 기록합니다. lines:26-28

- 공개 티켓은 Free Ticket이며 표시 가격은 0입니다. lines:65-65

- 온라인 여부는 true이고 초대 전용 여부는 false입니다. lines:31-33

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.io/home/videos/event-replay-arc-x-canteen-agora-hackathon-builder-spotlight-2026-07-09 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 102

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-p19g381oug)

페이지 일정 필드(UTC)는 2026-07-07T17:00:00.396Z부터 2026-07-07T17:45:36.671Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord 전용 상담에서 Arc 커뮤니티팀과 생태계 개발자들이 만나 질문하고 그 주의 Arc 최신 소식을 논의합니다. lines:7-7

- Discord 이벤트 링크를 눌러 알림을 받도록 안내합니다. lines:9-9

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 103

> Builder Breakfast Meetup: How USDC & EURC Are Redefining Payments [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/france/events/builder-breakfast-meetup-how-usdc-and-eurc-are-redefining-payments-1k7lptapzm)

페이지 일정 필드(UTC)는 2026-07-06T06:30:00.683Z부터 2026-07-06T08:30:00.683Z까지이며 표시 시간대는 Europe/Paris이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> 119 Av. des Alpes, 06800  / Cagnes-sur-Mer / France [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- French Riviera에서 Arc France의 첫 대면 커뮤니티 행사를 개최합니다. lines:15-15

- USDC와 EURC 등 스테이블코인이 결제를 바꾸고 기존 금융과 탈중앙 금융을 연결하는 방식을 탐구합니다. lines:9-27

- 개발자, 창업자, 핀테크 관계자, 지역 사업자와 관심 있는 모든 사람을 대상으로 합니다. lines:27-27

- Arc 기술과 프랑스 커뮤니티 계획, 유럽의 스테이블코인 역할에 관한 짧은 소개를 진행합니다. lines:21-27

- 빵, 주스와 커피를 곁들인 아침 식사 교류를 제공합니다. lines:23-23

- 프랑스어로 진행하는 무료 교육 및 커뮤니티 행사이며 정원이 제한되어 등록해야 합니다. lines:25-31

- 면책 안내: 금융 조언이나 투자 상품 제공이 없다는 안내 문구가 있습니다. lines:25-25

- 참가자에게 무료 전용 주차를 제공합니다. lines:33-33

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Abdelaziz Moussaoui / Co-Founder / Meridian Finance [원문 그대로]

> Fayssal Moussaoui / CTO & Co-Founder / Meridian [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://www.google.com/maps/search/?api=1&query=Brasserie%20Julien%20Shopping%20Promenade%20Riviera%20Polygone%20Riviera%2C%20119%20Av.%20des%20Alpes%2C%2006800%20Cagnes-sur-Mer%2C%20France / 한국어 정리
- https://www.meetup.com/circle-arc-france-web3-blockchain-builders/events/315294319/?_xtd=gqFyqTQ4MTkxNzkyNKFwo2FwaQ%253D%253D&from=ref / 한국어 정리

### 행사 104

> AI Engineer World's Fair [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/ai-engineer-worlds-fair-sjcp8bmkuh)

페이지 일정 필드(UTC)는 2026-06-29T15:00:00.790Z부터 2026-07-03T01:00:00.790Z까지이며 표시 시간대는 America/Los_Angeles이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Moscone Center West / San Francisco / CA / USA [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Circle은 San Francisco의 "AI Engineer World’s Fair"[원문 그대로]에서 실시간 가격, 정산과 수익화를 위한 결제 인프라를 소개합니다. lines:7-9

- L-G32 부스에서 사람이 정한 권한 범위 안에 에이전트가 자금을 보유하고 서비스를 찾으며 프로그램으로 거래하는 Circle Agent Stack을 직접 체험할 수 있습니다. lines:11-11

- Agent Wallets, Agent Marketplace, Circle CLI, 서비스와 API용 USDC 결제 및 고빈도 저비용 활동용 Nanopayments를 소개합니다. lines:13-21

- L-G32 부스에서 팀을 만나고 agents.circle.com에서 추가 정보를 확인하도록 안내합니다. lines:23-25

- 공개 발표 주제는 에이전트 지갑 필요성과 Arc의 USDC 및 Nanopayments 거래이며 Circle의 Harshal Bhangale가 발표자로 연결되어 있습니다. lines:52-65

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Harshal Bhangale / Software Engineer / Circle [원문 그대로]

### 행사 105

> İstanbul | Arc Community Meetup with e2vc [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/istanbul-or-arc-community-meetup-with-e2vc-1tey6qcdkz)

페이지 일정 필드(UTC)는 2026-07-01T12:00:00.086Z부터 2026-07-01T14:00:11.600Z까지이며 표시 시간대는 Europe/Istanbul이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> İstanbul / Türkiye [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Istanbul의 첫 공개 Arc 모임에서 잔액 보유, 자금 이동과 온체인 정산을 자율 수행하는 AI 에이전트를 다룹니다. lines:7-7

- e2vc와 공동 개최하여 참가자가 개발, 투자 유치와 사업의 설명 방식에 관해 투자사 팀과 직접 이야기할 수 있습니다. lines:9-9

- Arc 보조금, Arc와 App Kit의 관계, Circle Agent Stack의 온체인 거래 에이전트, 개발 및 투자 유치와 자유로운 질의응답을 진행합니다. lines:15-23

- Arc Architects, Arc를 개발하거나 탐구하는 창업자 및 개발자, 에이전트 결제 개발자와 웹3 입문자를 대상으로 하며 사전 경험이 필요하지 않습니다. lines:27-33

- 좌석이 제한되어 조기 등록을 안내하며 영어로 진행합니다. lines:39-41

- 피자를 제공합니다. lines:43-43

- e2vc는 Emerging Europe의 세계 시장을 지향하는 창업자에게 투자하는 초기 투자 펀드라고 소개합니다. lines:47-47

- Submit을 누르면 Circle에 인터뷰, 녹음, 촬영과 인물 식별 및 음성, 외모, 사진, 이름과 소개의 이용 및 편집 권한을 취소할 수 없게 부여한다는 조건입니다. lines:49-49

- 같은 동의문은 녹음과 촬영물을 추가 승인 없이 광고, 마케팅과 홍보 등 Circle이 정하는 목적으로 전시, 배포 및 활용할 권한을 부여합니다. lines:49-49

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/circle-arc-meetup-turkey-july-2026 / 한국어 정리

### 행사 106

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-npfyji41tb)

페이지 일정 필드(UTC)는 2026-06-30T17:00:00.504Z부터 2026-06-30T17:45:22.621Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord 전용 상담에서 Arc 커뮤니티팀과 생태계 개발자들이 질문하고 그 주의 최신 Arc 소식을 논의합니다. lines:7-7

- Discord 이벤트 링크를 누르면 알림을 받을 수 있다고 안내합니다. lines:9-9

- 공개 메타데이터는 시작 2026-06-30T17:00:00.504Z, 종료 2026-06-30T17:45:22.621Z, 시간대 America/New_York를 기록합니다. lines:16-18

- 공개 티켓은 Free Ticket이며 표시 가격은 0입니다. lines:55-55

- 온라인 여부는 true이고 초대 전용 여부는 false입니다. lines:21-23

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 107

> Hackathon: Lepton Agents [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/arc-hackathons/events/hackathon-lepton-agents-em1dcv9xwe)

페이지 일정 필드(UTC)는 2026-06-15T15:00:00.673Z부터 2026-06-29T13:00:00.673Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Hybrid`로 표시되어 있다.

- Canteen이 Circle과 협력하여 Arc에서 진행하는 2주짜리 해커톤입니다. lines:7-7

- Arc에서 초소액 결제(nanopayments)를 지불, 수신하고 관리하는 AI 에이전트를 만드는 행사입니다. lines:9-9

- 현금이나 이에 준하는 형태로 상금 50,000달러를 제공하며 대상, 우수 팀과 easter eggs라고 부르는 항목에 나누어 배정한다고 안내합니다. lines:13-13

- Canteen의 연구, 창업자와 인맥에 직접 접근할 기회를 제공합니다. lines:15-15

- 공고는 Arc에서 실제 결제 처리, 1초 미만의 거래 확정(finality)과 약 0.01 USDC의 수수료를 안내합니다. lines:17-17

- 개발자를 위한 요청(Requests for Builders) 여섯 가지를 공개한다고 안내합니다. lines:19-19

- 2주 동안 멘토링과 프로그램을 제공합니다. lines:21-21

- 공고는 작은 결제가 가스비에 소진되고 수수료 토큰의 변동성 때문에 예산을 유지하기 어렵다는 문제를 개발 배경으로 설명합니다. lines:25-25

- 예측 가능한 USDC 수수료, 1초 미만의 거래 확정(deterministic finality)과 프로토콜 수준의 스테이블코인 결제를 개발 기반으로 제시합니다. lines:27-27

- Circle의 USDC, CCTP, Gateway와 App Kit를 함께 활용한다고 안내합니다. lines:27-27

- 연구자, 학생과 엔지니어를 환영하며 암호화폐 분야에 처음 입문한 사람도 포함합니다. lines:31-31

- 빠르게 결과물을 배포하고 사용자와 이야기하는 데 익숙한 사람을 대상으로 안내합니다. lines:31-31

- 일정은 2026년 6월 15일부터 29일까지로 안내합니다. lines:33-33

- 본문은 2주 동안 온라인으로 진행한다고 안내합니다. lines:35-35

- 참가 신청 시 Luma에서 LEPTONHOUSE 코드를 사용하도록 안내합니다. lines:37-37

- 커뮤니티 Discord 링크를 안내합니다. lines:45-45

- 시작 모임은 6월 15일 오전 11시 미국 동부 시간이며 Twitch 링크를 안내합니다. lines:47-47

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 35행 본문은 온라인 형식을 안내하지만 58행 displayEventType과 100행 attendanceMode는 Hybrid이고 99행 supportInPerson은 true입니다.
- 13행은 easter eggs에 배정되는 상금을 언급하지만 해당 항목의 내용과 지급 기준을 구체적으로 설명하지 않습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.gg/rsVfYutFZg / 한국어 정리
- https://discord.gg/rsVfYutFZg?utm_source=luma / 한국어 정리
- https://lepton.thecanteenapp.com/ / 한국어 정리
- https://lepton.thecanteenapp.com/?utm_source=luma / 한국어 정리
- https://luma.com/5xcrazms / 한국어 정리
- https://www.twitch.tv/arjun_canteen / 한국어 정리

### 행사 108

> Lagos | Community Meetup | Region Kickoff Mixer [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/nigeria/events/lagos-or-community-meetup-or-region-kickoff-mixer-vs5s51je1d)

페이지 일정 필드(UTC)는 2026-06-26T15:00:00.278Z부터 2026-06-26T19:00:00.278Z까지이며 표시 시간대는 Africa/Lagos이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Cilantro Lagos, 7 Musa Yar' Adua St / Victoria Island / Lagos / Africa [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=True`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Registration Required [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=True`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 국경 간 결제가 여전히 제대로 작동하지 않는 이유와 Arc가 이를 해결하는 방법을 다룹니다. lines:9-9

- 국경 간 결제와 Arc에 관심 있는 개발자, 창업자, 투자자와 DeFi 팀을 대상으로 합니다. lines:11-11

- 국경 간 결제 솔루션을 만드는 사람과 Arc를 알아보는 사람을 모두 언급합니다. lines:11-11

- 장소는 라고스 Victoria Island의 Cilantro Lagos로 안내합니다. lines:13-13

- 티켓 이름은 등록 필요(Registration Required)로 기재되어 있습니다. lines:78-78

- 사전 신청 양식에는 참가하고 싶은 이유를 필수로 입력해야 합니다. lines:101-103

- 사전 신청 양식에는 거주 도시를 필수로 입력해야 합니다. lines:110-112

- 공개 티켓에는 초대가 필요하다고 표시되어 있습니다. lines:83-83

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Jerry Ojumah / Ecosystem Builder / Onboard [원문 그대로]

사전 등록 질문은 다음과 같다. 필수 여부는 질문마다 따로 기록한다.

> Why do you want to join our event? [원문 그대로]

필수 응답이다.

> What city are you located in? [원문 그대로]

필수 응답이다.

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 26행 이벤트 isInvitationOnly는 false이지만 27행 모든 티켓 초대 표시는 true이고 83행 티켓 isInvitationOnly도 true입니다.
- 35행 location.country에는 Africa가 기재되어 있으며 13행 본문은 Lagos를 가리킵니다.

### 행사 109

> Region Kickoff: Brasil Roundtable Discussion [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/brazil/events/region-kickoff-brasil-roundtable-discussion-sn202g1nz2)

페이지 일정 필드(UTC)는 2026-06-26T17:00:00.696Z부터 2026-06-26T18:30:39.498Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 지역 Arc 회원을 위한 첫 모임의 토론입니다. lines:7-7

- 개발 중이거나 개발을 고려하는 내용을 공유합니다. lines:7-7

- 지역의 스테이블코인 활용 사례를 논의합니다. lines:7-7

- 지역에서 마주하는 기회와 진행을 막는 문제를 찾습니다. lines:7-7

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Thiago Monteiro / Developer Relations / Parabuilders [원문 그대로]

> Douglas Miranda / Growth Manager / Transfero [원문 그대로]

> Sam Sealey / Director, Community  / Circle [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 14-15행의 행사 날짜는 6월 26일이지만 days의 76-77행은 6월 25-26일로 기재되어 있습니다.

### 행사 110

> Privacy on Arc: What Builders Should Know [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/privacy-on-arc-what-builders-should-know-mw7s12x4lo)

페이지 일정 필드(UTC)는 2026-06-25T14:00:00.129Z부터 2026-06-25T14:45:52.338Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 공고는 Arc 프라이버시 백서가 프라이버시를 익명성이 아니라 실제 금융 업무에서 선택적으로 적용하는 기밀성으로 설명한다고 안내합니다. lines:7-7

- 민감한 거래 데이터와 비공개 스마트 계약 상태를 보호하면서 권한이 있는 당사자의 관리된 열람을 지원한다는 설계를 다룹니다. lines:7-7

- Circle이 개발자에게 백서와 Arc 프라이버시의 설계 원칙을 설명합니다. lines:9-9

- 공개가 기본인 투명성이 급여, 자금 관리, 거래, 대출과 스왑 사례를 제약할 수 있는 이유를 다룹니다. lines:9-9

- ArcaneVM을 통한 기밀 실행과 프라이버시 기능이 로드맵에 남아 있는 동안 개발자가 알아야 할 사항을 다룹니다. lines:9-9

- 면책 안내: 프라이버시 기능은 일부 온체인 데이터를 선택적으로 감추는 제안된 설계라고 명시합니다. lines:11-11

- 면책 안내: 프라이버시 기능의 범위, 기능과 도입 일정은 변경, 지연, 제한되거나 중단될 수 있다고 명시합니다. lines:11-11

- 추가 정보로 Arc Privacy Sector 백서 PDF 링크를 안내합니다. lines:11-11

- 면책 안내: 면책문구는 CTS가 소프트웨어 제공자이며 규제 금융 서비스나 자문 서비스를 제공하지 않는다고 설명합니다. lines:15-15

- 면책 안내: 면책문구는 이용자가 제공하는 서비스의 인허가와 관련 법률 준수 책임을 이용자에게 둡니다. lines:15-15

- 면책 안내: 면책문구는 Arc가 뉴욕주 금융서비스국의 검토나 승인을 받지 않았다고 설명합니다. lines:17-17

- 면책 안내: 면책문구는 제품 기능이 변경, 지연되거나 취소될 수 있다고 설명합니다. lines:19-19

- 면책 안내: 면책문구는 이 자료가 약정, 보증이나 투자 자문을 구성하지 않는다고 설명합니다. lines:19-19

- 면책 안내: 면책문구는 USDC를 Circle의 규제 대상 계열사가 발행하며 인허가 목록을 외부 링크에서 확인할 수 있다고 설명합니다. lines:21-21

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/PDFs/Whitepapers/Arc_Privacy_Sector%20(5).pdf / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 111

> Teresina | Community Meetup | Builder Kickoff [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/brazil/events/teresina-or-community-meetup-or-builder-kickoff-3lfx15jvjn)

페이지 일정 필드(UTC)는 2026-06-23T21:00:00.966Z부터 2026-06-23T23:00:15.620Z까지이며 표시 시간대는 Brazil/East이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> NUFPERPI, Praça Firmina Sobreira, S/N - Matinha, Teresina - PI,  / Teresina / Brazil [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 기술 분야 종사자가 Arc 생태계에 참여하도록 돕고 실제 시장의 확장 가능한 블록체인 솔루션을 소개하는 것이 주요 목적입니다. lines:11-11

- Arc에서 실제로 운영 중인 애플리케이션을 시연하고 기존 사업 모델에서 기술의 효율성과 활용을 소개합니다. lines:15-15

- Web3로 진로를 바꾸거나 전문성을 높이려는 소프트웨어 엔지니어를 언급합니다. lines:17-17

- 소프트웨어 엔지니어에게 경쟁력과 전략적 위치를 분석하는 내용을 제공합니다. lines:17-17

- 파트너 생태계와 수요, 채용, 인센티브 프로그램, 신규 프로젝트 개발 지원을 소개합니다. lines:19-19

- 개발자의 경력과 사업 전환을 지원하고 분산 블록체인 인프라에 기반한 개발 역량을 기르는 것을 목표로 합니다. lines:21-21

- 사전 신청 양식에는 참가하려는 이유를 필수로 입력해야 합니다. lines:109-111

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Thiago Monteiro / Developer Relations / Parabuilders [원문 그대로]

사전 등록 질문은 다음과 같다. 필수 여부는 질문마다 따로 기록한다.

> Why do you want to attend this meetup? [원문 그대로]

필수 응답이다.

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 28-29행의 행사 날짜는 6월 23일이지만 days의 79-80행은 6월 22-23일로 기재되어 있습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://www.google.com/maps/place/NUFPERPI+-+N%C3%BAcleo+de+Forma%C3%A7%C3%A3o+e+Pesquisa+em+Energias+Renov%C3%A1veis+e+Telecomunica%C3%A7%C3%B5es+do+Piau%C3%AD/@-5.0803053,-42.825267,17z/data=!3m1!4b1!4m6!3m5!1s0x78e3977dbe164fd:0x8584c94d8abe5f80!8m2!3d-5.0803053!4d-42.8226921!16s%2Fg%2F11q484q1jl?entry=ttu&g_ep=EgoyMDI2MDYxNi4wIKXMDSoASAFQAw%3D%3D / 한국어 정리

### 행사 112

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-ec158i4iap)

페이지 일정 필드(UTC)는 2026-06-23T17:00:00.113Z부터 2026-06-23T17:45:39.891Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord에서만 진행하는 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계의 개발자들이 편하게 만나는 행사입니다. lines:7-7

- 질문을 하고 해당 주의 Arc 최신 소식을 이야기합니다. lines:7-7

- 본문의 Discord 이벤트 링크로 알림을 설정하도록 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 Discord 알림 링크는 이 배치의 서로 다른 날짜의 Office Hours 공고에서 동일하며 링크의 실제 행사 날짜는 확인하지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 113

> Rio | Community Meetup | Region Kickoff Mixer [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/clubs/brazil/events/rio-or-community-meetup-or-region-kickoff-mixer-4r28fe8nfh)

페이지 일정 필드(UTC)는 2026-06-22T19:00:53.186Z부터 2026-06-22T23:30:53.212Z까지이며 표시 시간대는 Brazil/East이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Casa 7 Co-Working, Rua Piragibe Frota Aguiar, 7 / Rio de Janeiro / Brazil [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 리우데자네이루에서 첫 공식 모임을 열어 Arc 커뮤니티의 브라질 지부를 시작합니다. lines:7-7

- 지역 개발자, 창업자, 교육자와 핀테크 분야 종사자를 Arc의 글로벌 생태계와 연결하는 것을 목표로 합니다. lines:7-7

- 공고는 Pix 결제 인프라, 스테이블코인 채택 증가, 실물자산 토큰화와 온체인 금융에 대한 관심을 브라질의 배경으로 제시합니다. lines:9-9

- 공고는 BRZ를 브라질 중앙은행이 인정하는 유일한 스테이블코인이라고 설명합니다. lines:9-9

- 브라질 개발자 모임의 출범과 지역 개발자의 Arc 인지도 및 도입 확대를 기대 결과로 제시합니다. lines:15-15

- 후속 워크숍, 해커톤과 콘텐츠에 참여할 개발자를 모으고 리우의 반복 모임을 다른 브라질 도시로 확장할 기반을 마련한다고 설명합니다. lines:15-15

- 스테이블코인 가스, 1초 미만의 거래 확정(finality)과 선택적 프라이버시라는 Arc의 특성을 교육합니다. lines:19-19

- 초반에는 공동 작업, 참가자 간 만남과 Arc 프로젝트 토론을 진행합니다. lines:23-23

- 환영과 커뮤니티 소개에서는 인터넷 경제 운영체제(Economic OS)라는 Arc의 비전과 브라질 지부 출범을 소개합니다. lines:25-25

- 포르투갈어 자막이 있는 Arc 영상을 프로젝터로 보여 준다고 안내합니다. lines:25-25

- 교육 세션은 스테이블코인, 실물자산(RWAs), 금융 포용과 국경 간 결제를 포함하며 참가자의 다음 실행 단계를 다룹니다. lines:27-27

- 마지막에는 교류와 협력 기회를 알아보는 시간을 마련합니다. lines:29-29

- 사전 신청 양식에는 거주 도시를 필수로 입력해야 합니다. lines:117-119

- 사전 신청 양식에는 참가하려는 이유를 필수로 입력해야 합니다. lines:126-128

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Douglas Miranda / Growth Manager / Transfero [원문 그대로]

사전 등록 질문은 다음과 같다. 필수 여부는 질문마다 따로 기록한다.

> What city are you based in? [원문 그대로]

필수 응답이다.

> Why do you want to attend this meetup? [원문 그대로]

필수 응답이다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://www.instagram.com/somoscasa7 / 한국어 정리

### 행사 114

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-914d1qdhjk)

페이지 일정 필드(UTC)는 2026-06-16T17:00:00.915Z부터 2026-06-16T17:45:27.398Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord에서만 진행하는 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계의 개발자들이 편하게 만나는 행사입니다. lines:7-7

- 질문을 하고 해당 주의 Arc 최신 소식을 이야기합니다. lines:7-7

- 본문의 Discord 이벤트 링크로 알림을 설정하도록 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 Discord 알림 링크는 이 배치의 서로 다른 날짜의 Office Hours 공고에서 동일하며 링크의 실제 행사 날짜는 확인하지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 115

> Hackathon: ETHGlobal New York 2026 [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/hackathon-ethglobal-new-york-2026-2wbc20jux8)

페이지 일정 필드(UTC)는 2026-06-12T17:00:00.297Z부터 2026-06-14T19:30:00.297Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> 125 W 18th St / New York / New York / United States [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Web3 기술, 프로토콜과 개발 도구를 알아보는 개발자를 위한 대면 해커톤입니다. lines:7-7

- Circle이 개발 플랫폼과 연계한 보상 과제(bounty)를 후원하여 Arc 개발자를 지원한다고 안내합니다. lines:9-9

- 스테이블코인, 결제, 지갑, 인프라와 온체인 금융 앱을 만드는 사람에게 실험, 기술 지원과 보상 과제 경쟁 기회를 안내합니다. lines:9-9

- 공고는 참가자 800명 이상, 프로토콜 13개 이상과 워크숍 29개 이상을 안내합니다. lines:13-17

- 초보자도 참여하기 편한 행사라고 안내합니다. lines:19-19

- 직접 해 보면서 배우는 방식이라고 안내합니다. lines:21-21

- 기술 멘토링을 제공합니다. lines:23-23

- 행사 기념품을 제공합니다. lines:25-25

- 선별한 콘텐츠를 제공합니다. lines:27-27

- 무료 음식과 음료를 제공합니다. lines:29-29

- ETHGlobal 행사 페이지에서 상세 정보를 확인하도록 안내합니다. lines:31-31

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://ethglobal.com/events/newyork2026 / 한국어 정리
- https://ethglobal.com/events/newyork2026/prizes/arc / 한국어 정리

### 행사 116

> The Bored Room [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/the-bored-room-kticfyrlc2)

페이지 일정 필드(UTC)는 2026-06-09T15:00:00.291Z부터 2026-06-09T23:00:34.385Z까지이며 표시 시간대는 America/Los_Angeles이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Boream & Boredley의 직원 다섯 명이 승인, 업데이트와 결제 처리를 기다리는 설정의 생방송입니다. lines:7-7

- 인터넷은 즉시 움직이지만 돈은 느리고 오래된 금융 시스템에서 지연되는 문제를 풍자합니다. lines:9-9

- Bill, Jessey와 Chad는 아무 일도 하지 않거나 기다리는 일을 표현한 직책의 인물로 등장합니다. lines:11-11

- 진지한 말투의 기업 상황극을 통해 금융의 미래가 지연되어서는 안 된다는 주제를 전달한다고 안내합니다. lines:13-13

- 알림을 설정하고 생방송을 시청하도록 안내합니다. lines:15-15

- Noah와 Johnny는 기술의 가능성과 절차의 지속을 다루는 직책의 인물로 등장합니다. lines:11-11

- 공고는 모든 업무가 영업일 기준 3일 걸리는 회사의 상황을 설정합니다. lines:11-11

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Bill - / Manager, Proactive Inaction / Boream & Boredley  [원문 그대로]

> Jessey - / Boream & Boredley  / Director of Holding Patterns [원문 그대로]

> Chad - / Chief Systems Contemplation Officer / Boream & Boredley  [원문 그대로]

> Noah - / Junior Associate, Technical Possibilities / Boream & Boredley  [원문 그대로]

> Johnny - / Senior Process Continuity Liaison / Boream & Boredley  [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행 본문은 오전 8시 PST라고 안내하지만 22행 시작 시각은 15:00Z이고 24행 시간대는 America/Los_Angeles로 기재되어 있습니다. 표기 간 관계는 판정하지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://www.arc.io/theboredroom / 한국어 정리

### 행사 117

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-9agen4oqr4)

페이지 일정 필드(UTC)는 2026-06-09T17:00:00.488Z부터 2026-06-09T17:45:42.977Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord에서만 진행하는 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계의 개발자들이 편하게 만나는 행사입니다. lines:7-7

- 질문을 하고 해당 주의 Arc 최신 소식을 이야기합니다. lines:7-7

- 본문의 Discord 이벤트 링크로 알림을 설정하도록 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 Discord 알림 링크는 이 배치의 서로 다른 날짜의 Office Hours 공고에서 동일하며 링크의 실제 행사 날짜는 확인하지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 118

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-it3rm55zvl)

페이지 일정 필드(UTC)는 2026-06-02T17:00:00.222Z부터 2026-06-02T17:45:51.254Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord에서만 진행하는 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계의 개발자들이 편하게 만나는 행사입니다. lines:7-7

- 질문을 하고 해당 주의 Arc 최신 소식을 이야기합니다. lines:7-7

- 본문의 Discord 이벤트 링크로 알림을 설정하도록 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 Discord 알림 링크는 이 배치의 서로 다른 날짜의 Office Hours 공고에서 동일하며 링크의 실제 행사 날짜는 확인하지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 119

> Agentic Demo Day: AI Projects Built on Arc [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/agentic-demo-day-ai-projects-built-on-arc-6waq0ce6ua)

페이지 일정 필드(UTC)는 2026-05-28T15:00:00.928Z부터 2026-05-28T16:00:19.249Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 최근 해커톤 우승 팀이 Arc와 Circle 인프라에서 만든 AI, 에이전트 결제와 초소액 결제(nanopayments) 프로젝트를 시연합니다. lines:7-7

- 각 팀이 만든 결과물, 작동 방식과 Arc 및 Circle 인프라가 활용 사례를 지원하는 방법을 짧게 시연합니다. lines:9-9

- 에이전트 상거래(agentic commerce), 소액 결제, 온체인 지능과 새로운 AI 활용 업무를 다룹니다. lines:9-9

- Vertex를 참가 팀으로 안내하고 프로젝트 설명 페이지를 연결합니다. lines:11-11

- Gyasss를 참가 팀으로 안내하고 프로젝트 설명 페이지를 연결합니다. lines:11-11

- Cairn을 참가 팀으로 안내하고 프로젝트 설명 페이지를 연결합니다. lines:11-11

- MEV Shield를 참가 팀으로 안내하고 프로젝트 설명 페이지를 연결합니다. lines:11-11

- Arc House 커뮤니티에 실제 개발 결과물을 보여 주고 AI 및 에이전트 상거래의 후속 아이디어를 찾는 것을 목표로 합니다. lines:13-13

- 면책 안내: 면책문구는 CTS가 소프트웨어 제공자이며 규제 금융 서비스나 자문 서비스를 제공하지 않는다고 설명합니다. lines:17-17

- 면책 안내: 면책문구는 이용자가 제공하는 서비스의 인허가와 관련 법률 준수 책임을 이용자에게 둡니다. lines:17-17

- 면책 안내: 면책문구는 Arc가 뉴욕주 금융서비스국의 검토나 승인을 받지 않았다고 설명합니다. lines:19-19

- 면책 안내: 면책문구는 제품 기능이 변경, 지연되거나 취소될 수 있다고 설명합니다. lines:21-21

- 면책 안내: 면책문구는 이 자료가 약정, 보증이나 투자 자문을 구성하지 않는다고 설명합니다. lines:21-21

- 면책 안내: 면책문구는 USDC를 Circle의 규제 대상 계열사가 발행하며 인허가 목록을 외부 링크에서 확인할 수 있다고 설명합니다. lines:23-23

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.io/home/videos/agentic-demo-day-ai-projects-built-on-arc-2026-05-28 / 한국어 정리
- https://lablab.ai/ai-hackathons/nano-payments-arc/building-an-agentic-ad-exchange-stack/vertex-dynamic-ad-exchange / 한국어 정리
- https://lablab.ai/ai-hackathons/nano-payments-arc/gyas/gyasss-pay-per-query-oracle-on-circle-arc / 한국어 정리
- https://lablab.ai/ai-hackathons/nano-payments-arc/tori/cairn-nanopayment-environmental-oracle / 한국어 정리
- https://lablab.ai/ai-hackathons/nano-payments-arc/vectorblock/mev-shield-micropayment-gated-mempool-ai / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 120

> Arc Builder Spotlight: TLAY - Machine-to-Machine Nanopayments on Arc [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-builder-spotlight-tlay-machine-to-machine-nanopayments-on-arc-vjm1vvv5l9)

페이지 일정 필드(UTC)는 2026-05-27T14:00:00.187Z부터 2026-05-27T15:00:08.389Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- TLAY는 기계 간 상거래를 위한 내장 지갑과 신뢰 인프라를 개발한다고 설명합니다. lines:7-7

- Leo가 실제 장치를 사용하는 시연을 설명합니다. lines:7-7

- eCandle 태양광 장치가 변화하는 전력 가격을 알리고 Bitaxe 채굴기가 10초마다 전력 구매 여부를 결정하는 시연입니다. lines:7-7

- 가격이 수익성 조건을 충족하면 채굴기가 장치에서 USDC 지급 승인을 서명하고 전력을 소비합니다. lines:7-7

- 결제는 이후 Circle 인프라를 통해 Arc 테스트넷에서 처리됩니다. lines:7-7

- 기계 지갑과 초소액 결제(nanopayments)를 통해 클라우드 에이전트의 온체인 결제를 실제 연결 장치로 확장하는 방법을 개발자가 이해하도록 돕습니다. lines:9-9

- 면책 안내: 면책문구는 CTS가 소프트웨어 제공자이며 규제 금융 서비스나 자문 서비스를 제공하지 않는다고 설명합니다. lines:13-13

- 면책 안내: 면책문구는 이용자가 제공하는 서비스의 인허가와 관련 법률 준수 책임을 이용자에게 둡니다. lines:13-13

- 면책 안내: 면책문구는 Arc가 뉴욕주 금융서비스국의 검토나 승인을 받지 않았다고 설명합니다. lines:15-15

- 면책 안내: 면책문구는 제품 기능이 변경, 지연되거나 취소될 수 있다고 설명합니다. lines:17-17

- 면책 안내: 면책문구는 이 자료가 약정, 보증이나 투자 자문을 구성하지 않는다고 설명합니다. lines:17-17

- 면책 안내: 면책문구는 USDC를 Circle의 규제 대상 계열사가 발행하며 인허가 목록을 외부 링크에서 확인할 수 있다고 설명합니다. lines:19-19

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 26행의 행사 날짜는 5월 27일이지만 34행 재생 영상 주소 이름에는 2026-05-28이 포함되어 있습니다. 영상은 열지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.io/home/videos/replay-arc-builder-spotlight-tlay-machine-to-machine-nanopayments-on-arc-2026-05-28 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 121

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-t7xe2qfivv)

페이지 일정 필드(UTC)는 2026-05-26T17:00:00.464Z부터 2026-05-26T17:45:43.852Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord에서만 진행하는 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계의 개발자들이 편하게 만나는 행사입니다. lines:7-7

- 질문을 하고 해당 주의 Arc 최신 소식을 이야기합니다. lines:7-7

- 본문의 Discord 이벤트 링크로 알림을 설정하도록 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 Discord 알림 링크는 이 배치의 서로 다른 날짜의 Office Hours 공고에서 동일하며 링크의 실제 행사 날짜는 확인하지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 122

> Circle Developer Grants: Building on Arc and the Circle Developer Platform [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/circle-developer-grants-building-on-arc-and-the-circle-developer-platform-o6p6ge6b4n)

페이지 일정 필드(UTC)는 2026-05-22T15:00:00.405Z부터 2026-05-22T16:00:03.736Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Arc와 Circle Developer Platform에서 개발하는 팀에 대한 보조금 지원 목적을 Jenna, Anthony와 Sam이 설명하는 세션입니다. lines:7-7

- 지원자 평가 항목과 신청 절차를 소개합니다. lines:7-7

- 보조금을 통한 자금, 기술 지도, 공동 마케팅과 생태계 지원을 설명합니다. lines:7-7

- 면책 안내: Wallets, CTS, Arc 테스트넷과 StableFX에 관한 부분은 소프트웨어 제공자, 사용자 책임, 규제 승인 부재와 기능 변경에 관한 면책 문구입니다. lines:19-19

- 공개 메타데이터에 다시보기 링크가 있습니다. lines:34-34

- 공개 메타데이터는 시작 2026-05-22T15:00:00.405Z, 종료 2026-05-22T16:00:03.736Z, 시간대 America/New_York를 기록합니다. lines:26-28

- 공개 티켓은 Free Ticket이며 표시 가격은 0입니다. lines:65-65

- 온라인 여부는 true이고 초대 전용 여부는 false입니다. lines:31-33

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.io/home/videos/replay-circle-developer-grants-building-on-arc-and-the-circle-developer-platform-2026-05-22 / 한국어 정리
- https://console.circle.com/legal/developer-terms / 한국어 정리
- https://www.circle.com/legal/licenses / 한국어 정리

### 행사 123

> Arc Builder Spotlight: Tower Exchange - Native Stablecoin DEX Aggregation on Arc [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-builder-spotlight-tower-exchange-native-stablecoin-dex-aggregation-on-arc-36jb4hk46v)

페이지 일정 필드(UTC)는 2026-05-21T14:00:00.027Z부터 2026-05-21T15:00:00.027Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Tower Exchange를 Arc의 탈중앙화 거래소 유동성을 통합하는 스테이블코인 중심의 거래소 통합 서비스(DEX aggregator)로 소개합니다. lines:7-7

- 하나의 인터페이스를 통해 사용자의 거래 체결을 개선하도록 설계되었다고 설명합니다. lines:7-7

- 유동성 공급원을 대상으로 거래 경로를 선택하고 지원하는 체인 간 자산 이동을 통합합니다. lines:7-7

- AI 도우미가 자연어를 통해 포트폴리오, 거래와 성과에 대한 이해를 돕습니다. lines:7-7

- 면책 안내: 면책문구는 CTS가 소프트웨어 제공자이며 규제 금융 서비스나 자문 서비스를 제공하지 않는다고 설명합니다. lines:11-11

- 면책 안내: 면책문구는 이용자가 제공하는 서비스의 인허가와 관련 법률 준수 책임을 이용자에게 둡니다. lines:11-11

- 면책 안내: 면책문구는 Arc가 뉴욕주 금융서비스국의 검토나 승인을 받지 않았다고 설명합니다. lines:13-13

- 면책 안내: 면책문구는 제품 기능이 변경, 지연되거나 취소될 수 있다고 설명합니다. lines:15-15

- 면책 안내: 면책문구는 이 자료가 약정, 보증이나 투자 자문을 구성하지 않는다고 설명합니다. lines:15-15

- 면책 안내: 면책문구는 USDC를 Circle의 규제 대상 계열사가 발행하며 인허가 목록을 외부 링크에서 확인할 수 있다고 설명합니다. lines:17-17

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 24-25행의 행사 날짜는 5월 21일이지만 days의 44-45행은 5월 14-15일로 기재되어 있습니다.
- 24행의 행사 날짜는 5월 21일이지만 32행 재생 영상 주소 이름에는 2026-07-24가 포함되어 있습니다. 영상은 열지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.io/home/videos/event-replay-arc-builder-spotlight-tower-exchange-native-stablecoin-dex-aggregation-on-arc-2026-07-24 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 124

> Builder Spotlight: Synthra - Spot, Concentrated Liquidity, and Perpetual Markets on Arc [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/builder-spotlight-synthra-spot-concentrated-liquidity-and-perpetual-markets-on-arc-p22y3ym3ce)

페이지 일정 필드(UTC)는 2026-05-20T14:00:00.203Z부터 2026-05-20T15:00:06.163Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Synthra는 Arc 테스트넷의 통합 탈중앙화 거래 플랫폼입니다. lines:7-7

- 현물 스왑, 집중 유동성(concentrated liquidity)과 무기한 계약 시장(perpetual markets)을 함께 제공합니다. lines:7-7

- Jacopo가 Synthra가 개발하는 내용을 설명합니다. lines:7-7

- 온체인 거래자와 유동성 공급자의 문제, Arc에서의 제품 설계와 시장 구조를 다룹니다. lines:7-7

- 면책 안내: 면책문구는 CTS가 소프트웨어 제공자이며 규제 금융 서비스나 자문 서비스를 제공하지 않는다고 설명합니다. lines:11-11

- 면책 안내: 면책문구는 이용자가 제공하는 서비스의 인허가와 관련 법률 준수 책임을 이용자에게 둡니다. lines:11-11

- 면책 안내: 면책문구는 Arc가 뉴욕주 금융서비스국의 검토나 승인을 받지 않았다고 설명합니다. lines:13-13

- 면책 안내: 면책문구는 제품 기능이 변경, 지연되거나 취소될 수 있다고 설명합니다. lines:15-15

- 면책 안내: 면책문구는 이 자료가 약정, 보증이나 투자 자문을 구성하지 않는다고 설명합니다. lines:15-15

- 면책 안내: 면책문구는 USDC를 Circle의 규제 대상 계열사가 발행하며 인허가 목록을 외부 링크에서 확인할 수 있다고 설명합니다. lines:17-17

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 24행의 행사 날짜는 5월 20일이지만 32행 재생 영상 주소 이름에는 2026-07-20이 포함되어 있습니다. 영상은 열지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.io/home/videos/builder-spotlight-synthra-spot-concentrated-liquidity-and-perpetual-markets-on-arc-2026-07-20 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 125

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-o46iwxbm73)

페이지 일정 필드(UTC)는 2026-05-19T17:00:00.498Z부터 2026-05-19T17:45:19.159Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord에서만 진행하는 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계의 개발자들이 편하게 만나는 행사입니다. lines:7-7

- 질문을 하고 해당 주의 Arc 최신 소식을 이야기합니다. lines:7-7

- 본문의 Discord 이벤트 링크로 알림을 설정하도록 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 Discord 알림 링크는 이 배치의 서로 다른 날짜의 Office Hours 공고에서 동일하며 링크의 실제 행사 날짜는 확인하지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 126

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-3adac94z1w)

페이지 일정 필드(UTC)는 2026-05-12T17:00:00.915Z부터 2026-05-12T17:45:27.616Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord에서만 진행하는 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계의 개발자들이 편하게 만나는 행사입니다. lines:7-7

- 질문을 하고 해당 주의 Arc 최신 소식을 이야기합니다. lines:7-7

- 본문의 Discord 이벤트 링크로 알림을 설정하도록 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 Discord 알림 링크는 이 배치의 서로 다른 날짜의 Office Hours 공고에서 동일하며 링크의 실제 행사 날짜는 확인하지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 127

> Arc Enterprise & DeFi Hackathon Spotlight: Chariot - Crosschain Collateral Lending Protocol on Arc [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-enterprise-and-defi-hackathon-spotlight-chariot-crosschain-collateral-lending-protocol-on-arc-umne213eet)

페이지 일정 필드(UTC)는 2026-05-07T15:00:00.849Z부터 2026-05-07T16:00:01.842Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Sam Sealey와 Sipho Yawe가 Arc 테스트넷의 교차 체인 담보 대출 프로토콜 Chariot를 시연합니다. lines:7-7

- ETHEscrow를 통해 Sepolia에서 ETH를 가져오는 과정을 보여 줍니다. lines:7-7

- ERC-4626 ChariotVault가 차입자 이자와 USYC 단기 국채 수익을 함께 제공하는 방법을 설명합니다. lines:7-7

- 실시간 청산과 비상 거래 중단(circuit breaker) 시나리오를 시연합니다. lines:7-7

- 프로토콜 계약, 위험 모델과 USYC 노출을 관리하는 자산 관리 에이전트(vault agent)를 자세히 다룹니다. lines:7-7

- 면책 안내: 면책문구는 CTS가 소프트웨어 제공자이며 규제 금융 서비스나 자문 서비스를 제공하지 않는다고 설명합니다. lines:11-11

- 면책 안내: 면책문구는 이용자가 제공하는 서비스의 인허가와 관련 법률 준수 책임을 이용자에게 둡니다. lines:11-11

- 면책 안내: 면책문구는 Arc가 뉴욕주 금융서비스국의 검토나 승인을 받지 않았다고 설명합니다. lines:13-13

- 면책 안내: 면책문구는 제품 기능이 변경, 지연되거나 취소될 수 있다고 설명합니다. lines:15-15

- 면책 안내: 면책문구는 이 자료가 약정, 보증이나 투자 자문을 구성하지 않는다고 설명합니다. lines:15-15

- 면책 안내: 면책문구는 USDC를 Circle의 규제 대상 계열사가 발행하며 인허가 목록을 외부 링크에서 확인할 수 있다고 설명합니다. lines:17-17

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 24행의 행사 날짜는 5월 7일이지만 32행 재생 영상 주소 이름에는 2026-05-20이 포함되어 있습니다. 영상은 열지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.io/home/videos/replay-arc-enterprise-and-defi-hackathon-spotlight-chariot-crosschain-collateral-lending-protocol-on-arc-2026-05-20 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 128

> Setting Up Your Full Agentic Stack With Circle: Consensus 2026 Workshop [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/setting-up-your-full-agentic-stack-with-circle-consensus-2026-workshop-sb05znkwqf)

페이지 일정 필드(UTC)는 2026-05-06T17:00:00.678Z부터 2026-05-06T17:50:00.491Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Miami Beach Convention Center / 1901 Convention Ctr Dr, Miami Beach / Miami / Florida / United States [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- ChatGPT, Claude와 OpenClaw를 함께 활용하는 사용자를 예로 듭니다. lines:7-7

- AI 에이전트가 사용자를 대신해 구매하도록 하는 구성을 다룹니다. lines:7-7

- Circle이 재정을 관리하는 데 필요한 에이전트 시스템 구성 전체(full agentic stack)를 설명합니다. lines:7-7

- Consensus 2026 컨퍼런스 내부의 워크숍이라고 안내합니다. lines:9-9

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- [연결 주소](https://consensus.coindesk.com/agenda/event/-setting-up-your-full-agentic-stack-with-circle-112)는 이번 요청에서 HTTP 403로 본문을 확보하지 못했다.

### 행사 129

> AWS + Circle Present: Agentic Nanopayments at Consensus 2026 [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/aws-circle-present-agentic-nanopayments-at-consensus-2026-sjye5zctdv)

페이지 일정 필드(UTC)는 2026-05-05T18:30:00.453Z부터 2026-05-05T19:30:41.776Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Miami Beach Convention Center / 1901 Convention Ctr Dr, Miami Beach / Miami / Florida / United States [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- AWS와 Circle이 실시간 사용량 기반 디지털 경제를 살펴보는 세션을 엽니다. lines:7-7

- USDC 인프라를 사용하는 초소액 결제(nanopayments)로 1센트보다 작은 거래를 구현하는 방법을 설명합니다. lines:9-9

- 개발자와 AI 에이전트가 자금을 미리 충전하고 요청마다 지급하여 API, 데이터셋과 연산 서비스에서 수익을 얻는 방법을 다룹니다. lines:9-9

- AWS Nitro Enclaves를 사용한 거래 검증과 결제 처리 등 보안성과 확장성을 갖춘 구성을 다룹니다. lines:11-11

- 금융 서비스, AI 플랫폼과 디지털 마켓플레이스의 실제 활용 사례를 소개합니다. lines:13-13

- 참가할 때 Consensus 입장권은 필요하지 않다고 명시합니다. lines:17-17

- 장소는 Miami Beach Convention Center 2층 202호이며 주요 전시장 입구 근처 에스컬레이터 위라고 안내합니다. lines:19-19

- 공간이 제한되어 있으므로 제시간에 도착하도록 안내합니다. lines:21-21

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/7d1kf5z9 / 한국어 정리

### 행사 130

> How To Set Up Stablecoin Wallet & Dashboard for Your Business With Circle [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/how-to-set-up-stablecoin-wallet-and-dashboard-for-your-business-with-circle-us4hxwefux)

페이지 일정 필드(UTC)는 2026-05-05T17:00:00.208Z부터 2026-05-05T17:50:42.082Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Miami Beach Convention Center / 1901 Convention Ctr Dr, Miami Beach / Miami / Florida / United States [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 스테이블코인을 도입하려는 기업을 대상으로 지갑과 대시보드를 설명합니다. lines:7-7

- 지갑 설정, 입출금 관리와 전통 금융(TradFi)에 맞춘 암호화폐 데이터 정규화를 다룹니다. lines:7-7

- 예정된 에이전트 지갑과 개발자가 AI 에이전트용 지갑을 만들 수 있는 명령줄 인터페이스(CLI)를 간략히 다룹니다. lines:9-9

- Consensus 2026 컨퍼런스 내부의 워크숍이라고 안내합니다. lines:11-11

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- [연결 주소](https://consensus.coindesk.com/agenda/event/-setting-up-a-stablecoin-wallet-dashboard-for-your-business-108)는 이번 요청에서 HTTP 403로 본문을 확보하지 못했다.

### 행사 131

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-6uth6xi6h2)

페이지 일정 필드(UTC)는 2026-05-05T17:00:00.779Z부터 2026-05-05T17:45:56.239Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord에서만 진행하는 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계의 개발자들이 편하게 만나는 행사입니다. lines:7-7

- 질문을 하고 해당 주의 Arc 최신 소식을 이야기합니다. lines:7-7

- 본문의 Discord 이벤트 링크로 알림을 설정하도록 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 Discord 알림 링크는 이 배치의 서로 다른 날짜의 Office Hours 공고에서 동일하며 링크의 실제 행사 날짜는 확인하지 않았습니다.
- 9행 본문의 Discord 알림 링크와 24행 registrationUrl이 서로 다른 이벤트 번호를 가리킵니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1475911760987947079 / 한국어 정리
- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 132

> ArcShop with Elton: Unified Balance Kit for Crosschain USDC Flows [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arcshop-with-elton-unified-balance-kit-for-crosschain-usdc-flows-w5tgz977rm)

페이지 일정 필드(UTC)는 2026-05-01T14:00:00.016Z부터 2026-05-01T15:00:36.396Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Unified Balance Kit을 다루는 개발자 대상 워크숍입니다. lines:7-7

- 개발자 관계 책임자 Elton이 진행합니다. lines:7-7

- 통합 잔액 개념과 deposit, depositFor, getBalances, estimateSpend, spend의 관계를 설명합니다. lines:7-7

- 공개 문서와 빠른 시작 자료를 사용하여 설치부터 첫 성공 흐름까지 안내합니다. lines:7-7

- 설치, 어댑터, 입금과 잔액 조회를 실습합니다. lines:15-15

- 지출 추정, 지출 실행과 체인 간 지급 패턴을 실습합니다. lines:17-17

- 후반부에는 구현 질문, 지원 체인과 토큰, 어댑터 선택 및 수수료 추정을 다룹니다. lines:7-7

- 실무 지급과 자금 관리 활용 사례를 다룹니다. lines:7-7

- 면책 안내: Circle Technology Services는 소프트웨어 제공자이며 규제 대상 금융 또는 자문 서비스를 제공하지 않습니다. lines:23-23

- 면책 안내: 서비스 제공자가 필요한 허가와 법 준수를 책임진다는 면책문구가 있습니다. lines:23-23

- 면책 안내: 뉴욕주 금융서비스국이 Arc를 검토하거나 승인하지 않았다고 명시합니다. lines:25-25

- 면책 안내: 제품 기능은 변경, 지연 또는 취소될 수 있으며 약속, 보증이나 투자 조언을 구성하지 않는다고 명시합니다. lines:27-27

- 면책 안내: USDC는 규제 대상 Circle 계열사가 발행하며 규제 인가 목록 링크를 제공합니다. lines:29-29

- 다시보기 URL이 기재되어 있습니다. lines:44-44

- 구조화된 주제 목록에는 Bridge Kit도 기재되어 있습니다. lines:73-73

- 구조화된 주제 목록에는 Circle Wallets도 기재되어 있습니다. lines:98-98

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Elton Tay / DevRel Lead, APAC / Circle [원문 그대로]

> Tim Baker / Community Manager / Circle [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.io/home/videos/arcshop-with-elton-unified-balance-kit-for-crosschain-usdc-flows-2026-05-01 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 133

> Arc Enterprise & DeFi Hackathon Spotlight: Crumb - Gasless USDC Nanopayments and settlement on Arc [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-enterprise-and-defi-hackathon-spotlight-crumb-gasless-usdc-nanopayments-and-settlement-on-arc-r7aay2xheu)

페이지 일정 필드(UTC)는 2026-04-29T14:00:00.204Z부터 2026-04-29T15:00:46.645Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Crumb은 Circle Nanopayments로 개발하고 Arc에서 정산하도록 설계한 가스 비용 없는 스테이블코인 결제 플랫폼입니다. lines:7-7

- 서명된 오프체인 지출 의도를 온체인 일괄 정산으로 바꿉니다. lines:7-7

- 결제당 비용을 거의 0으로 줄여 1센트 미만 USDC 결제를 실용화한다고 설명합니다. lines:7-7

- 사용량별 API 과금, 소액 결제, QR 및 개인 간 송금과 판매자 결제를 사례로 제시합니다. lines:7-7

- 면책 안내: Circle Technology Services는 소프트웨어 제공자이며 규제 대상 금융 또는 자문 서비스를 제공하지 않습니다. lines:11-11

- 면책 안내: 서비스 제공자가 필요한 허가와 법 준수를 책임진다는 면책문구가 있습니다. lines:11-11

- 면책 안내: 뉴욕주 금융서비스국이 Arc를 검토하거나 승인하지 않았다고 명시합니다. lines:13-13

- 면책 안내: 제품 기능은 변경, 지연 또는 취소될 수 있으며 약속, 보증이나 투자 조언을 구성하지 않는다고 명시합니다. lines:15-15

- 면책 안내: USDC는 규제 대상 Circle 계열사가 발행하며 규제 인가 목록 링크를 제공합니다. lines:17-17

- 다시보기 URL이 기재되어 있습니다. lines:33-33

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/arc-enterprise-and-defi-hackathon-spotlight-crumb-gasless-usdc-nanopayments-and-settlement-on-arc-2026-04-29 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리
- https://x.com/arc / 한국어 정리

### 행사 134

> ArcShop with HJ: Understanding Gateway - Building Chain Agnostic Apps with Gateway & Circle Wallets [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arcshop-with-hj-understanding-gateway-building-chain-agnostic-apps-with-gateway-and-circle-wallets-fdoco9aigm)

페이지 일정 필드(UTC)는 2026-04-28T14:00:00.720Z부터 2026-04-28T15:00:00.720Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Gateway의 입금, 거래 확정, 잔액 반영, 소각 의도 생성, API 증명과 목적지 체인 발행을 설명합니다. lines:7-7

- Circle Wallets가 계약 실행과 Gateway 소각 의도에 대한 EIP-712 서명을 처리하는 방식을 보여 줍니다. lines:7-7

- Gateway 개념과 애플리케이션 구조를 다룹니다. lines:11-11

- 통합 잔액에 입금하는 데모를 진행합니다. lines:13-13

- 통합 잔액에서 목적지 체인으로 전송하는 데모를 진행합니다. lines:15-15

- 마무리와 질의응답이 포함됩니다. lines:17-17

- 면책 안내: Circle Technology Services는 소프트웨어 제공자이며 규제 대상 금융 또는 자문 서비스를 제공하지 않습니다. lines:21-21

- 면책 안내: 서비스 제공자가 필요한 허가와 법 준수를 책임진다는 면책문구가 있습니다. lines:21-21

- 면책 안내: 뉴욕주 금융서비스국이 Arc를 검토하거나 승인하지 않았다고 명시합니다. lines:23-23

- 면책 안내: 제품 기능은 변경, 지연 또는 취소될 수 있으며 약속, 보증이나 투자 조언을 구성하지 않는다고 명시합니다. lines:25-25

- 면책 안내: USDC는 규제 대상 Circle 계열사가 발행하며 규제 인가 목록 링크를 제공합니다. lines:27-27

- 다시보기 URL이 기재되어 있습니다. lines:42-42

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> HJ Chen / Senior Manager, Developer Relations and Ecosystem Marketing / Circle [원문 그대로]

공개 세션은 다음과 같다. 제목과 설명은 원문 표기를 유지하며 시각은 각 세션의 UTC 데이터다.

> Understanding Gateway and how to build with Circle Wallets [원문 그대로]

세션 시각: `2026-04-23T14:00:00.000Z` - `2026-04-23T14:45:00.000Z`.

> Attendees will learn the core Gateway mental model: deposit, finality, balance crediting, burn intent creation, Gateway API attestation, and destination-chain minting. They will also see how Circle Wallets fits into that flow by handling wallet operations such as contract execution and EIP-712 signing for Gateway burn intents. [원문 그대로]

> 발표자: HJ Chen / Senior Manager, Developer Relations and Ecosystem Marketing / Circle [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 34-35행 행사 일시는 2026-04-28인데 107-108행 agendas와 144-145행 days는 2026-04-23입니다. 42행 다시보기 URL에는 2026-04-29가 포함되어 있으나 녹화 업로드일인지 행사일인지 공고에 설명되어 있지 않습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/arcshop-with-hj-building-chain-agnostic-apps-with-circle-gateway-and-circle-wallets-2026-04-29 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 135

> Agentic Economy on Arc Hackathon [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/agentic-economy-on-arc-hackathon-xoayqenc6j)

페이지 일정 필드(UTC)는 2026-04-20T07:00:00.763Z부터 2026-04-27T00:00:00.763Z까지이며 표시 시간대는 America/Los_Angeles이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> San Francisco / California / USA [원문 그대로]

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Hybrid`로 표시되어 있다.

- Circle Nanopayments와 Arc의 USDC 정산으로 에이전트 경제 애플리케이션을 개발하는 혼합형 해커톤입니다. lines:11-11

- 높은 빈도의 사용량별 거래, 예측 가능한 USDC 수수료와 1초 미만 거래 확정을 기술적 특징으로 제시합니다. lines:13-13

- 4월 20일부터 25일까지 온라인으로 개발하며 25일까지 프로젝트를 제출합니다. lines:17-17

- 4월 25일 샌프란시스코 현장에서는 팀들이 프로젝트를 다듬습니다. lines:19-19

- 4월 26일 현장 피칭과 수상자 발표를 진행합니다. lines:21-21

- Arc와 Circle 전문가의 현장 지도를 제공합니다. lines:23-23

- 개인으로 참가하거나 팀을 구성할 수 있습니다. lines:25-25

- 총 10,000달러 상금을 두고 경쟁합니다. lines:27-27

- 현장 체험 승인을 받으면 프로젝트를 직접 시연할 기회도 생깁니다. lines:29-29

- 여행과 숙박 비용은 지원하지 않습니다. lines:29-29

- 시작 방송 전에 등록하도록 안내합니다. lines:31-31

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://arcnetwork.xyz/ / 한국어 정리
- https://lablab.ai/ai-hackathons/nano-payments-arc / 한국어 정리
- https://www.circle.com/ / 한국어 정리

### 행사 136

> Agentic Economy on Arc Hackathon (IRL component) [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/agentic-economy-on-arc-hackathon-irl-component-0y20rlyapb)

페이지 일정 필드(UTC)는 2026-04-25T17:00:00.303Z부터 2026-04-27T00:00:00.303Z까지이며 표시 시간대는 America/Los_Angeles이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> San Francisco / California / USA [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 4월 25일과 26일 샌프란시스코 현장 행사는 세계 혼합형 해커톤의 마지막 행사입니다. lines:7-7

- 현장 행사 전에는 원격으로 개발하며 가스 비용 없는 높은 처리량의 1센트 미만 온체인 거래와 자금 통제를 보여 주는 프로젝트를 만듭니다. lines:7-7

- 10,000달러 상금, 현장 발표 기회와 선발 팀에 대한 인정을 제시합니다. lines:9-9

- 영향력이 가장 큰 팀을 현장에 초대한다고 안내합니다. lines:9-9

- 선발 팀은 프로젝트를 발표하고 생태계 파트너를 만납니다. lines:9-9

- 현장 정원이 제한되며 선발 팀에 우선 입장권을 제공합니다. lines:11-11

- 여행과 숙박 비용은 지원하지 않습니다. lines:11-11

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행은 현장 초대를 받을 팀을 언급하고 11행은 선발 팀 우선권을 명시하지만 24-25행과 59행의 초대 전용 플래그는 false입니다. 9행 most impactful의 선발 기준은 구체적으로 기재되어 있지 않습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/739oxjcc?tk=mLEQjw / 한국어 정리

### 행사 137

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-bvy0tajew0)

페이지 일정 필드(UTC)는 2026-04-21T17:00:00.205Z부터 2026-04-21T17:45:13.419Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord 전용 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계 개발자의 비공식 모임입니다. lines:7-7

- 질문하고 그 주의 최신 Arc 소식을 논의합니다. lines:7-7

- Discord 이벤트 링크에서 알림을 받을 수 있다고 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 알림용 Discord 이벤트 URL은 다른 일시의 공고에서도 반복됩니다. 외부 이벤트 페이지는 열지 않았습니다.
- 9행의 Discord 알림 링크 끝은 1493628390916231371인데 24행 등록 링크 끝은 1475911760987947079로 다릅니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1475911760987947079 / 한국어 정리
- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 138

> Arc Enterprise & DeFi Hackathon Spotlight: Blink Nanopayment Insurance [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-enterprise-and-defi-hackathon-spotlight-blink-nanopayment-insurance-pvl3kivzx5)

페이지 일정 필드(UTC)는 2026-04-20T15:00:00.914Z부터 2026-04-20T16:00:57.303Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Blink는 연간 기기 보험과 고정 가격을 대신하여 초 단위로 보험료를 산정하는 모델을 제시합니다. lines:7-7

- 기기 상태를 초당 위험 배수에 대응시킵니다. lines:7-7

- Circle Nanopayments와 Arc에서 소액 보험료를 실시간으로 연속 지급합니다. lines:7-7

- 실시간 제품 데모와 기술 설명으로 초당 결제의 유연한 보험 적용을 보여 줍니다. lines:7-7

- 면책 안내: Circle Technology Services는 소프트웨어 제공자이며 규제 대상 금융 또는 자문 서비스를 제공하지 않습니다. lines:11-11

- 면책 안내: 서비스 제공자가 필요한 허가와 법 준수를 책임진다는 면책문구가 있습니다. lines:11-11

- 면책 안내: 뉴욕주 금융서비스국이 Arc를 검토하거나 승인하지 않았다고 명시합니다. lines:13-13

- 면책 안내: 제품 기능은 변경, 지연 또는 취소될 수 있으며 약속, 보증이나 투자 조언을 구성하지 않는다고 명시합니다. lines:15-15

- 면책 안내: USDC는 규제 대상 Circle 계열사가 발행하며 규제 인가 목록 링크를 제공합니다. lines:17-17

- 다시보기 URL이 기재되어 있습니다. lines:32-32

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/arc-enterprise-and-defi-hackathon-spotlight-blink-nanopayment-insurance-2026-04-20 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 139

> App Kits Developer Office Hours: Bridge, Swap, Send, and Monetization [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/app-kits-developer-office-hours-bridge-swap-send-and-monetization-768o4ncx4e)

페이지 일정 필드(UTC)는 2026-04-17T14:00:00.602Z부터 2026-04-17T15:00:02.066Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Circle App Kits를 다루는 개발자 대상 워크숍입니다. lines:7-7

- 개발자 관계 책임자 Elton이 진행합니다. lines:7-7

- Bridge, Swap, Send와 내장 수익화 기능의 관계를 설명합니다. lines:7-7

- 공개 문서와 빠른 시작 자료로 설치부터 첫 통합까지 안내합니다. lines:7-7

- 설치, 어댑터, 빠른 시작 흐름과 주요 문서 및 자료를 실습합니다. lines:15-15

- 후반부에는 구현 질문, 지원 체인과 토큰, 어댑터 선택과 실무 사례를 다룹니다. lines:7-7

- 실시간 개발자 질의응답과 활용 사례 토론이 포함됩니다. lines:17-17

- 면책 안내: Circle Technology Services는 소프트웨어 제공자이며 규제 대상 금융 또는 자문 서비스를 제공하지 않습니다. lines:23-23

- 면책 안내: 서비스 제공자가 필요한 허가와 법 준수를 책임진다는 면책문구가 있습니다. lines:23-23

- 면책 안내: 뉴욕주 금융서비스국이 Arc를 검토하거나 승인하지 않았다고 명시합니다. lines:25-25

- 면책 안내: 제품 기능은 변경, 지연 또는 취소될 수 있으며 약속, 보증이나 투자 조언을 구성하지 않는다고 명시합니다. lines:27-27

- 면책 안내: USDC는 규제 대상 Circle 계열사가 발행하며 규제 인가 목록 링크를 제공합니다. lines:29-29

- 다시보기 URL이 기재되어 있습니다. lines:44-44

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Elton Tay / DevRel Lead, APAC / Circle [원문 그대로]

> Tim Baker / Community Manager / Circle [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/app-kits-developer-office-hours-bridge-swap-send-and-monetization-2026-04-20 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 140

> Building the Agentic Economy on Arc: VibeCard [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/building-the-agentic-economy-on-arc-vibecard)

페이지 일정 필드(UTC)는 2026-04-15T17:00:00.476Z부터 2026-04-15T18:00:00.476Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Sam Sealey와 Pete Budlong이 해커톤 수상 프로젝트 VibeCard를 설명하고 시연합니다. lines:7-7

- VibeCard는 공유에 대한 보상을 Arc의 Circle Wallets로 즉시 USDC 지급하는 네트워크입니다. lines:9-9

- 제작자는 보상 일부를 받고 일찍 공유한 사람은 이후 공유에서 발생하는 보상을 받습니다. lines:9-9

- Circle Wallets와 x402를 사용한 여러 수신자 대상 소액 결제, 보상 분할과 간편한 가입 경험을 시연합니다. lines:9-9

- 면책 안내: Circle Technology Services는 소프트웨어 제공자이며 규제 대상 금융 또는 자문 서비스를 제공하지 않습니다. lines:13-13

- 면책 안내: 서비스 제공자가 필요한 허가와 법 준수를 책임진다는 면책문구가 있습니다. lines:13-13

- 면책 안내: 뉴욕주 금융서비스국이 Arc를 검토하거나 승인하지 않았다고 명시합니다. lines:15-15

- 면책 안내: 제품 기능은 변경, 지연 또는 취소될 수 있으며 약속, 보증이나 투자 조언을 구성하지 않는다고 명시합니다. lines:17-17

- 면책 안내: USDC는 규제 대상 Circle 계열사가 발행하며 규제 인가 목록 링크를 제공합니다. lines:19-19

- 다시보기 URL이 기재되어 있습니다. lines:34-34

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 26행 행사는 2026-04-15이지만 46-47행 days는 2026-03-20부터 2026-03-21까지입니다. 7행은 recent 해커톤 수상 프로젝트로 설명하며 그 시점은 외부 자료를 열지 않아 확인하지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/building-the-agentic-economy-on-arc-vibecard-2026-04-15 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 141

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-1eu52c3sfr)

페이지 일정 필드(UTC)는 2026-04-14T17:00:00.356Z부터 2026-04-14T17:45:31.650Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord 전용 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계 개발자의 비공식 모임입니다. lines:7-7

- 질문하고 그 주의 최신 Arc 소식을 논의합니다. lines:7-7

- Discord 이벤트 링크에서 알림을 받을 수 있다고 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 알림용 Discord 이벤트 URL은 다른 일시의 공고에서도 반복됩니다. 외부 이벤트 페이지는 열지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1493628390916231371 / 한국어 정리

### 행사 142

> Arc House Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-house-office-hours-un7n6d3kef)

페이지 일정 필드(UTC)는 2026-04-07T17:00:00.370Z부터 2026-04-07T17:45:11.068Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=True`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=True`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 이번 주 Arc House에서 Office Hours를 시험한다고 안내합니다. lines:7-7

- Arc 커뮤니티 팀과 생태계 개발자의 비공식 모임입니다. lines:7-7

- 질문과 그 주의 최신 Arc 소식을 논의합니다. lines:7-7

- 모든 티켓이 초대 전용으로 표시되어 있습니다. lines:21-21

- 사전 등록 양식은 Discord 사용자명을 필수로 요구합니다. lines:63-65

- 사전 등록 양식은 영상과 함께 생태계 쇼케이스 포럼에 게시한 프로젝트의 링크를 필수로 요구합니다. lines:72-74

사전 등록 질문은 다음과 같다. 필수 여부는 질문마다 따로 기록한다.

> What is your discord username [원문 그대로]

필수 응답이다.

> Link to your project posted on ecosystem showcase forum with video. [원문 그대로]

필수 응답이다.

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 20행 행사 isInvitationOnly는 false지만 21행 isAllTicketOptionsInvitationOnly와 45행 티켓 isInvitationOnly는 true입니다.

### 행사 143

> ETHGlobal Cannes Hackathon [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/ethglobal-cannes-hackathon-aejsg2lm44)

페이지 일정 필드(UTC)는 2026-04-03T07:00:00.396Z부터 2026-04-04T22:00:00.396Z까지이며 표시 시간대는 Europe/Paris이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Palais des Festivals et des Congrès, 1 Bd de la Croisette, 06400 Cannes, France / Cannes / France [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 웹3 기술을 실험하고 관심 있는 아이디어를 개발하며 암호화폐 학습, 인맥 확대와 업계 관계자 및 동료와의 만남을 제공합니다. lines:7-7

- Arc는 후원자로서 온체인 대출, 자본시장, 외환과 결제를 개발하는 참가자에게 15,000달러 상금을 제공합니다. lines:9-9

- ETHGlobal Cannes 2026 등록 페이지로 연결합니다. lines:24-24

- 대면 장소는 프랑스 Cannes의 "Palais des Festivals et des Congrès"[원문 그대로]입니다. lines:29-32

- 공개 메타데이터는 시작 2026-04-03T07:00:00.396Z, 종료 2026-04-04T22:00:00.396Z, 시간대 Europe/Paris를 기록합니다. lines:16-18

- 공개 티켓은 Free Ticket이며 표시 가격은 0입니다. lines:106-106

- 온라인 여부는 false이고 초대 전용 여부는 false입니다. lines:21-23

- 발표자 목록은 Jenna Teeman의 직함을 Principle Program Manager, Developer Marketing, 소속을 Circle로 기록합니다. lines:45-47

- 발표자 목록은 Anthony Kelani의 직함을 Director of Ecosystem Growth, 소속을 Circle로 기록합니다. lines:55-57

- 발표자 목록은 Corey Cooper의 직함을 Senior Manager, Developer Relations and Ecosystem Marketing, 소속을 Circle로 기록합니다. lines:65-67

- 발표자 목록은 Blessing Adesiji의 직함을 Developer Relations Manager, EMEA, 소속을 Circle로 기록합니다. lines:75-77

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Jenna Teeman / Principle Program Manager, Developer Marketing  / Circle [원문 그대로]

> Anthony Kelani / Director of Ecosystem Growth  / Circle [원문 그대로]

> Corey Cooper / Senior Manager, Developer Relations and Ecosystem Marketing / Circle [원문 그대로]

> Blessing Adesiji / Developer Relations Manager, EMEA / Circle [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://ethglobal.com/events/cannes2026 / 한국어 정리
- https://ethglobal.com/events/cannes2026/prizes/arc / 한국어 정리

### 행사 144

> Introducing Arc House and Architects [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/introducing-arc-house-and-architects-hyp33duk9f)

페이지 일정 필드(UTC)는 2026-04-02T17:00:00.258Z부터 2026-04-02T18:00:00.258Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Arc House와 생태계 기여를 인정하고 보상하는 Architects 프로그램을 소개합니다. lines:7-7

- Arc House는 프로그램, 행사, 토론, 인정과 생태계 활동을 한 공간에 모읍니다. lines:7-7

- Architects의 포인트, 등급, 혜택과 역할의 관계 및 기여 인정과 시작 방법을 설명합니다. lines:9-9

- 다음 계획과 실시간 청중 질의응답을 포함합니다. lines:9-9

- 면책 안내: Architects는 독립적인 커뮤니티 참가자이며 Circle 직원이나 대리인이 아니라고 명시합니다. lines:13-13

- 면책 안내: 프로그램 참여는 고용, 대리, 제휴, 합작, 신탁 또는 다른 공식 관계를 만들지 않습니다. lines:13-13

- 면책 안내: 서면 권한 없이 Circle을 대표하여 발언할 수 없고 Circle을 구속할 수 없습니다. lines:13-13

- 면책 안내: 일부 역할과 기회에는 추가 조건과 사전 승인이 적용됩니다. lines:13-13

- 면책 안내: Circle Technology Services는 소프트웨어 제공자이며 규제 대상 금융 또는 자문 서비스를 제공하지 않습니다. lines:15-15

- 면책 안내: 서비스 제공자가 필요한 허가와 법 준수를 책임진다는 면책문구가 있습니다. lines:15-15

- 면책 안내: 뉴욕주 금융서비스국이 Arc를 검토하거나 승인하지 않았다고 명시합니다. lines:15-15

- 면책 안내: 제품 기능은 변경, 지연 또는 취소될 수 있으며 약속, 보증이나 투자 조언을 구성하지 않는다고 명시합니다. lines:15-15

- 다시보기 URL이 기재되어 있습니다. lines:30-30

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 22행 시작 일시는 2026-04-02인데 42-43행 days는 2026-03-27부터 2026-03-28까지입니다. 30행 다시보기 URL에는 2026-04-03이 포함되며 날짜의 의미는 설명되지 않습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/event-replay-introducing-arc-house-and-architects-2026-04-03 / 한국어 정리

### 행사 145

> ETHGlobal Pragma [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/ethglobal-pragma-l7dy3xfft9)

페이지 일정 필드(UTC)는 2026-04-02T07:00:00.095Z부터 2026-04-02T15:00:00.095Z까지이며 표시 시간대는 Europe/Paris이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

>  50 Bd de la Croisette, 06400 Cannes, France / Cannes / France [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Circle 팀은 ETHGlobal 해커톤에 앞서 Pragma에 참가하며 Arc 부스 방문을 안내합니다. lines:7-7

- 소수의 창업자와 개발자가 Web3의 미래와 과거를 논의하는 행사입니다. lines:9-9

- 동시에 진행되는 세션이 없다고 안내합니다. lines:11-11

- 본문은 초대 전용이라고 명시합니다. lines:13-13

- 유명 창업자 참여를 특징으로 제시합니다. lines:15-15

- 선별된 콘텐츠를 특징으로 제시합니다. lines:17-17

- 초보자 친화적 행사라고 안내합니다. lines:19-19

- 소규모의 친밀한 토론을 특징으로 제시합니다. lines:21-21

- Arc 부스로 찾아오라고 안내합니다. lines:23-23

- ETHGlobal의 Pragma Cannes 등록 링크가 기재되어 있습니다. lines:38-38

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Blessing Adesiji / Developer Relations Manager, EMEA / Circle [원문 그대로]

> Jenna Teeman / Principle Program Manager, Developer Marketing  / Circle [원문 그대로]

> Corey Cooper / Senior Manager, Developer Relations and Ecosystem Marketing / Circle [원문 그대로]

> Anthony Kelani / Director of Ecosystem Growth  / Circle [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 13행 본문은 Invite only이지만 36-37행 행사와 113행 티켓 초대 전용 플래그는 false입니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- [연결 주소](https://ethglobal.com/events/pragma-cannes2026)는 이번 요청에서 HTTP 403로 본문을 확보하지 못했다.

### 행사 146

> Building an Agentic Economy on Arc with RSoft Agentic Bank [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/building-an-agentic-economy-on-arc-with-rsoft-agentic-bank-79o43gi2cn)

페이지 일정 필드(UTC)는 2026-04-01T14:00:00.905Z부터 2026-04-01T15:00:10.555Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Sam과 Ricardo가 LabLab x Arc 해커톤 온라인 부문 1위 프로젝트를 소개합니다. lines:7-7

- RSoft Agentic Bank는 자율 에이전트의 신원 신호, 위험 점수와 정산을 프로그램으로 처리하는 기반을 개발합니다. lines:9-9

- Ricardo Pari가 전체 시스템과 구조를 설명합니다. lines:11-11

- 암호학적 에이전트 신원 확인 수단인 KYA를 다룹니다. lines:13-13

- 평판 기반의 동적 신용과 위험 신호를 다룹니다. lines:15-15

- USDC 자금의 추적과 할당을 다룹니다. lines:17-17

- Arc에서 에이전트 거래의 온체인 원자적 정산을 다룹니다. lines:19-19

- 면책 안내: Circle Technology Services는 소프트웨어 제공자이며 규제 대상 금융 또는 자문 서비스를 제공하지 않습니다. lines:23-23

- 면책 안내: 서비스 제공자가 필요한 허가와 법 준수를 책임진다는 면책문구가 있습니다. lines:23-23

- 면책 안내: 뉴욕주 금융서비스국이 Arc를 검토하거나 승인하지 않았다고 명시합니다. lines:25-25

- 면책 안내: 제품 기능은 변경, 지연 또는 취소될 수 있으며 약속, 보증이나 투자 조언을 구성하지 않는다고 명시합니다. lines:27-27

- 면책 안내: USDC는 규제 대상 Circle 계열사가 발행하며 규제 인가 목록 링크를 제공합니다. lines:29-29

- 다시보기 URL이 기재되어 있습니다. lines:44-44

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/event-replay-building-an-agentic-economy-on-arc-with-rsoft-agentic-bank-2026-04-02 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 147

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-l1in7rkbow)

페이지 일정 필드(UTC)는 2026-03-31T17:00:00.795Z부터 2026-03-31T17:45:09.174Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord 전용 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계 개발자의 비공식 모임입니다. lines:7-7

- 질문하고 그 주의 최신 Arc 소식을 논의합니다. lines:7-7

- Discord 이벤트 링크에서 알림을 받을 수 있다고 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 알림용 Discord 이벤트 URL은 다른 일시의 공고에서도 반복됩니다. 외부 이벤트 페이지는 열지 않았습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1475911760987947079 / 한국어 정리

### 행사 148

> Arc Community Spotlight: Social Payments with USDC Powered by XyloNet & PayX [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-community-spotlight-social-payments-with-usdc-powered-by-xylonet-and-payx-llol04mzdr)

페이지 일정 필드(UTC)는 2026-03-26T14:00:00.203Z부터 2026-03-26T15:00:52.903Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Forge Labs가 창업자 중심으로 Arc Testnet의 XyloNet과 PayX를 설명합니다. lines:7-7

- XyloNet은 스왑, 브리지와 금고로 구성되는 스테이블코인 DeFi 도구 묶음입니다. lines:7-7

- PayX는 X 계정에 USDC 팁을 주고 확인 절차를 거쳐 수령하는 소셜 결제 흐름입니다. lines:7-7

- Arc의 네이티브 USDC와 Bridge Kit을 통한 Circle CCTP V2의 결제 UX 및 체인 간 전송을 다룹니다. lines:9-9

- 실시간 데모, 기술 구조 설명과 유사 애플리케이션을 개발하는 실무 절차를 제공합니다. lines:9-9

- 면책 안내: Circle Technology Services는 소프트웨어 제공자이며 규제 대상 금융 또는 자문 서비스를 제공하지 않습니다. lines:13-13

- 면책 안내: 서비스 제공자가 필요한 허가와 법 준수를 책임진다는 면책문구가 있습니다. lines:13-13

- 면책 안내: 뉴욕주 금융서비스국이 Arc를 검토하거나 승인하지 않았다고 명시합니다. lines:15-15

- 면책 안내: 제품 기능은 변경, 지연 또는 취소될 수 있으며 약속, 보증이나 투자 조언을 구성하지 않는다고 명시합니다. lines:17-17

- 면책 안내: USDC는 규제 대상 Circle 계열사가 발행하며 규제 인가 목록 링크를 제공합니다. lines:19-19

- 다시보기 URL이 기재되어 있습니다. lines:34-34

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/event-replay-arc-community-spotlight-social-payments-with-usdc-powered-by-xylonet-and-payx-2026-03-26 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 149

> Agentic Economy on Arc Hackathon Kickoff Stream [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/nano-payments-arc-lablab-hackathon-kickoff)

페이지 일정 필드(UTC)는 2026-03-25T17:00:00.697Z부터 2026-03-25T18:00:00.697Z까지이며 표시 시간대는 America/Los_Angeles이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Agentic Economy on Arc 해커톤의 시작 방송입니다. lines:7-7

- AI 에이전트가 자체 USDC 지갑으로 자동 소액 결제를 하는 주제를 다룹니다. lines:9-9

- Circle의 Corey Cooper와 LabLab AI 공동 창업자 "Paweł Czech"[원문 그대로]가 에이전트 간 상거래를 논의합니다. lines:11-11

- 해커톤에서는 Circle Nanopayments와 Arc의 USDC 정산으로 에이전트 경제 애플리케이션을 개발합니다. lines:17-17

- 4월 20일부터 25일은 온라인 기간이며 25일까지 제출합니다. lines:21-21

- 4월 26일은 현장 데모와 시상일입니다. lines:25-25

- 개인 또는 팀으로 참가할 수 있습니다. lines:27-27

- 총 10,000달러 상금을 제시합니다. lines:29-29

- 현장 체험 승인을 받으면 직접 프로젝트를 시연할 기회가 있습니다. lines:31-31

- 여행과 숙박 비용은 지원하지 않습니다. lines:31-31

- 시작 방송 전 등록을 안내합니다. lines:33-33

- 4월 25일에는 샌프란시스코 현장에서 팀들이 프로젝트를 다듬습니다. lines:23-23

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Corey Cooper / Senior Manager, Developer Relations and Ecosystem Marketing / Circle [원문 그대로]

> Pawel Czech / Co-Founder / LabLab &  Surgexyz [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 13행은 3월 25일 10 AM PST라고 쓰지만 40행 startedAt은 2026-03-25T17:00:00.697Z이며 42행 timezone은 America/Los_Angeles입니다. PST 표기가 계절 시간대의 통칭인지 문자 그대로인지는 공고에서 설명하지 않습니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://arcnetwork.xyz/ / 한국어 정리
- https://www.circle.com/ / 한국어 정리

### 행사 150

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-994m55p9cx)

페이지 일정 필드(UTC)는 2026-03-24T17:00:00.365Z부터 2026-03-24T17:45:01.962Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord 전용 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계 개발자의 비공식 모임입니다. lines:7-7

- 질문하고 그 주의 최신 Arc 소식을 논의합니다. lines:7-7

- Discord 이벤트 링크에서 알림을 받을 수 있다고 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 알림용 Discord 이벤트 URL은 다른 일시의 공고에서도 반복됩니다. 외부 이벤트 페이지는 열지 않았습니다.
- 16행 startedAt은 2026-03-24T17:00:00.365Z인데 36행 days.startAt은 2026-03-25T04:00:00.000Z로 다른 날짜입니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1475911760987947079 / 한국어 정리

### 행사 151

> USDC OpenClaw Hackathon Winner Spotlight: ClawRouter by BlockRunAI [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/usdc-openclaw-hackathon-winner-spotlight-clawrouter-by-blockrunai-tstqae2ka9)

페이지 일정 필드(UTC)는 2026-03-19T18:00:00.913Z부터 2026-03-19T19:00:15.812Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Sam Sealey와 Vicky Fu가 USDC OpenClaw 해커톤 수상작 ClawRouter를 소개합니다. lines:7-7

- ClawRouter는 각 OpenClaw 에이전트에 자체 USDC 지갑을 부여합니다. lines:9-9

- 사람이 만든 계정이나 API 키 없이 LLM 추론을 직접 구매하도록 합니다. lines:9-9

- 로컬 점수 시스템으로 요청을 처리할 수 있는 가장 싼 모델을 선택합니다. lines:9-9

- 서명된 USDC 승인을 사용하여 요청마다 결제합니다. lines:9-9

- 자율 온체인 모델 선택 및 결제의 구조와 프로젝트를 로컬에서 실행하고 확장하는 방법을 설명합니다. lines:11-11

- 실습 데모, 엔지니어링 설명과 실시간 청중 질의응답이 포함됩니다. lines:11-11

- 면책 안내: Circle Technology Services는 소프트웨어 제공자이며 규제 대상 금융 또는 자문 서비스를 제공하지 않습니다. lines:15-15

- 면책 안내: 서비스 제공자가 필요한 허가와 법 준수를 책임진다는 면책문구가 있습니다. lines:15-15

- 면책 안내: 뉴욕주 금융서비스국이 Arc를 검토하거나 승인하지 않았다고 명시합니다. lines:17-17

- 면책 안내: 제품 기능은 변경, 지연 또는 취소될 수 있으며 약속, 보증이나 투자 조언을 구성하지 않는다고 명시합니다. lines:19-19

- 면책 안내: USDC는 규제 대상 Circle 계열사가 발행하며 규제 인가 목록 링크를 제공합니다. lines:21-21

- 다시보기 URL이 기재되어 있습니다. lines:36-36

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/replay-usdc-openclaw-hackathon-winner-spotlight-clawrouter-by-blockrunai-2026-03-19 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 152

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-iaclori3gi)

페이지 일정 필드(UTC)는 2026-03-17T17:00:00.717Z부터 2026-03-17T18:00:00.717Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord 전용 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계 개발자의 비공식 모임입니다. lines:7-7

- 질문하고 그 주의 최신 Arc 소식을 논의합니다. lines:7-7

- Discord 이벤트 링크에서 알림을 받을 수 있다고 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 알림용 Discord 이벤트 URL은 다른 일시의 공고에서도 반복됩니다. 외부 이벤트 페이지는 열지 않았습니다.
- 16행 startedAt은 2026-03-17T17:00:00.717Z인데 36행 days.startAt은 2026-03-18T04:00:00.000Z로 다른 날짜입니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1475911760987947079 / 한국어 정리

### 행사 153

> Build with Circle Nanopayments: Agentic Payments, Usage‑Based Billing, and Streaming Value [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/build-with-circle-nanopayments-agentic-payments-usage-based-billing-and-streaming-value-n88znh6avx)

페이지 일정 필드(UTC)는 2026-03-12T15:00:00.072Z부터 2026-03-12T16:00:00.072Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Sam Sealey와 Blessing Adesiji가 Circle Nanopayments를 실시간으로 설명합니다. lines:7-7

- x402와 Circle Gateway 일괄 정산으로 결제당 가스 비용 없는 높은 빈도의 1센트 미만 결제를 다룹니다. lines:7-7

- 수수료가 결제액보다 클 때 사용량 과금이 성립하지 않는 이유와 Nanopayments의 해결 방식을 다룹니다. lines:13-13

- HTTP 402 Payment Required로 API 자원에 가격을 매기고 판매하는 x402 방식을 설명합니다. lines:15-15

- 구매자가 Gateway에 한 번 입금하고 오프체인 결제 승인에 서명하는 방식을 설명합니다. lines:17-17

- 일괄 정산이 결제별 가스 비용을 없애는 방식을 설명합니다. lines:19-19

- Express API를 포함한 검증 및 미들웨어 방식의 판매자 통합을 다룹니다. lines:21-21

- 에이전트 결제, 사용량 과금, 기계 간 상거래와 연속 가치 지급을 개발 사례로 제시합니다. lines:23-23

- 청중 질의응답이 포함됩니다. lines:25-25

- 면책 안내: Circle Technology Services는 소프트웨어 제공자이며 규제 대상 금융 또는 자문 서비스를 제공하지 않습니다. lines:29-29

- 면책 안내: 서비스 제공자가 필요한 허가와 법 준수를 책임진다는 면책문구가 있습니다. lines:29-29

- 면책 안내: 뉴욕주 금융서비스국이 Arc를 검토하거나 승인하지 않았다고 명시합니다. lines:31-31

- 면책 안내: 제품 기능은 변경, 지연 또는 취소될 수 있으며 약속, 보증이나 투자 조언을 구성하지 않는다고 명시합니다. lines:33-33

- 면책 안내: USDC는 규제 대상 Circle 계열사가 발행하며 규제 인가 목록 링크를 제공합니다. lines:35-35

- 다시보기 URL이 기재되어 있습니다. lines:50-50

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Sam Sealey / Director, Community  / Circle [원문 그대로]

> Blessing Adesiji / Developer Relations Manager, EMEA / Circle [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/build-with-circle-nanopayments-agentic-payments-usagebased-billing-and-streaming-value-2026-03-12 / 한국어 정리
- https://www.circle.com/legal/licenses?_gl=1\*chseek\*_gcl_au\*MjQyNzQzODQ3LjE3NzAxMjkxNjguNTMzMTg2Mjc2LjE3NzIxMTg1NTcuMTc3MjExODc1Nw / 한국어 정리

### 행사 154

> Arc Discord Architecture Review (Design Clinic) [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-architecture-review-design-clinic-60rn65umlw)

페이지 일정 필드(UTC)는 2026-03-11T12:30:00.661Z부터 2026-03-11T13:30:16.843Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Arc Discord 전용 실시간 세션입니다. lines:7-7

- 커뮤니티 개발자와 함께 진행합니다. lines:7-7

- 참가자의 시스템 설계 또는 계약 패턴을 검토하고 다음 작업에 집중합니다. lines:7-7

- Discord 초대 링크가 등록 URL로 기재되어 있습니다. lines:22-22

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.gg/buildonarc / 한국어 정리

### 행사 155

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-o8ev4wxduk)

페이지 일정 필드(UTC)는 2026-03-10T17:00:00.873Z부터 2026-03-10T17:45:00.873Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Discord 전용 Office Hours 세션입니다. lines:7-7

- Arc 커뮤니티 팀과 생태계 개발자의 비공식 모임입니다. lines:7-7

- 질문하고 그 주의 최신 Arc 소식을 논의합니다. lines:7-7

- Discord 이벤트 링크에서 알림을 받을 수 있다고 안내합니다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 9행의 알림용 Discord 이벤트 URL은 다른 일시의 공고에서도 반복됩니다. 외부 이벤트 페이지는 열지 않았습니다.
- 16행 startedAt은 2026-03-10T17:00:00.873Z인데 36행 days.startAt은 2026-03-03T05:00:00.000Z로 다른 날짜입니다.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1475911760987947079 / 한국어 정리

### 행사 156

> Arc Discord Show and Tell (Lightning Demos) [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-show-and-tell-lightning-demos-zb35cf328l)

페이지 일정 필드(UTC)는 2026-03-05T18:00:00.239Z부터 2026-03-05T19:00:06.115Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Arc Discord 전용 실시간 데모 세션입니다. lines:7-7

- 개발자가 무대에서 5분 데모를 할 수 있습니다. lines:7-7

- 작은 성과의 발표도 권장합니다. lines:7-7

- Discord 초대 링크가 등록 URL로 기재되어 있습니다. lines:22-22

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.gg/buildonarc / 한국어 정리

### 행사 157

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-74d0lbk505)

페이지 일정 필드(UTC)는 2026-03-03T06:00:00.028Z부터 2026-03-03T07:00:41.622Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Arc 커뮤니티 팀과 다른 개발자가 Discord에서 편하게 질문하고 매주 최신 소식을 다루는 Office Hours이다. lines:7-7

- Discord 행사 링크에서 참여 알림을 설정하도록 안내한다. lines:9-9

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1475911760987947079 / 한국어 정리

### 행사 158

> Arc x Encode Enterprise & DeFi Hackathon [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-x-encode-enterprise-and-defi-hackathon-vcm38l2yye)

페이지 일정 필드(UTC)는 2026-02-27T15:00:00.990Z부터 2026-03-01T15:00:00.990Z까지이며 표시 시간대는 Europe/London이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Encode Club / 41 Pitfield St, London N1 6DA, UK, London, UK / London / United Kingdon [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Arc에서 DeFi, 기업 금융, 은행 인프라와 프로그래밍 가능한 화폐를 개발하는 해커톤이다. lines:9-9

- Encode Hub에서 3일간 현장 멘토링, 기술 세션과 통합 지원을 제공하며 여러 트랙의 총상금은 10,000달러이다. lines:11-11

- StableFX, USYC와 Circle Payments Network는 접근 허가가 필요한 기업 제품이므로 자격 증명과 시작 지원을 받도록 조기 등록을 안내한다. lines:13-13

- 금요일 오후 3시부터 5시까지 체크인한다. lines:19-19

- 금요일에는 개회, 간식, 오후 5시 30분부터 7시까지 워크숍, 저녁 식사와 오후 8시 이후 개발 시간이 있다. lines:21-29

- 토요일에는 24시간 개발과 아침, 점심, 간식을 안내한다. lines:33-39

- 일요일 정오에 제출을 마감하고 정오부터 오후 2시까지 심사한다. lines:45-47

- 일요일 오후 2시에 최종 발표를 하고 오후 3시에 마무리한다. lines:49-51

- 일요일 오전 8시에 아침 식사를 제공한다. lines:43-43

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Corey Cooper / Senior Manager, Developer Relations and Ecosystem Marketing / Circle [원문 그대로]

> Blessing Adesiji / Developer Relations Manager, EMEA / Circle [원문 그대로]

> Anthony Kelani / Director of Ecosystem Growth  / Circle [원문 그대로]

> Jenna Teeman / Principle Program Manager, Developer Marketing  / Circle [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/or9m52bp?tk=ZIBdMJ / 한국어 정리

### 행사 159

> Arc Discord Office Hours [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-discord-office-hours-lb26t214a4)

페이지 일정 필드(UTC)는 2026-02-24T18:00:00.935Z부터 2026-02-24T18:00:34.107Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Arc 커뮤니티 팀과 개발자가 Discord에서 질문하고 매주 최신 소식을 다루는 Office Hours이다. lines:7-7

- Discord 행사 링크에서 참여 알림을 설정하도록 안내한다. lines:9-9

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- startedAt와 endedAt가 같은 날 18:00:00.935Z 및 18:00:34.107Z로 표시된다. lines:16-17.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://discord.com/events/1423729540160815207/1475911760987947079 / 한국어 정리

### 행사 160

> Arc Side Quest at ETHDenver [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arcdenver)

페이지 일정 필드(UTC)는 2026-02-19T01:00:00.016Z부터 2026-02-19T04:00:57.198Z까지이며 표시 시간대는 America/Denver이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> 2734 Walnut St / F1 Arcade Denver / Denver / CO / 80205 [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Arc 팀, 업계 관계자와 개발자가 Denver의 F1 Arcade에 모이는 행사이다. lines:7-7

- Formula One 코스를 재현하는 움직이는 레이싱 시뮬레이터, 칵테일과 음식을 제공한다. lines:9-9

- Arc 팀과 직접 대화하고 암호화폐와 금융의 실제 활용을 논의하며 Arc의 속도, 신뢰와 상호운용성을 소개한다. lines:11-11

- 자리가 제한되어 있으므로 신청하도록 안내한다. lines:15-15

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 행사 startedAt 및 endedAt와 days의 날짜 범위가 다르다. lines:22-23,51-52.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/arcdenver2026?utm_source=arc-gradual / 한국어 정리

### 행사 161

> Arc Meetup London — Presented by Encode Club [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-meetup-london-presented-by-encode-club-fxva111t6b)

페이지 일정 필드(UTC)는 2026-02-12T09:00:00.494Z부터 2026-02-12T17:00:27.875Z까지이며 표시 시간대는 Europe/London이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> 41 Pitfield St, London N1 6DA, UK / London / UK [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> registrant [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=True`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Arc DeFi 해커톤을 앞두고 열리는 London 모임이다. lines:7-7

- 개발자, 창업자와 DeFi 팀이 Arc의 다음 계획을 논의한다. lines:9-9

- 생태계를 자세히 소개하고 Arc 팀과 다른 개발자를 만나 해커톤 아이디어를 미리 준비하는 시간이다. lines:11-15

- 이미 개발 중인 사람뿐 아니라 Arc를 알아보려는 사람도 초대한다. lines:21-21

- 대출, 자본 시장, 외환과 결제에서 통화와 자산 간 유동성을 다루는 Arc를 소개한다. lines:25-25

- USDC부터 시작하는 낮고 예측 가능한 법정화폐 기준의 스테이블코인 가스 요금을 소개한다. lines:29-29

- Malachite BFT 합의 엔진을 통한 1초 미만의 거래 확정(deterministic finality)을 소개한다. lines:31-31

- 규정을 준수하면서 잔액과 거래를 선택적으로 숨길 수 있는 개인정보 보호 설정을 소개한다. lines:33-33

- USDC, EURC, USYC, Mint, Wallets, Contracts, CCTP, Gateway와 Circle Payments Network 통합을 소개한다. lines:35-35

- 저녁 일정은 입장과 교류, 프로그래밍 가능한 화폐와 DeFi 및 기업 금융 발표, 해커톤 형식과 주제 소개, 질의와 교류로 구성된다. lines:104-194

- 참석하면 촬영과 녹음, 이름과 약력 및 초상의 이용을 취소할 수 없게 허용하고 추가 동의 없이 홍보 등에 사용할 수 있도록 동의한다. lines:47-47

- 티켓 설명에서 Luma 등록이 필요하다고 안내한다. lines:223-223

- 면책 안내: 제품 설명은 정보 제공이며 확약, 보증이나 투자 조언이 아니라는 면책 고지가 있다. lines:45-45

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Blessing Adesiji / Developer Relations Manager, EMEA / Circle [원문 그대로]

> Anthony  Beaumont / CEO and co-founder / Encode Club [원문 그대로]

공개 세션은 다음과 같다. 제목과 설명은 원문 표기를 유지하며 시각은 각 세션의 UTC 데이터다.

> Doors Open & Networking [원문 그대로]

세션 시각: `2026-02-12T18:30:00.000Z` - `2026-02-12T19:00:00.000Z`.

> Arrival and informal networking with builders, the Encode team, and Arc / Circle representatives. [원문 그대로]

> Short Talks & Lightning Sessions [원문 그대로]

세션 시각: `2026-02-12T19:00:00.000Z` - `2026-02-12T19:30:00.000Z`.

> Brief talks from the Arc team covering the vision and real-world use cases across programmable money, DeFi, and enterprise finance. [원문 그대로]

> 발표자: Blessing Adesiji / Developer Relations Manager, EMEA / Circle [원문 그대로]

> What’s Next: Arc Hackathon Preview [원문 그대로]

세션 시각: `2026-02-12T19:30:00.000Z` - `2026-02-12T20:00:00.000Z`.

> Early insights into the upcoming Arc IRL hackathon, including themes, format, and how to get a head start. [원문 그대로]

> 발표자: Anthony  Beaumont / CEO and co-founder / Encode Club [원문 그대로]

> Open Networking [원문 그대로]

세션 시각: `2026-02-12T20:00:00.000Z` - `2026-02-12T21:00:00.000Z`.

> Dedicated time for builders to connect, ask questions, and explore early ideas ahead of the hackathon. [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문과 agenda는 저녁 일정인데 startedAt 및 endedAt는 09:00Z부터 17:00Z이다. lines:19,54-55,104-194.
- 티켓은 isFull true이며 대기 명단은 false이다. lines:226-231.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/c5keppbm / 한국어 정리

### 행사 162

> ETHGlobal Hack Money DeFi Hackathon [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/ethglobal-hack-money-defi-hackathon-x4185sibue)

페이지 일정 필드(UTC)는 2026-01-30T05:00:00.442Z부터 2026-02-12T05:00:00.442Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- 세계 각지에서 비동기로 참여하는 온라인 DeFi 해커톤이다. lines:7-7

- 탐색 메뉴의 Groups에서 HackMoney를 찾아 해당 그룹으로 이동하도록 안내한다. lines:11-15

- 그룹에서 게시물을 만들고 Question 형식을 권장한다. lines:17-19

- 팀과 커뮤니티가 답변하며 해결한 답변을 정답으로 표시하도록 안내한다. lines:21-23

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> HJ Chen / Senior Manager, Developer Relations and Ecosystem Marketing / Circle [원문 그대로]

### 행사 163

> OpenClaw USDC Hackathon on Moltbooks [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/openclaw-usdc-hackathon-on-moltbooks-xdk1tu0nvo)

페이지 일정 필드(UTC)는 2026-02-04T01:00:22.443Z부터 2026-02-08T20:00:22.443Z까지이며 표시 시간대는 America/Los_Angeles이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Hybrid`로 표시되어 있다.

- AI 에이전트가 작품을 제출하고 투표하며 온체인에서 USDC를 이동하는 실험적인 해커톤이다. lines:11-11

- Moltbook은 AI 에이전트가 글, 댓글, 토론과 협업을 하고 사람은 관찰하는 소셜 네트워크이며 submolt라는 커뮤니티를 설명한다. lines:13-13

- OpenClaw 에이전트는 Clawdbots나 Moltbots로도 불린다고 설명한다. lines:15-15

- 사람의 심사 없이 에이전트가 공개적으로 제출하고 투표하며 USDC로 보상을 정산한다. lines:21-21

- 총 30,000 USDC를 세 트랙에 제공한다. lines:25-25

- Agentic Commerce 트랙은 에이전트가 USDC로 가격을 정하고 지급하며 인센티브와 협업을 구성하는 활동이다. lines:29-29

- Best OpenClaw Skill 트랙은 추론, 도구 사용과 온체인 상호작용을 개선하는 기능을 다룬다. lines:33-33

- Most Novel Smart Contract 트랙은 에이전트의 자율성, 협업과 실행을 위한 계약을 개발하고 배포하거나 상호작용하는 활동이다. lines:37-37

- 2월 8일 정오 PST를 마감으로 안내한다. lines:49-49

- Moltbook의 m/usdc에서 진행하며 제출 링크와 ClawHub 기능 및 설치 안내를 제공한다. lines:51-55

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문은 Moltbook에서 진행한다고 설명하지만 행사 및 티켓 참여 방식은 Hybrid로 표시된다. lines:19,66,96-97.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://www.clawhub.ai/swairshah/usdc-hackathon / 한국어 정리
- https://www.moltbook.com/m/usdc / 한국어 정리
- https://www.moltbook.com/post/b021cdea-de86-4460-8c4b-8539842423fe / 한국어 정리

### 행사 164

> Day One Architect: Para [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/day-one-architect-para-2810vw0dyd)

페이지 일정 필드(UTC)는 2026-02-05T18:00:00.522Z부터 2026-02-05T19:00:19.194Z까지이며 표시 시간대는 America/Los_Angeles이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Arc에서 실제 제품을 만드는 초기 개발자 시리즈로 Para의 내장형 지갑을 몇 가지 설정으로 준비하는 내용을 다룬다. lines:7-7

- Arc 체인 설정, 가입 과정의 불편 감소, 지갑 생성, 인증과 키 관리를 다룬다. lines:9-9

- 스테이블코인 가스, 즉시 거래 확정, 체인 간 유동성과 규정 준수 및 익숙한 사용자 경험을 다룬다. lines:11-11

- 내장형 지갑과 다른 지갑 방식의 차이, EVM과 Cosmos SDK 기반 여러 체인 지원을 다룬다. lines:13-13

- 핀테크와 암호화폐 앱 개발자를 위한 문서와 시작 자료를 안내한다. lines:15-15

- 등록하고 일정에 추가하도록 안내한다. lines:17-17

- 기존 금융(TradFi) 통합과의 관계를 다룬다. lines:11-11

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Anthony Kelani / Director of Ecosystem Growth  / Circle [원문 그대로]

> Aditi Sriram / Head of Business / Para [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/event-replay-day-one-architect-para-2026-02-05 / 한국어 정리

### 행사 165

> Agentic Commerce on Arc Hackathon Hosted by LabLab.ai [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/agentic-commerce-on-arc-hackathon-hosted-by-lablab-ai)

페이지 일정 필드(UTC)는 2026-01-09T17:00:00.217Z부터 2026-01-25T01:00:00.217Z까지이며 표시 시간대는 America/Los_Angeles이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> MindsDB / 3154 17th Street / San Francisco / CA / USA [원문 그대로]

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Hybrid`로 표시되어 있다.

- Arc와 Circle을 활용한 두 번째 해커톤으로 에이전트 결제를 다룬다. lines:9-9

- Arc와 Circle 파트너가 제시하는 실제 문제를 개발 과제로 삼는다. lines:13-13

- USDC를 기본 가스 토큰으로 쓰는 Arc를 활용한다. lines:15-15

- AI, 결제와 온체인 경제를 개발하는 팀에게 직접 배우고 세계 각지의 개발자와 교류하도록 안내한다. lines:17-19

- 등록하고 팀을 구성해 개발을 시작하도록 안내한다. lines:21-21

- 1월 9일부터 24일까지 진행한다. lines:25-25

- 온라인 참여와 1월 23일부터 24일까지 San Francisco 현장 참여를 안내한다. lines:27-27

- 거주지 질문은 필수가 아니며 향후 행사 장소를 계획하기 위한 질문이다. lines:122-124

사전 등록 질문은 다음과 같다. 필수 여부는 질문마다 따로 기록한다.

> What is your country of residence? [원문 그대로]

필수로 표시되지 않은 응답이다.

> *used to determine location of future events [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://lablab.ai/event/agentic-commerce-on-arc / 한국어 정리

### 행사 166

> Arc Meetup San Francisco — Presented by Thirdweb [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-meetup-san-francisco-presented-by-thirdweb-p621phpopg)

페이지 일정 필드(UTC)는 2026-01-16T01:00:11.727Z부터 2026-01-16T03:30:51.727Z까지이며 표시 시간대는 America/Los_Angeles이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> 2 Marina Blvd B300, San Francisco, CA 94123 / San Francisco / California / USA [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Arc를 여러 생태계 사이에서 스테이블코인 유동성을 이동하는 중심 네트워크로 소개하는 모임이다. lines:7-7

- 실시간 시연으로 상호운용성 기능을 소개한다. lines:9-9

- CCTP와 새로운 Bridge Kit SDK를 다룬다. lines:11-11

- Gateway의 여러 체인을 통합한 잔액을 다룬다. lines:13-13

- 개발자 자금 지원 기회를 소개한다. lines:15-15

- 여러 체인 활용의 다음 단계를 논의하는 패널이 있다. lines:17-17

- 패널에는 thirdweb의 Furqan, Daimo Pay의 Gianluca와 Circle의 Alokik이 참여한다. lines:19-19

- Arc와 다른 블록체인에서 실제 제품을 개발하는 사람들과 교류한다. lines:21-21

- QR 체크인과 가벼운 음식 및 교류 후 발표와 시연, 패널, 질의와 교류를 진행한다. lines:109-221

- 참석하면 녹음과 촬영 및 이름, 약력과 초상 이용을 허용하고 추가 동의 없이 홍보 등에 사용할 수 있도록 동의한다. lines:33-33

- 거주지 질문은 필수가 아니며 향후 행사 장소를 계획하기 위한 질문이다. lines:272-274

- 면책 안내: 제품 설명은 확약, 보증이나 투자 조언이 아니라는 면책 고지이다. lines:31-31

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Furqan Rydhan / Founder / Thirdweb [원문 그대로]

> Anthony Kelani / Director of Ecosystem Growth  / Circle [원문 그대로]

> Alokik Bhasin / Director, Product Management / Circle [원문 그대로]

> Gianluca Minoprio / Head of Growth / Daimo [원문 그대로]

공개 세션은 다음과 같다. 제목과 설명은 원문 표기를 유지하며 시각은 각 세션의 UTC 데이터다.

> Check-In & Welcome [원문 그대로]

세션 시각: `2026-01-16T01:00:00.000Z` - `2026-01-16T01:30:00.000Z`.

> Attendees check in using the Gradual QR code. Light refreshments and networking. [원문 그대로]

> Welcome and Circle Interop Overview [원문 그대로]

세션 시각: `2026-01-16T01:30:00.000Z` - `2026-01-16T02:00:00.000Z`.

> A short presentation + demos of Arc and Circle's interops + funding opportunities [원문 그대로]

> 발표자: Anthony Kelani / Director of Ecosystem Growth  / Circle [원문 그대로]

> Panel Discussion [원문 그대로]

세션 시각: `2026-01-16T02:00:00.000Z` - `2026-01-16T02:30:00.000Z`.

> Panel discussion with Furqan (thirdweb), Gianluca (Daimo Pay), and Alokik (Circle) discussing the future of onchain interoperability. [원문 그대로]

> 발표자: Alokik Bhasin / Director, Product Management / Circle [원문 그대로]

> 발표자: Furqan Rydhan / Founder / Thirdweb [원문 그대로]

> 발표자: Gianluca Minoprio / Head of Growth / Daimo [원문 그대로]

> Q&A and Networking [원문 그대로]

세션 시각: `2026-01-16T02:30:00.000Z` - `2026-01-16T03:30:00.000Z`.

사전 등록 질문은 다음과 같다. 필수 여부는 질문마다 따로 기록한다.

> What is your country of residence? [원문 그대로]

필수로 표시되지 않은 응답이다.

> *used to determine location of future events [원문 그대로]

### 행사 167

> Technical Insights on Arc Testnet Reliability [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/technical-insights-on-arc-testnet-reliability-p6lj4gragb)

페이지 일정 필드(UTC)는 2025-12-19T16:00:00.242Z부터 2025-12-19T17:00:01.008Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Adi Seredinschi가 Arc 테스트넷의 신뢰성, 예측 가능한 성능과 블록 시간을 설명한다. lines:11-11

- Reth와 Malachite를 어떻게 시험하는지 다룬다. lines:15-15

- 스트레스 시험 도구인 Quake, Guzzler와 Spammer를 다룬다. lines:17-17

- 검증자 사이에서 약 500ms 블록 주기를 안정적으로 유지하는 방법을 다룬다. lines:19-19

- 설계 선택의 장단점과 자세한 기술 내용을 다룬다. lines:21-21

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Adi Seredinschi / Principal Product Manager / Circle [원문 그대로]

> Corey Cooper / Senior Manager, Developer Relations and Ecosystem Marketing / Circle [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/public/videos/event-replay-technical-insights-on-arc-testnet-reliability-2025-12-19 / 한국어 정리

### 행사 168

> Crosschain Payments with CCTP Fast Transfer [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/crosschain-payments-with-cctp-fast-transfer-hwwm35tym4)

페이지 일정 필드(UTC)는 2025-12-15T18:00:25.534Z부터 2025-12-15T19:00:34.672Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Trails와 함께 CCTP Fast Transfer를 다루는 실시간 워크숍이다. lines:7-7

- CCTP를 사용한 체인 간 흐름 설계와 USDC 활용 방법을 다룬다. lines:13-13

- CCTP 내부 동작을 설명한다. lines:17-17

- 체인 간 결제 흐름을 설계하는 방법을 다룬다. lines:19-19

- USDC 활용의 권장 구현 방식을 설명한다. lines:21-21

- 여러 체인 사이에서 매끄럽게 거래하는 경험을 다룬다. lines:23-23

- Trails는 디지털 자산을 한 번의 클릭으로 보내거나 사용하는 거래 기반 기능으로 소개한다. lines:27-27

- 참가자의 질문을 받도록 안내한다. lines:35-35

- 면책 안내: CTS가 규제 금융이나 자문 서비스를 제공하지 않는다는 면책 고지가 있으나 문장의 끝이 잘려 있다. lines:39-39

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> James Lawton / Head of DevRel / Trails [원문 그대로]

> Sam Sealey / Director, Community  / Circle [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 면책 고지 문장이 responsible for service에서 끝나 있다. lines:39.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/event-replay-crosschain-payments-with-cctp-2025-12-15 / 한국어 정리

### 행사 169

> Day One Architect: Hinkal [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/day-one-architect-hinkal-xws9y2anoh)

페이지 일정 필드(UTC)는 2025-12-12T18:00:00.507Z부터 2025-12-12T19:00:34.573Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Hinkal CEO Georgi Koreli와 Anthony Kelani가 대화한다. lines:9-9

- 잔액, 이체와 거래 상대를 공개하지 않으면서 온체인 검증을 제공하는 지갑을 기관, 기업과 일반 사용자의 용도로 소개한다. lines:11-11

- 공개 지갑과 거래 상대 정보가 만드는 위험, 정보를 드러내지 않는 안전하고 감사 가능한 결제를 다룬다. lines:13-13

- Arc의 USDC 가스, 즉시 거래 확정, 빠른 정산과 Circle 인프라를 다룬다. lines:15-15

- 잔액과 거래 이력을 드러내지 않는 지갑 간 비공개 이체를 실시간 시연한다. lines:17-17

- 개인과 기관의 위험 및 새로운 활용 사례를 논의한다. lines:19-19

- 세계 자본 이동과 금융 개인정보 보호를 다룬다. lines:21-21

- 향후 개인정보 보호 채택 계획을 논의한다. lines:23-23

- 면책 안내: 제품 설명이 확약, 보증이나 투자 조언이 아니라는 면책 고지가 있다. lines:31-31

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Anthony Kelani / Director of Ecosystem Growth  / Circle [원문 그대로]

> Georgi Koreli / Co-Founder, CEO / Hinkal [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/event-replay-day-one-architect-hinkal-2025-12-12 / 한국어 정리
- https://www.circle.com/legal/licenses / 한국어 정리

### 행사 170

> Arcshop; Gateway with Blockradar [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arcshop-gateway-with-blockradar-qrzj2qi9wk)

페이지 일정 필드(UTC)는 2025-12-11T15:00:00.527Z부터 2025-12-11T16:00:33.854Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Circle 개발자 생태계 팀과 Blockradar가 핀테크 지갑 및 Gateway 기반 체인 간 결제를 설명한다. lines:9-9

- Abdulfatai Suleiman과 비수탁형 하위 지갑 기능을 소개한다. lines:9-9

- 핀테크의 규정 준수 불확실성, 지갑과 체인 개발의 복잡성, 여러 체인에서 들어오는 자금 대조 문제를 다룬다. lines:11-11

- 분산된 USDC 입금을 통합 잔액으로 관리하고 자동 정산 같은 작업을 자동화하거나 자금을 수동으로 관리하는 방법을 다룬다. lines:11-11

- 실시간 API 통합, 상위 및 하위 지갑 설정과 향후 하위 지갑 확장을 다룬다. lines:13-13

- 구현 관련 질문에 답하는 시간이 있다. lines:15-15

- 면책 안내: 제품 설명은 확약, 보증이나 투자 조언이 아니라는 면책 고지가 있다. lines:21-21

- 면책 안내: Circle Mint가 기관에만 제공된다는 제품 고지가 있다. lines:25-25

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Abdulfatai  Suleiman / Co-Founder, CEO / Blockradar [원문 그대로]

> Sam Sealey / Director, Community  / Circle [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 본문에 해결되지 않은 contentReference 표지가 포함된다. lines:9,11,13.
- 하위 지갑 기능을 최신 출시로도 향후 확장으로도 설명한다. lines:9,13.
- Abdulfatai Suleiman을 본문에서는 Product Engineering Lead로, 발표자 필드에서는 CEO로 표시한다. lines:9,53.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/event-replay-gateway-with-blockradar-2025-12-11 / 한국어 정리
- https://www.circle.com/legal/licenses / 한국어 정리

### 행사 171

> Event Replay: Arcshop- Introducing Bridge Kit [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/event-replay-arcshop-introducing-bridge-kit-xf7ek47gqf)

페이지 일정 필드(UTC)는 2025-12-10T16:30:00.134Z부터 2025-12-10T17:30:13.504Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- CCTP로 체인 간 USDC 이동을 쉽게 구현하는 Bridge Kit 워크숍이다. lines:9-9

- Dave Musicant와 Tobias Golbs가 체인, 지갑 제공자와 앱 작업을 추상화해 10줄 미만 코드로 구현하고 FeeTaker로 수익을 얻는 기능을 설명한다. lines:11-11

- Arc에서 Ethereum 테스트넷으로 이동하는 시연을 한다. lines:15-15

- 거의 코드를 바꾸지 않고 Arc에서 Solana로 이동하는 시연을 한다. lines:17-17

- Circle Wallets 어댑터를 다룬다. lines:19-19

- 개발자 수수료를 자신의 지갑으로 받는 방법을 다룬다. lines:21-21

- 설정, 다른 기능과의 조합, 메인넷 준비, 문서와 튜토리얼 및 지원을 안내한다. lines:23-23

- 개발자 문서를 안내한다. lines:25-25

- 면책 안내: 제품 설명이 확약, 보증이나 투자 조언이 아니라는 면책 고지가 있다. lines:31-31

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Dave Musicant / Sr Director, Engineering / Circle [원문 그대로]

> Tobias Golbs / Eng Manager / Circle [원문 그대로]

> Sam Sealey / Director, Community  / Circle [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/arcshop-event-replay-introducing-bridge-kit-2025-12-09 / 한국어 정리
- https://developers.circle.com/bridge-kit / 한국어 정리

### 행사 172

> Day One Architect: Crossmint [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/day-one-architect-crossmint-vdu7jo0a1i)

페이지 일정 필드(UTC)는 2025-12-05T18:00:00.331Z부터 2025-12-05T19:00:34.942Z까지이며 표시 시간대는 America/Los_Angeles이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Arc 공개 테스트넷 초기 파트너 Crossmint의 기업 지갑과 결제 인프라를 소개한다. lines:7-7

- 내장형 지갑, 법정화폐에서 디지털 자산으로 전환하는 기능, 결제와 에이전트 상거래 API를 소개하며 수백 기업과 개발자 40,000명 이상이 이용한다고 서술한다. lines:9-9

- 내장형 지갑과 USDC를 다룬다. lines:13-13

- 세계 각지의 자산 구매와 결제 기능을 다룬다. lines:15-15

- 에이전트 상거래와 자동화된 프로그래밍 가능한 결제를 다룬다. lines:17-17

- USDC 정산과 Arc 실행 기능을 다룬다. lines:19-19

- 즉시 거래 확정, 예측 가능한 USDC 가스와 규정 준수 인프라를 다룬다. lines:21-21

- Rodri Fernandez Touza와 Corey Cooper가 결제 자동화와 세계 상거래를 논의한다. lines:23-23

- 면책 안내: 제품 설명이 확약, 보증이나 투자 조언이 아니라는 면책 고지가 있다. lines:29-29

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Corey Cooper / Senior Manager, Developer Relations and Ecosystem Marketing / Circle [원문 그대로]

> Rodri  Fernández Touza / Co-Founder / Crossmint [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/event-replay-day-one-architect-crossmint / 한국어 정리

### 행사 173

> Trustless USDC Agents on Arc [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/trustless-usdc-agents-on-arc-bw4adrg7ac)

페이지 일정 필드(UTC)는 2025-12-03T18:00:00.225Z부터 2025-12-03T19:00:09.363Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- NovaNet 공동 창업자 Humane Shadab과 Wyatt Benno 및 Sam Sealey가 AI 에이전트의 자금 사용, 규정 준수와 안전 관련 모델 실행을 영지식 증명으로 검증하는 ZKML을 소개한다. lines:9-9

- Arc를 선택한 이유로 1초 미만의 거래 확정(deterministic finality), 예측 가능한 스테이블코인 가스, 가스와 자산에 같은 토큰 사용 및 Circle 지갑, 규정 준수, 외환과 체인 간 기능 조합을 설명한다. lines:11-11

- 에이전트 결정에 암호학적 증명을 붙여 평판이나 수동 감독에만 의존하지 않고 모델 실행을 검증하는 방식을 설명한다. lines:13-13

- USDC 지출 에이전트 시연에서 Oak가 작업을 조정하고 지출 정책 모델이 승인 여부를 판단하며 ZKML 증명을 생성한다. lines:15-15

- 증명 비용을 x402로 지불하고 거래 데이터와 서명을 묶어 Arc에서 실행한 뒤 증명을 온체인 기록으로 남긴다. lines:15-15

- Circle 지갑을 보유한 에이전트 둘이 Circle 규정 준수 엔진의 자료로 정책 충족 여부를 모델에 판단시키고 ZKML 검증 후 USDC를 지급한다. lines:17-17

- 이체, 증명 해시와 에이전트 행동을 연결한 기록으로 기관의 관리와 규정 준수 검증을 지원하는 시연이다. lines:17-17

- 서로 다른 체인의 로봇이 서비스 비용을 USDC로 지급하며 센서와 시각 모델이 충돌 등을 감지해 x402 지급을 유발하고 Gateway로 체인 간 자금을 이동한다. lines:19-19

- 로봇 장치에서 ZKML을 실행해 센서와 모델의 실행을 검증한 뒤 지급을 승인한다. lines:19-19

- Jolt Atlas는 거대 언어 모델보다 작은 분류 모델에 집중하고 Jolt의 RISC-V 중심 설계를 ONNX로 바꾸어 Hugging Face 등의 모델을 연결한다. lines:21-21

- Sumcheck와 조회 테이블을 사용해 선형 및 비선형 연산, ReLU와 softmax를 처리하며 장치에서 쓸 수 있는 빠르고 메모리 효율적인 증명을 설명한다. lines:23-23

- 기존 공개 구현 대비 흔히 4배에서 8배 빠른 벤치마크 결과를 서술한다. lines:23-23

- folding schemes는 일별 규정 준수 검사나 게임 및 에이전트 거래의 여러 증명을 하나로 합쳐 온체인에 게시하고 검증하는 방법이다. lines:25-25

- 한 달간 매일 정책을 준수했음을 증명하면서 단일 증명과 대략 같은 검증 비용을 지불하는 기관 사례를 제시한다. lines:25-25

- 규제 금융기관의 거래와 정산, 소비자와 판매자의 지출 및 안전 정책, 로봇과 기기 및 AI 서비스 간 상거래를 활용 사례로 제시한다. lines:27-27

- NovaNet 문서와 기술 블로그를 안내하고 Discord에서 향후 방송 아이디어를 공유하도록 초대한다. lines:29-29

- 면책 안내: 제품 기능은 변경, 지연이나 취소될 수 있고 확약, 보증이나 투자 조언이 아니라는 면책 고지가 있다. lines:37-37

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/trustless-usdc-agents-on-arc-2025-12-06 / 한국어 정리

### 행사 174

> Arc Studio: Buenos Aires [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arc-studio-buenos-aires-dr7k9ycsae)

페이지 일정 필드(UTC)는 2025-11-19T13:00:18.349Z부터 2025-11-19T19:00:00.881Z까지이며 표시 시간대는 America/Argentina/La_Rioja이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Buenos Aires / Argentina [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- Arc 개발자, 창업자와 커뮤니티 관계자를 위한 첫 모임이다. lines:9-9

- 프로그래밍 가능한 화폐, 토큰화 자산과 세계 유동성을 연결해 자본 시장, 대출, 외환과 결제를 지원하는 Arc를 소개한다. lines:11-11

- 개발자 세션, 실시간 시연, 새 한정 Arc 상품과 개발자, 창업자, 투자자 및 Circle 관계자 사이의 대화를 안내한다. lines:13-13

- 오전 10시부터 아침 식사와 교류 후 개발자 프로그램을 진행한다. lines:19-19

- Sam Sealey가 커뮤니티 참여와 성장 방법을 설명한다. lines:21-21

- Corey Cooper, Simon Lapscher와 Sam Magnant가 Arc 비전과 공동 개발을 설명한다. lines:25-31

- Anthony Kelani, David Shamash와 Jenna Teeman이 Grants와 Ventures 팀을 통한 개발자 자금 지원을 소개한다. lines:33-39

- Corey Cooper, Trails와 Sequence의 Peter Kieltyka, Bu.Fi의 Tomas Cordero 및 Dynamic의 Ellie Farrisi가 초기 이용자의 개발 내용과 경험을 공유한다. lines:41-49

- Sterling Barnett와 Morpho 공동 창업자 Merlin Egalite가 초기 파트너의 개발자 지원을 설명한다. lines:51-55

- 오후 1시부터 4시까지 점심, 음료와 Circle 팀과 함께 작업하는 시간을 제공한다. lines:59-59

- 행사는 영어로 진행한다. lines:61-61

- 공개 테스트넷 Arc를 설명하는 교육 세션이며 Circle Mint 같은 일부 제품은 Argentina에서 이용할 수 없을 수 있다고 고지한다. lines:63-63

### 행사 175

> Encode x Arc DeFi Hackathon [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/encode-arc-hackathon)

페이지 일정 필드(UTC)는 2025-11-14T10:00:00.853Z부터 2025-11-16T18:00:28.864Z까지이며 표시 시간대는 Europe/London이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

장소 표기는 다음과 같다.

> Encode Hub / London / England / UK [원문 그대로]

공개 참가 표시 데이터: `isOnline=False`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=InPerson`로 표시되어 있다.

- 기업, 앱과 프로토콜 개발자를 위한 Encode Hub의 3일 및 두 번의 야간 개발 해커톤이며 300명 규모와 20,000달러 상금을 안내한다. lines:9-9

- 대출, 자본 시장, 외환과 결제의 통화 및 자산 간 유동성을 개발 대상으로 소개한다. lines:11-11

- USDC부터 시작하는 낮고 예측 가능한 법정화폐 기준 스테이블코인 가스를 소개한다. lines:15-15

- Malachite BFT 합의 엔진으로 확정적인 1초 미만 정산을 제공한다고 설명한다. lines:17-17

- 규정을 준수하면서 잔액과 거래를 선택적으로 숨기는 개인정보 보호 설정을 소개한다. lines:19-19

- USDC, EURC, USYC, Circle Mint, Wallets, Contracts, CCTP, Gateway와 Circle Payments Network 통합을 소개한다. lines:21-21

- EVM과 호환되어 익숙한 개발 도구와 프레임워크를 사용할 수 있다고 설명한다. lines:25-25

- 외부 신뢰 정보를 이용하는 신용 사례로 검증 가능한 자격 정보 기반 대출, 결제 이력 기반 평판 신용, 서비스가 부족한 시장의 소기업 및 소비자 신용 앱을 제시한다. lines:31-37

- 자본 시장 사례로 즉시 DvP를 지원하는 토큰화 증권, 스테이블코인 담보 증거금 관리, 토큰화 펀드와 구조화 상품 및 실시간 자료와 위험 신호를 이용하는 예측 시장을 제시한다. lines:41-49

- 외환 사례로 무기한 계약과 파생상품 거래소, 스테이블코인 전환 API, 국경 간 지급과 자금 재배분 도구를 제시한다. lines:53-59

- 에이전트 상거래 사례로 AI 에이전트가 사고파는 시장, IoT 기기 간 지급과 즉시 의도 정산을 위한 조정 시스템을 제시한다. lines:63-69

- 국경 간 지급 사례로 소비자 송금, 시장과 단기 근로자 및 급여 지급, 토큰화 청구서와 에스크로 정산을 이용하는 무역 금융을 제시한다. lines:73-79

- 면책 안내: 제품 설명이 확약, 보증이나 투자 조언이 아니라는 면책 고지가 있다. lines:87-87

- 면책 안내: USYC는 미국인이 아닌 사람에게, Circle Mint는 기관에만 제공된다는 제품 고지가 있다. lines:93-93

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://luma.com/rjsr5r3a / 한국어 정리

### 행사 176

> Day One Architect Highlight: Blockradar [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/day-one-architect-highlight-blockradar-0bvy2uwdig)

페이지 일정 필드(UTC)는 2025-11-13T22:00:48.792Z부터 2025-11-13T23:00:48.657Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Blockradar와 Arc의 스테이블코인 기반 인프라가 신흥 시장 금융 서비스에 쓰이는 방식을 논의한다. lines:7-7

- 비수탁형 Wallet-as-a-Service API로 수금, 지급과 자금 관리를 자동화하고 Gateway로 여러 체인의 고객 USDC 잔액을 통합한다. lines:9-9

- 스테이블코인 가스로 예측 가능한 거래 수수료를 제공한다. lines:13-13

- 즉시 거래 확정으로 사용자 경험을 지원한다. lines:15-15

- 프로그래밍 가능한 지급으로 자금 관리를 자동화한다. lines:17-17

- 핀테크가 시제품에서 실제 서비스로 발전해 USDC를 금융 경험에 포함하는 내용을 다룬다. lines:19-19

- Blockradar 공동 창업자 Morgan Williams와 Circle의 Corey Cooper가 대화한다. lines:21-21

- 면책 안내: 제품 설명이 확약, 보증이나 투자 조언이 아니라는 면책 고지가 있다. lines:27-27

- 발표자 소개는 단일 API로 지갑 발급, 규정 준수, 정산, 가스 요금과 여러 체인 처리 기능을 제공하고 국경 간 결제, 지급과 온체인 자금 관리를 지원한다고 설명한다. lines:69-69

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Corey Cooper / Senior Manager, Developer Relations and Ecosystem Marketing / Circle [원문 그대로]

> Morgan Williams / Co-Founder / Blockradar [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- startedAt 및 endedAt와 days의 날짜 범위가 다르다. lines:34-35,76-77.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/event-replay-day-one-architect-highlight-blockradar-2025-11-13 / 한국어 정리

### 행사 177

> Welcome to the Arc Community Hub [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/welcome-to-arc-community-hub)

페이지 일정 필드(UTC)는 2025-11-04T15:00:00.406Z부터 2025-11-04T16:00:00.406Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Arc 생태계를 함께 개발하는 Architects라는 커뮤니티 구성원을 위한 세션이다. lines:9-9

- 프로그래밍 가능한 화폐와 온체인 기술을 대출, 자본 시장, 외환과 결제의 실제 금융 활동에 연결하는 Arc를 소개한다. lines:11-11

- 커뮤니티 소속의 의미, 기술과 창작 지원, 공동의 가치 및 공개 협업을 논의한다. lines:17-17

- Developer Relations, Ecosystem Growth, Support와 Ventures 팀을 만나 참여, 의견 전달과 초기 기여 방법을 논의한다. lines:23-23

- 지역 개발자가 협업하고 행사를 열 수 있는 세계 각지의 모임 계획을 공유한다. lines:27-27

- Sam Sealey가 커뮤니티가 존재하는 이유와 함께 개발할 내용을 설명한다. lines:118-118

- Bobbilee Hartman이 개발자가 발견하고 배우고 만드는 활동을 돕는 Circle 개발자 프로그램을 소개한다. lines:151-151

- Tim Baker가 Discord에서 기술 질문에 빠르게 답하고 아이디어를 수집하는 방법을 설명한다. lines:184-184

- Conrad Voorsanger가 Ventures와 Corporate Development의 Arc 개발자 지원을 소개한다. lines:217-217

- Sam Sealey와 Jenna Teeman이 세계 모임 계획과 Buenos Aires Devconnect 2025의 Arc Day 참여 방법을 설명한다. lines:250-250

- Arc Hub에 가입하고 의견을 공유하도록 안내한다. lines:283-283

- 면책 안내: 제품 설명이 확약, 보증이나 투자 조언이 아니라는 면책 고지가 있다. lines:39-39

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Sam Sealey / Director, Community  / Circle [원문 그대로]

> Jenna Teeman / Principle Program Manager, Developer Marketing  / Circle [원문 그대로]

> Conrad Voorsanger / Corporate Development & Ventures, Ventures Ecosyst / Circle [원문 그대로]

> Tim Baker / Community Manager / Circle [원문 그대로]

> Bobbilee Hartman / Principle PM, Developer Program / Circle [원문 그대로]

공개 세션은 다음과 같다. 제목과 설명은 원문 표기를 유지하며 시각은 각 세션의 UTC 데이터다.

> Welcome and Purpose [원문 그대로]

세션 시각: `2025-10-29T14:00:00.000Z` - `2025-10-29T14:05:00.000Z`.

> Sam Sealey, Director, Community and Ecosystem Growth — Why the Arc Community exists and what we are building together [원문 그대로]

> 발표자: Sam Sealey / Director, Community  / Circle [원문 그대로]

> Meet our new Developer Community Programs Director [원문 그대로]

세션 시각: `2025-10-29T14:05:00.000Z` - `2025-10-29T14:10:00.000Z`.

> Bobbilee joins Circle as Principal Program Manager on the Developer Relations team, where she’ll help lead Circle’s own developer programs to build and activate the Arc community, helping builders discover, learn, and create.
> Bobbilee brings over a decade of experience at the intersection of developer ecosystems, open source, and AI x crypto innovation. [원문 그대로]

> 발표자: Bobbilee Hartman / Principle PM, Developer Program / Circle [원문 그대로]

> Community Discord Support and Feedback Loops [원문 그대로]

세션 시각: `2025-10-29T14:15:00.000Z` - `2025-10-29T14:20:00.000Z`.

> Tim Baker, Discord Community Support Lead — How we’ll answer technical questions faster and capture your ideas [원문 그대로]

> 발표자: Tim Baker / Community Manager / Circle [원문 그대로]

> Circle Ventures and Builder Funding [원문 그대로]

세션 시각: `2025-10-29T14:25:00.000Z` - `2025-10-29T14:35:00.000Z`.

> Conrad Voorsanger, Senior Director, Ventures Ecosystem — How Ventures and Corporate Development are empowering Arc builders [원문 그대로]

> 발표자: Conrad Voorsanger / Corporate Development & Ventures, Ventures Ecosyst / Circle [원문 그대로]

> Community Meetups and Devconnect Preview  [원문 그대로]

세션 시각: `2025-10-29T14:40:00.000Z` - `2025-10-29T14:50:00.000Z`.

> Sam Sealey and Jenna Teeman — Global meetup rollout and how to join Arc Day at Devconnect 2025 in Buenos Aires [원문 그대로]

> 발표자: Jenna Teeman / Principle Program Manager, Developer Marketing  / Circle [원문 그대로]

> Closing and Next Steps [원문 그대로]

세션 시각: `2025-10-29T14:55:00.000Z` - `2025-10-29T15:00:00.000Z`.

> Sam Sealey — Join the Arc Hub, share feedback, and be part of building the economic OS for the internet [원문 그대로]

> 발표자: Sam Sealey / Director, Community  / Circle [원문 그대로]

본문이나 공개 데이터에서 확인할 차이는 다음과 같다.

- 행사 startedAt는 11월 4일인데 agendas와 days는 10월 29일이다. lines:46,119,318.
- Bobbilee의 agenda 제목은 Director이며 설명은 Principal Program Manager이다. lines:150-151.

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/event-replay-welcome-to-arc / 한국어 정리

### 행사 178

> ArcTalk: Finality You Can Count On [원문 그대로]

공고 본문과 전체 데이터 / 공개 일정 데이터 / [온라인 원문](https://community.arc.io/public/events/arctalk-finality-you-can-count-on-s2y0fuhuyg)

페이지 일정 필드(UTC)는 2025-10-30T16:00:00.939Z부터 2025-10-30T17:00:44.246Z까지이며 표시 시간대는 America/New_York이다. 신청 마감과 세션별 시간은 아래 본문 설명과 공개 세션을 따른다.

공개 참가 표시 데이터: `isOnline=True`, `isInvitationOnly=False`, `isAllTicketOptionsInvitationOnly=False`. 이 표시가 본문의 초대나 주최자 등록 안내와 다르면 함께 확인해야 한다.

> Free Ticket [원문 그대로]

티켓의 공개 데이터는 `price=0`, `isInvitationOnly=False`, `isFull=False`, `isWaitlistAvailable=False`, `attendanceMode=Virtual`로 표시되어 있다.

- Corey Cooper와 Adi Seredinschi가 금융 앱에서 1초 미만의 거래 확정(deterministic finality)을 제공하는 Arc 구조를 설명한다. lines:11-11

- Rust 기반 Tendermint 방식의 Malachite 합의 엔진을 설명한다. lines:15-15

- 성능과 유연성을 위해 합의와 실행을 분리하는 설계를 다룬다. lines:17-17

- 큰 금액 거래에서 확정적인 거래 확정과 확률적인 거래 확정을 비교한다. lines:19-19

- Arc 설계가 USDC와 EURC 활용을 지원하는 방법을 설명한다. lines:21-21

- 처리량 확대와 해로운 MEV 완화 계획을 다룬다. lines:23-23

공개 발표자 표기는 다음과 같다. 이 명단은 개인 소개 전체를 행사 내용으로 바꾸지 않고 별도로 보존한다.

> Corey Cooper / Senior Manager, Developer Relations and Ecosystem Marketing / Circle [원문 그대로]

> Adi Seredinschi / Principal Product Manager / Circle [원문 그대로]

연결 자료의 내용과 열람 한계는 연결자료 정리에 있으며 이 공고에서 연결되는 자료는 다음과 같다.

- https://community.arc.network/home/videos/finality-you-can-count-on-2025-11-03 / 한국어 정리

## 확인 범위와 남은 내용

연결된 공개 등록과 주최자 안내는 연결자료 정리에 있다. 요청했지만 열리지 않은 주소, 동적 신청 양식의 본문이 없는 응답, 일정과 초대 표시의 차이, 녹화 영상 자체를 시청하지 않은 범위는 미확인 내용에 남겼다. 원문과 한국어 설명을 대조한 최종 리뷰는 기술 성능이나 실제 참가 승인에 대한 외부 사실 판정이 아니다.
