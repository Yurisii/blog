
>[!definition] DEF
>**Design Exchange Format(DEF)** is a specification for representing physical layout of an intergrated circuit in an ASCII format. It contains netlist, component placement and routing information about IO pad cell to bump cell connectivity.

P&R의 결과를 표현하는 표준 파일 형식이다. 칩 안에 어떤 셀이 어디에 있고, 이 셀들 사이의 배선이 어떻게 연결되어 있는지를 정의하는 파일이다.
- **[[Auto P&R (FLOOR PLAN)#FLOOR PLAN|Floorplanning]]** : 칩의 전체적인 레이아웃과 주요 블록(Macro)의 위치 계획
- **[[Auto P&R (PLACEMENT)#Placement|Placement]]** : Standard Cell들의 구체적인 위치 지정
- **[[Auto P&R (CTS&ROUTE)#CTS(Clock Tree Synthesis)|CTS(Clock Tree Synthesis)]]**: 클럭 신호를 전달하는 네트워크 구성
- **[[Auto P&R (CTS&ROUTE)#Route|Routing]]** : Cell들을 연결하는 배선 경로 설정

#### LEF와의 관계
DEF를 이해하기 위해선 **[[LEF(Library Exchange Format)]]** 파일과의 관계를 꼭 알아야 한다.
- **LEF (재료 명세서):**
  칩 설계에 사용할 수 있는 **부품들(Standard Cells, Macro, I/O Pad 등)의 물리적 특성(크기, 모양, 핀 위치)**을 정의한 **'부품 카탈로그'**이다.
- **DEF (조립 설명서):**
  LEF에 정의된 부품들을 가져와 **실제 칩 위 어디에(Placement), 어떻게 배치하고(Orientation), 어떻게 연결했는지(Routing)**를 알려주는 **'조립 설명서'**이다.

**==LEF가 무엇을 사용할 수 있는지 알려준다면, DEF는 '그것을 어디에 어떻게' 사용했는지를 보여준다.==**

#### DEF 역할과 활용
1. **[[Auto Place and Route 개요|P&R]] Tool 최종 산출물 :**
   Cadence Innovus, Synopsys IC Compiler와 같은 P&R 툴이 모든 물리 설계를 완료한 후 내보내는 최종 결과물.
2. **후속 검증 단계의 핵심 입력 데이터:**
   - **Physical Verification** : 완성된 레이아웃에 [[DRC]], [[LVS]] 할 때 사용된다.
   - **[[Sign-off]]** : 실제 배선에서 발생하는 Delay와 RC 값을 추출해, 칩이 목표 Timing과 전력 소모 기준을 만족하는 지 최종 분석 시 사용한다.
1. **제조 데이터 생성의 기반:**
   DEF 정보를 바탕으로 Fab에 보낼 최종 마스크 제작용 데이터([[Auto P&R (GDSII)|GDSII]] or OASIS)가 생성된다.

>[!reflection]
>DEF는 ASIC 설계에서 물리적인 Layout 정보를 포함하는 파일 format. 이 파일은 회로의 placement, routing 정보를 나타내며, 디자인 데이터를 물리적인 위치와 크기로 변환하는 데 사용된다. 레이아웃 도구들은 DEF 파일을 입력으로 사용하여 디지털 회로의 물리적인 배치와 라우팅을 구성하고, 실제 반도체 칩을 제조할 때 필요한 정보를 추출한다.

``` def
VERSION 5.8 ;

DESIGN my_chip ;
UNITS DISTANCE MICRONS 2000 ;

DIEAREA ( 0 0 ) ( 100000 100000 ) ;

COMPONENTS 3 ;
- U1 AND2X1 + PLACED ( 15000 20000 ) N ;  # U1 이라는 이름의 AND2X1 셀을 (15000, 20000) 좌표에 북쪽(N) 방향으로 배치
- U2 DFFX1  + PLACED ( 15000 30000 ) N ;  # U2 이라는 이름의 DFFX1 셀을 (15000, 30000) 좌표에 배치
- U_MACRO_SRAM my_sram + PLACED ( 50000 50000 ) FS ; # 매크로를 배치
END COMPONENTS

PINS 2 ;
- clk + NET clk + DIRECTION INPUT + LAYER M5 ( 0 0 ) ( 100 200 ) + PLACED ( 0 50000 ) N ;
- dout + NET dout + DIRECTION OUTPUT + LAYER M5 ( 0 0 ) ( 100 200 ) + PLACED ( 100000 40000 ) N ;
END PINS

NETS 2 ;
- clk ( PIN clk ) ( U1 A1 ) ( U2 CLK ) ; # clk 넷은 외부 clk 핀, U1의 A1핀, U2의 CLK핀을 연결
- n1 ( U1 ZN ) ( U2 D ) ; # n1 넷은 U1의 ZN핀과 U2의 D핀을 연결
END NETS

SPECIALNETS 2 ;
- VDD ( * VDD ) ... ; # VDD 전원망 배선 정보
- VSS ( * VSS ) ... ; # VSS 접지망 배선 정보
END SPECIALNETS

# 라우팅 정보가 여기에 추가됨 (ROUTED 섹션)
# 예: + ROUTED M2 ( 15200 28000 ) ( 15200 31000 ) ...

END DESIGN
```
