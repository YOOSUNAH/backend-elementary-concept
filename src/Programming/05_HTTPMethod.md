
# Programming

---
### HTTP Method

**HTTP Method**

- HTTP 메서드는 HTTP 동사라고도 불리며, HTTP 요청이 서버에서 기대하는 작업을 나타냅니다. 특정 자원(Resource)에 대한 행위를 정의하는 역할이다.
- HTTP Method 는 일종의 약속이다. 메서드 그 자체가 기능을 제공하는 것이 아니며, 메서드 이름에 알맞는 내용으로 서버에서 코드를 구현해야 한다.

**주요 메서드**

- **GET :리소스 조회_서버로부터 데이터를 취득**
    - 서버에게 resource를 보내달라고 요청한다.
    - 서버(혹은 DB)의 resource는 클라이언트로 전달만 될 뿐 변경되지 않는다.
- **POST: 요청 데이터 처리, 주로 등록에 사용_서버에 데이터를 추가, 작성 등**
    - 서버에게 resource를 보내면서 생성해 달라고 요청한다.
- **PUT :  리소스를 대체 (덮어쓰기), 해당 리소스가 없으면 생성_서버의 데이터를 갱신, 작성 등**
    - PUT 메서드는 리소스 전체를 대체한다. 기존 리소스가 없을 경우 새로 생성한다.
      즉, 덮어쓰기를 수행한다고 볼 수 있다. ex) 회원정보 수정
    - 주의할 점은 리소스를 완전히 대체한다는 것이다. 부분적인 수정이 불가능하다.
    - POST와 차이점은 클라이언트가 리소스의 위치를 알고 URI를 명시해야 한다는 점이다.
- **PATCH : 리소스 부분 변경 (PUT이 전체 변경,  PATCH는 일부 변경)_ 리소스의 일부분을 수정**
    - PATCH 메서드는 리소스를 부분 변경한다.
        - 부분 변경이 필요한 상황에서 PATCH를 사용할 수 없다면 POST를 사용한다.
    - PATCH는 (PUT과 비교해서) 부분 데이터를 업데이트하는 차이점이 있다.
- **DELETE :리소스 삭제. 서버의 데이터를 삭제**
    - 서버에게 resource의 삭제를 요청합니다.

---
추가 설명
**HTTP Method**

- HTTP 메서드는 HTTP 동사라고도 불리며, HTTP 요청이 서버에서 기대하는 작업을 나타낸다.
- 특정 자원에 대한 행위를 정의하는 역할.
- HTTP Method 는 일종의 약속이다. 메서드 그 자체가 기능을 제공하는 것이 아니며, 메서드 이름에 알맞는 내용으로 서버에서 코드를 구현해야 한다.

**주요 메서드**

(자원)resource는 웝페이지(html), binary data(그림파일, 소리파일 등), db data(json/xml/혹은 html로 render된 data)를 뜻 한다.

- **GET**
  **리소스 조회_서버로부터 데이터를 취득**
  - 서버에게 resource를 보내달라고 요청한다.
    서버(혹은 DB)의 resource는 클라이언트로 전달만 될 뿐 변경되지 않는다.
  - GET 메서드는 리소스의 조회를 위해 사용한다.
  - 서버에 전달하고 싶은 데이터가 있다면 query(쿼리 파라미터, 쿼리 스트링)에 담아 보낸다.
  - 서버는 타겟 리소스에 해당하는 representation data를 응답 데이터로 보낸다.
  

- **POST**
  **요청 데이터 처리, 주로 등록에 사용_서버에 데이터를 추가, 작성 등**
  - 서버에게 resource를 보내면서 생성해 달라고 요청한다.
    예를 들어, 회원가입을 하면 DB에 새로운 회원정보가 등록되고, 사진을 업로드 하면 그 사진이 웹사이트에 등록된다.
  - **POST 메서드는 아래와 같은 작업을 요청할 때 사용된다.**
    1. HTML 양식으로 입력된 데이터 블록을 리소스 로직에 제공한다.
       예) HTML FORM에 입력한 정보로 회원 가입, 주문 등에서 사용
    2. 게시판, 뉴스 그룹, 메일링 리스트, 블로그 또는 유사한 기사 그룹에 메시지 게시
       예) 게시판 글쓰기, 댓글 달기
    3. 서버가 아직 식별하지 않은 새 리소스 생성
       예) 신규 주문 생성
    4. 기존 자원에 데이터 추가
       예) 한 문서 끝에 내용 추가하기
    5. 단순히 데이터를 생성하거나, 변경하는 것을 넘어서 프로세스를 처리해야 하는 경우
       예) 주문에서 결제완료 -> 배달시작 -> 배달완료 처럼 단순히 값 변경을 넘어 프로세스의 상태가 변경되는 경우. POST의 결과로 새로운 리소스가 생성되지 않을 수도 있다.
    6. 기타
       애매한 경우 POST를 사용한다.
       예) JSON으로 조회 데이터를 넘겨야 하는데, GET 메서드를 사용하기 어려운 경우. POST는 사실상 뭐든지 할 수 있다.


