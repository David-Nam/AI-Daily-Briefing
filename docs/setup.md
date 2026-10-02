# Cloud AI Daily Briefing 설정 및 검증

## 확인한 환경과 일정

- 실행: ChatGPT Work 웹 클라우드. Mac 전원·데스크톱 앱·로컬 checkout·SSH·로컬 스케줄러에 의존하지 않습니다.
- 저장소/브랜치: David-Nam/AI-Daily-Briefing / main.
- 일정: 평일 월–금 06:00, Asia/Seoul.
- AI Daily Briefing GitHub 예약: 활성. 2026-10-02에 최신 저장소 지시문을 읽는 프롬프트로 갱신했습니다.
- 조회 도구가 next_run_time을 반환하지 않아 다음 실행 시각은 직접 확인되지 않았습니다. 저장된 일정에서 계산한 다음 시각은 2026-10-05 06:00 KST입니다.
- 기존 AI Daily Briefing 예약도 최신 조회에서 활성입니다. 사용자가 Scheduled 화면에서 이전 예약을 일시 중지하면 중복 보고를 피할 수 있습니다. 새 흐름은 이전 예약을 자동 수정하지 않습니다.

## GitHub 연결

2026-10-02 쓰기 시험은 저장소가 GitHub App 허용 목록에 없어 처음 403 Resource not accessible by integration으로 실패했습니다. 사용자 추가 후 연결 도구의 생성과 원격 재읽기에 성공했습니다.

- 시험 파일: [docs/cloud-write-test.md](cloud-write-test.md)
- 시험 commit: 8569d153027c56d9248a87fe51614543864833f8
- 첫 실제 브리핑: [2026-10-02](../briefing/2026/10/2026-10-02.md)
- 첫 실제 commit: 4341785ab2c517da6c12a29d7aceb57493af0afa

403이 다시 발생하면 GitHub Settings → Applications → Installed GitHub Apps → 연결 앱 Configure에서 이 저장소가 선택되어 있고 필요한 Contents 쓰기 권한이 허용되어 있는지 확인합니다. 읽기 성공만으로 쓰기를 추정하지 않습니다.

## 모델 선택

초기 품질 기준은 GPT-6 Astra · Medium, 비용 비교 후보는 GPT-6.1 Sol · Extra high입니다. 이는 권장값이며 실제 예약 모델을 설정했다고 뜻하지 않습니다.

현재 연결된 예약 생성·수정·조회 도구에는 model/reasoning 필드가 없습니다. 실제 설정은 Work 또는 예약 편집 화면의 모델·추론 컨트롤에서 확인해야 합니다. 화면에 해당 컨트롤이 없다면 지정 가능 여부를 확인하기 전에는 모델을 확정했다고 보고하지 않습니다. YAML model 및 reasoning_effort는 런타임에서 확인할 수 없으면 unknown입니다.

같은 입력·동일 coverage_start/coverage_end로 comparison 실행을 비교하고 가장 가벼운 설정 중 품질 기준을 만족하는 것을 운영값으로 선택합니다. 모델 이름을 프롬프트에 쓰는 것으로 설정을 대신하지 않습니다.

## 재실행과 디버깅

- refresh(기본): 오늘의 complete 파일을 다시 작성해 같은 경로에 정상 update commit. 기존 coverage_start 유지, coverage_end 확장, revision 증가.
- comparison: 명시한 또는 이전 revision의 조사 시작·종료를 고정. 최신 뉴스라고 보고하지 않음. Git history로 이전 결과와 비교.
- 새 날짜: max(24시간, 이전 성공 이후 경과시간), 월요일은 금요일 이후 전체 구간.
- 불완전 파일·동시 변경·조사 실패: 이전 완성 결과를 자동 대체하지 않고 단계와 오류 보고.
- 파일 SHA를 직전 재조회하여 생성 당시 SHA와 비교. 바뀌면 덮어쓰지 않음.
- 브리핑 commit에는 그 날짜 파일 하나만 포함. 기존 파일은 delete/recreate하지 않음. force push 금지.

## 품질 및 저장 성공 기준

관심 분야와 네 세션의 상세 규칙은 [실행 지시문](../prompts/daily-briefing.md)에 한 곳에서 관리합니다. 예약 프롬프트는 이 파일을 매회 먼저 읽도록 구성합니다.

뉴스 원문 날짜와 사건일, 공식 주장과 독립 확인, practitioner 경험과 해석, 신규 소식과 과거 기술 참고 사례를 구분합니다. 부족한 세션은 두 번째 조사 후 한계를 기록합니다. Firmware에서는 실제 tool/repository와 작업 흐름을 확인합니다. 모델·조사 구간·prompt blob SHA·revision을 기록해 비교 가능하게 합니다.

후보가 품질 검사를 통과한 뒤 연결 GitHub create/update 도구로 main에 저장합니다. commit SHA 확보 후 main 및 가능하면 해당 commit에서 전체 내용을 재읽어 정확히 일치한 경우에만 저장 성공입니다. 예약 등록은 무인 실행 성공을 의미하지 않습니다. 첫 예약 실행 후 조사→쓰기→원격 검증까지 실행 기록을 확인해야 합니다.

## 공식 자료

- [Scheduled tasks](https://learn.chatgpt.com/docs/automations)
- [Models](https://learn.chatgpt.com/docs/models)
- [Model selection](https://learn.chatgpt.com/docs/model-selection)
