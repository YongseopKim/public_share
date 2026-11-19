---
date: 2026-08-07
type: analysis
tags: [AI, business, blockchain, career]
status: living
source: official event pages checked 2026-08-07; unresolved items retained as unknown
notes: .agent-payment-hackathon-scout.md
---

# 에이전트 결제에 맞는 해커톤 조사

> 이 문서는 어떤 행사가 에이전트 결제 제품에 맞는지 조사한 근거를 정리한다. 이 문서에
> 행사를 추가했다고 해서 참가를 추천하거나 확정한 것은 아니다.
>
> 관련 문서는 다음과 같이 역할을 나눈다.
>
> - 이 문서는 행사의 규칙과 제품 적합성을 조사한다.
> - 행사별 개발 일정은 참가 상태와 실제 작업 기간을
>   관리한다.
> - 제품 로드맵은 행사와 무관한 제품 개발 단계를 관리한다.

2026-10-10에 추가한 블록체인 AI 에이전트 해커톤 읽기 안내는 전용 행사와 범용 행사 안의 에이전트 트랙을 함께 정리한다. 전체 통합본에는 원문 세부와 미확인 항목을 보존했다. 이 자료는 후보 조사 근거이며, 참가 상태와 확정 일정은 제작 일정에서 계속 관리한다.

2026-10-10 후속 공식 공고 대조와 독립 검토에서 현재 일정, 상금의 성격과 제외 조건을 갱신했다. X-Agent는 온체인 보안과 감사 프로젝트를 제외하므로 이 제품의 참가 검토에서 해당 조건을 먼저 읽어야 한다.

## 0. 선발 기준 (2026-08-07, 사용자)

> 해커톤 참여가 동기부여가 된다. 커리어에도, 프로젝트 발전에도 좋다. 상금은 우선순위가
> 아니다. 결제 엔진에 직접 붙지 않더라도 AI Agent 부분을 강화한다면 후보로 찾는다.

따라서 행사 가치는 상금 순서가 아니라 아래 네 축으로 본다.

1. **외부 마감의 효과:** 행사 일정이 개발, 데모, 제출을 끝내는 데 도움이 되는가.
2. **행사 뒤에도 남는 결과물:** 공통 제품, 에이전트 기능, 측정 자료 가운데 하나 이상이
   남는가.
3. **경력 증거:** 작동하는 결과물과 외부 피드백이 창업과 이직 준비 양쪽에서
   설명 가능한가.
4. **참가자 적합성과 참가 비용:** 만날 사람의 적합성이 이동, 팀 구성, 다른 작업을
   중단하는 비용보다 큰가.

두 번째와 세 번째 기준은 위에 기록한 사용자 발언을 풀어 쓴 것이다. 첫 번째와 네 번째
기준은 2026-08-07 검토에서 에이전트가 추가했다.

상금은 우선 평가축에서 빼고, 다른 조건이 비슷할 때만 부차적으로 참고한다.

### Four Pillars 해커톤 판독이 보탠 관찰 기준

> The ability to produce a working demo in a short period no longer shows whether a
> team can keep building or contribute over time.

Four Pillars의 해커톤 분석은 Colosseum과
Base Batches를 근거로 해커톤이 일회성 상금 행사에서 창업팀을 찾고 투자하는 과정으로
바뀐다고 주장한다. 이 주장은 위 사용자 기준을 바꾸지 않는다. 오히려 두 번째 기준인
행사 뒤에도 남는 결과물과 세 번째 기준인 경력 증거를 다음과 같이 더 구체적으로
관찰하게 한다.

1. 제출물이 행사 뒤에도 개발되고 사용되는가.
2. 주최자가 시연 완성도 외에 문제 정의, 초기 사용, 팀의 실행 속도와 후속 개발을
   확인하는가.
3. 액셀러레이터, 투자, 고객 대화처럼 행사 뒤의 검토 과정이 실제로 있는가.

이는 행사 후보를 미리 제외하는 조건이 아니다. 각 행사의 공식 규칙을 확인한 뒤 제품과
경력에 무엇이 남는지를 평가할 때 쓰는 관찰 항목이다. Four Pillars가 집계한 88개 행사와
25,010개 제출물의 모집단 구성 및 연도별 분류는 재현하지 않았으므로, 산업 전체가 이미
이 방향으로 바뀌었다는 결론은 보류한다.

**행사를 배치하는 원칙은 에이전트가 제안했으며 아직 사용자가 채택하지 않았다.** 여러
행사를 동시에 준비하지 않고, 한 번에 한 행사에 참가하면서 서로 다른 약점을 하나씩
개선한다. 이 원칙은 참가 횟수나 특정 행사 참가를 결정하지 않는다.

행사의 상태, 판정 시점, 마지막 확인일은
행사별 개발 일정의 행사 목록에서만 관리한다. 같은 값을
여러 문서에 적으면 서로 달라질 수 있으므로, 2026-08-07에 이 문서의 표에서 상태와 판정
열을 제거했다. 이 문서에는 행사의 근거와 제품 적합성만 남긴다. 관찰, 후보, 확정, 완료의
정의도 행사별 개발 일정에서 확인한다.

## 1. 결제 제품과 직접 맞는 행사

### [Agents Onchain - KeeperHub](https://dorahacks.io/hackathon/agents-onchain)
- 일정과 형식: ~8/13 19:00 KST 제출, 온라인 2.5주(7/27 개막)
- 남길 수 있는 것: x402/MPP와 Stripe(Tempo) 이중 레일 위 실거래, 행위별 감사 로그(trigger, simulation, tx, gas,
  outcome, timestamp) - 엔진 구조와 겹침 최대
- 동기와 커리어 가치: 스택 일치가 가장 높은 행사. 상금은 소액(\$5,000+\$1,000, 스테이블코인 지급)
- 규칙, 마감, 충돌: KeeperHub를 온체인 실행 계층으로 강제 - 레일 중립과 충돌. 실거래 링크 제출 필수. 기존 코드 규칙 미게재. DoraHacks가
  정적 접근을 차단해 실브라우저로 확인(2026-08-07)

### [Arc Programmable Money](https://community.arc.io/public/events/hackathon-programmable-money-74llz8htis)
- 일정과 형식: 7/13~8/22, 온라인, 진행 중. DeFi/Agentic 두 트랙
- 남길 수 있는 것: Circle 도구(Wallets, Contracts, CCTP, Gateway, Paymaster, Nanopayments)를 붙인 새 레일,
  작동하는 프런트/백엔드, 3분 데모
