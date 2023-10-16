# Programming

---
### RESTFUL API
- REST(Representational State Transfer) 아키텍처를 따르는 API(Application Programming Interface)를 말한다.
- API 를 Restful 하게 정의하는 것이다.
    - 여기서, Restful한 방식은 URL은 **자원**, HTTP Method 는 **행위** 라고하는 역할을 구분해서 설계하는 것이다.
- 즉, HTTP URL(Uniform Resources Identifiler)를 통해 자원(Resource)을 명시하고,

  HTTP Method(POST, GET, PUT, DELETE)를 통해 해당 자원에 대한 CRUD Operation을 적용하는 것을 의미한다.

    - CRUD Operation
        - Create : 생성(POST)
        - Read : 조회 (GET)
        - Update : 수정(PUT)
        - Delete : 삭제( DELETE)
      
- **REST가 필요한 이유**
    - 애플리케이션 분리 및 통합
    - 다양한 클라이언트의 등장
    - 서버 프로그램은 다양한 브라우저와 안드로이폰, 아이폰과 같은 모바일 디바이스에서도 통신을 할 수 있어야 한다.
    - 이러한 멀티 플랫폼에 대한 지원을 위해 서비스 자원에 대한 아키텍처를 세우고 이용하는 방법을 모색한 결과, REST에 관심을 가지게 되었다.

---
추가 설명

- REST(Representational State Transfer)아키텍처를 따르는 API(Application Programming Interface)를 말한다.
    - REST는 자원 기반의 구조(ROA, Resource Oriented Architecture) 설계의 중심에 Resource가 있고
    - HTTP Method 를 통해 Resource를 처리하도록 설계된 아키텍쳐를 의미한다.
- API 를 Restful 하게 정의한다.
    - 여기서, Restful한 방식은 URL은 자원, HTTP Method 는 행위 라고하는 역할을 구분해서 설계하는 것이다.
- HTTP URL(Uniform Resources Identifiler)를 통해 자원(Resource)을 명시하고,

  (웹 사이트의 이미지, 텍스트, DB 내용 등 모든 자원(Resource)에 고유한 ID인 HTTP URL를 부여 한다.)

  HTTP Method(POST, GET, PUT, DELETE)를 통해 해당 자원에 대한 CRUD Operation을 적용하는 것을 의미한다.

    - CRUD Operation
        - Create : 생성(POST)
        - Read : 조회 (GET)
        - Update : 수정(PUT)
        - Delete : 삭제( DELETE)
        - HEAD: header 정보 조회(HEAD)
- REST란?
    - Representational State Transfer(REST)는 API작동방식에 대한 조건을 부과하는 소프트웨어 아키텍처.
    - 처음에 인터넷과 같은 복잡한 네트워크에서 통신을 관리하기 위한 지침으로 만들어졌다.
    - 쉽게 구현하고 수정할 수 있어 모든 API 시스템을 파악하고 여러 플랫폼에서 사용할 수 있다.
    - API 개발자는 여러 아키텍처를 사용하여 API를 설계할 수 있는데, REST 아키텍처 스타일을 따르는 API를 REST API라고 한다.
- API란?
    - API(Application Programming Interface)는 다른 소프트웨어 시스템과 통신하기 위해 따라야 하는 규칙을 정의합니다.
    - API : Application을 Programming 하는데 제공하거나 제공받는 모든 interface 들

      현업에서는 보통 http API를 칭한다.

        - 개발자는 다른 애플리케이션이 프로그래밍 방식으로 애플리케이션과 통신할 수 있도록 API 를 표시하거나 생성합니다.
          웹 API는 클라이언트와 웹 리소스 사이의 게이트웨이라고 생각할 수 있다.
            - 클라이언트 : 웹에서 정보에 엑세스 하려는 사용자.
            - 리소스 : 다양한 애플리케이션이 클라이언트에게 제공하는 정보. 이미지, 동영상, 텍스트, 숫자 또는 모든 유형의 데이터 일 수 있다. 클라이언트에 리소스를 제공하는 시스템을 서버라고도 합니다.
