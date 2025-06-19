
## Parent-Child Relationship
Qt의 거의 모든 위젯, 레이아웃, 액션, 타이머 등의 클래스들은 `QObject`라는 기본 클래스를 상속받는다.
`QObject`
1. 자동 메모리 관리:
   부모 `QObject`가 소멸될 때, 그에게 속한 모든 자식 `QObject`들도 자동으로 함께 소멸된다.
2. 객체 트리:
   객체들이 부모-자식 관계를 통해 tree 구조를 형성하여 객체들을 체계적으로 관리할 수 있다.
`{cpp icon title}|new MyObject(this)` 문법은 바로 이 부모-자식 관계를 생성하는 시점에 설정하는 것이다. 
적용은 모든 위젯(`QWdiget` 계열), 레이아웃(`QLayout` 계열), 보이지 않는 객체들(`QObject` 계열)에도 모두 사용 가능하다.

>[!chat gpt]
>Qt에서 어떤 객체(`A`)를 생성할 때, 그 객체가 논리적으로 다른 객체(`B`, 주로 `this`)에 **소속**된다면, 생성자 인자로 부모(`B`)를 전달하는 것이 기본이다.

`{cpp icon title}| QVBoxLayout *layout = new QVBoxLayout(this);` 이처럼 사용한다.

### Connect
`connect`함수는 특정 이벤트(시그널)이 발생했을 때, 정해진 동작(슬롯)을 실행하도록 둘을 연결하는 역할이다. 전구에 전선을 통해 스위치랑 연결하는 것처럼.

connect는 보통 4개의 인자를 받는다.
`{cpp}connect(1.누가, 2.어떤 신호를 보내면, 3.누가, 4.어떤 행동을 할 것인가);` 
실제 코드를 간략하게 보면
-> ex) `{cpp}connect(loadButton, &QPushButton::clicked, this, [this](){...});`

1. `loadButton`: 
   신호를 보내는 객체
2. `&QPushButton::clicked`:
   `QPushButton`의 `clicked`이라는 이름으로 정의된 시그널.
3. `this`:
   `connect`**코드를 포함**하고 있는 **클래스의 객체**를 가리킨다. (**현재 connect를 사용하고 있는 클래스의 객체**)
4. `[this]() {...}`:
   실행할 행동, **slot**에 해당된다. 여기서는 **Lambda 함수**를 사용해서 slot을 작성했다.

> [!reflection] reflection with Gemini : Lambda 함수
> `[캡처](인자) {함수 본문}`
> 1. `[this]` **Capture 절**
>    람다 함수는 기본적으로 **단절된, 독립된 것이라서 외부 변수나 함수를 사용하려면 어떤 것을 캡쳐해올지 명시해야 한다.** `[this]`는 **"이 람다 함수 안에서 `this` 포인터를 사용할 수 있게 해줘"** 라는 요청이다.
>    `this`를 캡처했기에, 람다 함수 내에서 `this`가 가리키는 객체의 멤버 함수를 호출 할 수 있다. 만약 `[]`로 비워두고, 멤버 함수를 호출하려 하면 해당 멤버 함수를 찾을 수 없는 컴파일 에러가 발생한다.
> 2. `()` **Parameter 목록**
>    이 람다 함수가 받을 인자를 정의하는 곳.
>    앞에 `QPushButton::clicked`는 전달하는 데이터가 없으므로, 이 람다 함수도 받는 인자가 없어 `()`가 비어있다.
> 3. `{...}` **함수 본문**
>    버튼이 클릭되었을 때 실제로 실행될 코드 블록.


### QCoreApplication
- Qt Application의 가장 기본형. GUI가 필요 없는 프로그램. 이벤트 루프와 신호/슬롯 메커니즘만 제공


### QGuiApplication
그래픽 관련 기능은 필요하지만, 위젯은 필요 없는 경우
OpenGL, QML, QtQuick 사용 시 적합.
QWidget은 사용 불가.

