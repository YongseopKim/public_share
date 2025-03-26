# 우리

첫 스타트를 끊었다는 것에 의의를 아주 크게 두자! 우리는 시작하였다!

SurveyX를 시작으로 우리 '학술검색' 또는 이런 시스템을 고려하는 개발자의 입장에서 어떠한 가치를 기반으로 어떠한 걸 만들지를 생각해보자. 혹은 어떤 일을 대비해도 좋고!

# SurveyX

SurveyX 목적
- 페이퍼가 기하급수적으로 늘어나니, 이런 페이퍼를 정리하는 문서를 생성해주는 자동화 시스템을 고려
- LLM만으로는 한계(최신 레퍼런스 지원, 컨텍스트 사이즈 제한 등)

파이프라인 구조
1. Preparation Phase
  1. References Acquisition: online/offline
  2. Reference Pre-processing
    - AttributeTree 생성
    - 각 논문에서 핵심 정보를 트리 구조로 정리 -> AttributeForest
2. Generation Phase
  1. Outline Generation
    1. LLM이 1차적인 상위 구성 작성
    2. AttributeTree를 Hint 삼아 구체적인 2차 아웃라인 작성
    3. Outline Optimization: wndqhr, qnfvlfdygks sodyd wjdfl
  2. Content Generation
    - 각 섹션별로 AttributeTree를 Hint로 추출 with RAG
  3. Post-Processing
    - RAG 기반 Rewriting
    - 표, 그림 등 생성

# 나

## 학술검색 딥러서치 대비

우리(BE ORCHE)가 할 수 있는 게 무엇이지? 분리가 되는 걸까? R&R을 자를 수가 있을까?

오히려 이 관점에서 보면 좀 답답한 시나리오가 펼쳐질 것 같음

학술검색 딥리서치를 한다고 들었다면, 그들이 어느 영역까지를 하고 싶어하는지가 중요할 듯

## 새로운 우리의 프로젝트 (bottom up 시도) -> 저만의 뇌절

SurveyX를 보고난 후 드는 생각
- general한 pipelining을 구축하는 것을 도와주는 framrwork를 만들 수 있지 않을까?

현재의 SurveyX
- AttributeForest를 구축하는 시스템
- AttributeForest를 이용하여 문서를 만들어내는 시스템

Let's generalize
- Knowledge를 구축하는 시스템
- Knowledge를 이용하는 시스템

이번에는 간단히 살짝만 구체화해보자.
- Knowledge를 구축하는 시스템
  - 어떤 Input? local files, web
  - 어떤 알고리즘? 어떤 process를 적용할 것인가?
  - 어떤 Output? KG일수도 있고, VectorStore에 담기는 형태일 수도 있고. Tree, Forest의 형태일수도
  - 그리고 무엇보다 이 결과물을 general하게 이용할 수 있는 MSA로 만들어진 시스템
- Knowledge를 이용하여 생성하는 시스템
  - 무엇을 생성할 것인가? 문서 작성, 요약, ...
  - 전처리 생성기: 목적에 따른 Outline 생성기
  - 컨텐츠 생성기
  - 후처리 생성기

여기까지 정리해보면, 그려지는 어떤 프로젝트는 SW 프레임워크인데, 다음을 정의 및 구현이 가능케 한다.
- Knowledge를 구축하는 시스템
- Knowledge를 이용하는 시스템

이를 위해, 큰 틀(pipeline template)을 제공하고, 또한 Agent를 제공할 수도 있고, 미리 구현된 컴포넌트들을 제공할 수 있다.

컴포넌트 example
- AttributeForest
- 문서 생성을 위한 전처리/컨텐츠/후처리 생성기
- 문서 요약을 위한 전처리/컨텐츠/후처리 생성기
- ...

이걸 현재의 지식창고에 적용?
- Knowledge를 구축하는 시스템
  - input: local files
  - output: embed in vector store
- Knowledge를 이용하는 시스템
  - 문서 생성을 위한 전처리/컨텐츠/후처리 생성기
