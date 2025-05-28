## SDC

>[!definition]
>SDC (Synopsys Design Constraints)는 논리 합성(Synthesis), 배치 및 배선(PnR), STA(Static Timing Analysis)을 위한 타이밍 제약 파일(`.sdc` 확장자)입니다.

### 타이밍 제약 정보
- 설계 내 클럭 구조, 입출력 지연, 타이밍 예외 등을 정의합니다.
- 주요 제약 항목:
  - `create_clock`: 클럭 생성
  - `set_input_delay`, `set_output_delay`: 입출력 지연 정의
  - `set_false_path`, `set_multicycle_path`: 타이밍 예외 설정
- 이러한 제약은 타이밍 분석 정확도를 높이고, 툴이 불필요한 경로를 최적화 대상에서 제외할 수 있게 도와줍니다.

### 타이밍 예외 정보
- False Path, Multicycle Path 등은 물리적으로 연결되어 있어도 논리적 타이밍 검사를 생략하거나 완화해야 하는 경로에 적용됩니다.
- 예를 들어:
  - 서로 다른 클럭 도메인 간의 경로
  - scan/테스트 회로 경로
  - 클럭 게이팅 회로 등

### 툴이 사용하는 방식
- 논리 합성 시: 클럭 및 타이밍 범위를 기준으로 최적화 수행
- PnR 중: Slack 기반 배치 및 배선 경로 선택
- STA 시: 경로 별 Setup/Hold 분석 기준으로 사용

### SDC의 역할 요약
- 설계자의 타이밍 의도를 툴에 전달하는 명세서 역할
- 경로 지연, 클럭 정의, 타이밍 분석 범위를 제어
- PnR 품질과 STA 정확도를 결정하는 핵심 요소

> [!reflection]
> SDC는 설계자가 원하는 타이밍 요구사항을 툴에 전달하는 핵심 수단이다. 클럭 정의부터 예외 처리까지 모두 포함되며, SDC의 정확성과 완성도가 전체 타이밍 품질을 좌우한다.

>[!question] Liberty랑 sdc랑 뭐가 다른거지? 둘 다 타이밍 정보 아니야?
> 맞아. 둘 다 타이밍과 관련된 정보야. 하지만 정보의 성격이 달라.
> - .lib는 셀 자체의 물리적 특성
> - .sdc는 디자이너가 의도한 시스템 레벨의 제약
> 즉, liberty는 셀이 실제로 얼마나 느린지를 말해주는 데이터고, 
> sdc는 그 느린 것을 감안해서 어디까지 알려주는 기준이다.
> 실제로 STA에서 
> 1. `LIB` -> 각 셀의 delay, slew, setup/hold 값을 정의
> 2. `SDC` -> 클럭, 입력 지연, 경로 예외 조건 등 설계 의도를 알려준다.
> 3. STA tool은 liberty를 이용해 delay를 계산하고, sdc 제약을 기준으로 slack을 계산한다.

