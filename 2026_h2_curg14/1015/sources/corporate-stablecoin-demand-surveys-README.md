# 2026-10-14 - 기업과 금융기관이 해외 지급 문제와 스테이블코인을 얼마나 중요하게 여기는가: 조사 발표 8건

Arc 해커톤 질문 묶음의 1번 답 다 절은 "고객이 이 문제를 얼마나 중요하게 여기는지는 측정하지 않았다"고 적었다. 사용자는 2026-10-14에 "충분히 외부 검색을 통해서도 힌트를 얻을 수 있는 것 같은데? 분명히 연구나 조사 이런게 있을 것 같은데?"[원문 그대로]라고 물었다. 이 단위는 그 물음에 답하려고 받은 조사 발표 여덟 건이다.

조사를 고른 기준은 두 가지다. 응답자가 기업이나 금융기관의 의사결정자일 것, 그리고 응답 수와 조사 시기를 밝힐 것. 응답자 집단이 서로 다른 조사를 일부러 함께 받았다. 지급 사업자와 금융기관을 물은 조사(Fireblocks, EY의 금융기관 쪽)와, 돈을 내는 기업의 재무 담당자를 물은 조사(AFP, PYMNTS, Deloitte, EY의 기업 쪽, Rapyd)가 그것이다. 이 구분은 내가 정했다. 두 집단의 답이 크게 달라서 하나로 합치면 읽을 수 없기 때문이다.

## 파일

`raw/`는 `.gitignore`(`cb/works/web/*/raw/**`)가 제외하므로 커밋에는 이 README와 `pages/`의 텍스트만 들어간다. 원본의 전체 SHA-256은 `raw/SHA256SUMS`에 있다. `pages/`의 텍스트는 이 세션이 쓴 일회용 변환기(Python `html.parser`, script와 style을 빼고 블록 요소마다 줄을 나눔)로 뽑았다. 인용한 문장은 모두 `pages/`에서 읽었다.

한 행은 받은 파일 하나다. "응답자"는 각 페이지의 조사 방법 문단이 적은 그대로다.

| 파일 | 무엇 | 응답자와 조사 시기 | 바이트, SHA-256 앞 16자 | 취득 URL | 텍스트 |
|---|---|---|---|---|---|
| raw/ey-2025-stablecoin-survey.html | EY-Parthenon, "Cost savings and speed drive stablecoin adoption", 2025-09-15. 이용률 13%, 비이용자의 54%가 6-12개월 안에 도입 예상, 이용자의 41%가 10% 이상 비용 절감, 관심 용도 1위 해외 공급사 지급 77%, 걸림돌 1위 규제 불확실성 73% | 금융기관 100, 기업 250, 의사결정자. 2025년 6월 중순(GENIUS Act 상원 통과 뒤, 서명 전) | 429,018, 0f6467ae9f0659d2 | `https://www.ey.com/en_us/insights/financial-services/cost-savings-and-speed-drive-stablecoin-adoption` | pages |
| raw/afp-2026-liquidity-survey-release.html | AFP(미국 재무전문가협회), 2026 Liquidity Survey 발표, 2026-06-16. 스테이블코인과 토큰화 상품을 시험하거나 제한적으로 쓰는 곳 1%, 적극 검토 9% | 미국 기관의 재무 담당자 309명. 2026년 3월 | 68,038, 5dcdc3bd6de99db4 | `https://www.financialprofessionals.org/about/learn-more/press-releases/Details/afp-survey-finds-stablecoins-remain-peripheral-to-liquidity-strategies-as-cash-reserves-rise` | pages |
| raw/pymnts-2026-03-cfo-stablecoins-waiting.html | PYMNTS Intelligence, "Waiting for Certainty", 2026년 3월. 이용 13%, 검토한 적 없음 58%, 3년 안에 "somewhat important"가 될 것이라는 답 4분의 1 미만, 도움이 될 것으로 은행 통합 45%와 규제 명확성 40%를 들고 비용 절감은 22% | 미국 중견기업(매출 1억-10억 달러) CFO 60명. 2026-01-13부터 01-21 | 151,692, f95a055483a486ba | `https://www.pymnts.com/study_posts/waiting-for-certainty-why-most-cfos-are-holding-back-on-crypto-and-stablecoins/` | pages |
| raw/pymnts-2026-03-cfo-stablecoins-promise.html | PYMNTS Intelligence, "Stablecoins Gain Ground", 2026년 3월. 같은 조사의 다른 편. 걸림돌로 규제 불확실성 67%, 기존 시스템과의 통합 43% | 위와 같은 조사 | 134,170, 1c8b4394ee776ae6 | `https://www.pymnts.com/study_posts/stablecoins-gain-ground-why-cfos-see-more-promise-there-than-in-crypto/` | pages |
| raw/fireblocks-state-of-stablecoins.html | Fireblocks, State of Stablecoins 2025 보고서 페이지. 이점 1위 빠른 정산 48%, 비용 절감 30%로 가장 낮음 | 은행, 결제 사업자, 핀테크, 암호화폐 사업자 등 295명(61%가 C-suite). 2025년 3월, 외부 조사회사 | 516,626, ee2bae94e232045b | `https://www.fireblocks.com/report/state-of-stablecoin` | pages |
| raw/fireblocks-pr-seekingalpha.html | 같은 보고서의 보도자료(PR Newswire 배포, Seeking Alpha 게재), 2025-05-15. 탐색 이유 1위는 시장 확대 39%, 비용 절감은 32% | 위와 같은 조사 | 132,032, 9ef65d55d5573ca2 | `https://seekingalpha.com/pr/20106152-fireblocks-report-stablecoins-move-from-experiment-to-production-with-revenue-growth-as-top` | pages |
| raw/rapyd-2023-cross-border-release.html | Rapyd, 2023 State of B2B Cross-Border Payments 발표, 2023-03-21. 해외 지급에 건당 10달러 이상 수수료 76%, 5일 이상 지연 경험 38%, 외환 수수료 0.25-1% 42% | 브라질, 독일, 멕시코, 싱가포르, 영국, 미국의 중대형 B2B 기업 715곳의 재무 의사결정자. 2023년 2월 온라인 | 113,667, cd4cff4db4c30fed | `https://www.rapyd.net/company/news/press-releases/cross-border-businesses-focus-on-expansion-but-common-payment-challenges-curb-growth/` | pages |
| raw/deloitte-2025-cfo-signals-crypto.html | Deloitte, CFO Signals 2Q25 발표, 2025-07-31. 스테이블코인의 동기로 고객 개인정보 보호 45%, 해외 거래 효율 39% | 북미 매출 10억 달러 이상 기업 CFO 200명. 2025-06-04부터 06-18 | 242,467, c93e65f7869880ea | `https://www.deloitte.com/us/en/about/press-room/cfo-signals-survey-north-american-cfos-anticipate-significant-uptick-in-corporate-cryptocurrency-adoption-2027.html` | pages |