- 동기와 커리어 가치: 짧은 다음 마감이고 Circle, Encode 피드백 경로가 있다. Agentic 트랙이 있고 상위 팀은 8주 액셀러레이터
- 규칙, 마감, 충돌: 늦은 등록 가능 여부와 기존 코드 허용 규칙이 공식 페이지에 미게재(2026-08-07 재검증 - 남은 수단은 주최 문의). GCP 회고
  직후 바로 새 제출로 가는 비용

### [BUIDL CTC 2026 Fall](https://dorahacks.io/hackathon/buidl-ctc-2026-fall)
- 일정과 형식: 제출 8/13~9/6, 온라인 + 서울 시상식(9/28 CTC Ignition)
- 남길 수 있는 것: AI가 온체인 거래를 트리거하는 트랙, 상위 3팀 투자 fast-track
- 동기와 커리어 가치: 서울 연계와 투자 경로. 솔로 참가 가능
- 규칙, 마감, 충돌: 행사 중 신작 요건("original work created during the hackathon")과 Attestcoin 필수 통합이 연속
  개발, 레일 중립과 정면 충돌. 마감 표기 불일치(본문 9/6 23:59 ET vs 위젯 UTC). 실브라우저 확인(2026-08-07)

### [Monad Metropolis](https://www.monad.xyz/developers/hackathons/metropolis)
- 일정과 형식: 9/1~10/13 온라인 6주(등록은 기간 중 상시, `hackathon.monad.xyz`에 GitHub나 Google이나 Discord로
  로그인), 심사 10/14~27, 발표 11/3. 하루 라운지 7개 도시에 서울은 없다(원문의
  Activations 절). 원문과 대조는 2026-09-06, 공식 페이지 캡처(`cb/works/web/2026-09-06-monad-metropolis-hackathon/README.md`)
- 남길 수 있는 것: Monad(EVM) 어댑터, 트랙 4 예시의 ERC-8004 에이전트 신원과 평판 연동, 스폰서 심사의 피드백.
  트랙 2(Consumer Products & Payments)의 예시 셋 `A payments app that never mentions a blockchain`,
  `Subscriptions that charge by the second`, `Shared wallets and group spending that settle up without an
  intermediary`는 엔진의 정책과 원장이 그대로 걸린다
- 동기와 커리어 가치: 심사위원 18명 중 Monad Foundation 셋(Keone Hon, Eunice Giarta, Tina Qi), 투자사 여덟
  (Galaxy, Electric Capital, Castle Island, IOSG, CoinFund, Paradigm, Dragonfly, Pantera), MetaMask DevRel 디렉터.
  멘토에 Agora의 CEO와 CTO, Monad Foundation AI 팀 셋. 상위 팀은 레지던시, 전원 DeltaV(800+ 스타트업)로
  이어진다. 커뮤니티 서포터의 국내 학회 일곱 중 CURG는 사용자가 2026-08-26에 최종 합격한 14기의 학회다
  (W35 08/26). 상금은 선발 기준 0절(선발 기준)대로 부차적이다 -
  트랙 상금은 팀당 \$10,000
- 규칙, 마감, 충돌: 기존 팀과 문맥은 허용, **심사 대상은 6주 안에 만든 것**(FAQ `what you show on 13 Oct
  should have been built during the six weeks`) - 연속 엔진 개발과 맞되 행사 시작 시점의 baseline tag가 필요.
  오픈소스는 권장이지 필수 아님. 국가 제한은 신청 플랫폼의 공식 규칙에만 있고 로그인 뒤라 확인하지 못했다
  (2026-09-06). ETHOnline(9/4~16), Tokyo(9/25~27), Colosseum(9/28~11/2)과 전 구간 겹침.
  08-07 "추가 참가 결정은 모두 보류" 유효

스폰서 바운티 21개(원문의 prize card, 스폰서명은 로고 alt). 크레딧 넷을 뺀 현금 바운티의 합은 \$76,500이고
크레딧 \$11,000을 더하면 \$87,500이다(이 세션이 카드 21개를 읽어 더한 값). 4자 캡처의 Claude가 `약 $87,500`이라
적은 것과 같다.

| 스폰서(로고 alt) | 금액 | 바운티 |
|---|---:|---|
| Envio | \$1,000 | Best Use of Envio |
| Cleanverse | \$2,000 | Best Integration of CVI/CVA |
| Kuru | \$5,000 | Build the Next Consumer Trading App on Kuru |
| Kuru | \$5,000 | Bring New Assets and Markets to Kuru |
| Dynamic | \$5,000 | Best Use of Dynamic |
| Alchemy | \$1,000 크레딧 | Best Projects using Alchemy |
| Chainlink | \$3,000 | Best workflow with CRE |
| Perpl | \$5,000 | Best use of Perpl's API |
| Perpl | \$3,000 | Best Analytics / Risk Tool |
| Privy | \$5,000 | Privy! |
| Nansen AI | \$5,000 | Best use of Nansen |
| Agora | \$10,000 | Best Mobile Trading App on Monad |
| Agora | \$10,000 | Best Cross-Border Payments App on Monad |
| Kepler Plan by Tencent | \$2,000 크레딧 | Build with Hunyuan |
| Kimi | \$3,000 크레딧 | Best Builds Powered by KIMI |
| Alibaba Cloud | \$5,000 크레딧 | Best Builds with Qwen 3.8 Max |
| Monad Foundation | \$2,500 | Best Mera-Powered UX on Monad |
| Monad Foundation | \$2,500 | Mera: One Passkey, Many Keys |
| Metamask | \$2,500 | Best Agent Wallet Plugin |
| Monad Foundation | \$5,000 | Best Community Team Project |
| Aurora Intents | \$5,000 | Bring Any-Chain Liquidity to Monad |

### [2026 금융 AI Challenge](https://www.fsec.or.kr/bbs/detail?bbsNo=11997&menuNo=66)
- 일정과 형식: 9/7 10:00 제출, 국내 온라인 예선->본선 대상 발표 9/22->10/13 오프라인 발표->수상 10/23. 개인 또는 4인 이내 팀
- 남길 수 있는 것: 금융 AI 웹서비스 URL, 기획서, 기능명세서, 국내 금융 문제 언어
- 동기와 커리어 가치: 금융보안원, 금융위원회, 은행, 증권, 보험 청중에 남는 국내 커리어 증거
- 규칙, 마감, 충돌: 공고 예시 7건 중 3~4건이 기업/기관용(이상거래, 보험사기 탐지, 투자 평가, AI 보안 대응)이라 B2B 자체는 배제되지
  않는다(2026-08-07 원문 확인 - 종전 "금융소비자 중심" 서술 정정). 다만 지출, 조달 거버넌스류 예시는 없다. 기존 코드 규칙은 공고 본문에
  없음(첨부 미확인). ETHOnline 시작 9/4와 겹침

