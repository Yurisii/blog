# NLDM(Non-Linear Delay Model)
NLDM은 기존의 타이밍 모델링 방식. 각 셀의 Delay를 Lookup table(LUT) 형식으로 저장.
입력 조건에 따라 지연이 Linear하게 변하지 않기 때문에 이 Delay를 미리 측정해서 table에 저장해 놓는 것
입력 조건 (index1:slew) + 출력 조건(index2:load)에 따라 Delay가 달라진다.

# NLPM(Non-Linear Power Model)
셀이 작동하면서 소비하는 Power를 모델링한 방식
Power Consumption이 input 조건이나 output loading capacitance에 따라서 non-linear하게 변하기 때문이다.

- switching power : 출력이 변할 때 consumption
- internal power : 내부 회로의 전류 흐름으로 인한 consumption
- leakage power : 아무 동작이 없어도 트랜지스터 누설로 인한 소비

NLPM은 이러한 전력 소비를 상황별로 측정해서 저장한 것이고, 이 역시 slew나 load 같은 조건에 따라 다르게 측정된다.

# CCS(Composite Current Source Model)
NLDM / NLPM 보다 정밀한 셀 모델링 방식
전류 기반 모델로, 시간에 따른 전류 흐름 자체를 기반으로 셀의 동작을 모델링한다.

실제 Transistor 수준 시뮬레이션에서, output pin에 흐르는 current waveform을 추출해서, 이 파형을 기준으로 출력 전압의 변화를 예측한다.
보다 정밀한 타이밍/전력 예측이 가능하다.
