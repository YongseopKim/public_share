# 기업 지급 결제에서 출발하는 Circle과 Arc: 제품의 역할, 참여 프로그램과 AI 개발 방향

기업의 지급 결제는 송금 버튼을 누르는 순간보다 훨씬 앞에서 시작하고, 거래가 처리된 뒤에도 이어진다. 계약과 청구서를 확인하고, 지급할 상대와 금액을 승인하며, 필요한 자금을 준비해야 한다. 돈을 보낸 다음에는 상대가 대금을 받았는지 확인하고 장부를 맞춘다. 지급 기술을 선택하려면 이 업무 가운데 무엇을 개선하려는지 먼저 정해야 한다.

이 글은 기업의 지급 업무와 실제 문제에서 출발해 Circle의 방향, 제품별 역할과 Arc의 기능을 살펴본다. 이어 공개된 개발 프로그램의 목적과 요구사항을 설명하고, 기업 지급 결제를 Arc + AI로 개선하는 제품 방향을 검토한다. 제품과 프로그램 설명에는 공개 출처를 붙였으며, 업무별 제품 조합과 AI의 활용은 이 글에서 제안하는 개발 가설이다.

## 1. 기업 지급 결제: 약속한 대금을 지급하는 업무는 어떻게 이어지는가?

이 글에서는 기업 지급 업무를 지급 의무의 확인, 대상과 조건의 확인, 승인과 자금 준비, 실행과 수취 확인, 기록 대조와 예외 처리로 나누어 설명한다. 이는 문제를 살펴보기 위해 정한 구성이다. 기업마다 담당 조직과 시스템이 다르며, 일부 업무는 동시에 진행되거나 반복된다.

### 1.1 지급할 의무의 확인: 계약, 주문, 납품과 청구서는 어떻게 연결되는가?

청구서를 받았다는 사실과 대금을 지급할 의무가 확정됐다는 사실은 구분해야 한다. 구매 담당자는 무엇을 주문했는지 알고, 현업 담당자는 물품이나 서비스를 받았는지 확인하며, 재무 담당자는 지급 금액과 시기를 관리한다. 계약, 주문, 납품 자료와 청구서가 서로 맞아야 지급 근거를 설명할 수 있다.

