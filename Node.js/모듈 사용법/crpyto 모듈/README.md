# Crypto 모듈

- node.js에서 데이터 암호화 기능을 제공하는 모듈이다.
- 현재 존재하는 대부분의 암호화 알고리즘을 지원하고 있다.
- Crypto 모듈은 다음과 같이 생성한다.
~~~
var crpyto = require('crypto');
~~~

- getCiphers: 지원하는 암호화 알고리즘 이름들을 반환한다.
- createCipher : 암호화용 객체를 생성한다.
- createDecipher : 복호화용 객체를 생성한다.
- update : 데이터를 암호화 하거나 복호화 한다.
- final : 암호화된 데이터에 마지막 종료 블럭을 추가한다.