### [Colosseum Eternal - Eternal Challenge 2026 H2](https://colosseum.com/eternal)
- 일정과 형식: 셀프페이스 4주 스프린트, 현재 윈도 마감 9/7 09:00 KST(페이지 데이터 countdownTarget 원문 확인)
- 남길 수 있는 것: 기존 제품을 그대로 넣고 4주 출하 속도로 심사받는 상시 온라인 트랙 - \$250K 프리시드 경쟁. 배경은
  GCP x Solana 행사 결정 문서의 후속 행사 검토에 정리되어 있다.
- 동기와 커리어 가치: 신작 제약 없이("Submit your crypto product in-between hackathons") 지금 엔진으로 참가 가능한 가장
  빠른 무대
- 규칙, 마감, 충돌:
  - **2026-08-13 확인으로 이 칸의 전제가 뒤집혔다.** 윈도가 가두는 것은 시작 시점 하나이고, 4주 완주는 윈도 밖으로 넘어가도 된다 - 공식
    FAQ의 `If you started a sprint during an active Eternal window, you can continue through
    your personal deadline even if Eternal is later paused.` 따라서 "여유 3일"이라는 계산 자체가 성립하지 않는다.
    9/6까지 아무 날이나 시작하면 되고 개인 마감은 거기서 4주 뒤다.
  - 대신 4주 동안 주간 1분 영상 업데이트가 필요하고 마지막 주에 해커톤 수준 제출물(3분 피치, 3분 데모, 저장소)을 낸다.
  - VC 투자를 받은 팀은 액셀러레이터와 수상 자격이 없다.
  - 원문은 2026-08-13 웹 자료 목록에 보관되어 있다.

### [Arbitrum Open House Singapore 온라인 빌드톤](https://www.hackquest.io/hackathons/Arbitrum-Open-House-Singapore-Online-Buildathon)
- 일정과 형식: 제출 9/13~10/4, 등록 ~10/3 02:01 KST, 온라인
- 남길 수 있는 것: "Bring an existing project or start from scratch" 명시(원문 확인) - 기존 엔진을 반입 허용 규칙
  아래 그대로 내는 첫 기회 + Arbitrum 어댑터
- 동기와 커리어 가치: 총상금 \$115K(USDC), 상위 3팀 싱가포르 Founder House 초청. 아시아, 온라인
- 규칙, 마감, 충돌: 전용 결제, 에이전트 트랙 미확인(주제 개방형). 플랫폼 공통 정책의 "재활용 금지" 문구와 행사 문구가 충돌 소지. ETHOnline
  마무리, 통합 구간, Colosseum 초반과 전면 겹침

### [GWDC Hackathon Korea 2026](https://www.gwdc.net/hackathon.html)
- 일정과 형식: 9/28~30 서울 aT센터 현장 48시간, 신청 마감 9/27, 1인 등록 폼 있음(팀 매칭 허브 연결)
- 남길 수 있는 것: 공식 Luma 아젠다 1번이 문자 그대로 "AI Agents & Autonomous Payments - AI 에이전트가 스테이블코인을 활용해
  자율 미세 결제" - 주제 정면 일치의 국내 현장 무대
- 동기와 커리어 가치: 서울 개최라 이동 비용 최소, 국내 web3 빌더 노출
- 규칙, 마감, 충돌: 상금 표기 불일치(공식 \$10,000 vs 언론 \$100,000+), 체인 목록, Ecosystem Challenge 과제, 심사 기준
  공백(주최는 홍콩 Web3Labs). Colosseum 개막 사흘(9/28~30)과 정면 충돌

### [제9회 핀테크 아이디어 공모전](https://www.fsc.go.kr/po010101/87437)
- 일정과 형식: 접수 8/3~10/8 16:00(핀테크포털), 본선 발표 10/30, 발표심사 11/4, 11/18, 시상 11/26 양재 aT센터
- 남길 수 있는 것: 해커톤이 아니라 아이디어/BM 공모(코드 제출 요건 없음) - 서류, 피칭만으로 국내 금융권에 제품 서사를 검증. 개인 참가 명시 가능(5인
  이하)
- 동기와 커리어 가치: 협력기관이 금융결제원, 코스콤, 금융보안원, 신용정보원이라
  제품 로드맵의 E2(그 수단이 기존 결제망에 유통될 것)를 검토할 국내 결제 기관이 심사에 참여한다.
  대상, 우수상에 금융결제원 사업제휴 우선권, 총상금 6천만원(공고 HWP 원문 확인)
- 규칙, 마감, 충돌: 기존 아이디어 재출품 명시 허용(기 수상작만 제외). 금융규제 샌드박스에 기공개된 서비스와 동일하면 수상 제외

### [TUM Blockchain & AI](https://tum.devfolio.co/)
- 일정과 형식: 10/30~31, 뮌헨 현장 30시간
- 남길 수 있는 것: `Agentic Payments`라는 직접 주제 아래 결제, 신뢰 기능과 현장 데모
- 동기와 커리어 가치: 주제 적합도가 높고 유럽 Blockchain x AI 빌더와 접점
- 규칙, 마감, 충돌: 등록 마감 10/29 12:00 UTC(행사 레코드, 2026-08-07 검증). Colosseum 마지막 포장 주간과 정면 충돌. 현재
  공개된 상금 트랙은 BSV(€4,000)뿐이고 다른 스폰서는 미공개. 기존 코드 규칙 미게재(규칙란은 Code of Conduct뿐)

### [ETHGlobal Mumbai](https://ethglobal.com/events)
- 일정과 형식: 11/6~8, 뭄바이 현장
- 남길 수 있는 것: Ethereum/Base 계열 신규 기능과 현장 피드백
- 동기와 커리어 가치: Ethereum 생태계 커리어, 네트워크 신호
- 규칙, 마감, 충돌: Colosseum 종료 4일 뒤이고 Since AI와 같은 날짜. Continuity, 파트너 트랙은 행사별 재확인 필요

