   # Java

---
### 접근 제한자(Access Modifier)
- 접근 제한자는 class , interface 그리고 이들이 가지고 있는 멤버(클래스의 변수나 메서드)의 접근을 제한하기 위해 사용 되는 것.
- public, protected, private , default 가 있다.
- 
- 접근을 제한하기 위해 사용된다.
    - 접근 : 클래스 및 인터페이스 그리고 이들이 가지고 있는 멤버의 접근
    - 접근이 가능하다는건 조회랑 변경이 가능하다는 것
- 접근 제한자 종류
    1. **public 접근제한자**
        - 모든 클래스에서 접근 가능.어디서나 (어디서든 접근 가능), 외부 클래스가 자유롭게 사용할 수 있다.
    2. **protected  접근 제한자**
        - 상속받은 내에서만 (해당 패키지 및 상속받은 클래스에서 접근)
        - 같은 패키지 또는 자식 클래스에서 접근 가능
    3. **private 접근 제한자**
        - 자기 class 내에서만 (해당 클래스에서만 접근 가능)
        - 외부에서 사용될 수 없도록 한다.

  위 3가지 접근 제한자가 적용되지 않으면, default 접근 제한을 가짐.

    1. **default 접근 제한**
        - 같은 패키지에 소속된 클래스에서만 사용할 수 있다.
        - (아무것도 적지 않았을 때) 같은 패키지 내에서만 접근 가능
            - 패키지 : 여러 클래스들이 모여있는

---
추가 설명
- 접근을 제한하기 위해 사용된다.
    - 접근 : 클래스 및 인터페이스 그리고 이들이 가지고 있는 멤버의 접근
    - 접근이 가능하다는건 조회랑 변경이 가능하다는 것
- 접근 제한자 종류
    1. **public 접근제한자**
        - 모든 클래스에서 접근 가능.어디서나 (어디서든 접근 가능), 외부 클래스가 자유롭게 사용할 수 있다.
    2. **protected  접근 제한자**
        - 상속받은 내에서만 (해당 패키지 및 상속받은 클래스에서 접근)
        - 같은 패키지 또는 자식 클래스에서 접근 가능
    3. **private 접근 제한자**
        - 자기 class 내에서만 (해당 클래스에서만 접근 가능)
        - 외부에서 사용될 수 없도록 한다.

  위 3가지 접근 제한자가 적용되지 않으면, default 접근 제한을 가짐.

    1. **default 접근 제한**
        - 같은 패키지에 소속된 클래스에서만 사용할 수 있다.
        - (아무것도 적지 않았을 때) 같은 패키지 내에서만 접근 가능
            - 패키지 : 여러 클래스들이 모여있는