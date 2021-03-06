## 변수 추출하기 (Extract variable)
* 표현식이 너무 복잡해서 이해하기 어려울 때가 있는데, 이럴 때 지역 변수를 활용하면 표현식을 쪼개 관리하기 더 쉽게 만들 수 있다.
* 이 과정에서 추가한 변수는 디버거에 breakpoint를 지정하여 디버깅에 도움이 될 수 있다.
* 변수 추출을 고려한다고 함은 표현식에 이름을 붙이고 싶다는 뜻이다. 이름을 붙이기로 했다면 그 이름이 들어갈 문맥도 살펴야 한다.
  * 현재 함수 안에서만 의미가 있다면 변수로 추출하는 것이 좋다.
  * 함수를 벗어난 넓은 문맥에서까지 의미가 된다면 그 넓은 범위에서 통용되는 이름을 생각해야 한다. 이는 변수가 아닌 (주로) 함수로 추출해야 한다.
* 이름이 통용되는 문맥을 넓힐 때 생기는 단점은 할 일이 늘어난다는 것이다.

### 절차
1. 추출하려는 표현식에 부작용은 없는지 확인한다.
2. 불변 변수를 하나 선언하고 이름을 붙일 표현식의 복제본을 대입한다.
3. 원본 표현식을 새로 만든 변수로 교체한다.
4. 테스트한다.
5. 표현식을 여러 곳에서 사용한다면 각각을 새로 만든 변수로 교체한다. 하나 교체할 때마다 테스트한다.
