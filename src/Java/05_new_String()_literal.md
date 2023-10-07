# Java

---
### new String()과 리터럴("")의 차이
*  실제 메모리에 할당되는 영역에 차이가 있다.

- **new 연산자**를 통해 문자열 객체를 생성하는 경우, 메모리의 **Heap 영역**에 할당되고,

  다른 객체들처럼 Heap 메모리에 새로운 주소를 할당 받아, 모든 String 변수의 주소가 다르게 저장된다.

- **리터럴 방식으**로 생성할 경우에는, **String Constant Pool이라는 상수풀 영역**에 할당된다.

  만약, 이미 같은 값을 가지고 있는 리터럴이 ConstantPool에 존재할 때,

  새로운 객체를 생성하지 않고, 기존에 존재하는 리터럴을 사용한다.


---
추가 설명
`new String()` new 연산자 방식

- `String객체(new String())`
- 다른 객체들처럼 **Heap 메모리**에 새로운 주소를 할당 받는다.
- **따라서 모든 String 변수의 주소가 다르게 저장된다.**

    ```java
    String a = "ABC";
    String b = new String("ABC");
    String c = new String("ABC");
    System.out.println(a == b || a == c);
    => false // a와 b, c가 각각 다른 주소에 저장되었다.
    ```

  예시) `String str = new String(”hello”);`

  - **new는 클래스를 메모리에 올려주세요** 라는 뜻, 이렇게 메모리에 올라간 클래스를 인스턴스라고한다.
    이 **메모리에 올라간 클래스를 가리키는 변수가 str**이다.  
    **변수가** 인스턴스를 가지고 있는 것이 아니라 **참조, 가리키고 있다!**
    str이라는 변수에는 “**메모리에 위치값**”이 저장되어 있다.
  - **new 연산자로 인스턴스를 만들면, 무조건 새롭게 만들어진다.**
  - **str3과 str4는 서로 다른 인스턴스를 참조한다.**
  - 즉, `str3 == str4` 의 결과는 false이다. **서로 다른 인스턴스를 참조**하기 때문이다.

    ```java
    String str3 = new String("hello");
    String str4 = new String("hello");
    ```
    
  ---

- String은 new연산자를 이용하지 않고도 인스턴스를 만들어 낼 수 있다!
  - 나머지 모든 클래스들은 new연산자를 이용해야지만 실제 인스턴스를 만들어낼 수 있다.
- 리터럴(`""`) 방식
- **문자열 리터럴은 Heap 내의 String Constant Pool이라는 영역에 할당된다.**
- 만약, 이미 같은 값을 가지고 있는 리터럴이 ConstantPool에 존재할 때,
  - **새로운 객체를 생성하지 않고, 기존에 존재하는 리터럴을 사용한다.**

    ```java
    String literal = “HelloWorld”;
    ```
 
    ```java
    String a = "ABC";
    String b = "ABC";
    System.out.println(a==b);
    => true // a와 b가 (String constant Pool내의) 같은 주소에 저장되었다.
    ```

- str1 과 str2는 같은 인스턴스를 참조하고(가리키고) 있다.
- `str1 == str2` 의 결과는 true이다. **같은 인스턴스를 참조**하기 때문이다.

   ```java
  String str1 = "hello"
  String str2 = "hello"
  ```