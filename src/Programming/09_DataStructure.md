# Programming

---
### 자료구조란 무엇인가? (Data Structure)

***자료구조(Data Structure)***

- 프로그램에서 사용할 많은 데이터를 메모리 상에서 관리하는 여러 구현방법들
- 효율적인 자료구조가 성능 좋은 알고리즘의 기반이 됨

- *Array (*배열)**
    - 선형으로 자료를 관리, **정해진 크기**의 메모리를 먼저 할당받아 사용한다.
    - 자료의 물리적 위치와 논리적 위치가 같음
        - 선형 자료구조 :한 줄로 자료를 관리하기
    - 같은 자료 형의 값 여러개를 저장하는 연속된 공간 (= **동일한 데이터 타입**을 **순서**에 따라 관리하는 자료 구조)
    - 각 값에 대해 별도의 변수를 선언하는 대신 **여러 값을** **하나의 변수**에 저장하는 데 사용된다.

> **ArrayList**
> - 단방향 포인터 구조로 각 데이터에 대한 인덱스를 가지고 있어 조회 기능에 성능이 뛰어남
> - 배열과 달리 초기크기를 지정하지 않아도 되므로, 삽입 삭제가 자유로움

- ***Linked List (연결 리스트)***
    - 선형으로 자료를 관리, 자료가 추가될 때마다 메모리를 할당 받고, 자료는 링크로 연결됨.
    - 자료의 물리적 위치와 논리적 위치가 다를 수 있음
    - List는 중복데이터를 허용한다.
    - LinkedList는 List 구현 클래스이므로, ArrayList와 사용하는 메소드는 같지만 내부 구조는 완전 다르다.
        - ArrayList는 내부 배열 객체를 저장해서 인덱스로 관리하지만,
        - LinkedList는 양방향 포인터 구조로, 각각마다 인접하는 참조를 링크해서 체인처럼 관리한다.
        - 
- ***Stack (스택) (LIFO방식)***
    - 한쪽 끝에서만 Data의 입출력이 가능한 대표적인 자료구조이다.
    - 제한적으로 접근할 수 있는 나열 구조.
    - 가장 나중에 입력 된 자료가 가장 먼저 출력되는 자료 구조 **(Last In First OUt)**
    - 특성) 재귀적 함수를 호출할 때 사용된다.
    - Java에서는 Stack을 편하게 사용할 수 있도록`java.util.Stack`으로 라이브러리를 제공해 준다. `Stack<Integer> stack = new Stack<>();`
        - java의 Stack 라이브러리에서는 크게`삽입`,`삭제`,`조회`,`검색`을 지원해준다.

- **Queue 큐 (FIFO방식)** 
- Collection framework의 일부이며, java.uil 패키지에 소속되어 있다.
- 가장 먼저 입력 된 자료가 가장 먼저 출력되는 자료 구조 **(First In First Out)**
    - Queue는 ‘줄을 서다’는 사전적 의미로, 줄을 서서 기다린다는 것처럼 먼저 들어오면 데이터가 먼저 나가는 형식이다.  (줄을 지어 순서대로 처리되는 자료 구조)
    - Queue의 앞부분 front는 삭제 연산만 수행
    - Queue의 뒷부분 rear는 삽입연산만 수행한다.

- ***Set  (세트)***
    - Colection class에서 자료구조 집합을 구현한 것이다.
    - 순서를 저장하지 않고, 중복되지 않는 값들을 저장하는 인터페이스
        - 같은 데이터의 중복 저장을 허용하지 않는다. 따라서 null도 하나의 null만 저장할 수 있다.
        - (순서 보장 X) 데이터의 저장 순서를 유지하지 않는다.
    - 집합이란 의미 (수학에서 유한집합을 컴퓨터로 구현한 것)
    - Set 컬렉션은 List 컬렉션처럼 인덱스로 객체를 검색해서 가져오는 메소드가 없다.
        - 대신 전체 객체를 대상으로 한 번 씩 다 가져오는 반복자, Iterator을 제공한다.
    - Set 인터페이스를 구현한 주요 클래스는 3개
        1. HashSet
            - HashSet (사용법)
                - HashSet 형식
                    - `HashSet<String> set = new HashSet<>();`
                    - <> 안에 어떤 형의 데이터를 넣을지 정의
                - 데이터 추가
                    - `set.add("삼겹살");`
                - 데이터 크기 조회
                    - `set.size();`  중복된 값은 제외됨.
                - 데이터 순회하면서 조회. (순서 보장하지 않음)
                    - 순서 보장을 원하면 HashSet 이 아닌 LinkedHashSet을 쓰면 됨
                    - `HashSet<Integer> intSet2 = new LinkedHashSet<>();`

                    ```java
                    for (String s : set) { 
                       System.*out*.println(s);}
                    ```

                - 포함 여부 확인
                    - `set.contains("삼겹살")` ()안에 확인하고 싶은 데이터를 넣으면 됨.
                - 데이터 삭제
                    - `set.remove("삼겹살");`
                    - 전체 삭제 : `set.clear();`
                - 비어있는지 확인
                    - `set.isEmpty()`
        2. TreeSet
        3. LinkedHashSet `HashSet<Integer> intSet2 = new LinkedHashSet<>();`
           >Class	|특징 </br>
           -HashSet	</br>
           순서가 필요없는 데이터를 hash table에 저장.</br>
           Set 중에 가장 성능이 좋음.</br>
           순서를 예측할 수 없음. (순서 보장 X)</br>
           -TreeSet	</br>
           저장된 데이터의 값에 따라 정렬됨. red-black tree 타입으로 값이 저장됨.</br>
           HashSet보다 성능이 느림.</br>
           정렬방법을 지정할 수 있음.</br>
           -LinkedHashSet	</br>
            연결된 목록 타입으로 구현된 hashtable에 데이터 저장.</br>
            저장된 순서에 따라 값이 정렬되나 셋 중 가장 느림</br>
           (순서 보장을 원하면 HashSet 이 아닌 LinkedHashSet을 쓰면 됨)
           >

- ***Hash Table***
    - **(Key, Value)로 데이터를 저장하는 자료구조 중 하나로, 빠르게 데이터를 검색할 수 있는 자료구조.**
    - 키와 값을 1:1형태로 가져가며 HashTable에 저장이 된다.
        - 키는 값을 식별하기 위한 고유한 키, 값은 키가 가진 값을 의미
    - **HashMap과 반대로 동기화가 이루어진다.**
    - HashMap에서는 값으로 null이 입력이 가능하지만, **HashTable에서는 null 입력이 불가능하다.**
        - 해시 테이블이 빠른 검색속도를 제공하는 이유는 내부적으로 배열(버킷)을 사용하여 데이터를 저장하기 때문이다.
        - 해시 테이블은 각각의 Key값에 해시함수를 적용해 배열의 고유한 index를 생성하고, 이 index를 활용해 값을 저장하거나 검색하게 된다

      > 해시 알고리즘 : hash algorithm </br>
      해시 알고리즘이란 해시 함수(hash function)를 사용하여 데이터를 해시 테이블에 저장하고, 다시 그것을 검색하는 알고리즘이다.

- ***Tree***
    - **계층적인 구조를 표현하기 위해 일상적으로 사용하는 구조**
    - 비선형 자료구조 중 하나다.
        - 비선형이라는 것은 말 그대로 일직선으로 나타내지 못하는 방식이며,
        - 그중 트리는 계층적 구조를 띄고 있다.
        - 계층적 구조는 일반적으로 조직도를 나타내는 경우에 자주 사용된다.
    - 부모 노드와 자식 노드간의 연결로 이루어진 자료 구조