# 웹프로그래밍 기초

## HTTP의 이해

**HTTP (Hypertext Transfer Protocol)란?**

- 팀 버너스리(Tim Berners-Lee)와 그가 속한 팀은 CERN에서 HTML뿐만 아니라 웹 브라우저 및 웹 브라우저 관련 기술과 HTTP를 발명하였습니다.
- 문서화된 최초의 HTTP버전은 HTTP v0.9(1991년)입니다.
- HTTP는 서버와 클라이언트가 인터넷상에서 데이터를 주고받기 위한 프로토콜(protocol)입니다.
- HTTP는 계속 발전하여 HTTP/2까지 버전이 등장한 상태입니다.

 

**HTTP 작동방식**

- HTTP는 서버/클라이언트 모델을 따릅니다.
- 장점
  \- 불특정 다수를 대상으로 하는 서비스에는 적합하다.
  \- 클라이언트와 서버가 계속 연결된 형태가 아니기 때문에 클라이언트와 서버 간의 최대 연결 수보다 훨씬 많은 요청과 응답을 처리할 수 있다.
- 단점
  \- 연결을 끊어버리기 때문에, 클라이언트의 이전 상황을 알 수가 없다.
  \- 이러한 특징을 무상태(Stateless)라고 말한다.
  \- 이러한 특징 때문에 정보를 유지하기 위해서 Cookie와 같은 기술이 등장하게 되었다.

 

**URL (Uniform Resource Locator)**

- 인터넷 상의 자원의 위치
- 특정 웹 서버의 특정 파일에 접근하기 위한 경로 혹은 주소

- **HTTP (Hypertext Transfer Protocol)**

- 요청 메서드 : GET, PUT, POST, PUSH, OPTIONS 등의 요청 방식이 온다.
- 요청 URI : 요청하는 자원의 위치를 명시한다.
- HTTP 프로토콜 버전 : 웹 브라우저가 사용하는 프로토콜 버전이다.

첫번째 줄의 요청메소드는 서버에게 요청의 종류를 알려주기 위해서 사용됩니다.

각각의 메소드 이름은 다음과 같은 의미를 가집니다.

참고로 최초의 웹 서버는 GET방식만 지원해줬습니다.

- GET : 정보를 요청하기 위해서 사용한다. (SELECT)
- POST : 정보를 밀어넣기 위해서 사용한다. (INSERT)
- PUT : 정보를 업데이트하기 위해서 사용한다. (UPDATE)
- DELETE : 정보를 삭제하기 위해서 사용한다. (DELETE)
- HEAD : (HTTP)헤더 정보만 요청한다. 해당 자원이 존재하는지 혹은 서버에 문제가 없는지를 확인하기 위해서 사용한다.
- OPTIONS : 웹서버가 지원하는 메서드의 종류를 요청한다.
- TRACE : 클라이언트의 요청을 그대로 반환한다. 예컨데 echo 서비스로 서버 상태를 확인하기 위한 목적으로 주로 사용한다.



## 웹서버



**웹 서버란?**

- 웹 서버는 소프트웨어(Software)를 보통 말하지만, 웹 서버 소프트웨어가 동작하는 컴퓨터를 말합니다.
- 웹 서버의 가장 중요한 기능은 클라이언트(Client)가 요청하는 HTML 문서나 각종 리소스(Resource)를 전달하는 것입니다. 
- 웹 브라우저나 웹 크롤러가 요청하는 리소스는 컴퓨터에 저장된 정적(static)인 데이터이거나 동적인 결과가 될 수 있습니다.

 ![image](https://user-images.githubusercontent.com/36303777/71472782-ae309600-2817-11ea-901a-bc3700a08424.png)

**웹 서버 소프트웨어의 종류**

- 가장 많이 사용하는 웹 서버는 Apache, Nginx, Microsoft IIS
- Apache웹 서버는 Apache Software Foundation에서 개발한 웹서버로 오픈소스 소프트웨어(Open-source Software)이며, 거의 대부분 운영체제에서 설치 및 사용을 할 수 있습니다.
- Nginx는 차세대 웹서버로 불리며 더 적은 자원으로 더 빠르게 데이터를 서비스하는 것을 목적으로 만들어진 서버이며 Apache웹 서버와 마찬가지로 오픈소스 소프트웨어입니다.



## WAS

**클라이언트/서버 구조**

클라이언트(Client)는 서비스(Service)를 제공하는 서버(Server)에게 정보를 요청하여 응답 받은 결과를 사용합니다.

[![img](https://cphinf.pstatic.net/mooc/20180213_10/151849899068982T3i_PNG/05.png?type=w760)](https://www.edwith.org/boostcourse-web/lecture/16666/#)

- **클라이언트/서버 구조**

**DBMS (DataBase Management System)**

다수의 사용자가 데이터베이스 내의 데이터에 접근할 수 있도록 해주는 소프트웨어입니다.

[![img](https://cphinf.pstatic.net/mooc/20180122_74/15166087526093WS9P_PNG/1_1_7_DBMS.PNG?type=w760)](https://www.edwith.org/boostcourse-web/lecture/16666/#)

- **DBMS (DataBase Management System)**

**미들웨어 (MiddleWare)**

클라이언트 쪽에 비즈니스 로직이 많을 경우, 클라이언트 관리(배포 등)로 인해 비용이 많이 발생하는 문제가 있습니다.

비즈니스 로직을 클라이언트와 DBMS사이의 미들웨어 서버에서 동작하도록 함으로써 클라이언트는 입력과 출력만 담당하도록 합니다.

[![img](https://cphinf.pstatic.net/mooc/20180122_267/1516608805247GN2hK_PNG/1_1_7_.PNG?type=w760)](https://www.edwith.org/boostcourse-web/lecture/16666/#)

- **미들웨어(MiddleWare)**

**WAS (Web Application Server)**

WAS는 일종의 미들웨어로 웹 클라이언트(보통 웹 브라우저)의 요청 중 웹 애플리케이션이 동작하도록 지원하는 목적을 가집니다.

[![img](https://cphinf.pstatic.net/mooc/20180122_270/1516606715302CWRJG_PNG/1_1_7_was.PNG?type=w760)](https://www.edwith.org/boostcourse-web/lecture/16666/#)

- **WAS (Web Application Server)**

**웹 서버 vs WAS**

- WAS도 보통 자체적으로 웹 서버 기능을 내장하고 있습니다.
- 현재는 WAS가 가지고 있는 웹 서버도 정적인 콘텐츠를 처리하는 데 있어서 성능상 큰 차이가 없습니다.
- 규모가 커질수록 웹 서버와 WAS를 분리합니다.
- 자원 이용의 효율성 및 장애 극복, 배포 및 유지보수의 편의성을 위해 웹서버와 WAS를 대체로 분리합니다.