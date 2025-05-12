<p>[##_Image|kage@nk1xa/btsNja9vX4w/0q3gtCexNJxen2sPGbuev0/tfile.dat|CDM|1.3|{"originWidth":306,"originHeight":304,"style":"alignCenter","caption":"Nekoder"}_##]</p>
<hr data-ke-style="style5" data-ke-type="horizontalRule" />
<p style="text-align: left;" data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">사실 제 전공과 Computer Architecture는 밀접한 관련은 없습니다.</span></p>
<p style="text-align: left;" data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">일을 시작하면서, 이 부분을 좀 배우고 오면 좋겠다는 의견이 있어서 Chat GPT를 이용해서 중요 내용만 빠르게 공부하면서, 해당 내용을 블로그에 정리하려 합니다. 추가로 OS도 조금 공부해서 정리할 예정입니다.</span></p>
<p style="text-align: left;" data-ke-size="size16"><span style="font-family: 'Noto Sans Light';"><a href="https://product.kyobobook.co.kr/detail/S000006082876" target="_blank" rel="noopener&nbsp;noreferrer">https://product.kyobobook.co.kr/detail/S000006082876</a></span></p>
<figure id="og_1745657068532" contenteditable="false" data-ke-type="opengraph" data-ke-align="alignCenter" data-og-type="website" data-og-title="Computer Organization and Design MIPS Edition | Patterson - 교보문고" data-og-description="Computer Organization and Design MIPS Edition | Moves forward into the post-PC era with new examples, exercises, and material highlighting the emergence of mobile computing and the cloud. This title includes examples, exercises, and material highlighting t" data-og-host="product.kyobobook.co.kr" data-og-source-url="https://product.kyobobook.co.kr/detail/S000006082876" data-og-url="https://product.kyobobook.co.kr/detail/S000006082876" data-og-image="https://scrap.kakaocdn.net/dn/bfXyU3/hyYFEq4BGB/owsGl7ZxerwHageGIxJn10/img.jpg?width=458&amp;height=540&amp;face=0_0_458_540,https://scrap.kakaocdn.net/dn/c5VUKE/hyYMdrIuB2/p0NlBKWVJueQJrewl2lKq0/img.jpg?width=458&amp;height=540&amp;face=0_0_458_540,https://scrap.kakaocdn.net/dn/g74e6/hyYIg38Ngk/eML0UYmQqRWq20gniuRQs1/img.png?width=335&amp;height=335&amp;face=0_0_335_335"><a href="https://product.kyobobook.co.kr/detail/S000006082876" target="_blank" rel="noopener" data-source-url="https://product.kyobobook.co.kr/detail/S000006082876">
<div class="og-image" style="background-image: url('https://scrap.kakaocdn.net/dn/bfXyU3/hyYFEq4BGB/owsGl7ZxerwHageGIxJn10/img.jpg?width=458&amp;height=540&amp;face=0_0_458_540,https://scrap.kakaocdn.net/dn/c5VUKE/hyYMdrIuB2/p0NlBKWVJueQJrewl2lKq0/img.jpg?width=458&amp;height=540&amp;face=0_0_458_540,https://scrap.kakaocdn.net/dn/g74e6/hyYIg38Ngk/eML0UYmQqRWq20gniuRQs1/img.png?width=335&amp;height=335&amp;face=0_0_335_335');">&nbsp;</div>
<div class="og-text">
<p class="og-title" data-ke-size="size16">Computer Organization and Design MIPS Edition | Patterson - 교보문고</p>
<p class="og-desc" data-ke-size="size16">Computer Organization and Design MIPS Edition | Moves forward into the post-PC era with new examples, exercises, and material highlighting the emergence of mobile computing and the cloud. This title includes examples, exercises, and material highlighting t</p>
<p class="og-host" data-ke-size="size16">product.kyobobook.co.kr</p>
</div>
</a></figure>
<p data-ke-size="size16">공부한 교재.</p>
<p style="text-align: left;" data-ke-size="size16">&nbsp;</p>
<p style="text-align: left;" data-ke-size="size16">우리는 Computer라는 말을 너무 당연하게 사용합니다. Compute는 동사로 "계산하다"라는 뜻입니다. 영문 뜻을 살펴보면,</p>
<blockquote data-ke-style="style3"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">to calculate an answer or amount by using a machine:</span></blockquote>
<p data-ke-size="size14"><span style="font-family: 'Noto Sans Light';">즉 기계를 사용해서 답이나 수량을 계산하는 작업을 Compute라고 합니다.</span></p>
<p data-ke-size="size14"><span style="font-family: 'Noto Sans Light';">이러한 역할을 수행하는 기계를 Computer라고 하겠죠?</span></p>
<p data-ke-size="size14"><span style="font-family: 'Noto Sans Light';">그럼 들어가 보겠습니다.</span></p>
<hr contenteditable="false" data-ke-type="horizontalRule" data-ke-style="style5" />
<h3 style="text-align: center;" data-ke-size="size23"><span style="font-family: Noto Sans Demilight, Noto Sans KR;"><span style="color: #333333;"><b>Computer</b></span></span></h3>
<hr contenteditable="false" data-ke-type="horizontalRule" data-ke-style="style8" />
<p data-ke-size="size16">&nbsp;</p>
<p data-ke-size="size16">&nbsp;</p>
<p data-ke-size="size16">&nbsp;</p>
<blockquote data-ke-style="style3"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">"A computer is a machine that can be instructed to carry out sequences of arithmetic or logical operations automatically via computer programming." </span></blockquote>
<p data-ke-size="size14"><span style="font-family: 'Noto Sans Light';"> 컴퓨터란, 프로그래밍을 통해 산술 또는 논리 연산의 일련의 과정을 <b>자동으로 수행하도록 지시할 수 있는 기계</b>이다.</span></p>
<p data-ke-size="size14">&nbsp;</p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">컴퓨터는 스스로 동작할 수 있게 만드는 '프로그램 가능한 자동 기계'라고 합니다.</span></p>
<p data-ke-size="size16">&nbsp;</p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">교재에서는 컴퓨터 아키텍처를 이해하는 데 핵심이 되는 8개의 아이디어를 소개합니다.</span></p>
<p data-ke-size="size16">&nbsp;</p>
<ol style="list-style-type: decimal;" data-ke-list-type="decimal">
<li data-end="1689" data-start="1640"><span style="font-family: 'Noto Sans Light';"><b>무어의 법칙에 맞춰 설계하기</b> (Design for Moore&rsquo;s Law)</span></li>
<li data-end="1754" data-start="1690"><span style="font-family: 'Noto Sans Light';"><b>추상화를 사용하여 설계 단순화하기</b> (Use Abstraction to Simplify Design)</span></li>
<li data-end="1806" data-start="1755"><span style="font-family: 'Noto Sans Light';"><b>공통 경로를 빠르게 만들기</b> (Make the Common Case Fast)</span></li>
<li data-end="1857" data-start="1807"><span style="font-family: 'Noto Sans Light';"><b>병렬성으로 성능 향상</b> (Performance via Parallelism)</span></li>
<li data-end="1910" data-start="1858"><span style="font-family: 'Noto Sans Light';"><b>파이프라이닝으로 성능 향상</b> (Performance via Pipelining)</span></li>
<li data-end="1961" data-start="1911"><span style="font-family: 'Noto Sans Light';"><b>예측을 통한 성능 향상</b> (Performance via Prediction)</span></li>
<li data-end="2007" data-start="1962"><span style="font-family: 'Noto Sans Light';"><b>메모리 계층 구조 사용</b> (Hierarchy of Memories)</span></li>
<li data-end="2059" data-start="2008"><span style="font-family: 'Noto Sans Light';"><b>여유를 통한 신뢰성 확보</b> (Dependability via Redundancy)</span></li>
</ol>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">몇 가지만 간략하게 살펴보면.</span></p>
<div data-ke-type="moreLess" data-text-more="더보기" data-text-less="닫기"><a class="btn-toggle-moreless">더보기</a>
<div class="moreless-content"><b><span style="font-family: 'Noto Sans Light';">Use Abstaction to Simply Design</span></b>
<blockquote data-ke-style="style3"><span style="font-family: 'Noto Sans Light';">Both computer architects and programmers had to invent techniques to make themselves more productive, for otherwise design time would lengthen as dramatically as resources grew by Moore&rsquo;s Law. A major productivity technique for hardware and soft ware is to use abstractions to represent the design at diff erent levels of representation; lower-level details are hidden to off er a simpler model at higher levels. We&rsquo;ll use the abstract painting icon to represent this second great idea.</span></blockquote>
<p data-end="1144" data-start="875" data-ke-size="size14"><span style="font-family: 'Noto Sans Light';">컴퓨터 아키텍트와 프로그래머 모두 <b>자신들의 생산성을 높이기 위해 기술을 발명해야 했다</b>. 그렇지 않으면, 무어의 법칙에 의해 자원(resource)이 늘어나는 만큼 <b>설계 시간이 비약적으로 늘어났을 것</b>이다. </span><span style="font-family: 'Noto Sans Light';">하드웨어와 소프트웨어 모두에서 <b>생산성을 높이는 주요 기술</b>은, </span><span style="font-family: 'Noto Sans Light';"><b>추상화(abstraction)를 사용하여 설계를 여러 수준(level)의 표현으로 나누는 것</b>이다. </span><span style="font-family: 'Noto Sans Light';">하위 수준의 세부사항은 숨기고, 상위 수준에서는 더 단순한 모델을 제공한다.</span></p>
<p data-end="1144" data-start="875" data-ke-size="size16">&nbsp;</p>
<p data-end="1144" data-start="875" data-ke-size="size16"><span style="font-family: 'Noto Sans Light';"><b>Make the Common Case Fast</b></span></p>
<blockquote data-end="1144" data-start="875" data-ke-style="style3"><span style="font-family: 'Noto Sans Light';"> Making the common case fast will tend to enhance performance better than optimizing the rare case.</span><br /><span style="font-family: 'Noto Sans Light';">Ironically, the common case is often simpler than the rare case and hence is often easier to enhance. </span></blockquote>
<p data-end="1144" data-start="875" data-ke-size="size14"><span style="font-family: 'Noto Sans Light';"> <b>공통적인 경우를 빠르게 만드는 것이</b>, 드문 경우를 최적화하는 것보다 <b>성능을 더 효과적으로 향상</b>시킨다.</span><br /><span style="font-family: 'Noto Sans Light';">아이러니하게도, <b>공통적인 경우가 드문 경우보다 더 단순한 경우가 많기 때문에</b>, 최적화하는 것도 더 쉽다. </span></p>
<p data-end="1144" data-start="875" data-ke-size="size16">&nbsp;</p>
<p data-end="1144" data-start="875" data-ke-size="size16"><b><span style="font-family: 'Noto Sans Light';">Performance via Prediction</span></b></p>
<blockquote data-end="1144" data-start="875" data-ke-style="style3"><span style="font-family: 'Noto Sans Light';"> Following the saying that it can be better to ask for forgiveness than to ask for permission, the final great idea is prediction. In some cases, it can be faster on average to guess and start working rather than wait until you know for sure, assuming that the mechanism to recover from a misprediction is not too expensive and your prediction is relatively accurate.</span></blockquote>
<p data-end="1144" data-start="875" data-ke-size="size14"><span style="font-family: 'Noto Sans Light';"> "허락을 구하는 것보다 용서를 구하는 것이 낫다"는 속담처럼, <b>마지막으로 중요한 아이디어는 '예측(prediction)'이다</b>. </span><span style="font-family: 'Noto Sans Light';">일부 경우에는, <b>확실해질 때까지 기다리는 것보다, 일단 추측하고 작업을 시작하는 것이 평균적으로 더 빠를 수 있다</b>. </span><span style="font-family: 'Noto Sans Light';">(단, 잘못된 예측을 복구하는 비용이 크지 않고, 예측의 정확도가 상대적으로 높다는 전제 하에서.)</span></p>
<p data-end="1144" data-start="875" data-ke-size="size16">&nbsp;</p>
<p data-end="1144" data-start="875" data-ke-size="size16"><b><span style="font-family: 'Noto Sans Light';">Performance via Pipelining</span></b></p>
<blockquote data-end="1144" data-start="875" data-ke-style="style3"><span style="font-family: 'Noto Sans Light';"> A particular pattern of parallelism is so prevalent in computer architecture that it merits its own name: pipelining.</span><br /><span style="font-family: 'Noto Sans Light';">For example, before fire engines, a "bucket brigade" would respond to a fire, which many cowboy movies show.</span><br /><span style="font-family: 'Noto Sans Light';">The townsfolk form a human chain to carry a water source to the fire, as they could much more quickly move buckets up the chain instead of individuals running back and forth. </span></blockquote>
<p data-end="1144" data-start="875" data-ke-size="size14"><span style="font-family: 'Noto Sans Light';"> <b>컴퓨터 아키텍처에서 매우 흔한 병렬 처리 패턴이 있는데</b>, </span><span style="font-family: 'Noto Sans Light';"><b>그것이 바로 '파이프라이닝(pipelining)'이다</b>. </span><span style="font-family: 'Noto Sans Light';">예를 들어, 소방차가 등장하기 전에는, <b>"버킷 브리게이드(bucket brigade)"</b> 방식으로 불을 껐다. (이 장면은 서부극 영화에서도 자주 나온다.) </span><span style="font-family: 'Noto Sans Light';">마을 사람들은 <b>사람들의 체인(chain)을 이루어</b>, 양동이를 나르는 식으로 물을 옮겼다. </span><span style="font-family: 'Noto Sans Light';"><b>한 사람이 계속 오가며 이동하는 것보다</b>, 체인으로 전달하는 방식이 훨씬 빠르기 때문이다.</span></p>
<p data-end="1144" data-start="875" data-ke-size="size14">&nbsp;</p>
<p data-end="1144" data-start="875" data-ke-size="size14"><span style="font-family: 'Noto Sans Light';">파이프라이닝은 제 다른 포스팅에서 다룬 적 있습니다.</span></p>
<p data-end="1144" data-start="875" data-ke-size="size14"><span style="font-family: 'Noto Sans Light';"><a href="https://chanfifo77.tistory.com/100" target="_blank" rel="noopener&nbsp;noreferrer">https://chanfifo77.tistory.com/100</a></span></p>
<figure id="og_1745663277588" contenteditable="false" data-ke-type="opengraph" data-ke-align="alignCenter" data-og-type="article" data-og-title="[Verilog] Verilog를 이용한 AI 설계 응용 및 SoC 설계 (2)" data-og-description="https://chanfifo77.tistory.com/99&nbsp;[Verilog] Verilog를 이용한 AI 설계 응용 및 SoC 설계 (1)&nbsp;chanfifo77.tistory.com&nbsp;이전 포스팅의 마무리인 STA부터 이어서 작성하겠습니다.STA로 모든 경로를 전수조사 할 때, 최단 " data-og-host="chanfifo77.tistory.com" data-og-source-url="https://chanfifo77.tistory.com/100" data-og-url="https://chanfifo77.tistory.com/100" data-og-image="https://scrap.kakaocdn.net/dn/o2fZn/hyYFzDiDe5/GXe08tK0VuLNpiK1QS621k/img.jpg?width=500&amp;height=375&amp;face=0_0_500_375,https://scrap.kakaocdn.net/dn/0yrvq/hyYIav7pgm/A1dqiPr9xt6fPQKOjPM7P0/img.jpg?width=500&amp;height=375&amp;face=0_0_500_375,https://scrap.kakaocdn.net/dn/AsqkY/hyYFGWJDMk/QcMqSWm1F6Tck6BR0HoVOK/img.png?width=1410&amp;height=903&amp;face=0_0_1410_903"><a href="https://chanfifo77.tistory.com/100" target="_blank" rel="noopener" data-source-url="https://chanfifo77.tistory.com/100">
<div class="og-image" style="background-image: url('https://scrap.kakaocdn.net/dn/o2fZn/hyYFzDiDe5/GXe08tK0VuLNpiK1QS621k/img.jpg?width=500&amp;height=375&amp;face=0_0_500_375,https://scrap.kakaocdn.net/dn/0yrvq/hyYIav7pgm/A1dqiPr9xt6fPQKOjPM7P0/img.jpg?width=500&amp;height=375&amp;face=0_0_500_375,https://scrap.kakaocdn.net/dn/AsqkY/hyYFGWJDMk/QcMqSWm1F6Tck6BR0HoVOK/img.png?width=1410&amp;height=903&amp;face=0_0_1410_903');">&nbsp;</div>
<div class="og-text">
<p class="og-title" data-ke-size="size16">[Verilog] Verilog를 이용한 AI 설계 응용 및 SoC 설계 (2)</p>
<p class="og-desc" data-ke-size="size16">https://chanfifo77.tistory.com/99&nbsp;[Verilog] Verilog를 이용한 AI 설계 응용 및 SoC 설계 (1)&nbsp;chanfifo77.tistory.com&nbsp;이전 포스팅의 마무리인 STA부터 이어서 작성하겠습니다.STA로 모든 경로를 전수조사 할 때, 최단</p>
<p class="og-host" data-ke-size="size16">chanfifo77.tistory.com</p>
</div>
</a></figure>
</div>
</div>
<hr contenteditable="false" data-ke-type="horizontalRule" data-ke-style="style5" />
<h3 style="text-align: center;" data-ke-size="size23"><span style="font-family: Noto Sans Demilight, Noto Sans KR;"><span style="color: #333333;"><b>Below Your Program</b></span></span></h3>
<hr contenteditable="false" data-ke-style="style8" data-ke-type="horizontalRule" />
<p>[##_Image|kage@BS0rp/btsNA8wgD5x/Vpx2OxPZGEti08OOmgYzIK/img.png|CDM|1.3|{"originWidth":235,"originHeight":230,"style":"alignCenter","caption":"A simplifi ed view of hardware and software as hierarchical layers, shown as concentric circles with hardware in the center and applications software outermost."}_##]</p>
<blockquote data-ke-style="style3"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';"> Programs are translated into a sequence of very simple instructions that the hardware understands. </span><br /><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">Software layers exist between the high-level language and the hardware, mainly <b>compilers</b> and <b>operating systems.</b></span><br /><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';"> High-level languages enable programmers to be more productive and portable across different hardware. </span></blockquote>
<p data-ke-size="size14">&nbsp;</p>
<p data-ke-size="size14"><span style="font-family: 'Noto Sans Light';"> <b>프로그램</b>은 컴퓨터가 이해할 수 있는 <b>아주 단순한 명령어</b>들의 시퀀스로 변환된다.</span><br /><span style="font-family: 'Noto Sans Light';">고급 언어와 하드웨어 사이에는 주로 <b>컴파일러(compiler)</b>와 <b>운영체제(operating system)</b> 같은 <b>소프트웨어 계층</b>이 존재한다.</span><br /><span style="font-family: 'Noto Sans Light';">고급 프로그래밍 언어(high-level language)는 <b>개발자의 생산성</b>을 높이고, <b>하드웨어 독립성</b>을 제공한다. </span></p>
<p data-ke-size="size16">&nbsp;</p>
<blockquote data-ke-style="style3"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';"> The main advantage of high-level languages is programmer productivity and portability across machines.</span></blockquote>
<p data-ke-size="size14"><span style="font-family: 'Noto Sans Light';">고급 언어의 가장 큰 장점은 <b>개발자 생산성</b>과 <b>다른 머신에서도 이식성</b>을 높이는 것이다.</span></p>
<p data-ke-size="size16">&nbsp;</p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">이게 무슨 말이냐면 다양한 프로그래밍 언어를 사용할 수 있는 이유는, 결국 컴퓨터는 해당 프로그래밍 언어(고급어)의 최종 번역된 기계어(저급어)를 이해하면 되기 때문입니다.</span></p>
<p data-ke-size="size16">&nbsp;</p>
<hr contenteditable="false" data-ke-type="horizontalRule" data-ke-style="style5" />
<h3 style="text-align: center;" data-ke-size="size23"><span style="font-family: Noto Sans Demilight, Noto Sans KR;"><span style="color: #333333;"><b>Under the Covers</b></span></span></h3>
<hr contenteditable="false" data-ke-type="horizontalRule" data-ke-style="style8" />
<p data-ke-size="size16">&nbsp;</p>
<p>[##_Image|kage@vkCK5/btsNAG1mCDa/F5wjlyl6MB73ZOpBDP5k50/img.png|CDM|1.3|{"originWidth":517,"originHeight":422,"style":"alignCenter","caption":"The organization of a computer, showing the five classic components."}_##]</p>
<p data-ke-size="size16">&nbsp;</p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">컴퓨터를 구성하는 5대 고전적 요소는 다음과 같습니다.</span></p>
<ul style="list-style-type: disc;" data-ke-list-type="disc">
<li><span style="font-family: 'Noto Sans Light';">입력(input) : 컴퓨터로 정보를 보냄.</span></li>
<li><span style="font-family: 'Noto Sans Light';">출력(output) : 컴퓨터로부터 정보를 받음.</span></li>
<li><span style="font-family: 'Noto Sans Light';">메모리(memory) : 프로그램과 데이터를 저장.</span></li>
<li><span style="font-family: 'Noto Sans Light';">데이터 경로(datapath) : 산술 연산(arithmatic operation)을 수행.</span></li>
<li><span style="font-family: 'Noto Sans Light';">제어(control) : 프로그램 명령어에 따라 데이터 경로, 메모리, 입출력 장치에 무엇을 해야 할지 지시.</span></li>
</ul>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">여기서 Processor는 datapath + control의 조합입니다. Processor는 메모리나 입출력 장치는 포함하지 않습니다. 프로세서 입장에서는 메모리와 I/O가 모두 외부 장치인 것이죠.</span></p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">메모리는 명령어와 데이터를 둘 다 저장하는 저장소입니다.</span></p>
<hr contenteditable="false" data-ke-style="style5" data-ke-type="horizontalRule" />
<h3 style="text-align: center;" data-ke-size="size23"><span style="font-family: Noto Sans Demilight, Noto Sans KR;"><span style="color: #333333;"><b>Performance</b></span></span></h3>
<hr contenteditable="false" data-ke-style="style8" data-ke-type="horizontalRule" />
<blockquote data-ke-style="style3"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';"> When we say one computer has better performance than another, what do we mean?</span><br /><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">If you were running a program on two different desktop computers, you&rsquo;d say that the faster one is the desktop computer that gets the job done first.</span><br /><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">As an individual computer user, you are interested in reducing response time&mdash;the time between the start and completion of a task&mdash;also referred to as execution time.</span><br /><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">Thus, we can relate performance and execution time for a computer X: </span></blockquote>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">여기서 말하는 건 컴퓨터가 다른 컴퓨터 보다 "더 성능이 좋다"라고 말할 때, 그게 어떤 것이 성능이 좋은 것을 의미하는가? 에 대한 답입니다.</span></p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">두 개의 컴퓨터에서 프로그램을 실행했을 때, 작업을 먼저 완료하는 컴퓨터.</span></p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">그렇기 때문에 사용자는 작업부터 완료까지의 전체 시간을 줄이는 것이 관심사입니다.</span></p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">그래서 컴퓨터의 성능과 실행 시간은 다음과 같이 관계를 맺습니다.</span></p>
<p>[##_Image|kage@dQ8C4Z/btsNAgPdrMP/A9zpCaF7DlQh5Vv1f3Vcm1/img.png|CDM|1.3|{"originWidth":277,"originHeight":57,"style":"alignCenter"}_##]</p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">즉, 실행 시간이 짧을수록 성능이 더 좋다는 뜻입니다.</span></p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">여기서 Response Time이나 Executionn Time은 컴퓨터가 작업을 완료하는 데 걸리는 전체 시간을 의미합니다.</span></p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">이 시간에는 디스크 접근, 메모리 접근, 입출력 작업(I/O), 운영체제 오버헤드, CPU 실행 시간 등이 모두 포함됩니다.</span></p>
<p data-ke-size="size16">&nbsp;</p>
<blockquote data-ke-style="style3"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';"><b> Throughput</b> is the total amount of work done in a given time.</span><br /><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">Thus, when we upgrade a system, we often improve throughput as well as response time. </span></blockquote>
<p data-ke-size="size16"><span>Throughput은 주어진 시간 동안 수행된 작업량을 의미합니다. 따라서 시스템을 업그레이드할 때, response time 뿐만 아니라 Throughput도 함께 향상시키는 경우가 많습니다.</span></p>
<p data-ke-size="size16">&nbsp;</p>
<p data-ke-size="size16"><span>그리고 Execution time을 성능의 주요 척도로 나타내는데, X가 Y보다 n배 빠르다는 것은 아래와 같이 표현합니다.</span></p>
<p>[##_Image|kage@nnoWI/btsNBAZ9nMs/GYeULpO90ggB8KlNEbWk2k/img.png|CDM|1.3|{"originWidth":232,"originHeight":65,"style":"alignCenter"}_##]</p>
<p data-ke-size="size16">&nbsp;</p>
<hr contenteditable="false" data-ke-type="horizontalRule" data-ke-style="style5" />
<h3 style="text-align: center;" data-ke-size="size23"><span style="font-family: Noto Sans Demilight, Noto Sans KR;"><span style="color: #333333;"><b>The Power Wall</b></span></span></h3>
<hr contenteditable="false" data-ke-type="horizontalRule" data-ke-style="style8" />
<blockquote data-ke-style="style3"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';"> Historically, manufacturers improved the performance of computers primarily by increasing the clock rate.</span><br /><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">This technique eventually hit a limit due to problems with power consumption and heat generation. </span></blockquote>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">과거에는, 제조업체에서 컴퓨터 성능 향상을 위해 clock rate를 증가시키는 방법을 썼지만, Power Consumption + Heat Generation 문제로 인해 한계에 부딪혔습니다.</span></p>
<p>[##_Image|kage@uJzlD/btsNAfbWgIJ/Xw9wxvMMlQRXb0WwWkrxp1/img.png|CDM|1.3|{"originWidth":412,"originHeight":41,"style":"alignCenter"}_##]</p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">전력 소비는 위의 식처럼 Capacitance, 전압 제곱, Frequency(Clock 속도)에 비례해 증가합니다.</span></p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">이렇게 Power와 Energy는 컴퓨터 설계에서 가장 지배적인 제약 요건이 되었습니다. 또한, 클럭 속도를 일정 수준 이상으로 올리려고 하면, 발생하는 열이 제어할 수 없을 정도로 커지게 됩니다.&nbsp;</span></p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">그래서 컴퓨터 아키텍트들이 병렬 처리 같은 새로운 성능 향상을 찾게끔 만들었습니다.</span></p>
<p>[##_Image|kage@chSz52/btsNAHeVWzQ/Cl1DqyNkM8I1S6ubmFkPr1/img.png|CDM|1.3|{"originWidth":796,"originHeight":324,"style":"alignCenter","caption":"Clock rate and Power for Intel x86 microprocessors over eight generations and 25 years."}_##]</p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">여기서 말하는 Power wall은 </span></p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';"><b>클럭 속도를 올려서 성능을 향상시키기 위해서 전력을 높이면 발열이 생기면서 성능이 떨어지고, 낮추면 클럭 속도가 느려져서 성능이 내려가는 trade off 관계</b>를 의미합니다.</span></p>
<p data-ke-size="size16">&nbsp;</p>
<p data-ke-size="size16">&nbsp;</p>
<hr contenteditable="false" data-ke-style="style5" data-ke-type="horizontalRule" />
<h3 style="text-align: center;" data-ke-size="size23"><span style="font-family: Noto Sans Demilight, Noto Sans KR;"><span style="color: #333333;"><b>The Switch from Uniprocessors to Multiprocessors</b></span></span></h3>
<hr contenteditable="false" data-ke-style="style8" data-ke-type="horizontalRule" />
<blockquote data-ke-style="style3"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';"> Because of the power wall, it was no longer possible to increase the clock rate significantly while maintaining manageable power consumption.</span><br /><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">As a result, computer designers turned to multiprocessors&mdash;computers with more than one processor&mdash;to improve performance. </span></blockquote>
<p data-ke-size="size16">&nbsp;</p>
<p data-ke-size="size16">앞서 설명한 Power Wall 때문에, 전력 소비를 감당 가능한 수준으로 유지하면서, 클럭 속도를 더 올리는 것이 불가능해졌습니다.</p>
<p data-ke-size="size16">그래서 컴퓨터 설계자들은 Multiprocessor로 방향을 틀었습니다.</p>
<p data-ke-size="size16">&nbsp;</p>
<blockquote data-ke-style="style3"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">A multiprocessor is a computer system with two or more processors that can work together to execute programs.</span><br /><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">These processors usually share access to the memory and input/output resources, coordinating their actions to improve system performance.</span></blockquote>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">교재에서는 <b>Multiprocessor를 "둘 이상의 프로세서를 가진 컴퓨터 시스템"이라고</b> 설명합니다. 이 프로세서들은 <b>메모리와 I/O resources를 공유</b>하며, 서로 협력하여 프로그램을 실행하고, 전체 시스템의 성능을 향상시키는 데 목적이 있습니다.</span></p>
<p data-ke-size="size16">&nbsp;</p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">그래서 이러한 멀티프로세서 혹은 멀티코어를 갖고 할 수 있는 작업이 있습니다.</span></p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">바로 병렬 프로그래밍(Parallel Programming)입니다.</span></p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">병렬 프로그래밍은 하나의 문제를 독립적인 여러 부분으로 나눠, 이를 여러 프로세스 또는 코어가 동시에 실행하도록 프로그램을 작성하는 방법을 말합니다. 목표는 작업을 병렬로 처리하여 전체 실행 시간을 줄이는 것입니다.</span></p>
<p data-ke-size="size16">&nbsp;</p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">+)추가 멀티프로세서 vs. 멀티코어</span></p>
<table style="border-collapse: collapse; width: 95.3469%; height: 261px;" border="1" data-ke-align="alignCenter" data-ke-style="style15">
<tbody>
<tr style="height: 17px;">
<td style="width: 18.2942%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">구분</span></td>
<td style="width: 41.7025%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">멀티프로세서 (Multiprocessor)</span></td>
<td style="width: 65.6802%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">멀티코어(Multicore)</span></td>
</tr>
<tr style="height: 17px;">
<td style="width: 18.2942%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">기본 정의</span></td>
<td style="width: 41.7025%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Light';">독립된 CPU 여러 개가 시스템에 존재.</span></td>
<td style="width: 65.6802%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Light';">하나의 CPU칩 안에 여러 개의 Core 존재</span></td>
</tr>
<tr style="height: 17px;">
<td style="width: 18.2942%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">물리적 구조</span></td>
<td style="width: 41.7025%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Light';">CPU 칩 여러 개</span></td>
<td style="width: 65.6802%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Light';">하나의 CPU 칩(패키지) 안에 여러 코어</span></td>
</tr>
<tr style="height: 17px;">
<td style="width: 18.2942%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">메모리 구조</span></td>
<td style="width: 41.7025%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Light';">보통 모든 CPU가 공유 메모리를 사용하거나, </span><br /><span style="font-family: 'Noto Sans Light';">각각 다른 메모리를 가질 수도 있음.</span></td>
<td style="width: 65.6802%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Light';">같은 칩 안이기 때문에 공유 메모리 사용이 기본.</span></td>
</tr>
<tr style="height: 17px;">
<td style="width: 18.2942%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">통신 방식</span></td>
<td style="width: 41.7025%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Light';">CPU 간 통신은 메인보드 경유, 상대적으로 느림.</span></td>
<td style="width: 65.6802%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Light';">코어 간 통신은 칩 내부에서 매우 빠르게 진행.</span></td>
</tr>
<tr style="height: 17px;">
<td style="width: 18.2942%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Demilight', 'Noto Sans KR';">예시</span></td>
<td style="width: 41.7025%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Light';">서버용 시스템(듀얼 소켓, 쿼드 소켓 머신)</span></td>
<td style="width: 65.6802%; text-align: center; height: 17px;"><span style="font-family: 'Noto Sans Light';">노트북, 스마트폰, CPU</span></td>
</tr>
</tbody>
</table>
<p style="text-align: center;" data-ke-size="size16">&nbsp;</p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">즉, 멀티프로세서 : CPU가 여러 개 있는 시스템</span></p>
<p data-ke-size="size16"><span style="font-family: 'Noto Sans Light';">멀티코어 : CPU안에 코어가 여러 개 있는 시스템</span></p>