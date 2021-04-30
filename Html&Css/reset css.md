### reset css?

웹 브라우저마다 다른 스타일로로 지정 되어 있는 기본 값을 초기화 하고, 이를 통해 다양한 웹 브라우저에서도 동일한 스타일이 적용되도록 함

### how to use?

- normalize

  - cdn 기법을 통해 링크로 적용 시킬 수 있음([https://cdnjs.com/libraries/normalize](https://cdnjs.com/libraries/normalize))
  - <head>태그 안에 스크립트 추가 적용
  - normalize의 특징은 기본 스타일은 남겨두고, 브라우저별로 다른 스타일만 초기화(모든 효과를 reset 하지 않음)

  ```jsx
  <!DOCTYPE html>
  <html lang="en">
    <head>
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/normalize/8.0.1/normalize.min.css" />
    </head>
    <body></body>
  </html>
  ```

- import
  - reset css 파일을 import시키는 방법으로도 사용 가능
