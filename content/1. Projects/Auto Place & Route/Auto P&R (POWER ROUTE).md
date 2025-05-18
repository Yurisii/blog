## Power Route
### 목적
Power Plan 단계에서는 전체적인 전원 구조(Ring, Stripe)를 구성했지만, Standard Cell 내부까지 실제로 전원이 연결된 상태는 아니다.

→ ==그래서 Power Route 단계에서는 각 셀에 실제로 VDD/VSS 전원이 닿도록 배선 경로를 연결해줘야 한다.==
이걸 _**Special Routing**_ 이라고 부른다.

### Power Route 원리
Standard Cell Row에는 이미 VDD, VSS 레일이 존재하지만, 이 레일이 Power Stripe 또는 Power Ring과 직접 연결되어 있지는 않다.
그래서 Power Route는 이 레일들을 Stripe와 연결해주는 **다리** 역할을 한다.
전원망은 일반 신호망과 달리
- 매우 넓은 금속층을 사용([[IR Drop]] 방지)
- 가급적 직선 경로, 최단 거리, 고정된 metal layer 사용.
- 라우팅 리소스를 차지하지 않도록 특수 배선(non-timing driven) 으로 처리된다.
  _전원망 설계에서는 데이터 신호의 시간 지연보다는 안정적인 전력 공급이 더 중요합니다. 그래서 신호 타이밍을 고려하지 않고, 전원이 잘 연결되도록 설계하는 것을 비타이밍(non-timing driven) 설계라고 합니다._

### 중요성
| 이유                  | 설명                                           |
| ------------------- | -------------------------------------------- |
| ==전류 흐름 완성==        | Stripe에서 셀까지 전류가 실제로 흐를 수 있어야 회로 동작 가능       |
| ==IR Drop 분석 가능==   | 실제 연결이 있어야 다음 단계에서 IR Drop 시뮬레이션 가능          |
| ==전원 integrity 확보== | VDD/GND 신호가 weak하게 연결되어 있으면 logic failure 위험 |

다음 [[Auto P&R (PLACEMENT)|Placement]]
