
# Systematic Variation
**예측 가능**하고 일정한 패턴을 가진 변화. 주로 **공정 장비**나 **설계** 단계에서 오는 **변수**.
- **OPC (Optical Proximity Correction)**: 포토리소그래피 시 optical distortion 보정을 위한 설계 기술. 하지만 보정이 완벽하지 않아 특정 패턴에서 systematic error 발생.
        
- **CMP (Chemical Mechanical Polishing)**: 금속층 평탄화 과정에서 칩 중앙과 가장자리의 물질 제거율이 달라, 두께 차이(systematic variation)가 생김.
        
- **Etching bias**, **layout pattern density**, **reticle field 위치 의존성** 등도 포함.

위치나 패턴에 따라 발생하기 때문에, 통계적 추정이나 모델링으로 보정할 수 있다.
# Non-Systematic Variation
**불규칙적**이고 **예측하기 어려운** 변수. **고유 생산 환경 노이즈**나, 미세한 **소재의 불균일성**이 여기에 해당한다.
- **RDF (Random Dopant Fluctuation)**: 트랜지스터 내 도핑된 이온 수의 확률적 차이에 따른 threshold voltage 변화.
    
- **LER (Line Edge Roughness)**: 게이트 등 패턴의 가장자리가 매끄럽지 않고 거칠어짐 → 채널 길이 불확실성.
    
- **OTV (Oxide Thickness Variation)**: 게이트 산화막 두께의 미세한 지역별 변화 → 전기적 특성 변화.
    
- **Work-function variation**, **Line width roughness (LWR)** 등도 해당.

**chip-to-chip**, **within-die**, 심지어 **transistor-to-transistor** 수준의 불균일성까지 발생한다. **예측 불가능하고, 평균화가 어렵기 때문에 worst-case 설계에 영향을 미침. **[[AOCV]], SOCV, POCV 등과 같은 **확률 기반 분석 기법**이 필요한 배경이 됨.

