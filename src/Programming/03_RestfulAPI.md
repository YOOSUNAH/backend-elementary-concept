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