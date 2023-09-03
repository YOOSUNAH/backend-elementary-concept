# Java

---
### JVM, JRE, JDK 의 관계
* JDK는 JRE를 포함하고, JRE는 JVM을 포함하는 형태로 배포된다.
  * JDK(Java Development Kit)
  * 자바 개발 키트를 의미한다. , JVM용 소프트웨어 개발도구
  * JRE와 컴파일러(Compiler), 디버거(debugger) 또는 디버깅 툴, Jar도구, 프로파일러 등을 포함하는 프로그램이다.
* JRE(Java Runtime Environment)
  - 자바 실행 환경, JVM용 운영체제,  JVM이 동작하기 위한 환경을 만드는 것
  - Java Class Library, JVM, 그리고 Java Class Loader(로더)를 포함한다.
  - Class Loader와 Class Library를 통해 작성된 자바 코드를 Library와 결합 후에 JVM으로 넘겨서 실행을 시킨다.
  - JRE 그 자체로 기능이 있다기보다는 JVM이 동작하기 위한 환경을 만드는 것이다.
- JVM(Java Virual Machine)
  - 자바 프로그램을 컴파일 해서 나온 결과인 **바이트코드를 실행시켜주는 가상 머신**이다.
  - ***JVM 만 설치되어 있다면 어디서든 자바 코드를 돌릴 수 있다는 점***
    - application을 실행시켜주는 가상머신을 사용함으로써, 윈도우,리눅스,맥 등 다양한 환경에서 언제나 동일하게 실행되도록 할 수 있다는 장점을 가지고 있다.
  - 프로그래머는 운영체제에 관계없이 프로그램을 개발할 수 있어, 한번 컴파일됐으면 운영체제에 따라 다시 컴파일할 필요가 없는 WORA(Write Once Run Anywhere)를 만족한다.
  - 자바 프로그램의 메모리를 효율적으로 관리 & 최적화 해 준다.
          * WAS는 Response 객체에 담겨있는 내용으로 HTTP 응답 정보를 생성'


