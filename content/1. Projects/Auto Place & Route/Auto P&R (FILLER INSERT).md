## Filler Insert
### 목적
Placement와 Routing 이후 남는 빈 공간에 **Filler Cell**을 삽입하여 셀 간 전원 연결을 연속적으로 유지하고, DRC 오류를 방지하는 단계

### 동작 원리
**왜 빈 공간이 생기는가:**
- Standard Cell은 일정한 크기로 구성되지만,placement 시 ==타이밍이나 혼잡도 등을 고려해 완벽하게 채워지지 않는다==.
- 따라서 Routing 후 일부 공간이 비어있게 된다.
**왜 채워야 하는가:**
- Well/Implant DRC 방지 : 셀 사이 N-Well이나 P-Well이 끊기면 DRC 발생
- Power Rail 연속성 확보 : 셀들의 VDD/VSS 연결이 단절되지 않도록 filler를 이용해 metal rail을 연장

다음 : [[Auto P&R (VERIFY)|Verify]]