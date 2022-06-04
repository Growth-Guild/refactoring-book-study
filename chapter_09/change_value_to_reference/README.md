## 값을 참조로 바꾸기 (Change Value to Reference)

### as-is
```javascript
let customer = new Customer(customerData);
```

### to-be
```javascript
let customer = customerRepository.get(customerData.id);
```

* 하나의 데이터 구조 안에 논리적으로 같은 제3의 데이터 구조를 참조하는 레코드가 여러 개 있을 때가 있다.
* 논리적으로 같은 데이터를 물리적으로 복제해 사용할 때 가장 크게 문제되는 상황은 그 데이터를 갱신할 때이다. 값 객체로 다루어진 데이터 구조는 갱신이 일어날 경우에 해당 복제본을 모두 찾아서 갱신해야 하기 때문이다.
* 이런 상황에서 값 객체를 참조로 바꿔주는 것이 좋다.

- - -

### 절차
1. 같은 부류에 속하는 객체들을 보관할 저장소를 만든다. (이미 있다면 생략)
2. 생성자에서 이 부류의 객체들 중 특정 객체를 정확히 찾아내는 방법이 있는지 확인한다.
3. 호스트 객체의 생성자들을 수정하여 필요한 객체를 이 저장소에서 찾도록 한다. 하나 수정할 때마다 테스트한다.