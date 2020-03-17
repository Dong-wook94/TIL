# RESTful API



## REST란 ?

REST란 `REpresentational State Transfer의 약자`이다. 

REST는 `Resource Oriented Architecture`  즉, HTTP기반으로 필요한 자원에 접근하는 방식을 정해놓은 아키텍쳐이다.  API 설계의 중심에 자원(Resource)이 있고 HTTP Method를 통해 자원을 처리하도록 설계하는 것이다.

쉽게 말해서 **웹에 존재하는 모든 자원(이미지, 동영상, DB자원)에 고유한 URI를 부여해 활용하는 것**으로 자원을 정의 하고 자원에 대한 주소를 지정하는 방법론을 의미한다고 한다. 

 여기에 ~ful 이라는 형용사형 어미를 붙여 ~한 API 라는 표현으로 사용된다. 즉 REST의 기본 원칙을 성실히 지킨 서비스 디자인은 `RESTful하다` 라고 표현할 수 있다.



## REST 구성 

* **자원 (Resource)** - URI
* **행위 (Verb)** - HTTP Method
* **표현 (Representations)** 



## REST의 특징

1. Uniform(유니폼 인터페이스) 
   HTTP 표준에만 따른다면, 안드로이드/IOS 플랫폼이든, 특정 언어나 기술에 종속되지 않고 모든 플랫폼에 사용이 가능하며, URI로 지정한 리소스에 대한 조작이 가능한 아키텍처 스타일을 의미한다.
2. Stateless(무상태성) 
   REST는 무상태성 성격을 갖습니다. 다시말해 작업을 위한 상태정보를 따로 저장하거 관리하지 않습니다. 세션정보나 쿠키정보를 별도로 저장하고 관리하지 않기 때문에 API서버는 들어오는 요청만을 단순히 처리하면 됩니다. 때문에 서비스의 자유도가 높아지고 서버에서 불필요한 정보를 관리하지 않음으로써 구현이 단순해 집니다.
3. Casheable(캐시가능)
   REST의 가장 큰 특징 중 하나는 HTTP라는 기존 웹 표준을 그대로 사용하기 때문에 웹에서 사용하는 기존 인프라를 그대로 활용이 가능합니다. 따라서 HTTP 가 가진 캐싱 기능이 적용 가능합니다. HTTP 프로토콜 표준에서 사용하는 Last-Modified태그나 E-Tag를 이용하면 캐싱 구현이 가능합니다.
4. Self-descriptivness (자체 표현 구조)
   동사(Method) + 명사(URI) 로 이루어져 있어 어떤 메서드에 무슨 행위를 하는지 알 수 있으며, 메시지 포맷 역시 JSON을 이용해서 직관적으로 이해가 가능한 구조로, REST API 메시지만 보고도 이를 쉽게 이해할 수 있다.
5. Client - Server 구조
   REST 서버는 API 제공, 클라이언트는 사용자 인증이나 컨텍스트(세션, 로그인 정보)등을 직접 관리하는 구조로 각각의 역할이 확실히 구분되기 때문에 클라이언트와 서버에서 개발해야 할 내용이 명확해지고 서로간 의존성이 줄어들게 됩니다.
6. 계층형 구조
   REST 서버는 다중 계층으로 구성될 수 있으며 보안, 로드 밸런싱, 암호화 계층을 추가해 구조상의 유연성을 둘 수 있고 PROXY, 게이트웨이 같은 네트워크 기반의 중간매체를 사용할 수 있게 합니다.



## 대표적인 HTTP 메소드 4가지

* GET : 해당 리소스를 조회
* POST : 해당 URL를 요청하면 리소스를 생성
* PUT : 해당 리소스를 수정
* DELETE 해당 리소스를 삭제

## URI 설계 시 주의할점

1. 슬래시 구분자(/)는 계층 관계를 나타내는 데 사용

2. URI 마지막 문자로 슬래시(/)를 포함하지 않는다.

   ~~~
    http://restapi.example.com/houses/apartments/ (X)
    http://restapi.example.com/houses/apartments  (0)
   ~~~

3. 하이픈(-)은 URI의 가독성을 높이는데 사용

4. 밑줄(_)은 URI에 사용하지 않는다.

5. URI 경로에는 소문자가 적합하다.

6. 파일확장자는 URI에 포함하지 않는다.

   ~~~
   http://restapi.example.com/members/soccer/345/photo.jpg (X)
   ~~~

   

### References
* https://dong-co.tistory.com/8
* https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/master/Development_common_sense
* https://medium.com/@dydrlaks/rest-api-3e424716bab
* https://brainbackdoor.tistory.com/53
* https://meetup.toast.com/posts/92