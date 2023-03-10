# 0309react

**React Component**

: 리액트에서는 **모든 페이지가 컴포넌트**로 구성되어 있고, 하나의 컴포넌트는 또 다른 여러개의 컴포넌트 조합으로 구성될 수 있다. (레고 블록 조립) / **작은 컴포넌트들이 모여서 하나의 컴포넌트를 구성하고 이런 컴포넌트들이 모여서 전체 페이지를 구성**한다. ⇒ 하나의 컴포넌트를 반복적으로 사용함으로써 전체 코드의 양이 줄고, 개발 시간과 유지보수 비용도 줄일 수 있다. 

### Component

1. **클래스 컴포넌트**
2. **함수 컴포넌트**

React 컴포넌트는 **함수형 컴포넌트**와 **클래스형 컴포넌트** 두 가지로 나눌 수 있다. 

- 리액트 초기 버전에서는 클래스 컴포넌트를 주로 사용했는데, 불편하다는 의견이 많아지면서 함수 컴포넌트를 개선해서 지금은 클래스 컴포넌트를 거의 사용하지 않는다.
- 함수 컴포넌트를 개선하는 과정에서 개발된 것이 바로 훅(Hook) 현재 리액트 개발에서는 거의 다 훅을 사용한다고 생각하면 된다.
- 컴포넌트의 이름은 항상 대문자로 시작해야 한다.

1. 반복적인 html 축약할 때’
2. 큰 페이지들
3. 자주 변경되는 HTML UI

⭐리액트 컴포넌트는 개념적으로 자바스크립트 함수와 비슷하다. 함수가 입력 받아서 출력하는 것처럼, 리액트 컴포넌트도 입력 받아서 정해진 출력을 내뱉는다. **리액트 컴포넌트를 하나의 함수라고 생각하면 쉬움**⭐

**Component를 사용하면 원하는 HTML을 한 단어로 줄일 수 있다!**

1. function을 이용해서 함수를 하나 만들어주고 작명 (대문자)

2. 그 함수 안에 return() 안에 축약을 원하는 HTML을 담는다.

3. 원하는 곳에서 **<함수명></함수명>** / **<함수명/>** 사용하면 축약한 HTML이 화면에 렌더링

이렇게 축약한 HTML 덩어리를 ‘**Component’** 라고 부른다.

> Component 만들 때 주의점
> 

1. component 작명할 땐 영어 대문자로 작명.

2. return () 안엔 html 태그들이 평행하게 여러개 들어갈 수 없다.

3. function App(){} 내부에서 만들면 안된다.

  ⇒ component 안에 component를 생성하지 않는다. 

4. **<컴포넌트></컴포넌트>** 이렇게 또는 **<컴포넌트/>** 이렇게 사용한다.

- 사이트에 반복해서 출현하는 HTML 덩어리
- 다른 페이지를 만들고 싶다면 그 페이지의 HTML 내용을 하나의 Component로 만든다.
- 협업할 때 페이지를 Component 단위로 나눠서 작업을 분배

1. **함수형 컴포넌트 (Functional Component)**
- 함수를 통해 컴포넌트를 정의한다.
- React Hooks이 도입되면서 기능이 많아져서 복잡한 UI도 만들 수 있다.

```jsx
// 함수형 컴포넌트 예시
function MyComponent(props) {
  return <h1>Hello, {props.name}!</h1>;
}
```

1. **클래스형 컴포넌트 (Class Component)**
- ES6의 클래스 문법을 사용하여 컴포넌트를 정의한다.
- 예전에는 주로 사용했으나, 현재는 잘 사용하지 않는다.

```jsx
import React, { Component } from 'react';

class Hello extends Component {
  render() {
    return <div>Hello, {this.props.name}!</div>;
  }
}
```

컴포넌트를 사용할 때는, 해당 컴포넌트를 import하여 JSX 문법 안에서 사용한다

```jsx
import React from 'react';
import Hello from './Hello';

function App() {
  return (
    <div>
      <Hello name="John" />
      <Hello name="Jane" />
    </div>
  );
}

export default App;
```

컴포넌트를 만들어 재사용할 수 있기 때문에, 코드의 재사용성이 좋아진다. 또한 **컴포넌트 단위로 코드를 작성하면, 유지보수가 용이해지고, 코드의 가독성이 좋아진다.**

React 컴포넌트를 다른 파일에서 사용하려면 해당 컴포넌트를 불러와야 한다. 이를 위해 **import Comment from "./Comment";**키워드를 사용한다. **`import`**키워드를 이용해 다른 파일에서 정의된 컴포넌트를 현재 파일에서 불러올 수 있다.

```jsx
import Comment from "./Comment";
```

**html덩어리를 하나의  component 로 만드는 방법**

1. function을 만든다 (위치 중요!) 다른 함수 바깥에 만들어야 한다. 작명 할 때는 영어 대문자 사용! 
2. return( ) 안에 html 담기 /return안에서는 꼭 하나의 태그로 시작해서 하나의 태그로 끝나야 한다!
3. 한 단어로 축약한 함수 이름을 컴포넌트라고 한다.
4. 사용하고 싶은 곳에서 html 태그 형식으로 사용한다.

return( ) 안에 html을 병렬 기입 하고 싶다면

1. 두 개를 만들고 한 번 더 전체를 감싸준다
2. 의미없는 div 사용하기 싫다면 ⇒ < > </> 사용(리액트 상의 문법 **Fragment**

- React는 컴포넌트 기반으로 동작하며, 각 컴포넌트는 자체적으로 관리되는 상태와 props(속성)를 가질 수 있다.
- 컴포넌트로 재사용성을 높이고 코드를 간결하게 유지할 수 있다. 컴포넌트는 클래스 기반 컴포넌트와 함수 기반 컴포넌트가 있다.
- props와 state를 사용하여 컴포넌트의 데이터를 관리한다. props는 상위 컴포넌트에서 하위 컴포넌트로 전달된다. state는 컴포넌트 내부에서 관리되며 변경될 때 컴포넌트가 재렌더링 된다.
