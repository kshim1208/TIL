### 배열

- 의미
    - 고정된 크기를 갖는 연관된 데이터들을 하나의 변수에 연속적으로 (물리적으로도) 묶어서 관리하는 방법
    - 하나의 변수에 여러 데이터 저장 가능
    - compile 타임에 정적으로 메모리에 할당됨
- 단점
    - 각 인덱스마다 데이터가 할당되어있기에 한 인덱스의 값을 제거해도 빈 인덱스가 남아 메모리를 점유함.
    - 처음 배열의 크기를 모두 채우지 않더라도 배열의 실제 크기는 처음 지정한 크기와 동일함 (실제 데이터와의 괴리 발생 가능)
    - 배열이 늘어나거나 줄어들면 새로 배열을 할당해야 함. 또한 데이터를 삽입하거나 삭제하려면 교환하는 연산이 따로 필요함.
        - 10 20 30 40 50 60 70 80 90 이라는 데이터를 저장하고 있는 크기 9 배열에  25를 추가할 경우, 크기 10 배열을 새로 할당한 뒤 기존 데이터 중 일부는 복사하고, 25를 추가한 뒤, 나머지 값은 인덱스를 밀어내며 저장해야 함.

</br>

-----

</br>

### 리스트

- 의미
    - ‘순서가 있는 데이터의 모임’
    - 원소를 삭제해도 삭제된 데이터 뒤에 원소가 빈틈없이 적재된다. (배열과 달리 리스트를 끊고 이을 수 있음)
    - run 타임에 리스트에 노드를 추가할 때 동적으로 할당됨.
- 단점
    - spatial locality (공간적 지역성) 보장하지 않는다. 
    → 일반적으로 프로그램은 순차적으로 실행될 것이라 CPU의 Cache가 예측하는데, 리스트의 경우 저장된 데이터 (노드)의 주소가 항상 연속적이라는 보장이 없다. 따라서 Cache Hit 발생률이 감소하여 배열에 비해 상대적으로 속도가 떨어질 수 있다.
        
        (CPU의 속도가 빨라져서 RAM과의 괴리가 발생(병목 현상). 이를 보충하기 위해 Cache가 생겨남. Cache가 예측을 위한 데이터를 보관하는 기준이 2가지 있음. Temporal Locality, Spatial Locality임.
        Temporal Locality → 최근에 사용된 명령이나 데이터가 다시 사용될 가능성이 높다. ((Loop문 등))) 
        
    - list를 지원하지 않는 언어가 있을 수도 있다. (c의 경우 구현 필요)
- 특이 사항
    - 구현 방법에 따라 Array List, Linked List로 구분할 수 있다.
        - Array List - 배열을 이용해 리스트를 구현한 것. 접근은 빠르지만 데이터를 추가하거나 삭제하기 힘듬.
        - Linked List - 연결로 리스트를 구현한 것. 한 원소에서 원소의 값과 다음 원소의 주소를 저장하는 방식. 삽입 및 삭제는 쉽지만 해당 지점에 접근하는 비용이 필요.
    - **논리적 저장 순서 과 물리적 저장 순서 불일치
      
</br>      
      
------

</br>

### 스택

- 의미
    - 한 쪽 끝에서만 자료를 넣고 뺄 수 있는 구조. 후입선출. LIFO (Last In First Out).
    - 따라서 가장 최근에 스택에 추가한 항목에만 접근할 수 있다.
        - 기능 - pop (스택 가장 위 제거), push (스택 가장 위에 추가), peek (스택 가장 위 반환) ,isEmpty (스택이 비어있다면 true)
- 배열과 스택의 비교
    - 배열과 달리 스택은 i번째 항목에 도달하는게 걸리는 시간이 길다.
    - 스택에 데이터를 추가하거나 삭제하는 연산은 빠르다.
    - 배열과 달리 데이터가 추가되었을 때 원소를 이동시킬 필요가 없다.
- 사용 사례
    - 재귀 알고리즘 - 임시 데이터를 스택에 넣고, backtrack할 경우 스택에 넣어둔 임시 데이터를 사용
    - 웹 브라우저 방문기록 (뒤로)
    - 실행 취소
    - 역순 문자열
    - 괄호 검사

</br>

------

</br>

### 큐

- 의미
    - 먼저 입력된 자료를 먼저 뺄 수 있는 구조. 선입선출. FIFO (First In First Out).
    - 따라서 데이터의 저장과 삭제가 다른 곳에서 이루어진다.
        - 기능 - Enqueue (가장 뒤에 데이터 추가), Dequeue (가장 앞 데이터에 접근), peek (가장 앞 데이터 반환)
- 선형 배열, 연결 리스트, 원형 큐를 이용한 큐의 구현

</br>

-------

</br>

### 덱