### [Agent Pay - MERGE Madrid](https://www.mmerge.io/hackathon-2026)
- 일정과 형식: 11/27~29, 마드리드 현장 48시간
- 남길 수 있는 것: Agent Commerce 또는 Agent Micropayments 위에서 통합된 제품, 데모
- 동기와 커리어 가치: 개발자뿐 아니라 핀테크, 기업, 기관 자본이 함께 있는 청중, 상위 팀의 멘토링, pilot 대화, 2027-03 데모데이 경로
- 규칙, 마감, 충돌: 참가 마감, 기존 코드, 여행 지원 셋 다 공식 페이지 미게재(2026-08-07 검증). 데모데이는 MERGE Buenos Aires
  2027-03

### [Arbitrum Open House Dubai 온라인 빌드톤](https://www.hackquest.io/hackathons/Arbitrum-Open-House-Dubai-Online-Buildathon)
- 일정과 형식: 등록 10/31~, 제출 11/17~12/7 KST(페이지 내장 데이터 원문 확인)
- 남길 수 있는 것: 싱가포르 회차와 같은 "Bring an existing product" 반입 허용 문구의 11~12월 온라인 창구
- 동기와 커리어 가치: Madrid 전후의 온라인 대안
- 규칙, 마감, 충돌: 심사 기준, 상금 구성, 트랙 전부 "Coming soon"

### [BNB Hack: Online Edition](https://www.bnbchain.org/en/hackathons/bnb-ai-hack)
- 일정과 형식: 상시 온라인, 제출 마감 없음
- 남길 수 있는 것: 사용자 판단 대기
- 동기와 커리어 가치: 사용자 판단 대기
- 규칙, 마감, 충돌: 아래 상세 평가 참조

### [The Smart Money Era: Build the Era](https://www.bnbchain.org/en/hackathons)
- 일정과 형식: 8/5~9/9, 온라인
- 남길 수 있는 것: 권한 관리 화면, BSC 결제, 비교 측정 보고서
- 동기와 커리어 가치: 외부 마감과 처음 보여줄 수 있는 권한 관리 화면
- 규칙, 마감, 충돌: 아래 상세 평가 참조


### BNB Hack: Online Edition 상세 평가

- **일정:** 페이지 데이터에는 2025-02-12부터 2026-12-31까지 진행 중이라고 표시되어
  있다. `submit_project_end_time`은 비어 있어 제출 마감이 없다.
- **제품 결과물과 경력 가치는 아직 작성하지 않았다.** 사용자가 참가 검토를 보류했기
  때문이다.
- **서로 충돌하는 제출 요건:**
  - `the development start date is not restricted`는 기존 제품의 연속 개발을 허용한다.
  - `Projects must not participate in any past hackathons or previously
    funded ones`는
    과거 해커톤에 참가했거나 자금을 받은 제품을 금지한다.
  - agent-spend-gate는 GCP x Solana 행사에 제출한 적이 있어 두 번째 요건에 해당할 수
    있다.
  - 다른 주최자의 행사도 과거 해커톤에 포함하는지, `funded`가 외부 투자까지 뜻하는지는
    공개 문구만으로 확인할 수 없다. 주최자에게 문의해야 한다.
- **기술 및 공개 요건:** opBNB 또는 BSC에 배포해야 하고, 코드를 공개해야 한다.
- **상금:** 1위는 10,000 USDT, 5만 달러 규모의 초기 지원, MVB 인터뷰 기회를 받는다.
- **일정 충돌:** 제출 마감이 없으므로 현재 일정과 직접 충돌하지 않는다.
- **마지막 확인:** 2026-08-13이다.

### The Smart Money Era: Build the Era 상세 평가

- **일정:**
  - 시작 시각은 `2026-08-05 12:00`이다.
  - 제출 마감은 `2026-09-09 12:00`이고 시간대 필드는 `UTC +0`이다.
  - 심사는 9/23까지 진행하고 결과는 11/5에 발표한다.
- **행사 뒤에도 남길 결과물:**
  - Altana 트랙의 호출 허용 목록, 지출 상한, 만료, 취소 요구를 권한 관리 화면에
    구현한다.
  - BSC 세션 키로 실제 거래를 실행해 Solana와 Base에 이어 세 번째 결제망을 검증한다.
  - TermiX의 `Agent Advantage Report` 형식에 따라 같은 과제 세 건을 에이전트 사용 전후로
    실행하고 시간, 비용, 품질을 비교한다.
  - DeFi 카테고리 자료 화면과 BNB Agent Studio CLI 연결은 행사 전용 작업으로 분류한다.
- **경력에 남는 결과:** 권한과 취소 기능을 사람이 직접 볼 수 있는 화면을 처음 만든다.
  이는 GCP x Solana 행사 회고에서 확인한 데모와 발표 자료 부족을 보완한다.
  - 이 평가는 에이전트가 정리한 내용이며 사용자 발언이 아니다.
- **참가 자격과 제출 규칙:**
  - 개인과 팀 모두 참가할 수 있다.
  - 한 팀은 제출물 하나만 낼 수 있다.
  - 심사 기간에는 제출물을 공개 상태로 유지해야 한다.
  - 마켓플레이스에 등록하는 에이전트는 BSC에서 실제로 작동해야 한다.
  - 기존 코드를 사용할 수 있는지는 공개된 규칙에서 확인하지 못했다.
- **상금:** 메인 트랙 1위는 3만 달러이다. 파트너 상금은 TermiX 1만 달러,
  PancakeSwap 1,000 CAKE, Altana 50,000 XP이다.
- **행사의 범위:** 일반적인 분산 애플리케이션을 만드는 행사가 아니라 BNB Agent Studio
  마켓플레이스를 만드는 행사이다.
- **일정 충돌:** ETHOnline의 9/4부터 9/16까지 일정과 겹친다.
- **마지막 확인:** 2026-08-13이다.

두 행사의 평가 진행 상태는 다음과 같다.

- **공통으로 확인한 항목:** 공식 URL, 일정, 형식, 참가 자격, 기존 제품과 사전 코드에
  관한 규칙, 다른 행사와의 일정 충돌을 공식 페이지에서 확인했다.
- **Build the Era:** 행사 뒤에도 남길 결과물과 참가 동기를 정했다. 따라서
  행사별 개발 일정의 행사 목록에 후보로 추가했다.
