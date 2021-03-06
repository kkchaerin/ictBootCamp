## 직무부트캠프 2주차 과제 

***

### HTTP (HyperText Transfer Protocol)

- 링크 기반으로 데이터를 요청하고 받는다.

- 클라이언트와 서버가 요청을 하고, 응답하기 위해 따르는 프로토콜이다.

- html 문서를 주고 받을 수 있고, 이미지, 동영상, 오디오, 텍스트 문서 등을 주고 받을 수 있다.

- HTTP 동작방식![image-20210810154635894](C:\Users\lg\AppData\Roaming\Typora\typora-user-images\image-20210810154635894.png)

  - 클라이언트: 웹 애플리케이션의 경우, 브라우저를 통해서 서버에 요청한다. 
  - 서버: 클라이언트로부터 받은 요청을 내부적으로 처리해 그에 대한 결과를 응답한다.

- HTTP 특징 및 기능

  1. connectionless + stateless

     - 1번 요청-응답 후 연결을 해체함.
     - 클라이언트의 이전 상태를 알 수 없다: 쿠키와 세션이 필요함
     - 수십만 명이 웹서비스를 사용(요청)하더라도 최소 유지를 할 수 있기 때문에, 많은 유저의 요청을 처리할 수 있다.

  2. keep-alive (http 1.1부터 지원함.)

     - http 는 1번 요청에 대해서 1번 응답하는 것을 기준으로 설계한다.

     - 웹사이트는 하나의 페이지에 수십개의 이미지, 수십개의 css파일, js파일들로 구성된다.

     - 1요청-1응답 기준이라면, 여러번 연결을 끊었다 해야해서 비효율적이다.

     - keep-alive 지원으로 지정된 시간 동안 연결을 끊지 않고, 연결된 상태를 유지할 수 있다.

     - keep-alive의 time out 내 클라이언트가 재요청을 하면, 새로운 연결이 아닌 기존 연결된 것을 이용한다.

       - 웹서버 연결. html 문서 다운로드. 필요한 img,css,js등을 다운로드. 연결 끊음.

         HTTP method와 Rest API : 요청의 종류를 서버에 알리기 위해 사용한다. 게시판 기능을 만들때 사용한다. 

  

  ###  HTTP method와 Rest API 

  - 요청의 종류를 서버에 알리기 위해 사용한다. 게시판 기능을 만들때 사용한다. 

  - 메소드 종류: GET(정보 요청), POST(정보 입력), PUT(정보 업데이트), DELETE(정보 삭제)
  - REST API란: HTTP 프로토콜 장점을 살릴 수 있는 네트워크 기반 아키텍처임.
    - REST API를 구현하려면, HTTP method+ 모든 개체 resource화+ URL디자인(라우팅)이 필요하다.
    - URI를 이용한 접근: 모든 개체를 리소스로 보고, 리소스에 고유번호를 부여한다.
    - URL 디자인 원칙: 자원에 대한 처리를 주소에 나타내지 않는다. // HTTP method는 내부적으로 처리하도록함..
    - REST API를 구현하기 위해 HTTP 프로토콜에 대한 이해, method 종류, 라우팅에 대한 이해가 있어야 한다.
    - HTTP method를 클라이언트가 필요한 처리에 맞게 선택하여 서버에 요청한다.
    - 

  

  

  



### Rest API

