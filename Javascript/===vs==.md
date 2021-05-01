### == : Equality

자바스크립트에서 == 연산자를 사용하게 되면 연산이 되기 전에 피연산자들을 먼저 비교할 수 있는 형태로 변환시킨다.

```jsx
254 == "254"; // return true
true == 1; // return true
undefined == null; // return true
"abc" == new String("abc"); // return true
null == false; // return false
"true" == true; // return false
true == 2; // return false
```

위와 같은 결과가 나오기 때문에 정확한 결과를 원하는 코드에서는 적합하지 않다.

### === : Identity

```jsx
254 === "254"; // return false
true === 1; // return false
undefined === null; // return false
"abc" === new String("abc"); // return false
```

===연산자는 ==보다 더 strict 하게 연산을 비교한다.

값 뿐만이 아닌 타입까지 놓고 비교 하기 때문에 정확한 연산을 필요로 할 때 사용한다.