- **BNB Hack: Online Edition:** 사용자가 검토를 보류했으므로 행사 뒤에도 남길 결과물과
  참가 동기를 정하지 않았다. 행사 목록에도 아직 추가하지 않았다.

### Build the Era의 상세 페이지에서 추가로 확인한 내용

- **확인 날짜:** 2026-08-13이다.

**행사 목록 페이지의 카드는 메인 트랙만 말한다.** 3-2절(행사 목록을 받은 단계)의 배치가 목록 페이지만 받고 상세
페이지를 받지 않아, 이 행은 처음에 `과제가 좁다 - BNB Agent Studio 마켓플레이스를 만드는
것이다` 한 줄로만 적혀 있었다. 상세 페이지에는 **파트너 트랙 넷이 더 있고 그중 하나가 이
프로젝트의 주제와 거의 같다.** 원본은
빌드 캘린더 확인.

**그리고 제출물은 하나다.** `One entry per team.` 파트너 상금은 별도 제출이 아니라 **그
하나의 제출물을 각자 심사**한다 - Altana는 `your submission must show live onchain
transactions in the Altana explorer`, TermiX는 `The submission is the
marketplace
itself`. 대조군이 분명하다: 같은 주최자의 상시 해커톤은 `Each sponsored challenge has its
own timeline, including different submission periods ... with their
submission form.`
이라고 **명시**하는데, Build the Era 페이지에는 그런 문장이 없다.

세 트랙은 서로 다른 제품을 요구하지 않는다. 하나의 제품에서 서로 다른 부분을 평가한다.

| 층 | 트랙 | 그 트랙이 보는 것 |
|---|---|---|
| 증거 | TermiX | 이 에이전트를 사는 것이 직접 하는 것보다 나은가 - 측정된 보고서로 |
| 발견 | 메인 | 찾고, 이해하고, 고용한다 - 네 카테고리 균등 |
| 권한 | Altana | 무엇을 호출할 수 있고, 얼마까지, 언제까지 - 온체인 등록과 취소 |

세 트랙은 제품을 이루는 계층 가운데 발견과 평가, 권한과 정책,
검증에 각각 대응한다. 따라서 하나의 사용자 화면에서 세 요구 사항을 함께 구현할 수 있다.
사용자는 2026-08-13에 메인 트랙에도 도전하기로 결정했다.

**남은 위험 넷** (전부 원문 근거가 있다):

1. **배점은 합쳐지지 않는다.** 제출물이 하나라는 것과 배점이 하나라는 것은 다르다. 메인의
   `Agent Diversity`는 네 DeFi 카테고리 균등을 요구하고
   (`Single-category submissions score poorly. All four, equally deep,
is the bar.`),
   Altana 최적화는 세션과 취소와 온체인 등록에 시간을 쓴다.
2. **TermiX 보고서가 27일 중 가장 무겁다.** `At least 3 real tasks run both ways`,
   최소 1건은 거래나 주식이나 보안. 화면을 만드는 일이 아니라 **거래 에이전트를 실제로
   운용해 기록을 만드는 일**이고 FE와 병렬로 굴려야 한다.
3. **심사 2단계가 비공개다.** 타임라인에 `Phase 2: [REDACTED]`라고 적혀 있다.
4. **1위 상금에 운영 의무가 붙을 수 있다.** `official adoption as the BNB Agent Studio
   marketplace, the canonical front door for every agent on BSC` 그리고
   `This isn't a demo day. Whatever you ship here is what real users
interact with next.`
   조건이 문면에 없어 주최자 확인 사항이다.

### BNB 상시 해커톤에 기존 제품을 그대로 제출할 수 없는 이유

- **확인 날짜:** 2026-08-13이다.

사용자는 "그대로 내도 되는지 모르겠다"[원문 그대로]고 말하며 참가 검토를 보류했다.
제출 요건을 다시 확인한 결과, 기존 해커톤 참가 이력 외에도 세 가지 조건을 더 확인해야
한다.

| | 걸리는 것 | 성격 |
|---|---|---|
| 1 | `Projects must not participate in any past hackathons or previously funded ones` - agent-spend-gate는 GCP x Solana 참가분 | **주최자 확인**, 범위가 문면에 없다 |
| 2 | `Work must be deployed on or connected to opBNB/BSC mainnet or testnet in some way` + `Ensure the contract address has at least 2 successful transactions within the hackathon timeframe` | 작업. Build the Era의 BSC 요구와 **같은 어댑터를 쓴다** |
| 3 | `open source, and free for others to use` | **2026-08-13 사용자 결정으로 해소** - 엔진은 원래 public 방향이었다(business-hub의 10절(엔진의 공개 방향)) |
| 4 | `Provide full open-source code with a reasonable commit history and mark your weekly milestones` | 이 저장소에서 실제로 측정한 값과 어긋난다 - 마감에 붙은 8일간 159커밋, 마감이 사라진 뒤 7일간 0커밋. 감점 항목 `Lack of Novelty Proof: Insufficient evidence to prove the project's novelty or contribution history`와 직접 연결된다 |

ETHOnline Continuity, BNB 상시 해커톤, Build the Era는 모두 코드 공개를 요구하거나
공개를 전제로 한다. 이전에는 제품을 공개할지에 관한 결정을 한 곳에 기록하지 않아 행사마다
다시 판단해야 했다. 현재 결정은 사업 판단 기록의 공개 범위에 정리되어
있다.

두 행사에서 확인한 출처와 인용은 BNB Chain 조사 문서에 정리되어 있다.
원본은 2026-08-13 웹 자료 목록에 보관되어 있다.

### 현재 해석 (세션 제안, 미채택)

- **주제 적합도가 가장 높은 후속 무대는 Agent Pay Madrid다.** 행사 질문 자체가 "에이전트는
  무엇에 어떻게 지불하는가"이고, Agent Commerce와 Micropayments를 별도 트랙으로 둔다.
- **Arc는 지금 당장 확인해야 하지만 곧바로 참가해야 한다는 뜻은 아니다.** 공식 페이지가
  기능 MVP와 3분 데모를 요구하므로 포장 결손을 교정하는 무대가 될 수 있는 반면, 마감까지
  짧고 사전 작업 규칙이 비어 있다.
- **금융 AI Challenge는 국내 커리어 접점이 강하지만 제품을 소비자 서비스로 비틀 근거는
  없다.** 현재 엔진이 공고의 넓은 금융 현안 범위 안에 드는지 먼저 확인한다.

## 2. AI Agent 강화 - 결제는 아니지만 엔진의 약점을 고칠 수 있는 행사

