# 리버티 파일 (Liberty File)

리버티(Liberty) 파일은 디지털 반도체 설계에서 각 셀의 **논리 기능, 타이밍, 전력 특성**을 기술하는 표준화된 **텍스트 포맷** 파일입니다. 보통 `.lib` 확장자를 가지며, Synopsys에서 정의한 포맷을 따릅니다.

이 파일은 논리 합성(Logic Synthesis) 및 정적 타이밍 분석(Static Timing Analysis, STA) 과정에서 핵심적으로 사용되며, 설계 툴이 셀의 동작을 정확히 예측하고 최적화할 수 있도록 정보를 제공합니다.

---

## 주요 구성 요소

### 1. 셀 정의 (`cell`)
각 셀 단위로 구조가 정의되며, 이름, 핀 구성, 기능 등이 포함됩니다.
```liberty
cell (AND2X1) {
    ...
}
```

### 2. 핀 정보 (`pin`)
각 입력 및 출력 핀에 대한 방향, 커패시턴스, 출력 기능 등을 기술합니다.
``` liberty
pin (A) {
    direction : input;
    capacitance : 0.002;
}
pin (Y) {
    direction : output;
    function : "A & B";
}
```
### 3. 타이밍 아크 (`timing`)

입력 핀과 출력 핀 사이의 지연(delay) 및 전이 시간(transition time)을 기술합니다.
```liberty
timing() {
    related_pin : "A";
    cell_rise (...) ;
    cell_fall (...) ;
}
```
### 4. 전력 정보

셀의 **정적 누설 전력(leakage power)** 및 **동적 전력(dynamic power)** 소비 정보가 포함되어 전력 분석에 활용됩니다.

## 리버티 파일의 역할

- **논리 합성**  
    `.lib` 파일을 참고해 타이밍 조건을 만족하는 게이트를 선택하고 배치함.
    
- **정적 타이밍 분석 (STA)**  
    경로 지연 계산에 필요한 셀 내부 지연 및 트랜지션 정보를 제공.
    
- **전력 분석**  
    전력 최적화를 위해 셀의 정적 및 동적 전력 특성을 분석