# 기업 지급 결제에서 출발하는 Circle과 Arc: 제품의 역할, 참여 프로그램과 AI 개발 방향

외부 공유 자료를 작성하기 위한 목차 초안입니다. 기업의 지급 업무와 실제 문제를 먼저 살펴보고, Circle과 Arc가 제공하려는 기능, 개발 프로그램과 제품 개발 방향으로 이어갑니다. 제품 설명과 프로그램 조건은 공개 출처를 바탕으로 구성하며, 제품 조합과 AI의 역할은 검토할 개발 가설로 제시합니다.

## 1. 기업 지급 결제: 약속한 대금을 지급하는 업무는 어떻게 이어지는가?

### 1.1 지급할 의무의 확인: 계약, 주문, 납품과 청구서는 어떻게 연결되는가?

### 1.2 지급 대상과 조건의 확인: 누구에게, 얼마를, 어떤 통화와 기한으로 지급하는가?

### 1.3 지급 승인과 자금 준비: 누가 승인하며 필요한 돈과 통화는 어디에 있는가?

### 1.4 지급 실행과 수취 확인: 송금 요청, 자산 이전과 상대방의 대금 수령은 어떻게 다른가?

### 1.5 기록 대조와 예외 처리: 청구서, 지급 기록과 잔액을 어떻게 맞추며 오류와 분쟁은 어떻게 처리하는가?

이 순서는 기업 업무를 설명하기 위한 구성입니다. 모든 기업이 같은 시스템이나 순서로 처리한다는 가정은 두지 않습니다.

## 2. 지급 결제의 문제: 어느 업무에서 어떤 일이 실제로 발생하는가?

### 2.1 지급 지시의 진위: 거래처가 보낸 요청과 실제 지급할 상대는 일치하는가?

