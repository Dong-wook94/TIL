# 데이터 통신

데이터 : 데이터를 만들어 사용하는 사용자 간에 합의딘 형태로 표현된 정보.

데이터 통신 : 멀리 떨어져 있는 입출력 장치와 컴퓨터를 통신회선을 이용하여서 넓은 범위의 데이터 처리와 데이터 전송을 종합적으로 가능케 하는 방식.

 

### 데이터 통신의 목표

1. 데이터 전송의 **정확성**
   1. 데이터의 전송중 신호 감쇄, 잡음 등에 의한 형태의 변경 -> 잘못된 정보 전송
   2. 정확성을 위한 기술 : 채널 코딩 / 에러제어 코딩, 동기 기술, 스위칭 기술, 어드레싱/네이밍 기술, 흐름제어 기술
2. 데이터 전송의 **안정성**
   1. 데이터의 내용이 제 3자에게 누출되거나 변형되면 안됨.
   2. 안정성을 위한 기술 : 비화 코딩
3. 데이터 전송의 **효율성**
   1. 획득 정보의 가치가 데이터 전송 장비의 가치보다 작으면 비효율적 이다.
   2. 효율성을 위한 기술 : 소스코딩, 다중화 기술

 

 

### 데이터 통신의 구성 요소



![img](https://k.kakaocdn.net/dn/ccramP/btqCPAX4tB5/YsNfiZDVVIjwrItx0EjWp0/img.png)



- 메시지(Message)
  - 통신의 대상이 되는 정보(데이터)
  - 문자, 숫자, 그림, 시로, 영상 또는 이들의 조합.
- 전송매체(Transmission medium)
  - 메시지가 송신자로부터 수신자에게 전다로디는 물리적 경로
  - twisted pair wire(꼬임쌍선), coaxial cable(동축 케이블), fiber-optic cable(광케이블), laser 또는 wireless wave
- 프로토콜(Protocol)
  - 데이터 통신을 제어하는 약속 또는 규칙들의 집합
  - 데이터 통신을 하기위한 통신 규약이라 생각하면 된다.
- 송신자(Sender)
  - 메시지의 생성 및 송신을 담당하는 장치
  - 컴퓨터, 전화기, 비디오 카메라 등
- 수신자(Receiver)
  - 전송매체를 통해 전송된 메시지를 수신하는 장치
  - 컴퓨터, 전화기, TV

### **데이터 흐름 방향**

- **단방향 방식(simplex mode)**
  - 한쪽 방향으로만 통신이 가능
  - 한 지국은 송신만, 다른 한 지국은 수신만 가능



![img](https://k.kakaocdn.net/dn/mZIiM/btqCNGZiwyn/PZfKnJblyakKP38BkC9Q5k/img.png)



- **반이중 방식(half-duplex mode)**
  - 각 지국들은 송, 수신이 가능
  - 각 지국간 동시에 송신 불가
  - 예 : 워키토키, 민간방송용 라디오(CB radio)



![img](https://k.kakaocdn.net/dn/lNCuy/btqCQ4YG8DE/5zQ8tbyN1wo2wsDMJAVKpk/img.png)



- **전이중 방식(full-duplex mode)**
  - 양족 지국간 동시에 송/수신이 가능
  - 양방향으로 통행이 가능한 2차선 도로와 같음
  - 신호는 링크의 용량을 공유해서 양방향으로 전달.
  - 예 : 전화



![img](https://k.kakaocdn.net/dn/bSVp9v/btqCOyfo1EL/yI9ZRXVAMn1fjVdA6qynz0/img.png)





### **Reference**

- https://blog.naver.com/james_parku/110146907297
- https://dong-co.tistory.com/10