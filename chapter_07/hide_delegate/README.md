## 위임 숨기기 (Hide Delegate)

### as-is
```javascript
manager = aPerson.department.manager;
```

### to-be
```javascript
manager = aPerson.manager;

class Person {
    get manager() {return this.department.manager;}
}
```

* 모듈화 설계의 핵심은 캡슐화다.
* 캡슐화는 모듈들이 시스템의 다른 부분에 대해 알아야 할 내용을 줄여준다.
* 캡슐화가 잘 되어 있다면 무언가를 변경해야 할 때 함께 고려해야 할 모듈의 수가 적어져서 코드를 변경하기가 수월해 진다.

- - -

### 절차
1. 위임 객체의 각 메서드에 해당하는 위임 메서드를 서버에 생성한다.
2. 클라이언트가 위임 객체 대신 서버를 호출하도록 수정한다. 하나씩 바꿀 때마다 테스트한다.
3. 모두 수정했다면, 서버로부터 위임 객체를 얻는 접근자를 제거한다.
4. 테스트한다.
