**웹 브라우저에서 [www.google.com](http://www.google.com) 입력 시,**

1. **사용자가 웹브라우저 검색창에 [www.google.com](http://www.google.com) 입력**
2. **웹브라우저는 캐싱된 DNS 기록들을 통해 해당 도메인 주소와 대응하는 IP주소를 확인**

   이 단계에서 캐싱된 기록이 없을 경우, 다음 단계로 넘어간다.
   > DNS (Domain Name System Servers) 도메인 이름 시스템 서버 <br/>
   > : URL들의 이름과 IP 주소를 저장하고 있는데이터베이스로, 웹사이트를 위한 주소록

3. **웹브라우저가 HTTP를 사용하여 DNS에게 입력된 도메인 주소를 요청**
   > HTTP (Hypertext Transfer Prococol) <br/>
   > : 클라이언트와 서버가 서로 통신할 수 있게 하기 위한 언어를 정의하는 어플리케이션 규약

4. **DNS가 웹브라우저에게 찾는 사이트의 IP주소를 응답.**
   ISP(Internet Service Provider)의 DNS서버가 호스팅하고 있는 서버의 IP주소를 찾기 위해 DNS query를 날린다.
    - DNS query의 목적 : DNS 서버들을 검색해서 해당 사이트의 IP주소를 찾는데에 있다.
      현재 DNS 서버에 원하는 IP 주소가 존재하지 않으면, 다른 DNS 서버를 방문하는 과정을 원하는 IP주소를 찾을 때까지 반복한다.
      IP주소를 찾을 때까지 DNS서버에서 다른 DNS서버를 오가며 에러가 날때까지?? 반복적으로 검색한다. = `recursive search`

    
        'www.google.com' 주소에 대해 검색할 때,
        1. DNS recursor가 root name server에 연락
        2. .com 도메인 name server로 리다이렉트
        3. google.com name server로 리다이렉트
        4. 최종적으로 DNS기록에서 'www.google.com' 에 매칭되는 IP주소 찾기
        5. 찾은 주소를 DNS recursor로 보내기
        ```

5. **웹 브라우저가 웹 서버에게 IP 주소를 이용하여 html 문서를 요청**

   TCP로 연결이 되면, 브라우저는 GET요청을 통해 서버에게 www.google.com의 웹페이지를 요구한다.
   HTTP 요청 메세지는 TCP/IP 프로토콜을 사용하여 서버로 전송된다.

   > TCP/IP (Transmission Control Protocol/ Internet Protocol) 전송제어규약,인터넷규약 <br/>
   > : 데이터가 어떻게 웹을 건너 여행하는지 정의하는 통신 규약. <br/>
   > 송신자가 수신자에게 IP주소를 사용해서 데이터를 전달하고 그 데이터가 제대로 갔는지에 대해 이야기 하는 것. <br/>
   > TCP는 전송제어프로토콜로, 데이터의 전송을 제어하고, 데이터를 어떻게 보낼 지 어떻게 맞출지 정한다.

6. **웹어플리케이션서버(WAS)와 데이터베이스(DB)에서 우선 웹페이지 작업을 처리**

   웹 서버 혼자서 모든 로직을 수행하고 데이터를 관리할 수 있다면 간단하겠지만, 그렇게 될 경우 서버에 과부하가 일어날 수 있다. 그렇기 때문에 서버의 일을 돕는 조력자 역할을 하는 것이 WAS(Web  Applicaion Server)이다.
    
   > WAS
   : 사용자의 컴퓨터나 장치에 웹어플리케이션을 수행해주는 미들웨어 <br/>
   > 웹서버와 웹어플리케이션서버(WAS)의 차이점 <br/>
   > - 웹서버 : 정적인 컨텐츠(HTML, CSS, IMAGE 등)를 요청받아 처리 <br/>
   > - WAS : 동적인 컨텐츠(JSP, ASP, PHP 등)를 요청받아 처리 <br/>
   >     => DB서버에 대한 접속 정보가 있기 때문에 외부에 노출 될 경우 보안상의 문제를 이유로 웹서버와의 연결을 통해 요청을 전달받음
   
7. **위의 작업처리 결과를 웹 서버로 전송**

8. **웹서버는 웹브라우저에게 html 문서결과를 응답.**
   `response`는 `status code`(상태 코드)로 서버 요청에 따른 결과 및 상태를 보낸다.
   > 1xx  : 정보만 담긴 메세지  <br/>
   > 2xx : response 성공 <br/>
   > 3xx : 클라이언트를 다른 URL로 리다이렉트 <br/>
   > 4xx : 클라이언트 측에서 에러 발생 <br/>
   > 5xx : 서버 측에서 에러 발생

9. **웹브라우저는 화면에 웹페이지 내용물 출력**