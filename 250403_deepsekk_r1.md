## DeepSeek-V3-Base -> DeepSeek-R1-Zero

No SFT(지도학습)

RL
- GRPO(Group Relative Policy Optimization)
- 자연 발현된 추론 패턴(사고 시간 증가, 자기 검증(self-verification), "아하 순간(aha moment)" 등)
- 보상 모델링: 정확도 보상(문제 정답; `<think>`), 형식 보상(태그 구조 준수; `<answer>`)

```
(A conversation between user and assistant)
User: (문제)
Assistant:
<think> (여기에 모델의 내부 추론을 기록) </think>
<answer> (최종 답변) </answer>
```

가독성 문제; 언어 혼합 문제; 출력 형식 비일관성

## DeepSeek-V3-Base -> DeepSeek-R1

Coldstart 데이터
- 소규모 고품질 CoT 데이터 (수천 개)
- 형식: `|special_token|<reasoning_process>|special_token|<summary>`

다단계 RL 파이프라인
1. SFT: Coldstart 데이터
  - 목적: RL 훈련의 안정적 출발점 제공, 가독성 확보
  - 특징: 읽기 쉬운 형식 정의, 언어 혼합 문제 예방
2. 추론 중심 RL
  - 목적: 수학, 코딩, 과학 등 명확한 정답이 있는 영역의 추론 능력 향상
  - 특징: 정확도 보상 + 언어 일관성 보상 적용
3. 거부 샘플링 및 SFT
  - 목적: 고품질 데이터 생성 및 일반 능력 보완
  - 특징: RL 체크포인트에서 60만 추론 + DeepSeek-V3에서 20만 비추론 데이터 통합
4. 전체 시나리오 RL
  - 목적: 추론 능력 유지하면서 유용성과 안전성 향상
  - 특징: 추론 데이터(규칙 기반 보상) + 일반 데이터(보상 모델 기반) 통합 적용

## 증류(Distillation) 모델: 교사/대형 모델(DeepSeek-R1) -> 학생/소형 모델

Qwen(1.5B~32B), Llama(8B~70B)

SFT, No RL

-> 큰 모델에 직접 RL 적용보다 증류가 더 효과적
