**웹 브라우저에서 http://www.google.com 입력 시,**

1. **사용자가 웹 브라우저 검색창에 http://www.google.com/ 입력**
2. **웹 브라우저는 캐싱된 DNS 기록들을 통해 해당 도메인 주소와 대응하는 IP 주소를 확인**

   사용자가 도메인 이름인 http://www.google.com/을 입력하면, 먼저 웹 브라우저는 로컬 DNS 캐시를 확인한다.

   캐시에 해당 도메인의 IP 주소가 없으면 운영체제의 DNS 캐시, 라우터의 DNS 캐시 등을 차례로 확인한다.
    
   > DNS (Domain Name System Servers) 도메인 이름 시스템 서버
   : URL들의 이름과 IP 주소를 저장하고 있는 데이터베이스로, 웹사이트를 위한 주소록
   
3. **웹 브라우저가 HTTP를 사용하여 DNS에게 입력된 도메인 주소를 요청**

   캐시에서 IP 주소를 찾을 수 없다면, 웹 브라우저는 해당 도메인 주소를 DNS 서버에 묻는다.

   DNS 서버는 Recursive DNS Query를 통해 최종적으로 IP 주소를 찾아낸다.
    
   > HTTP (Hypertext Transfer Protocol)
   : 클라이언트와 서버가 서로 통신할 수 있게 하기 위한 언어를 정의하는 애플리케이션 규약

4. **DNS가 웹 브라우저에게 찾는 사이트의 IP 주소를 응답**

   DNS 서버는 Recursive DNS Query를 통해 해당 도메인의 IP 주소를 찾기 위해 여러 DNS 서버를 순차적으로 조회한다. 이때, 최종적으로 찾은 IP 주소를 웹 브라우저에게 응답한다.
    
   > DNS query의 목적
   : DNS 서버들을 검색해서 해당 사이트의 IP 주소를 찾는데에 있다.
   현재 DNS 서버에 원하는 IP 주소가 존재하지 않으면, 다른 DNS 서버를 방문하는 과정을 원하는 IP 주소를 찾을 때까지 반복한다.
   IP 주소를 찾을 때까지 DNS 서버에서 다른 DNS 서버를 오가며 에러가 날 때까지 반복적으로 검색한다. (recursive search)
  
\

       'www.google.com' 주소에 대해 검색할 때, 
         DNS가 웹 브라우저에게 찾는 사이트의 IP 주소를 응답하는 과정

       1. DNS resolver 가 root name server에 연락
         웹 브라우저가 DNS에게 도메인 주소를 물어본다.
         이때 사용되는 DNS 서버를 DNS resolver라고 한다.
         (DNS resolver는 DNS 계층 구조에서 클라이언트의 DNS 쿼리를 처리하고 적절한 응답을 반환하는 시스템)
         DNS resolver가 먼저 전 세계의 DNS 계층 구조의 최상위인 Root Name Server에연락하여
         .com 도메인을 관리하는 네임 서버 정보를 요청한다.
       2..com 도메인 name server로 리다이렉트
         Root Name Server는 .com 도메인을 관리하는 Name Server의 주소를 알려준다.
         DNS resolver가 해당 Name Server에 연락한다.
       3. google.com name server로 리다이렉트
         .com 도메인 Name Server는 google.com 도메인을 관리하는 Name Server의 주소를 알려준다.
         DNS resolver가 해당 Name Server에 연락합니다.
       4. 최종적으로 DNS기록에서 'www.google.com' 에 매칭되는 IP주소 찾기
         google.com 도메인 Name Server는 요청받은 도메인에 대한 IP 주소를 알려준다.
      5. 찾은 주소를 DNS resolver로 보내기
         DNS resolver는 찾은 IP 주소를 가지고 이를 다시 웹 브라우저에게 응답하여,
         웹 브라우저가 해당 IP 주소로 웹 서버에 접속할 수 있게 한다.
    
5. **웹 브라우저가 웹 서버에게 IP 주소를 이용하여 HTML 문서를 요청**

    웹 브라우저(web client)는 찾은 IP 주소를 사용하여 web Server에 HTTP GET 요청을 보낸다. 
    
    HTTP 요청 메시지는 TCP/IP 프로토콜을 사용하여 서버로 전송된다.
    
    > TCP/IP (Transmission Control Protocol/Internet Protocol)
    : 데이터가 어떻게 웹을 건너 여행하는지 정의하는 통신 규약. 
    송신자가 수신자에게 IP 주소를 사용해서 데이터를 전달하고 그 데이터가 제대로 갔는지에 대해 이야기하는 것. 
    TCP는 전송 제어 프로토콜로, 데이터의 전송을 제어하고, 데이터를 어떻게 보낼 지 어떻게 맞출 지 정한다.
     

6. **웹 어플리케이션 서버(WAS)와 데이터베이스(DB)에서 웹 페이지 작업을 처리**

   웹 서버 혼자서 모든 로직을 수행하고 데이터를 관리할 수 있다면 간단하지만, 과부하가 발생할 수 있다. 따라서 웹 어플리케이션 서버(WAS)가 동적 컨텐츠를 처리하고 데이터베이스(DB)와 상호 작용하여 작업을 처리한다.
    
   > WAS (Web Application Server)
   : 사용자의 컴퓨터나 장치에 웹 어플리케이션을 수행해주는 미들웨어.
   DB 서버에 대한 접속 정보가 있기 때문에 외부에 노출될 경우 보안상의 문제를 이유로 웹 서버와의 연결을 통해 요청을 전달받는다.
   Web Server는 정적인 컨텐츠(HTML, CSS, 이미지 등)를 요청받아 처리하고,
   WAS는 동적인 컨텐츠(JSP, ASP, PHP 등)를 요청받아 처리한다.
   