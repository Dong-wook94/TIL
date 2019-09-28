# basic module

## 모듈 사용하기
- node.js에서 자주 사용하는 함수의 경우 별도의 js 파일에 만들어 주면 되는데 이 때 모듈이라는 개념을 사용한다.

- node.js에서는 js파일이 하나의 모듈이 되며 이는 하나의 객체 단위로 생각하면 된다. 

- exports 객체에 필요한 함수를 추가하여 준다.

~~~js
exports.f2 = function(){
    console.log("f2 함수호출");
}
~~~

- require 함수를 이요애 모듈 객체를 생성한다
~~~js
var test = require("/.second.js");
~~~

- 모듈 객채를 이용해 함수를 호출한다.
~~~js
test.f2();
~~~

- node.js 는 모듈이라는 개념을 사용하여 외부 파일의 기능을 가져다 사용할 수 있다.
