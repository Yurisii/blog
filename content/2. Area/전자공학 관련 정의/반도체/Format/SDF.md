# Standard Delay Format

SDF는 cell과 interconnect의 propagation delay, interconnection delay, constraint (setup/hold, recovery/removal), timing check, 그리고 path delay 등 static timing 특성 전반을 구조화된 방식으로 써놓은 포맷이다. 이를 통해 layout 이후에 추출된 parasitic-aware timing data를 정확히 simulation 환경이나 timing analysis 도구에 주입해서 사용할 수 있다.

**특징**

- **정확성(Accuracy)**: parasitic extraction 및 P&R 툴의 타이밍 characterization 결과를 기반으로 생성되므로, 실제 배선 기반 delay를 정밀하게 반영한다.
    
- **호환성(Interoperability)**: 대부분의 시뮬레이션 및 STA 툴에서 지원하며, netlist-level에서 타이밍 back-annotation이 가능하다.
    
- **구조화된 표현**: ASCII 기반 계층적 표현으로 사람이 해석 가능하고, tool 간 연동이 용이하다.
    

 기본 구조 예시


```
(DELAY
	(ABSOLUTE 
		(IOPATH A Z (0.15:0.17:0.20) (0.12:0.14:0.16))   
	) 
)
```

이 예시는 A에서 Z로의 I/O 경로에 대해 **rising과 falling delay**가 각각 **min:typ:max**의 형태로 주어짐을 나타낸다. 해당 정보는 timing arc 단위로 precision을 갖는 지연 모델링을 가능하게 한다.

#### Typical Flow Integration

1. **Place & Route Tool** (e.g., Synopsys IC Compiler II, Cadence Innovus) → SDF Generation
    
2. **Simulation Tool** (e.g., Synopsys VCS, Siemens ModelSim) → SDF Back-annotation for gate-level timing simulation
    
3. **Static Timing Analyzer** (e.g., PrimeTime, Tempus) → Annotated STA with SDF timing
    

#### 활용 의의

SDF는 layout-dependent timing behavior를 functional simulation이나 STA에 정확히 반영함으로써, **signoff-level의 타이밍 검증을 가능하게 하는 핵심 전달 매커니즘**이다. 특히 multi-corner, multi-mode (MCMM) 환경에서는 각 조건에 맞는 SDF를 생성해 분석 정확도를 극대화한다.