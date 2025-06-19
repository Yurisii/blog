[[Liberty|Liberty 파일]]에 **셀에 특성을 저장**하는 **모델링 방식**들
쉽게 말하면 셀의 사용 설명서나 성능표의 더미
# NLDM(Non-Linear Delay Model)
**NLDM**은 기존의 **타이밍 모델링** 방식. 각 셀의 Delay를 **Lookup table(LUT)** 형식으로 저장.
입력 조건에 따라 지연이 **Linear하게 변하지 않기 때문**에 이 **Delay를 미리 측정**해서 table에 저장해 놓는 것
입력 조건 (index1:slew) + 출력 조건(index2:load)에 따라 Delay가 달라진다.

# NLPM(Non-Linear Power Model)
셀이 작동하면서 **소비하는 Power를 모델링**한 방식
**Power Consumption**이 **input 조건**이나 **[[Output Loading Capacitance|output loading capacitance]]**에 따라서 non-linear하게 변하기 때문이다.

- **switching power** : 출력이 변할 때 consumption
- **internal power** : 내부 회로의 전류 흐름으로 인한 consumption
- **leakage power** : 아무 동작이 없어도 트랜지스터 누설로 인한 소비

NLPM은 이러한 **전력 소비를 상황별로 측정**해서 저장한 것이고, 이 역시 slew나 load 같은 조건에 따라 다르게 측정된다.

# CCS(Composite Current Source Model)
NLDM / NLPM **보다 정밀한** 셀 모델링 방식
**전류 기반 모델**로, **시간에 따른 전류 흐름 자체를 기반**으로 셀의 동작을 모델링한다.

실제 Transistor 수준 시뮬레이션에서, output pin에 흐르는 current waveform을 추출해서, 이 파형을 기준으로 출력 전압의 변화를 예측한다.
보다 정밀한 타이밍/전력 예측이 가능하다.

# ECSM(Effective Current Source Model)
CCS와 마찬가지로 **전류원 기반 모델**이지만, 데이터를 표현하고 사용하는 방식이 다르다.

CCS는 Current Waveform을 샘플링해서 저장하지만, ECSM은 특정 기준 부하(Reference Load)에 대한 드라이버의 출력 **전압 파형을 샘플링**하여 **저장**하는 경우가 많다. (다만, 내부적으로는 전류원 모델을 사용하는 것은 유사)

- **출력 파형 표현:**
  CCS는 전류 파형을 직접 저장하고, 이를 적분해서 전압 파형을 얻었다. ECSM은 특정 조건에서의 전압 파형을 저장하고, 다른 부하 조건에 대해서는 이 기준 파형을 스케일링하거나 조정하여 사용하기도 한다.
- **Zero Load Handling:**
  ECSM은 이론적으로 부하가 0(Zero Load)인 경우부터 모델링이 가능하다고 알려져 있지만, CCS는 특정 최소 부하 이상에서 특성화되는 경우가 일반적이다.
- **Library Congestion:**
  경우에 따라 ECSM 라이브러리가 CCS보다 단순하거나 데이터 양이 적을 수도 있지만, 이는 벤더나 특성화 방식에 따라 다를 수 있다.

**정확도:**
CCS와 ECSM은 **일반적으로 NLDM보다 높은 정확도**를 제공하며, 둘 사이의 정확도 차이는 기술 노드, 셀 특성, 툴 구현 방식 등에 따라 달라질 수 있다. 종종 CCS와 ECSM은 **서로 변환이 가능한 형태로 간주되기도 하지만, 변환 과정에서 정확도 손실**이 있을 수 있다.

**사용:**
CCS와 마찬가지로 정밀한 타이밍 분석, 전력 분석, 노이즈 분석 등에 사용된다.


