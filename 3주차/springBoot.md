![image](https://user-images.githubusercontent.com/48851895/130092956-2a24d863-fdc4-425d-b942-737c6a74580c.png)
- 스프링부트 버전 : 2.5.4

- pom.xml에 오류 발생..
  - 오류 및 해결방법: https://jjunii486.tistory.com/92

- 실행방법
  - Run As Java..!
  - 참고 : https://offbyone.tistory.com/391

- 오류 발생
  - Description:

Field uMapper in com.example.settingweb_boot.service.StatisticServiceImpl required a bean of type 'com.example.settingweb_boot.dao.StatisticMapper' that could not be found.

The injection point has the following annotations:
	- @org.springframework.beans.factory.annotation.Autowired(required=true)


Action:

Consider defining a bean of type 'com.example.settingweb_boot.dao.StatisticMapper' in your configuration.

  - ![image](https://user-images.githubusercontent.com/48851895/130188448-19a52cef-3711-4aa7-a49e-07a97af5c900.png)여기서 devfun을 example로 바꿨는데도 여전히 같은 오류 뜸..
  
  
  - ![image](https://user-images.githubusercontent.com/48851895/130188767-7eb04892-4a4a-427b-9039-9b6a8550ff6f.png) 여기가 오류였음. 밑줄부분을 devfun에서 example로 변경했더니 됨.
  
  
  - ![image](https://user-images.githubusercontent.com/48851895/130188843-ed645e35-935d-4169-9c0e-03949a393189.png)아직 DB 입력 전임..

  - ![image](https://user-images.githubusercontent.com/48851895/130224221-5a438adc-6da1-425b-bc0a-55768b789b1b.png) 비밀번호로 바꿔주고..
  - ![image](https://user-images.githubusercontent.com/48851895/130224642-0b7da864-6f10-4310-9642-2f91a7ab0340.png) MySQL Workbench에다가 DB도 만듦.
  - 최종 결과
  ![image](https://user-images.githubusercontent.com/48851895/130224725-f85b38a9-af59-4f85-94d3-2fe85200228e.png)


