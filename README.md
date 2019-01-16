# Spring-Study
Spring 공부를 위한 repository

## 1. 웹 프로그래밍 설계 모델


### WAS (Web Application Server)
 - 설계 모델
   - mode1, model1으로 나뉨, model1은 html java 등 컨트롤러 부분과 view 부분을 나누지 않고 모두 한 파일로 만드는 것 최근엔 분리한 model2가 대부분
   
 - 사용자의 요청 처리과정
   - 클라이언트가 브라우저로 어떤 작업 요청
   - WAS에서 DB와 통신과 service 작업 등 요청을 잘 처리해 다시 브라우저로 응답 반환
   
 - MVC 모델
   - 소프트웨어 디자인 패턴 사용자 인터페이스로 부터 비즈니스로직의 분리 model(data), controller( data 와 비즈니스 로직 상호작용), view (사용자에게 보여지는 것)으로 나누어 개발하는 것 (https://ko.wikipedia.org/wiki/%EB%AA%A8%EB%8D%B8-%EB%B7%B0-%EC%BB%A8%ED%8A%B8%EB%A1%A4%EB%9F%AC)
   - 장점으로는 유지보수의 편리함과 서로의 영향을 최소화한다
   
 - 스프링에서 MVC 모델 설계 구조
   - 요청을 가장 먼저 DispatcherServlet이 받아 가장 HandlerMapping에게 전달
   - HandlerMapping은 가장 적합한 controller 선택하도록한다.
   - HandlerAdapter는 요청에 맞는 controller의 method중 적절한 method를 사용하게 한다.
   - controller에서 DB에서 데이터를 가져오고 service 처리된 것을 viewResolver가 적절한 출력을 하기위해 가장 적합한 view를 찾아 응답을 만든다
   - 만들어진 View는 클라이언트(브라우저)로 응답된다.
   - 개발자는 Controller와 View DAO DB 등을 개발하여 spring의 잘 갖추어진 servlet,mapping,adapter,viewresolver는 적절히 맞게 쓰기만 하면된다.
