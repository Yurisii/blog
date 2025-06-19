[[STA(Static Timing Analysis)|STA]] Report로 확인 할 수 있는 딜레이. 각 cell이나 net간 delay를 나타낸다.
### **Incr (Incremental Delay)**

- Incr은 **이전 셀의 출력(Output)부터 현재 셀의 입력(Input)까지의 지연 시간**을 의미한다.
    
- 즉, 타이밍 경로 상에서 해당 셀 또는 핀까지 **추가로 발생한 지연**을 나타낸다.
    
- 이 값은 일반적으로 **Cell Delay + Net Delay**의 합으로 구성된다.

## 목적

- **지연 병목 파악**
    - 타이밍 경로에서 **Incr 값이 급격히 증가하는 구간**은 병목 지점일 가능성이 높다.
- **타이밍 최적화 포인트 식별**
    - Incr 값이 큰 셀이나 넷(Net)은 **지연 최적화 대상**이 될 수 있다.
- **경로 병목 개선**
    - Incr이 큰 부분에 대해 **버퍼 삽입, 셀 크기 조정, Re-[[Auto P&R (CTS&ROUTE)#Route|routing]]** 등을 고려하여 지연을 개선할 수 있다.

>[!reflection] 
>**방금 지나온 구간에서 발생한 delay**, 전체 delay만 안다면, 어느 구간에서 **delay**가 확 늘어났는지 모른다. 그래서 **병목 현상이 일어나는 지점**을 찾기 위한 단서다.
>문제 지점을 찾고 **Cell을 교체**하거나, **Re-routing** 하거나, **Buffer를 삽입**해 신호 보강이 가능하다.