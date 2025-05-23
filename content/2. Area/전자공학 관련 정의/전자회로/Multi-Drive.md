- **정의**: 하나의 net(배선)을 **여러 개의 source**가 동시에 구동하는 상태.
    
- **문제점**:
    
    - 서로 다른 로직이 **충돌**하면 전압 불안정, 누설 전류, 고장 가능.
        
    - 예: 두 개의 output이 하나의 net을 서로 다른 값으로 구동할 때.
        
- **방지 방법**:
    
    - tri-state 버퍼, mux 등을 사용해 **서로 다른 드라이버가 동시에 작동하지 않도록** 설계해야 함.

>[!reflection]
>두 개의 전압 소스가 같은 배선에 연결되어 서로 다른 전압을 출력한다면, 이는 전압 충돌을 일으켜 회로에 문제가 발생할 수 있다. 이런 상황이 multi-drive라고 한다.
>==쉽게 말해, 병렬 연결된 전압원이 동시에 다른 전압을 출력하려고 하면, 전압 충돌이 일어나 회로에 문제가 발생하는 것.==