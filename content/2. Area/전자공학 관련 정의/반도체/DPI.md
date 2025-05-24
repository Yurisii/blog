# SystemVerilog와 C/C++ 간의 연결: DPI란 무엇인가?
SystemVerilog에서는 PLI/VPI의 복잡함을 줄이고 외부 코드를 더 쉽게 호출하기 위해 DPI(Direct Programming Interface) 기능이 도입되었습니다. DPI는 SystemVerilog와 C/C++ 같은 외부 언어를 직접 연결해주는 인터페이스입니다. PLI나 VPI처럼 복잡한 과정 없이 SystemVerilog에서 곧바로 C 함수를 호출할 수 있도록 설계된 것이 특징입니다.

DPI를 사용하는 방법도 간단합니다. C로 구현된 함수를 SystemVerilog에 import로 선언해두면, 마치 내부 함수를 부르듯 바로 사용할 수 있습니다. 반대로 SystemVerilog 함수를 export로 지정하면 C 코드에서 호출하는 것도 가능합니다. 이렇게 기존에 C/C++로 만들어둔 라이브러리나 복잡한 알고리즘 코드를 손쉽게 재사용할 수 있습니다. 가령 Verilog로 구현하기 어려운 DSP(디지털 신호처리) 알고리즘이 이미 C로 작성되어 있다면, DPI로 그 코드를 불러와 시뮬레이션에 활용하면 됩니다.

**언제 DPI를 쓸까?** 실무에서는 대부분 외부 코드 연동에 DPI를 사용합니다. 특히 연산량이 많은 모델이나 기존 C/C++ 코드를 재사용할 때 유용합니다.

- 고속 연산 처리:
  복잡한 수치 연산이나 알고리즘을 C/C++로 구현하고 시뮬레이션에서 호출
- 기존 라이브러리 재사용:
  이미 검증된 오픈소스 C/C++ 라이브러리를 테스트벤치에 활용
- 소프트웨어 통합 검증: 임베디드 소프트웨어나 다른 시뮬레이터를 SystemVerilog 환경과 연동

DPI는 사용이 쉽고 오버헤드가 적어 시뮬레이션 성능 면에서도 유리합니다. 다만 VPI처럼 시뮬레이터의 모든 내부를 제어할 수 있는 것은 아니라서, 특정 신호 강제 변경이나 심층 디버깅 같은 작업에는 여전히 VPI가 필요합니다. 그래도 대부분의 외부 연동 요구사항은 DPI로 충분하기 때문에 처음에는 DPI부터 활용하는 것이 정석입니다. 

## DPI(Direct Programming Interface)
> [!definition]
>SystemVerilog와 C/C++ 간 통신을 할 수 있도록 도와주는 인터페이스.
>상호 간 task 혹은 function을 export/import 하여 사용할 수 있도록 하는 인터페이스

하드웨어 설계 후 검증을 위해 SystemVerilog를 가장 많이 사용할 텐데, C 만을 사용하여 하드웨어를 제어하는 데에는 
- 하드웨어 Access 자체가 어렵다.
- Delay를 모델링 할 수있다.

이러한 C 언어의 제약사항을 DPI를 통해 극복할 수 있다. C 코드에서 verilog로 작성된 task를 호출하여 사용하고, 혹은 그 반대로 SystemVerilog 코드에서 C로 작성된 함수를 호출하여 사용할 수 있다.

Import Method:
- 다른 프로그래밍 언어로 구현된 함수를 SystemVerilog 코드에서 호출되는 Method
Export Method:
- SystemVerilog로 구현된 메소드를 다른 프로그래밍 언어에서 호출하는 Method

>위 Method들에 argument를 pass & return함으로써, 서로 다른 두 언어 간 data를 주고 받을 수 있다.
