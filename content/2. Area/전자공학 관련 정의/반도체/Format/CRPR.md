# Clock Reconvergence Pessimism Removal

**CRPR(Clock Reconvergence Pessimism Removal)** 은 디지털 회로 설계에서 시간 분석의 정확성을 높이기 위한 기법입니다. 이는 **경로가 겹치는 경우**, 최소 및 최대 지연 시간을 산출할 때 발생할 수 있는 불필요한 보수성(pessimism)을 제거합니다. 특히, **[[STA(Static Timing Analysis)]]** 도구인 **PrimeTime**을 통해 생성되는 리포트에서 활용됩니다.

> [!reflection]
> 겹치는 Path에서 min과 max를 모두 계산할 때 이미 convergence point가 있으면 어떤 point에서 부터 Delay를 계산할 것인지 설정하는 단계.

