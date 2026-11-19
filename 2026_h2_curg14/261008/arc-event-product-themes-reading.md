# Arc 이벤트의 개발 문제와 참여 방식 비교

이 문서는 [Arc 행사 공고](https://community.arc.io/public/events)에 제시된 개발 문제, 활동 목적과 참여 방식을 비교한다. 공고의 설명을 재구성한 자료이며, 개인에게 적합한 프로그램이나 현재 접수 여부를 확정하지 않는다.

아래 구분은 내가 각 공고의 활동 목적과 개발 문제를 비교하려고 만든 것이다. 공고가 전체 생태계를 이 방식으로 분류하거나 개발자의 참여 순서를 정한 것은 아니다. 행사별 세부 조건과 세션은 각 공고에서 확인해야 하며, 이 문서는 그 내용의 차이를 설명한다.

## 만들 제품을 정하는 행사와 구현을 배우는 행사는 다르다

| 공고가 제공하는 활동 | 본문에서 읽을 내용 | 서로 혼동하지 않을 점 |
|---|---|---|
| 해커톤과 후원 상금 | 개발 주제, 필수 도구와 체인, 제출물, 기존 코드 허용, 심사와 상금 및 등록 조건을 읽는다. | 같은 대회의 킥오프와 현장 행사 및 발표회가 별도로 올라올 수 있다. 전체 상금과 Arc 상금도 다르다. |
| 워크숍과 Bootcamp | 지갑과 계약, API, 체인 간 자금 이동, 에이전트 결제와 실습 예제를 읽는다. | 준비할 계정과 노트북이 있을 수 있다. 교육 참가가 해커톤 등록이나 자금 지원 선정은 아니다. |
| Technical Office Hours와 Design Clinic | 구체적인 기술 질문과 프로젝트 설계에 대한 상담을 읽는다. | 사전 질문, 프로젝트 자료와 등록 승인을 요구하는 회차를 구분한다. |
| Builder Spotlight, Show & Tell과 Demo Day | 개발한 제품의 목적, 구현과 사용 사례 및 발표 기회를 읽는다. | 관람과 자신의 발표, 새 대회 모집과 선발팀 결과 발표는 다르다. |
| Microgrants와 액셀러레이터 | 배포한 결과물, 기존 사업의 통합 개발, 심사와 후속 지원을 읽는다. | 작은 실험의 지원, 사업 운영 단계의 지원과 이전 해커톤 선발팀 후속 지원은 서로 다르다. |
| 지역 모임과 Build Club | 도시와 언어, 함께 개발하기, 커뮤니티 소개와 교류 활동을 읽는다. | 개최 장소가 곧 시민권 제한은 아니다. 온라인 여부와 대상 표현은 공고마다 확인한다. |

개인 제품이 아직 구체화되지 않았다는 사정만으로 두 해커톤과 Microgrants가 최적이라고 결론 낼 수는 없다. 제품 제안을 읽는 행사뿐 아니라 구현 실습, 개발자의 사례와 기술 상담도 아이디어를 구체화하는 데 필요한 내용을 제공한다. 이는 공고에 명시된 활동을 비교한 설명이며 참가 가치의 순위를 매긴 것은 아니다.

## 공고에서 제시한 개발 문제

| 사례와 자료 | 주최자가 제시한 문제와 제품 | 제출 및 증거의 차이 |
|---|---|---|
| [Lepton 주최자 안내](https://lepton.thecanteenapp.com/) | 유료 자원을 구매하는 에이전트, 에이전트 서비스를 건별로 판매하기, 에이전트 간 지급, 지속 과금, 개발 도구, 창작자와 출판자의 콘텐츠 수익화를 제안한다. 기존 공개 서비스의 플러그인, API와 웹훅에 결제를 붙이는 사례도 제시한다. | RFB(Requests for Builders, 주최자가 제안한 개발 문제)는 경쟁 트랙이 아니다. 실제 사용과 AI의 판단을 강조하고 기존 프로젝트에서 행사 중 추가한 결과를 구분한다. |
| [Tameion 주최자 안내](https://tameion.thecanteenapp.com/) | 기업 자금 관리, 지급 채무 및 받을 돈(accounts payable/accounts receivable) 자동화, 외주 및 공급업체 관리, 자율 사업 운영과 거래 상대의 위험 심사를 제안한다. 송장 대조, 지급 판단, 실행, 대사와 감사 기록을 연결한다. | 실제 사업 사용과 지급 기록, 공개 코드 및 녹화 시연을 요구한다. 목업이나 합성 데이터와 실제 사용을 구분하며 기존 프로젝트의 추가 결과를 본다. |
| [LabLab Agentic Economy 규칙](https://lablab.ai/ai-hackathons/nano-payments-arc) | API, 자료, 모델 추론과 연산을 사용량에 따라 과금하며 에이전트가 USDC로 지급하는 앱을 제안한다. Gemini, 특화 모델과 자료 API에 대한 별도 과제도 설명한다. | 필수 Arc 정산과 USDC 및 Nanopayments, 동작 시연과 거래 증거, 공개 코드, 제품 피드백을 요구한다. 여러 상금 표기가 충돌하는 부분은 합산하지 않았다. |
| [LabLab Agentic Commerce 규칙](https://lablab.ai/event/agentic-commerce-on-arc) | 소액 상거래, 에이전트의 신원과 정책, 자율 구매 및 판매, 개발 도구와 사용자 경험을 제안한다. Google 도구를 쓰는 별도 과제를 설명한다. | 온라인 제출과 초대된 참가자의 현장 활동, 일반 등록과 조기 접근 제품의 등록 기한을 구분한다. |
| [ETHGlobal Cannes Arc 상금](https://ethglobal.com/events/cannes2026/prizes/arc) | 조건부 스마트 계약, 여러 체인의 USDC 유동성을 연결하는 앱, 에이전트 경제와 실제 의사 결정에 쓰는 예측 시장을 제시한다. | 신청하는 상금 분야, 작동하는 화면과 서버, 구조도, 시연 및 상세 저장소를 요구한다. 후원 상금은 전체 대회와 별도로 읽는다. |
| [ETHGlobal New York Arc 상금](https://ethglobal.com/events/newyork2026/prizes/arc)과 [ETHOnline Arc 상금](https://ethglobal.com/events/ethonline2026/prizes/arc) | 개별 Arc 상금 페이지에 개발 주제와 요건을 설명한다. | 해당 회차의 원문 조건을 확인한다. 회차 간 금액과 기한을 옮겨 쓰지 않는다. |
| [OpenClaw USDC 공고](https://community.arc.io/public/events/openclaw-usdc-hackathon-on-moltbooks-xdk1tu0nvo) | 에이전트 상거래, OpenClaw 기능과 새로운 스마트 계약이라는 경쟁 분야를 명시한다. | Arc 사이트에 실렸다는 이유로 Arc 배포 의무를 추가하지 않는다. 제출과 투표 방식도 공고의 설명을 따른다. |
| [Programmable Money 공고](https://community.arc.io/public/events/hackathon-programmable-money-74llz8htis) | DeFi와 에이전트 분야에서 Arc 및 Circle 도구를 활용한 제품을 개발한다. | 작동하는 시제품, 화면과 서버, 코드 및 시연을 요구한다. 후속 액셀러레이터는 상위 팀을 이어 지원한다고 적는다. |
| [Agentic Economy Prize 공고](https://community.arc.io/public/events/the-agentic-economy-prize-aignfyumkq) | 실제 사업에서 지급하거나 수취하는 자율 에이전트를 제안한다. | 기존 XPRIZE 참가 팀, Google Cloud와 Circle Agent Stack 및 실제 USDC 거래 증거라는 조건을 다른 해커톤에 옮기지 않는다. |

다시보기의 공개 대화 텍스트에는 Gateway의 잔액과 전송, Bridge Kit의 통합, Hinkal의 개인정보 보호, Para와 Crossmint의 지갑 및 에이전트 개발, Arc의 합의와 프라이버시 등 구현 설명이 있다. 개발자가 만든 Vertex, Gyasss, Cairn과 MEV Shield의 발표도 별도로 연결되어 있다. 이는 발표자와 팀이 설명한 구현이며 성능이나 상용 채택을 독립적으로 검증한 결과는 아니다.

## 지원 프로그램은 무엇을 받아 심사하는가

| 프로그램 | 공고의 입력과 목적 | 아직 구체적인 개인 제품이 없는 경우에 읽을 점 |
|---|---|---|
| [Arc Microgrants](https://community.arc.io/public/events/arc-microgrants-f8tijfjhyq) | 이미 Arc 메인넷에 배포한 작은 결과물, 공개 코드와 설명 및 공개 프로필을 받는다. 회사와 사용 실적은 필수 조건으로 쓰지 않는다. | 아이디어만 신청하는 공고는 아니다. 해당 회차의 마감과 제외 조건을 확인하고 결과물을 만든 뒤 제출한다. 상시 반복 공고로 일반화하지 않는다. |
| [Arc Acceleration Season](https://community.arc.io/public/events/arc-acceleration-season-vanemu91dk) | 라틴아메리카 핀테크와 AI 스타트업이 기존 사업에 Arc 및 Circle을 통합하고 출시하는 과정이다. | 대상 사업과 지역, 기존 실적을 읽는다. 국적만으로 참가 불가를 확정할 상세 자격 규칙은 본문에 제시되지 않았다. |
| Programmable Money 후속 액셀러레이터 | 해커톤의 상위 팀이 제품 출시를 이어가도록 워크숍, 상담과 진행 점검을 제공한다. | 새로운 독립 공개 신청과 이전 해커톤 선발팀 지원을 구분한다. |
| [Circle Developer Grants 소개 행사](https://community.arc.io/public/events/circle-developer-grants-building-on-arc-and-the-circle-developer-platform-o6p6ge6b4n) | 자금 지원의 취지, 평가와 신청 및 기술 지원과 홍보를 소개한다. | 방송 등록과 지원금 신청은 다르다. 프로그램 안내와 실제 신청 양식의 기준을 따로 확인한다. |

## 확인 범위

공고의 조건은 회차별로 구별한다. 날짜는 공개 데이터, 본문에 명시한 제출 마감과 주최자 안내를 따로 기록한다. Tameion의 빈 Arc 설명을 과거 또는 주최자 설명으로 몰래 채우지 않았다. 로그인이나 신청을 제출하지 않았고 녹화 영상 자체를 시청하지 않았다.