- **비유 (설명)**
    - API 를 Restful 하게 정의한다.
    - URL 도 결국 식별가능한 자원을 의미하는 용어인데
      **’내가 제공하는 API가 자원에 대해 어떻게 표현할거냐’ 를 URL과 HTTP Method 를 사용해서 표현하는 것.**
    - 예를 들어, 사실 URL 이라고 하는거는 자기 맘대로 설정할 수 있는데,
      만약에 ‘내가 작성한 게시글 조회’ 라는 역할을 수행하는 API 를 호출한다고 했을 때,
      이렇게도  `GET /post/by/writing/me/{userId}` 작성할 수 있는데
      이건 URL이 자원에 명시한다기 보다 행위까지 표현하고 있는 것.
    - 이걸 Restful 로 풀어보면,
      `GET /users/{userId}/posts`
      여기서 URL 이 표현하는 건 **특정 자원**일 뿐이고, **행위는 HTTP Method가 표현하**고 있는데,
    - **이런식으로 URL은 자원, HTTP Method 는 행위 라고하는 역할을 구분해서 설계하는 것이 Restful한 방식이다**
- **REST 구성 요소**
    1. **자원(Resource) : URL**
        - 모든 자원에 고유한 URI(Uniform Resource Identifier)로 식별된다. 이 자원은 Server에 존재한다.
        - 자원을 구별하는 ID는 ‘/groups/:group_id’와 같은 HTTP URL 다.
        - Client URL을 이용해서 자원을 지정하고 해당 자원의 상태(정보)에 대한 조작을 Server에 요청한다.
        - 예를 들어, 웹 사이트에서 사용자를 관리하는 API의 자원은 "/users"와 같이 표현될 수 있다.
    2. **행위(actions. Verb) : HTTP Method**
        - HTTP 프로토콜의 Method를 사용한다.
        - **HTTP 프로토콜은 GET, POST, PUT, DELETE 와 같은 메서드를 제공한다.**
        - **HTTP 메서드(GET, POST, PUT, DELETE 등)**를 사용하여 자원에 대한 행위를 표현한다.
          예를 들어,
          GET 메서드는 자원의 조회,
          POST 메서드는 자원의 생성,
          PUT 메서드는 자원의 업데이트,
          DELETE 메서드는 자원의 삭제를 수행한다.
    3. **표현(Representation of Resource)**
        - Client가 자원의 상태(정보)에 대한 조작을 요청하면 Server는 이에 적절한 응답(Representation)을 보낸다.
        - 자원은 여러 가지 형태로 표현될 수 있다. 주로 JSON, XML, HTML 등의 데이터 형식으로 표현되며, 클라이언트가 원하는 표현 형식을 요청할 수 있다.
        - REST에서 하나의 자원은 JSON, XML, TEXT, RSS 등 여러 형태의 표현(Representation)으로 나타내어 질 수 있다.
       

