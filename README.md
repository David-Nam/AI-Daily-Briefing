# AI Daily Briefing

ChatGPT Work 웹 클라우드에서 한국어 AI 브리핑을 생성하고 한국 시간 기준 날짜별 Markdown으로 GitHub에 저장합니다.

## 구조

```text
briefing/YYYY/MM/YYYY-MM-DD.md   # 실제 브리핑; 같은 날짜는 revision 갱신
samples/2026-10-02.md            # 형식 예시, 실제 뉴스 아님
prompts/daily-briefing.md        # 관심 분야·조사·저장 규칙의 단일 기준
docs/setup.md                   # 클라우드 예약 설정 및 검증 안내
docs/cloud-write-test.md        # 쓰기 시험; 실제 브리핑 아님
```

## 운영 원칙

- 날짜·시간은 Asia/Seoul이며 네 세션을 한국어로 작성합니다.
- 매 실행마다 연결된 GitHub 도구로 main의 실행 지시문을 먼저 읽습니다.
- 기본 refresh 모드는 같은 날짜의 complete 파일도 전체 재작성하여 정상 업데이트 커밋으로 갱신합니다. Git history에 이전 결과가 남습니다.
- 같은 날은 coverage_start를 보존하고 조사 종료 시각을 확장합니다. 새 날짜는 최소 24시간 또는 이전 성공 이후 전체 구간을 조사합니다.
- 고정 조사 구간의 comparison 모드로 프롬프트·모델을 비교할 수 있습니다. 실제 모델 설정은 프롬프트로 바뀌지 않습니다.
- 공식 원문과 practitioner 증거, 실제 Firmware 도구 사례를 구분해 확인합니다. 샘플과 시험 파일은 성공 기록에서 제외합니다.
- 조사 실패·불완전 파일·동시 변경은 자동 덮어쓰지 않습니다. 다른 파일을 같은 브리핑 커밋에 포함하거나 force push하지 않습니다.
- main과 가능하면 작성 commit에서 원격 내용을 다시 읽어 일치한 경우에만 저장 성공으로 알립니다.

## 현재 상태

2026-10-02: GitHub 연결 앱에 저장소 접근을 추가한 후 클라우드 파일 생성·원격 재읽기에 성공했습니다. 실제 브리핑도 저장·검증했으며, v2.0 실행 지시문에 기존 네 세션 관심 분야와 강화된 조사·재실행 규칙을 병합했습니다.

AI Daily Briefing GitHub 예약은 평일 월–금 06:00, Asia/Seoul, 활성 상태입니다. 예약 프롬프트는 실행마다 이 저장소의 최신 지시문을 읽습니다. 무인 예약의 새 지시문 실행과 모델 선택은 아직 별도 확인이 필요합니다. 기존 AI Daily Briefing 예약은 자동 수정·중지하지 않습니다.

[설정 안내](docs/setup.md) · [실행 지시문](prompts/daily-briefing.md)