1. REST(Representational State Transfer) 아키텍쳐의 제약조건을 준수하는 애플리케이션 프로그래밍 인터페이스를 의미한다.

   - 웹에 존재하는 모든 자원(img, video, DB자원)에 고유한 URI를 부여해 활용하는 것이다.

   - HTTP URI를 통해 자원을 명시하고, HTTP method를 통해 해당 자원에 대한 CRUD 오퍼레이션을 적용하는 것을 의미한다.

     *CRUD 오퍼레이션: create(POST), read(GET), update(PUT), delete(DELETE), head(HEAD)*

   - REST 는 네트워크 상에서 CLIENT와 SERVER사이의 통신 방법 중 하나이다.

   - Rest는 기본적으로 웹의 기존 기술과 HTTP 프로토콜을 그대로 활용하기 때문에, 웹의 장점을 최대한 활용할 수 있는 아키텍처 스타일이다.

   - 장점

     - HTTP 프로토콜의 인프라를 그대로 사용하므로, REST API 사용을 위한 별도 인프라를 구축할 필요없음.
     - HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용 가능함.
     - Hypermedia API의 기본을 충실히 지키면서, 범용성을 보장함.
     - REST API메시지가 의도하는 바를 명확하게 나타내므로 의도하는 바를 쉽게 파악할 수 있음.
     - 서버와 클라이언트의 역할을 명확히 분리함.

   - 단점

     - 표준이 없음.
     - 사용할 수 있는 메소드가 4가지 뿐임. (HTTP method 형태가 제한적임.)

   - REST가 필요한 이유: 애플리케이션의 분리 및 통합. 다양한 클라이언트의 등장(다양한 브라우저 및 디바이스).

   - REST의 구성요소

     1.  자원: URI
        - 모든 자원에 고유한 ID가 존재, 이 자원은 서버에 존재함.
        - 자원을 구별하는 ID는 HTTP URI이다.
        - CLIENT는 URI를 이용해 자원을 지정하고, 해당 자원의 상태(정보)에 대한 조작을 SERVER에 요청한다.
     2. 행워: HTTP Method
        - HTTP 프로토콜의 Method를 사용함 : GET, POST, PUT, DELETE
     3. 표현

   - 6가지 조건: Uniform interface, client-server, stateless, cachable, layered system, code on demand(optional)

   - REST의 구성

   - ![image-20210810164438877](C:\Users\lg\AppData\Roaming\Typora\typora-user-images\image-20210810164438877.png)

     - LEVEL 0: 웹의 기본 메커니즘을 전혀 사용하지 않는 단계. 하나의 URI를 가지고, 하나의 HTTP method(주로 POST)를 사용한다. 내용에 대한 구분은 xml을 payload로 사용해서 요청을 구분하는 방식을 사용한다. 모든걸 하나의 리소스를 가지고 처리한다.
     - LEVEL 1 - resource: 함수를 호출하고 인자들을 넘기는 것이 아니라, 다른 정보를 위해 인자들을 제공하는 특정 리소스로 요청을 보낸다. 이점은 자원이 외부에 보여지는 방식과 내부에 저장되는 방식을 분리할 수 있다는 것이다. 예를 들어, 클라이언트 단에서 완전히 다른 포맷으로 저장하더라도, JSON 형태의 데이터를 요청할 수 있다. 다양한 URI를 사용하지만, HTTP method는 하나만 사용한다.  
     - LEVEL 2 - HTTP method: LEVEL1의 URL+HTTP method. 리소스를 구분하는 것으로 응답 상태를 HTTP status code를 활용한다. 현재 가장 많은 Restful API가 이 단계를 제공한다. 
       - 발생한 에러의 종류를 커뮤니케이션하기 위해 상태 코드를 사용한다.  : 기존에는 유저 생성 요청 시, redirect request를 서버에서 내려주는 방식이었지만, 지금은 created로 유저 생성을 알릴 뿐이지, 이동은 client단에서 해결하는 방식을 사용한다. 즉, 서버는 순수하게 api로서의 기능만 제공하면 되고, view는 클라이언트에서 표시해준다.
       - 안전한 오퍼레이션(GET 등)과 안전하지 않은 오퍼레이션 간의 강한 분리를 제공한다. : http에서 GET은 호출 순서나 횟수에 영향받지 않고 매번 같은 결과를 받을 수 있게 한다. 따라서 모든 request에 캐싱 기능을 지원하는 다양한 방법을 제공한다.

2. API(Application Programming Interface)는 애플리케이션 sw를 구축하고, 통합하는 정의 및 프로토콜 세트이다. 컴퓨터나 시스템과 상호작용하여 정보를 검색하거나 기능을 수행하고자 할때 API는 사용자가 원하는 것을 시스템에 전달할 수 있게 지원하여, 시스템이 이 요청을 이해하고 이행하도록 한다.



### 브라우저에 URL입력했을때

예) 웹 브라우저에 "www.daum.net"을 입력했다면

### ![웹브라우저 동작원리](D:\2021-여름방학\성남산업진흥원\직무부트캠프\웹브라우저 동작원리.png)

1. 브라우저의 URL파싱 : 입력받은 URL의 구조를 해석한다.프로토콜 종류, 도메인, 포트 등을 해석한다.

2. URL을 IP주소로 변환 

   - 컴퓨터가 읽을 수 있는 IP주소로 변환해야 한다. 
   - 먼저, 브라우저는 자신의 로컬 hosts 파일과 브라우저 캐시에 해당 URL이 존재하는지 확인.
     - 존재하지 않는다면, 도메인 주소(URL)를 IP주소로 변환해주는 DNS서버에 요청해 해당 URL을 IP주소로 변환한다 : 미리 설정된 LOCAL DNS에 해당 URL주소의 IP주소를 요청 -> Local DNS서버에 존재한다면 응답, 없다면 다른 DNS서버와 통신. root DNS 서버에 요청 -> root DNS서버에 해당 IP주소가 없다면, 하위 DNS서버에 요청하라고 응답. 이 응답을 받은 Local DNS서버는 .net 도메인을 관리하는 DNS 서버에 요청. ->.net DNS서버에 해당 IP주소가 없다면, 하위 DNS 서버에 요청하라고 한다. 다시 daum.net 도메인관리 DNS 서버에 요청 -> daum.net DNS 서버에서 IP주소를 응답받은 Local DNS는 해당 IP주소를 캐싱하고 응답한다.

3. 라우터를 통해 해당 서버의 게이트웨이까지 이동 

   : 해당 IP주소로 가는 경로는 라우팅(routing)을 통해 알아낸다. 라우터가 라우팅 테이블을 통해 해당 요청의 경로를 정해준다.

4. ARP통해 IP주소를 MAC주소로 변환 : 논리주소(IP)를 물리주소(MAC)으로 변환해야 함. 이를 위해 해당 네트워크 내에서 ARP를 브로드 캐스팅한다. 해당 IP주소를 가지고 있는 노드는 자신의 MAC 주소를 응답한다.