### [MCP Dev Summit Seoul](https://events.linuxfoundation.org/mcp-dev-summit-seoul/)
- 일정과 형식: 8/13~14 서울 강남(Grand InterContinental Parnas) 현장 - 컨퍼런스이지 해커톤이 아님. Linux Foundation
  AAIF 주최
- 강화되는 부분: 세션 절반이 엔진의 질문 그 자체 - "Who Authorized That Agent? Identity and Policy Enforcement
  for MCP Tool Calls", MCP 인가, 도구 큐레이션, 프로덕션 실패 모드. Anthropic, AWS 키노트
- 동기와 커리어 가치: 서울에서 도구 권한, 정책 집행을 다루는 청중을 만나는 가장 빠른 방. 빌드 이월분은 없고 지식, 네트워크가 남는다
- 규칙, 마감, 충돌: 유료 - Late 구간(8/4~14) ₩650,000, Academic ₩149,000(등록 페이지 원문 확인). 6일 전

### [All Things Agentic Hackathon](https://allthingsagentichackathon.devpost.com/)
- 일정과 형식: 8/3~8/31 17:00 PT 제출, 온라인(Google 주최, Devpost)
- 강화되는 부분: GCP 프리미티브로 거버넌스 계층 직접 구현 - Agent Identity(zero-trust 접근), Agent Gateway(정책 집행),
  Model Armor, OTel 감사 로그
- 동기와 커리어 가치: \$180K(크레딧 중심), 솔로 전용 상 별도, 한국 거주 자격 확인됨
- 규칙, 마감, 충돌: 프로젝트는 제출 기간 중 신작이어야 하나 기존 코드는 공개(disclosure) 조건부 반입 가능(규칙 원문 확인). Gemini 3.5+와
  Google 프레임워크(ADK 등), GCP 서비스 필수. 결제, 정산 트랙 없음. Arc 마감과
  제품 로드맵의 Stage 1(독립화)이 8월에 전면 겹침

### [AI Agent Security - Multi-Step Tool Attacks](https://www.kaggle.com/competitions/ai-agent-security-multi-step-tool-attacks)
- 일정과 형식: 참가 등록 ~8/25, 최종 제출 9/1. 온라인 코드 대회(Kaggle, OpenAI, Google, IEEE) - 해커톤 아님
- 강화되는 부분: 도구 거버넌스의 공격면을 방어자 관점으로 훈련 - untrusted input에서 unsafe action으로 가는 다단계
  경로(Exfiltration, Confused deputy 등)
- 동기와 커리어 가치: \$50,000. 게이트 설계에 공격자 시야를 넣는 유일한 후보
- 규칙, 마감, 충돌: 일정, 상금은 실브라우저 확인이고 본 세션 정적 재확인 불가(Kaggle은 JS 렌더링). Rules 탭의 국가 제한 미확인

### [Voice AI Hackathon Seoul](https://luma.com/1jihwnz7)
- 일정과 형식: 8/24(월) 09:00~20:30 KST(행사 레코드, 상세 일정 기준), 서울 현장 1일
- 강화되는 부분: 실시간 음성 인터페이스, 사용자 위임, 예외 승인, 설명 UX, 당일 작동 데모
- 동기와 커리어 가치: 이동 비용이 낮고 하루 안에 빌드->발표를 반복하는 훈련
- 규칙, 마감, 충돌: 공식 페이지 한 줄 안에 영문 8/24, 국문 8/22가 병기돼 충돌하나, 행사 레코드와 상세 일정은 8/24다(2026-08-07 검증 -
  국문 쪽이 오기로 보임). 팀 2~4인 필요. 음성이 제품에 장식으로만 붙을 위험

### [TrueFoundry Agent Harness](https://luma.com/truefoundry-agent-harness-hackathon-sep19-2026)
- 일정과 형식: 9/19, 미국 South Bay 현장 1일
- 강화되는 부분: MCP 도구 권한, routing, retry, fallback, tracing, eval, 비용 통제, governance
- 동기와 커리어 가치: 지금 제품의 정책, 감사, 복구와 기술 질문이 거의 일치하고 프로덕션 agent infra 경력에 직접 설명 가능
- 규칙, 마감, 충돌: 등록 마감, 기존 코드 규칙 미확인. 하루 행사를 위한 미국 이동 비용, ETHOnline 회고 구간 침범

### [GOSIM Shenzhen](https://shenzhen2026.gosim.org/)
- 일정과 형식: 10/16~17, 선전 현장
- 강화되는 부분: Agent Engineering, MCP, A2A, multi-agent collaboration, open-source agent stack
- 동기와 커리어 가치: 아시아 오픈소스 AI 네트워크와 최신 agent engineering 접점
- 규칙, 마감, 충돌: 공식 페이지는 프로그램에 hackathons를 명시하지만 별도 도전과 참가 규칙은 아직 부족. Colosseum 빌드 중간

### [Since AI Hackathon](https://sinceai.ai/hackathon)
- 일정과 형식: 11/6~8, 핀란드 Turku 현장 72시간
- 강화되는 부분: 실제 기업 과제에 작동하는 AI 제품; 목업, 슬라이드가 아닌 실행물
- 동기와 커리어 가치: 1,000명 목표의 글로벌 AI 빌더, 기업 네트워크, AI 엔지니어링 커리어 신호
- 규칙, 마감, 충돌: 기존 코드 규칙 미게재(MLH 멤버 행사라 MLH 규정 적용 여지). 파트너 과제사는 공개됨 - Google for Developers,
  Bayer, Sandvik, Kongsberg, Valmet, €50,000 풀(2026-08-07 검증). 개별 과제문은 미공개. ETHGlobal
  Mumbai와 같은 날짜

### [Junction 2026](https://2026.hackjunction.com/)
- 일정과 형식: 11/13~15, 핀란드 Espoo 현장 48시간; 9/6은 여행 지원금 신청 마감(일반 참가 마감은 미게재 - 2026-08-07 검증, 종전
  "지원 9/6 마감"은 오독)
- 강화되는 부분: 팀 빌딩, 짧은 제품화, 라이브 데모와 발표
- 동기와 커리어 가치: 대형 국제 해커톤 경험과 여행 지원 가능성
- 규칙, 마감, 충돌: 기존 코드 규칙 미확인. challenge 미공개라 제품 이월분을 아직 정의할 수 없음. Mumbai/Since 바로 다음 주

