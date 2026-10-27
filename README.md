# Ethics Agent Game — 2팀

> **인공지능과 경영 · 11주차 협동학습**
> Global AI Ethics Simulator — 문화권 기반 윤리 강화학습 3주 스프린트

![Python](https://img.shields.io/badge/python-3.11-blue)
![Streamlit](https://img.shields.io/badge/streamlit-1.32+-red)
![License](https://img.shields.io/badge/license-CC%20BY--NC%204.0-green)
![CI](https://github.com/<org>/<repo>/actions/workflows/ci.yml/badge.svg)

---

## 🌏 팀 정보

| 항목 | 내용 |
|---|---|
| 팀명 | 2팀 |
| 배정 문화권 | LATIN_AM |
| Streamlit Cloud URL | https://<your-app>.streamlit.app |
| 시연 영상 | (선택) YouTube 링크 |

## 👥 팀원

| 이름 | 학번 | 전공 | 역할 | Email |
|---|---|---|---|---|
| 강민지 | 2025240001 | 인공지능학과 | 기획 | 2025240001@tukorea.ac.kr |
| 김윤서 | 2025xxxxxx | 경영학부 데이터사이언스경영학과 | 발표 | 2782jacob@gmail.com |
| 안예은 | 2025xxxxxx | 경영학부 데이터사이언스경영학과 | 시뮬레이션 | computer5904@naver.com |
| 이채원 | 2025xxxxxx | 경영학부 데이터사이언스경영학과 | 검증 | si2438431@gmail.com |
| 오지민 | 2025xxxxxx | 경영학부 데이터사이언스경영학과 | 데이터 | ohjimin0714@naver.com |

## 📅 진행 상태

- [ ] **Week 1** — 문화권 기반 초기 전략 설계 (Problem framing)
- [ ] **Week 2** — 시나리오 설계 및 보상 구조화 (AI augmentation)
- [ ] **Week 3** — 시뮬레이션 실행·감사·재설계 (S·A·R)

## 🚀 로컬 실행

```bash
# 1. 가상환경
python3.11 -m venv .venv && source .venv/bin/activate

# 2. 의존성 설치
pip install -r requirements.txt

# 3. Secrets 설정 (필요 시)
cp .streamlit/secrets.toml.example .streamlit/secrets.toml
# → 편집 후 API 키 입력

# 4. 앱 실행
streamlit run app.py
```

## 🧪 시나리오 검증

```bash
python scripts/validate_scenarios.py --file data/scenarios.json
```

`exit code 0` = 통과, 그 외는 CI에서 자동 실패 처리됩니다.

## 📂 폴더 구조

```
ethics-agent-game-<팀명>/
├── README.md
├── .gitignore
├── requirements.txt
├── app.py                      # Ethics Agent Game (강화학습)
├── narrative_app.py            # 시나리오 저작 앱
├── data/scenarios.json         # Week2 산출물
├── docs/
│   ├── week1/culture_report.md
│   ├── week2/scenario_review.md
│   └── week3/final_report.md
├── logs/
│   ├── ai_usage_log.md         # AI 사용 로그 (매 주차)
│   └── experiments/*.csv       # 시드 스윕 결과
├── scripts/validate_scenarios.py
├── schemas/scenario.schema.json
├── .streamlit/secrets.toml.example
└── .github/
    ├── workflows/ci.yml
    ├── PULL_REQUEST_TEMPLATE.md
    └── ISSUE_TEMPLATE/value_check.md
```

## 📚 참고

- 원본 강의자료: `05_source_materials/20251118_인공지능과경영_11주차_협동학습가이드.pdf`
- 워크북: `../../01_workbook/`
- 슬라이드: `../../02_slides/`
- 평가 루브릭: `../../03_rubric_xlsx/Week1-3_평가루브릭_통합.xlsx`

---

© 2026 강송희 교수 · 한국공학대학교 경영학부 · **CC BY-NC 4.0**
