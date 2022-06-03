## 반복문을 파이프라인으로 바꾸기 (Replace Loop with Pipeline)

### as-is
```javascript
const names = [];
for (const i of input) {
    if (i.job === 'programmer')
        names.push(i.name);
}
```

### to-be
```javascript
const names = input
    .filter(i => i.job === 'programmer')
    .map(i => i.name);
```

* 컬렉션 파이프라인을 이용하면 처리 과정을 일련의 연산으로 표현할 수 있다.
* 논리를 파이프라인으로 표현하면 이해하기 쉬워진다. 객체가 파이프라인을 따라 흐르며 어떻게 처리되는지 읽을 수 있기 때문이다.

- - -

### 절차
1. 반복문에서 사용하는 컬렉션을 가리키는 변수를 하나 만든다.
2. 반복문의 첫 줄에서 시작해서, 각각의 단위 행위를 적절한 컬렉션 파이프라인 연산으로 대체한다. 이 때 컬렉션 파이프라인 연산은 1에서 만든 반복문 컬렉션 변수에서 시작하며, 이전 연산의 결과를 기초로 연쇄적으로 수행한다. 하나를 대체할 때마다 테스트한다.
3. 반복문의 모든 동작을 대체했다면 반복문 자체를 지운다.