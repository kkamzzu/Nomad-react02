# `Start React`

- cd Desktop
- npx create-react-app (name:my-hompage)
- npm i prop-types

# `import css`

- import "./styles.css";
- import 하지 않으면 작동안함.

- css file을 index.js에 import시키지 않고 방법은 style.css를 사용하지않고, style prop을 사용한다.

```js
function Button({ text }) {
  return (
    <button
      style={{
        backgroundColor: "tomato",
        color: "white",
      }}
    >
      {text}
    </button>
  );
}
```

- 만약 우리가 전역적인 css style을 원하지 않고 위처럼 직접적으로 넣고싶지 않을때가 있음. ->CSS modules

- create-react-app으로 작업할 때의 포인트는 "분활하고" "정복하는" 것.

- css file 대신 Button.module.css 으로 변경

- change class

```css
.btn {
  color: white;
  background-color: tomato;
}
```

- 후에 Button.js에 import해줌.
- create-react-app은 이 css 코드를 javascript오브젝트로 변환시켜줌.

```js
import styles from "./Button.module.css";
```

- and 이 javascript 오브젝트는 btn을 안에 갖고 있는 것.

```js
function Button({ text }) {
  return <button className="{styles.btn}">{text}</button>;
}
```

- create-react-app이 랜덤하게 클라스네임을 바꿔주기 때문에 이제는 다른 클래스 네임들을 기억할 필요가 없음.
- 이제 컴포넌트를 분리해서 만들 수 있고, 그 컴포넌트를 위한 css만들수도 있음. (독립적인 형태)
- 같은 클래스 이름을 써도 html내에서는 렌덤 방식으로 생성이 됨.
