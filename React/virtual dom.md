DOM? → 웹 페이지를 이루는 태그들을 자바스크립트가 이요할 수 있게끔 브라우저가 트리구조로 만든 객체 모델

dom은 html과 js를 서로 이어주는 역할을 하고 있다.

### virtual dom의 존재 이유?

- 메모리 누수와 속도

  만일 개발자가 dom tree 깊숙한 곳에 h1태그를 생성했는데, 이를 변수에 저장하지 않고 매번 이 h1태그에 접근한다면 매 단계마다 수많은 document 객체들을 전부 훑으며 찾게 된다. 이는 곧 메모리의 비효율성으로 이어지게 되고, 혹시라도 이 h1 태그에서 변화가 일어나다면 css를 다시 연산하고 레이아웃을 구성하고 웹페이지를 다시 그려주는 데에서도 시간이 든다. 이런 과정이 컴포넌트를 하나하나 조작할 때마다 일어나게 된다.

- 코드량

  또 다른 이유로는 위의 저 h1이 속해 있는 객체를 찾기 위해 작성하는 코드가 번잡스러울 수 있다는 점이 있다. 고유성을 침해당하지 않기 위해 변수명도 계속 해서 고민해야 할 것이고, 메소드 자체의 길이도 길기 때문에 코드의 절대적인 양이 많아 질 수 있다.

위와 같은 이유들로 최소한의 dom조작을 통해 작업을 개선하고자 하여 가상돔이라는 개념을 도입한다.

### virtual dom?

`실제 돔의 사본 같은 개념`

리애트를 이용해서 돔을 업데이트 시키는 과정은 다음과 같다.

1. 변화를 인지하고 변화된 버전을 가상돔으로 바꾼다.
2. 데이터가 업데이트 되면 전체 UI를 가상돔에 리렌더링한다.
3. 변화 전의 가상돔과 변화된 가상돔을 비교한다.
4. 바뀐 부분을 실제 돔에 적용함으로써 레이아웃 계산은 한 번만 이행된다.
