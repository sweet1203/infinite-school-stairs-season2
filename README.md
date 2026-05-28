# Infinite School Stairs Season 2

노트북/데스크톱 가로 화면 전용 영어 타자 게임입니다.  
시즌1(무한 계단)은 그대로 두고, 시즌2는 별도 레포에서 완전히 다른 장르로 구성했습니다.

## 게임 규칙

- **A 단계 (기초 타임어택)**: 5분 제한 안에 최대 점수 달성
- **B 단계 (심화 서바이벌)**: 시간 제한 없음, 오답 5회 누적 시 게임 종료
- 정답 시 단어 길이만큼 점수 획득
- **오타 1글자 허용(단어 모드)**: 5글자 이상 단어는 레벤슈타인 거리 1까지 부분 점수 인정
- WPM, 정확도, 콤보, 오답 수 실시간 표시
- **월별 필터**: 3월/6월/9월/10월/전체 선택 가능
- **문장 모드**: 단어 3개 조합 또는 고정 문장 타이핑 연습
- **시즌2 랭킹 분리 저장**: Firebase `rankingsSeason2` 경로 사용 (실패 시 로컬 폴백)

## 단어 소스

게임 내부 단어 풀은 아래 시험 범위를 기반으로 구성했습니다.

- 2025년 3월 모의고사 영어 어휘
- 2025년 6월 모의고사 영어 어휘
- 2025년 9월 모의고사 영어 어휘
- 2025년 10월 모의고사 영어 어휘

> 참고: 공개된 기출 어휘 정리 자료를 바탕으로 게임 플레이에 맞게 단어를 선별/정제했습니다.

## 실행

```bash
npx serve -p 8788 .
```

브라우저에서 `http://localhost:8788` 접속.

## Firebase Rules 배포

시즌2 랭킹은 Realtime Database의 `rankingsSeason2` 경로를 사용합니다.

```bash
firebase login
firebase deploy --only database
```

`database.rules.json`이 배포되면 시즌2 랭킹 저장/조회가 정상 동작합니다.

## 프로젝트 구조

```text
infinite-school-stairs-season2/
├── index.html
├── manifest.json
├── sw.js
├── icon.svg
├── icon-192.png
└── icon-512.png
```
