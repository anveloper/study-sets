# CLAUDE.md — 스케줄 작업 규칙

이 리포지토리에 파일을 추가/수정하는 스케줄 작업(`daily-cs-security-study-set`)이 반드시 따라야 할 규칙입니다.

## 파일 위치
- 새 학습세트 HTML은 **반드시 `YYYY-MM/` 월별 폴더에** 저장.
- 월 폴더가 없으면 `mkdir -p YYYY-MM`으로 생성.
- 루트에 학습세트 HTML을 두지 말 것. 루트는 `README.md`, `CLAUDE.md`, `index.html`, 월별 폴더만.

## 파일명
`YYYY-MM-DD-HH-slot.html` (KST 기준)
- 시간대 매핑:
  - 06:00 ~ 11:59 → `09-morning`
  - 12:00 ~ 14:59 → `12-noon`
  - 15:00 ~ 23:59 → `18-evening`

## 인덱스 갱신
- 푸시 직전 **`index.html`을 자동 재생성**한다.
- 인덱스는 `find . -path './YYYY-MM/*.html' -not -name 'index.html'` 결과를 **파일명 역순(최신순)** 으로 나열.
- 손으로 편집한 인덱스 변경분은 덮어쓰여진다 (의도된 동작).

## 인덱스 디자인
블로그 글 목록 스타일. 다음 항목을 한 줄씩:
- 날짜(`YYYY-MM-DD`)
- 시간대 한국어 라벨(오전 9시 / 정오 12시 / 오후 6시)
- 상대 경로 링크 (`YYYY-MM/filename.html`)
- 월별 헤더로 그룹화

## 커밋 메시지
`Add study set: YYYY-MM-DD HH-slot` 형식.

## 푸시 전 체크리스트
1. `YYYY-MM/` 디렉토리 존재
2. 새 HTML 파일이 그 안에 있음
3. `index.html`이 새 파일을 포함하도록 재생성됨
4. `README.md`, `CLAUDE.md`는 건드리지 않음

## 충돌 시
- `git pull --rebase` 후 재푸시. 동시에 두 회차가 겹치는 일은 거의 없지만 안전장치.
