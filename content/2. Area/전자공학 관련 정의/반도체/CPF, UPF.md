# CPF(Common Power Format)
Cadence가 제안한 power intent 기술 포맷으로, 저전력 디지털 회로 설계에서 power domain, switch, cell control 등을 정의하는 언어입니다.

- **Cadence** 툴 체계에 최적화 되어있습니다.(innovus, Genus 같은)
- 기본 Syntax는 Tcl에 가깝지만 자체 구조화된 형식
- RTL과 별개로 존재하며, logic과 power intent를 분리해 설계 유연성을 확보합니다.

power-aware 구현 및 시뮬레이션, synthesis, STA에서 전력 조건을 정확히 반영하도록 보조합니다.

# UPF(Unified Power Format)
Accellera에서 제안한 포맷으로 **EDA 툴 간 호환성을 위한 공식적인 power intent 기술 포맷**이다.

- **Synopsys, Siemens, Cadence** 등 거의 모든 주요 툴에서 지원
- IEEE 표준으로 관리되어서 **호환성**이 좋다.
- Tcl 기반의 명령어 스타일
- 설계 단계별 refinement 가능(top-down, bottom-up 접근 모두 지원)

**RTL -> Gate -> Post -> Layout** 전 구간에서 일관된 power intent를 유지하면서 power-aware synthesis, simulation, STA, verification에 사용

> [!define] power_intent?
> 칩은 전기를 어떻게 쓸지, 어디를 꺼둘지, 어디는 항상 켜둘지, 꺼졌다 다시 켜질 때 어떻게 상태를 복구할지 등을 설계자가 계획해놓아야 한다. 이 계획이 바로 power intent다.

