
---

사실 제 전공과 Computer Architecture는 밀접한 관련은 없습니다.

일을 시작하면서, 이 부분을 좀 배우고 오면 좋겠다는 의견이 있어서 Chat GPT를 이용해서 중요 내용만 빠르게 공부하면서, 해당 내용을 블로그에 정리하려 합니다. 추가로 OS도 조금 공부해서 정리할 예정입니다.

[https://product.kyobobook.co.kr/detail/S000006082876](https://product.kyobobook.co.kr/detail/S000006082876)

공부한 교재.

  

우리는 Computer라는 말을 너무 당연하게 사용합니다. Compute는 동사로 "계산하다"라는 뜻입니다. 영문 뜻을 살펴보면,

> to calculate an answer or amount by using a machine:

즉 기계를 사용해서 답이나 수량을 계산하는 작업을 Compute라고 합니다.

이러한 역할을 수행하는 기계를 Computer라고 하겠죠?

그럼 들어가 보겠습니다.

---

### **Computer**

---



> "A computer is a machine that can be instructed to carry out sequences of arithmetic or logical operations automatically via computer programming."

컴퓨터란, 프로그래밍을 통해 산술 또는 논리 연산의 일련의 과정을 **자동으로 수행하도록 지시할 수 있는 기계**이다.

  

컴퓨터는 스스로 동작할 수 있게 만드는 '프로그램 가능한 자동 기계'라고 합니다.

  

교재에서는 컴퓨터 아키텍처를 이해하는 데 핵심이 되는 8개의 아이디어를 소개합니다.

  

1. **무어의 법칙에 맞춰 설계하기** (Design for Moore’s Law)
2. **추상화를 사용하여 설계 단순화하기** (Use Abstraction to Simplify Design)
3. **공통 경로를 빠르게 만들기** (Make the Common Case Fast)
4. **병렬성으로 성능 향상** (Performance via Parallelism)
5. **파이프라이닝으로 성능 향상** (Performance via Pipelining)
6. **예측을 통한 성능 향상** (Performance via Prediction)
7. **메모리 계층 구조 사용** (Hierarchy of Memories)
8. **여유를 통한 신뢰성 확보** (Dependability via Redundancy)

몇 가지만 간략하게 살펴보면.

**Use Abstaction to Simply Design**

> Both computer architects and programmers had to invent techniques to make themselves more productive, for otherwise design time would lengthen as dramatically as resources grew by Moore’s Law. A major productivity technique for hardware and soft ware is to use abstractions to represent the design at diff erent levels of representation; lower-level details are hidden to off er a simpler model at higher levels. We’ll use the abstract painting icon to represent this second great idea.

컴퓨터 아키텍트와 프로그래머 모두 **자신들의 생산성을 높이기 위해 기술을 발명해야 했다**. 그렇지 않으면, 무어의 법칙에 의해 자원(resource)이 늘어나는 만큼 **설계 시간이 비약적으로 늘어났을 것**이다. 하드웨어와 소프트웨어 모두에서 **생산성을 높이는 주요 기술**은, **추상화(abstraction)를 사용하여 설계를 여러 수준(level)의 표현으로 나누는 것**이다. 하위 수준의 세부사항은 숨기고, 상위 수준에서는 더 단순한 모델을 제공한다.

  

**Make the Common Case Fast**

> Making the common case fast will tend to enhance performance better than optimizing the rare case.  
> Ironically, the common case is often simpler than the rare case and hence is often easier to enhance.

**공통적인 경우를 빠르게 만드는 것이**, 드문 경우를 최적화하는 것보다 **성능을 더 효과적으로 향상**시킨다.  
아이러니하게도, **공통적인 경우가 드문 경우보다 더 단순한 경우가 많기 때문에**, 최적화하는 것도 더 쉽다.

  

**Performance via Prediction**

> Following the saying that it can be better to ask for forgiveness than to ask for permission, the final great idea is prediction. In some cases, it can be faster on average to guess and start working rather than wait until you know for sure, assuming that the mechanism to recover from a misprediction is not too expensive and your prediction is relatively accurate.

"허락을 구하는 것보다 용서를 구하는 것이 낫다"는 속담처럼, **마지막으로 중요한 아이디어는 '예측(prediction)'이다**. 일부 경우에는, **확실해질 때까지 기다리는 것보다, 일단 추측하고 작업을 시작하는 것이 평균적으로 더 빠를 수 있다**. (단, 잘못된 예측을 복구하는 비용이 크지 않고, 예측의 정확도가 상대적으로 높다는 전제 하에서.)

  

**Performance via Pipelining**

> A particular pattern of parallelism is so prevalent in computer architecture that it merits its own name: pipelining.  
> For example, before fire engines, a "bucket brigade" would respond to a fire, which many cowboy movies show.  
> The townsfolk form a human chain to carry a water source to the fire, as they could much more quickly move buckets up the chain instead of individuals running back and forth.

**컴퓨터 아키텍처에서 매우 흔한 병렬 처리 패턴이 있는데**, **그것이 바로 '파이프라이닝(pipelining)'이다**. 예를 들어, 소방차가 등장하기 전에는, **"버킷 브리게이드(bucket brigade)"** 방식으로 불을 껐다. (이 장면은 서부극 영화에서도 자주 나온다.) 마을 사람들은 **사람들의 체인(chain)을 이루어**, 양동이를 나르는 식으로 물을 옮겼다. **한 사람이 계속 오가며 이동하는 것보다**, 체인으로 전달하는 방식이 훨씬 빠르기 때문이다.

  

파이프라이닝은 제 다른 포스팅에서 다룬 적 있습니다.

[https://chanfifo77.tistory.com/100](https://chanfifo77.tistory.com/100)

[

  

[Verilog] Verilog를 이용한 AI 설계 응용 및 SoC 설계 (2)

https://chanfifo77.tistory.com/99 [Verilog] Verilog를 이용한 AI 설계 응용 및 SoC 설계 (1) chanfifo77.tistory.com 이전 포스팅의 마무리인 STA부터 이어서 작성하겠습니다.STA로 모든 경로를 전수조사 할 때, 최단

chanfifo77.tistory.com



](https://chanfifo77.tistory.com/100)

---

### **Below Your Program**

---

![](https://blog.kakaocdn.net/dn/BS0rp/btsNA8wgD5x/Vpx2OxPZGEti08OOmgYzIK/img.png)

A simplifi ed view of hardware and software as hierarchical layers, shown as concentric circles with hardware in the center and applications software outermost.

> Programs are translated into a sequence of very simple instructions that the hardware understands.  
> Software layers exist between the high-level language and the hardware, mainly **compilers** and **operating systems.**  
> High-level languages enable programmers to be more productive and portable across different hardware.

  

**프로그램**은 컴퓨터가 이해할 수 있는 **아주 단순한 명령어**들의 시퀀스로 변환된다.  
고급 언어와 하드웨어 사이에는 주로 **컴파일러(compiler)**와 **운영체제(operating system)** 같은 **소프트웨어 계층**이 존재한다.  
고급 프로그래밍 언어(high-level language)는 **개발자의 생산성**을 높이고, **하드웨어 독립성**을 제공한다.

  

> The main advantage of high-level languages is programmer productivity and portability across machines.

고급 언어의 가장 큰 장점은 **개발자 생산성**과 **다른 머신에서도 이식성**을 높이는 것이다.

  

이게 무슨 말이냐면 다양한 프로그래밍 언어를 사용할 수 있는 이유는, 결국 컴퓨터는 해당 프로그래밍 언어(고급어)의 최종 번역된 기계어(저급어)를 이해하면 되기 때문입니다.

  

---

### **Under the Covers**

---

  

![](https://blog.kakaocdn.net/dn/vkCK5/btsNAG1mCDa/F5wjlyl6MB73ZOpBDP5k50/img.png)

The organization of a computer, showing the five classic components.

  

컴퓨터를 구성하는 5대 고전적 요소는 다음과 같습니다.

- 입력(input) : 컴퓨터로 정보를 보냄.
- 출력(output) : 컴퓨터로부터 정보를 받음.
- 메모리(memory) : 프로그램과 데이터를 저장.
- 데이터 경로(datapath) : 산술 연산(arithmatic operation)을 수행.
- 제어(control) : 프로그램 명령어에 따라 데이터 경로, 메모리, 입출력 장치에 무엇을 해야 할지 지시.

여기서 Processor는 datapath + control의 조합입니다. Processor는 메모리나 입출력 장치는 포함하지 않습니다. 프로세서 입장에서는 메모리와 I/O가 모두 외부 장치인 것이죠.

메모리는 명령어와 데이터를 둘 다 저장하는 저장소입니다.

---

### **Performance**

---

> When we say one computer has better performance than another, what do we mean?  
> If you were running a program on two different desktop computers, you’d say that the faster one is the desktop computer that gets the job done first.  
> As an individual computer user, you are interested in reducing response time—the time between the start and completion of a task—also referred to as execution time.  
> Thus, we can relate performance and execution time for a computer X:

여기서 말하는 건 컴퓨터가 다른 컴퓨터 보다 "더 성능이 좋다"라고 말할 때, 그게 어떤 것이 성능이 좋은 것을 의미하는가? 에 대한 답입니다.

두 개의 컴퓨터에서 프로그램을 실행했을 때, 작업을 먼저 완료하는 컴퓨터.

그렇기 때문에 사용자는 작업부터 완료까지의 전체 시간을 줄이는 것이 관심사입니다.

그래서 컴퓨터의 성능과 실행 시간은 다음과 같이 관계를 맺습니다.

![](https://blog.kakaocdn.net/dn/dQ8C4Z/btsNAgPdrMP/A9zpCaF7DlQh5Vv1f3Vcm1/img.png)

즉, 실행 시간이 짧을수록 성능이 더 좋다는 뜻입니다.

여기서 Response Time이나 Executionn Time은 컴퓨터가 작업을 완료하는 데 걸리는 전체 시간을 의미합니다.

이 시간에는 디스크 접근, 메모리 접근, 입출력 작업(I/O), 운영체제 오버헤드, CPU 실행 시간 등이 모두 포함됩니다.

  

> **Throughput** is the total amount of work done in a given time.  
> Thus, when we upgrade a system, we often improve throughput as well as response time.

Throughput은 주어진 시간 동안 수행된 작업량을 의미합니다. 따라서 시스템을 업그레이드할 때, response time 뿐만 아니라 Throughput도 함께 향상시키는 경우가 많습니다.

  

그리고 Execution time을 성능의 주요 척도로 나타내는데, X가 Y보다 n배 빠르다는 것은 아래와 같이 표현합니다.

![](https://blog.kakaocdn.net/dn/nnoWI/btsNBAZ9nMs/GYeULpO90ggB8KlNEbWk2k/img.png)

  

---

### **The Power Wall**

---

> Historically, manufacturers improved the performance of computers primarily by increasing the clock rate.  
> This technique eventually hit a limit due to problems with power consumption and heat generation.

과거에는, 제조업체에서 컴퓨터 성능 향상을 위해 clock rate를 증가시키는 방법을 썼지만, Power Consumption + Heat Generation 문제로 인해 한계에 부딪혔습니다.

![](https://blog.kakaocdn.net/dn/uJzlD/btsNAfbWgIJ/Xw9wxvMMlQRXb0WwWkrxp1/img.png)

전력 소비는 위의 식처럼 Capacitance, 전압 제곱, Frequency(Clock 속도)에 비례해 증가합니다.

이렇게 Power와 Energy는 컴퓨터 설계에서 가장 지배적인 제약 요건이 되었습니다. 또한, 클럭 속도를 일정 수준 이상으로 올리려고 하면, 발생하는 열이 제어할 수 없을 정도로 커지게 됩니다. 

그래서 컴퓨터 아키텍트들이 병렬 처리 같은 새로운 성능 향상을 찾게끔 만들었습니다.

![](https://blog.kakaocdn.net/dn/chSz52/btsNAHeVWzQ/Cl1DqyNkM8I1S6ubmFkPr1/img.png)

Clock rate and Power for Intel x86 microprocessors over eight generations and 25 years.

여기서 말하는 Power wall은

**클럭 속도를 올려서 성능을 향상시키기 위해서 전력을 높이면 발열이 생기면서 성능이 떨어지고, 낮추면 클럭 속도가 느려져서 성능이 내려가는 trade off 관계**를 의미합니다.

  

  

---

### **The Switch from Uniprocessors to Multiprocessors**

---

> Because of the power wall, it was no longer possible to increase the clock rate significantly while maintaining manageable power consumption.  
> As a result, computer designers turned to multiprocessors—computers with more than one processor—to improve performance.

  

앞서 설명한 Power Wall 때문에, 전력 소비를 감당 가능한 수준으로 유지하면서, 클럭 속도를 더 올리는 것이 불가능해졌습니다.

그래서 컴퓨터 설계자들은 Multiprocessor로 방향을 틀었습니다.

  

> A multiprocessor is a computer system with two or more processors that can work together to execute programs.  
> These processors usually share access to the memory and input/output resources, coordinating their actions to improve system performance.

교재에서는 **Multiprocessor를 "둘 이상의 프로세서를 가진 컴퓨터 시스템"이라고** 설명합니다. 이 프로세서들은 **메모리와 I/O resources를 공유**하며, 서로 협력하여 프로그램을 실행하고, 전체 시스템의 성능을 향상시키는 데 목적이 있습니다.

  

그래서 이러한 멀티프로세서 혹은 멀티코어를 갖고 할 수 있는 작업이 있습니다.

바로 병렬 프로그래밍(Parallel Programming)입니다.

병렬 프로그래밍은 하나의 문제를 독립적인 여러 부분으로 나눠, 이를 여러 프로세스 또는 코어가 동시에 실행하도록 프로그램을 작성하는 방법을 말합니다. 목표는 작업을 병렬로 처리하여 전체 실행 시간을 줄이는 것입니다.

  

+)추가 멀티프로세서 vs. 멀티코어

|   |   |   |
|---|---|---|
|구분|멀티프로세서 (Multiprocessor)|멀티코어(Multicore)|
|기본 정의|독립된 CPU 여러 개가 시스템에 존재.|하나의 CPU칩 안에 여러 개의 Core 존재|
|물리적 구조|CPU 칩 여러 개|하나의 CPU 칩(패키지) 안에 여러 코어|
|메모리 구조|보통 모든 CPU가 공유 메모리를 사용하거나,  <br>각각 다른 메모리를 가질 수도 있음.|같은 칩 안이기 때문에 공유 메모리 사용이 기본.|
|통신 방식|CPU 간 통신은 메인보드 경유, 상대적으로 느림.|코어 간 통신은 칩 내부에서 매우 빠르게 진행.|
|예시|서버용 시스템(듀얼 소켓, 쿼드 소켓 머신)|노트북, 스마트폰, CPU|

  

즉, 멀티프로세서 : CPU가 여러 개 있는 시스템

멀티코어 : CPU안에 코어가 여러 개 있는 시스템