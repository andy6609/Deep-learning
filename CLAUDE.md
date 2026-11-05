# 강의 따라가기 학습 레포 — 작업 규칙

> 이 파일은 과목이 바뀌어도 그대로 쓸 수 있게 만든 공통 규칙이다.
> 과목별 정보는 맨 아래 "과목 정보" 섹션만 바꾸면 된다.

## 1. 사용자와 목표
- 사용자: 영국 대학 CS 학생, 한국인. 영어 강의를 최대한 영어로 받아들이고 싶어 함.
- 슬라이드를 하나도 빠짐없이 완벽히 이해하고 넘어가고 싶어 하는 성향.
- 공부 방식: **강의 영상(교수 말) 중심**으로 따라가고, 슬라이드는 보조. 퀴즈·워크시트는 강의 후 따로.

## 2. 폴더 구조
```
<repo>/
├── CLAUDE.md
├── Weekly/                     ← 슬라이드 보관함 (주차별)
│   └── weekNN/
│       ├── README.md           ← 강의 목록, 퀴즈, 읽을 범위
│       ├── slides/LNN-<주제>.pdf|.txt
│       └── transcripts/YYYY-MM-DD_LNN-LMM_<주제>.txt
└── Lecturely/                  ← 실제 수업 세션 단위
    └── YYYY-MM-DD_LNN[-LMM]/
        ├── LNN-<주제>.pdf      ← 그 수업에서 실제로 쓴 슬라이드
        ├── transcript.txt
        └── notes.md            ← 설명을 끼운 학습 노트
```

### 규칙
- 사용자가 **PDF만** 주면 → `Weekly/weekNN/slides/`에만 저장. Lecturely 폴더는 만들지 않는다.
- 사용자가 **"강의 제목(예: <과목코드>_..._9/21/2026) + 트랜스크립트"**를 주면 →
  1. `Lecturely/YYYY-MM-DD_LNN[-LMM]/` 생성 (날짜를 맨 앞에. `/`는 파일명에 못 쓰므로 `-`로)
  2. `transcript.txt` 저장 (Weekly의 transcripts에도 복사)
  3. 트랜스크립트 내용을 보고 **실제로 다룬 슬라이드**를 판단해 Weekly에서 복사 (한 수업에 두 강의를 할 수도 있음)
  4. `notes.md` 작성 (아래 형식)
- 원본 파일은 사용자의 Downloads 폴더에서 찾아 복사. 채팅에 텍스트로만 붙여넣은 자료는 .txt로 만들어 저장.
- 주차별 `README.md`를 갱신.

## 3. notes.md 형식 (강의 따라가기 노트)
트랜스크립트 흐름을 그대로 따라가며 아래를 끼워 넣는다.

```
### 📄 LNN slide K · <슬라이드 제목>      ← 교수가 지금 보고 있는 슬라이드

🎙️ <교수 원문 영어. 자동자막 오타는 바로잡아서>
→ <한국어 번역>

> 💡 <쉬운 설명: 지금 무슨 얘기인지, 슬라이드의 식/그래프, 숫자 예시>
> ⭐ 시험/중요 표시, "not part of the course"는 범위 밖이라고 표시

### 📌 단어
- *word*: 뜻
```

- 강의가 길면 **구간(Part)별로 나눠서** 채팅에 보여주고, 사용자가 "다음"이라고 하면 이어간다.
- 같은 내용을 `notes.md`에 계속 append.
- 자동자막 흔한 오타 예: aggression→regression, psychic/Esco learn→scikit-learn, theatre→theta, Walla→voilà.
- 학생 질문/답변 장면은 [학생 1] 식으로 정리.
- 교수 입버릇·영국식 표현·농담은 짚어서 듣기에 익숙해지게.

## 4. 설명 스타일
- **설명은 한국어, 전문 용어와 수식은 영어 그대로** (예: posterior, likelihood).
- 영어 슬라이드/원문 문장 아래에는 **직역**을 붙인다 (내용은 알아도 문장 구조가 헷갈릴 때가 많음).
- 추상적인 설명보다 **작은 숫자 예시로 직접 계산**해서 보여준다.
- 사용자가 "왜?"를 물으면 공식의 정의부터 거슬러 올라가 설명 (예: 분산의 정의 → 잔차 → N−p−1).
- 사용자가 "짧게"라고 하면 짧게.
- 범위 밖인 내용(교수가 "not part of the course"라고 한 것)은 명시해서 공부 우선순위를 알려준다.

## 5. Git
- 작업 단위마다 **커밋까지만** 한다. 푸시는 사용자가 직접(`git push`).
- 커밋 author는 레포 기존 author를 따른다.
- 사용자가 만든 파일(.DS_Store, 기타 미추적 파일)은 건드리지 않는다.

---

## 과목 정보 (과목마다 이 부분만 교체)
- 과목: COMS30035 Machine Learning (University of Bristol, 2026-27 TB-1)
- 교수: James Cussens / 교재: Bishop PRML (주), Murphy PML
- 강의 제목 형식: `COMS30035_2026_TB-1 - Machine Learning_M/D/YYYY`
- 시간표: 월 09:00, 화 11:00 강의 / 목 13:00 랩 / 목 17:00 drop-in
- 중간고사: 2026-10-28(수) 13:00, MVB 2.11, closed book, 1–5주차
- 시험 범위 참고: cribsheet (unit GitHub 페이지), Teams 'Past assessments'
