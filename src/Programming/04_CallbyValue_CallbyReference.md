# Programming

---
### Call by Value, Call by Reference

**메서드를 호출할 때 파라미터를 전달하는 방법**에는 두가지가 있다 .

함수에 정의한 **매개변수의 형태**에 따라 **Call by value** 혹은 **Call by reference**인지 결정된다.

**Call by Value (값에 의한 호출)**

- 메서드를 호출할 때 **값**을 넘겨주기 때문에 Pass by Value라고도 부른다.
- 메서드를 호출하는 호출자( Caller)의 변수와 호출 당하는 수신자(Calee)의 파라미터는 **복사된 서로 다른 변수다.**
  값만을 전달하기 때문에 수신자의 파리미터를 수정해도 호출자의 변수에는 **아무런 영향이 없다**

**Call by Reference (참조에 의한 호출)**

- **참조(주소)**를 직접 전달하며 Pass by Reference라고도 부른다.
- 참조를 직접 넘기기 때문에 호출자의 변수와 수신자의 파라미터는 **완전한 동일한 변수**다.

***Java에서의 파라미터 전달 방법***

- Java는 포인터가 따로 없어 기본적인 매개변수는  Call by Value지만,
  예외적으로 배열과 클래스는 참조변수로 Call by Reference로 작동한다.