### [Agent Forge Seoul](https://luma.com/agentforgeseoul)
- 일정과 형식: 8/22(토) 13:00~18:00 KST(행사 레코드, 2026-08-07 검증), 서울 강남 현장 5시간(본문 표현은 "full-day"),
  등록 열림(무료, 승인제)
- 강화되는 부분: 실시간 데이터, workflow 자동화, agent 실행 격리(Daytona 샌드박스), 배포, 상위 10팀 3분 무대 발표
- 동기와 커리어 가치: 낮은 이동 비용으로 production-grade agent와 발표를 함께 훈련
- 규칙, 마감, 충돌: 기존 코드 규칙 미확인. 본문 무날짜는 Luma 렌더링 특성이고 레코드는 8/22 단일 - 종전 "8월/10월 충돌"은 재현 실패로 철회.
  Arc 마감과 같은 날


### 행사에서 확인한 내용을 제품 개발 질문으로 옮기는 법

참가하지 않아도 행사 brief가 정확한 제품 질문이면 버리지 않는다.

- TrueFoundry의 요구는 `도구 권한 / trace / retry / eval / 비용 / escalation` 체크리스트로
  읽는다. 이는 결제 레일이 아니라 **에이전트 실행 하네스**에 남는다.
- Voice AI는 음성 기능 자체가 아니라 `누가 어떤 위임을 했고, 예외 승인이 무엇이었는가`를
  사용자에게 설명하고 확인받는 인터페이스가 될 때만 제품 델타다.
- Since AI의 "작동하는 데모만" 조건은 실행 완성도 훈련이고, Junction의 가치는 challenge가
  현재 제품의 열린 문제와 만날 때만 생긴다.

## 3. 일정이 겹치는 구간과 남은 결정

### 8/8부터 8/31까지

- **겹치는 일정:**
  - KeeperHub 제출은 8/13이다.
  - MCP Summit Seoul은 8/13부터 8/14까지이다.
  - Arc 제출과 Agent Forge가 모두 8/22이다.
  - Voice AI는 8/24이다.
  - All Things Agentic은 8/31까지이다.
  - 같은 기간에 제품 로드맵의 Stage 1(독립화)을 진행한다.
- **남은 결정:** 제품을 회복하고 독립화하는 작업을 멈추고 다음 제출 자료를 바로 만들
  정도로 조건이 좋은 행사가 있는지 판단해야 한다.

### 9/4부터 9/9까지

- **겹치는 일정:**
  - ETHOnline은 9/4에 시작한다.
  - BUIDL CTC는 9/6에 마감한다.
  - Colosseum Eternal은 9/7 09:00까지 시작해야 한다. 제출 마감이 아니다.
  - 금융 AI Challenge는 9/7 10:00에 마감한다.
  - Build the Era는 9/9 12:00 UTC에 마감한다.
- **남은 결정:** 국내 금융 분야의 경력 증거, Colosseum Eternal 참가, Ethereum과 Base
  기능 개발 가운데 무엇에 집중할지 정해야 한다. Build the Era는 BNB Agent Studio
  마켓플레이스를 만드는 행사이므로 다른 네 행사와 결과물을 공유하기 어렵다.

### 9/13부터 10/4까지

- **겹치는 일정:** Arbitrum Singapore 온라인 빌드톤이 ETHOnline 마무리, 행사 결과를
  제품에 반영하는 기간, Colosseum 초반과 겹친다.
- **남은 결정:** 기존 제품을 제출할 수 있다는 장점을 위해 세 작업 기간을 바꿀지 판단해야
  한다.

### 9/17부터 9/24까지

- **겹치는 일정:** ETHOnline 결과를 제품에 반영하는 기간에 TrueFoundry가 9/19에 열린다.
- **남은 결정:** 미국에 체류할 별도 일정이 없다면 제품 반영 기간을 유지할지 판단해야
  한다.

### 9/28부터 9/30까지

- **겹치는 일정:** 서울에서 열리는 GWDC Hackathon Korea와 Colosseum 시작일이 겹친다.
- **남은 결정:** 제품 주제와 직접 맞지만 과제와 상금 정보가 공개되지 않은 GWDC에
  Colosseum의 첫 사흘을 사용할지 판단해야 한다.

### 10/16부터 11/2까지

- **겹치는 일정:** Colosseum 진행 중에 GOSIM과 TUM 행사가 열린다.
- **남은 결정:** GOSIM에는 참가하지 않고 관찰과 교류만 할지, TUM을 Colosseum 대신
  참가할 행사로 볼지 판단해야 한다.

### 11/6부터 11/15까지

- **겹치는 일정:** Mumbai와 Since AI가 같은 날 열리고, 다음 주에 Junction이 열린다.
- **남은 결정:** Ethereum 분야의 경력 증거, AI 제품 개발 경험, 대형 범용 해커톤 경험
  가운데 직전 결과에 가장 필요한 것을 선택해야 한다.

### 11/27부터 11/29까지

- **행사:** Agent Pay Madrid가 열린다.
- **남은 결정:** 앞선 행사에서 만든 제품과 제출 자료를 합쳐, 에이전트 결제에 직접 관심이
  있는 참가자에게 보여줄 준비가 되었는지 판단해야 한다.

**현재 참가 결정은 0건이다.** 가능한 일정 조합의 한 예는 `Arc 또는 금융 AI Challenge →
ETHOnline → Colosseum → Agent Pay`지만, 이것은 추천 일정이 아니라 각 행사가 서로 다른
기능을 맡을 수 있음을 보인 조합 예시다. 실제 작업 캘린더에는 4절(참가 후보에서 제외했거나 후속 행사만 확인할 대상)의 참가 게이트를 통과한
행사에 대응하는 구간만 배정한다.

## 4. 참가 후보에서 제외했거나 후속 행사만 확인할 대상

- Rain x Monad의 Raingentic Commerce NYC(8/8~9)는 뉴욕 현장, 5년+ 경력 senior engineer
  명시 대상이고 확인 시점 다음 날 시작이라 참가 후보에서 제외했다(2026-08-07 검증,
  Encode Club 공동 주최 - Encode 캘린더의 "Raingentic Commerce"와 동일 행사이니 중복
  등재 주의). Rain, Monad, Encode는 Agentic Commerce 후속 행사를 확인할 대상으로 남긴다.
