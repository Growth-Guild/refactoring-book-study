## 필드 내리기 (Push Down Field)

### as-is
```java
class Employee {
    private String quota;
}

class Engineer extends Employee { /* ... */ }
class Salesperson extends Employee { /* ... */ }
```

### to-be
```java
class Employee { /* ... */ }

class Engineer extends Employee { /* ... */ }
class Salesperson extends Employee {
    protected String quota;
}
```

* 서브클래스 하나, 혹은 소수에서만 사용하는 필드는 해당 서브클래스들로 옮긴다.

- - -

### 절차
1. 대상 필드를 모든 서브클래스에 정의한다.
2. 슈퍼클래스에서 그 필드를 제거한다.
3. 테스트한다.
4. 이 필드를 사용하지 않는 모든 서브클래스에서 제거한다.
5. 테스트한다.