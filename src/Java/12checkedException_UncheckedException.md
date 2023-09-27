   # Java

---
## **Checked Exceptiond과 Unchecked Exception의 차이**

### - Checked Exception
- CheckedException은 **컴파일 시점에 컴파일러에서 확인하는 Exception(예외)이며,** Exception 클래스를 상속하며, 컴파일러가 이 예외를 처리하도록 강제한다.
- 반드시 에러처리를 해야하는 특징(try/ catch or throw)을 가지고 있다.

- **예시:**

  - **`IOException`**: 파일을 읽거나 쓸 때 발생할 수 있는 입출력 예외.
  - **`SQLException`**: 데이터베이스 관련 작업 시 발생할 수 있는 예외.

---

### - Unchecked Exception
- Unchecked Exception은, **컴파일 때 체크되지 않고, Runtime에 발생하는 Exception(예외)이며,** RuntimeException을 상속하는 클래스이다.

- **예시:**

  - **`NullPointerException`**: 객체 참조가 없는 상태에서 메소드를 호출할 때 발생하는 예외.
  - **`ArithmeticException`**: 산술 연산 중에 부적절한 산술 연산이 발생했을 때.