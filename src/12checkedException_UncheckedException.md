   # Java

---
### **Unchecked Exception와 CheckedException의 차이**

- Unchecked Exception은, 
- **컴파일 때 체크되지 않고, Runtime에 발생하는 Exception(예외)이며,** RuntimeException을 상속하는 클래스이다.

- CheckedException은 
- **컴파일 시점에 컴파일러에서 확인하는 Exception(예외)이며,** Exception 클래스를 상속하며, 컴파일러가 이 예외를 처리하도록 강제한다.
    - 반드시 에러처리를 해야하는 특징(try/ catch or throw)을 가지고 있다.