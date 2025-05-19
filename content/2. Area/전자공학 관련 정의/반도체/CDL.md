## CDL(Circuit Description Language)
- **정의**: **회로 순서도(netlist)**를 기술하기 위한 언어 포맷.
    
- **역할**:
    
    - Layout에서 추출한 netlist와 **설계자의 원래 회로 schematic netlist**를 비교할 때 사용.
        
- **CDL 검사**:
    
    - **LVS (Layout vs. Schematic)**에서 핵심적으로 사용됨.
        
    - LVS 도구가 CDL netlist와 layout netlist를 비교해 **회로가 일치하는지 검증**.

## Usage
1. **회로 설계 초기 단계**
   - 설계자가 **회로의 초기 스케매틱(schematic)을 작성**할 때 CDL 형식의 netlist를 사용합니다.
2. **물리 설계 검증 단계 ([[LVS]] - Layout vs. Schematic)**
   - **회로의 layout이 완료된 후에** CDL netlist는 layout에서 추출된 netlist와 비교하여 설계의 정합성을 검증합니다.
3. **회로 비교 및 검증**
   - CDL은 설계자의 원래 회로와 layout 결과물을 상호 비교하여 **의도한 회로와 일치하는지 검증하는 과정**에서 사용됩니다.

### 예시
   **아래와 같은  회로가 있다고 하면**
> ```lua
  VDD
   |
   R1
   |
   +----- OUT
   |
   C1
   |
  GND
>```

이걸 CDL Netlist로 표현하면
>```
>* Simple RC circuit
R1 OUT VDD 1k
C1 OUT GND 10p
.END
>```
>- `R1 OUT VDD 1k`: OUT과 VDD 사이에 1kΩ 저항
>- `C1 OUT GND 10p`: OUT과 GND 사이에 10pF 커패시터

목적은 
>1. LVS용 기준회로
>2. 시뮬레이션 용도 (SPICE와 유사)


>[!reflection]
- 설계자가 Schematic으로 회로를 그리면, CAD Tool이 이걸 CDL 형식의 netlist로 추출한다. 나중에 LVS 시 비교 기준이 되는 회로가 CDL이다.
- CDL은 SPICE 호환 Format이기 때문에, 바로 회로 시뮬레이션에 쓸 수도 있다. 실제로는 .subckt 등을 포함해서 블록 단위로 기술된다.
- ==CDL이 정답, Layout은 답안 같은 느낌으로 LVS를 진행한다.==
- IP 블록, 라이브러리 셀, 메모리 등 모든 서브회로 검증용 기준이 되는 포맷
