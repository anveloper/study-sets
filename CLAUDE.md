# CLAUDE.md — 스케줄 작업 규칙

이 리포지토리에 파일을 추가/수정하는 스케줄 작업(`daily-cs-security-study-set`)이 반드시 따라야 할 규칙입니다.

## 파일 위치
- 새 학습세트 HTML은 **반드시 `YYYY-MM/` 월별 폴더에** 저장.
- 월 폴더가 없으면 `mkdir -p YYYY-MM`으로 생성.
- 루트에 학습세트 HTML을 두지 말 것. 루트는 `README.md`, `CLAUDE.md`, `index.html`, 월별 폴더만.

## 파일명 (HHMM 방식)
`YYYY-MM-DD-HHMM.html` — **실제 실행 시각(KST)** 을 그대로 사용.
- 예: 9:00 정각 실행 → `2026-05-28-0900.html`
- 예: 11:08에 Run now → `2026-05-28-1108.html`
- 같은 날 여러 번 실행돼도 파일 충돌 없음.
- HHMM은 4자리 zero-padded.

## 인덱스 갱신
- 푸시 직전 **`index.html`을 자동 재생성**한다.
- 인덱스는 `cowork-data/build-index.sh` 스크립트를 사용 (HHMM/legacy 양쪽 명명 모두 처리).
- 손으로 편집한 인덱스 변경분은 덮어쓰여진다 (의도된 동작).

## 커밋 메시지
`Add study set: YYYY-MM-DD HHMM` 형식.

## 푸시 전 체크리스트
1. `YYYY-MM/` 디렉토리 존재
2. 새 HTML 파일이 그 안에 있음 (HHMM 명명)
3. `index.html`이 새 파일을 포함하도록 재생성됨
4. `README.md`, `CLAUDE.md`는 건드리지 않음

## 충돌 시
- `git pull --rebase` 후 재푸시.
