## UPI(Unified Programming Interface)
- **정의**: 
	- 여러 시스템, 언어, 또는 툴을 하나의 통일된 인터페이스로 다룰 수 있게 하는 API 또는 구조
		여가선 ==Cadence의 OA(OpenAccess) DB에 접근하기 위한 **표준화된 API 인터페이스**.==
    
- **목적**:
    
    - EDA 툴 간 **interoperability** 확보.
        
    - 툴 개발자가 특정 툴에 종속되지 않고 **OA 형식으로 설계 데이터를 읽고 쓸 수 있도록** 지원.
        
- **실제 사용 예**:
    
    - **custom EDA 툴을 개발**할 때, UPI를 통해 OA 기반 라이브러리나 레이아웃 정보를 읽음.
        
    - **Verdi, IC Compiler, Innovus** 등의 툴과 연계 시 내부적으로 활용됨.


OpenAccess 기반 설계 데이터에 접근하거나, 조작하는 데 사용되는 C++ API의  집합

UPI는 Cadence에서 제공하는, OA 데이터베이스에 접근할 수 있도록 설계된 API 프레임워크로, EDA 개발자가 자신의 툴을 OA와 연동하기 위해 사용하는 공식 인터페이스이다.

>[!reflection]
쉽게 말해, 고객사가 Cadence Tools을 이용하고 툴체인에 Cadence가 아닌 A 회사의 툴이 맞물려 있다면, 고객은 OA를 이용하면 편하게 작업할 수 있을 것이다. 하지만 ==A 회사가 Cadence가 아니라면 OA에 직접 접근할 수 없기에, 대신 UPI 같은 공식 인터페이스를 사용해서 OA 데이터를 읽고 쓰게 할 수 있다.==
>
>추가로 **site-lisence**는 카피 단위로 툴을 계약하는 게 아니라, 일정 기간 동안 기업 전체가 툴을 무제한으로(카피 수 상관없이) 사용할 수 있는 라이센스이다.


>[!chat-gpt]
> **Unified Programming Interface란?**
> 
>"Unified Programming Interface"는 말 그대로:
> 여러 시스템, 언어, 또는 툴을 하나의 **통일된 인터페이스**로 다룰 수 있게 하는 API 또는 구조
입니다. 
>SystemVerilog 같은 HDL 환경에서는 이런 UPI가 보통 아래와 같은 목적을 가집니다:
 >
 >**예: UPI in EDA (Electronic Design Automation)**
EDA 툴 벤더들(Cadence, Synopsys, Siemens 등)은 종종 ==[[SystemVerilog]] 시뮬레이터==와 C/C++ 코드, Python, DPI-C, PLI, 또는 ==UVM 등의 연동을 위해 자체적인 UPI 레이어==를 제공합니다.