- Prava Agentic Commerce(7/31~8/2, 온라인 48시간)와 Base Agent Hackathon Korea #1
  (4월 하순 서울)은 종료됐다. Prava 규칙 원문은 기존 작업을 출발점으로 허용하되 "전체
  제출물일 수 없고 행사 전 존재분은 공개"를 요구했다 - 연속 개발 모델이 만나게 될 규칙
  형태의 실물 예시다. Base Korea는 공식 원문 기준 x402, ACP 중심이다(종전 "AgentKit"
  표기와 4/25 날짜는 3자 요약에만 있어 미확증 - 2026-08-07 검증). #2 발표는 X 접근
  한계로 확인 불가이며 부재 단정은 하지 않는다.
- 삼일PwC Open Innovation 2026(접수 8/3~9/11 18:00)은 모집분야가 Digital Asset
  결제, "AI 기반 감사 증거 수집, 분석 자동화"로 제품과 정면 인접하지만, 제출서류에
  사업자등록증이 명시돼 순수 개인 자격이 없어 제외. 법인/개인사업자가 생기면
  재검토(2026-08-07 공고 원문 확인).
- 자격 배제로 제외: OpenSearch Agent Skills Hackathon(~8/17)은 미국 거주자 한정,
  Amazon Nova AI Challenge는 재학생 팀 한정, KOSCOM AI Agent Challenge는 직전 회차가
  대학생 전용(2026 회차 미공고), FIN:NECT 챌린지는 대학생/예비창업자 대상에 이미
  종료(2026-08-07 확인).
- 한국코드페어는 2026년 참가 자격이 중, 고등학생이라 제외했다.
- GSA MCP Server and AI Agent Hackathon은 미국 연방정부 내부 참가 행사라 제외했다.

## 5. 계속 찾을 곳

### 결제 제품과 직접 관련된 행사를 확인할 곳

- Circle/Arc House, Encode Club - 단 Circle 공식 Luma 캘린더는 향후 행사 0건(2026-08-07
  API 확인)이라 Arc 이후는 공백
- ETHGlobal, Base Korea, Colosseum(가을 해커톤 + Eternal 다음 윈도)
- Prava, Rain, Coinbase/x402 관련 행사, KeeperHub, OKX.AI Genesis 차기 회차
- BNB Chain 공식 해커톤 페이지(2026-08-13 추가) - 목록 페이지에 박힌 JSON의 `status`
  필드가 진행 여부를 그대로 말해 준다(2026-08-13 실제 측정: 12개 중 `Ongoing` 2,
  나머지 `Ended`, `Upcoming` 0). **트위터나 디스코드로만 공지된 행사는 이 목록에 없을 수
  있으므로**, 이 페이지가 비었다는 것을 "행사가 없다"로 읽지 않는다
- MERGE Agent Pay, TUM Blockchain Club
- Seoulana(Superteam Korea) 하반기 로컬 트랙 - 공식 랜딩 세 번째 카드가 "Coming
  Soon"(2026-08-07). 상반기 패턴은 로컬 트랙 \$10K -> Colosseum 글로벌
- KBW 2026 사이드이벤트 Luma 캘린더 - 현재 "Coming Soon". 오픈되면 해커톤 유무 확인
- x402 on XRPL: AI Builders Night Korea(8/13 서울 밋업, 현재 대기자만) - XRPL Korea는
  2025 서울 해커톤 주최라 후속 해커톤 파이프라인
- StableHacks 차기 - 2026 회차(3월 종료)는 기관 스테이블코인 결제 트랙에 KYC, KYT, AML
  필수로 주제 적합도가 이번 조사 전체에서 가장 높았다
- Solana 재단 계열은 8~12월 해커톤 0건(공식 커뮤니티 캘린더 future 33건 전수 분류,
  2026-08-07) - 컨퍼런스, 코워킹뿐이고 Hacker House도 런던 1건뿐

### 에이전트 기능을 강화할 행사를 확인할 곳

- AI Builders Seoul, Tokyo, TrueFoundry
- Since AI, Junction, GOSIM
- OpenAI DevDay Exchange Seoul - 2026 개최 도시로 확정됐고 날짜 미발표("Sign up to be
  the first to know") - 알림 신청을 걸어둘 것. 검색에 뜨는 "Seoul Nov 13"은 2025
  회차다(2026-08-07 확인)
- Linux Foundation AAIF 시리즈 - AGNTCon+MCPCon 도쿄 9/10~11(8/24까지 ¥60,000, 이후
  두 배), 새너제이 10/22~23. MCP Dev Summit Seoul의 후속 무대
- 랄프톤(팀어텐션) 하반기 회차, NIPA "AI AGENT 융합, 확산 지원사업"(과제형, 기업 한정
  여부 미확인)
- Stripe ACP, AWS 글로벌 에이전트 해커톤, Anthropic 아시아 행사는 창 안에 없음을
  확인(2026-08-07) - 각각 Tour 쇼케이스뿐 / 2025 회차 종료 / 런던 Founder House뿐
- lablab.ai와 Devfolio는 발견용으로 쓰되 공식 주최자 페이지에서 다시 확인 -
  lablab.ai는 2026-08-07 현재 자동 접근이 전면 차단돼(403, Cloudflare) 수동 확인 필요.
  DoraHacks, HackQuest, Devpost도 같은 규칙으로 쓴다

## 6. 연결 문서

- 2026-09-24 Circle과 Arc 프로그램 조사 대화는
  Arc Microgrants와 개발자 보조금, 새 해커톤의 후보를 찾는 등급 D 자료다. 공식 일정과 자격을
  재확인하지 않았으므로 1절(결제 제품과 직접 맞는 행사)의 확정 행사 행으로 옮기지 않았다.
  Circle과 Arc 허브는 원글부터 이어진 자료를 모으고,
  참여 프로그램 판독은 보존한 공식 공고의 조건을 대조한다.
- Arc 해커톤 질문 묶음의
  7번은 2026-10-08 보관본으로 Tameion, Arc Microgrants,
  Encode London, ETHGlobal Mumbai의 공개 조건을 대조하고, 사용자가 고른 네 축으로 지원 조건을 정했다(2026-10-14).
  사용자가 판정 기준을 대화로 새로 정하기로 해서 0절(선발 기준)은 근거로 쓰지 않았다. 이 네 행사는 아직
  이 문서의 행사 행으로 옮기지 않았다.
- 행사의 사업상 의미와 현재 개발 위치는 사업 판단 기록에 정리한다.
- 참가 동기와 경력 기준은 전문성 및 경력 판단 문서에 정리한다.