- **REST 특징** 
    1. Server-Client(서버-클라이언트 구조)
        - 자원이 있는 쪽이 Server, 자원을 요청하는 쪽이 Client가 된다.
            - REST Server : API를 제공하고 비즈니스 로직 처리 및 저장을 책임진다.
            - Client : 사용자 인증이나 context(세션, 로그인 정보) 등을 직접 관리하고 책임진다.
        - 서로 간 의존성이 줄어든다.
    2. Stateless(무상태)
        - RESTful API는 상태를 유지하지 않는다는 특징이 있다. 각 요청은 독립적으로 처리되며, 이전 요청에 대한 정보를 서버가 유지하지 않는다. 따라서, 클라이언트와 서버 간의 통신은 상태를 저장하지 않고 이루어진다.
        - HTTP프로토콜DMS Stateless Protocol이므로 REST 역시 무상태성을 갖는다.
        - Client의 context를 Server에 저장하지 않는다.
            - 즉, 세션과 쿠키와 같은 context 정보를 신경쓰지 않아도 되므로 구현이 단순해진다.
        - Server는 각각의 요청을 완전히 별개의 것으로 인식하고 처리한다.
            - 각 API 서버는 Client의 요청만을 단순 처리한다.
            - 즉, 이전 요청이 다음 요청의 처리에 연관되어서는 안된다.
            - 물론 이전 요청이 DB를 수정하여 DB에 의해 바뀌는 것은 허용한다.
            - Server의 처리 방식에 일관성을 부여하고 부담이 줄어들며, 서비스의 자유도가 높아진다.
    3. Cacheable(캐시 처리 가능)
        - 웹 표준 HTTP프로토콜을 그대로 사용하므로 웹에서 사용하는 기존의 인프라를 그대로 활용 할 수 있다.
            - 즉, HTTP가 가진 가장 강력한 특징 중 하나인 캐싱 기능을 적용할 수 있다.
            - HTTP 프로토콜 표준에서 사용하는 Last-Modified  태그나 E-Tag를 이용하면 캐싱 구현이 가능하다.
        - 대량의 요청을 효율적으로 처리하기 위해 캐시가 요구된다.
        - 캐시 사용을 통해 응답시간이 빨라지고 REST Server 트랜잭션이 발생하지 않기 때문에 전체 응답시간, 성능, 서버의 자원 이용률을 향상 시킬 수 있다.
    4. Layered System(계층화)
        - Client는 REST API Server만 호출한다.
        - REST Server는 다중 계층으로 구성될 수 있다.
            - API Server는 순수 비즈니스 로직을 수행하고 그 앞단에 보안, 로드밸런싱, 암호화, 사용자 인증 등을 추가하여 구조상의 유연성을 줄 수 있다.
            - 또한 로드밸런싱, 공유 캐시 등을 통해 확장성과 보안성을 향상시킬 수 있다.
    5. Code-On-demand(optional)
    6. Uniform Interface(인터페이스 일관성)
  

- **REST의 장점**
    - HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API사용을 위한 별도의 인프라를 구출할 필요가 없다.
    - HTTP 프로토콜의 표준을 최대한 활용하여 여러 추가적인 장점을 함께 가져갈 수 있게 해준다.
    - HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.
    - Hypermedia API 의 기본을 충실히 지키면서 범용성을 보장한다.
    - REST API 메시지가 의도하는 바를 명확하게 나타내므로 의도하는 바를 쉽게 파악할 수 있다.
    - 여러가지 서비스디자인에서 생길 수 있는 문제를 최소화 한다.
    - 서버와 클라이언트의 역할을 명확하게 분리한다.
  

- **REST의 단점**
    - 표준이 존재하지 않는다.
    - 사용할 수 있는 메서드가 4가지 밖에 없다.
        - HTTP Method 형태가 제한적이다.
    - 브라우저를 통해 테스트할 일이 많은 서비스라면 쉽게 고칠 수 있는 URL보다 Header 값이 왠지 더 어렵게 느껴진다.
    - 구형 브라우저가 아직 제대로 지원해주지 못하는 부분이 존재한다.
        - PUT, DELETE를 사용하지 못하는 점.
        - pushState를 지원하지 않는 점.
      

- **REST가 필요한 이유**
    - 애플리케이션 분리 및 통합
    - 다양한 클라이언트의 등장
    - 서버 프로그램은 다양한 브라우저와 안드로이폰, 아이폰과 같은 모바일 디바이스에서도 통신을 할 수 있어야 한다.
    - 이러한 멀티 플랫폼에 대한 지원을 위해 서비스 자원에 대한 아키텍처를 세우고 이용하는 방법을 모색한 결과, REST에 관심을 가지게 되었다.


- **RESTful API를 사용 시 이점?**
    1. 확정성
        - REST API 를 구현하는 시스템은 REST가 클라이언트 - 서버 상호작용을 최적화 하기 때문에 효율적으로 크기 조정할 수 있다 무상태는 서버가 과거 클라이언트 요청 정보를 유지할 필요가 없기 때문에 서버 로드를 제거한다.
    2. 유연성
        - RESTful 웹 서비스는 완전한 클라이언트-서버 분리를 지원한다.
        - 각 부분이 독립적으로 발전할 수  있도록 다양한 서.버 구성요소를 단순화하고 분리한다.
    3. 독립성
        - REST API는 사용되는 기술과 독립적이다.
        - API설게에 영항을 주지 않고 다양한 프로그램 언어로 클라이언트 및 서버 애플리케이션을 몯 작성할 수 있다 .
        - 또한 통신에 영향을 주지 않고 양쪽의 기본 기술을 변경할 수 있다.