# FireStore 연동
> FireStore 연동시 발생 한 주요 에러 대처법에 대하여 정리해 보았습니다.


## 개발 환경 설정
Cloud Firestore Android 라이브러리를 app/build.gradle 파일에 추가합니다.
~~~gradle  
//구글 document에서 가이드 해준 버전
implementation 'com.google.firebase:firebase:firebase-firestore:20.2.0'

//실제로 사용한 버전
implementation 'com.google.firebase:firebaseㄴfirestore:17.1.3'
~~~
구글 document 에서 가이드 해준 버전을 사용하니 NoClassDefFoundError에러가 발생하여 이전버전을 사용하였다.

#### ClassNotFoundException Vs NoClassDefFoundError
* ClassNotFoundException : 클래스 로더가 클래스 패스에서 해당 클래스를 못찾으면 발생. 이에러가 발생하면 기본적으로 클래스 패스와 그 패스에 해당 클래스가 존재하는지 확인해야 한다.
* NoClassDefFoundError : 컴파일타임때 요구되는 클래스가 존재하지만 런타임 시점에서 클래스들이 바뀌거나, 제거되거나, 클래스의 스태틱 초기화가 예외를 던지면 이 에러가 발생한다.
**클래스 패스에 클래스가 존재하더라도, 이 클래스에 요구되는 클래스들 중 하나에 문제가 생겼기 때문**에 발생하는 에러이다.

## Permission denied Error 발생시
FireStore 연동 과정에서 Permission error 발생시 firestore 보안 규칙을 수정해야한다.  

보안규칙에 대한 설명은 다음 링크에서 제공해준다.
* firestore 보안규칙 [https://firebase.google.com/docs/firestore/security/get-started](https://firebase.google.com/docs/firestore/security/get-started)

## Reference
* 구글 Document : [https://firebase.google.com/docs/firestore/quickstart?hl=ko](https://firebase.google.com/docs/firestore/quickstart?hl=ko)
* ClassNotFoundException Vs NoClassDefFoundError : [https://hamait.tistory.com/348](https://hamait.tistory.com/348)