예를 들어 외주 개발 계약에서 중간 결과물을 제출하면 일부 대금을 지급하기로 했다고 가정하자. 제출 파일이 있다는 사실만으로 지급 조건이 충족되는 것은 아니다. 누가 결과물을 검수하고 어떤 기준으로 승인하는지까지 정해야 한다. Team Arc도 상거래 조건과 단계별 지급, 분쟁 처리를 개발자가 구현할 업무로 제안한다. [Team Arc의 개발 제안](https://www.arc.io/blog/the-unfinished-business-of-finance-machine-commerce-and-global-money)

### 1.2 지급 대상과 조건의 확인: 누구에게, 얼마를, 어떤 통화와 기한으로 지급하는가?

지급할 의무를 확인한 다음에는 그 의무를 구체적인 지급 지시로 바꾼다. 수취인의 이름과 계좌 또는 지갑 주소, 지급 금액, 통화, 기한과 비용 부담을 확인한다. 계약 상대가 맞더라도 지급 주소가 바뀌었거나 청구 통화와 수취 통화가 다르면 추가 확인이 필요하다.

특히 거래처의 계좌 변경 요청은 문서의 내용과 요청자의 권한을 함께 확인해야 하는 문제다. 익숙한 이메일 주소에서 왔다는 이유만으로 새 계좌를 신뢰하면 지급 자산이 올바르게 이전되어도 잘못된 상대에게 돈이 도착할 수 있다. 대한무역투자진흥공사(KOTRA)가 소개한 무역대금 사기 사례가 이 차이를 보여준다. [KOTRA의 계좌 변경 사기 사례](https://dream.kotra.or.kr/kotranews/cms/news/actionKotraBoardDetail.do?CONTENTS_NO=2&MENU_ID=80&SITE_NO=3&bbsGbn=242&bbsSn=242&pNttSn=226395)

### 1.3 지급 승인과 자금 준비: 누가 승인하며 필요한 돈과 통화는 어디에 있는가?

지급 요청을 작성하는 사람, 거래처 정보를 변경하는 사람과 지급을 승인하는 사람은 서로 다른 권한을 가질 수 있다. 승인한 금액과 수취인을 실행 단계까지 유지하려면 권한, 한도와 승인 기록을 지급 요청에 연결해야 한다. 디지털 지갑에서도 거래를 요청하는 주체와 서명을 승인하는 주체는 지갑 유형에 따라 달라진다. [Circle Wallets의 서명과 승인 모델](https://developers.circle.com/wallets/signing-and-authorization-models)

승인과 별도로 지급에 사용할 자금을 준비해야 한다. 은행 계좌에 있는 돈, 특정 체인의 지갑 잔액과 환매가 필요한 운용 자산은 사용 조건이 다르다. 달러로 청구됐다고 해서 모든 보유 자금을 즉시 달러 지급에 사용할 수 있는 것도 아니다. 자금의 위치와 통화, 실제 사용 가능 시점을 지급 기한에 맞춰 확인해야 한다.

### 1.4 지급 실행과 수취 확인: 송금 요청, 자산 이전과 상대방의 대금 수령은 어떻게 다른가?

지급 시스템에 요청을 보냈다는 것, 블록체인에서 자산 이전이 확정됐다는 것과 수취인이 필요한 형태로 대금을 받았다는 것은 서로 다른 상태다. 수취인이 은행 입금을 원한다면 온체인 이전 이후에도 지급 파트너의 처리와 현지 계좌 입금이 이어질 수 있다. Circle Payments Network도 스테이블코인 지급과 현지 법정화폐 지급을 구분한다. [Circle Payments Network](https://developers.circle.com/cpn)

따라서 업무 화면의 완료 표시가 무엇을 뜻하는지 정해야 한다. 요청 접수, 거래 제출, 실행 성공, 자산 이전 확정과 수취 완료를 같은 상태로 표시하면 담당자는 다음 업무를 언제 시작해도 되는지 알기 어렵다. 실패 후 다시 요청할 때에는 앞선 지급이 실제로 처리됐는지도 먼저 확인해야 한다.

### 1.5 기록 대조와 예외 처리: 청구서, 지급 기록과 잔액을 어떻게 맞추며 오류와 분쟁은 어떻게 처리하는가?

지급 이후에는 청구서의 금액, 승인 기록, 실제 지급과 잔액을 대조한다. 이 업무를 대사(reconciliation)라고 한다. 기업의 회계 장부, 지급 서비스의 고객별 장부와 실제 자금을 보관한 계정은 서로 다른 기록일 수 있으므로, 같은 시점과 같은 자금 범위를 비교해야 한다.

차이가 발견되면 미지급, 중복 지급, 수수료 차감, 환전 또는 다른 원인을 구분하고 담당자에게 전달해야 한다. 환불이나 분쟁도 별도 업무로 남는다. Synapse 파산관재인의 보고서는 서비스 장부와 실제 은행 자금의 대조가 왜 중요한지 보여주는 사례다. 지급 시스템의 설계는 이처럼 지급 전의 근거와 지급 후의 결과를 이어 설명할 수 있어야 한다. [Synapse 파산관재인 보고서](https://www.cravath.com/a/web/ogvbURUX4uGN9FJ178bssS/aafskj/20250206-485-chapter-11-trustees-fifteenth-status-report.pdf)

## 2. 지급 결제의 문제: 어느 업무에서 어떤 일이 실제로 발생하는가?

지급 문제를 모두 송금 속도의 문제로 설명하면 개선할 업무를 놓치기 쉽다. 잘못된 상대에게 지급한 사건, 승인과 다르게 실행된 사건, 판매자가 대금을 받지 못한 사건과 해외 수익을 이전하지 못한 상황은 발생 지점과 필요한 대응이 다르다. 아래 사례는 그 차이를 살펴보기 위해 배치했다.

### 2.1 지급 지시의 진위: 거래처가 보낸 요청과 실제 지급할 상대는 일치하는가?

KOTRA가 소개한 한국 기업의 무역대금 피해에는 거래처와 비슷한 이메일 주소나 해킹된 실제 이메일을 통해 계좌 변경 요청을 받은 경우가 있다. 기업은 거래처에 지급한다고 생각했지만 변경된 계좌로 송금했다. 여기서 문제는 자금 이전이 처리되지 않았다는 것이 아니라, 지급할 상대와 요청의 진위를 잘못 판단했다는 데 있다. [KOTRA의 피해 사례](https://dream.kotra.or.kr/kotranews/cms/news/actionKotraBoardDetail.do?CONTENTS_NO=2&MENU_ID=80&SITE_NO=3&bbsGbn=242&bbsSn=242&pNttSn=226395)

Toyota Boshoku도 위조된 지급 지시로 손실이 발생했다고 공시했다. 이는 거래처 변경 관리, 별도 연락을 통한 확인과 지급 승인 기록을 함께 검토해야 하는 문제를 보여준다. 지갑 주소와 서명이 기술적으로 유효하다는 사실만으로 그 주소가 올바른 거래처의 주소인지 확인할 수는 없다. [Toyota Boshoku 공시](https://www.toyota-boshoku.com/global/news/_assets/upload/190906e-1.pdf)

### 2.2 승인과 실행의 일치: 올바른 지급을 의도해도 왜 다른 금액이 나갈 수 있는가?

Citi의 Revlon 관련 오지급은 사기와 구분해야 한다. Citi는 이자를 지급하는 과정에서 대출 원금에 해당하는 돈도 잘못 지급한 일을 분기보고서에 기록했다. 의도한 업무와 실제 실행된 자금 이전이 달라진 사례다. [Citi 분기보고서](https://www.citigroup.com/rcs/citigpa/storage/public/q2003c.pdf)

제품 설계에서는 승인한 수취인과 금액이 실행 요청에도 그대로 적용되는지, 예외적인 처리에서 확인 절차가 유지되는지 살펴봐야 한다. 자동화는 잘못 구성된 요청도 빠르게 처리할 수 있으므로, 실행 속도와 실행의 정확성을 따로 평가해야 한다. 이미 이전된 돈을 어떻게 회수하거나 반환할지도 지급 이후의 업무로 남는다.

### 2.3 판매대금 정산: 고객의 결제 완료가 판매자의 대금 수령을 뜻하는가?

티몬과 위메프의 정산 지연은 고객의 구매 결제가 끝나도 판매자가 대금을 받지 못할 수 있음을 보여준다. 금융위원회는 피해 판매자에 대한 유동성 지원을 발표했다. 판매자가 필요한 시점에 정산금을 사용할 수 있는지는 결제 승인 화면과 다른 문제다. [금융위원회 발표](https://www.fsc.go.kr/no010101/82816)

판매자별 지급 의무, 정산 일정, 실제 보유 자금과 지급 완료를 연결해 확인해야 한다. 이전 기술이 개선되어도 중개자의 자금 부족이나 보관 및 정산 방식이 그대로라면 판매자의 위험은 남는다. 따라서 지급 기록을 투명하게 만드는 기능과 판매대금을 적절하게 관리하는 책임을 함께 설명해야 한다.

### 2.4 고객자금과 장부: 장부에 기록한 잔액은 실제 보관한 돈과 일치하는가?

Synapse 파산관재인의 보고서는 은행에 실제로 있는 자금과 Synapse 장부에 기록된 고객자금 사이의 부족분을 다룬다. 고객에게 표시한 잔액, 중개 서비스의 장부와 은행의 실제 보관금이 같은 상태를 가리키는지 대조해야 하는 문제다. [Synapse 관재인 보고서](https://www.cravath.com/a/web/ogvbURUX4uGN9FJ178bssS/aafskj/20250206-485-chapter-11-trustees-fifteenth-status-report.pdf)

영국 금융행위감독청의 발표도 도산한 결제회사들에서 발생한 고객자금 부족을 다룬다. 이는 여러 회사의 경험을 종합한 감독기관 자료이며 Synapse와 같은 개별 사건의 설명은 아니다. 두 자료는 고객별 자금의 귀속, 실제 보관금과 반환 책임을 지속적으로 확인해야 한다는 질문에 연결된다. [영국 금융행위감독청 발표](https://www.fca.org.uk/news/press-releases/payment-safeguarding-rules-changes)

블록체인의 잔액도 대사의 입력 자료가 될 수 있다. 다만 은행 계정이나 다른 서비스에 있는 돈까지 포함한 전체 고객자금을 설명하려면 해당 기록도 함께 확보해야 한다. 어느 시점의 어떤 자금을 비교하는지 불분명하면 숫자가 일치해도 올바른 대사라고 판단하기 어렵다.

### 2.5 국경을 넘는 지급: 현지 매출과 송금 요청이 있어도 왜 대금을 받지 못하는가?

KOTRA의 모잠비크 자료에는 셋톱박스, 정수기 필터와 진단장비를 수출한 한국 기업들의 대금 지연 사례가 있다. 자료가 설명하는 시중 달러 부족은 송금 요청 이후에도 지급할 통화를 확보하고 처리를 승인받는 조건이 남는다는 것을 보여준다. 이 자료의 기업들은 익명으로 소개되어 있다. [KOTRA의 수출기업 사례](https://dream.kotra.or.kr/kotranews/cms/news/actionKotraBoardDetail.do?CONTENTS_NO=1&MENU_ID=70&SITE_NO=3&bbsGbn=00&bbsSn=506%2C242%2C244%2C322%2C245%2C444%2C246%2C464%2C518%2C505%2C484&pEndDt=&pIndustCd=&pKbcCd=&pNatCd=&pNewsAll=&pNewsCd=242&pNewsCd=244&pNewsCd=245&pNewsCd=246&pNewsCd=322&pNewsCd=464&pNewsCd=484&pNewsCd=505&pNewsCd=506&pNewsCd=518&pNewsGbn=506%2C242%2C244%2C322%2C245%2C246%2C464%2C518%2C505%2C484&pNttSn=220388&pRegnCd=&pStartDt=&pageNo=12&pagePerCnt=10&recordCountPerPage=10&sSearchVal=&viewType=)

국제항공운송협회는 정부의 제한, 승인 절차와 외환 부족 때문에 항공사들이 현지 수익을 본국으로 보내지 못하는 상황을 발표했다. 이는 업계 전체를 다루는 자료다. 현지에서 매출을 얻은 것과 그 돈을 본국의 지급에 사용할 수 있게 된 것은 서로 다르다. [국제항공운송협회 발표](https://www.iata.org/en/pressroom/2025-releases/2025-12-10-01/)

새로운 지급 자산이나 환전 기능을 검토할 때에도 필요한 통화의 공급, 수취 방식, 금융기관의 승인과 현지 제도 조건을 함께 살펴봐야 한다. 기술적으로 자산을 옮길 수 있다는 설명이 이러한 조건까지 해결했다는 뜻이 되지는 않는다.

### 2.6 문제의 구분: 자금 이동 기술로 개선할 부분과 계약, 운영 및 제도에서 처리할 부분은 무엇인가?

위 사례들은 개선할 업무를 알려주는 근거다. 지급 지시의 진위에는 거래처 확인이, 오지급에는 승인과 실행의 일치가, 고객자금 문제에는 보관 책임과 대사가 중요하다. 국제 지급에는 자산 이동 외에도 통화 공급과 수취 조건이 영향을 준다.

이 구분에 따라 자금 이전, 교환과 기록을 기술로 처리할 부분을 찾고, 그 앞뒤의 확인과 운영을 앱에 어떻게 연결할지 검토할 수 있다. 특정 사고가 존재한다는 사실만으로 Circle, Arc 또는 AI가 그 사고를 예방할 수 있다고 결론 내리지는 않는다. 다음 장에서는 Circle이 어떤 기능을 연결하려는지 먼저 살펴본다.

## 3. Circle의 해결 방향: 디지털 자산에 대한 접근, 보관, 교환과 이동을 어떻게 연결하려는가?

Circle은 제품 비전에서 기업과 금융기관이 디지털 자산에 접근하고, 보관하고, 교환하고, 이동할 수 있는 기능을 연결하려는 방향을 제시한다. 이를 인터넷 금융 플랫폼이라는 관점에서 설명한다. 이 글은 그 넓은 목표 가운데 기업 지급 결제에 해당하는 업무를 살펴본다. [Circle의 제품 비전](https://www.circle.com/blog/building-the-internet-financial-system-circles-product-vision-for-2026)

### 3.1 Circle의 목표: 디지털 자산과 인터넷 금융 플랫폼은 어떤 업무 변화를 지향하는가?

기업이 디지털 자산을 지급에 활용하려면 자산을 얻는 일, 보관하고 승인하는 일, 다른 통화로 교환하는 일과 상대에게 전달하는 일이 연결되어야 한다. Circle의 제품 비전은 이러한 기능을 하나의 플랫폼에서 조합할 수 있게 하는 방향으로 읽을 수 있다.

기업 관점에서는 스테이블코인을 보유하는 데서 업무가 끝나지 않는다. 기존 은행 자금으로 지급 자산을 준비하고, 승인된 지급을 실행하며, 상대가 원하는 형태로 대금을 받을 때까지 관리해야 한다. 이처럼 자산과 금융 기능을 연결해 실제 업무에 사용할 수 있게 하는 것이 제품 구성을 이해하는 출발점이다.

### 3.2 기업 업무의 변화: 지급, 외환과 자금 관리를 어떻게 연결하려는가?

국제 지급에는 사용할 통화와 자금의 위치가 중요하다. 환전에는 견적과 유동성, 교환 결제가 필요하다. 자금 관리에는 예정 지급과 사용 가능 잔액, 운용 자금의 회수 시점이 영향을 준다. Circle은 제품 비전의 애플리케이션 설명에서 지급, 외환과 자금 관리에 이러한 기능을 연결하려는 방향을 제시한다. [Circle의 애플리케이션 방향](https://www.circle.com/blog/building-the-internet-financial-system-circles-product-vision-for-2026)

이 방향을 기업 지급 결제에 적용하면 질문은 구체적이 된다. 필요한 돈을 어디서 준비할지, 지급 전에 환전할지, 어떤 경로로 상대에게 전달할지와 각 처리 결과를 어떻게 확인할지를 함께 설계해야 한다. 앞선 실제 사례는 이 연결에서 확인해야 할 업무를 알려주지만, 회사가 각 사건을 직접 해결했다고 판단하는 근거는 아니다.

### 3.3 제품 구성: 개발 기반, 디지털 자산과 금융 애플리케이션은 각각 무엇을 제공하는가?

Circle의 제품 비전은 자체 구성으로 Arc와 개발 기반(Arc and Developer Infrastructure), 디지털 자산과 서비스(Digital Assets and Services), 애플리케이션(Applications)을 제시한다. 개발 기반은 앱이 자산과 금융 기능을 사용할 환경과 도구를 제공하고, 자산과 서비스는 지급 및 운용에 사용할 자산과 연결 기능을 제공한다. 애플리케이션은 이를 지급, 외환과 자금 관리 같은 업무에 활용한다. [Circle이 제시한 제품 구성](https://www.circle.com/blog/building-the-internet-financial-system-circles-product-vision-for-2026)

이후 장에서 사용하는 지급 자산, 승인, 환전과 수취 등의 구분은 기업 업무를 설명하기 위해 이 글에서 정한 것이다. Circle의 공식 분류와 함께 보되, 자산과 네트워크, 금융 서비스와 개발 도구를 구별해서 읽어야 한다. Circle은 여러 블록체인 사이의 연결과 Arc의 연계를 함께 발전시키려는 방향도 설명하므로, 제품 목록 전체를 Arc 전용 상품으로 이해해서는 안 된다.

### 3.4 개발자의 과제: 제공된 기능 위에서 어떤 상거래와 지급 업무를 완성해야 하는가?

Team Arc의 개발 제안에는 상거래 계약의 단계별 지급, 분쟁 처리, 국제 급여와 합의한 결과를 확인한 뒤 지급하는 서비스 등이 등장한다. 이는 자산 이전 기능에 계약과 업무 상태를 연결하라는 제안으로 읽을 수 있다. [Team Arc의 빌더 제안](https://www.arc.io/blog/the-unfinished-business-of-finance-machine-commerce-and-global-money)

예를 들어 외주 대금을 지급하는 앱은 지갑과 계약을 연결하는 것 외에도 납품 증거, 검수 권한, 지급 조건과 이의 제기를 처리해야 한다. AI가 문서를 해석하도록 구성한다면 어떤 판단을 보조하고 어떤 결정을 사람이 승인할지도 정해야 한다. 따라서 기업 지급 결제를 Arc + AI로 개선한다는 방향은, Circle이 제공하는 기능 위에서 상거래와 지급 업무를 완성하려는 개발 가설로 구체화할 수 있다.

## 4. Circle 제품: 각 제품은 기업의 어떤 업무를 맡는가?

기업 업무를 기준으로 제품을 읽으면 같은 목록에 있는 이름들이 서로 다른 종류라는 것을 알 수 있다. USDC는 지급에 사용할 자산이고, Wallets는 지급 권한과 거래 요청을 다루며, CPN은 수취인까지의 지급을 연결한다. 아래 설명 순서는 이러한 차이를 이해하기 위해 정한 것이다.

### 4.1 지급할 자산: USDC와 EURC는 어떤 통화의 대금을 다루는가?

USDC는 달러 기준, EURC는 유로 기준으로 지급과 자금 이동에 사용하는 스테이블코인이다. 스테이블코인은 특정 기준 자산의 가치를 따라가도록 설계한 디지털 자산을 말한다. 기업 지급에서는 청구 통화와 지급 자산을 맞추거나 필요한 환전 경로를 검토하는 출발점이 된다. [Circle의 디지털 자산 설명](https://www.circle.com/blog/building-the-internet-financial-system-circles-product-vision-for-2026)

이때 토큰을 이전한 것과 수취인이 은행에서 사용할 돈을 확보한 것은 구분한다. 수취인이 해당 자산을 받아 사용할 수 있는지, 어떤 체인에서 보유하는지와 법정화폐로 전환할 경로가 중요하다. 지급 자산의 선택은 보관, 전환과 수취 조건에 연결된다.

### 4.2 은행 자금과의 연결: Circle Mint는 법정화폐와 스테이블코인을 어떻게 연결하는가?

Circle Mint는 기관이 법정화폐를 USDC나 EURC로 전환하고 상환하는 접점을 제공한다. 기업 또는 금융기관이 은행 자금으로 온체인 지급 자산을 준비하거나, 보유한 스테이블코인을 은행 자금으로 회수할 때 연결되는 역할이다. [Circle Mint의 기관용 기능](https://www.circle.com/blog/circle-mint-delivers-a-powerful-institutional-onramp-to-usdc-and-eurc)

Mint를 기업 앱의 모든 사용자에게 동일하게 제공되는 개인용 환전 창구로 이해하면 이용 조건을 놓칠 수 있다. 기관 계정, 지역, 은행 처리와 상품별 전환 경로에 조건이 있다. 제품을 조합할 때에는 자금을 전환하는 주체와 필요한 계정, 처리 상태를 앱의 지급 계획에 연결해야 한다.

### 4.3 지급 승인과 실행 요청: Circle Wallets는 요청과 서명 승인을 어떻게 구분하는가?

Circle Wallets는 지갑의 키 관리와 거래 요청, 서명 승인을 다룬다. 지갑 유형에 따라 누가 거래를 요청하고 누가 서명을 승인하는지가 달라진다. 기업 앱에서는 재무 담당자, 사용자와 자동화 서비스 가운데 누가 어떤 지급을 허용할지 이 모델에 맞춰 설계한다. [Wallets의 서명과 승인 모델](https://developers.circle.com/wallets/signing-and-authorization-models)

서명은 거래 실행을 허용하는 기술적 행위다. 계약상 지급 의무가 있는지, 계좌 변경 요청이 진짜인지 또는 납품이 완료됐는지는 별도 자료로 판단해야 한다. AI가 지급을 제안하더라도 승인된 대상과 금액, 한도를 Wallets 및 앱의 정책에 어떻게 반영할지 명시해야 한다.

### 4.4 체인 사이의 자금 이동: CCTP와 Gateway는 어떤 업무를 서로 다르게 맡는가?

CCTP(Cross-Chain Transfer Protocol)는 출발 체인의 USDC를 소각하고 목적지 체인에서 발행하는 방식으로 체인 간 이전을 수행한다. 특정 체인에 있는 자금을 다른 체인에서 사용할 때 연결되는 기능이다. 출발과 목적지의 지원 여부, 이전 상태와 최종 사용 가능 시점을 확인해야 한다. [CCTP 공식 설명](https://developers.circle.com/cctp)

Gateway는 예치한 USDC를 지원 체인에서 사용할 통합 잔액으로 다룬다. 앱이 여러 체인에 분산된 지급 자금을 관리할 때 잔액과 사용 경로를 연결하는 역할이다. 통합 잔액은 선행 예치와 지원 체인 등의 조건을 가진다. 기업의 모든 은행 계좌와 지갑 잔액이 자동으로 포함되는 전체 회계 장부와는 다르다. [Gateway 공식 설명](https://developers.circle.com/gateway)

따라서 CCTP의 체인 간 이전과 Gateway의 예치 기반 잔액 사용을 같은 기능으로 설명하면 안 된다. 두 제품 모두 은행 수취인에게 현지 통화로 지급하는 네트워크의 역할과도 구별된다.

### 4.5 환전과 교환 결제: StableFX는 견적과 자산 교환을 어떻게 연결하는가?

StableFX는 기관의 환전 견적과 Arc상의 자산 교환 결제를 연결하는 기능이다. 공식 설명은 견적을 얻고 양쪽 자산을 조건에 맞춰 교환하는 과정을 다룬다. 견적과 계약 실행을 연결한다는 점에서, 기업 앱의 환전 업무와 Arc의 실행 기록이 만나는 제품이다. [StableFX 공식 설명](https://developers.circle.com/stablefx)

앱은 필요한 통화와 금액, 견적, 지급할 자금과 교환 결과를 관리해야 한다. 거래를 구성하려면 접근 승인, 지원 자산과 유동성 등의 조건이 충족되어야 한다. 이러한 교환 기능을 제공한다는 사실이 특정 국가의 외환 부족이나 송금 제한까지 해결한다는 뜻은 아니다.

### 4.6 수취인까지의 지급: CPN의 지급 상품과 Managed Payments는 무엇을 맡는가?

CPN(Circle Payments Network)은 금융기관과 지급 파트너를 연결하는 Circle의 지급 네트워크다. 공식 문서는 스테이블코인 지급, 현지 법정화폐 지급과 Managed Payments를 구분한다. 기업이 온체인 자금 이동에서 수취인의 지급 방식까지 연결할 때 어떤 상품과 파트너가 처리하는지 살펴볼 수 있다. [CPN의 상품과 운영 방식](https://developers.circle.com/cpn)

Managed Payments는 자산 보관, 준법 처리와 온체인 운영을 Circle이 맡는 방식으로 설명된다. 고객별 하위 계정과 기록 및 보고도 업무에 연결된다. 기업 앱이 모든 온체인 운영을 직접 수행하는 구성과 책임의 배분이 다르다. [Managed Payments](https://developers.circle.com/cpn/managed-payments)

이용 계약과 고객 확인, 국가와 통화별 경로가 실제 지급을 좌우한다. 어떤 방식이든 수취인이 대금을 받았는지와 서비스 장부가 실제 자금과 맞는지는 확인해야 한다. CPN의 네트워크 조정과 Arc의 거래 확정을 같은 완료 상태로 표시해서는 안 된다.

### 4.7 자금 운용과 파트너 자산: USYC와 xReserve는 지급 자산과 어떻게 다른가?

Circle의 제품 비전에서 USYC는 자금 운용에 연결되는 토큰화 자산으로 소개된다. 기업 앱에서는 지급을 기다리는 자금의 운용과 회수를 검토할 때 관련된다. 지급할 때 곧바로 사용할 잔액과 운용 자산을 구분하고, 운용 위험, 환매 조건과 이용 자격을 지급 계획에 반영해야 한다. [Circle의 USYC 설명](https://www.circle.com/blog/building-the-internet-financial-system-circles-product-vision-for-2026)

xReserve는 USDC 준비금과 파트너 스테이블코인 발행을 연결하는 기능이다. 다른 생태계의 자산과 USDC를 연결할 때 관련되며, 일반 기업의 모든 지급에서 반드시 사용하는 제품은 아니다. 파트너가 발행한 자산의 책임과 상환 조건을 함께 확인해야 한다. USYC의 운용 목적, xReserve의 발행 및 연결 목적과 USDC의 지급 목적은 각각 다르다. [Circle의 xReserve 설명](https://www.circle.com/blog/building-the-internet-financial-system-circles-product-vision-for-2026)

### 4.8 앱과 에이전트의 구현: App Kits, Agent Stack과 Arc Studio는 어떤 개발 작업을 돕는가?

App Kits는 지급, 체인 간 이전, 교환, 잔액과 자금 운용 등의 기능을 앱에서 조합하는 개발 도구다. 앱은 해당 Kit와 그 아래 서비스의 지원 조건에 맞춰 업무를 구현한다. 지급 기능과 운용 또는 차입 기능을 같은 금융 행위로 취급하지 않고, 필요한 기능만 업무에 연결할 수 있다. [App Kits](https://docs.arc.io/app-kit)

Agent Stack은 정책 아래에서 에이전트의 지갑, 서비스 탐색과 지급을 연결하는 구성이다. Wallets와 Gateway Nanopayments 등이 관련된다. Nanopayments는 작은 서비스 사용 단위의 USDC 지급을 연결하는 기능으로 소개된다. 에이전트가 유료 서비스를 사용하는 업무와 지급 권한을 함께 구성할 수 있지만, 청구서의 진위와 지급 상대에 대한 AI 판단은 따로 검증해야 한다. [Circle Agent Stack](https://www.circle.com/blog/introducing-circle-agent-stack-financial-infrastructure-for-the-agentic-economy)

Arc Studio는 자연어로 앱과 계약 코드를 작성하고 미리보기와 테스트넷 배포를 돕는 도구다. 테스트넷은 실제 자금 사용에 앞서 동작을 시험하는 네트워크다. 공식 설명의 테스트넷 배포 범위와 실제 사업용 배포 및 운영 준비를 구분해야 한다. 코드를 생성하고 배포하는 도구를 사용해도 지급 조건과 오류 처리가 올바르게 구현됐는지는 확인해야 한다. [Arc Studio](https://docs.arc.io/ai/arc-studio)

## 5. Arc의 역할: 금융 업무의 실행과 기록을 어떤 공통 기반에서 처리하려는가?

Circle 제품은 각각 자산, 승인, 이전, 교환과 수취 등의 업무를 맡는다. Arc는 그중 자산 이전과 계약 실행 결과를 처리하고 기록을 확정하는 네트워크다. Circle은 제품 비전에서 Arc를 자사 애플리케이션의 조정을 위한 기반으로 발전시키려는 방향을 설명한다. [Circle의 제품 비전](https://www.circle.com/blog/building-the-internet-financial-system-circles-product-vision-for-2026)

### 5.1 공통 기반의 필요성: Circle은 자산, 계약과 결제 결과를 왜 연결하려는가?

조건부 지급을 생각하면 자산 이전과 업무 조건의 관계가 드러난다. 예산이 승인되고 검수가 끝나면 대금을 지급하려는 앱은 어떤 조건에서 실행을 허용하고, 실행 뒤 무엇을 기록할지 정해야 한다. 환전에서는 양쪽 자산의 교환 조건과 결과를 함께 다루어야 한다.

Circle이 제시한 방향은 이러한 자산과 금융 기능을 공통 기반에서 연결하는 것이다. 기존 제품이 맡는 은행 자금 전환, 지갑 승인과 수취 경로에 계약 실행과 기록을 조합할 수 있게 하려는 방향으로 이해할 수 있다. 이것은 제품 간 연결을 발전시키려는 목표이며, 모든 상품의 연동이 완료됐다는 평가와는 구별된다. [Circle의 Arc 연계 방향](https://www.circle.com/blog/building-the-internet-financial-system-circles-product-vision-for-2026)

### 5.2 Arc의 구성: 자산 이전과 계약 실행 결과를 무엇이 처리하고 기록하는가?

공식 문서는 Arc를 스테이블코인 금융 앱을 위한 독립적인 블록체인(Layer 1)으로 소개한다. 이더리움 가상머신(EVM, Ethereum Virtual Machine)에서 계약 코드를 실행하고, 네트워크의 합의를 통해 거래 기록을 확정하는 역할을 설명한다. 앱의 요청, 실행 결과와 확정된 기록을 연결하는 기반이다. [Arc Network](https://docs.arc.io/arc-chain), [시스템 구성](https://docs.arc.io/arc/concepts/system-overview)

Arc라는 네트워크, 그 위에서 이전하는 USDC 같은 자산과 StableFX 같은 금융 서비스는 종류가 다르다. 네트워크는 실행과 기록을 처리하고, 자산은 지급하거나 교환할 대상을 나타내며, 서비스는 해당 기능을 업무에 사용할 절차를 제공한다. 이 구분을 유지해야 앱의 각 처리 결과가 어디서 발생하는지 이해할 수 있다.

### 5.3 지급 비용: USDC로 거래 수수료를 내는 방식은 어떤 관리 업무를 줄이려는가?

Arc의 공식 설명은 USDC로 거래 수수료를 내는 스테이블코인 기반 모델을 제시한다. 지급에 사용할 자산과 별도의 가스(gas, 거래 실행 수수료) 자산을 각각 준비해야 하는 관리 업무를 줄이려는 설계다. 달러 기준으로 수수료를 계산하는 방식은 기업의 비용 관리와도 연결된다. [스테이블코인 기반 모델](https://docs.arc.io/arc/concepts/stablecoin-native-model)

수수료 설계는 비용의 급격한 변동을 완화하려는 구조도 설명한다. 그러나 거래 수수료가 있다는 점과 자금 전환, 환전 및 수취 경로에서 다른 비용이 발생할 수 있다는 점은 남는다. 기업의 전체 지급 비용을 평가할 때에는 해당 업무에 필요한 비용을 함께 계산해야 한다. [Arc의 수수료 설계](https://docs.arc.io/arc/concepts/stable-fee-design)

### 5.4 거래 확정과 업무 완료: 어느 기록을 확인하면 다음 처리를 시작할 수 있는가?

확정적 최종성(deterministic finality)은 네트워크의 합의 조건 아래에서 거래 기록의 확정을 다루는 개념이다. 기업 앱에서는 기록이 확정된 뒤 해당 결과를 바탕으로 후속 처리를 시작하는 기준이 된다. [Arc의 거래 확정 설명](https://docs.arc.io/arc/concepts/deterministic-finality)

확정된 기록 안에서도 계약의 호출 결과를 확인해야 한다. 또한 온체인 자산 이전이 성공했다고 해서 납품이 검수됐거나 수취인의 은행 입금이 끝났다는 뜻은 아니다. 앱은 네트워크에서 확정할 상태와 외부에서 확인할 업무 상태를 각각 관리해야 한다. 그래야 자금 이전 완료와 상거래 완료를 혼동하지 않는다.

### 5.5 기업 데이터와 운영 권한: 어떤 정보를 공개하며 누가 거래 기록을 확정하는가?

급여, 거래처와 계약 조건을 다루는 앱은 공개할 정보와 접근을 제한할 정보를 정해야 한다. Arc의 공식 문서는 선택적으로 데이터를 비공개로 처리하는 설계(opt-in privacy)를 도입 계획으로 설명한다. 앱은 이 계획과 실제로 사용할 수 있는 기능을 구분해 데이터의 공개 범위를 설계해야 한다. [Arc의 비공개 실행 설계](https://docs.arc.io/arc/concepts/opt-in-privacy)

네트워크 운영 권한도 별도의 문제다. Arc Network 설명은 개발자의 앱 접근과 허가제로 운영하는 검증자 참여를 구분한다. 앱을 개발할 수 있다는 사실과 거래 기록을 확정하는 운영에 참여할 수 있다는 사실이 같지는 않다. 기업은 어떤 운영 주체와 합의 조건을 신뢰하는지까지 제품 구성에 포함해 이해해야 한다. [Arc Network의 참여 구조](https://docs.arc.io/arc-chain)

### 5.6 Circle 제품과의 연결: Arc의 기록은 환전, 다른 체인의 자금과 수취인 지급에 어떻게 이어지는가?

StableFX의 공식 설명은 Arc에서 교환 결제를 처리하는 연결을 보여준다. 반면 CCTP와 Gateway는 지원되는 체인 사이의 자금 이전 및 잔액 사용, Mint는 은행 자금의 전환, CPN은 수취인까지의 지급에 관련된다. 제품을 조합할 때에는 각 기능의 지원 조건과 상태를 서로 연결해야 한다. [StableFX](https://developers.circle.com/stablefx), [CCTP](https://developers.circle.com/cctp), [Gateway](https://developers.circle.com/gateway), [CPN](https://developers.circle.com/cpn)

기업 앱은 지급의 목적과 경로에 따라 필요한 제품을 선택한다. 같은 체인의 자산을 직접 지급하는 업무에 다른 체인 이전이 항상 필요한 것은 아니며, 은행 수취인을 위한 경로는 별도로 구성해야 한다. 따라서 Arc를 공통 실행 기반으로 검토하되 제품 전체를 하나의 고정된 실행 순서로 그려서는 안 된다.

### 5.7 앱이 완성할 기업 업무: 거래처 확인, 지급 조건과 예외 처리는 누가 맡는가?

앱은 기업의 문서와 실제 업무 상태를 지급 요청에 연결해야 한다. 거래처 변경 요청을 검토하고, 승인된 조건을 실행에 적용하며, 지급 상태와 장부를 대조하고, 실패나 분쟁을 담당자에게 전달하는 일이다. Team Arc의 조건부 지급과 분쟁 처리 제안도 이러한 응용 업무에 연결된다. [Team Arc의 개발 제안](https://www.arc.io/blog/the-unfinished-business-of-finance-machine-commerce-and-global-money)

AI는 문서를 해석하고 기록 차이를 찾거나 담당자의 판단을 보조하는 후보가 된다. 실행할 권한과 한도는 명시적인 정책으로 제한하고, 체인 밖의 사실을 누가 확인하는지 정해야 한다. Arc가 실행과 기록을 맡는다는 설명에서 기업의 모든 판단과 운영 책임이 자동으로 해결된다는 결론이 나오지는 않는다.

## 6. Circle과 Arc의 조합: 각 제품의 업무와 역할은 어떤 문제의 개선으로 이어지는가?

개별 제품을 이해한 다음에는 기업 업무에서 어떻게 함께 사용할지 검토할 수 있다. 아래 조합은 공식 제품 설명과 개발 제안을 기업 업무에 연결한 이 글의 설계 가설이다. 하나의 통합 상품이나 검증된 배포 구성으로 소개하는 것은 아니다.

### 6.1 제품별 역할표: 담당 업무, Arc와의 관계, 연결 제품과 기대 효과를 어떻게 정리하는가?

표의 한 행은 제품 또는 명시한 개발 기능 하나다. 제품의 역할과 기대 효과를 나란히 두되, 효과를 얻기 위해 필요한 조건도 함께 적었다. 자산과 금융 서비스, 네트워크와 개발 도구를 구분해 읽으면 실제 앱이 연결할 범위를 정하기 쉽다.

| 제품 | 담당 업무와 역할 | Arc 및 다른 제품과의 관계 | 개선을 기대하는 문제와 조건 | 공개 근거 |
|---|---|---|---|---|
| Arc | 자산 이전과 계약 실행 결과를 처리하고 기록을 확정한다. | 거래 요청, 계약 실행과 StableFX의 교환 결제를 연결하는 공통 실행 환경이다. | 실행 결과의 확인에 쓰인다. 외부 납품과 은행 수취는 별도로 확인한다. | [Arc](https://docs.arc.io/arc-chain) |
| USDC | 달러 기준 지급 자산이며 Arc의 거래 수수료 자산이다. | Mint의 발행과 상환, Wallets의 지급 및 Arc 실행에 연결한다. | 지급 자산과 수수료 자산의 관리 업무를 줄이려는 구성이다. 수취 통화와 상환 조건은 남는다. | [스테이블코인 모델](https://docs.arc.io/arc/concepts/stablecoin-native-model) |
| EURC | 유로 기준 지급 자산이다. | 유로 청구와 이용 가능한 교환 및 상환 경로에 연결한다. | 청구 통화와 지급 통화를 맞추는 문제다. 체인과 교환 경로별 지원을 확인한다. | [제품 비전](https://www.circle.com/blog/building-the-internet-financial-system-circles-product-vision-for-2026) |
| Circle Mint | 은행 자금과 스테이블코인의 발행 및 상환을 연결한다. | 지급 자금 준비와 은행 자금으로의 회수에 관련된다. | 법정화폐와 온체인 잔액의 전환 문제다. 기관 계정과 은행 처리 조건이 있다. | [Mint](https://www.circle.com/blog/circle-mint-delivers-a-powerful-institutional-onramp-to-usdc-and-eurc) |
| Circle Wallets | 거래 요청, 서명 승인과 키 관리를 다룬다. | 앱의 지급 정책과 거래 제출 및 상태 확인을 연결한다. | 권한과 승인된 요청의 실행을 관리한다. 상대방과 문서의 진위 확인은 별도 업무다. | [서명과 승인](https://developers.circle.com/wallets/signing-and-authorization-models) |
| CCTP | 소각과 발행으로 체인 간 USDC 이전을 처리한다. | 지급에 사용할 자금을 다른 지원 체인으로 옮긴다. | 체인별 자금 배치 문제다. 양쪽 지원과 이전 완료를 확인한다. | [CCTP](https://developers.circle.com/cctp) |
| Gateway | 선행 예치한 USDC를 지원 체인의 통합 잔액으로 다룬다. | 자금 조회, 사용 경로와 에이전트 지급에 연결한다. | 분산된 사용 가능 자금의 관리 문제다. 예치와 출금 조건을 가진다. | [Gateway](https://developers.circle.com/gateway) |
| StableFX | 기관 환전의 견적과 조건부 자산 교환을 연결한다. | Arc의 계약이 교환 결제를 처리하고 앱이 견적과 결과를 관리한다. | 자산 교환에서 상대방 위험을 줄이려는 기능이다. 접근 승인과 유동성이 필요하다. | [StableFX](https://developers.circle.com/stablefx) |
| CPN | 스테이블코인 지급과 파트너의 현지 법정화폐 지급을 연결한다. | 온체인 자금에서 수취인이 원하는 지급 방식으로 이어진다. | 국제 지급과 수취 상태의 관리 문제다. 국가, 통화와 파트너의 지원 조건이 있다. | [CPN](https://developers.circle.com/cpn) |
| Managed Payments | 보관, 준법 처리, 온체인 운영과 고객별 기록을 제공한다. | CPN 지급 업무를 서비스 운영 방식에 연결한다. | 지급 운영 및 기록 관리 업무를 줄이려는 구성이다. 실제 자금 대사와 계약상 책임은 확인한다. | [Managed Payments](https://developers.circle.com/cpn/managed-payments) |
| USYC | 지급 자산과 구분되는 토큰화 운용 자산이다. | 대기 자금의 운용과 지급을 위한 회수에 관련된다. | 유휴 자금과 지급 시점의 관리 문제다. 운용 위험과 환매 및 이용 조건을 확인한다. | [제품 비전](https://www.circle.com/blog/building-the-internet-financial-system-circles-product-vision-for-2026), [자금 관리 제안](https://tameion.thecanteenapp.com/) |
| xReserve | USDC 준비금과 파트너 자산의 발행을 연결한다. | 파트너 스테이블코인과 USDC를 연결하는 생태계 구성이다. | 자산 발행과 연결의 문제다. 파트너의 발행 및 상환 책임을 확인한다. | [제품 비전](https://www.circle.com/blog/building-the-internet-financial-system-circles-product-vision-for-2026) |
| App Kits | 지급, 이전, 교환과 잔액 등의 기능을 앱에서 조합한다. | 각 Kit를 아래의 서비스와 연결한다. | 여러 기능을 연동하는 개발 업무다. 개별 기능의 지원 조건을 확인한다. | [App Kits](https://docs.arc.io/app-kit) |
| Agent Stack | 정책 아래 에이전트의 지갑, 서비스 탐색과 지급을 연결한다. | Wallets 및 Gateway Nanopayments 등의 기능을 활용한다. | 유료 서비스 사용과 지급 권한의 관리 문제다. AI 판단의 정확성은 따로 확인한다. | [Agent Stack](https://www.circle.com/blog/introducing-circle-agent-stack-financial-infrastructure-for-the-agentic-economy) |
| Arc Studio | 자연어 기반 코드 작성, 미리보기와 테스트넷 배포를 돕는다. | Arc와 USDC를 사용하는 시제품을 구현하고 코드를 내보낸다. | 시제품 개발 업무다. 테스트넷 배포와 사업용 운영 준비를 구분한다. | [Arc Studio](https://docs.arc.io/ai/arc-studio) |
| Contracts | Tameion 주최자가 계약 생성과 관리 기능으로 소개한다. | 예산, 승인 임계값과 단계별 지급의 제한에 연결하는 예시다. | 지급 조건의 집행 문제다. 주최자의 도구 소개와 계약 코드의 실제 동작을 구분한다. | [주최자 기능 소개](https://tameion.thecanteenapp.com/) |
| Paymaster | Tameion 주최자가 이용자의 수수료를 대신 내는 기능으로 소개한다. | 내부 이체와 판매자 지급의 수수료 준비를 줄이는 예시다. | 수수료 준비 문제다. 대납 비용과 지원 지갑 및 체인을 확인한다. | [주최자 기능 소개](https://tameion.thecanteenapp.com/) |

### 6.2 업무별 제품 조합: 자금 준비부터 승인, 실행, 수취 확인과 대사까지 어떻게 연결하는가?

해외 공급업체 대금 지급을 예로 들어 기능의 조합을 생각할 수 있다. 은행 자금으로 지급 자산을 준비한다면 Mint가 관련된다. 다른 체인의 자금이 필요하면 지원되는 CCTP 이전이나 Gateway 잔액 사용을 검토한다. 통화를 바꿔야 한다면 사용할 수 있는 StableFX 경로와 견적을 확인한다. 앱의 승인 정책과 Wallets를 통해 실행을 허용하고, Arc의 거래 결과를 지급 기록에 연결한다.

수취인이 은행 입금을 원한다면 해당 경로를 처리하는 CPN 상품과 파트너가 관련된다. 마지막으로 청구서, 승인, 자산 이전, 수취 결과와 잔액을 대조한다. 이는 기능별로 조합을 검토하는 예이며, 실제 구성은 제품별 지원 체인, 서비스 접근과 지급 경로가 확인된 뒤에 정한다. 이미 자산을 보유했거나 환전이 필요 없는 지급에는 일부 단계가 줄어들 수 있다.

### 6.3 조합의 조건과 한계: 어떤 연결이 제공되며 어떤 연결은 앱과 운영 절차로 만들어야 하는가?

제품을 연결하려면 자산과 체인 지원뿐 아니라 계정, 서비스 접근, 거래 상태와 운영 책임이 맞아야 한다. 한 제품이 거래를 완료했다고 표시하는 시점과 다음 제품이 자금을 사용할 수 있는 시점이 같지 않을 수 있다. 앱은 이 상태들을 추적하고 실패 및 재시도를 처리해야 한다. [Wallets의 거래 처리](https://developers.circle.com/wallets/signing-and-authorization-models), [CPN](https://developers.circle.com/cpn)

계약과 청구서의 연결, 거래처 변경 승인, 납품 증거, 장부 대사와 분쟁 처리는 기업의 자료와 운영에 맞춰 구현해야 한다. 공식 기능은 필요한 일부 처리를 제공하고, 기업 앱은 그 처리와 실제 업무 조건을 이어준다. Arc의 비공개 실행처럼 계획으로 제시된 기능도 실제 이용 범위와 구분한다. [Arc의 비공개 실행 설계](https://docs.arc.io/arc/concepts/opt-in-privacy)

### 6.4 개발 방향의 기준: Arc 사용과 Circle 제품 연결이 기업의 어떤 업무를 개선하는가?

개발 방향은 어떤 기업이 무엇을 확인하고 지급하려는지, 지금 어떤 문제가 생기는지와 제품 조합이 어느 업무를 개선하는지로 설명할 수 있어야 한다. 처리 단계가 줄어드는지, 승인과 실제 지급을 대조하기 쉬워지는지 또는 담당자가 예외를 더 빨리 발견할 수 있는지 등을 검토할 수 있다. 이는 앞으로 실제 업무에서 확인할 효과다.

Circle과 Arc를 함께 이해하는 이유도 이 연결에 있다. Arc는 실행과 기록의 기반으로 검토하고, Circle 제품은 자산 준비, 승인, 이전, 환전과 수취의 해당 역할에 연결한다. 앱은 그 조합을 계약과 기업 업무에 맞게 완성한다. 이어지는 프로그램 설명에서는 이런 개발을 배우고 구현하고 지원받는 활동이 각각 무엇을 요구하는지 살펴본다.

## 7. 참여 프로그램: 프로그램별 목적, 요구사항과 지원 내용은 무엇인가?

Arc House의 행사 목록에는 개발 경쟁, 지원금 안내, 교육, 상담과 발표 등이 함께 올라온다. 같은 해커톤의 시작 행사와 결과 발표가 별도 카드로 나타나기도 한다. 이 글에서는 공고의 목적을 비교하기 위해 활동을 구분했다. 아래는 공개된 회차와 프로그램을 이해하는 자료이며, 현재 모집 중인 목록이나 개인의 참가 자격 판정은 아니다. [Arc House 공식 행사 목록](https://community.arc.io/public/events)

### 7.1 개발 경쟁: 해커톤과 후원 상금은 어떤 제품과 제출 증거를 요구하는가?

해커톤은 정해진 회차에서 제품을 개발하고 결과물을 제출하는 활동이다. 후원 상금은 본대회 규칙에 더해 특정 도구와 분야의 요구를 적용할 수 있다. 신청 승인, 팀 구성, 작품 제출과 후원 상금 심사를 구분해야 한다. 표의 조건은 명시한 공고에 해당하며 모든 Arc 행사에 공통으로 적용되지 않는다. 메인넷은 실제 자산과 운영을 다루는 네트워크를 말하며, 시험용 자산으로 동작을 확인하는 테스트넷과 구분한다.

| 대회 또는 회차 | 개발 목적 | 요구사항과 참여 조건 | 지원 내용과 공개 출처 |
|---|---|---|---|
| Canteen Agora의 결과 발표 | Arc에서 USDC로 정산하는 시장 및 거래 관련 AI 에이전트의 구현 경험을 공유한다. | Spotlight 공고는 선정팀의 발표를 다룬다. 신규 참가 조건은 해당 해커톤의 규칙으로 확인한다. | 구현 시연, 공개 소스 예시와 개발 경험을 제공한다. [Agora Spotlight](https://community.arc.io/public/events/arc-x-canteen-agora-hackathon-builder-spotlight-00mi9xlatf) |
| Canteen Lepton | 지급과 수취, 서비스 대금을 처리하는 에이전트를 개발한다. | 온라인 가입 신청, 공개 코드 저장소와 녹화 시연을 요구한다. 개발 제안(Requests for Builders)과 필수 경쟁 분야를 구분하며 실제 사용과 행사 중 추가한 개발 결과를 설명한다. | 상금, 멘토링, 개발 자료와 주최자의 연구 및 관계망 접근을 안내한다. [Lepton](https://lepton.thecanteenapp.com/) |
| Canteen Tameion | 기업의 자금, 청구서, 외주와 감사 기록을 관리하는 에이전트를 개발한다. | 가입 절차, 공개 코드와 녹화 시연을 요구한다. 테스트넷 또는 메인넷 USDC를 Arc와 Agent Stack에서 실제 이동시키고 실제 사업의 사용을 보여야 한다. 합성 자료만으로 실제 사용 요건을 충족하지는 못한다. | 상금, 개발 자료와 계속 개발하는 팀의 후속 자금 및 배포와 사용자 연결 지원을 안내한다. [Tameion](https://tameion.thecanteenapp.com/) |
| Encode x Arc DeFi | 탈중앙 금융(DeFi, Decentralized Finance)의 대출, 자본시장, 환전과 에이전트 상거래 등을 개발한다. | 현장 참가와 작품 제출 규칙을 따른다. 공고의 개발 주제와 해당 시점에 제공되는 기능을 구분한다. | 상금과 현장 공동 개발을 안내한다. [해당 회차 공고](https://community.arc.io/public/events/encode-arc-hackathon) |
| Arc x Encode Enterprise & DeFi | 기업 금융, 은행 인프라와 프로그래밍 가능한 지급 기능을 개발한다. | 현장 등록과 작품 제출이 필요하다. StableFX, USYC와 CPN에는 별도 접근 승인 및 조기 등록 안내가 있다. | 멘토링, 기술 세션, 통합 지원과 상금을 안내한다. [해당 회차 공고](https://community.arc.io/public/events/arc-x-encode-enterprise-and-defi-hackathon-vcm38l2yye) |
| Encode Programmable Money | Arc와 Circle 도구로 실제 제품의 시제품을 개발한다. | Arc 배포, 작동하는 화면과 서버, 코드 저장소와 영상 시연을 요구한다. | 개발 경쟁과 상위 팀의 후속 액셀러레이터 참여를 연결한다. [해당 회차 공고](https://community.arc.io/public/events/hackathon-programmable-money-74llz8htis) |
| LabLab Agentic Commerce | 에이전트 상거래, 자율 구매와 판매, 신원 및 정책과 개발 도구를 구현한다. | Arc와 USDC를 사용한 정산, 공개 코드와 앱, 영상 및 제품 피드백을 요구한다. 일부 조기 접근 제품의 등록 기한은 일반 참가 기한과 다르다. | 상금, 개발 자료와 일부 조기 접근, Google 도구의 별도 과제를 안내한다. [주최자 규칙](https://lablab.ai/event/agentic-commerce-on-arc) |
| LabLab Agentic Economy | API, 데이터, 모델과 연산을 작은 사용 단위로 구매하는 에이전트를 개발한다. | API(Application Programming Interface)는 서비스 기능을 프로그램에서 호출하는 접점이다. 공고는 Arc, USDC와 Nanopayments, 공개 코드와 시연, 거래 검증 및 제품 피드백을 요구한다. 온라인 제출과 승인된 현장 참여 조건을 구분한다. | 상금, Circle 및 Arc 전문가의 안내와 개발 자료를 제공한다. 건별 가격, 거래 빈도와 비용 구조의 시연 기준도 확인한다. [주최자 규칙](https://lablab.ai/ai-hackathons/nano-payments-arc) |
| ETHGlobal HackMoney | 온라인에서 탈중앙 금융 앱을 개발한다. | 본대회와 선택한 후원 과제의 규칙을 따른다. Arc의 개발 지원 그룹 참여는 질문과 답변을 위한 별도 활동이다. | Arc 및 커뮤니티의 개발 질문 지원을 안내한다. [Arc의 HackMoney 안내](https://community.arc.io/public/events/ethglobal-hack-money-defi-hackathon-x4185sibue) |
| ETHGlobal Cannes의 Arc 상금 | 조건부 계약, 체인 간 USDC 앱과 에이전트 경제 등의 개발을 지원한다. | 분야별 규칙, 작동하는 화면과 서버, 구조도, 영상 및 상세 코드 문서를 요구한다. | Arc 후원 상금과 개발 자료를 제공한다. [Arc 상금 규칙](https://ethglobal.com/events/cannes2026/prizes/arc) |
| ETHGlobal New York의 Arc 상금 | 계약 기반 지급, 여러 체인의 자금과 에이전트 지급을 다룬다. | 분야별 제출 요건을 따른다. 비공개 소액 결제 분야에는 별도 지갑과 프라이버시 도구의 통합 조건이 있다. | 분야별 후원 상금, 개발 문서와 워크숍을 안내한다. [Arc 상금 규칙](https://ethglobal.com/events/newyork2026/prizes/arc) |
| ETHOnline의 Arc 상금 | 금융 앱, Agent Stack의 에이전트와 계속 개발하는 프로젝트를 다룬다. | 작동하는 화면과 서버, 구조도, 시연과 코드 문서가 필요하다. 기존 프로젝트를 이어 개발하는 분야(Continuity Track)와 일부 상금의 메인넷 배포 조건을 구분한다. | 분야별 상금과 개발 자료를 제공한다. [Arc 상금 규칙](https://ethglobal.com/events/ethonline2026/prizes/arc) |
| ETHGlobal Mumbai | 여러 블록체인과 개발 주제를 다루는 현장 해커톤이다. | 개인별 신청과 승인, 팀 구성 및 예치 절차와 작품 제출 규칙을 따른다. 기존 코드 사용에 관한 안내가 충돌하는 부분은 주최자에게 확인해야 한다. | 현장 멘토와 파트너 지원 및 식사 등을 안내한다. 이동과 숙박, Arc 후원 상금 조건은 각각 확인한다. [본대회](https://ethglobal.com/events/mumbai) |
| OpenClaw USDC | 자율 에이전트의 상거래, 기능 확장과 스마트 계약을 실험한다. | 에이전트가 Moltbook에 제출하고 다른 에이전트가 투표하는 방식이다. Arc House 게시 여부만으로 추가 배포 조건을 만들지 않고 해당 공고를 따른다. | 분야별 USDC 상금과 실험 참여를 안내한다. [공고](https://community.arc.io/public/events/openclaw-usdc-hackathon-on-moltbooks-xdk1tu0nvo) |
| Agentic Economy Prize | 실제 사업에서 에이전트가 지급하고 수취하는 모습을 평가한다. | Build with Gemini XPRIZE라는 별도 대회에 이미 참여하는 팀을 위한 선택형 추가 상금이다. Google Cloud 기반 프로젝트, Agent Stack, 공개 코드와 검증 가능한 실제 USDC 거래 시연을 요구한다. | Circle의 추가 상금이다. 참가의 출발점은 원래 대회의 자격이다. [공고](https://community.arc.io/public/events/the-agentic-economy-prize-aignfyumkq) |

실제 사용, 테스트넷 시연과 메인넷 배포는 서로 다른 증거다. 같은 제품을 사용하는 해커톤이어도 어떤 증거를 요구하는지에 따라 준비할 결과물이 달라진다. 총 대회 상금과 Arc의 특정 후원 상금도 각각의 규칙으로 읽어야 한다.

### 7.2 자금 지원과 사업 성장: 작은 결과물, 제품 출시와 회사의 성장에는 어떤 지원이 연결되는가?

지원금과 성장 프로그램은 개발 경쟁과 다른 신청 자료를 요구할 수 있다. 이미 배포한 결과물, 제품의 통합 구조와 사업 상태를 확인하는 이유도 프로그램의 목적에 따라 달라진다. 투자 검토는 지원금 지급과 구별한다.

| 프로그램 | 목적 | 요구사항과 구분할 조건 | 지원 내용과 공개 출처 |
|---|---|---|---|
| Arc Microgrants | 이미 만든 초기 실험과 작은 결과물을 지원한다. | 공개 신청 안내는 Arc 메인넷에서 동작하는 배포, 검증 가능한 계약 주소 또는 거래 해시, 공개 저장소, 설명과 공개 프로필을 요구한다. 이전 배포 경험과 지원금 수령 이력도 제출하며 이미 지원받은 작업의 제외 조건을 확인한다. | 지분을 제공하는 방식이 아닌 USDC 지원금, 기술 안내, 상담과 커뮤니티 소개 및 후속 지원 경로다. [신청 안내](https://dorahacks.io/hackathon/arc-microgrants) |
| Circle Developer Grants | Arc와 Circle 제품을 의미 있게 연결한 금융 업무 제품을 지원한다. | 사업과 통합 구조, 개발 계획 및 지원금 지급 단계를 제출한다. 구현 능력, 사용 또는 실증, 성공 경로와 생태계 기여를 평가하고 승인한 단계에 따라 지급한다. | USDC 자금, 기술 및 설계 지원, 공동 홍보와 생태계 연결을 안내한다. [공식 프로그램](https://www.circle.com/grant) |
| Arc Acceleration Season | 라틴아메리카 핀테크와 AI 스타트업의 Arc 통합 및 출시를 돕는다. | 기존 사업과 사용 실적을 가진 팀의 통합 개발, 테스트넷 시제품, 메인넷 출시와 발표를 다루는 공고다. 대상 사업과 지역 조건은 해당 회차로 확인한다. | 기술 상담, 비동기 지원과 Circle 및 Arc 팀의 도움, 투자자와 생태계 관계자 대상 발표 기회다. [공고](https://community.arc.io/public/events/arc-acceleration-season-vanemu91dk) |
| Programmable Money 후속 액셀러레이터 | 해커톤 결과물을 실제 출시로 연결한다. | 앞선 해커톤의 상위 팀에 연결된 지원이다. 독립적으로 신청 가능한 공개 모집인지는 별도 공고로 확인한다. | 워크숍, 개별 상담, 목표와 진행 점검 및 참여팀의 공동 개발이다. [연결된 해커톤 공고](https://community.arc.io/public/events/hackathon-programmable-money-74llz8htis) |
| Arc Builders Fund와 Circle Ventures Investor Network | Arc 기반 금융 앱과 회사의 투자 및 장기 협력을 검토한다. | 투자 설명 자료를 제출하고 개별 심사를 받는다. Builders Fund는 Circle Ventures의 내부 활동을 설명하는 명칭이다. 투자자 소개와 실제 투자 결정은 구별한다. | 자본 검토, 핵심 팀의 지원과 투자자 소개를 안내한다. Investor Network 참여사에 투자 의무가 생기는 것은 아니다. [공식 안내](https://www.arc.io/builders-fund) |

Microgrants의 결과물 요건을 회사의 실적 요건과 혼동하면 안 된다. 공고는 배포와 검증 가능한 결과를 요구하지만 회사 설립이나 사용 실적을 동일한 필수 조건으로 두는 프로그램이라고 해석해서는 안 된다. 반면 성장 지원은 기존 사업과 출시를 다루는 목적을 가질 수 있다. 각 프로그램의 제출 규칙을 구체적으로 읽어야 한다.

Microgrants의 요구사항은 공개 신청 안내의 배포본을 기준으로 설명했다. 현재 접수 가능 여부와 신청 화면의 최신 조건은 해당 링크에서 확인해야 한다. 지원 프로그램 사이의 연결도 자동 선발이나 중복 지원 허용을 뜻하지 않는다.

### 7.3 교육과 구현 실습: Bootcamp와 워크숍은 어떤 기능을 배우게 하는가?

Programmable Money Bootcamp는 스테이블코인 지급 앱을 구현하는 비동기 교육이다. 지갑, 계약, 체인 간 이동과 환전 등의 기능을 실습하는 목적이다. 교육 과정 참여와 해커톤 작품 제출, 지원금 신청은 각각 다른 절차다. [Bootcamp 공고](https://community.arc.io/public/events/programmable-money-on-arc-bootcamp-mvixsdscmu)

ArcShop과 제품별 워크숍은 App Kits, Gateway와 에이전트 지급 등의 구현을 다룬다. 회차별 계정, 노트북과 실습 준비물을 갖추고 예제와 질의응답을 통해 기능을 배운다. 예를 들어 Gateway와 Wallets 실습은 체인별 자금과 지갑을 앱에 연결하는 작업에 관련된다. [Gateway 및 Wallets 실습](https://community.arc.io/public/events/arcshop-with-hj-understanding-gateway-building-chain-agnostic-apps-with-gateway-and-circle-wallets-fdoco9aigm)

### 7.4 기술 상담: Office Hours와 Design Clinic에는 무엇을 준비해 가져가는가?

Technical Office Hours는 개발자의 구체적인 기술 질문을 상담하는 활동이다. 공고에는 기술 질문의 사전 입력과 참여 승인을 요구하는 회차가 있다. 어떤 기능을 구현하고 있는지, 어느 단계에서 어떤 문제가 생겼는지 설명할 자료를 준비하면 상담 목적에 맞는다. [Technical Office Hours](https://community.arc.io/public/events/technical-office-hours-wyeu64jawb)

Design Clinic은 시스템 설계와 계약 패턴을 검토하는 활동이다. 지급 조건, 승인 구조, 계약 상태와 실패 후 처리를 구조도나 예제로 제시하는 일이 관련된다. 이러한 상담의 제공 내용은 기술 검토와 다음 작업에 대한 피드백이며, 제품 심사나 지원금 선정과는 구분한다. [Design Clinic](https://community.arc.io/public/events/arc-discord-architecture-review-design-clinic-60rn65umlw)

### 7.5 결과 발표와 공동 개발: Spotlight, Demo Day와 지역 모임에서는 어떤 경험을 얻는가?

Builder Spotlight는 선정팀의 구현과 개발 경험을 소개하는 활동이다. Show & Tell과 Demo Day는 자신의 결과물을 시연하거나 다른 팀의 발표를 살펴보는 기회가 된다. 공고에서 관람, 발표 신청과 선발팀 발표를 구분해야 한다. 발표가 공개된 제품은 팀의 구현 사례이며 독립적으로 검증한 성능 결과라고 읽어서는 안 된다. [Show & Tell](https://community.arc.io/public/events/arc-discord-show-and-tell-lightning-demos-zb35cf328l), [Agora Spotlight](https://community.arc.io/public/events/arc-x-canteen-agora-hackathon-builder-spotlight-00mi9xlatf)

Build Club과 지역 모임은 함께 개발하고 다른 개발자를 만나는 활동이다. 준비 중인 프로젝트, 도시와 언어, 온라인 참여 여부 등의 조건을 회차별로 확인한다. 제공하는 것은 공동 개발과 교류의 기회이며, 장소의 안내를 개인의 시민권 제한으로 해석하지 않는다. [공식 행사 목록](https://community.arc.io/public/events)

### 7.6 생태계 참여: Architects, 컨퍼런스와 Pragma는 어떤 기여와 교류를 지원하는가?

Architects는 커뮤니티 기여를 인정하고 역할 및 혜택과 연결하는 프로그램으로 소개된다. 소개 공고는 기여 활동과 인정 방식의 관계를 설명한다. 구체적인 기여 규칙과 역할 승인 조건은 해당 프로그램에서 확인해야 하며, 커뮤니티 역할과 회사의 직원 또는 대리인 권한은 구분한다. [Arc House와 Architects 소개](https://community.arc.io/public/events/introducing-arc-house-and-architects-hyp33duk9f)

Pragma, Circle House와 생태계 컨퍼런스는 강연, 토론과 관계자 교류에 연결된다. 입장권, 신청 심사와 초대 등 참여 조건은 행사마다 다르다. Pragma 입장과 연결된 해커톤의 참가 승인도 각각 확인해야 한다. 프로그램을 비교할 때에는 강연 및 교류의 제공 내용과 개발 자금 지원을 구별한다. [Pragma Mumbai](https://ethglobal.com/events/pragma-mumbai), [공식 행사 목록](https://community.arc.io/public/events)

### 7.7 보안 연구: Bug Bounty는 어떤 취약점 보고와 보상을 다루는가?

Team Arc는 Bug Bounty를 책임 있는 취약점 보고와 보상을 위한 활동으로 소개한다. 개발 제품을 제출하는 해커톤과 취약점을 보고하는 보안 연구는 평가 대상이 다르다. 실제 참여에는 프로그램이 정한 대상 시스템, 허용 범위, 보고 방식과 보상 기준을 확인해야 한다. [Team Arc의 프로그램 소개](https://www.arc.io/blog/the-unfinished-business-of-finance-machine-commerce-and-global-money), [Arc Bug Bounty](https://hackerone.com/arc-bbp/)

이 글은 그 활동의 목적을 소개하는 범위이며 구체적인 대상과 보상 등급을 확정하지 않는다. 보안 연구자는 해당 프로그램의 상세 규칙을 기준으로 참여 범위를 정해야 한다.

### 7.8 참여 조건의 읽기: 행사 일정, 제출 마감, 신청 조건과 지원의 범위를 어떻게 확인하는가?

행사 목록의 날짜, 주최자의 제출 마감과 별도 제품의 접근 신청 기한은 서로 다른 항목일 수 있다. Tameion과 Lepton의 Arc 안내 및 주최자 안내에는 일정의 차이가 있으며, Mumbai에서는 기존 작업 사용에 관한 설명이 충돌하는 부분이 있다. 신청에 적용할 조건은 해당 회차의 최신 주최자 규칙으로 확인하고 차이가 남으면 직접 문의해야 한다. [Tameion](https://tameion.thecanteenapp.com/), [Lepton](https://lepton.thecanteenapp.com/), [Mumbai](https://ethglobal.com/events/mumbai)

이벤트 등록을 작품 제출이나 지원금 신청으로 대신해서는 안 된다. 또 전체 대회 상금, 후원사의 분야별 상금, 지원금과 투자 검토는 지원 방식이 다르다. 프로그램별 목적과 필요한 증거를 이해한 다음, 개발하려는 기업 업무와 어느 활동이 연결되는지 검토할 수 있다.

## 8. Arc + AI 제품 방향: 기업 문제를 어떤 제품 조합과 프로그램으로 연결할 수 있는가?

기업 지급 결제를 Arc + AI로 개선한다는 방향은 지급 전의 확인, 승인된 범위의 실행과 지급 후의 대사를 연결하는 제품으로 구체화할 수 있다. 아래는 실제 사례가 드러낸 업무와 주최자의 개발 제안을 연결한 이 글의 설계 가설이다. 주최자가 특정 사고의 해결책을 인증한 것으로 읽어서는 안 된다.

### 8.1 지급 전 확인: 청구서와 거래처 변경 요청을 검토하고 승인된 지급만 실행할 수 있는가?

AI는 계약과 청구서, 거래처 변경 요청을 비교해 수취인이나 금액의 변경, 빠진 증거와 설명이 필요한 항목을 담당자에게 제시할 수 있다. 계좌 변경 사기 사례를 바탕으로 검토할 제품은 이러한 변경을 찾아 별도 확인과 승인에 연결하는 지급 전 검토 도구다. 이 기능의 정확성은 실제 요청 자료와 담당자의 확인 결과를 비교해 검증해야 한다.

승인된 결과는 수취인, 금액, 기한과 지급 한도 같은 명시적인 정책으로 실행에 연결한다. Wallets가 서명과 권한을 다루고 Arc가 계약 실행과 결과를 기록하는 구성을 검토할 수 있다. AI가 작성한 설명을 읽는 일과 돈을 보내는 권한은 구분한다. Tameion의 AP/AR(Accounts Payable/Accounts Receivable, 지급할 돈과 받을 돈의 처리) 및 상대방 위험 관련 제안은 이 업무에 연결된다. [Tameion의 개발 제안](https://tameion.thecanteenapp.com/), [Wallets의 권한 모델](https://developers.circle.com/wallets/signing-and-authorization-models)

### 8.2 조건부 지급: 납품과 계약 단계의 확인을 대금 지급 및 분쟁 처리와 연결할 수 있는가?

외주나 공급업체의 단계별 지급에서는 문서에 적힌 조건과 실제 검수 결과를 연결해야 한다. AI는 계약에서 필요한 증거와 지급 조건을 정리하고, 제출된 자료와 비교하며, 판단하기 어려운 항목을 담당자에게 전달하는 역할을 검토할 수 있다. 누가 검수를 승인하고 이의를 처리하는지까지 앱에 포함해야 한다.

승인된 조건을 Arc의 계약과 지갑 지급에 적용하되, 계약이 판단할 수 있는 상태와 사람이 확인할 외부 사실을 구분한다. 이는 Team Arc와 Tameion의 조건부 지급 제안에서 출발한 제품 후보다. 앞선 실제 피해 사례에 추가된 새로운 사고 사례는 아니다. Cannes와 New York의 계약 기반 지급 분야 및 Design Clinic의 설계 검토와 관련된다. [Team Arc의 제안](https://www.arc.io/blog/the-unfinished-business-of-finance-machine-commerce-and-global-money), [Cannes의 Arc 분야](https://ethglobal.com/events/cannes2026/prizes/arc), [New York의 Arc 분야](https://ethglobal.com/events/newyork2026/prizes/arc)

### 8.3 지급 후 확인: 지급 기록, 판매자 정산과 고객별 잔액을 지속적으로 대조할 수 있는가?

판매자 정산에는 지급할 의무, 정산 일정, 실제 사용 가능한 자금과 수취 결과를 연결하는 도구를 검토할 수 있다. AI는 일정과 잔액을 비교하고 누락 및 지연을 찾거나 원인 확인에 필요한 자료를 담당자에게 제시하는 역할이다. Arc의 실행 기록과 CPN의 지급 상태를 기업의 정산 기록에 연결하되 판매자의 실제 수취를 따로 확인한다.

고객자금 대사는 서비스 장부, 지갑과 은행 기록의 시점 및 범위를 맞추는 업무다. AI는 기록을 분류하고 차이를 찾아 설명을 보조할 수 있지만, 근거가 없는 숫자로 부족분을 메우면 검증이 되지 않는다. 고객별 귀속, 실제 보관금과 지급 기록이라는 독립된 입력을 확보해야 한다. Synapse와 영국 감독기관 자료는 이 책임을 검토하는 근거다. [Synapse 보고서](https://www.cravath.com/a/web/ogvbURUX4uGN9FJ178bssS/aafskj/20250206-485-chapter-11-trustees-fifteenth-status-report.pdf), [영국 감독기관 발표](https://www.fca.org.uk/news/press-releases/payment-safeguarding-rules-changes)

Tameion의 감사 기록과 사업 운영, Encode의 기업 금융 및 Developer Grants의 자금 관리 방향이 관련된다. 블록체인 기록의 활용은 보관 책임과 중개자의 지급 능력을 보장하는 것과 구분한다. [Tameion](https://tameion.thecanteenapp.com/), [기업 금융 공고](https://community.arc.io/public/events/arc-x-encode-enterprise-and-defi-hackathon-vcm38l2yye), [Developer Grants](https://www.circle.com/grant)

### 8.4 자금 준비와 국제 지급: 분산된 잔액, 환전과 수취인 지급을 함께 관리할 수 있는가?

기업은 지급 예정 금액과 실제 사용 가능 자금을 함께 확인해야 한다. AI가 청구서와 일정을 읽고 부족 자금, 다른 체인으로의 이전 필요와 환전 시점을 담당자에게 제안하는 구성을 검토할 수 있다. Gateway의 예치 잔액, CCTP의 이전, Mint의 전환과 StableFX의 교환을 각 역할에 맞게 연결한다. 운용 자산을 활용한다면 환매와 지급 시점의 조건도 포함한다.

국제 지급에서는 수취 통화와 실제 지급 경로를 확인하고, CPN의 지원 상품 및 파트너 처리 상태를 연결한다. 모잠비크와 항공사 자료가 보여주는 통화 공급, 승인과 제도 조건은 따로 다룬다. AI가 유리한 경로를 제안하거나 온체인 이전이 가능하다는 사실만으로 지급 가능성을 확정할 수는 없다. Tameion의 자금 관리, Encode Enterprise & DeFi와 Developer Grants의 환전 및 자금 관리 방향이 관련된다. [Tameion](https://tameion.thecanteenapp.com/), [Encode의 기업 금융 주제](https://community.arc.io/public/events/arc-x-encode-enterprise-and-defi-hackathon-vcm38l2yye), [Developer Grants](https://www.circle.com/grant)

### 8.5 기업의 유료 자원 구매: 에이전트가 예산 안에서 API와 서비스를 구매하고 비용 근거를 남길 수 있는가?

기업의 에이전트가 데이터, 모델과 연산을 유료로 사용하는 업무를 생각할 수 있다. 제품은 사용할 서비스, 예산, 승인 조건과 구매 이유를 기록하고 실제 사용량 및 지급을 확인해야 한다. AI는 필요한 자원을 선택하는 판단을 맡을 수 있으며, 지급 권한과 한도는 명시적인 정책으로 제한한다.

Agent Stack과 Gateway Nanopayments는 서비스 탐색과 작은 사용 단위의 지급에 연결된다. Lepton과 LabLab의 Agentic Economy 및 Commerce는 이러한 구매와 지급을 개발 주제로 제시한다. Agentic Economy Prize도 관련되지만 원래 대회의 참가 자격과 실제 사업 사용 조건을 함께 읽어야 한다. 서비스 사용과 지급을 시연하는 증거, 반복 요청과 취소 처리 및 비용 근거를 남기는 설계가 중요하다. [Agent Stack](https://www.circle.com/blog/introducing-circle-agent-stack-financial-infrastructure-for-the-agentic-economy), [LabLab Agentic Economy](https://lablab.ai/ai-hackathons/nano-payments-arc), [추가 상금 공고](https://community.arc.io/public/events/the-agentic-economy-prize-aignfyumkq)

### 8.6 문제와 프로그램의 연결: 어떤 개발 주제, 제출 증거와 지원 방식이 각 업무에 연결되는가?

프로그램을 문제와 연결할 때에는 주제의 관련성과 실제 제출 조건을 함께 확인한다. 아래 표는 프로그램 추천 순위나 개인의 참가 가능성 판단이 아니다. 각 기업 업무를 어떤 개발 제안과 구현 또는 지원 활동에 연결할 수 있는지 비교한다.

| 기업 업무 문제 | 검토할 AI 업무 | Circle과 Arc의 역할 | 관련 프로그램과 연결 이유 | 개선을 확인할 증거 |
|---|---|---|---|---|
| 거래처 변경과 지급 지시의 진위 | 청구서와 계약, 변경 요청의 차이를 찾고 확인할 항목을 제시한다. | Wallets 및 앱의 정책으로 승인된 지급을 제한하고 Arc에 실행 결과를 기록한다. | [Tameion](https://tameion.thecanteenapp.com/)의 AP/AR와 상대방 위험 제안이 관련된다. | 실제 확인 자료, 놓친 위험과 잘못 차단한 요청, 승인 및 지급 기록을 비교한다. |
| 승인과 실제 집행의 불일치 | 수취인과 금액을 대조하고 반복 및 재시도 요청을 검토한다. | 한도와 승인 조건, 지갑 서명 및 Arc의 실행 결과를 연결한다. | Tameion의 승인 제한 예시와 [Design Clinic](https://community.arc.io/public/events/arc-discord-architecture-review-design-clinic-60rn65umlw)의 계약 검토가 관련된다. | 승인한 값과 실행한 값, 중복 집행 및 오류 이후 처리 기록을 확인한다. |
| 조건부 외주 및 공급업체 지급 | 계약과 납품 자료를 읽고 지급 조건 판단을 보조한다. | 승인된 상태를 계약과 Wallets의 지급에 적용한다. | [Cannes](https://ethglobal.com/events/cannes2026/prizes/arc)와 [New York](https://ethglobal.com/events/newyork2026/prizes/arc)의 계약 기반 지급 분야가 관련된다. | 납품 및 검수 증거, 지급 결정과 이의 제기 처리를 확인한다. |
| 판매대금 정산과 자금 부족 | 정산 일정과 지급 의무, 잔액 및 지연을 대조한다. | 실행 기록과 CPN의 수취 상태를 기업의 정산 기록에 연결한다. | [Encode Enterprise & DeFi](https://community.arc.io/public/events/arc-x-encode-enterprise-and-defi-hackathon-vcm38l2yye)와 Tameion의 기업 금융 및 자금 관리 주제가 관련된다. | 판매자별 지급 의무와 실제 수취, 부족 자금 및 지연을 확인한다. |
| 장부와 실제 자금의 불일치 | 서로 다른 기록을 분류하고 차이와 원인을 전달한다. | Arc와 지갑, 지급 서비스 및 은행 기록을 대사의 입력으로 연결한다. | Tameion의 감사 기록과 [Developer Grants](https://www.circle.com/grant)의 자금 관리 방향이 관련된다. | 같은 시점과 범위의 원본 기록, 차이의 원인과 해결 내용을 확인한다. |
| 국제 지급과 통화 확보 | 잔액, 수취 통화와 경로를 조회하고 이전 및 환전 판단을 보조한다. | 지원되는 Mint, CCTP 또는 Gateway, StableFX와 CPN의 역할을 조합한다. | Encode의 기관 제품 통합, Developer Grants의 환전 및 [Bootcamp](https://community.arc.io/public/events/programmable-money-on-arc-bootcamp-mvixsdscmu)의 실습이 관련된다. | 견적, 자금 사용 가능 시점과 실제 수취를 확인한다. 제도와 금융기관의 조건도 남는다. |
| 분산 자금과 예정 지급 | 예정 지급과 사용 가능한 자금을 비교하고 배분과 회수 시점을 제안한다. | 예치 잔액과 자산 이전, 필요에 따른 운용 자산을 자금 계획에 연결한다. | Tameion, [Acceleration Season](https://community.arc.io/public/events/arc-acceleration-season-vanemu91dk)과 Developer Grants의 자금 관리 주제가 관련된다. | 예상과 실제 현금 수요, 환매 및 지급 시점의 차이를 확인한다. |
| API 및 서비스 사용료 | 정책과 예산 안에서 서비스를 선택하고 사용과 비용 근거를 남긴다. | Agent Stack, Nanopayments와 지원되는 Arc 정산을 연결한다. | [Lepton](https://lepton.thecanteenapp.com/), [LabLab](https://lablab.ai/ai-hackathons/nano-payments-arc) 및 에이전트 지급 분야가 관련된다. | 실제 서비스 사용과 지급, 한도, 반복 요청 및 취소 처리를 확인한다. |

학습할 기능이 필요하면 교육과 상담을, 구현 결과를 비교하려면 해커톤과 공개 시연을, 배포 이후 지원이 필요하면 해당 지원금 및 성장 프로그램을 검토할 수 있다. 이것은 활동의 목적에 따른 연결이며 반드시 순서대로 거쳐야 하는 단계는 아니다. 최종 신청에서는 각 회차의 자격, 도구 접근과 제출 증거를 다시 확인한다.

### 8.7 제품 방향의 판단: Circle과 Arc의 목표에 어떻게 연결되며 무엇으로 개선을 확인할 것인가?

이 글에서 도출한 방향은 기업의 지급 업무를 지속적으로 확인하고, 승인된 범위에서 실행하며, 실제 수취와 장부까지 결과를 확인하는 제품이다. Circle의 자산 및 금융 기능 연결 방향과 Team Arc의 상거래 및 에이전트 개발 제안에서 출발한 가설이다. Circle이 발표한 단일 제품 전략이나 개발해야 할 유일한 제품으로 확정하는 것은 아니다. [Circle의 제품 비전](https://www.circle.com/blog/building-the-internet-financial-system-circles-product-vision-for-2026), [Team Arc의 제안](https://www.arc.io/blog/the-unfinished-business-of-finance-machine-commerce-and-global-money)

제품 후보는 담당 기업과 업무 문제, AI가 해석할 자료, 사람이 승인할 조건, Arc가 실행하고 기록할 상태와 사용할 Circle 제품을 함께 설명해야 한다. 그 다음에는 잘못된 지급, 중복 집행, 정산 지연과 대사 오류 등의 변화로 개선을 확인한다. 거래 기록을 제출해 프로그램 조건을 충족한 것과 기업 업무가 개선됐다는 증거도 구분한다.

따라서 Arc 기반으로 개발하되, Circle 제품과 연결해 실제 기업 지급 업무를 완성하는 방향을 검토한다. AI는 그 업무에서 필요한 문서 해석, 기록 대조와 판단 보조에 연결한다. 개인의 구현 가능성보다 먼저 정리할 것은 이 제품이 어떤 기업 문제를 맡고, Circle과 Arc가 제공하려는 기능에 어떻게 연결되는지다.
