# 2026 블록체인 AI 에이전트 해커톤 조사 대화

2026-10-10에 내보낸 대화 묶음이다. 같은 질문에 대한 답변을 합쳤으며, 보고서 첨부물도 검색본과 통합본에 반영했다. 원본은 raw/에 불변으로 보존한다. 2026-10-12에 내보낸 Arc App Kits와 Build with AI 비교 대화 세 개를 같은 단위에 더했다. 2026-10-13에 내보낸 Circle Agent Stack 심층 조사 대화 세 개도 같은 단위에 더했다.

- 읽기 안내
- 공식 공고 대조
- 독립 검토와 반영 결정
- 전체 통합본
- 변환과 확인 기록
- App Kits와 Build with AI 비교 읽기 안내
- App Kits와 Build with AI 비교 통합본
- App Kits와 Build with AI 비교의 변환과 확인 기록
- Circle Agent Stack 읽기 안내
- Circle Agent Stack 통합본
- Circle Agent Stack의 선별 확인 기록
- Circle Agent Stack의 변환과 확인 기록
- 기존 해커톤 조사
- 기존 제작 일정
- 사업 허브의 자료 연결

## 원본과 검색본

| 원본 | 검색본 | 출처와 범위 |
| --- | --- | --- |
| chatgpt_2026 블록체인 AI 해커톤 조사.jsonl | chatgpt.md | 2026 블록체인 AI 해커톤 조사; https://chatgpt.com/g/g-p-6a48c7276a44819180e4bc3c4787e07c-ai-agent/c/6ac9f26f-1c2c-83ee-9fbe-44d4efc96b2e |
| claude_2026 blockchain AI Agent hackathon.jsonl | claude.md | 2026 blockchain AI Agent hackathon; https://claude.ai/chat/42efbbd8-6c44-452d-b88e-efce58db27b9 |
| grok_2026 블록체인 AI Agent 해커톤 아이디어.jsonl | grok.md | 2026 블록체인 AI Agent 해커톤 아이디어; https://grok.com/c/b7115a66-b23f-44e2-b9fd-7411e2780bc9?rid=2b5c49c5-fab4-4231-b48a-e605d2b20895 |
| chatgpt_차이 비교.jsonl | chatgpt.md | 차이 비교; https://chatgpt.com/g/g-p-6ab0b6e03b048191b429994d9dee2847-circle/c/6acd5862-8a70-83ee-b596-abbcf5a0dd90 |
| claude_App-kits vs Build with AI.jsonl | claude.md | App-kits vs Build with AI; https://claude.ai/chat/27f46aab-0052-4169-bc95-782490b6e784 |
| grok_Arc App-Kit과 Build with AI 차이점.jsonl | grok.md | Arc App-Kit과 Build with AI 차이점; https://grok.com/project/a2af8907-0e1d-4b39-8ac5-f4c8de053a15?chat=2248b67c-714a-4f2f-8a76-5d687f6bf851 |
| chatgpt_Circle Agent Stack 심층조사.jsonl | chatgpt.md | Circle Agent Stack 심층조사; https://chatgpt.com/g/g-p-6ab0b6e03b048191b429994d9dee2847-circle/c/6acd5a29-feb0-83ec-a7dc-82882d10399f |
| claude_Circle agent stack 심층 조사.jsonl | claude.md | Circle agent stack 심층 조사; https://claude.ai/chat/d3496663-d9ae-49cb-b026-c83971776ef9 |
| grok_Circle Agent Stack 깊이 있는 조사.jsonl | grok.md | Circle Agent Stack 깊이 있는 조사; https://grok.com/project/a2af8907-0e1d-4b39-8ac5-f4c8de053a15?chat=b7f6c4cf-8626-4923-936c-5a55ba57356a |

## 보존과 한계

태그는 AI, business, blockchain이다. 내보내기 경로는 inbox/aiagents_hackathon이었다. 각 파일의 SHA-256, 크기와 원래 메타데이터는 원본 명세에 있다. 검색본은 기존 정규화 도구로 만들었고 원본을 수정하지 않았다.

보고서 첨부물은 내보내기 도구가 API 원문 대신 화면에 렌더링된 Markdown을 저장했다고 경고했다. 그 텍스트를 포함했으며 별도의 API 원본을 확보했다고 주장하지 않는다. 모델의 사전 노출과 비공개 프로젝트 문맥은 알 수 없다.

비교 대화 세 개 가운데 ChatGPT 대화에는 artifact 첨부물이 하나 있다. 그 HTML은 `pages/arc-app-kit-vs-build-ai/chatgpt-4.html`에, 그 안의 SVG 그림은 같은 폴더의 `images/`에 있고, 첨부물 텍스트를 넣은 검색본은 `readable/chatgpt.md`이다. 기본 렌더링인 `pages/arc-app-kit-vs-build-ai/chatgpt.md`는 첨부물 자리에 표지만 둔다. 통합본의 근거는 2026-10-07에 보관한 Arc 공식 문서이며, 대화를 내보낸 2026-10-12와 날짜가 다르다. 이 비교는 허브에 등록하지 않았다.

Circle Agent Stack 대화 세 개는 같은 질문을 담고 있다. ChatGPT 대화에는 답변을 렌더링한 HTML이 함께 내보내졌고, 그 파일은 `pages/circle-agent-stack/chatgpt-4.html`에 있다. 기본 렌더링 `pages/circle-agent-stack/chatgpt.md`에 data URI로 들어 있던 SVG 그림 21개(서로 다른 파일 13개)와 jpg 사진 세 장은 같은 폴더의 `images/`로 꺼냈다. 그 파일을 링크로 가리키는 검색본이 `readable/chatgpt.md`이고, 그림 명세는 `svg-manifest.json`과 `image-manifest.tsv`에 있다. Claude 대화에는 보고서의 핵심 판단을 요약한 답변과 보고서 본문이 따로 있고, 그 사이에 빈 답변이 하나 있다. 내보내기 도구는 보고서를 API 원문 대신 화면에 렌더링된 Markdown으로 저장했다고 경고했고, 화면의 메시지 수(2개)와 내보낸 메시지 수(3개)가 다르다고도 경고했다. 통합본의 근거는 vault에 이미 보관되어 있던 Circle 자료이며, 이번에 웹을 새로 받지 않았다. 답변이 인용한 외부 기사와 개발자 문서 대부분은 캡처되어 있지 않아서 `확인 불가`나 `미확인`으로 남았다. 이 조사도 허브에 등록하지 않았다.

보안 검사는 사용자가 중지한 상태이며 통과 판정을 기록하지 않았다.

## 읽기와 관련 기록

이 묶음은 후보 조사 근거이다. 참가 상태와 실제 작업 기간은 기존 제작 일정 문서가 맡는다. 공식 페이지의 선별 확인에는 별도 웹 수집 단위를 사용했다. 두 단위 모두 사업 허브에서 찾아갈 수 있다.

2026-10-15의 시각화 적용 기록과 영문 기록은 안내문과 해당 Arc 원고의 표현 개정을 다룬다. 기존 사실의 기준일과 원본 그림을 옮긴 부분은 유지했다.
