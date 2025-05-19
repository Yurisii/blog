## POWER PLAN
setup에서는 각각의 환경에서 칩이 어떻게 동작하는지(.sdf, .lef, .lib, .netlist)
floor plan에서는 chip의 동작에 따라 구성할 건지 크기 결정

### Global Nets
Power Planning 이전에 Connect Global Nets를 실행한다. 
- netlist의 Power/Ground와 P&R에서 Power/Ground를 알려줘야 한다.
- netlist에서 VDD/VSS를 확인하고 없으면 netlist에 선언하고 저장한다.

>[!reflection]
>==innovus== 에서는 
>**netlist**에서 작성한 Pin name(VDD, VSS)을 넣고
>**global net**에서는 import에서 Power/Ground  nets(VDD, VSS)를 넣어준다.
>global net은 _VDD, VSS로 명시하면, Power Ring, Stripe, Tap Cell 등이 이 net을 기준으로 생성된다._
>_또한 CLK같은 전역 클락도 global net으로 등록하면 CTS가 해당 net을 clock source로 인식한다. _
>Pin 할당은 여러가지 방법이 있으나, starting point를 주고 offset 값으로 설정하는 것이 가장 편리하다.

### Power Planning?
칩 전체에 ==VDD와 VSS를 안정적으로 분배==하기 위한 ==구조를 설계==하는 과정
_[[IR Drop]], [[EM(Electro Migration)]] 등의 [[PI(Power Integrity)|신호 무결성(Power Integrity)]] 이슈를 방지하는 것이 목적._

- 모든 인스턴스에 충분한 전력 및 접지를 공급하는 글로벌 전력 분배 네트워크 설계 프로세스
- 칩의 ==여러 부분에 필요한 전력을 전달하는데 필요한  Metal Layer== 선택이 포함
- 부적절한 전력 분배로 인해 과도한 전압 강하 및 타이밍에 영향을 미침
- 해결을 위해 충분한 VDD 및  VSS 패드를 제공하여 디바이스의 전원 공급 보장

| 구성 요소                        | 설명                                  |
| ---------------------------- | ----------------------------------- |
| ==Power Ring==               | 코어 영역 바깥쪽에 VDD/VSS를 분리된 큰 사각형으로 둘러침 |
| ==Power Stripe==             | 코어 내부에 수직/수평으로 VDD/VSS 라인을 그리드처럼 배치 |
| ==Tap Cell / Endcap Cell==   | Substrate 연결, ESD 방지용 셀 배치          |
| ==Standard Cell Power Rail== | 각 Row마다 VDD/GND 가로 전력선 제공           |
| ==Via, Metal Layer==         | 층간 전력 연결을 위해 다층 배선 필요               |

### Power Planning 순서
1. **Power Ring 생성**:
   Add Ring - Core 중심으로 외곽에 큰 전원 틀 만들기
2. **Power Stripe 생성**:
   Add Stripe - Core에 Power/Ground가 잘 들어갈 수 있도록 내부 수직/수평 라인 형성(격자 구조)
3. **[[Tap Cell#Tap Cell|Tap Cell]] 삽입**:
   [[Latch-up]] 방지, [[Tap Cell#Well Tie|Well Tie]]용 셀 삽입

- 모든 인스턴스에 충분한 전력 및 접지를 공급하는 프로세스(필요한 metal layer 포함)
- Cell 마다, Block 마다 동일한 전력을 공급하기 위한 배치를 구성

다음 : [[Auto P&R (POWER ROUTE) | Power Route]]