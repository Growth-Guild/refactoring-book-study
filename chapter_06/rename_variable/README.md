## 변수 이름 바꾸기 (Rename variable)

### as-is
```javascript
let a = height * width;
```

### to-be
```javascript
let area = height * width;
```

* 변수는 프로그래머가 하려는 일에 관해 많은 것을 설명해준다. 단, 이름을 잘 지었을 때만 그렇다.
* 이름의 중요성은 그 사용 범위에 영향을 많이 받는다. 한 줄짜리 람다식에서 사용하는 변수는 대체로 쉽게 파악할 수 있다. 맥락으로부터 변수의 목적을 명확히 알 수 있어서 한 글자로 된 이름을 짓기도 한다.

- - -

### 절차
1. 폭널게 쓰이는 변수라면 변수 캡슐화하기를 고려한다.
2. 이름을 바꿀 변수를 참조하는 곳을 모두 찾아서, 하나씩 변경한다.
3. 테스트한다.