- **PUT**
  **리소스를 대체 (덮어쓰기), 해당 리소스가 없으면 생성_서버의 데이터를 갱신, 작성 등**
  - PUT 메서드는 리소스 전체를 대체한다. 기존 리소스가 없을 경우 새로 생성한다. 즉, 덮어쓰기를 수행한다고 볼 수 있다.
  - ex) 회원정보 수정 등에 사용된다.
  - 주의할 점은 리소스를 완전히 대체한다는 것이다. 부분적인 수정이 불가능하다.
  - POST와 차이점은 클라이언트가 리소스의 위치를 알고 URI를 명시해야 한다는 점이다.
    - 어떤 데이터를 대체할지를 알아야 요청을 보낼 수 있으므로 당연하다.
    - POST 메서드는 클라이언트가 등록될 리소스의 경로를 모른다.
    

- **PATCH**
  **리소스 부분 변경 (PUT이 전체 변경,  PATCH는 일부 변경)_ 리소스의 일부분을 수정,**
  - PATCH 메서드는 리소스를 부분 변경한다. 부분 변경이 필요한 상황에서 PATCH를 사용할 수 없다면 POST를 사용한다.
  - PATCH는 (PUT과 비교해서) 부분 데이터를 업데이트하는 차이점이 있다.
  - 서버에게 resource의 업데이트를 요청합니다. 회원정보 수정 등에 사용된다.
  
- **DELETE**
  **리소스 삭제. 서버의 데이터를 삭제**
  - 서버에게 resource의 삭제를 요청한다.
- **기타 메소드**
  - OPTIONS : 대상 리소스에 대한 통신 가능 옵션(메서드)
    - 예비 요청(Preflight)에 사용되는 HTTP메서드
    - 예비 요청이란 본 요청을 하기 전에 안전한지 미리 검사하는 것.
    - 서버의 지원 가능한 HTTP 메서드와 출처를 응답 받아 CORS 정책을 검사하기 위한 요청이다.
    - 서버에 실제 요청을 보내기 전에 서버를 테스트해보는 용도
    - 리소스가 지원하고 있는 메소드의 취득.
    - 목표 리소스와의 통신 옵션을 설명하기 위해 사용됨. (주로 CORS에서 사용)
    - 서버가 어떤 메서드를 지원하는지 알아볼 때 사용된다.
    - **OPTIONS https://myfit.xyz/modal/order HTTP/1.1** 요청을 보내면
    - GET, HEAD, POST가 온다.

  - HEAD : GET과 동일하지만 메시지 부분(body 부분)을 제외하고, 상태 줄과 헤더만 반환
    - 서버 리소스의 헤더(메타 데이터의 취득)
    - HEAD는 요청에서 헤더만 가져올 때 사용한다. 단, 헤더가 GET 요청의 헤더다.
  
  - CONNECT : 대상 자원으로 식별되는 서버에 대한 터널을 설정
    - 프록시 동작의 터널 접속을 변경, CONNECT는 양뱡향 통신을 할 때 쓰임.
    - 요청한 리소스에 대해 양방향 연결을 시작하는 메소드. 터널을 열기 위해 사용.

  - TRACE : 대상 리소스에 대한 경로를 따라 메시지 루프백 테스트를 수행
    - TRACE는 핑퐁 테스트같은 데 쓰이고,
    - 대상 리소스에 대한 경로를 따라 메시지 루프백 테스트를 수행.


- 참고 :: HTTP

  ***HTTP란? (Hyper Text Transfer Protocol)***
  - 인터넷에서 데이터를 주고받을 수 있는 프로토콜 (= 규칙)
  - HTTP는 월드 와이드 웹의 토대로 사용된다.
  - HTTP는 네트워크 장치 간에 정보를 전송하도록 설계된 애플리케이션 계층(by `OSI 7 계층`) 프로토콜이며, 네트워크 [프로토콜]스택의 다른 계층 위에서 실행된다.
  - **HTTP를 통한 일반적인 흐름**에는 클라이언트 시스템에서 **서버에 요청한 다음 서버에서 응답** 메시지를 보내는 작업이 포함된다.
  - HTTP 요청은 웹 브라우저와 같은 인터넷 통신 플랫폼에서 웹 사이트를 로드하는 데 필요한 정보를 요청하는 방법이다.
  - 일반적인 HTTP 요청의 구성요소
    - Request Line - Http Method(GET, POST, PUT, …), Endpoint (`/members/1/posts`)
    - Header - Content-Length, Content-Type, Accept, …
    - Body - 데이터
    