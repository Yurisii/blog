# [[Liberty]] Variation Format
공정 변화가 심해지면서, 단일 값이 아닌 통계적 분포를 갖는 타이밍/전력 모델의 필요성이 대두되었다. LVF는 이러한 공정 변화의 영향을 모델링하여 통계적 정적 타이밍 분석([[SSTA|SSTA, Statsitcal Static Timing Analysis]])을 지원한다. [[Liberty Modeling Method#NLDM(Non-Linear Delay Model)|NLDM]], [[Liberty Modeling Method#CCS(Composite Current Source Model)|CCS]], [[Liberty Modeling Method#ECSM(Effective Current Source Model)|ECSM]] 모델 모두 LVF 형태로 제공 가능

>[[POCV]] 데이터를 정의하는 format, 분포 기반 모델로 [[OCV]] 표현 Delay, Slew, Timing Constraints의 변동성을 모델링하기 위한 정보
> - Cell Delay:
>   input slew, load에 따라 달라짐. [[데이터 통계#평균 (Mean, μ)|mean]], [[데이터 통계#표준 편차 (Standard Deviation, σ)|sigma]]
> - Slew:
  Cell의 output slew에 대한 변동성
> - Timing Constraints:
  input slew와 load에 따른 타이밍 제약의 변동성


각 지연 요소나 전력 소비가 고정된 값이 아니고 **확률 분포로 표현**되기 때문에, 실제 제조 공정에서 발생할 수 있는 다양한 변동성을 보다 정확하게 반영할 수 있다. 이를 통해 칩 설계자는 최악의 상황뿐만 아니라 **평균적인 성능**이나 **수율**까지도 **예측**할 수 있으며, 보다 최적화된 설계를 도출할 수 있다. LVF는 기존의 타이밍/전력 모델에 비해 분석 정확도는 높이고, **과도한 보수적 마진은 줄일 수 있는** 현실적인 모델링 방식이다.

>[!reflection]
>NLDM이나 CCS 모델처럼 기존에 배운 타이밍 모델들은 고정된 delay를 기준으로 분석했지만, 실제 공정에서는 그런 이상적인 조건이 거의 없다. 그렇기에 LVF는 delay나 전력을 확률 분포로 표현함으로써, 실제 반도체 제조에서 생기는 공정 편차나 환경 변화 같은 **불확실성을 더 현실적으로 반영**할 수 있는 것!
>특히 SSTA는 처음 본다. 근데 단순하게 worst-case만 보는 게 아니라, 평균이나 분산 같은 통계적 특성을 이용해서 전체 칩의 수율이나 성능을 예측할 수 있게 해준다.
>이런 접근 방식이 공정 미세화가 더 심해질수록 중요한 방식이라고 생각.


