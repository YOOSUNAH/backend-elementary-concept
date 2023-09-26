   # Java

---
### ***Inner Class(내부 클래스)***

- 하나의 클래스 내부에 선언된 또 다른 클래스를 의미한다.
- 내부 클래스의 종류
  - 정적 클래스 (static class),인스턴스 클래스(instance class) ,지역 클래스(local class) , 익명 클래스(anonymous class)

***Inner Class(내부 클래스)의 장점***

1. **클래스를 논리적으로 그룹화한다.** 
2. **더 많은 캡슐화의 적용이 가능하다.**
  - 캡슐화를 통해 외부에서의 접근을 차단하면서도, 내부 클래스에서 외부 클래스의 멤버들을 제약 없이 쉽게 접근할 수 있어 구조적인 프로그래밍이 가능해진다.
  - 캡슐화 :
    관련이 있는 변수와 함수를 하나의 클래스로 묶고 외부에서 쉽게 접근하지 못하도록 은닉하는게 핵심이다.
    객체에 직접적인 접근을 막고 외부에서 내부의 정보에 직접 접근하거나 변경할 수 없고, 객체가 제공하는 필드와 메서드를 통해서만 접근이 가능합니다.

3. **가독성이 좋고 유지 관리가 쉬운 코드 작성이 가능하다.**
  - 내부클래스를 작성하는 경우, 물리적으로 외부 클래스에 더 가깝게 위치하게 된다. 유지보수에 이점을 가지게 된다.


---
- 캡슐화의 예시
```java
 class OuterClass {
  private int outerData;

  // Inner Class
  class InnerClass {
  private int innerData;

        public InnerClass(int innerData) {
            this.innerData = innerData;
        }

        public void displayInnerData() {
            System.out.println("Inner Data: " + innerData);
        }
  }

  public OuterClass(int outerData) {
  this.outerData = outerData;
  }

  public void displayOuterData() {
  System.out.println("Outer Data: " + outerData);
  }

  public InnerClass createInnerClass(int innerData) {
  return new InnerClass(innerData);
  }
  }

public class Main {
public static void main(String[] args) {
// 생성자를 통한 OuterClass 인스턴스 생성
OuterClass outer = new OuterClass(10);

        // OuterClass의 메서드 호출
        outer.displayOuterData();

        // InnerClass 인스턴스 생성
        OuterClass.InnerClass inner = outer.createInnerClass(5);

        // InnerClass의 메서드 호출
        inner.displayInnerData();
    }
}
```
위의 코드에서 OuterClass는 외부 클래스로, InnerClass는 내부 클래스로 정의되어 있다. 
OuterClass는 outerData라는 private 멤버 변수를 가지고 있고, InnerClass는 innerData라는 private 멤버 변수를 가지고 있다.
InnerClass는 OuterClass의 private 멤버 변수에도 접근할 수 있으며, createInnerClass 메서드를 통해 InnerClass의 인스턴스를 생성할 수 있다. 
이를 통해 캡슐화가 달성되고 데이터 은닉이 이루어진.