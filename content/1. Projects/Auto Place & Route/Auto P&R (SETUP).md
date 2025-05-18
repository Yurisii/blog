## SETUP
### P&R을 위한 파일
- 설계자 제공 파일
  1. netlist 파일 : 합성 결과물
  2. sdc 파일 : 디자인 제약 조건(CLK, In/out, fan etc)
- 공정사 제공 파일
  1. 디지털 라이브러리,[[LEF(Library Exchange Format)|lef 파일]]

### Design Import
1. Netlist 설정
2. Technology/Physical Libraries 설정
	`Library exchange format(.lef)`
    ==LEF 파일은 표준 셀/매크로의 물리적 정보(셀/핀 이름, 셀/핀 치수/ 차단 등)를 포함하는 물리적 라이브러리 파일==
3. Power/Ground net 설정
4. Analysis Configuration
	`MMMC(Multi Mode Multi-corner) View Definition File`
	==.lib, .sdc 를 기반으로 다양한 동작 모드와 다양한 공정/온도/전압 조건(이게 코너라고 부름)을 고려한 타이밍 분석을 위해, 어떤 타이밍 모델(lib)과 제약 조건(sdc)을 사용하는 지 지정하는 설정 파일 ==
	   
	`Timing Library (.lib)`
	==.lib 파일은 모든 표준 셀/매크로의 논리적 정보(설정 시간, 유지 시간, 셀 지연 등)를 포함하는 타이밍 라이브러리==
	   
	`max_delay, min_delay로 worst_case, best_case`  확인
_PnR에서 사용할 파일들의 위치를 알려주는 과정_
_min_delay, max_delay 선택 후, Setup, Hold Time에 대한 케이스를 등록을 해줘야 한다. _
_Setup&Hold 다시 보려면 여기 [[Setup&Hold Violation Check#1. 개념 정리]]_

다음 [[Auto P&R (FLOOR PLAN)]]