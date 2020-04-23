# Servlet Lifecylcle



## **LifecycleServlet**

HttpServlet의 3가지 메소드를 오버라이딩

- init()
  - 서블릿은 init() 메서드를 호출하여 초기화된다.
- service(request, response)
  - 서블릿은 service() 메서드를 호출하여 클라이언트의 요청을 처리한다.
- destroy()
  - 서블릿은 destroy() 메서드를 호출하여 종료한다.

[![img](https://cphinf.pstatic.net/mooc/20180124_22/1516782982944xjogH_PNG/1_5_3_ServletLifcycle.PNG?type=w760)](https://www.edwith.org/boostcourse-web/lecture/16688/#)

## **Servlet 생명주기**

- WAS는 서블릿 요청을 받으면 해당 서블릿이 메모리에 있는지 확인합니다.
-  if (메모리에 없음) {
   \- 해당 서블릿 클래스를 메모리에 올림
   \- init() 메소드를 실행
  }
   \- service()메소드를 실행
- **was가 종료되거나, 웹 어플리케이션이 새롭게 갱신될 경우** destroy() 메소드가 실행됩니다.



왜 이전까지는 service 메서드 없이 실행됐지?

**service(request, response) 메소드**

HttpServlet의 service메소드는 템플릿 메소드 패턴으로 구현합니다.

- 클라이언트의 요청이 GET일 경우에는 자신이 가지고 있는 doGet(request, response)메소드를 호출
  - url에서 직접넘어가면 GET
- 클라이언트의 요청이 Post일 경우에는 자신이 가지고 있는 doPost(request, response)를 호출



### Reference

* https://www.edwith.org/boostcourse-web/lecture/16688/