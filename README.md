# 📚 Study Sets

매일 오전 9시·정오 12시·오후 6시(KST)에 Cowork 스케줄 작업이 자동 생성하는 학습 세트 아카이브입니다.

- 자료구조/알고리즘 1문제
- CS 면접 2문제 (운영체제·네트워크·DB·자료구조·디자인패턴)
- 정보보안기사 실기 3문제 (시스템·네트워크·앱·암호·관리·포렌식 순환)

게시 URL: <https://anveloper.github.io/study-sets/>

---

## 디렉토리 규칙

```
study-sets/
├── README.md         ← 이 파일 (사람용)
├── CLAUDE.md         ← Claude 스케줄 작업이 따라야 할 규칙
├── index.html        ← 자동 생성되는 글 목록 (최신순)
└── YYYY-MM/          ← 월별 폴더
    └── YYYY-MM-DD-HH-slot.html
```

### 파일 위치
- 모든 학습세트 HTML은 **`YYYY-MM/` 월별 폴더**에 둔다.
- 루트에는 `README.md`, `CLAUDE.md`, `index.html`, 월별 폴더만 둔다.
- 테스트/임시 파일도 해당 월 폴더에 둔다.

### 파일명 규칙
`YYYY-MM-DD-HH-slot.html` 형식.

| 시간대 | HH | slot |
|--------|----|----|
| 오전 9시 | `09` | `morning` |
| 정오 12시 | `12` | `noon` |
| 오후 6시 | `18` | `evening` |

예: `2026-05-28-12-noon.html` → 2026-05-28 정오 12시 세트

### 인덱스 페이지
루트 `index.html`은 매 푸시마다 **자동 재생성**된다. 모든 `YYYY-MM/*.html` 파일을 스캔해 최신순으로 나열하며, 손으로 편집하지 않는다.

---

## 생성 방식
Cowork(Claude Agent SDK 기반)에서 정의된 스케줄 작업 `daily-cs-security-study-set`이 매 회차 실행되어 Gmail 초안 생성 + 본 리포지토리 푸시를 수행한다. 작업 규칙은 `CLAUDE.md` 참고.
