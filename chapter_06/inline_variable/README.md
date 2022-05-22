## 변수 인라인하기 (Inline variable)

### as-is
```javascript
let basePrice = anOrder.basePrice;
return (basePrice > 1000);
```
### to-be
```javascript
return anOrder.basePrice > 1000;
```

* 변수는 함수 안에서 표현식을 가리키는 이름으로 쓰인다. 하지만 그 이름이 원래 표현식과 다를 바 없을 때도 있다.
* 변수가 주변 코드를 리팩터링하는 데 방해가 되기도 한다. 이럴 때는 그 변수를 인라인 하는 것이 좋다.

- - -

### 절차
* 대입문의 우변(표현식)에서 부작용이 생기지는 않는지 확인한다.
* 변수가 불변으로 선언되지 않았다면 불변으로 만든 후 테스트한다.
* 이 변수를 가장 처음 사용하는 코드를 찾아서 대입문 우변의 코드로 바꾼다.
* 테스트한다.
* 변수를 사용하는 부분을 모두 교체할 때까지 이 과정을 반복한다.
* 변수 선언문과 대입문을 지운다.
* 테스트한다.