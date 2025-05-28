## 개요
- **정의**: SystemC는 시스템 수준 설계 및 시뮬레이션을 위한 C++ 기반 라이브러리입니다.
- **역사**: 1990년대 후반에 시스템 수준 모델링을 위해 개발되었습니다.
- **표준화**: IEEE 1666 표준으로 규정되어 있으며, 다양한 시스템 레벨 디자인을 지원합니다.

## 특징
- **기반 언어**: C++ 기반으로, 객체 지향 프로그래밍을 활용하여 시스템 수준 디자인을 구현할 수 있습니다.
- **모델링 능력**: 하드웨어와 소프트웨어가 통합된 시스템의 동작을 모델링하는 데 적합합니다.
- **멀티레벨 지원**: 비트 정확도 및 유닛 타임 모델링을 통해 다양한 디자인 레벨을 지원합니다.
- **확장 가능성**: 라이브러리와 병렬 처리를 통해 복잡한 시스템 설계가 가능합니다.

## Verilog/SystemVerilog와의 차이점
- **초점**: SystemC는 시스템 수준의 동작 및 성능 모델링을 목표로 하고, [[Verilog]]/[[SystemVerilog]]는 주로 하드웨어 설계와 검증에 집중합니다.
- **언어 기반**: Verilog/SystemVerilog는 HDL인 반면, SystemC는 C++ 라이브러리로 구현됩니다.
- **모델링의 심도**: SystemC는 하드웨어와 소프트웨어 통합 모델링을 강조하며, Verilog/SystemVerilog는 하드웨어의 논리적 설계 및 검증에 중점을 둡니다.

## 용도
- **시스템 수준 설계**: 하드웨어와 소프트웨어의 통합 설계 및 시뮬레이션에 적합합니다.
- **성능 검증**: 시스템의 성능 및 타이밍 검증을 위한 모의 실험을 수행할 수 있습니다.
- **아키텍처 연구 및 분석**: 시스템 아키텍처의 설계 및 최적화 과정에서 활용됩니다.
- **교육 및 학습 도구**: 시스템 수준 설계의 개념을 학습하는 데 사용됩니다.


## SystemC vs SystemVerilog

```C++
//System C
#include <systemc.h>

SC_MODULE(mux2to1) {
    sc_in<bool> a, b, sel;
    sc_out<bool> y;

    void process_multiplex() {
        y.write(sel.read() ? b.read() : a.read());
    }

    SC_CTOR(mux2to1) {
        SC_METHOD(process_multiplex);
        sensitive << a << b << sel;
    }
};
```


```Systemverilog
module mux2to1 (
    input logic a,
    input logic b,
    input logic sel,
    output logic y
);
    always_comb begin
        y = (sel) ? b : a;
    end
endmodule
```