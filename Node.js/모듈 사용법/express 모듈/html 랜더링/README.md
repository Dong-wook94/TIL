# html 랜더링

- express 모듈은 외부 파일의 데이터를 읽어와 html 코드로 만든다음 클라이언트에게 전달하는 기능을 제공하는데 이를 랜더링이라고 부른다.

- express 에서 랜더링을 위해서는 다른 모듈을 사용해야 하는데 여기에서는 ejs 모듈을 사용하도록 한다.

## ejs 모듈 사용하기
- ejs 모듈을 사용하기 위해 모듈 객체를 생성한다.
~~~js
var ejs = requre("ejs");
~~~

- 다음으로 html 파일을 만들어 놓을 폴더를 지정한다.
~~~js
app.set("views",__dirname+"/views");
~~~

- 다음으로 랜더링에 사용할 모듈을 지정한다.
~~~js
app.set("view engine","ejs");
~~~

- 다음으로 html일 경우 사용할 ejs 모듈을 지정한다.
~~~js
app.engine("html",ejs.renderFile);
~~~

## 정적 파일 사용하기
- html 문서에서 css,js,imgae,동영상, 사운드 등의 파일들을 사용할 때는 정적 파일이 위치하는 폴더를 지정하여 사용할 수 있다.