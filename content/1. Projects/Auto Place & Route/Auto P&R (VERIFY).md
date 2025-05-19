## Verify (검증)
>[!definition]
>Place&Route 이후, 물리적 설계가 모든 [[DRC]], [[LVS]], Timing, [[IR Drop|IR]] 조건을 만족하는지 확인하는 단계

위 과정을 통과해야만 실제 [[Auto P&R (GDSII)|GDSII]]로 내보낼 수 있음.

### 검증 항목
[[DRC]](Design Rule Check) :
- 공정에서 요구하는 배선 간격, 폭, via 규칙 등 확인
[[LVS]](Layout vs Schematic) :
- 물리적 배선이 논리적 회로와 동일한지 비교
Antenna Check :
- Routing 중 긴 metal이 형성되어 트랜지스터 파괴 위험 여부 확인
Timing Verification :
- [[Setup&Hold Violation Check|Setup/Hold violation]] 여부 확인 (STA 기반)
[[IR Drop]] 분석
- VDD/GND 전압 강하 시뮬레이션 $\rightarrow$ 전원망 무결성 확인
[[EM(Electro Migration)]] 
- 금속에 전류 흐름이 과도해 배선이 파괴되는 현상 분석


다음 [[Auto P&R (GDSII)|GDSII]]