5. 대상 서버와 TCP소켓 연결 : 소켓 연결은 3-way-handshaking 과저을 통해 이뤄짐. HTTPS 요청이라면, TLS 핸드쉐이킹이 추가된다(암호화 통신).

6. HTTP(HTTPS) 프로토콜로 요청, 응답 : 연결이 확정되면 해당 페이지를 달라고 서버에게 요청. 서버에서는 요청을 받아, 검사한다. 그리고 이 요청에 대한 응답을 생성해 브라우저에게 전달.

7. 브라우저에서 응답을 해석 : 서버에서 응답한 내용은 HTML, CSS, Javascript 등으로 이뤄짐. 이를 브라우저에서 해석해 그려줌.



***

### 코멘토의 주차별 내용

- 백엔드 실무 체험을 위해 '총 로그인 수 조회 API서비스'를 직접 구축해보고자 한다. 

- 백엔드 개발자는 프론트엔드 개발자와의 협업을 위한 API가이드를 작성한다. 서로 주고 받을 데이터의 룰을 정하는 것이다.
  - 가이드 문서는 통신방법, 입력 파라미터, 출력 정보 등을 포함한다.
  
  - 2차 과제는 마지막 주차에 완성할 sw활용 현황 통계 API문서 초안을 작성하며 Restful API에 대한 학습을 진행한다.
  
  - *이 과제 수행이 중요한 이유*: API 가이드 문서 작성을 통해 백엔드 개발자와 프론트 엔드 개발자가 어떻게 소통하는지 이해할 수 있다. API 인터페이스 가이드의 내용에는 통신 방법, 데이터 포맷, 입력 파라미터, 출력 정보 등이 포함되어 있어 개바릐 기초가 개념들을 정립하는데에도 크게 도움이 된다. 그리고 해당 문서를 초안으로 마지막 과제에서 최종 완성을 하며, 협업과 개발의 프로세스를 익혀보는 중요한 요소이다.
  
    

***

- 본 과제는 최종 과제의 초안 문서이다.
- 카카오 예시를 보고 API문서 가이드 작성을 진행하자.
- [관심키워드 데이터셋 API 가이드 문서](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/8380ec34-0930-4617-841a-160c724cc56d/kakaoAPI_____(1).pdf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210810%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210810T054306Z&X-Amz-Expires=86400&X-Amz-Signature=fc207706510e3a629285bd08c38f08a9b3e789dd2b87199523aa8aa7407d70a0&X-Amz-SignedHeaders=host&response-content-disposition=filename %3D"kakaoAPI_%EC%B0%B8%EA%B3%A0%EB%AC%B8%EC%84%9C_%EA%B4%80%EC%8B%AC%20%ED%82%A4%EC%9B%8C%EB%93%9C%20%EB%B6%84%EC%84%9D%20(1).pdf")



- API 가이드 문서는 데이터를 어떻게 주고받을지에 대한 개발자간의 소통이다.
- 경우에 따라서 팀간의 소통, 백엔드와  프론트엔드 개발자 간의 소통 방법이다.
- 클라이언트(=프론트엔드)개발자가 서버에 어떤 값을 넘겨주면 어떤 데이터를 응답해줄 지에 대한 내용을 정의한다.
- 경우에 따라서, 해당 데이터를 어떤 식으로 활용할 지 예시를 함께 작성하기도 한다.
- 그리고 어떤 데이터 포맷으로 응답할지에 대한 예시도 문서로 함께 작성한다.- 



- 백엔드 API 만들기 과정에서 필요한 API를 직접 정의(API 제목, API 기능)하여 만들어 보기!
- 확인 필요한 내용
  - 요청 URL, 요청 Parameter, 응답 바디의 확인이 필요하다.
  - 어떤 URL로 어떤 파라미터를 넘겼을 때 어떤 응답이 오는지 확인할 수 있다.
  - 예시 문서에서 pathVariable방식으로 응답을 요청하고, JSON 포맷으로 데이터를 응답하는게 특징이다.
  - 그리고 API의 특징은 http 통신으로 이루어지고 있다는 점이다.
    - 예시 문서를 작성하며 pathVariable, JSON, HTTP에 대한 키워드를 함께 학습해보자.
    - 그리고, 해당 내용은 차주 퀴즈 문제의 주요 내용이 될 것이다...!
- SW활용률에 필요한 데이터가 무엇일지 고민해보고 해당 내용에 맞게 문서를 작성한다.
- 참고 
  - 작성방법: GITHUB에 PPT/WORD 로 등록(문서는 자유)
  - 수행중 질문사항은 카톡 활용
- 필수로 진행하기!
  - Rest API가 무엇인지 학습하고, GITHUB에 올리기
    - HTTP 통신에 관하여..
    - 브라우저에 URL을 입력한 수 요청하여 서버에 응답하는 과정까지에 대해 학습한 내용을 작성하기.
- 개인 GITHUB에 올리고, 코멘토 클래스 룸에 GITHUB 링크를 메모장에 작성하여, TXT 파일로 등록
