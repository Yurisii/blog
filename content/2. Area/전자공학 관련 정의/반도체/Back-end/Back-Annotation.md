레이아웃 후에 R,C 값을 추출하는 작업

실제 **physical design 이후**의 정확한 parasitic 정보 및 delay 데이터를 functional simulation이나 [[STA(Static Timing Analysis)]]에 반영하기 위한 **필수 절차**이다. Logic Synthesis 단계에서는 library 기반의 추정 delay를 사용하지만, 실제 layout 이후의 net length, fanout, [[Output Loading Capacitance|load capacitance]], interconnect resistance 등의 영향으로 delay는 크게 달라질 수 있다. 따라서, 정확한 timing verification을 위해 post-layout data를 simulation 및 analysis 단계에 feedback하는 과정이 필요하다.

이를 위해 [[반도체 설계 과정#back-end|P&R]] tool은 extracted parasitic 및 cell delay 정보를 포함한 [[SDF(Stdandard Delay Format)|SDF(Stdandard Delay Format)]] 파일을 생성한다. 이 파일은 gate-level simulation(GLS) tool 또는 STA tool(PrimeTime)에 입력되어, 실제 chip의 동작에 근접한 타이밍 특성을 시뮬레이션 할 수 있도록 한다.

Back-annotation은 [[Setup&Hold Violation Check|setup/hold timing violation]] 검출, functional verification, power estimation, yield optimization 등 최종 signoff 단계에서 핵심적인 역할을 수행한다. 정확한 delay 정보를 기반으로 함으로써, **overly possimistic design margin**을 줄이고 **성능 최적화**를 달성할 수 있다.

>[!reflection]
>타이밍 분석이라고 하면 그냥 시뮬레이션에서 delay 값 보고 timing met 했는지만 확인하는 건 줄 알았다. 하지만 **실제 칩 설계에서는 배치 배선 후에 delay가 확 달라질 수 있다**는 점이 중요해 보인다. 특히 **Back-annotation**이라는 개념은 말 그대로 '**물리 정보를 다시 가져와서 시뮬레이션에 반영한다**'는 말인데, 이게 단순하게 데이터 입력이 아니라, **layout의 parasitic**을 **실제 timing 분석에 연결**해주는 핵심 단계라는 걸 이제 좀 알겠다.
>
>P&R tool에서 나온 SDF 파일을 simulation tool에 넣는 과정을 통해 gate-level simulation을 더 현실적으로 할 수 있다는 게 신기하다. 단순히 기능이 맞는지 보는 게 아니라, 그 기능이 실제 타이밍 조건에서 안정적으로 동작하는 지를 검증하는 거니까, 이게 실제로 tape-out 전 마지막 단계에서 굉장히 매우 매우 중요하다! 를 배우고 간다.

