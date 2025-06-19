# On Chip Variation
반도체 칩 내부에서 발생할 수 있는 **PVT** 변화에 의한 Delay의 **변동성을 고려**하여 **[[STA(Static Timing Analysis)]]**에서 더 정확하고 안전하게 설계 타이밍을 검증하기 위한 보수적 분석 기법이다.

## Why? OCV
현대 칩에서는 수백만 개의 셀과 수천 개의 경로가 있음. 이 경로들은:
- **같은 라이브러리 셀**을 사용해도
- **위치**나 **온도, 전압 조건**이 다르면
- 실제 **delay**가 달라질 수 있다.
이러한 변화를 반영하지 않으면, **STA**에서  slack이 충분하다고 나왔더라고 실제 실리콘에서는 timing violation이 발생할 수 있다.

그래서 **OCV를 고려해 경로별 delay에 margin을 추가해서 worst-case 상황을 안전하게 가정**함.

## Concepts
- OCV는 각 Cell이나 net delay에 대해 worst-case 가정을 적용.
- 예: 특정 셀 delay가 100ps인데, OCV margin 10%라면
  1. Launch path에서는 delay가 느려지게 (+10%) 적용
  2. Capture path에서는 delay가 빨라지게 (-10%) 적용
- 이렇게 하면 launch는 늦게 출발하고, capture는 빨리 도착하므로 slack이 줄어들고, 보수적으로 분석한다.


>[!note]
>**OCV는 반도체 칩의 PVT 변화에 따른 성능 변동성을 고려하여 설계 타이밍을 보수적으로 검증하는 기법**

처음에 OCV를 고려할 때는 간단한 derating factor를 사용했는데, margin을 너무 크게 잡는다는 문제 때문에 [[AOCV]]로 넘어가게 된다.