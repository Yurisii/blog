>[!definition] Latch
디지털 회로에서 데이터를 저장하는 기본적인 메모리 소자. 주로 [[Flip-Flop|flip-flop]]과 비교되며, flip-flop과 달리 latch는 **클럭 신호 없이** 입력 신호의 상태에 따라 달라지는 점이 특징이다.

1. **작동 원리:**
   입력 신호(보통 Enable 또는 Control 신호)가 **활성화되어 있는 동안** 입력의 변화가 출력에 반영되며, 비활성화되면, 그 시점의 출력 상태를 유지한다.
   즉, 입력이 변할 때마다 무조건 상태가 바뀌는게 아니라, **제어 신호가 허용할 때만** 바뀐다.
2. **종류:**
   가장 일반적인 Latch는 **SR(Set-Reset) Latch**와 **D(Data) Latch**가 있다.
	   1. **SR Latch:** Set과 Reset 입력을 통해 상태를 설정하거나 초기화한다. NAND 또는 NOR 게이트를 기반으로 구성되며, 동시 활성화 시 **Invalid condition(Forbidden state)**가 발생할 수 있다.
	   2. **D Latch:** 하나의 데이터 입력(D)를 사용하며, Enable 신호가 활성화된 동안 입력 값을 출력에 반영한다. SR Latch의 문제점(불안정 상태)을 해결하기 위해 고안되었다.
3. **활용:**
   임시 저장이나, 클럭 없이 상태를 유지해야 할 때 사용되며, 주로 **비동기식 회로나 간단한 저장 요소**로 사용된다.
4. **동작 시점:**
   latch는 **level-sensitive**하며 입력이 활성화된 동안 출력이 지속적으로 변경될 수 있다. 플립플롭과 달리 **Edge**가 아닌 **신호의 레벨**에 반응하므로, **글리치나 노이즈에 민감**할 수 있다.

>[!reflection]
>**D vs SR**
>D Latch는 단일 입력이 있어서 Invalid condition이 없고 안정적이다. 
>SR Latch는 두 입력(Set, Reset)으로 작동하며 동시에 활성화되면 Invalid condition이 발생할 수 있다.