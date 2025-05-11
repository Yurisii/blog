---
Verlog: " "
---
**먼저 중요한 말은, Verilog로 회로를 설계할 때 크게 3가지로 구성됩니다.**

1.  **assign**
2.  **always**
3.  **instantiation**
**이 세 가지로 회로 설계의 모든 게 가능하다고 합니다.**

---

### ASIC Design Flow
ASIC Design Flow를 보고 들어갑니다.

![](https://blog.kakaocdn.net/dn/kHIen/btsJNtppFcj/8lNVv9rGxC4XKv0kJv5NZ0/img.png)
*ASIC Design Flow*

---

### Buffer(CTS, Fan out)

![](https://blog.kakaocdn.net/dn/bfML68/btsJLVne9iY/GQwcZF6k9rbcYOcPNg7SBk/img.png)
*CTS(Clock Tree Synthesis)*

CLK을 사용하는 각각의 Register는 들어오는 CLK과 물리적인 거리의 차이가 있습니다. 그렇기 때문에 그 거리에 따른 CLK 오차 손실(Skew)을 줄여주기 위해 CLK이 빨리 들어오는 Register에 Buffer를 두어 속도를 맞추는 방법이 있습니다.

CLK이 다르게 들어올 수 밖에 없는 이유는 CLK는 Chip 내부에서 만드는 것이 아니라 칩 밖에 **Crystal**에서 만들어, Chip으로 들어옵니다. Chip에 들어오면 **PLL(Phase Locked Loop)**를 통해 들어온 CLK의 Phase, Hz 등을 늘리거나 줄여 목적에 맞는 CLK을 Chip 내부에 Register로 보내게 됩니다.

#### Fan out

![](https://blog.kakaocdn.net/dn/tjBCc/btsJLI2Lm6I/j56rUv1uXI8M8QnjcRZy50/img.png)
*Fan out*

이 외에도 Buffer를 사용하여 Fan out을 증가시키는 방법이 있습니다.

**Fan out**은 한 개의 논리 게이트의 출력이 몇 개의 논리 게이트의 입력으로 들어갈 수 있는지를 말합니다, 왜냐하면 소자의 출력단에 걸 수 있는 전류의 제한이 있기 때문입니다. 그래서 그 사이에 Buffer를 배치하여 Fan out을 증가 시킬 수 있는 방법도 있습니다.

---

### SoC(System on Chip)

![](https://blog.kakaocdn.net/dn/OnTfv/btsJMig9kxn/WlkTgTJ7y13EihsRl50mA1/img.png)

**uP(마이크로 프로세서)를 BUS로 연결해 사용.**
**HW는 빠른 프로세싱을 위한 외부장치(FPGA) HW 가속기라고 볼 수 있음.**
**IO를 통해 uP로 갖고오는데, DMA(Direct Memory Access)를 사용하면 기존 1 Cycle로 사용하는 것이 아니라 주고받는 일을 DMA로 넘겨서 일을 시키는 방법.**
**DMA 내부에 FIFO를 사용해 Cycle마다 Memory에 저장.**

#### zybo_z7_20에서 nand_gate.v 작성

##### design source 생성

![](https://blog.kakaocdn.net/dn/NIbOd/btsJKhdv0qO/yhCH8wRafpoKad1WqRXUD1/img.png)

##### IO 포트 설정용 .xdc(constraint) 코드 작성

xdc = Xilinx Design Constraint

![](https://blog.kakaocdn.net/dn/cdVYA1/btsJKdh2JEK/O2dKf94Zmq1MdSBmfjabz0/img.png)


![](https://blog.kakaocdn.net/dn/ojn1z/btsJLTBYvSj/kPDHMZlvVQCGr2yTft2XK1/img.png)


![](https://blog.kakaocdn.net/dn/ccVxjB/btsJLjnMUdE/9mKk6HwbEIAm7L8a0N8vRK/img.png)


![](https://blog.kakaocdn.net/dn/b3uKr3/btsJLQk7kiw/5wKQuZSFKk7T6du1HxJgi1/img.png)

```
set_property PACKAGE_PIN Y16 [get_ports A]
set_property PACKAGE_PIN K19 [get_ports B]
set_property PACKAGE_PIN D18 [get_ports X]

set_property IOSTANDARD LVCMOS33 [get_ports A]
set_property IOSTANDARD LVCMOS33 [get_ports B]
set_property IOSTANDARD LVCMOS33 [get_ports X]
```
pin 연결 및 3.3V 설정

##### Generate Bitstream

##### Open Hardware Manager 및 Auto Connect

##### Program Device

보드로 업로드합니다.
![](https://blog.kakaocdn.net/dn/eouSF5/btsJLhEyOhz/SXueZ4OCUXrlJLDkTxikVK/img.png)
![](https://blog.kakaocdn.net/dn/b8cH6B/btsJLBCIDeF/PNE5P1Mx7GuBacyJXRDgmk/img.png)
*좌 : NAND 입력 0, 0으로 켜진 LED 우 : NAND 입력 1, 1로 꺼진 LED*

#### Block Design Flow

![](https://blog.kakaocdn.net/dn/AtOuV/btsJK3lvg0w/aL2KKkEH8hV5puDhmEg4rk/img.png)

![](https://blog.kakaocdn.net/dn/4xLJd/btsJLyL3gXW/b46cNeyYlbSjLndKSXPez0/img.png)

##### Clocking Wizard 선택

![](https://blog.kakaocdn.net/dn/bKOrKa/btsJMjf80HX/4aeWfPK5hSpC3Sz0G43xKk/img.png)

Clock 신호는 Chip 밖에서 생성됩니다.
Zybo-z7-20은 125MHz를 생성합니다.
여기서 Clocking Wizard가 PLL(Phase Locked Loop) 역할을 합니다.

##### Counter 추가

![](https://blog.kakaocdn.net/dn/wtqAa/btsJLGwpYQX/AMKPLOz2KHmskwFrv3oZq1/img.png)

![](https://blog.kakaocdn.net/dn/bMnjQs/btsJKLMaj7y/0y67pfdB4SkSv0K98bOqlK/img.png)

![](https://blog.kakaocdn.net/dn/d8OjlE/btsJLxmaBYL/A1tCQOovNEMEI4qRaQmjnK/img.png)

##### CLK Divider 코드 작성

```verilog
module clk_divider (
    input clk_in, 
    output clk_out
);
reg[31:0] o=32'd0;
reg clk_out=1'b0; 
parameter DIVISOR = 32'd6000000;
//clk_out = clk_in / DIVISOR

always @(posedge clk_in) begin
   
   if(o == DIVISOR/2-1) begin
       o <= 0; 
       clk_out <= ~clk_out; 
   end 
   else o <= o + 1; 
end
endmodule
```
o값이 2,999,999가 되면 0으로 초기화하는 CLK counter입니다.
clk_out을 2,999,999마다 반전시켜 clk_out 생성합니다. (6MHz clk을 counter를 이용해 1Hz로 변경)

![](https://blog.kakaocdn.net/dn/uNaAd/btsJMdtH5Zj/KKUOKjclX7wKFdwkgsvm60/img.png)
*125MHz > 6 MHz > 1Hz > 초당 1씩 증가하는 카운터*

![](https://blog.kakaocdn.net/dn/bfQRLj/btsJK7VORoL/Du52parnB6LweTQhVQrieK/img.png)

![](https://blog.kakaocdn.net/dn/PXIb8/btsJMjgcrfI/AoyQEQd4OKf5eqRH1KxeAK/img.png)

##### CLK_Divider Parameter 변경

![](https://blog.kakaocdn.net/dn/drcLdR/btsJLVGWCtx/4h427p0ODmHykDUsZtq2t1/img.png)

##### Binary Counter 변경

![](https://blog.kakaocdn.net/dn/b0ACcR/btsJLTCnMzQ/oAMAqOfz2nWUv3J6LPLIU0/img.png)

![](https://blog.kakaocdn.net/dn/eaWX1G/btsJKIvs7dm/PwsqGp83NWRwBeHSJcpKB1/img.png)
이름 변경.
이처럼 reset, clk도 포트 생성 및 이름 변경합니다.

![](https://blog.kakaocdn.net/dn/d1HL2u/btsJMiIm07j/V4hEyQYQtdbM3sDmW1q7Tk/img.png)

##### Validation Check

##### Constraint(.xdc) 파일 생성 (top.xdc)

```xdc
set_property PACKAGE_PIN K17 [get_ports clk]
set_property IOSTANDARD LVCMOS33 [get_ports clk]

set_property PACKAGE_PIN Y16 [get_ports reset]
set_property IOSTANDARD LVCMOS33 [get_ports reset]

set_property PACKAGE_PIN M14 [get_ports {LED[0]}]
set_property PACKAGE_PIN M15 [get_ports {LED[1]}]
set_property PACKAGE_PIN G14 [get_ports {LED[2]}]
set_property PACKAGE_PIN D18 [get_ports {LED[3]}]
set_property IOSTANDARD LVCMOS33 [get_ports {LED[*]}]
```

전체 Diagram을 wrapper로 모듈 v파일로 만듭니다.
Generate bitstream > Auto Connect > Program Device > Program 순으로 진행합니다.

---

### SoC 구성
1.  **Processor(MCU, DSP core, multiprocessor)**
2.  **Memory(ROM, RAM, EEPROM, Flash Memory)**
3.  **Clock(oscillator, PLL)**
4.  **Peripherals(counter-timer, GPIO)**
5.  **External Interface (USB, Ethernet, USART, SPI)**
6.  **Analog Interfaces (ADCs, DACs)**
7.  **Voltage Regulator, PMIC**
8.  **BUS Interface**
9.  **DMA Controller**

---

### Hardcore & Softcore

#### Hardcore
1.  설계부터 내부에 넣어둠.
2.  Implementation defined in silicon
3.  CPU system already present in silicon

즉, Hardware Processor는 이미 설계가 결정되어 공정까지 끝마친 uP를 의미한다.

#### Soft Core
1.  그 후에 변경해서 사용(Programable Logic)
2.  HDL 설명에 정의된 구현
3.  CPU 시스템 구현에 필요한 FPGA 프로그래밍

즉, Softcore Processor는 S/W로 완전히 설명되는 uP로, 일반적으로 HDL로, FPGA와 같은 프로그래밍 가능한 하드웨어에서 합성 가능함.

#### Softcore 장점
1.  필요한 기능만 포함해서 넣을 수 있습니다.
2.  Core의 수를 유연하게 조절 가능합니다.
3.  차세대 FPGA에서 디자인을 다시 사용할 수 있습니다.
#### Softcore 단점
1.  Hardcore보다 느리고 간단할 수 있습니다.
2.  Hardcore에 비해 면적 효율성이 떨어짐(Firm IP)

---

### HLS(High Level Synthesis)

**C to HDL로 설계하는 방법**

1.  HLS가 math.h 지원하기 때문에 HDL로 짜기 힘든 설계가 가능해진다. ex) 행렬곱, Sin, Cos
2.  AI로 인한 수요 증가. (병렬처리용 모델을 만들기 좋다. = 곱셈기를 만들기에 좋다.)

---

### Register = F/F

![](https://blog.kakaocdn.net/dn/dquM1n/btsJLR6pw92/DWmUTWkRj2lKuIwEIzOhzK/img.png)

**Tc = Clock 1주기 시간**
**Tcq = Clock이 Register로 들어가서 q로 나오는 시간**
**Tpd = C.L이 갖는 Delay**


**Tcq + Tpd + Tsetup < Tc**


언뜻 보면 F/F를 여러 개를 두어 나누지 말고, 한 번에 처리하는 방식을 생각할 수 있습니다. 하지만, 한 번에 처리하면 오류가 생길 가능성이 높고, F/F로 일을 나누어 처리하면 얻는 이득이 있습니다. 사람이 분업을 하는 것처럼 F/F도 각자의 업무를 나누어 처리한다고 생각하면 편합니다.

1.  **Scheduler : 일 하는 Timing을 나누어 줍니다.**
2.  **Pipelining : 일 처리 속도를 올려줍니다.**
3.  **저장 : 값을 저장하는 역할을 합니다.**

---

### STA(Static Timing Analysis)

**Violation이 있는지에 대한 Design Check를 위한 STA를 3단계로 나눌 수 있습니다.**

1.  Timing Path 집합으로 설계 분류
2.  각 Path의 Propagation Delay 계산
3.  설계와 Input/Output Interface에서 Timing constaraints의 Violation 여부 Check
STA Tool에서 각각의 모든 Start point에서 End point까지의 Path를 분석하여 주어진 constraint와 비교합니다. 결국 모든 Path는 제한되어야 하며, 대부분의 경로는 Clock 주기의 정의와 회로의 주요 입력 및 출력의 Timing 특성에 의해 제한됩니다.

Timing Path는 signal type에 따라 나뉩니다.

-   Asynchronous path
-   Data path
-   Clock path
-   Clock-gating path

여기서 Clock-gating path를 조절하여 Dynamic Power를 줄일 수 있습니다.

Power는 크게 두 가지로 나뉩니다.

-   Dynamic Power(신호가 바뀔 때 마다 소모되는 Power = 동작시키는 전력 소모)
-   Static Power(전원 공급으로 상시 들어가는 Power = 전원 코드만 꽂은 전력 소모)

Clock-gating path를 통해 회로의 일부에 들어가는 Clock을 끊어 회로를 끄고 켜서 전력 소모를 줄이기 위한 Path입니다.