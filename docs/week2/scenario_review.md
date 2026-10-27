# [T?] Week 2 · 시나리오 설계 & 상호 리뷰 노트

> Global AI Ethics Simulator — Week 2 산출물 템플릿
> © 2026 강송희 교수 · CC BY-NC 4.0

---

## 1. 우리 팀 시나리오 3종 요약

| sid | 제목 | 핵심 딜레마 축 | 로컬 근거 |
|---|---|---|---|
| S1_subway  | 지하철 스크린도어 정지 딜레마 | 개인 vs 공동체 | 2022 이태원 관련 안전 담론 |
| S2_noise   | 아파트 층간소음 중재 | 규범 vs 관용 | 국토부 층간소음 가이드 |
| S3_nokids  | 노키즈존 도입 | 사업권 vs 포용 | 국가인권위 2017 결정 |

> 실제 JSON 은 `data/scenarios.json` 에 저장, 검증은 `python scripts/validate_scenarios.py`.

## 2. 보상 벡터링 근거

| sid | 옵션 | emotion | social | moral | identity | 근거 |
|---|---|---|---|---|---|---|
| S1_subway | A | +0.8 | −0.6 | −0.5 | +0.3 | 즉각 개입은 감정적 만족 크나 규정 위반 |
| S1_subway | B |  |  |  |  | |
| S2_noise  | A |  |  |  |  | |
| ... | | | | | | |

## 3. 상호 Value-Check (다른 팀 리뷰 결과)

| 리뷰 대상 팀 | 우리 판정 | Issue 링크 | 주요 지적 |
|---|---|---|---|
| T? (USA) | ⚠️ 수정 요청 | #12 | S2 옵션 A의 identity 점수 근거 부족 |
| T? (MIDDLE_E) | ✅ 승인 | #13 | 종교적 프레임이 moral 에 잘 반영됨 |

## 4. 우리가 받은 리뷰 대응

| Issue | 지적 | 대응 | 커밋 SHA |
|---|---|---|---|
| #21 | S3의 social 점수 부호 검토 | +0.8 → +0.6 조정 | `abcd123` |

## 5. AI 사용 로그 (Non-AI 초안 vs AI 개선)

> 전체 로그는 `logs/ai_usage_log.md` Entry #4~#8

---

### 🔍 자기 점검

- [ ] 시나리오 3개 이상
- [ ] 각 시나리오가 서로 다른 딜레마 축을 자극
- [ ] `scripts/validate_scenarios.py` 통과
- [ ] 상호 리뷰 Issue 2건 이상
- [ ] 받은 리뷰에 대한 대응 커밋 존재
