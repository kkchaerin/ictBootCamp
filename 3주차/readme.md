### Spring Framework
1. REST(Respresentational State Transfer)
- 기본개념
  - 하나의 URI는 하나의 고유한 리소스를 대표하도록 설계되었다는 개념이다.
  - REST 방식은 특정한 URI는 반드시 그에 상응하는 데이터 자체라는 것을 의미한다.

- Rest API
  - 외부에서 위와 같은 방식으로 특정 URI를 통해 사용자가 원하는 정보를 제공하는 방식이다.

- 스프링에서의 REST
  - 스프링3버전 부터 @Responsebody 어노테이션을 지원하게 되면서, REST 방식의 처리를 지원하고 있다.
  - 스프링4부터는 @RestController를 통해 구현이 가능하다.

2. @RestController 어노테이션
- @RestController 
  - 스프링4부터 사용가능함.
  - 기존의 특정한 JSP와 같은 뷰를 만들어 내는 것이 목적이 아니라, REST 방식의 데이터를 처리하기 위해 사용하는 어노테이션이다.
  - 이때, 반환되는 데이터로 사용되는 것은 단순 문자열(Json, XML)이다.
  
- @Controller, @ResponseBody
  - 스프링3에서는 컨트롤러는 @Controller만 사용해서 처리했기 때문에, 화면 처리를 담당하는 JSP가 아닌 데이터자체를 서비스 하려면 해당 메서드나 리턴 타입에 @ResponseBody 어노테이션을 추가하는 형태로 작성했다.

3. @RestController 예제
- 기존에는 @Controller를 붙였지만, @RestController 를 붙이면 된다.
```
@RequestMapping("\hello")
public String sayHello(){
  return "Hello World";
}
```
![image](https://user-images.githubusercontent.com/48851895/130063532-9677bb71-5646-4818-9227-ba54a14c4775.png)