### QApplication
Qt GUI Application을 실행하기 위해 기본적인 환경을 초기화하고 관리하는 클래스


### QFileDialog
#### getOpenFileName()
`QFileDialog` 객체를 직접 생성하지 않고, `QFileDialog::` 형태로 바로 호출할 수 있다.

```cpp
QString QFileDialog::getOpenFileName(
	QWidget *parent,
	const QString &caption,
	const QString &dir,
	const QString &filter
);
```
일반적으로 이렇게 사용하는데
1. `parent`: 대화 상자를 띄울 부모 위젯(보통 `this` 사용)
2. `caption`: 대화 상자의 제목 표시줄에 보일 텍스트.
3. `dir`: 대화 상자가 처음 열릴 때 보여줄 디렉토리 경로.
4. `filter`: 선택할 파일의 종류를 거르는 필터.

예시:
```cpp
QString QFileDialog::getOpenFileName(this, "XML select file", "", "XML files (*.xml)");
```

### QIODevice
`QIODevice`는 Qt에서 파일, 버퍼, 네트워크 소켓 등 모든 입출력 장치의 기본이 되는 인터페이스 클래스.
데이터를 읽고 쓰는 모든 클래스(`QFile`, `QTcpSocket`, `QBuffer` 등)는 `QIODevice`를 상속받는다.

쉽게 말하면, 데이터를 다루는 다양한 장치들을 일관된 방식으로 제어할 수 있도록 공통 기능(열기, 닫기, 읽기, 쓰기 등)을 정의한 것이다.

#### `QIODevice::ReadOnly | QIODevice::Text`
`{cpp}if (!file.open(QIODeviec::ReadOnly | QIODevice::Text))` 코드에서 `QIODevice::` 뒤에 붙는 것들은 파일을 어떤 모드로 열지 지정하는 flag.
- `QIODevice::ReadOnly`: 
  파일을 읽기 전용으로 연다. 이 모드에서는 파일에 데이터를 쓸 수 없다.
- `QIODevice::Text`:
  파일을 텍스트 모드로 연다. 이 플래그를 사용하면 OS에 따라 다른 줄 바꿈 문자(`\r\n`)가 c++에서 사용하는 표준 줄 바꿈 문자(`\n`)로 자동으로 변환되어 읽기 편해진다.

### Dialog

### setWindowTitle
```cpp
setWindowTitle(tr("Title Name"));
```

### DialogButtonBox
Action이 자동 연결된 것들이 있다. 그냥 ButtonBox 사용 시 일일이 버튼마다 동작을 작성해줘야 한다.

```cpp
QDialogButtonBox *buttonBox = new QDialogButtonBox(QDialogButtonBox::Ok);
connect(buttonBox, &QDialogButtonBox::accepted, this, &QDialog::accept);
```

### ButtonBox
```cpp
QPushButton *okButton = new QPushButton("OK");
layout->addWidget(okButton);

connect(okButton, &QPushButton::clicked, this, [this]() {
    this->close(); 
});
```

### Connect
```cpp
connect(sender, signal, receiver, slot);
```

| 인자       | 의미            |
| -------- | ------------- |
| sender   | 시그널을 발생시키는 객체 |
| signal   | 발생시키는 시그널     |
| receiver | 슬롯을 소유하는 객체   |
| slot     | 실행할 함수 (슬롯)   |

### XML Parsing

QXMLStreamReader는 Event-driven Parser이다. 근데 파일 용량이 크니까 QXMLStreamReader가 유리하다.

| DOM 방식 (QDomDocument) | QXmlStreamReader |
| --------------------- | ---------------- |
| 전체 XML 메모리에 로드        | 한 줄씩 순차적으로 읽음    |
| 메모리 많이 먹음 (큰 파일 위험)   | 메모리 적게 먹음        |
| 구조 탐색 편함              | 직접 state 관리 필요   |
| 간단할 땐 편함              | 실전 대용량에 적합       |

