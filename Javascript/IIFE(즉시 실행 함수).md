## IIFE 즉시실행함수

`IIFE : Immediately-invoked function expression`

글로벌 스코프에 정의 된 것은 코드 내의 어디서든지 접근이 가능하다는 문제는 자바스크립트를 이용 할 때, 가장 큰 문제점으로 여겨졌다. 이런 경우 외부에 공유되면 안되거나 공유 될 필요가 없는 속성, 메소드들이 노출 되는 문제가 발생한다. 또한, 다른 스크립트 파일 내에 동일한 이름으로 명명된 함수나 변수가 있을 경우 사이드 이펙트가 생기게 된다.

---

```jsx
//함수표현식
var app = function () {
  console.log("함수 호출"); // "함수 호출" 출력
};
app();
```

```jsx
//즉시실행함수
(function () {
  console.log("함수 호출"); // "함수 호출" 출력
})();
```

위의 코드들은 같은 동작을 수행하게 된다.

함수 표현식은 함수를 정의하고, 변수에 함수를 저장하는 과정을 거치게 된다. 즉시실행함수는 이와 같이 변수에 함수를 저장하는 과정을 거치지 않고 바로 실행된다.

```jsx
var app = (function () {
  var privateVar = "private";
  return {
    prop: privateVar,
  };
})();
console.log(app.prop); // "private" 출력
```

위와 같은 코드에서는 함수 외부에서도 즉시실행함수 내에서 선언한 변수에 접근 가능한 것을 확인할 수 있다. 즉시실행함수는 변수의 스코프를 포함하는데 사용되며 외부에서 함수내의 변수에 접근할 경우 이를 통제할 수 있기 때문이다.
