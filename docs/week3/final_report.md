# [T?] Week 3 · 시뮬레이션 최종 분석 리포트

> Global AI Ethics Simulator — Week 3 산출물 템플릿
> © 2026 강송희 교수 · CC BY-NC 4.0

---

## 1. 실행 조건

| 문화권 | seeds | episodes | learning_rate | epsilon_init | epsilon_decay | 실행 로그 |
|---|---|---|---|---|---|---|
| KOREA   | 42, 123, 2026, 7777, 31337 | 500 | 0.1 | 0.5 | 0.99 | `logs/experiments/20260726_KOREA_seed42_ep500.csv` |
| USA     | 42, 123, 2026, 7777, 31337 | 500 | 0.1 | 0.5 | 0.99 | `.../20260726_USA_seed42_ep500.csv` |
| MIDDLE_E| 42, 123, 2026, 7777, 31337 | 500 | 0.1 | 0.5 | 0.99 | `.../20260726_MIDDLE_E_seed42_ep500.csv` |

## 2. 핵심 지표 (5개 seed 평균 ± 표준편차)

| 문화권 | 최종 Reward | 최종 Entropy | Diversity | Pearson r (div-rew) | p-value |
|---|---|---|---|---|---|
| KOREA    | __ ± __ | __ ± __ | __ | __ | __ |
| USA      | __ ± __ | __ ± __ | __ | __ | __ |
| MIDDLE_E | __ ± __ | __ ± __ | __ | __ | __ |

## 3. 시각화

### Fig 1. Reward Curve (3문화권 오버레이)
![reward_curve](../../logs/experiments/fig1_reward_curve.png)

### Fig 2. Strategy Entropy Decay
![entropy_decay](../../logs/experiments/fig2_entropy_decay.png)

### Fig 3. Diversity vs Reward 산점도 + 회귀선
![diversity_reward](../../logs/experiments/fig3_diversity_reward.png)

## 4. 가설 검증

| 가설 | 지지 / 기각 | 근거 지표 | 해석 |
|---|---|---|---|
| H1. KOREA 는 S1에서 옵션 B 수렴 | ✅ 지지 | 200 ep 이후 B 선택률 78% | identity+social 가중치 합이 0.6으로 지배 |
| H2. identity 高 → diversity 低 | ⚠️ 부분 지지 | KOREA/MIDDLE_E 비교 | seed 편차 큼, 추가 스윕 필요 |
| H3. 최종 entropy ≤ 0.3 | ✅ 지지 | 평균 0.21 | ε-decay 효과 확인 |

## 5. Audit 노트 (Tech-Check 취지)

### 5-1 재현성
- seed 고정 시 5회 실행 동일 결과 여부: **✅ 완전 일치**
- 다른 실행 환경(Colab vs Streamlit Cloud) 차이: `1e-6` 이내

### 5-2 편향
- A 옵션 선택률의 문화 간 극단 차이(예: KOREA 22% vs USA 71%) → 문화 결정론적 해석 경계
- 시나리오 자체의 편향(뉴스 기반 → 부정 사례 편중) 명시

### 5-3 한계
- ε-greedy 단일 에이전트라는 강한 가정
- 시나리오 3개는 통계적 유의미성 확보에 부족
- 4프레임 축소가 실제 도덕 판단의 다차원성을 단순화

## 6. 재설계(R) 제안

| 제안 | 근거 | 다음 스프린트 계획 |
|---|---|---|
| identity 가중치 0.4 → 0.3 재조정 | H2 부분 지지 | Week 4 pilot |
| 시나리오 3 → 5 확장 | 통계 유의성 확보 | Narrative 앱 재저작 |
| DQN 등 심층 RL 비교 | ε-greedy 한계 극복 | 후속 프로젝트 |

## 7. 성찰 (Reflection)

> - 우리 결과가 "한국인은 이렇게 판단한다" 로 오독될 위험은 어떻게 방지할 것인가?
> - 이 시스템을 실서비스에 적용한다면 Value-Check/Tech-Check 관점에서 무엇이 걸릴까?
> - AI 사용 로그를 통해 우리 팀 사고 흐름이 어떻게 바뀌었는가?

---

### 🔍 제출 전 최종 체크

- [ ] seed 5개 이상 스윕
- [ ] 지표 표(Reward/Entropy/Diversity/Pearson) 완성
- [ ] 그림 3장 이상 저장
- [ ] Audit 3필러(재현성·편향·한계) 각 1건 이상
- [ ] 재설계 제안 1건 이상
- [ ] `logs/ai_usage_log.md` 최종 커밋
