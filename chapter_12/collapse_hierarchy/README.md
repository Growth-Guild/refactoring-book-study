## 계층 합치기 (Collapse Hierarchy)

### as-is
```javascript
class Employee { /* ... */ }
class Salesperson extends Employee { /* ... */ }
```

### to-be
```javascript
class Employee { /* ... */ }
```

* 계층 구조가 진화함에 따라 어떤 클래스와 그 부모가 너무 비슷해져서 더는 독립적으로 존재해야 할 이유가 사라지는 경우가 생긴다. 이때는 그 둘을 하나로 합쳐야 할 시점이다.

- - -

### 절차
1. 두 클래스 중 제거할 것을 고른다.
2. '필드 올리기'와 '메서드 올리기' 혹은 '필드 내리기'와 '메서드 내리기'를 적용하여 모든 요소를 하나의 클래스로 옮긴다.
3. 제거할 클래스를 참조하던 모든 코드가 남겨질 클래스로 참조하도록 한다.
4. 빈 클래스를 제거한다.
5. 테스트한다.
