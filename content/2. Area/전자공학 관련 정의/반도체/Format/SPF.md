## SPF(Standard Parasitic Format)
- **정의**: 배선의 RC 성분(parasitic resistance, capacitance) 정보를 담고 있는 **표준 포맷**.
    
- **용도**:
    - PnR 완료 후 **정확한 타이밍 분석**(Static Timing Analysis, STA)을 위해 사용.
        
    - **Back-annotation** 용도로도 사용됨 (게이트 레벨 시뮬레이션 시 parasitic 정보 반영).
        
- **형태**: RC-net 형식으로 각 net에 저항과 커패시턴스를 지정.

## Usage
1. **[[Auto Place and Route 개요|P&R]] 이후**
   설계가 배치 및 배선 작업을 마친 후에 SPF 파일은 생성됩니다. 이 파일은 배치된 네트워크의 **기생 저항(parasitic resistance**)과 **기생 캐패시턴스(parasitic capacitance)**에 대한 정보를 포함합니다.
2. **STA**
   SPF 파일은 정확한 타이밍 분석을 위해 필요합니다. 기생 성분 정보가 포함된 파일을 통해, 설계의 각 경로에 대해 정확한 타이밍을 계산하고, 목표 성능을 만족시키는지를 검토할 수 있습니다.
3. **Back-annotation**
	게이트 레벨 시뮬레이션 시에는 실제 배선의 기생 효과를 반영한 시뮬레이션을 수행하기 위해 사용됩니다. 이는 설계의 기능이 원하는 대로 동작하는 검증하는데 유용합니다.


>[!reflection]
>SPF 파일은 반도체 설계에서 배선의 RC 정보를 포함하는 파일이다. 설계한 대로 정확하게 동작하고, 원하는 퍼포먼스가 나오는지 검증하는데 사용되는 중요한 도구이다. 
>==쉽게 말해, 설계가 제대로 작동하도록 돕는 배선의 RC 정보를 포함한 파일이다.==