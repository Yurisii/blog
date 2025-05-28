
셀에 Output에 연결된 전체 Capacitance를 의미한다.
1. 외부에 연결된 **Cell Cap**
2. 해당 **Cell까지 가는데 연결된 Wire Cap**
등이 있을 수 있는데, 해당하는 **모든 Capacitance를 합친 값**을 의미한다.

max capacitance와 index에 있는 capacitance 중 가장 큰 값이 일치하는 case가 ideal하다.

max capacitance보다 큰 값이 위치하면, 해당 값에 대한 범위를 벗어난다.

하지만 더 큰 문제는 max capacitance와 capacitance index 중 가장 큰 값과 차이가 나는 상황에서 발생한다.

max cap = 4ps, 이고 찾는 cap = 3.5ps 인 상황이라고 가정하자.

| Cap | 1ps | 2ps | 3ps |
| --- | --- | --- | --- |
이런 상황이라면 interpolation 으로 값을 계산할 수 없기 때문에 extrapolation으로 계산해 정확도가 많이 낮아지는 문제가 발생한다.



