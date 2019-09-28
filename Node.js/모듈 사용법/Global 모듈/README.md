# Global 모듈

- node.js에서 모듈을 생성하지 않고 사용할 수 잇는 것들을 가지고 있는 모듈 객체이다.

- Global 모듈 객체는 프로그램 시작과 동시에 생성이 되며 어디서든 사용이 가능하다.
- Buffer : 메모리를 동적할당 할 수 있는 모듈
- __dirname : 현재 실행중인 파일의 경로를 가지고 있다.
- __filename : 현재 실행주인 파일의 경로와 파일명을 가지고 잇다.
- setImmediate : 하나의 사건처리가 끝나면 동작할 코드를 등록한다.
- clearImmediate : 등록된 Immediate 를 제거한다.
- setInterval : 주어진 함수를 주어진 시간마다 계속 호출한다.
- clearInterval : 등록된 Interval을 제거한다.
- setTimeout : 주어진 한수를 주어진 시간 후에 한번 호출한다.
- clearTimeout : 등록된 Timeout을 제거한다.
- console : 화면 출력을 위한 객체이다.
- exports : 개발자가 모듈을 만들때 사용하는 객체이다.
- require : 모듈 객체를 만드는 함수이다.