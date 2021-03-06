## 메서드 올리기 (Pull Up Method)

### as-is
```javascript
class Employee { /* ... */ }

class Salesperson extends Employee {
    get name() { /* ... */ }
}

class Engineer extends Employy {
    get name() { /* ... */ }
}
```

### to-be
```javascript
class Employee {
    get name() { /* ... */ }
}

class Salesperson extends Employee { /* ... */ }
class Engineer extends Employee { /* ... */ }
```

* 중복 코드는 두 메서드가 당장은 문제없이 동작할지라도 미래에는 버그를 만들어낼 가능성이 있다.
* 무언가 중복되었다는 것은 한쪽의 변경이 다른 쪽에는 반영되지 않을 수 있다는 위험을 항상 수반한다.
* 메서드 올리기 리팩토링을 적용하려면 선행 단계를 거쳐야 할 때가 많다.
  * 서로 다른 두 클래스의 두 메서드를 각각 매개변수화하면 궁극적으로 같은 메서드가 되기도 한다.
  * 메서드의 본문에서 참조하는 필드들이 서브클래스에만 있는 경우에는 해당 필드들을 먼저 슈퍼클래스로 올린 후에 메서드를 올려야 한다.
* 두 메서드의 전체 흐름은 비슷하지만 세부 내용이 다르다면 템플릿 메서드 만들기를 고려한다.

- - -

### 절차
1. 똑같이 동작하는 메서드인지 면밀히 살펴본다.
   * 실질적으로 하는 일은 같지만 코드가 다르다면 본문 코드가 똑같아질 때까지 리팩토링한다.
2. 메서드 안에서 호출하는 다른 메서드와 참조하는 필드들을 슈퍼클래스에서도 호출하고 참조할 수 있는지 확인한다.
3. 메서드 시그니처가 다르다면 '함수 선언 바꾸기'로 슈퍼클래스에서 사용하고 싶은 형태로 통일한다.
4. 슈퍼클래스에 새로운 메서드를 생성하고, 대상 메서드의 코드를 복사해넣는다.
5. 정적 검사를 수행한다.
6. 서브클래스 중 하나의 메서드를 제거한다.
7. 테스트한다.
8. 모든 서브클래스의 메서드가 없어질 때까지 다른 서브클래스의 메서드를 하나씩 제거한다.