## 어떻게 받았나

2026-10-14(KST)에 이 세션이 `curl`로 받아 scratchpad의 빈 디렉토리에 두고, 텍스트를 뽑은 뒤 이 단위로 옮겼다. 후보는 웹 검색으로 찾았지만, 검색 도구의 요약은 쓰지 않았다. 요약 가운데 하나가 GENIUS Act의 상원 통과를 2026년 6월로 적었는데, EY 원문은 2025-06-17로 적는다(`pages/ey-2025-stablecoin-survey.txt` 484행).

**받지 못한 것과 받지 않은 것.**

- SWIFT와 EuroFinance의 2017년 재무 담당자 조사 페이지(`https://www.swift.com/de/node/138866`)는 HTTP 403이었다. 검색 요약에 나온 그 조사의 수치는 원문으로 확인하지 못했으므로 쓰지 않는다.
- msg for banking의 2025년 Cross-border Payments Study(독일, 오스트리아, 스위스의 100명) 두 페이지는 받았지만, 조사 방법만 있고 결과 수치가 없어서 보관하지 않았다.
- PNC의 스테이블코인 기사(`https://www.pnc.com/insights/corporate-institutional/gain-market-insight/stablecoins-step-into-the-spotlight.html`)는 받는 명령이 파일을 쓰지 못하고 실패해서 받지 못했다. 다시 시도하지 않았다.
- 보고서 PDF 본문(EY, AFP, PYMNTS)은 받지 않았다. 여기 있는 것은 발행 기관이 공개한 요약 페이지다.

**같은 조사의 두 판이 다른 곳.** Fireblocks 보고서 페이지는 비용 절감을 30%, 유동성 개선을 33%로 적고(`pages/fireblocks-state-of-stablecoins.txt` 187행), 보도자료는 32%와 34%로 적는다(`pages/fireblocks-pr-seekingalpha.txt` 128행). 어느 쪽이 맞는지는 확인하지 않았다.

## 읽을 때의 한계

- 발행 기관의 이해관계가 있다. Fireblocks와 Rapyd는 스테이블코인 인프라와 해외 지급 서비스를 파는 회사다. EY와 Deloitte는 자문 회사다. AFP는 재무 담당자의 직업 단체이고, PYMNTS는 결제 산업 매체다.
- 미국 응답자가 많다. AFP, PYMNTS, Deloitte가 미국 또는 북미이고, 아시아와 한국 기업을 따로 물은 조사는 없다.
- 응답 수가 작은 것이 있다. PYMNTS는 60명이다.
- 모두 의견과 의향을 물은 조사다. 실제 거래량이나 비용을 잰 자료가 아니다.

## 쓰이는 곳

- Arc 해커톤 질문 묶음 1번 답의 다-3(고객이 느끼는 중요도) 소절이 이 파일들의 줄을 인용한다. 이 소절은 처음에 "고객의 문제가 핵심적이지 않다는 것을 어떻게 아는가"라는 소절의 3번 항목이었고, 2026-10-15에 목차를 만들면서 소절로 올렸다. 같은 답의 나-2(USDC 집중) 아래 USDC 중심 인프라 그림도 그 표의 두 값(EY 79%, PYMNTS 88%)을 다시 쓴다.
- Circle과 Arc 허브 3절(원자료 지도)에 등록했다.