한국 기업의 무역대금 계좌 변경 사기와 Toyota Boshoku의 위조 지급 지시 피해를 함께 설명합니다. [KOTRA 사례](https://dream.kotra.or.kr/kotranews/cms/news/actionKotraBoardDetail.do?CONTENTS_NO=2&MENU_ID=80&SITE_NO=3&bbsGbn=242&bbsSn=242&pNttSn=226395), [Toyota Boshoku 공시](https://www.toyota-boshoku.com/global/news/_assets/upload/190906e-1.pdf)

### 2.2 승인과 실행의 일치: 올바른 지급을 의도해도 왜 다른 금액이 나갈 수 있는가?

Citi의 Revlon 관련 오지급을 통해 사람의 확인, 시스템 처리와 실제 지급 결과를 구분합니다. [Citi 분기보고서](https://www.citigroup.com/rcs/citigpa/storage/public/q2003c.pdf)

### 2.3 판매대금 정산: 고객의 결제 완료가 판매자의 대금 수령을 뜻하는가?

티몬과 위메프의 정산 지연을 설명합니다. [금융위원회 발표](https://www.fsc.go.kr/no010101/82816)

### 2.4 고객자금과 장부: 장부에 기록한 잔액은 실제 보관한 돈과 일치하는가?

Synapse의 장부 대사 문제와 영국 결제회사 도산 관련 감독기관 자료를 구분해 다룹니다. 대사(reconciliation)는 서로 다른 장부와 실제 지급 및 잔액 기록을 대조하는 업무입니다. [Synapse 관재인 보고서](https://www.cravath.com/a/web/ogvbURUX4uGN9FJ178bssS/aafskj/20250206-485-chapter-11-trustees-fifteenth-status-report.pdf), [영국 금융행위감독청 발표](https://www.fca.org.uk/news/press-releases/payment-safeguarding-rules-changes)

### 2.5 국경을 넘는 지급: 현지 매출과 송금 요청이 있어도 왜 대금을 받지 못하는가?

모잠비크의 달러 부족으로 인한 한국 수출기업의 대금 지연과 항공사 해외 수익의 송금 제한을 설명합니다. 익명 기업 사례와 업계 전체 집계를 구분합니다. [KOTRA 자료](https://dream.kotra.or.kr/kotranews/cms/news/actionKotraBoardDetail.do?CONTENTS_NO=1&MENU_ID=70&SITE_NO=3&bbsGbn=00&bbsSn=506%2C242%2C244%2C322%2C245%2C444%2C246%2C464%2C518%2C505%2C484&pEndDt=&pIndustCd=&pKbcCd=&pNatCd=&pNewsAll=&pNewsCd=242&pNewsCd=244&pNewsCd=245&pNewsCd=246&pNewsCd=322&pNewsCd=464&pNewsCd=484&pNewsCd=505&pNewsCd=506&pNewsCd=518&pNewsGbn=506%2C242%2C244%2C322%2C245%2C246%2C464%2C518%2C505%2C484&pNttSn=220388&pRegnCd=&pStartDt=&pageNo=12&pagePerCnt=10&recordCountPerPage=10&sSearchVal=&viewType=), [국제항공운송협회 발표](https://www.iata.org/en/pressroom/2025-releases/2025-12-10-01/)

### 2.6 문제의 구분: 자금 이동 기술로 개선할 부분과 계약, 운영 및 제도에서 처리할 부분은 무엇인가?

사고 사례는 문제가 발생한 업무를 보여주는 근거입니다. 특정 제품이 그 사고를 예방한다는 증거로 사용하지 않습니다.

## 3. Circle의 해결 방향: 디지털 자산에 대한 접근, 보관, 교환과 이동을 어떻게 연결하려는가?

### 3.1 Circle의 목표: 디지털 자산과 인터넷 금융 플랫폼은 어떤 업무 변화를 지향하는가?

### 3.2 기업 업무의 변화: 지급, 외환과 자금 관리를 어떻게 연결하려는가?

### 3.3 제품 구성: 개발 기반, 디지털 자산과 금융 애플리케이션은 각각 무엇을 제공하는가?

### 3.4 개발자의 과제: 제공된 기능 위에서 어떤 상거래와 지급 업무를 완성해야 하는가?

Circle의 전체 목표와 기업 지급 결제라는 설명 주제를 구분합니다. [Circle의 제품 비전](https://www.circle.com/blog/building-the-internet-financial-system-circles-product-vision-for-2026), [Team Arc의 빌더 제안](https://www.arc.io/blog/the-unfinished-business-of-finance-machine-commerce-and-global-money)

## 4. Circle 제품: 각 제품은 기업의 어떤 업무를 맡는가?

### 4.1 지급할 자산: USDC와 EURC는 어떤 통화의 대금을 다루는가?

### 4.2 은행 자금과의 연결: Circle Mint는 법정화폐와 스테이블코인을 어떻게 연결하는가?

### 4.3 지급 승인과 실행 요청: Circle Wallets는 요청과 서명 승인을 어떻게 구분하는가?

### 4.4 체인 사이의 자금 이동: CCTP와 Gateway는 어떤 업무를 서로 다르게 맡는가?

CCTP(Cross-Chain Transfer Protocol)는 체인 간 USDC 이전 프로토콜이며, Gateway는 선행 예치한 USDC를 지원 체인에서 사용할 통합 잔액으로 다루는 서비스입니다.

### 4.5 환전과 교환 결제: StableFX는 견적과 자산 교환을 어떻게 연결하는가?

### 4.6 수취인까지의 지급: CPN의 지급 상품과 Managed Payments는 무엇을 맡는가?

CPN(Circle Payments Network)은 금융기관과 지급 파트너를 연결하는 Circle의 지급 네트워크입니다. 스테이블코인 지급, 현지 법정화폐 지급과 운영 관리의 역할을 구분합니다.

### 4.7 자금 운용과 파트너 자산: USYC와 xReserve는 지급 자산과 어떻게 다른가?

### 4.8 앱과 에이전트의 구현: App Kits, Agent Stack과 Arc Studio는 어떤 개발 작업을 돕는가?

제품 이름과 실제 실행 서비스, 지원 체인과 이용 조건을 함께 설명합니다. [Circle 개발 문서](https://developers.circle.com/), [App Kits](https://docs.arc.io/app-kit), [Agent Stack](https://www.circle.com/blog/introducing-circle-agent-stack-financial-infrastructure-for-the-agentic-economy), [Arc Studio](https://docs.arc.io/ai/arc-studio)

## 5. Arc의 역할: 금융 업무의 실행과 기록을 어떤 공통 기반에서 처리하려는가?

### 5.1 공통 기반의 필요성: Circle은 자산, 계약과 결제 결과를 왜 연결하려는가?

### 5.2 Arc의 구성: 자산 이전과 계약 실행 결과를 무엇이 처리하고 기록하는가?

### 5.3 지급 비용: USDC로 거래 수수료를 내는 방식은 어떤 관리 업무를 줄이려는가?

### 5.4 거래 확정과 업무 완료: 어느 기록을 확인하면 다음 처리를 시작할 수 있는가?

### 5.5 기업 데이터와 운영 권한: 어떤 정보를 공개하며 누가 거래 기록을 확정하는가?

### 5.6 Circle 제품과의 연결: Arc의 기록은 환전, 다른 체인의 자금과 수취인 지급에 어떻게 이어지는가?

### 5.7 앱이 완성할 기업 업무: 거래처 확인, 지급 조건과 예외 처리는 누가 맡는가?

현재 기능, 향후 계획과 앱이 설계할 업무를 구분합니다. 거래 확정과 은행 입금 완료도 구분합니다. [Arc Network](https://docs.arc.io/arc-chain), [거래 확정](https://docs.arc.io/arc/concepts/deterministic-finality), [비공개 실행 설계](https://docs.arc.io/arc/concepts/opt-in-privacy)

## 6. Circle과 Arc의 조합: 각 제품의 업무와 역할은 어떤 문제의 개선으로 이어지는가?

### 6.1 제품별 역할표: 담당 업무, Arc와의 관계, 연결 제품과 기대 효과를 어떻게 정리하는가?

Arc, 지급 자산, 자금 전환, 승인, 자금 이동, 환전, 수취, 자금 운용과 개발 도구를 제품별로 나란히 정리합니다. 기대 효과 옆에 지원 범위와 선행 조건을 붙입니다.

### 6.2 업무별 제품 조합: 자금 준비부터 승인, 실행, 수취 확인과 대사까지 어떻게 연결하는가?

### 6.3 조합의 조건과 한계: 어떤 연결이 제공되며 어떤 연결은 앱과 운영 절차로 만들어야 하는가?

### 6.4 개발 방향의 기준: Arc 사용과 Circle 제품 연결이 기업의 어떤 업무를 개선하는가?

Arc 기반 개발을 검토하되, Circle 제품과 연결해 실제 지급 업무에 가까워지는 방향을 제시합니다. 모든 제품을 사용해야 한다는 조건이나 기존 사고 해결의 보장으로 바꾸지 않습니다. [Circle의 제품 비전](https://www.circle.com/blog/building-the-internet-financial-system-circles-product-vision-for-2026)

## 7. 참여 프로그램: 프로그램별 목적, 요구사항과 지원 내용은 무엇인가?

아래 활동 구분은 각 공고의 목적을 비교하기 위한 설명 구성입니다. 먼저 각 프로그램을 목적, 대상, 필수 기술, 제출물, 심사, 지원, 일정과 신청 경로라는 같은 항목으로 설명합니다. 행사 등록, 작품 제출과 지원금 신청을 구분하며, 과거 회차를 현재 모집으로 소개하지 않습니다. [Arc House 이벤트](https://community.arc.io/public/events)

### 7.1 개발 경쟁: 해커톤과 후원 상금은 어떤 제품과 제출 증거를 요구하는가?

Canteen의 Agora, Lepton과 Tameion, Encode의 DeFi 및 Enterprise & DeFi와 Programmable Money, LabLab의 Agentic Commerce 및 Agentic Economy, ETHGlobal의 HackMoney, Cannes, New York, ETHOnline 및 Mumbai를 다룹니다. OpenClaw USDC와 Agentic Economy Prize의 별도 참여 방식도 비교합니다. 대회별 실제 사용, 테스트넷과 메인넷, 도구와 코드 공개 요구를 구분합니다. [Tameion](https://tameion.thecanteenapp.com/), [LabLab Agentic Economy](https://lablab.ai/ai-hackathons/nano-payments-arc), [ETHGlobal Mumbai](https://ethglobal.com/events/mumbai)

### 7.2 자금 지원과 사업 성장: 작은 결과물, 제품 출시와 회사의 성장에는 어떤 지원이 연결되는가?

Arc Microgrants, Circle Developer Grants, Arc Acceleration Season, Programmable Money 후속 액셀러레이터, Arc Builders Fund와 Circle Ventures Investor Network를 구분합니다. 지원금, 기술 및 홍보 지원과 투자 검토의 차이도 설명합니다. [Microgrants](https://dorahacks.io/hackathon/arc-microgrants), [Developer Grants](https://www.circle.com/grant), [Builders Fund](https://www.arc.io/builders-fund)

### 7.3 교육과 구현 실습: Bootcamp와 워크숍은 어떤 기능을 배우게 하는가?

Programmable Money Bootcamp, ArcShop과 제품별 실습에서 지갑, 계약, 체인 간 이동, 환전과 에이전트 지급을 다룹니다. 교육 등록과 해커톤 또는 지원금 신청을 구분합니다. [Bootcamp](https://community.arc.io/public/events/programmable-money-on-arc-bootcamp-mvixsdscmu)

### 7.4 기술 상담: Office Hours와 Design Clinic에는 무엇을 준비해 가져가는가?

Office Hours는 질의응답과 개발 상담이며 Design Clinic은 시스템 설계와 계약 패턴 검토입니다. 구체적인 질문과 등록 승인을 요구하는 회차를 설명합니다. [Technical Office Hours](https://community.arc.io/public/events/technical-office-hours-wyeu64jawb), [Design Clinic](https://community.arc.io/public/events/arc-discord-architecture-review-design-clinic-60rn65umlw)

### 7.5 결과 발표와 공동 개발: Spotlight, Demo Day와 지역 모임에서는 어떤 경험을 얻는가?

제품 발표 관람, 직접 시연, 함께 개발하는 Build Club과 지역 교류를 구분합니다. 발표된 제품은 팀의 구현 사례이며, 독립적인 성능 검증 결과와 구별합니다.

### 7.6 생태계 참여: Architects, 컨퍼런스와 Pragma는 어떤 기여와 교류를 지원하는가?

Architects는 커뮤니티 기여와 인정을 연결하는 프로그램입니다. Pragma와 Circle House 등은 강연 및 교류, 별도 입장과 초대 조건을 설명합니다. [Arc House와 Architects 소개](https://community.arc.io/public/events/introducing-arc-house-and-architects-hyp33duk9f), [Pragma Mumbai](https://ethglobal.com/events/pragma-mumbai)

### 7.7 보안 연구: Bug Bounty는 어떤 취약점 보고와 보상을 다루는가?

개발 경쟁과 취약점 보고 활동을 구분하고 대상 범위, 보고 규칙과 보상 조건을 별도로 설명합니다. [Arc Bug Bounty](https://hackerone.com/arc-bbp/)

### 7.8 참여 조건의 읽기: 행사 일정, 제출 마감, 신청 조건과 지원의 범위를 어떻게 확인하는가?

본행사와 부대 행사, 전체 상금과 Arc 후원 상금, 지원금과 투자 검토를 구분합니다. 공고와 주최자 안내가 다르면 차이를 남기고 신청에 적용할 최신 규칙을 확인합니다.

## 8. Arc + AI 제품 방향: 기업 문제를 어떤 제품 조합과 프로그램으로 연결할 수 있는가?

### 8.1 지급 전 확인: 청구서와 거래처 변경 요청을 검토하고 승인된 지급만 실행할 수 있는가?

### 8.2 조건부 지급: 납품과 계약 단계의 확인을 대금 지급 및 분쟁 처리와 연결할 수 있는가?

### 8.3 지급 후 확인: 지급 기록, 판매자 정산과 고객별 잔액을 지속적으로 대조할 수 있는가?

### 8.4 자금 준비와 국제 지급: 분산된 잔액, 환전과 수취인 지급을 함께 관리할 수 있는가?

### 8.5 기업의 유료 자원 구매: 에이전트가 예산 안에서 API와 서비스를 구매하고 비용 근거를 남길 수 있는가?

### 8.6 문제와 프로그램의 연결: 어떤 개발 주제, 제출 증거와 지원 방식이 각 업무에 연결되는가?

### 8.7 제품 방향의 판단: Circle과 Arc의 목표에 어떻게 연결되며 무엇으로 개선을 확인할 것인가?

AI는 문서 해석, 기록 대조와 판단 보조를 맡고, 지급 권한과 한도는 명시적인 정책 및 승인 절차로 제한하는 구성을 검토합니다. Arc와 Circle 제품의 역할, AI 판단, 기업의 운영 책임과 외부 제도 조건을 구분합니다. 개인의 구현 가능성 평가는 이후에 다룹니다. [Team Arc의 빌더 제안](https://www.arc.io/blog/the-unfinished-business-of-finance-machine-commerce-and-global-money), [Tameion 개발 제안](https://tameion.thecanteenapp.com/)
